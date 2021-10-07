---
title: コンテンツ検索を使用& OneDrive for Businessのメールボックス を検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: コンテンツ検索とこの記事のスクリプトを使用して、メールボックスを検索し、OneDrive for Businessのサイトを検索します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12a97cddaa26fbd6f63f9af60bcebe9105b970ec
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197463"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーのリストを探す

セキュリティ & コンプライアンス センター PowerShell には、時間のかかる電子情報開示関連のタスクを自動化できる多数のコマンドレットがあります。 現在、多数の保管担当者コンテンツの場所Microsoft 365 コンプライアンス センターするコンテンツ検索を作成するには、時間と準備が必要です。 検索を作成する前に、各サイトの URL をOneDrive for Businessし、各メールボックスとサイトOneDrive for Businessを検索に追加する必要があります。 今後のリリースでは、この操作は簡単に行えるMicrosoft 365 コンプライアンス センター。 それまでは、この記事のスクリプトを使用して、このプロセスを自動化できます。 このスクリプトでは、組織の MySite ドメインの名前 (URL の **contoso** など)、ユーザーの電子メール アドレスの一覧、新しいコンテンツ検索の名前、および使用する検索クエリを求めるメッセージが表示されます。 `https://contoso-my.sharepoint.com` スクリプトは、リスト内の各ユーザーの OneDrive for Business URL を取得し、指定した検索クエリを使用して、リスト内の各ユーザーのメールボックスと OneDrive for Business サイトを検索するコンテンツ検索を作成して開始します。
  
## <a name="permissions-and-script-information"></a>アクセス許可とスクリプト情報

- 手順 3 でスクリプトを実行するには、Microsoft 365 コンプライアンス センター および SharePoint Online グローバル管理者の電子情報開示マネージャー役割グループのメンバーである必要があります。

- 手順 2 で作成したユーザーの一覧と、手順 3 のスクリプトを同じフォルダーに保存してください。 そうすると、スクリプトの実行が容易になります。

- スクリプトには、最小限のエラー処理が含まれています。 その主な目的は、各ユーザーのメールボックスとサイトOneDrive for Business簡単に検索することです。

- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする

最初の手順は、オンライン管理シェルSharePointインストールします。 この手順ではシェルを使用する必要はありません。ただし、手順 3 で実行するスクリプトに必要な前提条件が含まれているため、インストールする必要があります。 これらの前提条件により、スクリプトは SharePoint Online と通信して、サイトの URL をOneDrive for Businessできます。
  
[オンライン[管理シェル](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)のセットアップ] SharePointに移動しWindows PowerShell手順 1 と手順 2 を実行して、オンライン管理シェルSharePointインストールします。
  
## <a name="step-2-generate-a-list-of-users"></a>手順 2: ユーザーの一覧を生成する

手順 3 のスクリプトでは、コンテンツ検索を作成して、メールボックスを検索し、ユーザーのOneDriveアカウントを検索します。 テキスト ファイルに電子メール アドレスを入力するか、Windows PowerShell でコマンドを実行して電子メール アドレスの一覧を取得し、ファイルに保存できます (手順 3 でスクリプトを保存するフォルダーと同じフォルダーにあります)。
  
組織内のすべてのユーザー Exchange Onlineの電子メール アドレスの一覧を取得し、それをという名前のテキスト ファイルに保存するために実行できる[PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)コマンドを次に示します `Users.txt` 。 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

このコマンドを実行した後、必ずファイルを開き、プロパティ名を含むヘッダーを削除します  `PrimarySmtpAddress` 。 テキスト ファイルには、メール アドレスの一覧が含まれているだけで、それ以外は含めずにしてください。 電子メール アドレスの一覧の前または後に空白行が表示されません。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>手順 3: スクリプトを実行して検索を作成して開始する

この手順でスクリプトを実行すると、次の情報を求めるメッセージが表示されます。 スクリプトを実行する前に、この情報を準備してください。
  
- **ユーザー資格情報**- スクリプトは資格情報を使用して SharePoint Online にアクセスして OneDrive for Business URL を取得し、セキュリティ & コンプライアンス センター PowerShell に接続します。 
    
- **MySite ドメインの名前**- MySite ドメインは、組織内のすべてのサイトOneDrive for Business含むドメインです。 たとえば、MySite ドメインの URL が次の場合は、MySite ドメインの名前を求めるメッセージがスクリプトに表示されたら **https://contoso-my.sharepoint.com**  `contoso` 入力します。 
    
- **手順 2 のテキスト ファイル** のパス名 - 手順 2 で作成したテキスト ファイルのパス名。 テキスト ファイルとスクリプトが同じフォルダーにある場合は、テキスト ファイルの名前を入力します。 それ以外の場合は、テキスト ファイルの完全なパス名を入力します。 
    
- **コンテンツ検索の名前** - スクリプトによって作成されるコンテンツ検索の名前。 
    
- **検索クエリ** - コンテンツ検索で使用される検索クエリが作成され、実行されます。 検索クエリの詳細については、「電子情報開示のキーワード クエリと [検索条件」を参照してください](keyword-queries-and-search-conditions.md)。


**このスクリプトを実行するには、以下の手順を実行します。**
    
1. ファイル名のサフィックスを使用してWindows PowerShellスクリプト ファイルに次のテキストを保存.ps1。たとえば、 `SearchEXOOD4B.ps1` . 手順 2 でユーザーの一覧を保存したのと同じフォルダーにファイルを保存します。
    
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

2. [Windows PowerShellを開き、手順 2 からスクリプトとユーザーの一覧を保存したフォルダーに移動します。
    
3. スクリプトを開始します。例えば：
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. 資格情報の入力を求めるメッセージが表示されたら、メール アドレスとパスワードを入力し **、[OK] をクリックします**。 
    
5. スクリプトの指示に従って、次の情報を入力します。 各情報を入力し、Enter キーを **押します**。
    
    - MySite ドメインの名前。 
    
    - ユーザーのリストを含むテキスト ファイルのパス名。
    
    - コンテンツ検索の名前。
    
    - 検索クエリ (コンテンツの場所のすべてのアイテムを返す場合は、この空白のままにします)。
    
    スクリプトは、各サイトの URL をOneDrive for Businessし、検索を作成して開始します。 セキュリティ & コンプライアンス センター PowerShell で **Get-ComplianceSearch** コマンドレットを実行して検索の統計情報と結果を表示するか、Microsoft 365 コンプライアンス センター の[コンテンツ検索] ページに移動して検索に関する情報を表示できます。
