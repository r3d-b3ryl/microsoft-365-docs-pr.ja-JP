---
title: PowerShell を使用してパスワードを管理する
ms.author: josephd
author: JoeDavies-MSFT
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
description: PowerShell を使用してパスワードを管理する方法について説明します。
ms.openlocfilehash: d3f5ebfb7f7171cd45cf5ad1749b7bbb807068f812ee2a37f78ead7f6e8660c6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53858749"
---
# <a name="manage-passwords-with-powershell"></a>PowerShell を使用してパスワードを管理する

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

PowerShell を使用して、Microsoft 365の代わりに、Microsoft 365 管理センターパスワードを管理Microsoft 365。 

この記事のコマンド ブロックで変数値を指定する必要がある場合は、次の手順を使用します。

1. コマンド ブロックをクリップボードにコピーし、コマンド ブロックメモ帳 PowerShell 統合スクリプト環境 (ISE) に貼り付けます。
2. 変数の値を入力し、"<" 文字と ">" 文字を削除します。
3. PowerShell ウィンドウまたは PowerShell ISE でコマンドを実行します。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="set-a-password"></a>パスワードを設定する

ユーザー アカウントのパスワードを指定するには、次のコマンドを使用します。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>ユーザーにパスワードの変更を強制する

次のコマンドを使用して、パスワードを設定し、ユーザーに新しいパスワードを強制的に変更します。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

次のコマンドを使用して、パスワードを設定し、ユーザーが次回サインインする時に新しいパスワードを強制的に変更します。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="set-a-password"></a>パスワードを設定する

ユーザー アカウントのパスワードを指定するには、次のコマンドを使用します。

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>ユーザーにパスワードの変更を強制する

ユーザーに強制的にパスワードを変更するには、次のコマンドを使用します。

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)

