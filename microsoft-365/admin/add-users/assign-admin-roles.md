---
title: 管理者の役割を管理センター Microsoft 365割り当てる
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
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 管理センターで特定のタスクを実行できるよう、管理者の役割をビジネス内のユーザーまたは複数のユーザーに割り当てる方法について説明します。
ms.openlocfilehash: c723053d8d1a39bf0f996840bc418ffe299db089
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023991"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="c6d4f-103">管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6d4f-103">Assign admin roles</span></span>

<span data-ttu-id="c6d4f-104">Microsoft Business サブスクリプションを購入したユーザーは、グローバル管理者です。つまり、サブスクリプション内の製品を無制限に制御し、ほとんどのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="c6d4f-105">詳細については、「[管理者の役割について](about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="c6d4f-106">新しいユーザーを追加する場合、管理者ロールを割り当てない場合は、ユーザーロールに含め、Microsoft 管理センターに管理者特権はありません。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="c6d4f-107">ただし、ヘルプが必要な場合は、管理者の役割をユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="c6d4f-108">たとえば、パスワードのリセットを支援する必要がある場合は、グローバル管理者の役割を割り当ててはいけない場合は、パスワード管理者の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="c6d4f-109">データやオンライン ビジネスに無制限にアクセスできるグローバル管理者が多すぎると、セキュリティ リスクが生じます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="c6d4f-110">ウォッチ: 管理者を追加します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="c6d4f-111">このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../../business-video/index.yml)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="c6d4f-112">管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6d4f-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="c6d4f-113">ユーザーを役割に割り当てるには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="c6d4f-114">ユーザーの詳細と役割の管理に移動して **、ユーザー** に役割を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="c6d4f-115">または、[ロール] **に移動** して役割を選択し、そのロールに複数のユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="c6d4f-116">ロールを使用して管理者ロールをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6d4f-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="c6d4f-117">管理センターで、[ロール] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="c6d4f-118">組織で **使用できるAD** を表示するには、[Azure の管理者] タブまたは **[Intune]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="c6d4f-119">ユーザーを割り当てる管理者の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="c6d4f-120">[割 **り当てられた管理者の追加]** > **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="c6d4f-121">ユーザーの表示 **名またはユーザー** 名を **入力** し、候補の一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="c6d4f-122">完了するまで、複数のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="c6d4f-123">[ **保存]** を選択すると、割り当てられた管理者の一覧にユーザーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="c6d4f-124">アクティブ ユーザーから管理者の役割にユーザーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6d4f-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="c6d4f-125">管理センターで、[ユーザーのアクティブな **ユーザー]** > [ページに移動](https://go.microsoft.com/fwlink/p/?linkid=834822) します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="c6d4f-126">[アクティブ **なユーザー] ページ** で、管理者ロールを変更するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="c6d4f-127">[フライアウト] ウィンドウの [役割] **で、[役割** の管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-127">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="c6d4f-128">ユーザーに割り当てる管理者の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="c6d4f-129">探している役割が表示できない場合は、リストの下部にある [すべて表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c6d4f-130">管理センターで、[**ユーザー**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="c6d4f-131">[アクティブ **なユーザー] ページ** で、管理者ロールを変更するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="c6d4f-132">フライアウト ウィンドウの [ロール] の横にある **[編集**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="c6d4f-133">[編集] オプションが表示されない場合は、編集権限を持たなかったり、管理者の役割を他のユーザーに割り当てなかったりします。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="c6d4f-134">ビジネスのグローバル管理者にロールの割り当てをお願いします。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="c6d4f-135">小規模企業では、ビジネス所有者 (サブスクリプションを購入したユーザー) がグローバル管理者です。大企業では、IT 部門の主要なユーザーはグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="c6d4f-136">[ **カスタマイズされた管理者]** を選択して、カスタマイズした役割の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="c6d4f-137">各役割の説明については、「管理者ロール [について」を参照してください。](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c6d4f-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c6d4f-138">管理センターで、[**ユーザー**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="c6d4f-139">[アクティブ **なユーザー] ページ** で、管理者ロールを変更するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="c6d4f-140">フライアウト ウィンドウの [ロール] の横にある **[編集**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="c6d4f-141">[編集] オプションが表示されない場合は、編集権限を持たなかったり、管理者の役割を他のユーザーに割り当てなかったりします。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="c6d4f-142">ビジネスのグローバル管理者にロールの割り当てをお願いします。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="c6d4f-143">小規模企業では、ビジネス所有者 (サブスクリプションを購入したユーザー) がグローバル管理者です。大企業では、IT 部門の主要なユーザーはグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="c6d4f-144">[ **カスタマイズされた管理者]** を選択して、カスタマイズした役割の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="c6d4f-145">各役割の説明については、「管理者ロール [について」を参照してください。](about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c6d4f-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="c6d4f-146">複数のユーザーに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6d4f-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="c6d4f-147">PowerShell を知っている場合は [、「PowerShell を使用して役割をユーザー アカウントに割り当てる」を参照してください](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="c6d4f-148">これは多数のユーザーにロールを割り当てるための最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="c6d4f-149">次の手順を使用して、多数のユーザーにロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="c6d4f-150">組織内の管理者の役割を確認する</span><span class="sxs-lookup"><span data-stu-id="c6d4f-150">Check admin roles in your organization</span></span>

<span data-ttu-id="c6d4f-151">管理者の役割を他のユーザーに割り当てる適切なアクセス許可が付与されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-151">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="c6d4f-152">正しいアクセス許可を持っているか、別の管理者にロールを割り当てさせるか確認します。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-152">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="c6d4f-153">管理者ロールのアクセス許可は、次の 2 つの方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-153">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="c6d4f-154">ユーザーの詳細に移動し、[アカウント] ページの [ **役割** ] で **確認** できます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-154">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="c6d4f-155">または、[役割] **に移動** して管理役割を選択し、割り当てられた管理者を選択して、割り当てられているユーザーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6d4f-155">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="c6d4f-156">関連記事</span><span class="sxs-lookup"><span data-stu-id="c6d4f-156">Related articles</span></span>

[<span data-ttu-id="c6d4f-157">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="c6d4f-157">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="c6d4f-158">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c6d4f-158">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[<span data-ttu-id="c6d4f-159">PowerShell を使用して役割をユーザー アカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6d4f-159">Assign roles to user accounts with PowerShell</span></span>](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)

[<span data-ttu-id="c6d4f-160">パートナー関係の承認または削除</span><span class="sxs-lookup"><span data-stu-id="c6d4f-160">Authorize or remove partner relationships</span></span>](../misc/add-partner.md)