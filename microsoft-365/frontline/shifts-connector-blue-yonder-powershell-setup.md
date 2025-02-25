---
title: PowerShell を使用して Shifts を Blue Yonder Workforce Management に接続する
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: PowerShell を使用して Shifts と Blue Yonder Workforce Management を統合する方法について説明します。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 22b820bdbb372b5f07967836613a9d7348bd7b1c
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822676"
---
# <a name="use-powershell-to-connect-shifts-to-blue-yonder-workforce-management"></a>PowerShell を使用して Shifts を Blue Yonder Workforce Management に接続する

## <a name="overview"></a>概要

[Blue Yonder 用の Microsoft Teams Shifts コネクタ](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)を使用して、Microsoft Teams の Shifts アプリを Blue Yonder Workforce Management (Blue Yonder WFM) と統合します。 接続が設定されると、フロントライン ワーカーは、Shifts 内から Blue Yonder WFMでスケジュールをシームレスに表示および管理できます。

この記事では、PowerShell を使用して、Shifts と Blue Yonder WFMを統合するようにコネクタを設定および構成する方法について説明します。

接続を設定するには、PowerShell スクリプトを実行します。 このスクリプトでは、コネクタを構成し、同期設定を適用し、接続を作成し、Blue Yonder WFM インスタンスをチームにマップします。 同期設定は、Shifts で有効になっている機能と、Blue Yonder WFM と Shifts の間で同期されるスケジュール情報を決定します。 マッピングは、Blue Yonder WFM インスタンスと Teams 内のチーム間の同期関係を定義します。 既存のチームと新しいチームにマップできます。

2 つのスクリプトを提供します。 既存のチームにマップするか、マップする新しいチームを作成するかに応じて、どちらのスクリプトを使用することもできます。

複数の接続を設定できます。それぞれ異なる同期設定を使用します。 たとえば、組織に異なるスケジュール要件を持つ複数の場所がある場合は、場所ごとに一意の同期設定を持つ接続を作成します。 Blue Yonder WFM インスタンスは、特定の時点で 1 つのチームにのみマップできることに注意してください。 インスタンスが既にチームにマップされている場合、別のチームにマップすることはできません。

Blue Yonder WFM をレコードのシステムとして使用すると、フロントライン ワーカーはシフトの表示と交換、可用性の管理、デバイスの Shifts での休暇の要求を行うことができます。 フロントライン マネージャーは、引き続き Blue Yonder WFM を使用してスケジュールを設定できます。

> [!NOTE]
> Microsoft 365 管理センターの [Shifts コネクタ ウィザード](shifts-connector-wizard.md)を使用して、Shifts を Blue Yonder WFM に接続することもできます。

## <a name="before-you-begin"></a>はじめに

### <a name="prerequisites"></a>前提条件

[!INCLUDE [shifts-connector-prerequisites](includes/shifts-connector-prerequisites.md)]

### <a name="admin-role-to-manage-the-connector-using-powershell"></a>PowerShell を使用してコネクタを管理するロールを管理する

