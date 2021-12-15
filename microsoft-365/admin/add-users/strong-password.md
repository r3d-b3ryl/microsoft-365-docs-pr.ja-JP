---
title: ユーザーの強力なパスワード要件をオフにする
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
description: ユーザーに強力なパスワード要件を設定する方法については、Windows PowerShell。
ms.openlocfilehash: 5932f01c2f17a72f4f6a20a6457d263bed7dd85e
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61530489"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>ユーザーの強力なパスワード要件をオフにする

この記事では、ユーザーの強力なパスワード要件をオフにする方法について説明します。 強力なパスワード要件は、ビジネス組織向けMicrosoft 365既定で有効になっています。 組織には、強力なパスワードを無効にする必要がある場合があります。 強力なパスワード要件をオフにするには、以下の手順に従います。 PowerShell を使用してこれらの手順を実行する必要があります。

## <a name="before-you-begin"></a>始める前に

この記事は、ビジネス、学校、または非営利団体のパスワード ポリシーを管理するユーザー向けです。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは?([Microsoft 365 管理センター]の概要。/admin-overview/admin-center-overview.md) これらの手順を実行するには、グローバル管理者または[パスワード](about-admin-roles.md)管理者である必要があります。

PowerShell を使用して、Microsoft 365接続する必要があります。

## <a name="set-strong-passwords"></a>強力なパスワードを設定する

1. [Connect PowerShell をMicrosoft 365する方法を説明します](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

2. PowerShell を使用すると、次のコマンドを使用して、すべてのユーザーの強力なパスワード要件をオフにできます。

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn **OFF** strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> userPrincipalName は、ユーザー名の後にアット 記号 (@) とドメイン名が続くインターネット スタイルのサインイン形式である必要があります。 たとえば、次の user@contoso.com。

## <a name="related-content"></a>関連コンテンツ

[PowerShell で Microsoft 365 に接続する方法](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[PowerShell MsolUser コマンドの詳細情報](/powershell/azure/active-directory/install-adv2)

[パスワード ポリシーの詳細情報](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
