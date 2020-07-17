---
title: ユーザーにライセンスを割り当てる
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: ユーザーにライセンスを割り当てる方法を説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 648a3433bf5c2bd9bb96abb90335f56ee4fb6bee
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015949"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="346fe-103">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="346fe-104">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="346fe-104">The admin center is changing.</span></span> <span data-ttu-id="346fe-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346fe-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="346fe-106">[**アクティブなユーザー**] ページまたは [**ライセンス**] ページで、ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="346fe-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="346fe-107">使用する方法は、製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="346fe-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="346fe-108">[ユーザーを追加すると同時にライセンスを割り当てる方法を説明します](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="346fe-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="346fe-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="346fe-109">Before you begin</span></span>

- <span data-ttu-id="346fe-110">ライセンスを割り当てるには、グローバル、ライセンス、またはユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="346fe-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="346fe-111">詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346fe-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="346fe-112">[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](https://go.microsoft.com/fwlink/p/?linkid=850410)ことができます。</span><span class="sxs-lookup"><span data-stu-id="346fe-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="346fe-113">グループ ベースのライセンスを使用するには、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346fe-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="346fe-114">Sway などの一部のサービスでは、ユーザーに自動的に割り当てられるため、個別に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="346fe-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="346fe-115">[ライセンス] ページを使用して、ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="346fe-116">[**ライセンス**] ページを使用してライセンスを割り当てる場合、特定の製品のライセンスを最大 20 人のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="346fe-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="346fe-117">[**ライセンス**] ページに、サブスクリプションがあるすべての製品のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="346fe-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="346fe-118">また、各製品のライセンスの総数、割り当てられているライセンスの数、および使用可能なライセンスの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="346fe-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="346fe-119">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="346fe-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="346fe-120">製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-120">Select a product.</span></span>
3. <span data-ttu-id="346fe-121">製品の詳細ページで、[**ライセンスの割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="346fe-122">[**ユーザーにライセンスを割り当てる**] ウィンドウで、名前の入力を開始し、結果から名前を選択して一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="346fe-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="346fe-123">最大 20 人のユーザーを同時に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="346fe-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="346fe-124">特定のアイテムへのアクセス権を割り当てまたは削除するには、[**アプリとサービスをオンまたはオフにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="346fe-125">完了したら、**[割り当て]** を選択し、**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="346fe-126">競合がある場合、メッセージが表示され、問題の内容と修正方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="346fe-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="346fe-127">たとえば、競合するサービスを含むライセンスを選択した場合、各ライセンスに含まれるサービスを確認して再試行するように伝えるエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="346fe-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="346fe-128">ユーザーがアクセスできるアプリとサービスを変更する</span><span class="sxs-lookup"><span data-stu-id="346fe-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="346fe-129">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="346fe-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="346fe-130">[**ライセンス**] ページで、特定のユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="346fe-131">右側のウィンドウで、アクセスを許可または削除するアプリとサービスを選択または選択解除します。</span><span class="sxs-lookup"><span data-stu-id="346fe-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="346fe-132">完了したら、[**保存**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="346fe-133">[アクティブなユーザー] ページでライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="346fe-134">[**アクティブなユーザー**] ページを使用してライセンスを割り当てる場合、ユーザー ライセンスを製品に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="346fe-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="346fe-135">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="346fe-136">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="346fe-137">ライセンスを割り当てるユーザー名の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="346fe-138">上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="346fe-139">[**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てに追加する**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="346fe-140">[**既存の製品に追加**] ウィンドウで、選択したユーザーに付与するライセンスのトグルを [**オン**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="346fe-141">既定では、それらのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="346fe-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="346fe-142">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="346fe-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="346fe-143">ユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="346fe-144">ウィンドウの下部で、[**追加**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="346fe-145">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="346fe-146">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="346fe-147">ライセンスを割り当てるユーザー名の横のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="346fe-148">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="346fe-149">[**製品の割り当て**] ウィンドウで、[**既存の製品ライセンス割り当てに追加する**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="346fe-150">選択したユーザーに付与するライセンスのトグルを [**オン**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="346fe-151">既定では、それらのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="346fe-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="346fe-152">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="346fe-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="346fe-153">ユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="346fe-154">[**既存の製品を追加する**] ウィンドウの下部で、[**追加**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="346fe-155">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="346fe-156">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="346fe-157">ライセンスを割り当てるユーザー名の横のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="346fe-158">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="346fe-159">[**製品の割り当て**] ウィンドウで、[**既存の製品ライセンス割り当てに追加する**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="346fe-160">選択したユーザーに付与するライセンスのトグルを [**オン**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="346fe-161">既定では、それらのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="346fe-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="346fe-162">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="346fe-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="346fe-163">ユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="346fe-164">[**既存の製品を追加する**] ウィンドウの下部で、[**追加**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="346fe-165">1 人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="346fe-166">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="346fe-167">ライセンスを割り当てるユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="346fe-168">右側のウィンドウで、[**ライセンスとアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="346fe-169">[**ライセンス**] セクションを展開し、割り当てるライセンスのボックスを選択して、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="346fe-170">1 人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="346fe-171">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="346fe-172">ライセンスを割り当てるユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="346fe-173">右側のウィンドウの [**製品ライセンス**] 行で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="346fe-174">[ **製品のライセンス**] ウィンドウで、このユーザーに割り当てるライセンスを [ **オン**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="346fe-175">既定では、そのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="346fe-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="346fe-176">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="346fe-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="346fe-177">そのユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="346fe-178">[**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="346fe-179">1 人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="346fe-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="346fe-180">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="346fe-181">ライセンスを割り当てるユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="346fe-182">右側のウィンドウの [**製品ライセンス**] 行で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="346fe-183">[ **製品のライセンス**] ウィンドウで、このユーザーに割り当てるライセンスを [ **オン**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="346fe-184">既定では、そのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="346fe-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="346fe-185">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="346fe-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="346fe-186">そのユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="346fe-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="346fe-187">[**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="346fe-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="346fe-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="346fe-188">Next steps</span></span>

<span data-ttu-id="346fe-189">ユーザーがまだ Office アプリをインストールしていない場合は、「[従業員クイック スタート ガイド](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)」をユーザーと共有して、ユーザーが「[PC または Mac に Microsoft 365 または Office 2019 をダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="346fe-189">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="346fe-190">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="346fe-190">Related content</span></span>

<span data-ttu-id="346fe-191">[サブスクリプションとライセンスを理解する](../../commerce/licenses/subscriptions-and-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="346fe-191">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="346fe-192">[ユーザーからライセンスの割り当てを解除する](remove-licenses-from-users.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="346fe-192">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="346fe-193">[スクリプションのライセンスを購入または削除する](../../commerce/licenses/buy-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="346fe-193">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>