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
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626145"
---
# <a name="set-strong-password-requirement-for-users"></a>ユーザーに強力なパスワード要件を設定する

この記事では、ユーザーに強力なパスワード要件を設定する方法について説明します。 これらの手順は、PowerShell を使用して完了する必要があります。

## <a name="before-you-begin"></a>開始する前に

この記事は、ビジネス、学校、または非営利団体のパスワードポリシーを管理するユーザーを対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは](../admin-overview/admin-overview.md)。 これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。

また、PowerShell を使用して Microsoft 365 に接続する必要があります。

## <a name="set-strong-passwords"></a>強力なパスワードを設定する

1. [PowerShell を使用して Microsoft 365 に接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。

2. PowerShell を使用すると、次のコマンドを使用して、すべてのユーザーに対して強力なパスワード要件を有効にすることができます。

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> UserPrincipalName は、ユーザー名の後にアットマーク記号 (@) とドメイン名が続く、インターネットスタイルのサインイン形式にする必要があります。 例: user@contoso.com。

## <a name="related-content"></a>関連コンテンツ

[PowerShell で Microsoft 365 に接続する方法](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[PowerShell MsolUser コマンドの詳細情報](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[パスワード ポリシーの詳細情報](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)