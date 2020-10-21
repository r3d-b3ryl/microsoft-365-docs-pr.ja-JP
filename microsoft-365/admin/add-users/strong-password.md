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
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="d0b48-103">ユーザーに強力なパスワード要件を設定する</span><span class="sxs-lookup"><span data-stu-id="d0b48-103">Set strong password requirement for users</span></span>

<span data-ttu-id="d0b48-104">この記事では、ユーザーの強力なパスワード要件を無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0b48-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="d0b48-105">Microsoft 365 for business 組織では、強力なパスワード要件が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d0b48-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="d0b48-106">組織に強力なパスワードを無効にするための要件がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0b48-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="d0b48-107">強力なパスワード要件を無効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0b48-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="d0b48-108">これらの手順は、PowerShell を使用して完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b48-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d0b48-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="d0b48-109">Before you begin</span></span>

<span data-ttu-id="d0b48-110">この記事は、ビジネス、学校、または非営利団体のパスワードポリシーを管理するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="d0b48-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="d0b48-111">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b48-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="d0b48-112">管理者アカウントとは</span><span class="sxs-lookup"><span data-stu-id="d0b48-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="d0b48-113">これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b48-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="d0b48-114">また、PowerShell を使用して Microsoft 365 に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b48-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="d0b48-115">強力なパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="d0b48-115">Set strong passwords</span></span>

1. <span data-ttu-id="d0b48-116">[PowerShell を使用して Microsoft 365 に接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="d0b48-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="d0b48-117">PowerShell を使用すると、次のコマンドを使用して、すべてのユーザーの強力なパスワード要件を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0b48-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="d0b48-118">UserPrincipalName は、ユーザー名の後にアットマーク記号 (@) とドメイン名が続く、インターネットスタイルのサインイン形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0b48-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="d0b48-119">例: user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="d0b48-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="d0b48-120">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d0b48-120">Related content</span></span>

[<span data-ttu-id="d0b48-121">PowerShell で Microsoft 365 に接続する方法</span><span class="sxs-lookup"><span data-stu-id="d0b48-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="d0b48-122">PowerShell MsolUser コマンドの詳細情報</span><span class="sxs-lookup"><span data-stu-id="d0b48-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="d0b48-123">パスワード ポリシーの詳細情報</span><span class="sxs-lookup"><span data-stu-id="d0b48-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)