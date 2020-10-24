---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントを削除する
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
description: PowerShell で各種モジュールを使用して、Microsoft 365 ユーザーアカウントを削除する方法について説明します。
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754542"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>PowerShell を使用して Microsoft 365 ユーザーアカウントを削除する

Microsoft 365 の PowerShell を使用して、ユーザーアカウントを削除および復元することができます。

>[!Note]
>Microsoft 365 管理センターを使用して [ユーザーアカウントを復元](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) する方法について説明します。
>
>その他のリソースの一覧については、「 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)」を参照してください。
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。

接続した後、次の構文を使用して個々のユーザーアカウントを削除します。
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

この例では、ユーザーアカウント *fabricec \@ litwareinc.com*を削除します。
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> **Set-azureaduser**コマンドレットの *-ObjectID*パラメーターは、アカウントのサインイン名 (ユーザープリンシパル名またはアカウントのオブジェクト ID とも呼ばれます) のいずれかを受け入れます。
  
ユーザーの名前に基づいてアカウント名を表示するには、以下のコマンドを使用します。
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

次の使用例は、ユーザー *Caleb/ls*のアカウント名を表示します。
  
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

Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用してユーザーアカウントを削除しても、そのアカウントは完全に削除されません。 削除されたユーザー アカウントは 30 日以内であれば復元できます。

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。

ユーザー アカウントを削除するには、次の構文を使用します。
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core は、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールと、名前に *Msol* を指定したコマンドレットをサポートしていません。 これらのコマンドレットを Windows PowerShell から実行します。
>

この例では、ユーザーアカウント *BelindaN@litwareinc.com*を削除します。
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

削除されたユーザー アカウントを 30 日間の猶予期間内に復元するには、次の構文を使用します。
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

この例では、削除されたアカウントの * \@ litwareinc.com*を復元します。
  
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
> ユーザーアカウントの元のユーザープリンシパル名が別のアカウントで使用されている場合、ユーザーアカウントを復元するときに別のユーザープリンシパル名を指定するには、 _UserPrincipalName_の代わりに_newuserprincipalname_パラメーターを使用します。


## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
