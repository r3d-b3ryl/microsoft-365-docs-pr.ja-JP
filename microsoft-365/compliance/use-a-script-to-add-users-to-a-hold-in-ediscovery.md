---
title: セキュリティ & コンプライアンスセンターのコア電子情報開示ケースで、スクリプトを使用してユーザーを保留リストに追加する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられた新しい保留リストにメールボックス & OneDrive for Business サイトを追加するスクリプトを実行する方法について説明します。
ms.openlocfilehash: 454fd4ea4517a46410c9d0922cc83b141fdbd893
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357677"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>スクリプトを使用して、コア電子情報開示ケースの保留リストにユーザーを追加する

セキュリティ & コンプライアンスセンターでは、電子情報開示ケースの作成と管理に関連する時間のかかるタスクを自動化できる PowerShell コマンドレットが提供されています。 現時点では、セキュリティ & コンプライアンスセンターで電子情報開示ケースツールを使用して、大量の保管担当者コンテンツの場所を保持することにより、時間と準備がかかります。 たとえば、ホールドを作成する前に、保留にする各 OneDrive for Business サイトの URL を収集する必要があります。 その後、保持するユーザーごとに、メールボックスとその OneDrive for Business サイトを保留リストに追加する必要があります。 セキュリティ & コンプライアンスセンターの今後のリリースでは、この操作が簡単になりました。 その後、この記事のスクリプトを使用してこのプロセスを自動化できます。
  
