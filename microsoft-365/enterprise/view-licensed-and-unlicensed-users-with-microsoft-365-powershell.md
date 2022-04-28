---
title: PowerShell を使用してライセンスおよびライセンスのないMicrosoft 365ユーザーを表示する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: この記事では、PowerShell を使用してライセンスおよびライセンスのないMicrosoft 365ユーザー アカウントを表示する方法について説明します。
ms.openlocfilehash: 65dcc8e397f9ad56679b880f50caa99a51e4a4c5
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095534"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>PowerShell を使用してライセンスおよびライセンスのないMicrosoft 365ユーザーを表示する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365組織内のユーザー アカウントには、組織で利用可能なライセンス プランから、利用可能なライセンスの一部、全部、またはいずれも割り当てられていない場合があります。 PowerShell を使用してMicrosoft 365を使用すると、組織内のライセンスユーザーとライセンスのないユーザーをすばやく見つけることができます。

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Microsoft Graph PowerShell SDK を使用する

まず、[Microsoft 365 テナントに接続します](/graph/powershell/get-started#authentication)。

ライセンスの詳細を含むユーザー プロパティを読み取るには、User.Read.All アクセス許可スコープまたは[参照ページの [ユーザーの取得] Graph API](/graph/api/user-get)に一覧表示されている他のアクセス許可のいずれかが必要です。

テナントで使用可能なライセンスを読み取るには、Organization.Read.All アクセス許可スコープが必要です。

```powershell
Connect-Graph -Scopes User.Read.All, Organization.Read.All
```

特定のユーザー アカウントのライセンスの詳細を表示するには、次のコマンドを実行します。
  
```powershell
Get-MgUserLicenseDetail -UserId "<user sign-in name (UPN)>"
```

次に例を示します。

```powershell
Get-MgUserLicenseDetail -UserId "belindan@litwareinc.com"
```

ライセンス プラン (ライセンスのないユーザー) が割り当てられていない組織内のすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-MgUser -Filter 'assignedLicenses/$count eq 0' -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All

Write-Host "Found $unlicensedUserCount unlicensed users."
```

ライセンス プラン (ライセンスのないユーザー) が割り当てられていない組織内のすべてのメンバー ユーザー アカウント (ゲストを除く) の一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-MgUser -Filter "assignedLicenses/`$count eq 0 and userType eq 'Member'" -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All

Write-Host "Found $unlicensedUserCount unlicensed users (excluding guests)."
```

ライセンス プラン (ライセンスユーザー) が割り当てられている組織内のすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-MgUser -Filter 'assignedLicenses/$count ne 0' -ConsistencyLevel eventual -CountVariable licensedUserCount -All -Select UserPrincipalName,DisplayName,AssignedLicenses | Format-Table -Property UserPrincipalName,DisplayName,AssignedLicenses

Write-Host "Found $licensedUserCount licensed users."
```

E5 ライセンスが割り当てられている組織内のすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。

```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'

Get-MgUser -Filter "assignedLicenses/any(x:x/skuId eq $($e5sku.SkuId) )" -ConsistencyLevel eventual -CountVariable e5licensedUserCount -All

Write-Host "Found $e5licensedUserCount E5 licensed users."
```

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 
ライセンス プラン (ライセンスのないユーザー) が割り当てられていない組織内のすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

ライセンス プラン (ライセンスユーザー) が割り当てられている組織内のすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>サブスクリプション内のすべてのユーザーを一覧表示するには、コマンドを `Get-AzureAdUser -All $true` 使用します。
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

組織内のすべてのユーザー アカウントとそのライセンス状態の一覧を表示するには、PowerShell で次のコマンドを実行します。
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

組織内でライセンスのないすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

組織内でライセンスのあるすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
