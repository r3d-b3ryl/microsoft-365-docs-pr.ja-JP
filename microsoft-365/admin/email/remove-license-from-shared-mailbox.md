---
title: 共有メールボックスからライセンスを削除する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: '共有メールボックスからライセンスを削除して、別のユーザーに割り当てます。 '
ms.openlocfilehash: fb09036fc28ea3d9c182395d0a85e467f611dfdc
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140431"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="e4098-103">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="e4098-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e4098-104">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="e4098-104">The admin center is changing.</span></span> <span data-ttu-id="e4098-105">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4098-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e4098-106">メールボックスが 50 GB を超えるデータを保持していない限り、共有メールボックスにはライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e4098-106">Shared mailboxes don't need a license unless the mailbox has over 50GB of data.</span></span> <span data-ttu-id="e4098-107">共有メールボックスからライセンスを削除するには、次の手順に従って、ユーザーにライセンスを割り当てたり、不要なライセンスに対して支払いが行われないようにライセンスを戻したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4098-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>
  
## <a name="remove-the-license"></a><span data-ttu-id="e4098-108">ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="e4098-108">Remove the license</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e4098-109">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4098-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e4098-110">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-110">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e4098-111">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4098-111">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="e4098-112">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4098-112">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="e4098-113">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-113">Select the shared mailbox.</span></span>

3. <span data-ttu-id="e4098-114">[**ライセンスとアプリ**] タブで、[**ライセンス**] を展開し、削除するライセンスのボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e4098-114">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="e4098-115">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-115">Select **Save changes**.</span></span>

5. <span data-ttu-id="e4098-116">[**アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は**ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="e4098-116">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="e4098-117">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="e4098-117">You're still paying for the license.</span></span> <span data-ttu-id="e4098-118">その支払いを停止するには、[サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4098-118">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="e4098-119">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e4098-120">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4098-120">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="e4098-121">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4098-121">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="e4098-122">共有メールボックスを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-122">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="e4098-123">[**製品ライセンス**] ページで、削除するライセンスのトグルを [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="e4098-123">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="e4098-124">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-124">Select **Save**.</span></span>

5. <span data-ttu-id="e4098-125">[**アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は**ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="e4098-125">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="e4098-126">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="e4098-126">You're still paying for the license.</span></span> <span data-ttu-id="e4098-127">その支払いを停止するには、[サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4098-127">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="e4098-128">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e4098-129">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4098-129">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="e4098-130">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4098-130">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="e4098-131">共有メールボックスを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-131">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="e4098-132">[**製品ライセンス**] ページで、削除するライセンスのトグルを [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="e4098-132">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="e4098-133">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4098-133">Select **Save**.</span></span>

5. <span data-ttu-id="e4098-134">[**アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は**ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="e4098-134">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="e4098-135">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="e4098-135">You're still paying for the license.</span></span> <span data-ttu-id="e4098-136">その支払いを停止するには、[サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4098-136">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="e4098-137">関連記事</span><span class="sxs-lookup"><span data-stu-id="e4098-137">Related articles</span></span>

[<span data-ttu-id="e4098-138">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="e4098-138">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="e4098-139">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="e4098-139">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="e4098-140">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="e4098-140">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="e4098-141">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="e4098-141">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="e4098-142">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="e4098-142">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
