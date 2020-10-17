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
ms.openlocfilehash: 1230ff4b4235ac5acbc28aa823506dfa5af26c2d
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48581026"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="c4b78-103">ユーザーに強力なパスワード要件を設定する</span><span class="sxs-lookup"><span data-stu-id="c4b78-103">Set strong password requirement for users</span></span>

<span data-ttu-id="c4b78-104">この記事では、ユーザーに強力なパスワード要件を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4b78-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="c4b78-105">これらの手順は、PowerShell を使用して完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4b78-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c4b78-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="c4b78-106">Before you begin</span></span>

<span data-ttu-id="c4b78-107">この記事は、ビジネス、学校、または非営利団体のパスワードポリシーを管理するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="c4b78-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="c4b78-108">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4b78-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="c4b78-109">[管理者アカウントとは](../admin-overview/admin-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b78-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="c4b78-110">これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4b78-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="c4b78-111">また、PowerShell を使用して Microsoft 365 に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4b78-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="c4b78-112">強力なパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="c4b78-112">Set strong passwords</span></span>

1. <span data-ttu-id="c4b78-113">[PowerShell を使用して Microsoft 365 に接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="c4b78-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="c4b78-114">PowerShell で、次のコマンドを使用して、特定のユーザーに対して強力なパスワードを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4b78-114">Using PowerShell, you can disable strong passwords for specific users with this command:</span></span>

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="c4b78-115">UserPrincipalName は、ユーザー名の後にアットマーク記号 (@) とドメイン名が続く、インターネットスタイルのサインイン形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4b78-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="c4b78-116">例: user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c4b78-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="c4b78-117">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="c4b78-117">Related content</span></span>

[<span data-ttu-id="c4b78-118">PowerShell で Microsoft 365 に接続する方法</span><span class="sxs-lookup"><span data-stu-id="c4b78-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="c4b78-119">PowerShell MsolUser コマンドの詳細情報</span><span class="sxs-lookup"><span data-stu-id="c4b78-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="c4b78-120">パスワード ポリシーの詳細情報</span><span class="sxs-lookup"><span data-stu-id="c4b78-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)