[!INCLUDE [shifts-connector-admin-role](includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>環境を設定する

[!INCLUDE [shifts-connector-set-up-environment](includes/shifts-connector-set-up-environment.md)]

## <a name="connect-to-teams"></a>Teams に接続

Teams に接続するには、次を実行します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。 この記事のスクリプトと Shifts コネクタ コマンドレットを実行するように設定しました。

## <a name="identify-the-teams-you-want-to-map"></a>マップするチームを特定する

> [!NOTE]
> Blue Yonder WFM インスタンスを既存のチームにマッピングする場合は、この手順を完了します。 マップ先の新しいチームを作成する場合は、この手順をスキップできます。

Azure portalで、[[すべてのグループ]](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) ページに移動して、組織内のチームの TeamId の一覧を取得します。

マップするチームの TeamId をメモしておきます。 この情報の入力を求めるメッセージがスクリプトによって表示されます。

> [!NOTE]
> 1 つ以上のチームに既存のスケジュールがある場合、スクリプトはそれらのチームからスケジュールを削除します。 それ以外の場合は、重複するシフトが表示されます。

## <a name="run-the-script"></a>スクリプトを実行する

次のスクリプトを実行します。

- 接続を設定し、マップする新しいチームを作成するには、 [このスクリプトを実行します](#set-up-a-connection-and-create-new-teams-to-map)。
- 接続を設定し、既存のチームにマップするには、 [このスクリプトを実行します](#set-up-a-connection-and-map-to-existing-teams)。

このスクリプトでは、次のことが行われます。 セットアップと構成の詳細を入力するように求められます。

1. 入力した Blue Yonder WFM サービス アカウントの資格情報とサービス URL を使用して、Blue Yonder WFM への接続をテストして検証します。
1. Shifts コネクタを構成します。
1. 同期設定を適用します。 これらの設定には、同期頻度 (分単位) と、Blue Yonder WFM と Shifts の間で同期されるスケジュール データが含まれます。 スケジュール データは、次のパラメーターで定義されます。

    - **enabledConnectorScenarios** パラメーターは、Blue Yonder WFM から Shifts に同期されるデータを定義します。 オプションは `Shift`、`SwapRequest`、`UserShiftPreferences`、`OpenShift`、`OpenShiftRequest`、`TimeOff`、`TimeOffRequest` です。
    - **enabledWfiScenarios** パラメーターは、Shifts から Blue Yonder WFM に同期されるデータを定義します。 オプションは `SwapRequest`、`OpenShiftRequest`、`TimeOffRequest`、`UserShiftPreferences` です。

    詳しくは、[New-ClassificationRuleCollection](/powershell/module/teams/new-csteamsshiftsconnectioninstance) を参照してください。 各パラメーターでサポートされている同期オプションの一覧を表示するには、 [Get-CsTeamsShiftsConnectionConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) を実行します。

    > [!IMPORTANT]
    > このスクリプトを使用すると、これらのすべてのオプションの同期が有効になります。 同期設定を変更する場合は、接続の設定後に行うことができます。 詳細については、「[PowerShell を使用して Blue Yonder Workforce Managementへの Shifts 接続を管理する](shifts-connector-powershell-manage.md)」を参照してください。

1. 接続を作成します。
1. Blue Yonder WFM インスタンスをチームにマップします。 マッピングは、実行するスクリプトに応じて、作成する Blue Yonder WFM インスタンス ID と TeamIds に基づきます。 チームに既存のスケジュールがある場合、スクリプトは指定した日付と時刻の範囲のスケジュール データを削除します。

画面の [成功] メッセージは、接続が正常に設定されたことを示します。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>接続に変更を加える必要がある場合

セットアップ後に接続を変更するには、「[PowerShell を使用して Blue Yonder Workforce Managementへの Shifts 接続を管理する](shifts-connector-powershell-manage.md)」を参照してください。 たとえば、同期設定、チーム マッピングを更新し、接続の同期を無効にすることができます。

## <a name="scripts"></a>スクリプト

### <a name="set-up-a-connection-and-create-new-teams-to-map"></a>接続を設定し、マップする新しいチームを作成する

```powershell
#Map WFM instances to teams script
Write-Host "Map WFM sites to teams"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create a connection instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency"

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail $AdminEmailList
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of WFM instances
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

#Create a new Teams team with owner set to system account and name set to the site name
Write-Host "Creating a Teams team"
$teamsTeamName = Read-Host -Prompt "Input the Teams team name"
$Team = New-Team -DisplayName $teamsTeamName -Visibility "Public" -Owner $teamsUserId
Write-Host "Success"
$TeamsTeamId=$Team.GroupId

#Add users to the Team for Shifts
Write-Host "Adding users to Teams team"
$currentUser = Read-Host -Prompt "Input the current user's user name or ID"
Add-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
$failedWfmUsers=@()
foreach ($user in $WFMUsers) {
    try {
    $userEmail = $user.Name + "@" +$domain
    Add-TeamUser -GroupId $TeamsTeamId -User $userEmail
    } catch {
        $failedWfmUsers+=$user
    }
}
if($failedWfmUsers.Count -gt 0){
    Write-Host "There are WFM users not existed in Teams tenant:"
    write $failedWfmUsers
}

#Enable scheduling in the group
$RequestBody = @{
    Enabled = $true
    TimeZone = "America/Los_Angeles"
}
$teamUpdateUrl="https://graph.microsoft.com/v1.0/teams/"+$TeamsTeamId+"/schedule"
$Schedule = Invoke-MgGraphRequest -Uri $teamUpdateUrl -Method PUT -Body $RequestBody

#Create a mapping of the new team to the WFM instance
Write-Host "Create a mapping of the new team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"

$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}

#The Teams admin was set as an owner directly when creating a new team, removing it from owners
Remove-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
Disconnect-MgGraph
```

### <a name="set-up-a-connection-and-map-to-existing-teams"></a>接続を設定し、既存のチームにマップする

```powershell
#Map WFM sites to existing teams script
Write-Host "Map WFM sites to existing teams"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create a connection instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365 user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency in minutes. Value should be equal to or more than 10."

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail AdminEmailList

$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of WFM instances
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

$TeamsTeamId = Read-Host -Prompt "Input the ID of the Teams team to be mapped"
#Clear schedule of the Teams team
Write-Host "Clear schedule of the existing team"
$startTime = Read-Host -Prompt "Input the start time of clear schedule"
$endTime = Read-Host -Prompt "Input the end time of clear schedule"

$entityTypeString = Read-Host -Prompt 'Input the entity types of clear schedule'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$entityType = $entityTypeString -Split {$Delimiters -contains $_}
$entityType = $entityType.Trim()
$entityType = $entityType.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
Remove-CsTeamsShiftsScheduleRecord -TeamId $TeamsTeamId -DateRangeStartDate $startTime -DateRangeEndDate $endTime -ClearSchedulingGroup:$True -EntityType $entityType -DesignatedActorId $$teamsUserId

#Create a mapping of the new team to the WFM instance
Write-Host "Create a mapping of the existing team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"


$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Disconnect-MgGraph
```

## <a name="shifts-connector-cmdlets"></a>Shifts コネクタ コマンドレット

スクリプトで使用されるコマンドレットを含む Shifts コネクタ コマンドレットのヘルプについては、[Teams PowerShell コマンドレット リファレンス](/powershell/teams/intro)で **CsTeamsShiftsConnection** を検索してください。 一般的に使用されるコマンドレットへのリンクを次に示します。

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>関連記事

- [シフト コネクタ](shifts-connectors.md)
- [PowerShell を使用して Blue Yonder WFM とのシフトを管理する](shifts-connector-powershell-manage.md)
- [Teams で組織の シフト アプリを管理する](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams での PowerShell の概要](/microsoftteams/teams-powershell-overview)
- [Search-MailboxAuditLog PowerShell コマンドレットのリファレンス](/powershell/teams/intro)
