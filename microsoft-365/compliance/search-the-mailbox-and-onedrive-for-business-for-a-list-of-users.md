---
title: メールボックス & OneDrive for Business サイト上のユーザーの一覧にコンテンツ検索を使用する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: コンテンツ検索とこの記事のスクリプトを使用して、メールボックスとOneDrive for Businessサイトでユーザー グループを検索します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 838e565d385077416d1001afc02e1aceeebb5188
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66011632"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーのリストを探す

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Security & Compliance PowerShell には、時間のかかる電子情報開示関連のタスクを自動化できるコマンドレットが多数用意されています。 現在、Microsoft Purview コンプライアンス ポータルでコンテンツ検索を作成して多数のカストディアン コンテンツの場所を検索するには、時間と準備が必要です。 検索を作成する前に、各OneDrive for Business サイトの URL を収集し、各メールボックスとOneDrive for Business サイトを検索に追加する必要があります。 今後のリリースでは、コンプライアンス ポータルで行う方が簡単になります。 それまでは、この記事のスクリプトを使用して、このプロセスを自動化できます。 このスクリプトでは、組織の MySite ドメインの名前 (URL `https://contoso-my.sharepoint.com`内の **contoso** など)、ユーザーの電子メール アドレスの一覧、新しいコンテンツ検索の名前、使用する検索クエリの入力を求めるメッセージが表示されます。 スクリプトは、リスト内の各ユーザーのOneDrive for Business URL を取得し、指定した検索クエリを使用して、メールボックスとOneDrive for Business サイトを検索するコンテンツ検索を作成して開始します。

## <a name="permissions-and-script-information"></a>アクセス許可とスクリプト情報

- 手順 3 でスクリプトを実行するには、コンプライアンス ポータルの電子情報開示マネージャーロール グループのメンバーであり、SharePoint Online グローバル管理者である必要があります。

- 手順 2 で作成したユーザーの一覧と手順 3 のスクリプトを同じフォルダーに保存してください。 そうすることで、スクリプトを簡単に実行できるようになります。

- このスクリプトには、最小限のエラー処理が含まれています。 その主な目的は、各ユーザーのメールボックスとOneDrive for Business サイトをすばやく簡単に検索することです。

- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする

最初の手順では、SharePoint Online Management Shell をインストールします。 この手順ではシェルを使用する必要はありませんが、手順 3 で実行するスクリプトに必要な前提条件が含まれているため、シェルをインストールする必要があります。 これらの前提条件により、スクリプトは SharePoint Online と通信して、OneDrive for Business サイトの URL を取得できます。

[SharePoint Online Management Shell 環境のセットアップ](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)に移動し、手順 1 と手順 2 を実行して、SharePoint Online Management Shell をインストールします。

## <a name="step-2-generate-a-list-of-users"></a>手順 2: ユーザーの一覧を生成する

手順 3 のスクリプトでは、メールボックスを検索するコンテンツ検索を作成し、ユーザーの一覧をOneDriveアカウントを作成します。 テキスト ファイルに電子メール アドレスを入力するか、PowerShell でコマンドを実行して電子メール アドレスの一覧を取得し、ファイルに保存することができます (手順 3 でスクリプトを保存するのと同じフォルダーにあります)。

組織内のすべてのユーザーの電子メール アドレスの一覧を取得し、それをという名前`Users.txt`のテキスト ファイルに保存するために実行できる [powerShell](/powershell/exchange/connect-to-exchange-online-powershell) のExchange Onlineコマンドを次に示します。

```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

このコマンドを実行した後、ファイルを開き、プロパティ名  `PrimarySmtpAddress`を含むヘッダーを削除してください。 テキスト ファイルには、電子メール アドレスの一覧のみを含める必要があります。それ以外のアドレスは含まれません。 電子メール アドレスの一覧の前後に空白行がないことを確認します。

## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>手順 3: スクリプトを実行して検索を作成して開始する

この手順でスクリプトを実行すると、次の情報を求めるメッセージが表示されます。 スクリプトを実行する前に、必ずこの情報を準備しておいてください。

- **ユーザー資格情報** - このスクリプトでは、資格情報を使用してSharePoint Online にアクセスし、OneDrive for Business URL を取得し、Security & Compliance PowerShell に接続します。

- **MySite ドメインの名前** - MySite ドメインは、組織内のすべてのOneDrive for Business サイトを含むドメインです。 たとえば、MySite ドメインの URL が [MySite] ドメインの場合、 **https://contoso-my.sharepoint.com** スクリプトから MySite ドメインの名前の入力を求められたときに入力  `contoso` します。

- **手順 2 のテキスト ファイルのパス名 - 手順 2** で作成したテキスト ファイルのパス名。 テキスト ファイルとスクリプトが同じフォルダーにある場合は、テキスト ファイルの名前を入力します。 それ以外の場合は、テキスト ファイルの完全なパス名を入力します。

- **コンテンツ検索の名前** - スクリプトによって作成されるコンテンツ検索の名前。

- **検索クエリ** - コンテンツ検索で使用される検索クエリが作成され、実行されます。 検索クエリの詳細については、「 [電子情報開示のキーワード クエリと検索条件」を](keyword-queries-and-search-conditions.md)参照してください。

**このスクリプトを実行するには、以下の手順を実行します。**

1. 次のテキストをWindows PowerShell スクリプト ファイルに保存するには、.ps1 のファイル名サフィックスを使用します。たとえば、 `SearchEXOOD4B.ps1`. 手順 2 でユーザーの一覧を保存したのと同じフォルダーにファイルを保存します。

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
   # Connect to Security & Compliance PowerShell
   if (!$s -or !$a)
   {
       Import-Module ExchangeOnlineManagement
       Connect-IPPSSession
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

2. Windows PowerShell開き、手順 2. のスクリプトとユーザーの一覧を保存したフォルダーに移動します。

3. スクリプトを開始します。例えば：

    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. 資格情報の入力を求められたら、メール アドレスとパスワードを入力し、[OK] をクリック **します**。

5. スクリプトの入力を求められたら、次の情報を入力します。 各情報を入力し、Enter キーを押 **します**。

    - MySite ドメインの名前。

    - ユーザーの一覧を含むテキスト ファイルのパス名。

    - コンテンツ検索の名前。

    - 検索クエリ (コンテンツの場所内のすべてのアイテムを返すには、この空白のままにします)。

    このスクリプトは、各OneDrive for Business サイトの URL を取得し、検索を作成して開始します。 Security & Compliance PowerShell で **Get-ComplianceSearch** コマンドレットを実行して検索の統計情報と結果を表示するか、コンプライアンス ポータルの **コンテンツ検索** ページに移動して検索に関する情報を表示できます。
