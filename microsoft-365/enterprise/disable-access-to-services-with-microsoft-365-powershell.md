---
title: PowerShell を使用してMicrosoft 365 サービスへのアクセスを無効にする
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/27/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: この記事では、PowerShell を使用して、ユーザーのMicrosoft 365 サービスへのアクセスを無効にする方法について説明します。
ms.openlocfilehash: d6754cc2de6208b9dc4bce03ef6477939f8d530a
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939435"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>PowerShell を使用してMicrosoft 365 サービスへのアクセスを無効にする

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 アカウントにライセンス プランからライセンスが割り当てられると、Microsoft 365 サービスはそのライセンスからユーザーが利用できるようになります。 ただし、ユーザーがアクセスできるMicrosoft 365 サービスを制御できます。 たとえば、ライセンスで SharePoint Online サービスへのアクセスが許可されている場合でも、そのアクセスを無効にすることができます。 PowerShell を使用すると、特定のライセンス プランの任意の数のサービスへのアクセスを無効にすることができます。

- 個々のアカウント。
- アカウントのグループ。
- 組織内のすべてのアカウント。

>[!Note]
>他のサービスが依存している場合に、指定したサービスを無効にできないMicrosoft 365サービスの依存関係があります。
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Microsoft Graph PowerShell SDK を使用する

