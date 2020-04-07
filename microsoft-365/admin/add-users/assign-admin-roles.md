---
title: Microsoft 365 管理センターで管理者の役割を割り当てる
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: get-started-article
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 管理者の役割をユーザーまたは複数のユーザーに割り当てて、管理センターで特定のタスクを実行できるようにする方法について説明します。
ms.openlocfilehash: 9c10ef7d6dade3d826c9c291e58b3e8e2a58f2a6
ms.sourcegitcommit: 311bbd6f168225ede166d29696126a1e003eee0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2020
ms.locfileid: "43151379"
---
# <a name="assign-admin-roles"></a><span data-ttu-id="ec910-103">管理者の役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="ec910-103">Assign admin roles</span></span>

<span data-ttu-id="ec910-104">Microsoft business サブスクリプションを購入したユーザーである場合は、グローバル管理者になります。これは、サブスクリプション内の製品を無制限に制御でき、ほとんどのデータにアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ec910-104">If you're the person who purchased your Microsoft business subscription, you are the global admin. This means you have unlimited control over the products in your subscriptions and you can access most data.</span></span>

<span data-ttu-id="ec910-105">詳細については、「[管理者の役割につい](about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec910-105">For more information, see [About admin roles](about-admin-roles.md).</span></span>

<span data-ttu-id="ec910-106">新しいユーザーを追加した場合、管理者の役割を割り当てていないと、それらは*ユーザーの役割*にあり、Microsoft 管理センターのいずれかに対する管理者特権を持ちません。</span><span class="sxs-lookup"><span data-stu-id="ec910-106">When you add new users, if you don't assign them an admin role then they are in the *user role* and don't have admin privileges to any of the Microsoft admin centers.</span></span> <span data-ttu-id="ec910-107">しかし、操作の実行についてサポートが必要な場合は、管理者の役割をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ec910-107">But if you need help getting things done, you can assign an admin role to a user.</span></span> <span data-ttu-id="ec910-108">たとえば、パスワードのリセットを支援するユーザーが必要な場合は、グローバル管理者の役割を割り当てないでください。パスワード管理者の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec910-108">For example, if you need someone to help reset passwords, you shouldn't assign them the global admin role, you should assign them the password admin role.</span></span> <span data-ttu-id="ec910-109">データおよびオンラインビジネスへのアクセスを無制限にして、グローバル管理者が多すぎて、セキュリティ上のリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="ec910-109">Having too many global admins, with unlimited access to your data and online business, is a security risk.</span></span>

<span data-ttu-id="ec910-110">管理者の追加に関する短いビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec910-110">Watch a short video about adding an admin.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

<span data-ttu-id="ec910-111">このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec910-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ec910-112">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec910-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

## <a name="assign-admin-roles"></a><span data-ttu-id="ec910-113">管理者の役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="ec910-113">Assign admin roles</span></span> 

::: moniker range="o365-worldwide"

<span data-ttu-id="ec910-114">2つの異なる方法でユーザーを役割に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ec910-114">You can assign users to a role in 2 different ways:</span></span>

- <span data-ttu-id="ec910-115">ユーザーに役割を割り当てるには、[詳細]、[**役割の管理**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ec910-115">You can go to the user's details and **Manage roles** to assign a role to the user.</span></span>
- <span data-ttu-id="ec910-116">または、**役割**に移動して役割を選択し、複数のユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec910-116">Or you can go to **Roles** and select the role, and then add multiple users to it.</span></span>

### <a name="assign-admin-roles-to-users-using-roles"></a><span data-ttu-id="ec910-117">役割を使用して管理者の役割をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="ec910-117">Assign admin roles to users using Roles</span></span>

1. <span data-ttu-id="ec910-118">管理センターで、[**役割** >の**役割**] に移動して、組織で使用可能なすべての管理者の役割を表示します。</span><span class="sxs-lookup"><span data-stu-id="ec910-118">In the admin center, go to **Roles** > **Roles** to view all of the admin roles available for your organization.</span></span>
2. <span data-ttu-id="ec910-119">ユーザーの割り当て先の管理者の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-119">Select the admin role that you want to assign the user to.</span></span>
3. <span data-ttu-id="ec910-120">[**割り当てられた管理者** >の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-120">Select **Assigned admins** > **Add**.</span></span>
4. <span data-ttu-id="ec910-121">ユーザーの**表示名**またはユーザー**名**を入力し、候補の一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-121">Type the user's **display name** or **username**, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="ec910-122">完了するまで複数のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ec910-122">Add multiple users until you're done.</span></span>
6. <span data-ttu-id="ec910-123">[**保存**] を選択すると、割り当てられた管理者の一覧にユーザーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ec910-123">Select **Save**, and then the user will be added to the list of assigned admins.</span></span>

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a><span data-ttu-id="ec910-124">アクティブユーザーから管理者ロールにユーザーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ec910-124">Assign a user to an admin role from Active users</span></span>

1. <span data-ttu-id="ec910-125">管理センターで、[**ユーザー** >の[アクティブなユーザー](https://go.microsoft.com/fwlink/p/?linkid=834822) ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ec910-125">In the admin center, go to **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

2. <span data-ttu-id="ec910-126">[**アクティブなユーザー** ] ページで、変更する管理者の役割を持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-126">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="ec910-127">フライアウトウィンドウで、[**役割**] の横にある [**役割の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-127">In the flyout pane, next to **Roles**, select **Manage roles**.</span></span>

3. <span data-ttu-id="ec910-128">ユーザーに割り当てる管理者の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-128">Select the admin role that you want to assign to the user.</span></span> <span data-ttu-id="ec910-129">目的のロールが表示されない場合は、リストの一番下にある [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-129">If you don't see the role you're looking for, select **Show all** at the bottom of the list.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ec910-130">管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ec910-130">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ec910-131">[**アクティブなユーザー** ] ページで、変更する管理者の役割を持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-131">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="ec910-132">フライアウトウィンドウで、[**役割**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-132">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="ec910-133">[**編集**] オプションが表示されない場合は、編集する権限がなく、他のユーザーに管理者ロールを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="ec910-133">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="ec910-134">会社のグローバル管理者に、役割の割り当てを依頼します。</span><span class="sxs-lookup"><span data-stu-id="ec910-134">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="ec910-135">小規模な企業では、ビジネスの所有者 (サブスクリプションを購入した人物) はグローバル管理者です。大規模な企業では、IT 部門の主要な担当者はグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="ec910-135">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="ec910-136">カスタマイズした役割の一覧を表示するには、[カスタマイズされた**管理者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-136">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="ec910-137">各役割の説明については、「[管理者の役割につい](about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec910-137">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ec910-138">管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ec910-138">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ec910-139">[**アクティブなユーザー** ] ページで、変更する管理者の役割を持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-139">On the **Active users** page, select the user whose admin role you want to change.</span></span> <span data-ttu-id="ec910-140">フライアウトウィンドウで、[**役割**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-140">In the flyout pane, next to **Roles**, select **Edit**.</span></span> 

    <span data-ttu-id="ec910-141">[**編集**] オプションが表示されない場合は、編集する権限がなく、他のユーザーに管理者ロールを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="ec910-141">If you don't see the **Edit** option, then you don't have a permission to edit and can't assign admin roles to other people.</span></span> <span data-ttu-id="ec910-142">会社のグローバル管理者に、役割の割り当てを依頼します。</span><span class="sxs-lookup"><span data-stu-id="ec910-142">Ask a global admin in your business to assign roles for you.</span></span> <span data-ttu-id="ec910-143">小規模な企業では、ビジネスの所有者 (サブスクリプションを購入した人物) はグローバル管理者です。大規模な企業では、IT 部門の主要な担当者はグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="ec910-143">In a small business, the business owner (the person who purchased your subscription) is a global admin. In a large business, key people in the IT department are global admins.</span></span>

3. <span data-ttu-id="ec910-144">カスタマイズした役割の一覧を表示するには、[カスタマイズされた**管理者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec910-144">Select **Customized administrator** to see a list of roles we've customized for you.</span></span> <span data-ttu-id="ec910-145">各役割の説明については、「[管理者の役割につい](about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec910-145">For a description of each role, see [About admin roles.](about-admin-roles.md)</span></span>

::: moniker-end


## <a name="assign-admin-roles-to-multiple-users"></a><span data-ttu-id="ec910-146">複数のユーザーに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ec910-146">Assign admin roles to multiple users</span></span>

<span data-ttu-id="ec910-147">PowerShell がわかっている場合は、「PowerShell を使用して[ユーザーアカウントに役割を割り当てる](https://go.microsoft.com/fwlink/?linkid=854257)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec910-147">If you know PowerShell, see [Assign roles to user accounts with PowerShell](https://go.microsoft.com/fwlink/?linkid=854257).</span></span> <span data-ttu-id="ec910-148">これは多数のユーザーにロールを割り当てるための最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="ec910-148">It's ideal for assigning roles to hundreds of users.</span></span>
  
<span data-ttu-id="ec910-149">次の手順を使用して、多数のユーザーにロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ec910-149">Use the following instructions to assign roles to tens of users.</span></span>

::: moniker range="o365-worldwide"


## <a name="didnt-work-for-you"></a><span data-ttu-id="ec910-150">うまくいかない場合</span><span class="sxs-lookup"><span data-stu-id="ec910-150">Didn't work for you?</span></span>

<span data-ttu-id="ec910-151">適切なアクセス許可がない場合や、他のユーザーに管理者ロールを割り当てるためのアクセス権がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec910-151">You might not have the correct permissions and so you don't have access to assign admin roles to other users.</span></span> <span data-ttu-id="ec910-152">この場合は、自分にロールを割り当てるように、別の管理者に依頼してください。</span><span class="sxs-lookup"><span data-stu-id="ec910-152">Ask another admin to assign roles for you.</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="ec910-153">関連記事</span><span class="sxs-lookup"><span data-stu-id="ec910-153">Related articles</span></span>

[<span data-ttu-id="ec910-154">PowerShell を使用してユーザーアカウントに役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="ec910-154">Assign roles to user accounts with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[<span data-ttu-id="ec910-155">パートナー関係を承認または削除する</span><span class="sxs-lookup"><span data-stu-id="ec910-155">Authorize or remove partner relationships</span></span>](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)

[<span data-ttu-id="ec910-156">Exchange 管理センターを使用して、別の電子メールアドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="ec910-156">Add an alternative email address using the Exchange admin center</span></span>](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/email-addresses?view=exchserver-2019#add-an-email-address-to-a-user-mailbox)

