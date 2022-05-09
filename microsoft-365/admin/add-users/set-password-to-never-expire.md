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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Microsoft 365管理者アカウントにサインインして、Windows PowerShellを使用して一部の個々のユーザー パスワードが期限切れにならないように設定します。
ms.openlocfilehash: f0eff70b2b95c7e318f8a7e52777d4b684dbd8bf
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61911535"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>個別のユーザーのパスワードを無期限に設定する

この記事では、個々のユーザーのパスワードを有効期限が切れないように設定する方法について説明します。 PowerShell を使用してこれらの手順を完了する必要があります。

## <a name="before-you-begin"></a>開始する前に

この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [Microsoft 365 管理センターの概要に関するページを](/microsoft-365/admin/admin-overview/admin-center-overview?view=o365-worldwide)参照してください。

これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。

Microsoft クラウド サービスのグローバル管理者は[、GraphにAzure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2) を使用して、特定のユーザーに対してパスワードの有効期限が切れないように設定できます。 [また、AzureAD](/powershell/module/Azuread) コマンドレットを使用して、期限切れのない構成を削除したり、期限切れにならないように設定されているユーザー パスワードを確認したりすることもできます。

このガイドは、IntuneやMicrosoft 365などの他のプロバイダーにも適用されます。ID およびディレクトリ サービスのAzure ADにも依存しています。 パスワードの有効期限は、変更できるポリシーの唯一の部分です。


## <a name="how-to-check-the-expiration-policy-for-a-password"></a>パスワードの有効期限ポリシーを確認する方法

AzureAD モジュールのGet-AzureADUser コマンドの詳細については、参照記事 [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser) を参照してください。

次のいずれかのコマンドを実行します：

- 1 人のユーザーのパスワードが期限切れにならないように設定されているかどうかを確認するには、UPN ( *user@contoso.onmicrosoft.com* など) または確認するユーザーのユーザー ID を使用して、次のコマンドレットを実行します。

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

- すべてのユーザーの **[パスワードの有効期限が切れない** ] 設定を表示するには、次のコマンドレットを実行します。

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 現在のユーザーのデスクトップで PasswordNeverExpires in Html を持つすべてのユーザーのレポートを取得するには  **、ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- PasswordNeverExpires を含むすべてのユーザーのレポートを CSV で取得するには、現在のユーザーのデスクトップに名前 **がReportPasswordNeverExpires.csv**

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
> パラメーターを使用して構成されたユーザー アカウントは、 `-PasswordPolicies DisablePasswordExpiration` 属性に基づいて有効期間が `pwdLastSet` 続けられます。 属性に基づいて `pwdLastSet` 、有効期限を `-PasswordPolicies None`90 日より前の pwdLastSet に変更すると、ユーザーは次回サインインするときにパスワードを変更する必要があります。 この変更は、多数のユーザーに影響を与える可能性があります。

### <a name="set-a-password-to-expire"></a>有効期限が切れるパスワードを設定する

次のいずれかのコマンドを実行します：

- パスワードが期限切れになるように 1 人のユーザーのパスワードを設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 組織内のすべてのユーザーのパスワードが期限切れになるように設定するには、次のコマンドレットを使用します。

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>関連コンテンツ

[ユーザーが自分でパスワードをリセットできるようにする](../add-users/let-users-reset-passwords.md) (記事)\
[パスワードをリセットする](../add-users/reset-passwords.md) (記事)\
[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md) (記事)
