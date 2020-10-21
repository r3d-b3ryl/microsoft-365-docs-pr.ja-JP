---
title: ユーザーに強力なパスワード要件を設定する
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
description: Windows PowerShell を使用して、ユーザーに強力なパスワード要件を設定する方法について説明します。
ms.openlocfilehash: 9f6fd61396d99245ffeabf757d3cb65c5d5cb85e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646621"
---
# <a name="set-strong-password-requirement-for-users"></a>ユーザーに強力なパスワード要件を設定する

この記事では、ユーザーの強力なパスワード要件を無効にする方法について説明します。 Microsoft 365 for business 組織では、強力なパスワード要件が既定で有効になっています。 組織に強力なパスワードを無効にするための要件がある場合があります。 強力なパスワード要件を無効にするには、次の手順を実行します。 これらの手順は、PowerShell を使用して完了する必要があります。

## <a name="before-you-begin"></a>開始する前に

この記事は、ビジネス、学校、または非営利団体のパスワードポリシーを管理するユーザーを対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは](../admin-overview/admin-overview.md) これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。

また、PowerShell を使用して Microsoft 365 に接続する必要があります。

## <a name="set-strong-passwords"></a>強力なパスワードを設定する

1. [PowerShell を使用して Microsoft 365 に接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。

2. PowerShell を使用すると、次のコマンドを使用して、すべてのユーザーの強力なパスワード要件を無効にすることができます。

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName は、ユーザー名の後にアットマーク記号 (@) とドメイン名が続く、インターネットスタイルのサインイン形式にする必要があります。 例: user@contoso.com。

## <a name="related-content"></a>関連コンテンツ

[PowerShell で Microsoft 365 に接続する方法](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[PowerShell MsolUser コマンドの詳細情報](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[パスワード ポリシーの詳細情報](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)