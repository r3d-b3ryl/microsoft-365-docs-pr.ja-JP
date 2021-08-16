---
title: PowerShell を使用してセキュリティ グループ メンバーシップを維持する
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell を使用してグループ内のメンバーシップを維持するMicrosoft 365します。
ms.openlocfilehash: 0a66db0748c50d296ff9d26969ae8b3caa7f310f
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356698"
---
# <a name="maintain-security-group-membership-with-powershell"></a>PowerShell を使用してセキュリティ グループ メンバーシップを維持する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

PowerShell を使用して、Microsoft 365の代わりに、Microsoft 365 管理センターグループ のメンバーシップを維持Microsoft 365。 

>[!Note]
>[グループ メンバーシップを管理Microsoft 365する方法について](../admin/create-groups/add-or-remove-members-from-groups.md)Microsoft 365 管理センター。 その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する
最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>グループのメンバーとしてユーザー アカウントを追加または削除する

**UPN** でユーザー アカウントを追加するには、ユーザー アカウントのユーザー プリンシパル名 (UPN) (例: belindan@contoso.com) とセキュリティ グループの表示名を入力し、"<" 文字と ">" 文字を削除し、PowerShell ウィンドウまたは PowerShell 統合スクリプト環境 (ISE) でこれらのコマンドを実行します。

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

表示名でユーザー アカウントを追加するには、ユーザー アカウントの表示名 (例: Belinda Newman) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**UPN** でユーザー アカウントを削除するには、ユーザー アカウント UPN (例: belindan@contoso.com) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

表示名でユーザー アカウントを削除するには、ユーザー アカウントの表示名 (例: Belinda Newman) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>グループのメンバーとしてグループを追加または削除する

セキュリティ グループには、他のグループをメンバーとして含めできます。 Microsoft 365グループは使用できません。 このセクションには、セキュリティ グループのグループのみを追加または削除する PowerShell コマンドが含まれています。

グループを表示名で追加するには、追加するグループの表示名と、メンバー グループを含むグループの表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**グループ** を表示名で削除するには、削除するグループの表示名と、メンバー グループを含むグループの表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>グループのメンバーとしてユーザー アカウントを追加または削除する

**UPN** でユーザー アカウントを追加するには、ユーザー アカウントのユーザー プリンシパル名 (UPN) (例: belindan@contoso.com) とグループ表示名を入力し、"<" 文字と ">" 文字を削除し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

表示名でユーザー アカウントを追加するには、ユーザー アカウントの表示名 (例: Belinda Newman) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**UPN** でユーザー アカウントを削除するには、ユーザー アカウント UPN (例: belindan@contoso.com) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

表示名でユーザー アカウントを削除するには、ユーザー アカウントの表示名 (例: Belinda Newman) とグループ表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>グループのメンバーとしてグループを追加または削除する

セキュリティ グループには、他のグループをメンバーとして含めできます。 Microsoft 365グループは使用できません。 このセクションには、セキュリティ グループのグループのみを追加または削除する PowerShell コマンドが含まれています。

グループを表示名で追加するには、追加するグループの表示名と、メンバー グループを含むグループの表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

**グループ** を表示名で削除するには、削除するグループの表示名と、メンバー グループを含むグループの表示名を入力し、PowerShell ウィンドウまたは PowerShell ISE でこれらのコマンドを実行します。

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)