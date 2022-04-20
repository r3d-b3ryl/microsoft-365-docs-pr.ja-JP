---
title: PowerShell を使用してMicrosoft 365 ライセンスをユーザー アカウントに割り当てる
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: この記事では、PowerShell を使用してライセンスのないユーザーにMicrosoft 365ライセンスを割り当てる方法について説明します。
ms.openlocfilehash: 3c92b3baaa0b8d67a5d5a626951b296be2516436
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941701"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>PowerShell を使用してMicrosoft 365 ライセンスをユーザー アカウントに割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ユーザーは、アカウントにライセンス プランからライセンスが割り当てられるまで、Microsoft 365 サービスを使用できません。 PowerShell を使用すると、ライセンスのないアカウントにライセンスをすばやく割り当てることができます。 

まず、ユーザー アカウントに場所を割り当てる必要があります。 場所の指定は、[Microsoft 365 管理センター](../admin/add-users/add-users.md)で新しいユーザー アカウントを作成する際に必要な部分です。 

オンプレミスの Active Directory Domain Services から同期されたアカウントには、既定では場所が指定されていません。 これらのアカウントの場所は、次の場所から構成できます。

- Microsoft 365 管理センター
- [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
- [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active DirectoryUsers** >  > ユーザー アカウント> **ProfileContact** >  **infoCountry** >  **またはリージョン**)。

>[!Note]
>Microsoft 365 管理センター[を使用してユーザー アカウントにライセンスを割り当てる方法について説明](../admin/manage/assign-licenses-to-users.md)します。 その他のリソースの一覧については、「 [ユーザーとグループの管理](/admin)」を参照してください。
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Microsoft Graph PowerShell SDK を使用する

まず、[Microsoft 365 テナントに接続します](/graph/powershell/get-started#authentication)。

ユーザーのライセンスの割り当てと削除には、User.ReadWrite.All アクセス許可スコープまたは[「ライセンスの割り当て」Graph API参照ページ](/graph/api/user-assignlicense)に一覧表示されている他のアクセス許可のいずれかが必要です。

テナントで使用可能なライセンスを読み取るには、Organization.Read.All アクセス許可スコープが必要です。

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

コマンドを `Get-MgSubscribedSku` 実行して、利用可能なライセンス プランと、組織内の各プランで使用可能なライセンスの数を表示します。 各プランで利用可能なライセンスの数は、 **ActiveUnits** - **WarningUnits** - **ConsumedUnits** です。 ライセンスプラン、ライセンス、およびサービスの詳細については、「 [PowerShell でライセンスとサービスを表示する](view-licenses-and-services-with-microsoft-365-powershell.md)」を参照してください。

組織内のライセンスのないアカウントを見つけるには、このコマンドを実行します。

```powershell
Get-MgUser -Filter 'assignedLicenses/$count eq 0' -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All
```

**UsageLocation** プロパティが有効な ISO 3166-1 alpha-2 国コードに設定されているユーザー アカウントにのみライセンスを割り当てることができます。 たとえば、米国は US、フランスは FR です。 一部のMicrosoft 365 サービスは、特定の国では利用できません。 詳細については、「 [ライセンス制限について](https://go.microsoft.com/fwlink/p/?LinkId=691730)」を参照してください。

**UsageLocation** 値を持たないアカウントを検索するには、このコマンドを実行します。

```powershell
Get-MgUser -Select Id,DisplayName,Mail,UserPrincipalName,UsageLocation,UserType | where { $_.UsageLocation -eq $null -and $_.UserType -eq 'Member' }
```

アカウントに **UsageLocation** 値を設定するには、このコマンドを実行します。

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"

Update-MgUser -UserId $userUPN -UsageLocation $userLoc
```

例:

```powershell
Update-MgUser -UserId "belindan@litwareinc.com" -UsageLocation US
```

**Get-MgUser** コマンドレットを -**All** パラメーターを使用せずに使用すると、最初の 100 個のアカウントのみが返されます。

### <a name="assigning-licenses-to-user-accounts"></a>ユーザー アカウントへのライセンスの割り当て

ユーザーにライセンスを割り当てるには、PowerShell で次のコマンドを使用します。
  
```powershell
Set-MgUserLicense -UserId $userUPN -AddLicenses @{SkuId = "<SkuId>"} -RemoveLicenses @()
```

この例では、**SPE_E5** (Microsoft 365 E5) ライセンス プランからライセンスのないユーザー **belindan\@** にライセンスを割り当てます litwareinc.com
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{SkuId = $e5Sku.SkuId} -RemoveLicenses @()
```

この例では、**SPE_E5** (Microsoft 365 E5) と **EMSPREMIUM** (ENTERPRISE MOBILITY + SECURITY E5) をユーザー **の belindan\@** に割り当てます litwareinc.com
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$e5EmsSku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'EMSPREMIUM'
$addLicenses = @(
    @{SkuId = $e5Sku.SkuId},
    @{SkuId = $e5EmsSku.SkuId}
)

Set-MgUserLicense -UserId "belinda@litwareinc.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

この例 **では、****MICROSOFTBOOKINGS** (Microsoft Bookings) サービスとLOCKBOX_ENTERPRISE (Customer Lockbox) サービスがオフになっている **SPE_E5 (Microsoft 365 E5**) を割り当てます。
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$disabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("LOCKBOX_ENTERPRISE", "MICROSOFTBOOKINGS") | `
    Select -ExpandProperty ServicePlanId

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)

Set-MgUserLicense -UserId "belinda@litwareinc.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

次の使用例は **、SPE_E5** (Microsoft 365 E5) を使用してユーザーを更新し、ユーザーの既存の無効なプランを現在の状態のままにしたまま、Swayと Forms サービス プランをオフにします。
  
```powershell
$userLicense = Get-MgUserLicenseDetail -UserId "belinda@fdoau.onmicrosoft.com"
$userDisabledPlans = $userLicense.ServicePlans | `
    Where ProvisioningStatus -eq "Disabled" | `
    Select -ExpandProperty ServicePlanId

$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$newDisabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("SWAY", "FORMS_PLAN_E5") | `
    Select -ExpandProperty ServicePlanId

$disabledPlans = ($userDisabledPlans + $newDisabledPlans) | Select -Unique

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)

Set-MgUserLicense -UserId "belinda@litwareinc.onmicrosoft.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

### <a name="assign-licenses-to-a-user-by-copying-the-license-assignment-from-another-user"></a>別のユーザーからライセンスの割り当てをコピーして、ライセンスをユーザーに割り当てる

この例では、**belindan\@** に適用されているのと同じライセンス プランで **jamesp\@ litwareinc.com** を割り当てます litwareinc.com:

```powershell
$mgUser = Get-MgUser -UserId "belindan@litwareinc.com"
Set-MgUserLicense -UserId "jamesp@litwareinc.com" -AddLicenses $mgUser.AssignedLicenses -RemoveLicenses @()
```

### <a name="move-a-user-to-a-different-subscription-license-plan"></a>ユーザーを別のサブスクリプションに移動する (ライセンス プラン)

次の使用例は、**SPE_E3** (Microsoft 365 E3) ライセンス プランから **SPE_E5** (Microsoft 365 E5) ライセンス プランにユーザーをアップグレードします。

```powershell
$e3Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E3'
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'

# Unassign E3
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{} -RemoveLicenses @($e3Sku.SkuId)
# Assign E5
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{SkuId = $e5Sku.SkuId} -RemoveLicenses @()
```

このコマンドを使用すると、ユーザー アカウントのサブスクリプションの変更を確認できます。

```powershell
Get-MgUserLicenseDetail -UserId "belindan@litwareinc.com"
```

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

>[!Note]
>Set-AzureADUserLicense コマンドレットは廃止される予定です。 上記のように、スクリプトを Microsoft Graph SDK のSet-MgUserLicense コマンドレットに移行してください。 詳細については、「[Microsoft Graphからライセンス管理 API にアクセスするようにアプリを移行する」を参照](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366)してください。
>

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  

次に、このコマンドを使用して、テナントのライセンス プランを一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、ライセンスを追加するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれます) を取得します。

次に、ユーザー アカウントに使用場所が割り当てられていることを確認します。

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

使用場所が割り当てられていない場合は、次のコマンドを使用して割り当てることができます。

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

最後に、ユーザー サインイン名とライセンス プラン名を指定し、これらのコマンドを実行します。

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

>[!Note]
>Set-MsolUserLicenseおよびNew-MsolUser (-LicenseAssignment) コマンドレットは廃止される予定です。 上記のように、スクリプトを Microsoft Graph SDK のSet-MgUserLicense コマンドレットに移行してください。 詳細については、「[Microsoft Graphからライセンス管理 API にアクセスするようにアプリを移行する」を参照](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366)してください。
>

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

コマンドを `Get-MsolAccountSku` 実行して、利用可能なライセンス プランと、組織内の各プランで使用可能なライセンスの数を表示します。 各プランで利用可能なライセンスの数は、 **ActiveUnits** - **WarningUnits** - **ConsumedUnits** です。 ライセンスプラン、ライセンス、およびサービスの詳細については、「 [PowerShell でライセンスとサービスを表示する](view-licenses-and-services-with-microsoft-365-powershell.md)」を参照してください。

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

組織内のライセンスのないアカウントを見つけるには、このコマンドを実行します。

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

**UsageLocation** プロパティが有効な ISO 3166-1 alpha-2 国コードに設定されているユーザー アカウントにのみライセンスを割り当てることができます。 たとえば、米国は US、フランスは FR です。 一部のMicrosoft 365 サービスは、特定の国では利用できません。 詳細については、「 [ライセンス制限について](https://go.microsoft.com/fwlink/p/?LinkId=691730)」を参照してください。
    
**UsageLocation** 値を持たないアカウントを検索するには、このコマンドを実行します。

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

アカウントに **UsageLocation** 値を設定するには、このコマンドを実行します。

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

例:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
**-All** パラメーターなしで **Get-MsolUser** コマンドレットを使用する場合、最初の 500 個のアカウントだけが返されます。

### <a name="assigning-licenses-to-user-accounts"></a>ユーザー アカウントへのライセンスの割り当て
    
ユーザーにライセンスを割り当てるには、PowerShell で次のコマンドを使用します。
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

この例では、**litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンス プランからライセンスのないユーザー **belindan\@** にライセンスを割り当てます litwareinc.com
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

ライセンスのないすべてのユーザーにライセンスを割り当てるには、このコマンドを実行します。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>複数のライセンスを同じライセンス プランのユーザーに割り当てることはできません。 十分な数の利用可能なライセンスをお持ちでない場合は、使用可能なライセンスがなくなるまで、ライセンスは **Get-MsolUser** コマンドレットによって返される順序でユーザーに割り当てられます。
>

この例では、**litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンス プランのライセンスをライセンスのないすべてのユーザーに割り当てます。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

次の使用例は、米国の営業部門のライセンスのないユーザーに同じライセンスを割り当てます。
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell for Graph モジュールを使用してユーザーを別のサブスクリプション (ライセンス プラン) に移動する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
次に、サブスクリプションを切り替えるユーザー アカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれます) を取得します。

次に、このコマンドを使用して、テナントのサブスクリプション (ライセンス プラン) を一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、これらのコマンドを使用して、ユーザー アカウントが現在持っているサブスクリプションを一覧表示します。

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

ユーザーが現在持っているサブスクリプション (FROM サブスクリプション) と、ユーザーが移動するサブスクリプション (TO サブスクリプション) を特定します。

最後に、TO サブスクリプション名と FROM サブスクリプション名 (SKU パーツ番号) を指定し、これらのコマンドを実行します。

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

これらのコマンドを使用して、ユーザー アカウントのサブスクリプションの変更を確認できます。

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>関連項目

[ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
