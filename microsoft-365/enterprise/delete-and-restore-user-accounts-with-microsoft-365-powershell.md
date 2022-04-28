---
title: PowerShell でMicrosoft 365ユーザー アカウントを削除する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/23/2020
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: PowerShell のさまざまなモジュールを使用してMicrosoft 365ユーザー アカウントを削除する方法について説明します。
ms.openlocfilehash: b3d273e6f2274b43018848e5439f431281a54df8
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093440"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>PowerShell でMicrosoft 365ユーザー アカウントを削除する

Microsoft 365に PowerShell を使用して、ユーザー アカウントを削除および復元できます。

>[!Note]
>Microsoft 365 管理センターを使用して[ユーザー アカウントを復元](../admin/add-users/restore-user.md)する方法について説明します。
>
>その他のリソースの一覧については、「 [ユーザーとグループの管理](/admin)」を参照してください。
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

接続後、次の構文を使用して個々のユーザー アカウントを削除します。
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

この例では、ユーザー アカウント *fabricec\@ litwareinc.com を* 削除します。
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> **Remove-AzureADUser** コマンドレットの *-ObjectID* パラメーターは、アカウントのサインイン名 (ユーザー プリンシパル名またはアカウントのオブジェクト ID とも呼ばれます) を受け入れます。
  
ユーザーの名前に基づいてアカウント名を表示するには、以下のコマンドを使用します。
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

この例では、ユーザー *Caleb Sills* のアカウント名を表示します。
  
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

Windows PowerShellのMicrosoft Azure Active Directory モジュールを使用してユーザー アカウントを削除しても、そのアカウントは完全には削除されません。 削除されたユーザー アカウントは 30 日以内であれば復元できます。

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

ユーザー アカウントを削除するには、次の構文を使用します。
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。
>

次の使用例は、ユーザー アカウント *BelindaN@litwareinc.com* を削除します。
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

削除されたユーザー アカウントを 30 日間の猶予期間内に復元するには、次の構文を使用します。
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

次の使用例は、削除されたアカウント *BelindaN\@ litwareinc.com* を復元します。
  
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
> ユーザー アカウントの元のユーザー プリンシパル名が別のアカウントで使用されている場合は、_UserPrincipalName の代わりに NewUserPrincipalName_ パラメーターを使用して、ユーザー アカウントを復元するときに別のユーザー プリンシパル名を指定します。


## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)