---
title: ユーザーの強力なパスワード要件を無効にする
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
search.appverid:
- BCS160
- MET150
- MOE150
description: ビジネス、学校、非営利団体のパスワード ポリシーを管理する管理者の場合は、Azure AD PowerShell を使用して強力なパスワード要件を設定できます。
ms.openlocfilehash: 72f7e5dd36cf011592daf4bac2e57c438106319a
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441682"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>ユーザーの強力なパスワード要件を無効にする

この記事では、ユーザーの強力なパスワード要件を無効にする方法について説明します。 Microsoft 365 for business 組織では、強力なパスワード要件が既定で有効になっています。 組織には、強力なパスワードを無効にする必要がある場合があります。 強力なパスワード要件を無効にするには、次の手順に従います。 PowerShell を使用してこれらの手順を完了する必要があります。

## <a name="before-you-begin"></a>はじめに

この記事は、ビジネス、学校、非営利団体のパスワード ポリシーを管理するユーザーを対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは](../admin-overview/admin-center-overview.md#overview-of-the-microsoft-365-admin-center) これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。

PowerShell を使用して Microsoft 365 に接続する必要もあります。

## <a name="set-strong-passwords"></a>強力なパスワードを設定する

1. [PowerShell を使用して Microsoft 365 に接続](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。

2. PowerShell を使用すると、次のコマンドを使用して、すべてのユーザーの強力なパスワード要件を無効にすることができます。

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn **OFF** strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> userPrincipalName は、ユーザー名の後に at sign (@) とドメイン名が続くインターネット スタイルのサインイン形式である必要があります。 たとえば、user@contoso.com。

## <a name="related-content"></a>関連コンテンツ

[PowerShell で Microsoft 365 に接続する方法](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[PowerShell MsolUser コマンドの詳細情報](/powershell/azure/active-directory/install-adv2)

[パスワード ポリシーの詳細情報](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
