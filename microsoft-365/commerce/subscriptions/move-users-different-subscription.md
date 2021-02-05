---
title: ユーザーを別のサブスクリプションに移動する
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
description: サブスクリプション間でユーザーを移動する方法について学習します。
ms.date: 07/01/2020
ms.openlocfilehash: ec9385d10cc1799509c6f1d2fa88059eecf3bd8c
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114671"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="36035-103">ユーザーを別のサブスクリプションに移動する</span><span class="sxs-lookup"><span data-stu-id="36035-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="36035-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="36035-104">The admin center is changing.</span></span> <span data-ttu-id="36035-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36035-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="36035-106">複数のサブスクリプションがある場合、1 つのサブスクリプションのライセンスを持つユーザーを別のサブスクリプションに移動する場合は、既存のライセンスを別のサブスクリプションに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="36035-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="36035-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="36035-107">Before you begin</span></span>

<span data-ttu-id="36035-108">ライセンスを割り当てるには、グローバル、ライセンス、またはユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="36035-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="36035-109">詳細については、「[Microsoft 365 の管理者の役割](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36035-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="36035-110">ユーザーを別のサブスクリプションに移動する</span><span class="sxs-lookup"><span data-stu-id="36035-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="36035-111">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="36035-112">既存のライセンスを置き換えるユーザーの名前の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="36035-113">上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="36035-114">[**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="36035-115">これらのユーザーに割り **当てる** ライセンスのトグルをオンの位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="36035-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="36035-116">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="36035-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="36035-117">それらのユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="36035-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="36035-118">選択したユーザーで以前に割り当てられたライセンスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="36035-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="36035-119">[**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="36035-120">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="36035-121">既存のライセンスを置き換えるユーザー名の横のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="36035-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="36035-122">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="36035-123">[**製品の割り当て**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="36035-124">これらのユーザーに割り **当てる** ライセンスのトグルをオンの位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="36035-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="36035-125">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="36035-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="36035-126">そのユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="36035-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="36035-127">選択したユーザーで以前に割り当てられたライセンスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="36035-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="36035-128">[**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="36035-129">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="36035-130">既存のライセンスを置き換えるユーザー名の横のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="36035-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="36035-131">[**一括処理**] ウィンドウで、[**製品ライセンスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="36035-132">[**製品の割り当て**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="36035-133">これらのユーザーに割り **当てる** ライセンスのトグルをオンの位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="36035-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.</span></span>\
    <span data-ttu-id="36035-134">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="36035-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="36035-135">そのユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="36035-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="36035-136">選択したユーザーで以前に割り当てられたライセンスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="36035-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="36035-137">[**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36035-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="36035-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="36035-138">Next steps</span></span>

<span data-ttu-id="36035-139">未使用のライセンスを他のユーザー[](../../managed-desktop/get-started/assign-licenses.md)に再割り当てしない場合は、[](../../commerce/licenses/buy-licenses.md)サブスクリプションからライセンスを削除して、必要以上のライセンスの支払いを行わないか検討してください。</span><span class="sxs-lookup"><span data-stu-id="36035-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="36035-140">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="36035-140">Related content</span></span>

<span data-ttu-id="36035-141">[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="36035-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="36035-142">[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="36035-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="36035-143">[手動でプランを変更](change-plans-manually.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="36035-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="36035-144">[一ビジネス向け Microsoft 365 のサブスクリプションとライセンス](../licenses/subscriptions-and-licenses.md) について (記事)</span><span class="sxs-lookup"><span data-stu-id="36035-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="36035-145">[別の Microsoft 365 for Business サブスクリプションを購入する](../buy-another-subscription.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="36035-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>