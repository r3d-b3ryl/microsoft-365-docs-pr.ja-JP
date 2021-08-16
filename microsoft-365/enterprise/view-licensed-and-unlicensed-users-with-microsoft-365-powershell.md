---
title: PowerShell を使用して、ライセンスMicrosoft 365ライセンスされていないユーザーを表示する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/21/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: この記事では、PowerShell を使用してライセンスおよびライセンスのないユーザー アカウントを表示するMicrosoft 365説明します。
ms.openlocfilehash: 0f1b590dade1d07499ac6c9b5f8888d7cab7ecd6
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58354394"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>PowerShell を使用して、ライセンスMicrosoft 365ライセンスされていないユーザーを表示する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

組織のユーザー アカウントMicrosoft 365、組織内で利用可能なライセンス プランから、利用可能なライセンスの一部、すべて、または割り当てられていない可能性があります。 PowerShell を使用して、Microsoft 365ライセンスユーザーとライセンスのないユーザーをすばやく検索できます。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 
ライセンス プラン (ライセンスのないユーザー) が割り当てられていない組織内のすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

ライセンス プラン (ライセンス ユーザー) が割り当てられている組織内のすべてのユーザー アカウントの一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>サブスクリプション内のすべてのユーザーを一覧表示するには、コマンドを使用 `Get-AzureAdUser -All $true` します。
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

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