まず、[Microsoft 365 テナントに接続します](/graph/powershell/get-started#authentication)。

ユーザーのライセンスの割り当てと削除には、User.ReadWrite.All アクセス許可スコープまたは[「ライセンスの割り当て」Graph API参照ページ](/graph/api/user-assignlicense)に一覧表示されている他のアクセス許可のいずれかが必要です。

テナントで使用可能なライセンスを読み取るには、Organization.Read.All アクセス許可スコープが必要です。

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

次に、このコマンドを使用して、使用可能なライセンス プラン (SkuPartNumber とも呼ばれます) を表示します。

```powershell
Get-MgSubscribedSku | Select SkuId, SkuPartNumber, ServicePlans | Sort SkuPartNumber
```

詳細については、「 [PowerShell でライセンスとサービスを表示する](view-licenses-and-services-with-microsoft-365-powershell.md)」を参照してください。

このトピックの手順の前後の結果については、「 [PowerShell を使用したアカウント ライセンスとサービスの詳細の表示](view-account-license-and-service-details-with-microsoft-365-powershell.md)」を参照してください。

### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>特定のライセンス プランの特定のユーザーに対して特定のMicrosoft 365 サービスを無効にする
  
特定のライセンス プランのユーザーに対して特定のMicrosoft 365 サービスのセットを無効にするには、次の手順を実行します。
  
#### <a name="step-1-identify-the-undesired-services-in-the-licensing-plan-by-using-the-following-syntax"></a>手順 1: 次の構文を使用して、ライセンス プラン内の望ましくないサービスを特定します。

最初に、次のコマンドを使用して、テナントで使用可能なライセンス プランを一覧表示します。

```powershell
Get-MgSubscribedSku | Select SkuPartNumber

SkuPartNumber
-------------
EMSPREMIUM
SPE_E5
RIGHTSMANAGEMENT_ADHOC

```

次に、上記のコマンドから SkuPartNumber を使用し、特定のライセンス プラン (Sku) で使用できるサービス プランを一覧表示します。

次の例では、**SPE_E5 (Microsoft 365 E5**) で使用できるすべてのサービス プランを一覧表示します。

```powershell
Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5' |  select -ExpandProperty ServicePlans
```

```text
AppliesTo ProvisioningStatus ServicePlanId                        ServicePlanName
--------- ------------------ -------------                        ---------------
User      Success            b21a6b06-1988-436e-a07b-51ec6d9f52ad PROJECT_O365_P3
User      Success            64bfac92-2b17-4482-b5e5-a0304429de3e MICROSOFTENDPOINTDLP
User      Success            199a5c09-e0ca-4e37-8f7c-b05d533e1ea2 MICROSOFTBOOKINGS
User      Success            6db1f1db-2b46-403f-be40-e39395f08dbb CUSTOMER_KEY
User      Success            4a51bca5-1eff-43f5-878c-177680f191af WHITEBOARD_PLAN3
User      Success            07699545-9485-468e-95b6-2fca3738be01 FLOW_O365_P3
User      Success            9c0dab89-a30c-4117-86e7-97bda240acd2 POWERAPPS_O365_P3
User      Success            e212cbc7-0961-4c40-9825-01117710dcb1 FORMS_PLAN_E5
User      Success            57ff2da0-773e-42df-b2af-ffb7a2317929 TEAMS1
User      Success            21b439ba-a0ca-424f-a6cc-52f954a5b111 WIN10_PRO_ENT_SUB
User      Success            eec0eb4f-6444-4f95-aba0-50c24d67f998 AAD_PREMIUM_P2
User      Success            c1ec4a95-1f05-45b3-a911-aa3fa01094f5 INTUNE_A
User      Success            7547a3fe-08ee-4ccb-b430-5077c5041653 YAMMER_ENTERPRISE
User      Success            a23b959c-7ce8-4e57-9140-b90eb88a9e97 SWAY
User      Success            e95bec33-7c88-4a70-8e19-b10bd9d0c014 SHAREPOINTWAC
User      Success            5dbe027f-2339-4123-9542-606e4d348a72 SHAREPOINTENTERPRISE
User      Success            b737dad2-2f6c-4c65-90e3-ca563267e8b9 PROJECTWORKMANAGEMENT
User      Success            43de0ff5-c92c-492b-9116-175376d08c38 OFFICESUBSCRIPTION
User      Success            0feaeb32-d00e-4d66-bd5a-43b5b83db82c MCOSTANDARD
User      Success            9f431833-0334-42de-a7dc-70aa40db46db LOCKBOX_ENTERPRISE
User      Success            efb87545-963c-4e0d-99df-69c6916d9eb0 EXCHANGE_S_ENTERPRISE
```

ライセンス プラン (製品名とも呼ばれます)、含まれるサービス プラン、および対応するフレンドリ名の完全な一覧については、 [ライセンスの製品名とサービス プラン識別子に関するページを](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)参照してください。 (ServicePlanId を使用して、サービス プランの対応するフレンドリ名を検索します)。

次の例 **では、****MICROSOFTBOOKINGS** (Microsoft Bookings) サービスとLOCKBOX_ENTERPRISE (Customer Lockbox) サービスがオフになっている **SPE_E5 (Microsoft 365 E5**) を割り当てます。
  
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

Set-MgUserLicenseの AddLicenses パラメーターの DisabledPlans プロパティは、ユーザーの既存の DisabledPlans 値を上書きします。 既存のサービス プランの状態を維持するには、ユーザーの現在のサービス プランの状態を、無効にする新しいプランとマージする必要があります。

既存の DisabledPlans を含めなければ、ユーザーの以前に無効にしたプランが有効になります。

次の例では **、SPE_E5** (Microsoft 365 E5) を使用してユーザーを更新し、ユーザーの既存の無効なプランを現在の状態のままにしたまま、Swayと Forms サービス プランをオフにします。
  
```powershell
## Get the services that have already been disabled for the user.
$userLicense = Get-MgUserLicenseDetail -UserId "belinda@fdoau.onmicrosoft.com"
$userDisabledPlans = $userLicense.ServicePlans | `
    Where ProvisioningStatus -eq "Disabled" | `
    Select -ExpandProperty ServicePlanId

## Get the new service plans that are going to be disabled
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$newDisabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("SWAY", "FORMS_PLAN_E5") | `
    Select -ExpandProperty ServicePlanId

## Merge the new plans that are to be disabled with the user's current state of disabled plans
$disabledPlans = ($userDisabledPlans + $newDisabledPlans) | Select -Unique

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)
## Update user's license
Set-MgUserLicense -UserId "belinda@litwareinc.onmicrosoft.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

次に、次のコマンドを使用して、使用可能なライセンス プラン (AccountSkuIds とも呼ばれます) を表示します。

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

詳細については、「 [PowerShell でライセンスとサービスを表示する](view-licenses-and-services-with-microsoft-365-powershell.md)」を参照してください。
    
