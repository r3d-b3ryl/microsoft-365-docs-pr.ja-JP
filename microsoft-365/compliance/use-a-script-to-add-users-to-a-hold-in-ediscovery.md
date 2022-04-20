---
title: 電子情報開示 (Standard) ケースでユーザーをホールドに追加するスクリプトを使用する
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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
description: Microsoft Purview コンプライアンス ポータルで、電子情報開示ケースに関連付けられた新しいホールドにメールボックス& OneDrive for Businessサイトを追加するスクリプトを実行する方法について説明します。
ms.openlocfilehash: 8835e853825786668ba1b7617078d899c0773779
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64934531"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-ediscovery-standard-case"></a>電子情報開示 (Standard) ケースでユーザーをホールドに追加するスクリプトを使用する

Security & Compliance Center PowerShell には、電子情報開示ケースの作成と管理に関連する時間のかかるタスクを自動化できるコマンドレットが用意されています。 現在、Microsoft Purview コンプライアンス ポータルで Microsoft Purview 電子情報開示 (Standard) ケースを使用して、多数のカストディアン コンテンツの場所を保持するには、時間と準備が必要です。 たとえば、保留リストを作成する前に、保留にするOneDrive for Businessサイトごとに URL を収集する必要があります。 次に、保留にするユーザーごとに、メールボックスとそのOneDrive for Business サイトを保留に追加する必要があります。 この記事のスクリプトを使用して、このプロセスを自動化できます。
  
