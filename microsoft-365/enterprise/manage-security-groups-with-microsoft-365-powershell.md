---
title: PowerShell を使用してセキュリティ グループを管理する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: PowerShell を使用してセキュリティ グループを管理する方法について説明します。
ms.openlocfilehash: e9842585fbb88711c0efa6e515ca8b54c124338e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220937"
---
# <a name="manage-security-groups-with-powershell"></a>PowerShell を使用してセキュリティ グループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

PowerShell を使用して、Microsoft 365グループを管理する代わりに、Microsoft 365 管理センターを使用できます。 

この記事では、設定の一覧、作成、変更、およびセキュリティ グループの削除について説明します。 

この記事のコマンド ブロックで変数値を指定する必要がある場合は、次の手順を使用します。

1. コマンド ブロックをクリップボードにコピーし、コマンド ブロックメモ帳 PowerShell 統合スクリプト環境 (ISE) に貼り付けます。
2. 変数の値を入力し、"<" 文字と ">" 文字を削除します。
3. PowerShell ウィンドウまたは PowerShell ISE でコマンドを実行します。

「セキュリティ [グループ メンバーシップを維持して PowerShell](maintain-group-membership-with-microsoft-365-powershell.md) でグループ メンバーシップを管理する」を参照してください。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="list-your-groups"></a>グループを一覧表示する

このコマンドを使用して、すべてのグループを一覧表示します。

```powershell
Get-AzureADGroup
```
特定のグループの設定を表示名で表示するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>新しいグループを作成する

新しいセキュリティ グループを作成するには、このコマンドを使用します。

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>グループの設定を変更する

これらのコマンドを使用して、グループの設定を表示します。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

次に [、Set-AzureADGroup の記事を使用](/powershell/module/azuread/set-azureadgroup) して、設定を変更する方法を決定します。

### <a name="remove-a-security-group"></a>セキュリティ グループを削除する

セキュリティ グループを削除するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>セキュリティ グループの所有者を管理する

セキュリティ グループの現在の所有者を表示するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
次のコマンドを使用して、セキュリティ グループの現在の所有者にユーザー プリンシパル名 **(UPN)** でユーザー アカウントを追加します。

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
これらのコマンドを使用して、ユーザー アカウントを表示名でセキュリティ **グループの** 現在の所有者に追加します。

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
これらのコマンドを使用して **、UPN** によってセキュリティ グループの現在の所有者に対してユーザー アカウントを削除します。

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

次のコマンドを使用して、セキュリティ グループの現在の所有者に **表示名で** ユーザー アカウントを削除します。

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="list-your-groups"></a>グループを一覧表示する

このコマンドを使用して、すべてのグループを一覧表示します。

```powershell
Get-MsolGroup
```
特定のグループの設定を表示名で表示するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>新しいグループを作成する

新しいセキュリティ グループを作成するには、このコマンドを使用します。

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>グループの設定を変更する

これらのコマンドを使用して、グループの設定を表示します。

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

次に [、Set-MsolGroup の記事を使用](/powershell/module/msonline/set-msolgroup) して、設定を変更する方法を決定します。

### <a name="remove-a-security-group"></a>セキュリティ グループを削除する

セキュリティ グループを削除するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)