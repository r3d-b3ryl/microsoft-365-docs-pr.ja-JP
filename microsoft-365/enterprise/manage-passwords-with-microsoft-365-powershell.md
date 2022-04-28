---
title: PowerShell でパスワードを管理する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
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
- O365ITProTrain
description: PowerShell を使用してパスワードを管理する方法について説明します。
ms.openlocfilehash: e980e9c4c2511ea1f84df870c790a61a047c3a90
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091569"
---
# <a name="manage-passwords-with-powershell"></a>PowerShell でパスワードを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365でパスワードを管理するには、Microsoft 365 管理センターの代わりに PowerShell をMicrosoft 365に使用できます。 

この記事のコマンド ブロックで変数値を指定する必要がある場合は、次の手順を使用します。

1. コマンド ブロックをクリップボードにコピーし、メモ帳または PowerShell 統合スクリプト環境 (ISE) に貼り付けます。
2. 変数の値を入力し、"<" 文字と ">" 文字を削除します。
3. PowerShell ウィンドウまたは PowerShell ISE でコマンドを実行します。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="set-a-password"></a>パスワードを設定する

これらのコマンドを使用して、ユーザー アカウントのパスワードを指定します。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>ユーザーにパスワードの変更を強制する

これらのコマンドを使用して、パスワードを設定し、ユーザーに新しいパスワードの変更を強制します。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

これらのコマンドを使用して、パスワードを設定し、次回サインイン時にユーザーに新しいパスワードの変更を強制します。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="set-a-password"></a>パスワードを設定する

これらのコマンドを使用して、ユーザー アカウントのパスワードを指定します。

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>ユーザーにパスワードの変更を強制する

これらのコマンドを使用して、ユーザーにパスワードの変更を強制します。

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)

