---
title: ユーザーからライセンスの割り当てを解除する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: ユーザーアカウントからライセンスの割り当てを解除する方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015937"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="793bf-103">ユーザーからライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="793bf-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="793bf-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="793bf-104">The admin center is changing.</span></span> <span data-ttu-id="793bf-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="793bf-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="793bf-106">[**アクティブなユーザー** ] ページまたは [**ライセンス**] ページで、ユーザーからライセンスを割り当てを解除できます。</span><span class="sxs-lookup"><span data-stu-id="793bf-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="793bf-107">使用する方法は、特定のユーザーからの製品ライセンスの割り当てを解除するか、特定の製品からユーザーライセンスの割り当てを解除するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="793bf-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="793bf-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="793bf-108">Before you begin</span></span>

- <span data-ttu-id="793bf-109">ライセンスの割り当てを解除するには、グローバルなライセンス、ユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="793bf-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="793bf-110">詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="793bf-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="793bf-111">[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)ことができます。</span><span class="sxs-lookup"><span data-stu-id="793bf-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span></span>
- <span data-ttu-id="793bf-112">ライセンスを割り当てられた[ユーザーアカウントを削除](../add-users/delete-a-user.md)して、他のユーザーがライセンスを使用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="793bf-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="793bf-113">ユーザーアカウントを削除すると、そのライセンスはすぐに他のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="793bf-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="793bf-114">ライセンスの割り当てを解除するには、[ライセンス] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="793bf-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="793bf-115">[**ライセンス**] ページを使用してライセンスを割り当てを解除する場合は、最大20人のユーザーの特定の製品のライセンスの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="793bf-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="793bf-116">管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="793bf-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="793bf-117">ライセンスの割り当てを解除する製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="793bf-118">ライセンスの割り当てを解除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="793bf-119">[**ライセンスの割り当て解除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="793bf-120">[**ライセンスの割り当て解除**] ボックスで、[**割り当て**の解除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="793bf-121">ライセンスの割り当てを解除するには、[アクティブなユーザー] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="793bf-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="793bf-122">[**アクティブなユーザー** ] ページを使用してライセンスを割り当てを解除する場合は、ユーザーから製品ライセンスの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="793bf-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="793bf-123">1人のユーザーのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="793bf-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="793bf-124">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="793bf-125">ライセンスの割り当てを解除するユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="793bf-126">右側のウィンドウで、[**ライセンスとアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="793bf-127">[**ライセンス**] セクションを展開し、割り当てを解除するライセンスのボックスをオフにして、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="793bf-128">1人のユーザーのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="793bf-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="793bf-129">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="793bf-130">ライセンスの割り当てを解除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="793bf-131">右側の [**製品ライセンス**] 行で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="793bf-132">[**製品ライセンス**] ウィンドウで、ユーザーの割り当てを解除するライセンスを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="793bf-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="793bf-133">たとえば、Office 365 Enterprise E3 ライセンスをオフにした場合、そのライセンスとそのユーザーのライセンスの下にあるすべてのサービスは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="793bf-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="793bf-134">[**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="793bf-135">1人のユーザーのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="793bf-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="793bf-136">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="793bf-137">ライセンスの割り当てを解除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="793bf-138">右側の [**製品ライセンス**] 行で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="793bf-139">[**製品ライセンス**] ウィンドウで、ユーザーの割り当てを解除するライセンスを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="793bf-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="793bf-140">たとえば、Office 365 Enterprise E3 ライセンスをオフにした場合、そのライセンスとそのユーザーのライセンスの下にあるすべてのサービスは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="793bf-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="793bf-141">[**製品ライセンス**] ウィンドウの下部で、 [**保存**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="793bf-142">複数のユーザーからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="793bf-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="793bf-143">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="793bf-144">ライセンスの割り当てを解除するユーザーの名前の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="793bf-145">上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="793bf-146">[**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="793bf-147">[既存の製品を**置き換える**] ウィンドウの下部で、[選択した**ユーザーからすべての製品ライセンスを削除**する] チェックボックスをオンにし、[閉じるの**置換**] を選択し \> **Close**ます。</span><span class="sxs-lookup"><span data-stu-id="793bf-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="793bf-148">複数のユーザーからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="793bf-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="793bf-149">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="793bf-150">すべてのライセンスの割り当てを解除するユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="793bf-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="793bf-151">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="793bf-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="793bf-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="793bf-153">[**既存製品の置換**] ウィンドウの下部で、[**選択したユーザーからすべての製品ライセンスを削除**する] チェックボックスをオンにし、[**置換**閉じる] を選択し \> **Close** \> **Close**ます。</span><span class="sxs-lookup"><span data-stu-id="793bf-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="793bf-154">複数のユーザーからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="793bf-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="793bf-155">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="793bf-156">すべてのライセンスの割り当てを解除するユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="793bf-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="793bf-157">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="793bf-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="793bf-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="793bf-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="793bf-159">[**既存製品の置換**] ウィンドウの下部で、[**選択したユーザーからすべての製品ライセンスを削除**する] チェックボックスをオンにし、[**置換**閉じる] を選択し \> **Close** \> **Close**ます。</span><span class="sxs-lookup"><span data-stu-id="793bf-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="793bf-160">ライセンスを削除すると、ユーザーのデータはどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="793bf-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="793bf-161">ライセンスがユーザーから削除されると、そのアカウントに関連付けられているデータは30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="793bf-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="793bf-162">30日の猶予期間が過ぎると、データは削除され、回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="793bf-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="793bf-163">OneDrive for Business に保存されたファイルは、ユーザーが Microsoft 365 管理センターから削除されているか、Active Directory 同期によって削除されている場合を除き、削除されません。</span><span class="sxs-lookup"><span data-stu-id="793bf-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="793bf-164">詳細については、「 [OneDrive の保持と削除](https://docs.microsoft.com/onedrive/retention-and-deletion)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="793bf-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="793bf-165">ライセンスが削除されると、そのユーザーのメールボックスは、コンテンツ検索や高度な電子情報開示などの電子情報開示ツールを使用して検索できなくなります。</span><span class="sxs-lookup"><span data-stu-id="793bf-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="793bf-166">詳細については、「 [Microsoft 365 のコンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)」の「切断されたメールボックスまたはライセンスの解除済みメールボックスの検索」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="793bf-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="793bf-167">Office 365 Enterprise E3 などのエンタープライズサブスクリプションを使用している場合、Exchange Online では、[非アクティブなメールボックス](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)を使用して、削除されたユーザーアカウントのメールボックスデータを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="793bf-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="793bf-168">詳細については、「 [Exchange Online の非アクティブなメールボックスの作成と管理](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="793bf-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="793bf-169">ライセンスが削除された後に、ユーザーの Microsoft 365 データへのアクセスをブロックする方法、および後でデータにアクセスする方法については、「元[の従業員を削除](../add-users/remove-former-employee.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="793bf-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="793bf-170">ユーザーのライセンスを削除しても、まだ Office アプリがインストールされている場合は、office アプリを使用したときに Office のライセンスのない[製品とライセンス認証のエラー](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="793bf-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="793bf-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="793bf-171">Next steps</span></span>

<span data-ttu-id="793bf-172">使用されていない[ライセンスを他のユーザーに再割り当て](../../managed-desktop/get-started/assign-licenses.md)する予定がない場合は、[サブスクリプションからライセンスを削除](../../commerce/licenses/buy-licenses.md)して、必要なライセンス数を超えるライセンスを支払っていないことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="793bf-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="793bf-173">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="793bf-173">Related content</span></span>

<span data-ttu-id="793bf-174">[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="793bf-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="793bf-175">[ユーザーへのライセンスの割り当て](assign-licenses-to-users.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="793bf-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="793bf-176">[Microsoft 365 for business のサブスクリプションとライセンスについて理解する](../../commerce/licenses/subscriptions-and-licenses.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="793bf-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>