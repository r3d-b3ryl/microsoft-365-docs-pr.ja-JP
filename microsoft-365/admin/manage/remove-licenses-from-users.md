---
title: ユーザーからライセンスの割り当てを解除する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: ユーザー アカウントからライセンスの割り当てを解除する方法について学習します。
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114479"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="4b398-103">ユーザーからライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4b398-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="4b398-104">The admin center is changing.</span></span> <span data-ttu-id="4b398-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b398-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="4b398-106">ライセンスは、[アクティブなユーザー] ページまたは[ライセンス] ページでユーザーから割り当 **てを解除** できます。</span><span class="sxs-lookup"><span data-stu-id="4b398-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="4b398-107">使用する方法は、特定のユーザーからの製品ライセンスの割り当てを解除するか、特定の製品のライセンスの割り当てを解除するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4b398-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="4b398-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="4b398-108">Before you begin</span></span>

- <span data-ttu-id="4b398-109">ライセンスの割り当てを解除するには、グローバル、ライセンス、ユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b398-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="4b398-110">詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b398-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="4b398-111">[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell)ことができます。</span><span class="sxs-lookup"><span data-stu-id="4b398-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).</span></span>
- <span data-ttu-id="4b398-112">ライセンスが割 [り当てられた](../add-users/delete-a-user.md) ユーザー アカウントを削除して、ライセンスを他のユーザーが利用できるようすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4b398-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="4b398-113">ユーザー アカウントを削除すると、そのユーザーのライセンスがすぐに他のユーザーに割り当て可能になります。</span><span class="sxs-lookup"><span data-stu-id="4b398-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="4b398-114">[ライセンス] ページを使用してライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="4b398-115">[ライセンス] ページ **を使用** してライセンスの割り当てを解除すると、最大 20 人のユーザーの特定の製品のライセンスの割り当てを解除できます。</span><span class="sxs-lookup"><span data-stu-id="4b398-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="4b398-116">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4b398-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="4b398-117">ライセンスの割り当てを解除する製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="4b398-118">ライセンスの割り当てを解除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="4b398-119">[ライセンス **の割り当て解除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b398-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="4b398-120">[ライセンス **の割り当て解除] ボックスで** 、[割り当て **解除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b398-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="4b398-121">[アクティブなユーザー] ページを使用してライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="4b398-122">[アクティブなユーザー] **ページを使用** してライセンスの割り当てを解除すると、ユーザーから製品ライセンスの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="4b398-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="4b398-123">1 人のユーザーからライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="4b398-124">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4b398-125">ライセンスの割り当てを解除するユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="4b398-126">右側のウィンドウで、[**ライセンスとアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="4b398-127">[ライセンス **] セクションを** 展開し、割り当てを解除するライセンスのボックスをオフにして、[変更の保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b398-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="4b398-128">1 人のユーザーからライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="4b398-129">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4b398-130">ライセンスの割り当てを解除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="4b398-131">右側の [製品ライセンス] 行 **で** 、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4b398-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="4b398-132">[製品 **ライセンス] ウィンドウ** で、ユーザーの割り当てを解除するライセンスのトグルを [オフ] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="4b398-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="4b398-133">たとえば、Office 365 Enterprise E3 ライセンスをオフにした場合、そのユーザーのライセンスと、そのライセンスのすべてのサービスが割り当て解除されます。</span><span class="sxs-lookup"><span data-stu-id="4b398-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="4b398-134">[**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="4b398-135">1 人のユーザーからライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="4b398-136">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4b398-137">ライセンスの割り当てを解除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="4b398-138">右側の [製品ライセンス] 行 **で** 、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4b398-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="4b398-139">[製品 **ライセンス] ウィンドウ** で、ユーザーの割り当てを解除するライセンスのトグルを [オフ] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="4b398-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="4b398-140">たとえば、Office 365 Enterprise E3 ライセンスをオフにした場合、そのユーザーのライセンスと、そのライセンスのすべてのサービスが割り当て解除されます。</span><span class="sxs-lookup"><span data-stu-id="4b398-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="4b398-141">[**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="4b398-142">複数のユーザーからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="4b398-143">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4b398-144">ライセンスの割り当てを解除するユーザーの名前の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="4b398-145">上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="4b398-146">[**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="4b398-147">[既存の製品の置換 **]** ウィンドウの下部で、[選択したユーザーからすべての製品ライセンスを削除する] チェック ボックスをオンにし、[閉じる] を **選択** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="4b398-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="4b398-148">複数のユーザーからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="4b398-149">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4b398-150">すべてのライセンスの割り当てを解除するユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="4b398-151">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="4b398-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="4b398-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="4b398-153">[既存の製品の置換 **]** ウィンドウの下部で、[選択したユーザーからすべての製品ライセンスを削除する] チェックボックスをオンにして、[閉じる置換] を \> **選択** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="4b398-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="4b398-154">複数のユーザーからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="4b398-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="4b398-155">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4b398-156">すべてのライセンスの割り当てを解除するユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="4b398-157">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b398-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="4b398-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="4b398-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="4b398-159">[既存の製品の置換 **]** ウィンドウの下部で、[選択したユーザーからすべての製品ライセンスを削除する] チェックボックスをオンにして、[閉じる置換] を \> **選択** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="4b398-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="4b398-160">ライセンスを削除すると、ユーザーのデータは何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="4b398-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="4b398-161">ユーザーからライセンスが削除されると、そのアカウントに関連付けられているデータは 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="4b398-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="4b398-162">30 日間の猶予期間の後、データは削除され、回復できません。</span><span class="sxs-lookup"><span data-stu-id="4b398-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="4b398-163">ユーザーが Microsoft 365 管理センターから削除されたか、Active Directory 同期によって削除されない限り、OneDrive for Business に保存されたファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="4b398-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="4b398-164">詳細については [、「OneDrive の保持と削除」を参照してください](https://docs.microsoft.com/onedrive/retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="4b398-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="4b398-165">ライセンスが削除されると、ユーザーのメールボックスは、コンテンツ検索や Advanced eDiscovery などの電子情報開示ツールを使用して検索できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4b398-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="4b398-166">詳細については [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)のコンテンツ検索の「切断されたメールボックスまたはライセンス解除されたメールボックスの検索」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b398-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="4b398-167">Office 365 Enterprise E3 のような Enterprise サブスクリプションがある場合、Exchange Online では、非アクティブなメールボックスを使用して、削除されたユーザー アカウントのメールボックス データを [保持できます](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="4b398-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="4b398-168">詳細については、「Exchange Online で非アクティブ [なメールボックスを作成および管理する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="4b398-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="4b398-169">ライセンスが削除された後にユーザーの Microsoft 365 データへのアクセスをブロックする方法、および後でデータにアクセスする方法については、「元従業員を削除する」を参照 [してください](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="4b398-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="4b398-170">ユーザーのライセンスを削除し、引き続き Office アプリがインストールされている場合、ユーザーが Office アプリを使用すると、ライセンスのない製品とライセンス認証のエラーが [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b398-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b398-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="4b398-171">Next steps</span></span>

<span data-ttu-id="4b398-172">未使用のライセンスを他のユーザー[](../../managed-desktop/get-started/assign-licenses.md)に再割り当てしない場合は、[](../../commerce/licenses/buy-licenses.md)サブスクリプションからライセンスを削除して、必要以上のライセンスの支払いを行わないか検討してください。</span><span class="sxs-lookup"><span data-stu-id="4b398-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="4b398-173">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4b398-173">Related content</span></span>

<span data-ttu-id="4b398-174">[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4b398-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="4b398-175">[ユーザーにライセンスを割り当てる](assign-licenses-to-users.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="4b398-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="4b398-176">[一ビジネス向け Microsoft 365 のサブスクリプションとライセンス](../../commerce/licenses/subscriptions-and-licenses.md) について (記事)</span><span class="sxs-lookup"><span data-stu-id="4b398-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>