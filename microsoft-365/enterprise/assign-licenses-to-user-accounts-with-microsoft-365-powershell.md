---
title: PowerShell を使用してMicrosoft 365ライセンスをユーザー アカウントに割り当てる
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: この記事では、PowerShell を使用してライセンスを持たないユーザーにMicrosoft 365 ライセンスを割り当てる方法について説明します。
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572623"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>PowerShell を使用してMicrosoft 365ライセンスをユーザー アカウントに割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ユーザーは、ライセンス プランからライセンスが割り当てられるまで、Microsoft 365 サービスを使用できません。 PowerShell を使用すると、ライセンスをライセンスのないアカウントにすばやく割り当てることができます。 

ユーザー アカウントには、まず場所を割り当てる必要があります。 場所の指定は[、Microsoft 365管理センター](../admin/add-users/add-users.md)で新しいユーザー アカウントを作成する際に必要な部分です。 

オンプレミスの Active Directory ドメイン サービスから同期されたアカウントには、既定では場所が指定されていません。 これらのアカウントの場所は、次の場所から構成できます。

- Microsoft 365 管理センター
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - [Azure ポータル](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)(**ユーザー**  >  アカウント>ユーザー アカウント>**プロファイル**  >  **連絡先情報**  >  **国または地域**) 。

>[!Note]
>Microsoft 365管理センター[でユーザー アカウントにライセンスを割り当てる方法について説明](../admin/manage/assign-licenses-to-users.md)します。 その他のリソースの一覧については、 [ユーザーとグループの管理 を](../admin/add-users/index.yml)参照してください。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず[、Microsoft 365のテナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  

次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、ライセンスを追加するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれます)。

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

最後に、ユーザーサインイン名とライセンス プラン名を指定し、これらのコマンドを実行します。

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

このモジュールの機能が新しい[Azure Active Directory の PowerShell](/powershell/azuread/v2/azureactivedirectory)モジュールで利用可能な場合は、このモジュールの非推奨Graph始めます。 新しい PowerShell スクリプトを作成するお客様には、このモジュールではなく新しいモジュールを使用することをお勧めします。

まず[、Microsoft 365のテナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

`Get-MsolAccountSku`このコマンドを実行して、使用可能なライセンス プランと、組織の各プランで使用可能なライセンス数を表示します。 各プランで利用可能なライセンスの数は、 **ActiveUnits** - **WarningUnits** - **ConsumedUnits** です。 ライセンス プラン、ライセンス、およびサービスの詳細については [、「PowerShell を使用してライセンスとサービスを表示](view-licenses-and-services-with-microsoft-365-powershell.md)する」を参照してください。

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

組織内のライセンスされていないアカウントを検索するには、このコマンドを実行します。

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

ライセンスを割り当てるのは **、UsageLocation** プロパティが有効な ISO 3166-1 alpha-2 の国コードに設定されているユーザー アカウントに限られます。 たとえば、米国は US、フランスは FR です。 一部のMicrosoft 365サービスは、一部の国では利用できません。 詳細については、「 [ライセンス制限について」](https://go.microsoft.com/fwlink/p/?LinkId=691730)を参照してください。
    
**[使用** 場所] の値がないアカウントを検索するには、次のコマンドを実行します。

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

アカウントの **UsageLocation** 値を設定するには、このコマンドを実行します。

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

この例では **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンス プランからライセンスをライセンスのないユーザー **belindan \@ litwareinc.com** に割り当てます。
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

ライセンスをすべてのライセンスユーザーに割り当てるには、このコマンドを実行します。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>複数のライセンスを同じライセンス プランのユーザーに割り当てることはできません。 十分な数の利用可能なライセンスをお持ちでない場合は、使用可能なライセンスがなくなるまで、ライセンスは **Get-MsolUser** コマンドレットによって返される順序でユーザーに割り当てられます。
>

この例では **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンス プランのライセンスを、ライセンスを持つすべてのユーザーに割り当てます。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

この例では、同じライセンスを米国の営業部門のライセンスのないユーザーに割り当てます。
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Graph モジュールの PowerShell を Azure Active Directory使用して、別のサブスクリプション (ライセンス プラン) にユーザーを移動Graph

まず[、Microsoft 365のテナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
次に、サブスクリプションを切り替えるユーザー アカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれます)。

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

ユーザーが現在持っているサブスクリプション (FROM サブスクリプション) とユーザーが移動しているサブスクリプション (TO サブスクリプション) を識別します。

最後に、TO および FROM サブスクリプション名 (SKU の部品番号) を指定し、これらのコマンドを実行します。

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
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
