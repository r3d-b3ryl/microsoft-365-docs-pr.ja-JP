---
title: PowerShell Microsoft 365アカウント のライセンスとサービスの詳細を表示する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
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
- PowerShell
- Ent_Office_Other
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: PowerShell を使用して、ユーザーに割り当Microsoft 365サービスを特定する方法について説明します。
ms.openlocfilehash: c02d3ffe2fff330f46adfc6b6dd49e553f69ad86
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209527"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>PowerShell Microsoft 365アカウント のライセンスとサービスの詳細を表示する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

このMicrosoft 365ライセンス プラン (SKU または Microsoft 365 プランとも呼ばれる) のライセンスにより、ユーザーはそれらのプランに対して定義されている Microsoft 365 サービスにアクセスできます。 しかし、ユーザーは、現在割り当てられているライセンスで使用可能なすべてのサービスにアクセスできるとは限りません。 PowerShell を使用して、Microsoft 365サービスの状態を表示できます。 

ライセンス プラン、ライセンス、およびサービスの詳細については、「PowerShell でライセンスとサービスを表示 [する」を参照してください](view-licenses-and-services-with-microsoft-365-powershell.md)。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

これらのコマンドを使用して、各ライセンス プランで使用可能なサービスを一覧表示します。

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

ユーザー アカウントに割り当てられているライセンスを一覧表示するには、次のコマンドを使用します。

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

次に、このコマンドを実行して、組織で利用可能なライセンス プランを一覧表示します。 

```powershell
Get-MsolAccountSku
```
>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

次に、このコマンドを実行して、各ライセンス プランで使用可能なサービスと、そのサービスがリストされている順序 (インデックス番号) を一覧表示します。

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
このコマンドを使用して、ユーザーに割り当てられているライセンスと、ユーザーがリストされている順序 (インデックス番号) を一覧表示します。

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>ユーザー アカウントのサービスを表示するには

ユーザーがアクセスできるMicrosoft 365サービスを表示するには、次の構文を使用します。
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

次の使用例は、ユーザーがアクセスできるサービス BelindaN@litwareinc.com 示しています。 これにより、このユーザーのアカウントに割り当てられているすべてのライセンスに関連付けられているサービスが表示されます。
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

次の例では、ユーザー BelindaN@litwareinc.com が、アカウントに割り当てられている最初のライセンス (インデックス番号 0) からアクセスできるサービスが表示されます。
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

複数のライセンスが割り当てられているユーザーのすべてのサービスを表示するには *、次の* 構文を使用します。

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
