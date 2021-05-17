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
description: ユーザーに強力なパスワード要件を設定する方法については、Windows PowerShell。
ms.openlocfilehash: de2f47bb88fe4cb3d00e45698fe006035faa4e5c
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222075"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="0d897-103">ユーザーの強力なパスワード要件をオフにする</span><span class="sxs-lookup"><span data-stu-id="0d897-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="0d897-104">この記事では、ユーザーの強力なパスワード要件をオフにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d897-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="0d897-105">強力なパスワード要件は、ビジネス組織向けMicrosoft 365既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0d897-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="0d897-106">組織には、強力なパスワードを無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d897-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="0d897-107">強力なパスワード要件をオフにするには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0d897-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="0d897-108">PowerShell を使用してこれらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d897-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0d897-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="0d897-109">Before you begin</span></span>

<span data-ttu-id="0d897-110">この記事は、ビジネス、学校、または非営利団体のパスワード ポリシーを管理するユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="0d897-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="0d897-111">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d897-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="0d897-112">管理者アカウントとは</span><span class="sxs-lookup"><span data-stu-id="0d897-112">What's an admin account?</span></span>](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="0d897-113">これらの手順を実行するには [、グローバル管理者またはパスワード](about-admin-roles.md) 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d897-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="0d897-114">PowerShell を使用して、Microsoft 365接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d897-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="0d897-115">強力なパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="0d897-115">Set strong passwords</span></span>

1. <span data-ttu-id="0d897-116">[Connect PowerShell をMicrosoft 365する方法を説明します](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0d897-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="0d897-117">PowerShell を使用すると、次のコマンドを使用して、すべてのユーザーの強力なパスワード要件をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="0d897-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="0d897-118">userPrincipalName は、ユーザー名の後にアット 記号 (@) とドメイン名が続くインターネット スタイルのサインイン形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d897-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="0d897-119">たとえば、次の user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="0d897-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="0d897-120">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="0d897-120">Related content</span></span>

[<span data-ttu-id="0d897-121">PowerShell で Microsoft 365 に接続する方法</span><span class="sxs-lookup"><span data-stu-id="0d897-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="0d897-122">PowerShell MsolUser コマンドの詳細情報</span><span class="sxs-lookup"><span data-stu-id="0d897-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="0d897-123">パスワード ポリシーの詳細情報</span><span class="sxs-lookup"><span data-stu-id="0d897-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)