このスクリプトでは、組織の個人用サイト ドメインの名前 (URLhttps://contoso-my.sharepoint.com)、既存の電子情報開示ケースの名前、`contoso`ケースに関連付けられている新しいホールドの名前、保留にするユーザーの電子メール アドレスの一覧、クエリ ベースのホールドを作成する場合に使用する検索クエリなど) を求めるメッセージが表示されます。 スクリプトは、リスト内の各ユーザーのOneDrive for Business サイトの URL を取得し、新しい保留リストを作成し、リスト内の各ユーザーのメールボックスとOneDrive for Business サイトを保留リストに追加します。 このスクリプトでは、新しい保留に関する情報を含むログ ファイルも生成されます。
  
これを実現するための手順を次に示します。
  
[手順 1: SharePoint Online 管理シェルをインストールする](#step-1-install-the-sharepoint-online-management-shell)
  
[手順 2: ユーザーの一覧を生成する](#step-2-generate-a-list-of-users)
  
[手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>ユーザーを保留に追加する前に

- 手順 3 でスクリプトを実行するには、コンプライアンス ポータルの電子情報開示マネージャー役割グループのメンバーであり、SharePoint Online 管理者である必要があります。 詳細については、[Office 365 セキュリティ & コンプライアンス センターの電子情報開示アクセス許可の割り当て](assign-ediscovery-permissions.md)に関するページを参照してください。

- コンプライアンス ポータルの電子情報開示ケースに関連付けられているホールドには、最大 1,000 個のメールボックスと 100 個のサイトを追加できます。 保留にするすべてのユーザーにOneDrive for Business サイトがあると仮定すると、この記事のスクリプトを使用して、ホールドに最大 100 人のユーザーを追加できます。

- 手順 2 で作成したユーザーの一覧と手順 3 のスクリプトを同じフォルダーに保存してください。 そうすることで、スクリプトを簡単に実行できるようになります。

- このスクリプトは、既存のケースに関連付けられている新しい保留リストにユーザーの一覧を追加します。 スクリプトを実行する前に、保留リストを関連付けるケースが作成されていることを確認します。

- この記事のスクリプトでは、Security & Compliance Center PowerShell および SharePoint Online Management Shell に接続するときの先進認証がサポートされています。 Microsoft 365またはMicrosoft 365 GCC組織の場合は、スクリプトをそのまま使用できます。 ドイツのOffice 365組織、Microsoft 365 GCC High 組織、または Microsoft 365 DoD 組織の場合は、スクリプトを編集して正常に実行する必要があります。 具体的には、行 `Connect-IPPSSession` を編集し、 *ConnectionUri* パラメーターと *AzureADAuthorizationEndpointUri* パラメーター (および組織の種類に適した値) を使用して、Security & Compliance Center PowerShell に接続する必要があります。 詳細については、「[セキュリティ & コンプライアンス センター PowerShell にConnectする」の例を](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)参照してください。

- このスクリプトは、Security & Compliance Center PowerShell と SharePoint Online Management Shell から自動的に切断されます。

- このスクリプトには、最小限のエラー処理が含まれています。 その主な目的は、各ユーザーのメールボックスとOneDrive for Business サイトを迅速かつ簡単に保留にすることです。

- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする

最初の手順は、SharePoint Online Management Shell がローカル コンピューターにまだインストールされていない場合にインストールすることです。 この手順ではシェルを使用する必要はありませんが、手順 3 で実行するスクリプトに必要な前提条件が含まれているため、シェルをインストールする必要があります。 これらの前提条件により、スクリプトは SharePoint Online と通信して、OneDrive for Business サイトの URL を取得できます。
  
[SharePoint Online Management Shell Windows PowerShell環境のセットアップ](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)に移動し、手順 1 と手順 2 を実行して、SharePoint Online Management Shell をローカル コンピューターにインストールします。

## <a name="step-2-generate-a-list-of-users"></a>手順 2: ユーザーの一覧を生成する

手順 3 のスクリプトでは、電子情報開示ケースに関連付けられたホールドを作成し、ユーザーの一覧のメールボックスとOneDrive for Business サイトを保留に追加します。 テキスト ファイルに電子メール アドレスを入力するか、Windows PowerShellでコマンドを実行して電子メール アドレスの一覧を取得し、ファイルに保存することができます (手順 3 でスクリプトを保存するのと同じフォルダーにあります)。
  
組織内のすべてのユーザーの電子メール アドレスの一覧を取得し、HoldUsers.txtという名前のテキスト ファイルに保存する PowerShell コマンド (Exchange Online 組織に接続されているリモート PowerShell を使用して実行するコマンド) を次に示します。
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

このコマンドを実行した後、テキスト ファイルを開き、  `PrimarySmtpAddress`プロパティ名を含むヘッダーを削除します。 次に、手順 3 で作成する保留リストに追加するユーザーを除くすべての電子メール アドレスを削除します。 電子メール アドレスの一覧の前後に空白行がないことを確認します。
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する

この手順でスクリプトを実行すると、次の情報を求めるメッセージが表示されます。 スクリプトを実行する前に、必ずこの情報を準備しておいてください。
  
- **ユーザー資格情報:** このスクリプトでは、資格情報を使用して PowerShell を使用して Security & Compliance Center に接続します。 また、これらの資格情報を使用して、SharePoint Online にアクセスして、ユーザーの一覧のOneDrive for Business URL を取得します。

- **SharePoint ドメインの名前:** スクリプトは、<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint管理センター</a>に接続できるように、この名前を入力するように求められます。 また、組織内のOneDrive URL のドメイン名も使用します。 たとえば、管理センターの URL が`https://contoso-admin.sharepoint.com`OneDriveの URL である場合は`https://contoso-my.sharepoint.com`、スクリプトからドメイン名の入力を求められたときに入力`contoso`します。

- **ケースの名前:** 既存のケースの名前。 スクリプトによって、このケースに関連付けられた新しいホールドが作成されます。

- **保留リストの名前:** スクリプトが作成し、指定したケースに関連付ける保留リストの名前。

- **クエリ ベースのホールドの検索クエリ:** クエリ ベースのホールドを作成して、指定した検索条件を満たすコンテンツのみが保留に設定されるようにすることができます。 すべてのコンテンツを保留にするには、検索クエリの入力を求められたら **Enter** キーを押します。

- **保留を有効にするかどうか:** スクリプトを作成した後で保留を有効にするか、スクリプトを有効にせずに保留を作成することができます。 保持を有効にしたスクリプトがない場合は、後でコンプライアンス ポータルで有効にするか、次の PowerShell コマンドを実行します。

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **ユーザーの一覧を含むテキスト ファイルの名前** - ホールドに追加するユーザーの一覧を含む手順 2 のテキスト ファイルの名前。 このファイルがスクリプトと同じフォルダーにある場合は、ファイルの名前 (HoldUsers.txtなど) を入力するだけです。 テキスト ファイルが別のフォルダーにある場合は、ファイルの完全なパス名を入力します。

スクリプトから求められる情報を収集したら、最後にスクリプトを実行して新しいホールドを作成し、それにユーザーを追加します。
  
1. ファイル名のサフィックス`.ps1`を使用して、次のテキストをWindows PowerShell スクリプト ファイルに保存します。 たとえば、「 `AddUsersToHold.ps1` 」のように入力します。

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   eDiscovery (Standard) cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $finallist)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $false | out-null
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. ローカル コンピューターでWindows PowerShellを開き、スクリプトを保存したフォルダーに移動します。

3. スクリプトを実行します。例えば：

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. スクリプトの入力を求める情報を入力します。

   このスクリプトは Security & Compliance Center PowerShell に接続し、電子情報開示ケースで新しいホールドを作成し、一覧にユーザーのメールボックスとOneDrive for Businessを追加します。 コンプライアンス ポータルの **電子情報開示** ページでケースに移動して、新しいホールドを表示できます。

スクリプトの実行が完了すると、次のログ ファイルが作成され、スクリプトが配置されているフォルダーに保存されます。
  
- **LocationsOnHold.txt:** スクリプトが正常に保留にしたメールボックスとOneDrive for Business サイトの一覧が含まれます。

- **LocationsNotOnHold.txt:** スクリプトが保留にしなかったメールボックスとOneDrive for Business サイトの一覧が含まれます。 ユーザーがメールボックスを持ち、OneDrive for Business サイトを持っていない場合、ユーザーは保留にされていないOneDrive for Business サイトの一覧に含まれます。

- **GetCaseHoldPolicy.txt:** 新しいホールドの **Get-CaseHoldPolicy** コマンドレットの出力が含まれます。このコマンドレットは、新しいホールドの作成後にスクリプトが実行されました。 このコマンドレットによって返される情報には、メールボックスとOneDrive for Business サイトが保留にされたユーザーの一覧と、保留が有効または無効になっているかどうかが含まれます。 

- **GetCaseHoldRule.txt:** 新しいホールドの **Get-CaseHoldRule** コマンドレットの出力が含まれます。このコマンドレットは、新しいホールドの作成後にスクリプトが実行されました。 このコマンドレットによって返される情報には、クエリ ベースのホールドを作成するためにスクリプトを使用した場合の検索クエリが含まれます。
