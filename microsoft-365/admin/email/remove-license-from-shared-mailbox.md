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
ms.openlocfilehash: 9ba411c614fee93e37ac45e58fd40bf246a9c2ab
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327244"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="40c52-103">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="40c52-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="40c52-104">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="40c52-104">The admin center is changing.</span></span> <span data-ttu-id="40c52-105">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c52-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="40c52-106">通常、共有メールボックスにはライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="40c52-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="40c52-107">共有メールボックスからライセンスを削除するには、次の手順に従って、ユーザーにライセンスを割り当てたり、不要なライセンスに対して支払いが行われないようにライセンスを戻したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="40c52-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="40c52-108">次のシナリオでは、ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="40c52-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="40c52-109">共有メールボックスに、50 GB を超える記憶域が使用されています。</span><span class="sxs-lookup"><span data-stu-id="40c52-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="40c52-110">共有メールボックスは、インプレースアーカイブを使用します。</span><span class="sxs-lookup"><span data-stu-id="40c52-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="40c52-111">共有メールボックスは、訴訟ホールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="40c52-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="40c52-112">ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="40c52-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="40c52-113">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="40c52-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="40c52-114">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="40c52-115">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c52-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="40c52-116">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="40c52-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="40c52-117">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="40c52-118">[**ライセンスとアプリ**] タブで、[**ライセンス**] を展開し、削除するライセンスのボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="40c52-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="40c52-119">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="40c52-120">[**アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は**ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="40c52-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="40c52-121">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="40c52-121">You're still paying for the license.</span></span> <span data-ttu-id="40c52-122">その支払いを停止するには、[サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="40c52-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="40c52-123">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="40c52-124">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c52-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="40c52-125">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="40c52-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="40c52-126">共有メールボックスを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="40c52-127">[**製品ライセンス**] ページで、削除するライセンスのトグルを [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="40c52-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="40c52-128">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-128">Select **Save**.</span></span>

5. <span data-ttu-id="40c52-129">[**アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は**ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="40c52-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="40c52-130">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="40c52-130">You're still paying for the license.</span></span> <span data-ttu-id="40c52-131">その支払いを停止するには、[サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="40c52-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="40c52-132">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="40c52-133">[アクティブなユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c52-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="40c52-134">ライセンスはユーザー設定なので、共有メールボックスページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="40c52-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="40c52-135">共有メールボックスを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="40c52-136">[**製品ライセンス**] ページで、削除するライセンスのトグルを [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="40c52-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="40c52-137">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="40c52-137">Select **Save**.</span></span>

5. <span data-ttu-id="40c52-138">[**アクティブなユーザー** ] ページに戻ると、共有メールボックスの状態は**ライセンス**されません。</span><span class="sxs-lookup"><span data-stu-id="40c52-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="40c52-139">ライセンスの支払いはまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="40c52-139">You're still paying for the license.</span></span> <span data-ttu-id="40c52-140">その支払いを停止するには、[サブスクリプションからライセンスを削除](../../commerce/licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="40c52-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="40c52-141">関連記事</span><span class="sxs-lookup"><span data-stu-id="40c52-141">Related articles</span></span>

[<span data-ttu-id="40c52-142">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="40c52-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="40c52-143">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="40c52-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="40c52-144">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="40c52-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="40c52-145">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="40c52-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="40c52-146">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="40c52-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
