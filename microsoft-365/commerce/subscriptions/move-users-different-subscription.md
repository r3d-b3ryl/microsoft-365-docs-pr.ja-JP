---
title: ユーザーを別のサブスクリプションに移動する
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
description: サブスクリプション間でユーザーを移動する方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: d110ee7c49befa34f5a2cd3bb44dc114aec25b62
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016550"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="205d2-103">ユーザーを別のサブスクリプションに移動する</span><span class="sxs-lookup"><span data-stu-id="205d2-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="205d2-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="205d2-104">The admin center is changing.</span></span> <span data-ttu-id="205d2-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="205d2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="205d2-106">複数のサブスクリプションを持っている場合、ユーザーに1つのサブスクリプションのライセンスを付与し、別のサブスクリプションに移動するには、既存のライセンスを別のサブスクリプションに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="205d2-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="205d2-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="205d2-107">Before you begin</span></span>

<span data-ttu-id="205d2-108">ライセンスを割り当てるには、グローバル、ライセンス、またはユーザーの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="205d2-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="205d2-109">詳細については、「[Microsoft 365 の管理者の役割](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="205d2-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="205d2-110">ユーザーを別のサブスクリプションに移動する</span><span class="sxs-lookup"><span data-stu-id="205d2-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="205d2-111">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="205d2-112">既存のライセンスを置換するユーザーの名前の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="205d2-113">上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="205d2-114">[**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="205d2-115">これらのユーザーに割り当てるライセンスを **[オンに**する位置に切り替える。</span><span class="sxs-lookup"><span data-stu-id="205d2-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="205d2-116">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="205d2-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="205d2-117">それらのユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="205d2-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="205d2-118">選択したユーザーで以前に割り当てられたライセンスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="205d2-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="205d2-119">[**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="205d2-120">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="205d2-121">既存のライセンスを置き換えるユーザー名の横のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="205d2-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="205d2-122">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="205d2-123">[**製品の割り当て**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="205d2-124">これらのユーザーに割り当てるライセンスを **[オンに**する位置に切り替える。</span><span class="sxs-lookup"><span data-stu-id="205d2-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="205d2-125">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="205d2-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="205d2-126">そのユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="205d2-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="205d2-127">選択したユーザーで以前に割り当てられたライセンスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="205d2-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="205d2-128">[**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="205d2-129">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="205d2-130">既存のライセンスを置き換えるユーザー名の横のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="205d2-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="205d2-131">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="205d2-132">[**製品の割り当て**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="205d2-133">これらのユーザーに割り当てるライセンスを **[オンに**する位置に切り替える。</span><span class="sxs-lookup"><span data-stu-id="205d2-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="205d2-134">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="205d2-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="205d2-135">そのユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="205d2-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="205d2-136">選択したユーザーで以前に割り当てられたライセンスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="205d2-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="205d2-137">[**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="205d2-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="205d2-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="205d2-138">Next steps</span></span>

<span data-ttu-id="205d2-139">使用されていない[ライセンスを他のユーザーに再割り当て](../../managed-desktop/get-started/assign-licenses.md)する予定がない場合は、[サブスクリプションからライセンスを削除](../../commerce/licenses/buy-licenses.md)して、必要なライセンス数を超えるライセンスを支払っていないことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="205d2-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="205d2-140">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="205d2-140">Related content</span></span>

<span data-ttu-id="205d2-141">[ユーザーへのライセンスの割り当て](../../admin/manage/assign-licenses-to-users.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="205d2-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="205d2-142">[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="205d2-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="205d2-143">[プランを手動で変更](change-plans-manually.md)する (記事) </span><span class="sxs-lookup"><span data-stu-id="205d2-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="205d2-144">[Microsoft 365 for business のサブスクリプションとライセンスについて理解する](../licenses/subscriptions-and-licenses.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="205d2-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="205d2-145">[別の Microsoft 365 for business サブスクリプションを購入する](../buy-another-subscription.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="205d2-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>