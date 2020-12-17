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
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698305"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="263e6-103">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="263e6-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="263e6-104">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="263e6-104">The admin center is changing.</span></span> <span data-ttu-id="263e6-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="263e6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="263e6-106">共有メールボックスは、通常、ライセンスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="263e6-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="263e6-107">ユーザーにライセンスを割り当てるか、ライセンスを返して不要なライセンスの支払いを行わないでいく場合は、次の手順に従って共有メールボックスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="263e6-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="263e6-108">次のシナリオでは、ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="263e6-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="263e6-109">共有メールボックスには 50 GB を超える記憶域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="263e6-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="263e6-110">共有メールボックスは、イン Place Archiving を使用します。</span><span class="sxs-lookup"><span data-stu-id="263e6-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="263e6-111">共有メールボックスは訴訟ホールドの対象です。</span><span class="sxs-lookup"><span data-stu-id="263e6-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="263e6-112">共有メールボックスには、Microsoft Defender ライセンスが割り当てされています。</span><span class="sxs-lookup"><span data-stu-id="263e6-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="263e6-113">ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="263e6-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="263e6-114">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="263e6-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="263e6-115">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="263e6-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="263e6-116">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="263e6-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="263e6-117">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="263e6-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="263e6-118">[ライセンス **とアプリ] タブで** 、[ **ライセンス** ] を展開し、削除するライセンスのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="263e6-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="263e6-119">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="263e6-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="263e6-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span><span class="sxs-lookup"><span data-stu-id="263e6-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="263e6-121">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="263e6-121">You're still paying for the license.</span></span> <span data-ttu-id="263e6-122">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="263e6-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="263e6-123">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="263e6-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="263e6-124">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="263e6-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="263e6-125">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="263e6-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="263e6-126">共有メールボックスを選択し、[製品ライセンス] の横にある **[編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="263e6-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="263e6-127">[製品 **ライセンス] ページで**、削除するライセンスのトグルを [オフ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="263e6-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="263e6-128">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="263e6-128">Select **Save**.</span></span>

5. <span data-ttu-id="263e6-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span><span class="sxs-lookup"><span data-stu-id="263e6-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="263e6-130">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="263e6-130">You're still paying for the license.</span></span> <span data-ttu-id="263e6-131">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="263e6-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="263e6-132">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="263e6-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="263e6-133">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="263e6-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="263e6-134">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="263e6-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="263e6-135">共有メールボックスを選択し、[製品ライセンス] の横にある **[編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="263e6-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="263e6-136">[製品 **ライセンス] ページで**、削除するライセンスのトグルを [オフ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="263e6-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="263e6-137">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="263e6-137">Select **Save**.</span></span>

5. <span data-ttu-id="263e6-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span><span class="sxs-lookup"><span data-stu-id="263e6-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="263e6-139">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="263e6-139">You're still paying for the license.</span></span> <span data-ttu-id="263e6-140">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="263e6-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="263e6-141">関連記事</span><span class="sxs-lookup"><span data-stu-id="263e6-141">Related articles</span></span>

[<span data-ttu-id="263e6-142">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="263e6-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="263e6-143">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="263e6-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="263e6-144">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="263e6-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="263e6-145">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="263e6-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="263e6-146">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="263e6-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