スクリプトによって、組織の個人用サイトのドメインの名前 (たとえば、URL 内の **contoso** 、 https://contoso-my.sharepoint.com) 既存の電子情報開示ケースの名前、ケースに関連付けられた新しい保留の名前、保留するユーザーの電子メールアドレスのリスト、クエリベースの保持を作成する場合に使用する検索クエリ) の入力を求められます。 次に、スクリプトは、リスト内の各ユーザーの OneDrive for Business サイトの URL を取得し、新しいホールドを作成して、リスト内の各ユーザーのメールボックスと OneDrive for business サイトを保留リストに追加します。 このスクリプトは、新しいホールドに関する情報を含むログファイルも生成します。
  
これを行うには、以下の手順を実行します。
  
[手順 1: SharePoint Online 管理シェルをインストールする](#step-1-install-the-sharepoint-online-management-shell)
  
[手順 2: ユーザーのリストを生成する](#step-2-generate-a-list-of-users)
  
[手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>ユーザーを保留リストに追加する前に

- 手順3でスクリプトを実行するには、セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。また、SharePoint Online 管理者である必要があります。 詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。

- セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられている保留リストには、最大1000のメールボックスと100サイトを追加できます。 保持するユーザーに OneDrive for Business サイトが含まれている場合は、この記事のスクリプトを使用して、最大100ユーザーを保留リストに追加できます。

- 手順2で作成したユーザーの一覧と、手順3のスクリプトを同じフォルダーに保存するようにしてください。 これにより、スクリプトをより簡単に実行できるようになります。

- このスクリプトは、既存のケースに関連付けられている新しいホールドにユーザーのリストを追加します。 このスクリプトを実行する前に、保持を関連付けるケースを作成しておく必要があります。

- スクリプトを実行するたびに、新しいセキュリティ & コンプライアンス PowerShell および SharePoint Online PowerShell セッションが作成されます。 そのため、使用可能なすべての PowerShell セッションを使用できます。 この問題が発生しないようにするには、次のコマンドを実行して、アクティブな PowerShell セッションを切断することができます。

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

   ```powershell
   Disconnect-SPOService
   ```

- スクリプトには、最小限のエラー処理が含まれています。 その主な目的は、各ユーザーのメールボックスと OneDrive for business サイトを保持して、すばやく簡単に配置できるようにすることです。

- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする

最初の手順として、SharePoint Online 管理シェルがローカルコンピューターにまだインストールされていない場合はインストールします。 この手順でシェルを使用する必要はありませんが、手順3で実行するスクリプトに必要な前提条件が含まれているためインストールする必要があります。 これらの前提条件によって、スクリプトは SharePoint Online と通信して、OneDrive for Business サイトの Url を取得できます。
  
「 [Sharepoint Online 管理シェル Windows PowerShell 環境をセットアップ](https://go.microsoft.com/fwlink/p/?LinkID=286318) する」に移動し、手順1と手順2を実行して、ローカルコンピューターに Sharepoint Online 管理シェルをインストールします。 

## <a name="step-2-generate-a-list-of-users"></a>手順 2: ユーザーのリストを生成する

手順3のスクリプトは、電子情報開示ケースに関連付けられているホールドを作成し、ユーザーのリストのメールボックスと OneDrive for Business サイトを保留リストに追加します。 テキストファイルに電子メールアドレスを入力することも、Windows PowerShell でコマンドを実行して電子メールアドレスの一覧を取得し、それをファイルに保存することもできます (手順3でスクリプトを保存するのと同じフォルダーに格納されます)。
  
次に示すのは、PowerShell コマンド (Exchange Online 組織に接続されたリモート PowerShell を使用して実行する) で、組織内のすべてのユーザーの電子メールアドレスの一覧を取得し、それを HoldUsers.txt という名前のテキストファイルに保存することです。
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

このコマンドを実行した後、テキストファイルを開いて、プロパティ名を含むヘッダーを削除し  `PrimarySmtpAddress` ます。 その後、手順3で作成するホールドに追加するユーザーのメールアドレス以外のすべてのメールアドレスを削除します。 電子メールアドレスのリストの前または後に空白行がないことを確認します。
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する

この手順でスクリプトを実行すると、次の情報を入力するように求めるメッセージが表示されます。 スクリプトを実行する前に、この情報を用意しておいてください。
  
- **ユーザーの資格情報:** このスクリプトは、資格情報を使用して、リモート PowerShell を使用してセキュリティ & コンプライアンスセンターに接続します。 また、これらの資格情報を使用して SharePoint Online にアクセスし、ユーザーリストの OneDrive for Business Url を取得します。

- **個人用サイトのドメインの名前:** 個人用サイトのドメインは、組織内のすべての OneDrive for Business サイトを含むドメインです。 たとえば、個人用サイトのドメインの URL がの場合は、 **https://contoso-my.sharepoint.com**  `contoso` スクリプトで個人用サイトのドメインの名前の入力を求められたときに入力します。

- **ケースの名前:** 既存のケースの名前。 このスクリプトは、このケースに関連付けられている新しいホールドを作成します。

- **保留の名前:** スクリプトが作成し、指定されたケースに関連付けられているホールドの名前。

- **クエリベースの保持の検索クエリ:** クエリベースの保持を作成して、指定した検索条件に一致するコンテンツのみを保持することができます。 すべてのコンテンツを保持するには、検索クエリの入力を求められたときに **enter** キーを押します。

- **保留をオンまたはオフにします。** スクリプトを作成した後でホールドを有効にしたり、スクリプトで保持を有効にせずにホールドを作成したりすることができます。 スクリプトでホールドをオンにしていない場合は、後でセキュリティ & コンプライアンスセンターで有効にするか、次の PowerShell コマンドを実行します。

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **ユーザーのリストを含むテキストファイルの名前** -手順2で保留に追加するユーザーの一覧が含まれているテキストファイルの名前。 このファイルがスクリプトと同じフォルダーにある場合は、ファイルの名前 (たとえば、HoldUsers.txt) を入力するだけです。 テキストファイルが別のフォルダーにある場合は、ファイルの完全なパス名を入力します。

スクリプトが要求する情報を収集したら、最後の手順として、スクリプトを実行して新しいホールドを作成し、それにユーザーを追加します。
  
1. ファイル名サフィックスを使用して、次のテキストを Windows PowerShell スクリプトファイルに保存 `.ps1` します。 たとえば、`AddUsersToHold.ps1` などです。

   ```powershell
   #script begin
   " " 
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
   write-host "***********************************************"
   " " 
   # Get user credentials &amp; Connect to Office 365 SCC, SPO
   $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
   $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
   $a = Import-PSSession $s -AllowClobber
       if (!$s)
       {
           Write-Error "Couldn't create PowerShell session."
           return;
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
           Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
           return;
       }
   }
   if (!$spCreds)
   {
       $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
   }
   # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
   ""
   $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
   ""
   # Get other required information
   do{
   $casename = Read-Host "Enter the name of the case"
   $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
   if($caseexists -ne 'True')
   {""
   write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
   ""}
   }While($caseexists -ne 'True')
   ""
   do{
   $holdName = Read-Host "Enter the name of the new hold"
   $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
   if($holdexists -eq 'True')
   {""
   write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
   ""}
   }While($holdexists -eq 'True')
   ""
   $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
   ""
   $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
   do{
   ""
   $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
   ""
   $fileexists = test-path -path $inputfile
   if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
   }while($fileexists -ne 'True')
   #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
       #in the list are unique.
     [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
     [int]$dupl = $emailAddresses.count
     [array]$emailAddresses = $emailAddresses | select-object -unique
     $dupl -= $emailAddresses.count
   #Validate email addresses so the hold creation does not run in to an error.
   if($emailaddresses.count -gt 0){
   write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
   ""
   Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
   ""
   $finallist =@()
   foreach($emailAddress in $emailAddresses)
   {
   if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
   {$finallist += $emailaddress}
   else {"Unable to find the user $emailaddress"
   [array]$excludedlist += $emailaddress}
   }
   ""
   #find user's OneDrive Site URL using email address
   Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
   ""
   $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
   $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
   $urls = @()
   foreach($emailAddress in $emailAddresses)
   {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
   }
   if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
   ""
   Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
   if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
   }
   else{
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
   }
   ""
   }
   else {"No valid locations were identified. Therefore, the hold wasn't created."}
   #write log files (if needed)
   $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
   $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
   if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
   {
   Write-Host "Generating output files..." -foregroundColor Yellow
   if($ODAdded.count -gt 0){
   "OneDrive Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
   if($ODExluded.count -gt 0){ 
   "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
   "================================" | add-content .\LocationsNotOnHold.txt
   $ODExluded | add-content .\LocationsNotOnHold.txt}
   if($finallist.count -gt 0){
   " " | add-content .\LocationsOnHold.txt
   "Exchange Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
   if($excludedlist.count -gt 0){
   " "| add-content .\LocationsNotOnHold.txt
   "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
   "===============================" | add-content .\LocationsNotOnHold.txt
   $excludedlist | add-content .\LocationsNotOnHold.txt}
   $FormatEnumerationLimit=-1
   if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
   if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
   }
   }
   else {"The hold wasn't created because no valid entries were found in the text file."}
   ""
   Write-host "Script complete!" -foregroundColor Yellow
   ""
   #script end
   ```

2. ローカルコンピューターで、Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。

3. スクリプトを実行します。例えば：

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. スクリプトによってプロンプトが表示される情報を入力します。

   このスクリプトは、セキュリティ & コンプライアンスセンターの PowerShell に接続し、電子情報開示ケースで新しいホールドを作成し、リスト内のユーザーのメールボックスと OneDrive for Business を追加します。 セキュリティ & コンプライアンスセンターの [ **電子情報開示** ] ページに移動して、新しいホールドを表示することができます。 

スクリプトの実行が完了すると、次のログファイルが作成され、スクリプトが配置されているフォルダーに保存されます。
  
- **LocationsOnHold.txt:** スクリプトが正常に停止したメールボックスと OneDrive for Business サイトの一覧が含まれています。

- **LocationsNotOnHold.txt:** スクリプトが保留になっていないメールボックスと OneDrive for Business サイトの一覧が含まれています。 ユーザーがメールボックスを持っているが、OneDrive for Business サイトを持っていない場合、ユーザーは保留になっていない OneDrive for Business サイトの一覧に含まれています。

- **GetCaseHoldPolicy.txt:** 新しいホールドの **CaseHoldPolicy** コマンドレットの出力が含まれています。新しいホールドを作成した後にスクリプトが実行されます。 このコマンドレットによって返される情報には、メールボックスと OneDrive for Business サイトが保持されたユーザーの一覧、および保留が有効か無効かが含まれます。 

- **GetCaseHoldRule.txt:** 新しいホールドの **new-caseholdrule** コマンドレットの出力が含まれています。新しいホールドを作成した後にスクリプトが実行されます。 このコマンドレットによって返される情報には、クエリベースの保持を作成するためにスクリプトを使用した場合の検索クエリが含まれています。
