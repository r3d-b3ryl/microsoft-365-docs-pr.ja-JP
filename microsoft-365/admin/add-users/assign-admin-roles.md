---
title: Microsoft 365 管理センターで管理者の役割を割り当てる
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
description: 管理者の役割をユーザーまたは複数のユーザーに割り当てて、管理センターで特定のタスクを実行できるようにする方法について説明します。
ms.openlocfilehash: 59fc2211051aa4f122462186753e7f626715722f
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780639"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="bdccf-103">管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bdccf-103">Assign admin roles</span></span>

<span data-ttu-id="bdccf-104">Microsoft business サブスクリプションを購入したユーザーである場合は、グローバル管理者になります。これは、サブスクリプション内の製品を無制限に制御でき、ほとんどのデータにアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="bdccf-105">詳細については、「[管理者ロールについて](about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdccf-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="bdccf-106">新しいユーザーを追加した場合、管理者の役割を割り当てていないと、それらは*ユーザーの役割*にあり、Microsoft 管理センターのいずれかに対する管理者特権を持ちません。</span><span class="sxs-lookup"><span data-stu-id="bdccf-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="bdccf-107">しかし、操作の実行についてサポートが必要な場合は、管理者の役割をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bdccf-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="bdccf-108">たとえば、パスワードのリセットを支援するユーザーが必要な場合は、グローバル管理者の役割を割り当てないでください。パスワード管理者の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdccf-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="bdccf-109">データおよびオンラインビジネスへのアクセスを無制限にして、グローバル管理者が多すぎて、セキュリティ上のリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="bdccf-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

<span data-ttu-id="bdccf-110">管理者の追加に関する短いビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bdccf-110">Watch a short video about adding an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="bdccf-111">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bdccf-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="assign-admin-roles"></a><span data-ttu-id="bdccf-112">管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bdccf-112">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="bdccf-113">2つの異なる方法でユーザーを役割に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bdccf-113">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="bdccf-114">ユーザーに役割を割り当てるには、[詳細]、[**役割の管理**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-114">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="bdccf-115">または、**役割**に移動して役割を選択し、複数のユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bdccf-115">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="bdccf-116">役割を使用して管理者の役割をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="bdccf-116">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="bdccf-117">管理センターで、[**役割**の役割] に移動し > **Roles**て、組織で使用可能なすべての管理者の役割を表示します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-117">In the admin center, go to **Roles** > **Roles** to view all of the admin roles available for your organization.</span></span>
2. <span data-ttu-id="bdccf-118">ユーザーの割り当て先の管理者の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-118">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="bdccf-119">[**割り当てられた管理者**の追加] を選択し > **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="bdccf-119">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="bdccf-120">ユーザーの**表示名**またはユーザー**名**を入力し、候補の一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-120">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="bdccf-121">完了するまで複数のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-121">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="bdccf-122">[**保存**] を選択すると、割り当てられた管理者の一覧にユーザーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="bdccf-122">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="bdccf-123">アクティブユーザーから管理者ロールにユーザーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bdccf-123">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="bdccf-124">管理センターで、[ユーザーの**Users** > [アクティブなユーザー](https://go.microsoft.com/fwlink/p/?linkid=834822) ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-124">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="bdccf-125">[**アクティブなユーザー** ] ページで、変更する管理者の役割を持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-125">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="bdccf-126">フライアウトウィンドウで、[**役割**] の横にある [**役割の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-126">In the flyout pane, next to **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="bdccf-127">ユーザーに割り当てる管理者の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-127">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="bdccf-128">目的のロールが表示されない場合は、リストの一番下にある [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-128">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bdccf-129">管理センターで、[**ユーザー**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="bdccf-130">[**アクティブなユーザー** ] ページで、変更する管理者の役割を持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-130">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="bdccf-131">フライアウトウィンドウで、[**役割**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-131">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="bdccf-132">[**編集**] オプションが表示されない場合は、編集する権限がなく、他のユーザーに管理者ロールを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="bdccf-132">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="bdccf-133">会社のグローバル管理者に、役割の割り当てを依頼します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-133">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="bdccf-134">小規模な企業では、ビジネスの所有者 (サブスクリプションを購入した人物) はグローバル管理者です。大規模な企業では、IT 部門の主要な担当者はグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="bdccf-134">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="bdccf-135">カスタマイズした役割の一覧を表示するには、[カスタマイズされた**管理者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-135">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="bdccf-136">各役割の説明については、「[管理者の役割につい](about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdccf-136">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bdccf-137">管理センターで、[**ユーザー**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-137">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="bdccf-138">[**アクティブなユーザー** ] ページで、変更する管理者の役割を持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-138">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="bdccf-139">フライアウトウィンドウで、[**役割**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-139">In the flyout pane, next to **Roles**, select **Edit**.</span></span>

    <span data-ttu-id="bdccf-140">[**編集**] オプションが表示されない場合は、編集する権限がなく、他のユーザーに管理者ロールを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="bdccf-140">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="bdccf-141">会社のグローバル管理者に、役割の割り当てを依頼します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-141">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="bdccf-142">小規模な企業では、ビジネスの所有者 (サブスクリプションを購入した人物) はグローバル管理者です。大規模な企業では、IT 部門の主要な担当者はグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="bdccf-142">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="bdccf-143">カスタマイズした役割の一覧を表示するには、[カスタマイズされた**管理者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdccf-143">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="bdccf-144">各役割の説明については、「[管理者の役割につい](about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdccf-144">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end


## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="bdccf-145">複数のユーザーに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bdccf-145">Assign admin roles to multiple users</span></span>

<span data-ttu-id="bdccf-146">PowerShell がわかっている場合は、「PowerShell を使用して[ユーザーアカウントに役割を割り当てる](https://go.microsoft.com/fwlink/?linkid=854257)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdccf-146">If you know PowerShell, see [Assign roles to user accounts with PowerShell](https://go.microsoft.com/fwlink/?linkid=854257).</span></span> <span data-ttu-id="bdccf-147">これは多数のユーザーにロールを割り当てるための最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="bdccf-147">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="bdccf-148">次の手順を使用して、多数のユーザーにロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bdccf-148">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"


## <a name="didnt-work-for-you"></a><span data-ttu-id="bdccf-149">うまくいかない場合</span><span class="sxs-lookup"><span data-stu-id="bdccf-149">Didn't work for you?</span></span>

<span data-ttu-id="bdccf-150">適切なアクセス許可がない場合や、他のユーザーに管理者ロールを割り当てるためのアクセス権がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bdccf-150">You might not have the correct permissions and so you don't have access to assign admin roles to other users.</span></span> <span data-ttu-id="bdccf-151">この場合は、自分にロールを割り当てるように、別の管理者に依頼してください。</span><span class="sxs-lookup"><span data-stu-id="bdccf-151">Ask another admin to assign roles for you.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="bdccf-152">関連記事</span><span class="sxs-lookup"><span data-stu-id="bdccf-152">Related articles</span></span>

[<span data-ttu-id="bdccf-153">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="bdccf-153">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="bdccf-154">PowerShell を使用してユーザーアカウントに役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bdccf-154">Assign roles to user accounts with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[<span data-ttu-id="bdccf-155">パートナー関係を承認または削除する</span><span class="sxs-lookup"><span data-stu-id="bdccf-155">Authorize or remove partner relationships</span></span>](../misc/add-partner.md)

[<span data-ttu-id="bdccf-156">Exchange 管理センターを使用して、別の電子メールアドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="bdccf-156">Add an alternative email address using the Exchange admin center</span></span>](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/email-addresses?view=exchserver-2019#add-an-email-address-to-a-user-mailbox)