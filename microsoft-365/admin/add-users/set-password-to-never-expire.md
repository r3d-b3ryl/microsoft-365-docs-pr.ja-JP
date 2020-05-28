---
title: 個別のユーザーのパスワードを無期限に設定する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Windows PowerShell を使用して、一部のユーザーパスワードを期限切れにしないように設定する方法について説明します。
ms.openlocfilehash: 6562a4092c47d9c4bf7bf294767e6050a3e0577a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387007"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>個別のユーザーのパスワードを無期限に設定する

## <a name="set-the-password-expiration-policy-for-your-organization"></a>組織のパスワード有効期限ポリシーを設定します。

1. 管理センターで、[**設定**の \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">設定</a>] ページに移動します。
2. [設定] ページの上部で、[**セキュリティ & プライバシー**] を選択します。
3. [**パスワードの有効期限ポリシー**] を選択します。 
4. パスワードが期限切れにならないように設定されている場合は、[**ユーザーのパスワードの有効期限を何日後に設定**する] の横にあるチェックボックスをオンにします。 パスワードが期限切れになるまでの日数を指定するオプションが表示されます。

## <a name="set-the-password-expiration-policy-for-individual-users"></a>個々のユーザーのパスワードの有効期限ポリシーを設定する

Microsoft クラウドサービスのグローバル管理者は、 [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)を使用して、特定のユーザーに対してパスワードを無期限に設定することができます。 また、 [AzureAD](https://docs.microsoft.com/powershell/module/Azuread)コマンドレットを使用して、無期限の構成を削除したり、どのユーザーのパスワードが期限切れにならないかを確認したりすることもできます。

このガイドは、Intune や Microsoft 365 などの他のプロバイダーに適用されます。これは、id およびディレクトリサービスのために Azure AD にも依存しています。 ポリシーの変更可能な部分は、パスワードの有効期限のみです。

Graph の Azure AD PowerShell の詳細については、「 [Azure Active Directory powershell For graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)」を参照してください。

> [!NOTE]
> ディレクトリ同期によって同期されていないユーザーアカウントのパスワードのみ、期限切れにならないように構成できます。 ディレクトリ同期の詳細については、「 [CONNECT ad With AZURE ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)」を参照してください。

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>パスワードの有効期限ポリシーを確認する方法

AzureAD モジュールの Set-azureaduser コマンドの詳細については、「 [set-azureaduser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)」という参照記事を参照してください。

次のいずれかのコマンドを実行します。

- 単一のユーザーのパスワードが期限切れにならないように設定されているかどうかを確認するには、UPN (たとえば、 *user@contoso.onmicrosoft.com*) またはチェックするユーザーのユーザー ID を使用して、次のコマンドレットを実行します。

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    例:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- すべてのユーザーの**パスワードの有効期限**が設定されていないことを確認するには、次のコマンドレットを実行します。

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- **ReportPasswordNeverExpires**という名前の現在のユーザーのデスクトップに Html で PasswordNeverExpires を持つすべてのユーザーのレポートを取得するには

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- **ReportPasswordNeverExpires**という名前の現在のユーザーのデスクトップに Csv で PasswordNeverExpires を持つすべてのユーザーのレポートを取得するには

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a>パスワードの有効期限を設定する

次のいずれかのコマンドを実行します。

- パスワードの有効期限が切れるように1人のユーザーのパスワードを設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 組織内のすべてのユーザーのパスワードを期限切れになるように設定するには、次のコマンドレットを使用します。

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a>パスワードを無期限に設定する

次のいずれかのコマンドを実行します。

- 1人のユーザーのパスワードを無期限に設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 組織内のすべてのユーザーのパスワードを期限切れにならないように設定するには、次のコマンドレットを実行します。

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> パスワード `-PasswordPolicies DisablePasswordExpiration` は属性に基づいてエージングが設定さ `pwdLastSet` れています。 ユーザーのパスワードの有効期限が切れないように設定してから90日後に移行すると、パスワードの有効期限が切れます。 属性に基づいて、 `pwdLastSet` 有効期限を変更した場合、90日より前のパスワードについては、 `-PasswordPolicies None` 次に `pwdLastSet` サインインするときにユーザーを変更する必要があります。 この変更によって、多数のユーザーに影響を与える可能性があります。
