---
title: 管理管理センターに管理者ロールMicrosoft 365割り当てる
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
description: 管理者ロールをビジネスのユーザーまたは複数のユーザーに割り当て、管理センターで特定のタスクを実行できるようにする方法について説明します。
ms.openlocfilehash: f23a30cfd1be53982572d745d476558c3be615e6
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571867"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="74e92-103">管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="74e92-103">Assign admin roles</span></span>

<span data-ttu-id="74e92-104">Microsoft ビジネス サブスクリプションを購入したユーザーは、グローバル管理者です。つまり、サブスクリプション内の製品を無制限に制御でき、ほとんどのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="74e92-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="74e92-105">詳細については、「[管理者の役割について](about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e92-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="74e92-106">新しいユーザーを追加する場合、管理者ロールを割り当てなければ、その *ユーザーはユーザー ロール* に割り当てられており、Microsoft 管理センターに対する管理者特権がありません。</span><span class="sxs-lookup"><span data-stu-id="74e92-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="74e92-107">ただし、作業を完了するために支援が必要な場合は、ユーザーに管理者ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="74e92-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="74e92-108">たとえば、パスワードのリセットを支援する担当者が必要な場合は、グローバル管理者ロールを割り当てるべきではないので、パスワード管理者ロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e92-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="74e92-109">データやオンライン ビジネスに無制限にアクセスできるグローバル管理者が多すぎると、セキュリティ リスクが生じます。</span><span class="sxs-lookup"><span data-stu-id="74e92-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

