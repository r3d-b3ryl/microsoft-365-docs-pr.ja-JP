---
title: Microsoft 365 のユーザーアカウントに PowerShell を使用することを禁止する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: PowerShell を使用して、Microsoft 365 アカウントへのアクセスをブロックおよびブロック解除する方法について説明します。
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754682"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365 のユーザーアカウントに PowerShell を使用することを禁止する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 アカウントへのアクセスをブロックする場合は、ユーザーがアカウントを使用して Microsoft 365 組織のサービスとデータにサインインしてアクセスするのを防ぐことができます。 PowerShell を使用して、個別のまたは複数のユーザーアカウントへのアクセスをブロックすることができます。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。
 
### <a name="block-access-to-individual-user-accounts"></a>個別のユーザーアカウントへのアクセスをブロックする

個々のユーザーアカウントをブロックするには、次の構文を使用します。
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> **AzureAD**コマンドレットの *-ObjectID*パラメーターは、アカウントのサインイン名 (ユーザープリンシパル名とも呼ばれる)、またはアカウントのオブジェクト ID のいずれかを受け入れます。
  
この例では、ユーザーアカウント *fabricec@litwareinc.com*へのアクセスをブロックします。
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

このユーザー アカウントのブロックを解除するには、以下のコマンドを実行します。
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

ユーザーの表示名に基づいてユーザーアカウント UPN を表示するには、次のコマンドを使用します。
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

この例では、ユーザー  *Caleb*のユーザーアカウント UPN を表示します。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

ユーザーの表示名に基づいてアカウントをブロックするには、次のコマンドを使用します。
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

ユーザーアカウントのブロックされた状態を確認するには、次のコマンドを使用します。
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>複数のユーザーアカウントをブロックする

複数のユーザーアカウントのアクセスをブロックするには、次のように各行に1つのアカウントサインイン名を含むテキストファイルを作成します。
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

次のコマンドでは、サンプルテキストファイルは *C:\My Documents\Accounts.txt*です。 このファイル名を、テキストファイルのパスとファイル名に置き換えます。
  
テキスト ファイルに記載されているアカウントへのアクセスをブロックするには、次のコマンドを実行します。
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

テキストファイルに記載されているアカウントのブロックを解除するには、次のコマンドを実行します。
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。
    
### <a name="block-individual-user-accounts"></a>個別のユーザーアカウントをブロックする

個別のユーザーアカウントのアクセスをブロックするには、次の構文を使用します。
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core は、Windows PowerShell モジュールの Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットは、Windows PowerShell から実行する必要があります。

この例では、ユーザーアカウント *fabricec \@ litwareinc.com*へのアクセスをブロックします。
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

ユーザー アカウントのブロックを解除するには、次のコマンドを実行します。
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

ユーザーアカウントのブロック状態を確認するには、次のコマンドを実行します。
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>複数のユーザーアカウントのアクセスをブロックする

最初に、次のような各行に1つのアカウントを含むテキストファイルを作成します。
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

次のコマンドでは、サンプルテキストファイルは *C:\My Documents\Accounts.txt*です。 このファイル名を、テキストファイルのパスとファイル名に置き換えます。
    
テキストファイルに記載されているアカウントのアクセスをブロックするには、次のコマンドを実行します。
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
テキスト ファイルに記載されているアカウントへのアクセスのブロックを解除するには、次のコマンドを実行します。
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
