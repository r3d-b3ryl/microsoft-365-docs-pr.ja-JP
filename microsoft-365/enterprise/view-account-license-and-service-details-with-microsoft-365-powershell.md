---
title: PowerShell を使用Microsoft 365アカウント ライセンスとサービスの詳細を表示する
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
description: PowerShell を使用して、ユーザーに割り当てられているMicrosoft 365 サービスを決定する方法について説明します。
ms.openlocfilehash: 7e5724acbff571825f1496db5d59e04e11ba3a67
ms.sourcegitcommit: dc415d784226c77549ba246601f34324c4f94e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64915997"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>PowerShell を使用Microsoft 365アカウント ライセンスとサービスの詳細を表示する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365では、ライセンス プラン (SKU または Microsoft 365 プランとも呼ばれます) からのライセンスにより、ユーザーはそれらのプランに対して定義されているMicrosoft 365 サービスにアクセスできます。 しかし、ユーザーは、現在割り当てられているライセンスで使用可能なすべてのサービスにアクセスできるとは限りません。 Microsoft 365に PowerShell を使用して、ユーザー アカウント上のサービスの状態を表示できます。

ライセンス プラン、ライセンス、およびサービスの詳細については、「 [PowerShell を使用したライセンスとサービスの表示](view-licenses-and-services-with-microsoft-365-powershell.md)」を参照してください。

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Microsoft Graph PowerShell SDK を使用する

まず、[Microsoft 365 テナントに接続します](/graph/powershell/get-started#authentication)。

ライセンスの詳細を含むユーザー プロパティを読み取るには、User.Read.All アクセス許可スコープまたは[参照ページの [ユーザーの取得] Graph API](/graph/api/user-get)に一覧表示されている他のアクセス許可のいずれかが必要です。

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

次に、このコマンドを使用して、テナントのライセンス プランを一覧表示します。

```powershell
Get-MgSubscribedSku
```

これらのコマンドを使用して、各ライセンス プランで使用できるサービスを一覧表示します。

```powershell

$allSKUs = Get-MgSubscribedSku -Property SkuPartNumber, ServicePlans 
$allSKUs | ForEach-Object {
    Write-Host "Service Plan:" $_.SkuPartNumber
    $_.ServicePlans | ForEach-Object {$_}
}

```

これらのコマンドを使用して、ユーザー アカウントに割り当てられているライセンスを一覧表示します。

```powershell
Get-MgUserLicenseDetail -UserId "<user sign-in name (UPN)>"
```

次に例を示します。

```powershell
Get-MgUserLicenseDetail -UserId "belindan@litwareinc.com"
```

### <a name="to-view-services-for-a-user-account"></a>ユーザー アカウントのサービスを表示するには

ユーザーがアクセス権を持つすべてのMicrosoft 365 サービスを表示するには、次の構文を使用します。
  
```powershell
(Get-MgUserLicenseDetail -UserId <user account UPN> -Property ServicePlans)[<LicenseIndexNumber>].ServicePlans
```

この例では、ユーザー BelindaN@litwareinc.com がアクセスできるサービスを示します。 これにより、このユーザーのアカウントに割り当てられているすべてのライセンスに関連付けられているサービスが表示されます。
  
```powershell
(Get-MgUserLicenseDetail -UserId belindan@litwareinc.com -Property ServicePlans).ServicePlans
```

次の例では、ユーザー BelindaN@litwareinc.com が、アカウントに割り当てられている最初のライセンス (インデックス番号 0) からアクセスできるサービスが表示されます。
  
```powershell
(Get-MgUserLicenseDetail -UserId belindan@litwareinc.com -Property ServicePlans)[0].ServicePlans
```

*複数のライセンス* が割り当てられているユーザーのすべてのサービスを表示するには、次の構文を使用します。

```powershell
$userUPN="<user account UPN>"
$allLicenses = Get-MgUserLicenseDetail -UserId $userUPN -Property SkuPartNumber, ServicePlans
$allLicenses | ForEach-Object {
    Write-Host "License:" $_.SkuPartNumber
    $_.ServicePlans | ForEach-Object {$_}
}

```

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
次に、このコマンドを使用して、テナントのライセンス プランを一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

これらのコマンドを使用して、各ライセンス プランで使用できるサービスを一覧表示します。

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

これらのコマンドを使用して、ユーザー アカウントに割り当てられているライセンスを一覧表示します。

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

次に、このコマンドを実行して、組織で使用できるライセンス プランを一覧表示します。 

```powershell
Get-MsolAccountSku
```
>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

次に、このコマンドを実行して、各ライセンス プランで使用可能なサービスと、それらが一覧表示される順序 (インデックス番号) を一覧表示します。

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
このコマンドを使用して、ユーザーに割り当てられているライセンスと、それらが一覧表示される順序 (インデックス番号) を一覧表示します。

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>ユーザー アカウントのサービスを表示するには

ユーザーがアクセス権を持つすべてのMicrosoft 365 サービスを表示するには、次の構文を使用します。
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

この例では、ユーザー BelindaN@litwareinc.com がアクセスできるサービスを示します。 これにより、このユーザーのアカウントに割り当てられているすべてのライセンスに関連付けられているサービスが表示されます。
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

次の例では、ユーザー BelindaN@litwareinc.com が、アカウントに割り当てられている最初のライセンス (インデックス番号 0) からアクセスできるサービスが表示されます。
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

*複数のライセンス* が割り当てられているユーザーのすべてのサービスを表示するには、次の構文を使用します。

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