このトピックの手順の前後の結果については、「 [PowerShell を使用したアカウント ライセンスとサービスの詳細の表示](view-account-license-and-service-details-with-microsoft-365-powershell.md)」を参照してください。
    
このトピックで説明されている手順を自動化する PowerShell スクリプトが利用可能です。 具体的には、このスクリプトを使用すると、Swayを含む、Microsoft 365組織内のサービスを表示および無効にすることができます。 詳細については、「[PowerShell を使用してSwayへのアクセスを無効にする](disable-access-to-sway-with-microsoft-365-powershell.md)」を参照してください。
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>特定のライセンス プランの特定のユーザーに対して特定のMicrosoft 365 サービスを無効にする
  
特定のライセンス プランのユーザーに対して特定のMicrosoft 365 サービスのセットを無効にするには、次の手順を実行します。
  
#### <a name="step-1-identify-the-undesired-services-in-the-licensing-plan-by-using-the-following-syntax"></a>手順 1: 次の構文を使用して、ライセンス プラン内の望ましくないサービスを特定します。
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesiredService1>", "<UndesiredService2>"...
```

次の例では、(E3 Office 365 Enterprise) という名前`litwareinc:ENTERPRISEPACK`のライセンス プランで、Office および SharePoint Online サービスを無効にする **LicenseOptions** オブジェクトを作成します。
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>手順 2: 手順 1 の **LicenseOptions** オブジェクトを 1 人以上のユーザーに使用します。
    
サービスが無効になっている新しいアカウントを作成するには、次の構文を使用します。
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

次の例では、ライセンスを割り当て、手順 1 で説明したサービスを無効にする Allie Bellew の新しいアカウントを作成します。
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

PowerShell for Microsoft 365 でユーザー アカウントを作成する方法の詳細については、「[PowerShell でユーザー アカウントを作成する](create-user-accounts-with-microsoft-365-powershell.md)」を参照してください。
    
ライセンスを付与された既存のユーザー用のサービスを無効にするには、次の構文を使用します。
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

この例では、ユーザー BelindaN@litwareinc.com に対してサービスを無効にします。
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

既存のライセンスを持つすべてのユーザーに対して手順 1 で説明したサービスを無効にするには、**Get-MsolAccountSku** コマンドレット (**litwareinc:ENTERPRISEPACK** など) の表示からMicrosoft 365プランの名前を指定し、次のコマンドを実行します。
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 _All_ パラメーターを使用せずに **Get-MsolUser** コマンドレットを使用する場合は、最初の 500 個のユーザー アカウントのみが返されます。

既存のユーザーのグループに対してサービスを無効にするには、次のいずれかの方法を使用して、ユーザーを特定します。
    
**方法 1.既存のアカウント属性に基づいてアカウントをフィルター処理する** 

この設定を行うには、次の構文を使用します。
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

次の例では、米国の営業部門のユーザーに対してサービスを無効にします。
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**方法 2: 特定のアカウントの一覧を使用する** 

これを行うには、次の手順を実行します。
    
1. 次のように各行に 1 つのアカウントが含まれるテキスト ファイルを作成します。
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   この例では、テキスト ファイルは C:\\My Documents\\Accounts.txtです。
    
2. 次のコマンドを実行します。
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

複数のライセンス プランのサービスへのアクセスを無効にする場合は、ライセンス プランごとに上記の手順を繰り返して、次のことを確認します。

- ユーザー アカウントにライセンス プランが割り当てられています。
- 無効にするサービスは、ライセンス プランで使用できます。

ユーザーをライセンス プランに割り当てる間にMicrosoft 365サービスを無効にするには、「[ユーザー ライセンスの割り当て中にサービスへのアクセスを無効にする](disable-access-to-services-while-assigning-user-licenses.md)」を参照してください。

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>ライセンス プラン内のすべてのサービスをユーザー アカウントに割り当てる

サービスが無効になっているユーザー アカウントの場合は、次のコマンドを使用して、特定のライセンス プランのすべてのサービスを有効にすることができます。

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>関連トピック

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