## <a name="watch-add-an-adminbrbr"></a><span data-ttu-id="74e92-110">ウォッチ: 管理者を追加します。</span><span class="sxs-lookup"><span data-stu-id="74e92-110">Watch: Add an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="74e92-111">このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../../business-video/index.yml)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="74e92-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="74e92-112">管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="74e92-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="74e92-113">ユーザーをロールに割り当てるには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="74e92-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="74e92-114">ユーザーの詳細と **ロールの管理** に移動して、ロールをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="74e92-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="74e92-115">または、[ **ロール]** に移動してロールを選択し、複数のユーザーをロールに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="74e92-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="74e92-116">ロールを使用してユーザーに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="74e92-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="74e92-117">管理センターで、[ **ロール**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="74e92-117">In the admin center, go to **Roles**.</span></span> <span data-ttu-id="74e92-118">Azure **AD** または **Intune** タブを選択して、組織で使用可能な管理者ロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="74e92-118">Choose the **Azure AD** or **Intune** tabs to view the admin roles available for your organization.</span></span>
2. <span data-ttu-id="74e92-119">ユーザーを割り当てる管理者ロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="74e92-120">[ **割り当てられた管理者** > **追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="74e92-121">ユーザーの **表示名** または **ユーザー名** を入力し、候補の一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="74e92-122">完了するまで複数のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="74e92-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="74e92-123">[ **保存 ]** を選択すると、割り当てられた管理者の一覧にユーザーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="74e92-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="74e92-124">アクティブ ユーザーから管理者の役割にユーザーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="74e92-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="74e92-125">管理センターで、[ **ユーザー** > [アクティブユーザー](https://go.microsoft.com/fwlink/p/?linkid=834822) ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="74e92-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="74e92-126">[ **アクティブなユーザー** ] ページで、管理者ロールを変更するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="74e92-127">ポップアップ ウィンドウの [ **ロール]** で、[ **ロールの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-127">In the flyout pane, under **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="74e92-128">ユーザーに割り当てる管理者の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="74e92-129">目的のロールが表示されない場合は、一覧の下部にある **[すべて表示** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="74e92-130">管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="74e92-131">[ **アクティブなユーザー** ] ページで、管理者ロールを変更するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="74e92-132">フライアウト ペインで、[ **ロール**] の横にある [ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="74e92-133">**[編集]** オプションが表示されない場合は、編集権限が与えなくて、他のユーザーに管理者ロールを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="74e92-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="74e92-134">担当の役割を割り当ててもらうには、ビジネスのグローバル管理者に依頼してください。</span><span class="sxs-lookup"><span data-stu-id="74e92-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="74e92-135">小規模ビジネスでは、ビジネスオーナー (サブスクリプションを購入したユーザー) がグローバル管理者です。大企業では、IT 部門の主要な担当者はグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="74e92-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="74e92-136">**カスタマイズした** ロールの一覧を表示するには、[カスタマイズされた管理者] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="74e92-137">各ロールの説明については、「[管理者ロールについて](about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e92-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="74e92-138">管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="74e92-139">[ **アクティブなユーザー** ] ページで、管理者ロールを変更するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="74e92-140">フライアウト ペインで、[ **ロール**] の横にある [ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="74e92-141">**[編集]** オプションが表示されない場合は、編集権限が与えなくて、他のユーザーに管理者ロールを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="74e92-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="74e92-142">担当の役割を割り当ててもらうには、ビジネスのグローバル管理者に依頼してください。</span><span class="sxs-lookup"><span data-stu-id="74e92-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="74e92-143">小規模ビジネスでは、ビジネスオーナー (サブスクリプションを購入したユーザー) がグローバル管理者です。大企業では、IT 部門の主要な担当者はグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="74e92-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="74e92-144">**カスタマイズした** ロールの一覧を表示するには、[カスタマイズされた管理者] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e92-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="74e92-145">各ロールの説明については、「[管理者ロールについて](about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e92-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="74e92-146">複数のユーザーに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="74e92-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="74e92-147">PowerShell がわかっている場合は [、「PowerShell を使用してユーザー アカウントにロールを割り当てる](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e92-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md).</span></span> <span data-ttu-id="74e92-148">これは多数のユーザーにロールを割り当てるための最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="74e92-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="74e92-149">次の手順を使用して、多数のユーザーにロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="74e92-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a><span data-ttu-id="74e92-150">組織の管理者の役割を確認する</span><span class="sxs-lookup"><span data-stu-id="74e92-150">Check admin roles in your organization</span></span>

<span data-ttu-id="74e92-151">管理者ロールを他のユーザーに割り当てる適切な権限がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74e92-151">You might not have the correct permissions to assign admin roles to other users.</span></span> <span data-ttu-id="74e92-152">適切な権限があることを確認するか、別の管理者にロールの割り当てを依頼してください。</span><span class="sxs-lookup"><span data-stu-id="74e92-152">Check to make sure you have the correct permissions or ask another admin to assign roles for you.</span></span>

<span data-ttu-id="74e92-153">管理者の役割のアクセス許可は、次の 2 つの方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="74e92-153">You can check admin role permissions in 2 different ways:</span></span>

- <span data-ttu-id="74e92-154">ユーザーの詳細に移動し、[**アカウント**] ページの **[ロール**] を確認できます。</span><span class="sxs-lookup"><span data-stu-id="74e92-154">You can go to the user's details and look under **Roles** on the **Account** page.</span></span>
- <span data-ttu-id="74e92-155">または、[ **ロール]** に移動して管理者ロールを選択し、割り当てられた管理者を選択して、割り当てられているユーザーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="74e92-155">Or you can go to **Roles** and select the admin role, and select assigned admins to see which users are assigned.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="74e92-156">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="74e92-156">Related content</span></span>

<span data-ttu-id="74e92-157">[管理者ロールMicrosoft 365について](about-admin-roles.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="74e92-157">[About Microsoft 365 admin roles](about-admin-roles.md) (article)</span></span>

<span data-ttu-id="74e92-158">[Azure Active Directoryの管理者ロールのアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)(記事)</span><span class="sxs-lookup"><span data-stu-id="74e92-158">[Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (article)</span></span>

<span data-ttu-id="74e92-159">[PowerShell を使用してユーザー アカウントにロールを割り当てる](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="74e92-159">[Assign roles to user accounts with PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (article)</span></span>

<span data-ttu-id="74e92-160">[パートナー関係の承認または削除](../misc/add-partner.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="74e92-160">[Authorize or remove partner relationships](../misc/add-partner.md) (article)</span></span>