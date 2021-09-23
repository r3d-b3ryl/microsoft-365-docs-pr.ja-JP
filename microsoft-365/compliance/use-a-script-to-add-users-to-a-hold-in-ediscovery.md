---
title: スクリプトを使用してコア電子情報開示ケースの保留リストにユーザーを追加する
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
description: スクリプトを実行して、& OneDrive for Businessの電子情報開示ケースに関連付けられた新しい保留リストにメールボックスを追加するMicrosoft 365 コンプライアンス センター。
ms.openlocfilehash: f64ada92bdfc3081f1695e11cd4ee21fd2995c40
ms.sourcegitcommit: 0ed93816e2c1e6620e68bd1c0f00390062911606
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59483041"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>スクリプトを使用してコア電子情報開示ケースの保留リストにユーザーを追加する

セキュリティ & コンプライアンス センター PowerShell には、電子情報開示ケースの作成と管理に関連する時間のかかるタスクを自動化できるコマンドレットがあります。 現在、サーバーでコア電子情報開示ケースを使用Microsoft 365 コンプライアンス センター多数の保管担当者コンテンツの場所を保留にするのに時間と準備が必要です。 たとえば、保留リストを作成する前に、保留にOneDrive for Businessサイトごとに URL を収集する必要があります。 次に、保留に設定するユーザーごとに、メールボックスとそのユーザーのOneDrive for Businessを保留に追加する必要があります。 この記事のスクリプトを使用して、このプロセスを自動化できます。
  
このスクリプトでは、組織の My Site ドメインの名前 (URL、既存の電子情報開示ケースの名前、ケースに関連付けられた新しい保留の名前、保留するユーザーの電子メール アドレスの一覧、クエリ ベースの保持を作成する場合に使用する検索クエリなど) を求めるプロンプトが表示されます。 `contoso` https://contoso-my.sharepoint.com) 次に、スクリプトはリスト内の各ユーザーの OneDrive for Business サイトの URL を取得し、新しい保留リストを作成し、リスト内の各ユーザーのメールボックスと OneDrive for Business サイトを保留リストに追加します。 スクリプトは、新しい保留に関する情報を含むログ ファイルも生成します。
  
これを行う手順を次に示します。
  
