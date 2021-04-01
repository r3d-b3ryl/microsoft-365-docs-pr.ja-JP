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
ms.openlocfilehash: 82ec863d5c2ae550fb401e71744715a27c89d382
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470621"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="75846-103">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="75846-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="75846-104">共有メールボックスには通常、ライセンスは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="75846-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="75846-105">共有メールボックスからライセンスを削除するには、次の手順に従って、ユーザーに割り当てるか、不要なライセンスの支払いを行わない方法でライセンスを返します。</span><span class="sxs-lookup"><span data-stu-id="75846-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="75846-106">ライセンスは、次のシナリオで必要です。</span><span class="sxs-lookup"><span data-stu-id="75846-106">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="75846-107">共有メールボックスには、50 GB を超えるストレージが使用されます。</span><span class="sxs-lookup"><span data-stu-id="75846-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="75846-108">共有メールボックスは、インプレイス アーカイブを使用します。</span><span class="sxs-lookup"><span data-stu-id="75846-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="75846-109">共有メールボックスは訴訟ホールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="75846-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="75846-110">共有メールボックスには、Microsoft Defender ライセンスが割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="75846-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="75846-111">ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="75846-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="75846-112">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="75846-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="75846-113">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75846-113">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="75846-114">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="75846-114">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="75846-115">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="75846-115">Select the shared mailbox.</span></span>

3. <span data-ttu-id="75846-116">[ライセンス **とアプリ] タブの 1** つで、[ライセンス] **を展開** し、削除するライセンスのボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="75846-116">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="75846-117">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75846-117">Select **Save changes**.</span></span>

5. <span data-ttu-id="75846-118">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="75846-118">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="75846-119">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="75846-119">You're still paying for the license.</span></span> <span data-ttu-id="75846-120">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="75846-120">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="75846-121">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="75846-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75846-122">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75846-122">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="75846-123">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="75846-123">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="75846-124">共有メールボックスを選択し、[製品ライセンス] の **横にある [編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="75846-124">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="75846-125">[製品 **ライセンス] ページで** 、削除するライセンスのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="75846-125">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="75846-126">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="75846-126">Select **Save**.</span></span>

5. <span data-ttu-id="75846-127">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="75846-127">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="75846-128">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="75846-128">You're still paying for the license.</span></span> <span data-ttu-id="75846-129">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="75846-129">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="75846-130">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="75846-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75846-131">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75846-131">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="75846-132">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="75846-132">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="75846-133">共有メールボックスを選択し、[製品ライセンス] の **横にある [編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="75846-133">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="75846-134">[製品 **ライセンス] ページで** 、削除するライセンスのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="75846-134">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="75846-135">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="75846-135">Select **Save**.</span></span>

5. <span data-ttu-id="75846-136">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="75846-136">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="75846-137">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="75846-137">You're still paying for the license.</span></span> <span data-ttu-id="75846-138">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="75846-138">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="75846-139">関連記事</span><span class="sxs-lookup"><span data-stu-id="75846-139">Related articles</span></span>

[<span data-ttu-id="75846-140">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="75846-140">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="75846-141">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="75846-141">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="75846-142">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="75846-142">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="75846-143">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="75846-143">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="75846-144">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="75846-144">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)