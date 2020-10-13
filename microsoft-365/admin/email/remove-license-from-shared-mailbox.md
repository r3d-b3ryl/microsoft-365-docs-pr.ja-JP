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
description: '共有メールボックスからライセンスを削除して、別のユーザーに割り当てます。 '
ms.openlocfilehash: 43d32744afe42a8f244160ace20c1d989f501b28
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445497"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="de3ed-103">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="de3ed-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="de3ed-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="de3ed-104">The admin center is changing.</span></span> <span data-ttu-id="de3ed-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de3ed-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="de3ed-106">通常、共有メールボックスにはライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="de3ed-107">共有メールボックスからライセンスを削除するには、次の手順に従って、ユーザーにライセンスを割り当てたり、不要なライセンスに対して支払いが行われないようにライセンスを戻したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="de3ed-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="de3ed-108">次のシナリオでは、ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="de3ed-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="de3ed-109">共有メールボックスに、50 GB を超える記憶域が使用されています。</span><span class="sxs-lookup"><span data-stu-id="de3ed-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="de3ed-110">共有メールボックスは、インプレースアーカイブを使用します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="de3ed-111">共有メールボックスは、訴訟ホールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="de3ed-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="de3ed-112">ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="de3ed-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="de3ed-113">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="de3ed-114">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de3ed-114">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="de3ed-115">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-115">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="de3ed-116">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-116">Select the shared mailbox.</span></span>

3. <span data-ttu-id="de3ed-117">[ **ライセンスとアプリ** ] タブで、[ **ライセンス** ] を展開し、削除するライセンスのボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="de3ed-117">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="de3ed-118">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-118">Select **Save changes**.</span></span>

5. <span data-ttu-id="de3ed-119">[ **アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は **ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-119">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="de3ed-120">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-120">You're still paying for the license.</span></span> <span data-ttu-id="de3ed-121">その支払いを停止するには、 [サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-121">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="de3ed-122">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="de3ed-123">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de3ed-123">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="de3ed-124">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-124">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="de3ed-125">共有メールボックスを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-125">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="de3ed-126">[ **製品ライセンス** ] ページで、削除するライセンスのトグルを [ **オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-126">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="de3ed-127">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-127">Select **Save**.</span></span>

5. <span data-ttu-id="de3ed-128">[ **アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は **ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-128">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="de3ed-129">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-129">You're still paying for the license.</span></span> <span data-ttu-id="de3ed-130">その支払いを停止するには、 [サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-130">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="de3ed-131">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="de3ed-132">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de3ed-132">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="de3ed-133">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-133">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="de3ed-134">共有メールボックスを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-134">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="de3ed-135">[ **製品ライセンス** ] ページで、削除するライセンスのトグルを [ **オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-135">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="de3ed-136">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-136">Select **Save**.</span></span>

5. <span data-ttu-id="de3ed-137">[ **アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は **ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-137">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="de3ed-138">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="de3ed-138">You're still paying for the license.</span></span> <span data-ttu-id="de3ed-139">その支払いを停止するには、 [サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="de3ed-139">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="de3ed-140">関連記事</span><span class="sxs-lookup"><span data-stu-id="de3ed-140">Related articles</span></span>

[<span data-ttu-id="de3ed-141">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="de3ed-141">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="de3ed-142">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="de3ed-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="de3ed-143">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="de3ed-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="de3ed-144">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="de3ed-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="de3ed-145">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="de3ed-145">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
