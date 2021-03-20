---
title: PowerShell を使用して Microsoft 365 ライセンスをユーザー アカウントに割り当てる
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
description: この記事では、PowerShell を使用して、ライセンスのないユーザーに Microsoft 365 ライセンスを割り当てる方法について説明します。
ms.openlocfilehash: 5fb5f9095d4f732b0bf23f26eebb22eff608b48c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905466"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>PowerShell を使用して Microsoft 365 ライセンスをユーザー アカウントに割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

アカウントにライセンス プランからライセンスが割り当てられるまで、ユーザーは Microsoft 365 サービスを使用できません。 PowerShell を使用すると、ライセンスのないアカウントにライセンスをすばやく割り当てできます。 

ユーザー アカウントには、最初に場所を割り当てる必要があります。 場所の指定は [、Microsoft 365](../admin/add-users/add-users.md)管理センターで新しいユーザー アカウントを作成する際に必要な部分です。 

オンプレミスの Active Directory ドメイン サービスから同期されたアカウントは、既定では場所が指定されていません。 これらのアカウントの場所は、次の場所から構成できます。

- Microsoft 365 管理センター
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Active **Directory Users**  >  **>** プロファイル連絡先>**国**  >    >  または地域)

>[!Note]
>Microsoft 365 管理[センターで](../admin/manage/assign-licenses-to-users.md)ユーザー アカウントにライセンスを割り当てる方法について説明します。 その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  

次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、ライセンスを追加するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を取得します。

次に、ユーザー アカウントに使用場所が割り当てられているか確認します。

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

まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

このコマンドを実行して、利用可能なライセンス プランと、組織内の各プランで使用可能な `Get-MsolAccountSku` ライセンスの数を表示します。 各プランで利用可能なライセンスの数は、 **ActiveUnits** - **WarningUnits** - **ConsumedUnits** です。 ライセンス プラン、ライセンス、およびサービスの詳細については、「PowerShell でライセンスとサービスを表示 [する」を参照してください](view-licenses-and-services-with-microsoft-365-powershell.md)。

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

組織内のライセンスのないアカウントを検索するには、次のコマンドを実行します。

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

**UsageLocation** プロパティが有効な ISO 3166-1 α-2 の国コードに設定されているユーザー アカウントにのみライセンスを割り当てできます。 たとえば、米国は US、フランスは FR です。 一部の Microsoft 365 サービスは、特定の国では利用できません。 詳細については、「ライセンス制限 [について」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=691730)。
    
**UsageLocation** 値を持つアカウントを検索するには、次のコマンドを実行します。

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

アカウントの **UsageLocation 値を** 設定するには、次のコマンドを実行します。

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

次に例を示します。

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
**-All** パラメーターなしで **Get-MsolUser** コマンドレットを使用する場合、最初の 500 個のアカウントだけが返されます。

### <a name="assigning-licenses-to-user-accounts"></a>ユーザー アカウントへのライセンスの割り当て
    
ユーザーにライセンスを割り当てるには、PowerShell で次のコマンドを使用します。
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

次の使用例は **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンス プランのライセンスを、ライセンスのないユーザーの belindan litwareinc.com に **\@ 割り当 litwareinc.com。**
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

ライセンスのないすべてのユーザーにライセンスを割り当てるには、次のコマンドを実行します。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>複数のライセンスを同じライセンス プランのユーザーに割り当てることはできません。 十分な数の利用可能なライセンスをお持ちでない場合は、使用可能なライセンスがなくなるまで、ライセンスは **Get-MsolUser** コマンドレットによって返される順序でユーザーに割り当てられます。
>

次の使用例は **、litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) のライセンスプランからすべてのライセンスのないユーザーにライセンスを割り当てる。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

次の使用例は、米国の Sales 部門のライセンスのないユーザーに同じライセンスを割り当てします。
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell for Graph モジュールを使用してユーザーを別のサブスクリプション (ライセンス プラン) に移動する

まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
次に、サブスクリプションの切り替えに使用するユーザー アカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を取得します。

次に、このコマンドを使用してテナントのサブスクリプション (ライセンス プラン) を一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、これらのコマンドでユーザー アカウントが現在持っているサブスクリプションを一覧表示します。

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

ユーザーが現在持っているサブスクリプション (FROM サブスクリプション) と、ユーザーが移動するサブスクリプション (TO サブスクリプション) を識別します。

最後に、TO サブスクリプション名と FROM サブスクリプション名 (SKU パーツ番号) を指定し、これらのコマンドを実行します。

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