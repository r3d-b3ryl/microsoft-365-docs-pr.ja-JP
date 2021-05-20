---
title: 個別のユーザーのパスワードを無期限に設定する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
description: Windows PowerShellを使用して、一部のユーザーパスワードが期限切れにならない場合は、Microsoft 365管理者アカウントにサインインします。
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571927"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>個別のユーザーのパスワードを無期限に設定する

この資料では、個々のユーザーが期限切れにならないパスワードを設定する方法について説明します。 PowerShell を使用してこれらの手順を完了する必要があります。

## <a name="before-you-begin"></a>開始する前に

この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは](../../business-video/admin-center-overview.md)。 

これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。

Microsoft クラウド サービスのグローバル管理者は[、Graphに Azure Active Directory PowerShell を](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)使用して、特定のユーザーに対してパスワードの有効期限が切れないように設定できます。 [また、AzureAD](/powershell/module/Azuread)コマンドレットを使用して、無期限の構成を削除したり、どのユーザー パスワードが期限切れに設定されているかを確認することもできます。

このガイドは、Id サービスとディレクトリ サービスを Azure AD に依存する Intune や Microsoft 365 などの他のプロバイダーにも適用されます。 パスワードの有効期限は、ポリシーの変更可能な唯一の部分です。

> [!NOTE]
> ディレクトリ同期を通じて同期されないユーザー アカウントのパスワードのみを期限切れに設定できます。 ディレクトリ同期の詳細については[、「Azure AD を使用Connect AD」](/azure/active-directory/connect/active-directory-aadconnect)を参照してください。

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>パスワードの有効期限ポリシーを確認する方法

AzureAD モジュールのGet-AzureADUser コマンドの詳細については、参照記事 [「Get-AzureADUser」](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)を参照してください。

次のいずれかのコマンドを実行します：

- 1 人のユーザーのパスワードが無期限に設定されているかどうかを確認するには、UPN *(user@contoso.onmicrosoft.com)* など) または確認するユーザーのユーザー ID を使用して、次のコマンドレットを実行します。

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

- すべてのユーザーの **[パスワードを無期限** にする] 設定を表示するには、次のコマンドレットを実行します。

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 名前が l の現在のユーザーのデスクトップ上の Html でパスワードを持つすべてのユーザーのレポート **ReportPasswordNeverExpires.htm** 取得するには

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- 名前が **ReportPasswordNeverExpires.csv** の現在のユーザーのデスクトップ上の CSV でパスワードを持つすべてのユーザーのレポートを取得するには

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 組織内のすべてのユーザーのパスワードを無期限に設定するには、次のコマンドレットを実行します。

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> パラメータを使用して構成されたユーザー アカウント `-PasswordPolicies DisablePasswordExpiration` は、属性に基づいて経過時間が残っています `pwdLastSet` 。 属性に基づいて `pwdLastSet` 、有効期限を に変更した場合 `-PasswordPolicies None` 、90 日を超える pwdLastSet を持つすべてのパスワードは、ユーザーが次回サインインするときに変更する必要があります。 この変更は、多数のユーザーに影響を与える可能性があります。

### <a name="set-a-password-to-expire"></a>パスワードを期限切れに設定する

次のいずれかのコマンドを実行します：

- パスワードの有効期限が切れるように 1 人のユーザーのパスワードを設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 組織内のすべてのユーザーのパスワードを設定して有効期限が切れるようにするには、次のコマンドレットを使用します。

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>関連コンテンツ

[ユーザーが自分でパスワードをリセットできるようにする](../add-users/let-users-reset-passwords.md) (記事)

[パスワードをリセットする](../add-users/reset-passwords.md) (記事)