---
title: 共有メールボックスからライセンスを削除する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: '共有メールボックスからライセンスを削除して、別のユーザーに割り当てる。 '
ms.openlocfilehash: 1acd549936212db7f722355ed1f2518ff6bbac18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915688"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="3c862-103">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="3c862-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3c862-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="3c862-104">The admin center is changing.</span></span> <span data-ttu-id="3c862-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c862-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="3c862-106">共有メールボックスには通常、ライセンスは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="3c862-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="3c862-107">共有メールボックスからライセンスを削除するには、次の手順に従って、ユーザーに割り当てるか、不要なライセンスの支払いを行わない方法でライセンスを返します。</span><span class="sxs-lookup"><span data-stu-id="3c862-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="3c862-108">ライセンスは、次のシナリオで必要です。</span><span class="sxs-lookup"><span data-stu-id="3c862-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="3c862-109">共有メールボックスには、50 GB を超えるストレージが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c862-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="3c862-110">共有メールボックスは、インプレイス アーカイブを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c862-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="3c862-111">共有メールボックスは訴訟ホールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="3c862-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="3c862-112">共有メールボックスには、Microsoft Defender ライセンスが割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="3c862-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="3c862-113">ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="3c862-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3c862-114">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3c862-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3c862-115">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c862-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3c862-116">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c862-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="3c862-117">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3c862-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="3c862-118">[ライセンス **とアプリ] タブの 1** つで、[ライセンス] **を展開** し、削除するライセンスのボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3c862-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="3c862-119">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c862-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="3c862-120">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="3c862-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3c862-121">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="3c862-121">You're still paying for the license.</span></span> <span data-ttu-id="3c862-122">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="3c862-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="3c862-123">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3c862-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3c862-124">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c862-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3c862-125">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c862-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="3c862-126">共有メールボックスを選択し、[製品ライセンス] の **横にある [編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3c862-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="3c862-127">[製品 **ライセンス] ページで** 、削除するライセンスのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="3c862-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="3c862-128">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c862-128">Select **Save**.</span></span>

5. <span data-ttu-id="3c862-129">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="3c862-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3c862-130">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="3c862-130">You're still paying for the license.</span></span> <span data-ttu-id="3c862-131">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="3c862-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="3c862-132">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3c862-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3c862-133">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c862-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="3c862-134">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c862-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="3c862-135">共有メールボックスを選択し、[製品ライセンス] の **横にある [編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3c862-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="3c862-136">[製品 **ライセンス] ページで** 、削除するライセンスのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="3c862-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="3c862-137">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c862-137">Select **Save**.</span></span>

5. <span data-ttu-id="3c862-138">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="3c862-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="3c862-139">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="3c862-139">You're still paying for the license.</span></span> <span data-ttu-id="3c862-140">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="3c862-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="3c862-141">関連記事</span><span class="sxs-lookup"><span data-stu-id="3c862-141">Related articles</span></span>

[<span data-ttu-id="3c862-142">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="3c862-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="3c862-143">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="3c862-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="3c862-144">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="3c862-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="3c862-145">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="3c862-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="3c862-146">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="3c862-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)