[手順 1: SharePoint Online 管理シェルをインストールする](#step-1-install-the-sharepoint-online-management-shell)
  
[手順 2: ユーザーの一覧を生成する](#step-2-generate-a-list-of-users)
  
[手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>ユーザーを保留リストに追加する前に

- 手順 3 でスクリプトを実行するには、Microsoft 365 コンプライアンス センター および SharePoint Online 管理者の電子情報開示マネージャー役割グループのメンバーである必要があります。 詳細については、「Assign eDiscovery permissions in the Office [365 Security & コンプライアンス センター」を参照してください](assign-ediscovery-permissions.md)。

- 最大 1,000 のメールボックスと 100 のサイトを、Microsoft 365 コンプライアンス センター の電子情報開示ケースに関連付けられた保留リストに追加できます。 保留にしたいすべてのユーザーに OneDrive for Business サイトが含まれると仮定すると、この記事のスクリプトを使用して最大 100 人のユーザーを保留リストに追加できます。

- 手順 2 で作成したユーザーの一覧と、手順 3 のスクリプトを同じフォルダーに保存してください。 そうすると、スクリプトの実行が容易になります。

- スクリプトは、既存のケースに関連付けられている新しい保留リストにユーザーのリストを追加します。 スクリプトを実行する前に、ホールドを関連付けるケースが作成されます。

- この記事のスクリプトは、コンプライアンス センター PowerShell とオンライン管理シェルのセキュリティ &接続時SharePointをサポートします。 スクリプトは、ユーザーまたは組織のMicrosoft 365使用Microsoft 365 GCCできます。 ドイツの Office 365、Microsoft 365 GCC High 組織、または Microsoft 365 DoD 組織の場合は、スクリプトを編集して正常に実行する必要があります。 具体的には、行を編集し `Connect-IPPSSession` *、ConnectionUri* パラメーターと *AzureADAuthorizationEndpointUri* パラメーター (および組織の種類に適した値) を使用して、セキュリティ & コンプライアンス センター PowerShell に接続する必要があります。 詳細については、「コンプライアンス センター PowerShell のセキュリティ[Connect」の&を参照してください](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)。

- スクリプトは、コンプライアンス センター PowerShell のセキュリティ &、オンライン管理シェルSharePoint自動的に切断されます。

- スクリプトには、最小限のエラー処理が含まれています。 その主な目的は、各ユーザーのメールボックスとOneDrive for Businessを迅速かつ簡単に保留にすることです。

- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする

最初の手順は、ローカル コンピューター SharePointインストールされていない場合は、オンライン管理シェルをインストールします。 この手順ではシェルを使用する必要はありません。ただし、手順 3 で実行するスクリプトに必要な前提条件が含まれているため、インストールする必要があります。 これらの前提条件により、スクリプトは SharePoint Online と通信して、サイトの URL をOneDrive for Businessできます。
  
[SharePoint Online 管理シェル Windows PowerShell環境のセットアップ] に[移動](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)し、手順 1 と手順 2 を実行して、SharePoint Online 管理シェルをローカル コンピューターにインストールします。

## <a name="step-2-generate-a-list-of-users"></a>手順 2: ユーザーの一覧を生成する

手順 3 のスクリプトは、電子情報開示ケースに関連付けられた保留リストを作成し、ユーザーのリストのメールボックスと OneDrive for Business サイトを保留リストに追加します。 テキスト ファイルに電子メール アドレスを入力するか、Windows PowerShell でコマンドを実行して電子メール アドレスの一覧を取得し、ファイルに保存できます (手順 3 でスクリプトを保存するフォルダーと同じフォルダーにあります)。
  
ここでは、PowerShell コマンド (Exchange Online 組織に接続されたリモート PowerShell を使用して実行します) を使用して、組織内のすべてのユーザーの電子メール アドレスの一覧を取得し、HoldUsers.txt という名前のテキスト ファイルに保存します。
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

このコマンドを実行した後、テキスト ファイルを開き、プロパティ名を含むヘッダーを削除します  `PrimarySmtpAddress` 。 次に、手順 3 で作成する保留リストに追加するユーザーのメール アドレスを除くすべての電子メール アドレスを削除します。 電子メール アドレスの一覧の前または後に空白行が表示されません。
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>手順 3: スクリプトを実行して保留リストを作成し、ユーザーを追加する

この手順でスクリプトを実行すると、次の情報を求めるメッセージが表示されます。 スクリプトを実行する前に、この情報を準備してください。
  
- **ユーザー資格情報:** スクリプトは、資格情報を使用して PowerShell を使用してセキュリティ &コンプライアンス センターに接続します。 また、これらの資格情報を使用して、SharePointの URL を取得OneDrive for Businessオンラインにアクセスします。

- **ドメインのSharePoint:** このスクリプトでは、この名前を入力するように求めるメッセージが表示されます。この名前は、管理者センター SharePointできます。 また、組織の URL のドメインOneDrive使用します。 たとえば、管理センターの URL が、OneDrive の URL である場合は、スクリプトからドメイン名の入力を求めるメッセージが表示されたら `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` 入力します。

- **ケースの名前:** 既存のケースの名前。 スクリプトは、このケースに関連付けられた新しい保留リストを作成します。

- **保留リストの名前:** スクリプトが作成し、指定したケースに関連付ける保留リストの名前。

- **クエリ ベースのホールドの検索クエリ:** クエリ ベースの保留リストを作成して、指定した検索条件を満たすコンテンツのみを保留にできます。 すべてのコンテンツを保留に設定するには、検索クエリの入力を求めるメッセージが表示されたら **、Enter** キーを押します。

- **ホールドをオンにするか、オンにしないか:** 作成後にスクリプトを保留にするか、スクリプトを有効にせずに保持を作成できます。 スクリプトを保留にしない場合は、後でこのスクリプトを有効にするか、Microsoft 365 コンプライアンス センター PowerShell コマンドを実行します。

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **ユーザーの一覧** を含むテキスト ファイルの名前 - 保留リストに追加するユーザーの一覧を含む手順 2 のテキスト ファイルの名前。 このファイルがスクリプトと同じフォルダーにある場合は、ファイルの名前を入力します (たとえば、HoldUsers.txt)。 テキスト ファイルが別のフォルダーにある場合は、ファイルの完全なパス名を入力します。

スクリプトが求める情報を収集した後、最後にスクリプトを実行して新しい保留リストを作成し、ユーザーを追加します。
  
1. ファイル名のサフィックスを使用してWindows PowerShellスクリプト ファイルに次のテキストを保存します `.ps1` 。 たとえば、「 `AddUsersToHold.ps1` 」のように入力します。

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
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

2. ローカル コンピューターで、[スクリプト] Windows PowerShell開き、スクリプトを保存したフォルダーに移動します。

3. スクリプトを実行します。例えば：

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. スクリプトから求める情報を入力します。

   スクリプトはセキュリティ & コンプライアンス センター PowerShell に接続し、電子情報開示ケースに新しいホールドを作成し、リスト内のユーザーのメールボックスと OneDrive for Business を追加します。 [電子情報開示] ページの[ケース] に移動して、Microsoft 365 コンプライアンス センターを表示できます。

スクリプトの実行が完了すると、次のログ ファイルが作成され、スクリプトがあるフォルダーに保存されます。
  
- **LocationsOnHold.txt:** スクリプトが正常に保留にされたメールボックスOneDrive for Businessサイトの一覧が含まれる。

- **LocationsNotOnHold.txt:** スクリプトが保留にしなかったメールボックスOneDrive for Businessサイトの一覧が含まれる。 ユーザーがメールボックスを持っているが、OneDrive for Business サイトではない場合、ユーザーは保留にされていない OneDrive for Business サイトの一覧に含まれます。

- **GetCaseHoldPolicy.txt:** 新しいホールドの **Get-CaseHoldPolicy** コマンドレットの出力を含み、スクリプトは新しいホールドの作成後に実行しました。 このコマンドレットによって返される情報には、メールボックスと OneDrive for Business サイトが保留にされたユーザーの一覧と、保留が有効か無効かを示します。 

- **GetCaseHoldRule.txt:** 新しい保留リストの作成後にスクリプトが実行した、新しい保留リストの **Get-CaseHoldRule** コマンドレットの出力を格納します。 このコマンドレットによって返される情報には、スクリプトを使用してクエリ ベースの保持を作成した場合の検索クエリが含まれます。
