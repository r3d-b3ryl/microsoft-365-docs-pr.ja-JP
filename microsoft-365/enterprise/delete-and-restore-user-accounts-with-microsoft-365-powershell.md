---
title: PowerShell Microsoft 365ユーザー アカウントを削除する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: PowerShell でさまざまなモジュールを使用してユーザー アカウントを削除するMicrosoft 365説明します。
ms.openlocfilehash: 33a5a8d79413549d98bc0289dc1239e88cbc7c109334245cb6a7fa536477a89d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819429"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>PowerShell Microsoft 365ユーザー アカウントを削除する

PowerShell を使用して、ユーザー Microsoft 365を削除および復元できます。

>[!Note]
>ユーザー アカウントを[復元する方法については、Microsoft 365 管理センター。](../admin/add-users/restore-user.md)
>
>その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

接続後、次の構文を使用して個々のユーザー アカウントを削除します。
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

次の使用例は、ユーザー アカウント *fabricec を削除 \@ litwareinc.com。*
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> **Remove-AzureADUser** コマンドレットの *-ObjectID* パラメーターは、アカウントのサインイン名 (ユーザー プリンシパル名またはアカウントのオブジェクト ID とも呼ばれる) を受け入れる。
  
ユーザーの名前に基づいてアカウント名を表示するには、以下のコマンドを使用します。
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

次の使用例は、ユーザー *Caleb Sills のアカウント名を表示します*。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

ユーザーの表示名に基づいてアカウントを削除するには、次のコマンドを使用します。
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

ユーザー アカウントを削除する場合は、Microsoft Azure Active DirectoryモジュールをWindows PowerShellアカウントは完全に削除されません。 削除されたユーザー アカウントは 30 日以内であれば復元できます。

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

ユーザー アカウントを削除するには、次の構文を使用します。
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットは、Windows PowerShell から実行します。
>

次の使用例は、ユーザー アカウントを *削除 BelindaN@litwareinc.com。*
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

削除されたユーザー アカウントを 30 日間の猶予期間内に復元するには、次の構文を使用します。
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

次の使用例は、削除されたアカウント BelindaN を復元 *\@ litwareinc.com。*
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> 復元できる削除されたユーザーの一覧を表示するには、次のコマンドを実行します。
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> ユーザー アカウントの元のユーザー プリンシパル名を別のアカウントで使用する場合は _、UserPrincipalName_ ではなく _NewUserPrincipalName_ パラメーターを使用して、ユーザー アカウントを復元するときに別のユーザー プリンシパル名を指定します。


## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)