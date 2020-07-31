---
title: コンテンツ検索を使用するユーザーの一覧については、メールボックス & OneDrive for Business サイトを検索します。
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: コンテンツ検索とこの記事のスクリプトを使用して、ユーザーのグループのメールボックスと OneDrive for Business サイトを検索します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90aab661992ae2f0c19d18939191230dc0469eaa
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527363"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーのリストを探す

セキュリティ & コンプライアンスセンターでは、時間がかかる電子情報開示関連のタスクを自動化するための Windows PowerShell コマンドレットが多数提供されています。 現在、セキュリティ & コンプライアンスセンターでコンテンツ検索を作成して、大量の保管担当者コンテンツの場所を検索するには時間と準備がかかります。 検索を作成する前に、各 OneDrive for Business サイトの URL を収集し、各メールボックスと OneDrive for Business サイトを検索に追加する必要があります。 今後のリリースでは、これはセキュリティ & コンプライアンスセンターで行うのが容易になります。 その後、この記事のスクリプトを使用してこのプロセスを自動化できます。 このスクリプトは、組織の個人用サイトドメインの名前 (たとえば、URL 内の**contoso** `https://contoso-my.sharepoint.com` )、ユーザーの電子メールアドレスの一覧、新しいコンテンツ検索の名前、使用する検索クエリを入力するように求めます。 このスクリプトは、リスト内の各ユーザーの OneDrive for Business URL を取得し、ユーザーが指定した検索クエリを使用して、リスト内の各ユーザーのメールボックスと OneDrive for Business サイトを検索するコンテンツ検索を作成して開始します。
  
## <a name="permissions-and-script-information"></a>アクセス許可とスクリプト情報

- 手順3でスクリプトを実行するには、セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。また、SharePoint Online のグローバル管理者である必要があります。

- 手順2で作成したユーザーの一覧と、手順3のスクリプトを同じフォルダーに保存するようにしてください。 これにより、スクリプトをより簡単に実行できるようになります。

- スクリプトには、最小限のエラー処理が含まれています。 その主な目的は、各ユーザーのメールボックスと OneDrive for Business サイトをすばやく簡単に検索することです。

- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする

最初の手順として、SharePoint Online 管理シェルをインストールします。 この手順でシェルを使用する必要はありませんが、手順3で実行するスクリプトに必要な前提条件が含まれているためインストールする必要があります。 これらの前提条件によって、スクリプトは SharePoint Online と通信して、OneDrive for Business サイトの Url を取得できます。
  
「 [Sharepoint Online 管理シェル Windows PowerShell 環境をセットアップ](https://go.microsoft.com/fwlink/p/?LinkID=286318)する」に移動し、手順1と手順2を実行して、Sharepoint Online 管理シェルをインストールします。
  
## <a name="step-2-generate-a-list-of-users"></a>手順 2: ユーザーのリストを生成する

手順3のスクリプトは、メールボックスと OneDrive アカウントでユーザーのリストを検索するコンテンツ検索を作成します。 テキストファイルに電子メールアドレスを入力することも、Windows PowerShell でコマンドを実行して電子メールアドレスの一覧を取得し、それをファイルに保存することもできます (手順3でスクリプトを保存するのと同じフォルダーに格納されます)。
  
次の[Exchange Online の PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)コマンドでは、を実行して、組織内のすべてのユーザーの電子メールアドレスの一覧を取得し、それをという名前のテキストファイルに保存することができ `Users.txt` ます。 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

このコマンドを実行した後、必ずファイルを開いて、プロパティ名を含むヘッダーを削除してください `PrimarySmtpAddress` 。 テキストファイルには、電子メールアドレスのリストのみを含める必要があります。それ以外の場合は何も指定しないでください。 電子メールアドレスのリストの前または後に空白行がないことを確認します。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>手順 3: スクリプトを実行して検索を作成および開始する

この手順でスクリプトを実行すると、次の情報を入力するように求めるメッセージが表示されます。 スクリプトを実行する前に、この情報を用意しておいてください。
  
- **ユーザーの資格情報**-スクリプトは、自分の資格情報を使用して SharePoint Online にアクセスして、OneDrive for Business の url を取得し、リモート PowerShell を使用してセキュリティ & コンプライアンスセンターに接続します。 
    
- **個人用サイトのドメインの名前**-個人用サイトのドメインは、組織内のすべての OneDrive for business サイトを含むドメインです。 たとえば、個人用サイトのドメインの URL がの場合は、 **https://contoso-my.sharepoint.com** スクリプトによって、 `contoso` 個人用サイトのドメインの名前を入力するように求めるメッセージが表示されます。 
    
- **手順2のテキストファイルのパス名**。手順2で作成したテキストファイルのパス名。 テキストファイルとスクリプトが同じフォルダーにある場合は、テキストファイルの名前を入力します。 それ以外の場合は、テキストファイルの完全なパス名を入力します。 
    
- **コンテンツ検索の名前**-スクリプトによって作成されるコンテンツ検索の名前。 
    
- **検索クエリ**-コンテンツ検索と共に使用される検索クエリが作成され、実行されます。 検索クエリの詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。


**このスクリプトを実行するには、以下の手順を実行します。**
    
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、のように `SearchEXOOD4B.ps1` なります。 手順2でユーザーのリストを保存したのと同じフォルダーにファイルを保存します。
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. Windows PowerShell を開き、スクリプトを保存したフォルダーおよび手順2でユーザーのリストに移動します。
    
3. スクリプトを開始します。例えば：
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. 資格情報の入力を求められたら、電子メールアドレスとパスワードを入力し、[ **OK]** をクリックします。 
    
5. スクリプトによってプロンプトが表示されたら、次の情報を入力します。 各情報を入力し **、enter キーを押します。**
    
    - 個人用サイトのドメインの名前。 
    
    - ユーザーのリストを含むテキストファイルのパス名。
    
    - コンテンツ検索の名前を指定します。
    
    - 検索クエリ (空白のままにすると、コンテンツの場所にあるすべてのアイテムが返されます)。
    
    このスクリプトは、各 OneDrive for Business サイトの Url を取得し、検索を作成して開始します。 セキュリティ & コンプライアンスセンターの PowerShell で**new-compliancesearch**コマンドレットを実行して、検索の統計と結果を表示するか、またはセキュリティ & コンプライアンスセンターの**コンテンツ検索**ページに移動して、検索に関する情報を表示することができます。 
