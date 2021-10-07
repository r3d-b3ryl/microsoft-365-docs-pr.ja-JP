---
title: PowerShell Microsoft 365ユーザー アカウントをブロックする
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: PowerShell を使用して、アカウントへのアクセスをブロックおよびブロック解除するMicrosoft 365方法。
ms.openlocfilehash: 0ecfdfb8f99175ce5312769593c7637a7d1ae25b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189191"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>PowerShell Microsoft 365ユーザー アカウントをブロックする

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 アカウントへのアクセスをブロックすると、だれもがアカウントを使用してサインインし、組織のサービスとデータにアクセスMicrosoft 365します。 PowerShell を使用して、個々のユーザー アカウントまたは複数のユーザー アカウントへのアクセスをブロックできます。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="block-access-to-individual-user-accounts"></a>個々のユーザー アカウントへのアクセスをブロックする

次の構文を使用して、個々のユーザー アカウントをブロックします。

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> *Set-AzureAD* コマンドレットの **-ObjectID** パラメーターは、アカウントサインイン名 (ユーザー プリンシパル名とも呼ばれる) またはアカウントのオブジェクト ID を受け入れる。

次の使用例は、ユーザー アカウントへの *アクセスをブロック* fabricec@litwareinc.com。

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

このユーザー アカウントのブロックを解除するには、以下のコマンドを実行します。

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

ユーザーの表示名に基づいてユーザー アカウント UPN を表示するには、次のコマンドを使用します。

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

次の使用例は、ユーザー  *Caleb Sills のユーザー アカウント UPN を表示します*。

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

ユーザーの表示名に基づいてアカウントをブロックするには、次のコマンドを使用します。

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

ユーザー アカウントのブロックされた状態を確認するには、次のコマンドを使用します。

```powershell
Get-AzureADUser  -ObjectID <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>複数のユーザー アカウントをブロックする

複数のユーザー アカウントのアクセスをブロックするには、次のように各行に 1 つのアカウント サインイン名を含むテキスト ファイルを作成します。

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

次のコマンドでは、テキスト ファイルの例は *C:\My Documents\Accounts.txtです*。 このファイル名をテキスト ファイルのパスとファイル名に置き換える。

テキスト ファイルに記載されているアカウントへのアクセスをブロックするには、次のコマンドを実行します。

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

テキスト ファイルに一覧表示されているアカウントのブロックを解除するには、次のコマンドを実行します。

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="block-individual-user-accounts"></a>個々のユーザー アカウントをブロックする

個々のユーザー アカウントのアクセスをブロックするには、次の構文を使用します。

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core では、Msol を名前に含Microsoft Azure Active DirectoryモジュールWindows PowerShellコマンドレットのモジュール *モジュールは* サポートされていません。 これらのコマンドレットは、次の手順で実行Windows PowerShell。

この例では、ユーザー アカウント *fabricec \@* へのアクセスをブロック litwareinc.com。

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

ユーザー アカウントのブロックを解除するには、次のコマンドを実行します。

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

ユーザー アカウントのブロックされた状態を確認するには、次のコマンドを実行します。

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>複数のユーザー アカウントのアクセスをブロックする

最初に、次のように各行に 1 つのアカウントを含むテキスト ファイルを作成します。

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

次のコマンドでは、テキスト ファイルの例は *C:\My Documents\Accounts.txtです*。 このファイル名をテキスト ファイルのパスとファイル名に置き換える。

テキスト ファイルに一覧表示されているアカウントのアクセスをブロックするには、次のコマンドを実行します。

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
