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
ms.openlocfilehash: 873b50b34b9887ada92cc56f7083e3b748a52035
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327224"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="03b6b-103">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="03b6b-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="03b6b-104">共有メールボックスには通常、ライセンスは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="03b6b-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="03b6b-105">共有メールボックスからライセンスを削除するには、次の手順に従って、ユーザーに割り当てるか、不要なライセンスの支払いを行わない方法でライセンスを返します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="03b6b-106">ライセンスは、次のシナリオで必要です。</span><span class="sxs-lookup"><span data-stu-id="03b6b-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="03b6b-107">共有メールボックスには、50 GB を超えるストレージが使用されます。</span><span class="sxs-lookup"><span data-stu-id="03b6b-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="03b6b-108">共有メールボックスは、インプレイス アーカイブを使用します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="03b6b-109">共有メールボックスは訴訟ホールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="03b6b-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="03b6b-110">共有メールボックスには、Microsoft Defender ライセンスが割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="03b6b-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="03b6b-111">ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="03b6b-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="03b6b-112">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="03b6b-113">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03b6b-113">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="03b6b-114">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="03b6b-114">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="03b6b-115">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-115">Select the shared mailbox.</span></span>

3. <span data-ttu-id="03b6b-116">[ライセンス **とアプリ] タブの 1** つで、[ライセンス] **を展開** し、削除するライセンスのボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="03b6b-116">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="03b6b-117">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-117">Select **Save changes**.</span></span>

5. <span data-ttu-id="03b6b-118">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="03b6b-118">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="03b6b-119">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="03b6b-119">You're still paying for the license.</span></span> <span data-ttu-id="03b6b-120">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="03b6b-120">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="03b6b-121">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03b6b-122">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03b6b-122">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="03b6b-123">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="03b6b-123">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="03b6b-124">共有メールボックスを選択し、[製品ライセンス] の **横にある [編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03b6b-124">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="03b6b-125">[製品 **ライセンス] ページで** 、削除するライセンスのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-125">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="03b6b-126">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-126">Select **Save**.</span></span>

5. <span data-ttu-id="03b6b-127">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="03b6b-127">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="03b6b-128">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="03b6b-128">You're still paying for the license.</span></span> <span data-ttu-id="03b6b-129">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="03b6b-129">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="03b6b-130">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03b6b-131">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03b6b-131">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="03b6b-132">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="03b6b-132">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="03b6b-133">共有メールボックスを選択し、[製品ライセンス] の **横にある [編集** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03b6b-133">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="03b6b-134">[製品 **ライセンス] ページで** 、削除するライセンスのトグルを **[オフ** ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-134">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="03b6b-135">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="03b6b-135">Select **Save**.</span></span>

5. <span data-ttu-id="03b6b-136">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="03b6b-136">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="03b6b-137">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="03b6b-137">You're still paying for the license.</span></span> <span data-ttu-id="03b6b-138">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="03b6b-138">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="03b6b-139">関連記事</span><span class="sxs-lookup"><span data-stu-id="03b6b-139">Related articles</span></span>

[<span data-ttu-id="03b6b-140">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="03b6b-140">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="03b6b-141">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="03b6b-141">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="03b6b-142">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="03b6b-142">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="03b6b-143">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="03b6b-143">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="03b6b-144">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="03b6b-144">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)