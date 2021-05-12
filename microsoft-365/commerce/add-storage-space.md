---
title: サブスクリプションに容量を追加する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: Microsoft 365 サブスクリプションのファイル ストレージを追加および削減する方法について説明します。 追加のファイル ストレージを使用すると、SharePoint Online と OneDrive にさらに多くのコンテンツを格納できます。
ms.date: 04/02/2021
ms.openlocfilehash: 98fdb4412f263bd9e0a22b6890ff66509cb3e799
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332188"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="e8f90-104">サブスクリプションに容量を追加する</span><span class="sxs-lookup"><span data-stu-id="e8f90-104">Add storage space for your subscription</span></span>

<span data-ttu-id="e8f90-105">SharePoint Online サイト コレクションの容量が不足し始めた場合、ご使用のプランが対象に含まれている場合は、サブスクリプションに容量を追加できます。</span><span class="sxs-lookup"><span data-stu-id="e8f90-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="e8f90-106">使用可能なアドオンの一覧に Office **365 Extra File Storage** が表示されない場合は、プランが対象外となります。</span><span class="sxs-lookup"><span data-stu-id="e8f90-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="e8f90-107">詳細については、「自分のプラン [が適格か」を参照してください。](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="e8f90-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="e8f90-108">ボリューム ライセンスまたは CSP を使用してサブスクリプションを購入した場合、Microsoft から直接組織Office **365 Extra File Storage** を購入することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8f90-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="e8f90-109">サポートが必要な場合は、担当者またはパートナーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e8f90-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e8f90-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="e8f90-110">Before you begin</span></span>

<span data-ttu-id="e8f90-111">この記事のタスクを実行するには、グローバル管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f90-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="e8f90-112">詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f90-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="e8f90-113">使用可能なストレージの表示</span><span class="sxs-lookup"><span data-stu-id="e8f90-113">View available storage</span></span>

1. <span data-ttu-id="e8f90-114">SharePoint 管理センターで、[アクティブ な<a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a>サイト] ページに移動し、組織の管理者権限を持つ[アカウントでサインイン](/sharepoint/sharepoint-admin-role)します。</span><span class="sxs-lookup"><span data-stu-id="e8f90-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="e8f90-115">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8f90-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="e8f90-116">組織が 365 で複数地域を構成しているOfficeバーには、すべての地域の場所で使用される記憶域の量も表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8f90-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![[アクティブなサイト] ページの記憶域バー](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="e8f90-118">記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。</span><span class="sxs-lookup"><span data-stu-id="e8f90-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="e8f90-119">使用している記憶域の量を決定した後、サブスクリプションの記憶域を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="e8f90-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="e8f90-120">記憶域の追加に必要なコストを確認するには、この記事の手順に従い、購入前に価格情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8f90-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="e8f90-121">サイト コレクションの記憶域制限の設定の詳細については [、「Manage site collection storage limits」を参照してください](/sharepoint/manage-site-collection-storage-limits)。</span><span class="sxs-lookup"><span data-stu-id="e8f90-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="e8f90-122">サブスクリプションにストレージを追加する</span><span class="sxs-lookup"><span data-stu-id="e8f90-122">Add storage to your subscription</span></span>

<span data-ttu-id="e8f90-123">サブスクリプション用の追加ストレージをまだ購入していない場合は、そのストレージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8f90-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="e8f90-124">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e8f90-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="e8f90-125">[サービスの購入]ページの下部にある[アドオン] セクションで **、[365** Officeストレージ] を見つけて、[詳細] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="e8f90-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="e8f90-126">[製品の詳細] ページで、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8f90-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="e8f90-127">必要に応じて、基本サブスクリプションを選択し、追加するストレージのギガバイト数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e8f90-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="e8f90-128">[今 **すぐチェックアウト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8f90-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="e8f90-129">[この **外観の確認方法]** ページで、選択したストレージのギガバイト数を確認し、価格情報を確認し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="e8f90-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="e8f90-130">[注文 **の完了] ページ** で、合計を確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f90-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="e8f90-131">変更が必要な場合は、[順序の編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8f90-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="e8f90-132">注文で与信チェックが必要な場合は、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e8f90-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="e8f90-133">完了したら、[管理ホームに移動する] を \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8f90-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="e8f90-134">容量を増やす、または減らす</span><span class="sxs-lookup"><span data-stu-id="e8f90-134">Increase or decrease storage</span></span>

<span data-ttu-id="e8f90-135">**Office 365** Extra File Storage アドオンを使用して追加のファイル ストレージを既に購入している場合は、次の手順を使用して、サブスクリプションの余分な記憶域領域を増やしたり減らしたりできます。</span><span class="sxs-lookup"><span data-stu-id="e8f90-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="e8f90-136">ストレージを 1 ギガバイトまで減らします。</span><span class="sxs-lookup"><span data-stu-id="e8f90-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="e8f90-137">余分な記憶域を削除するには、サポート [にお問い合わせください](../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f90-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="e8f90-138">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8f90-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="e8f90-139">[製品 **] タブ** で、365 Extra File **Storage Officeを含むサブスクリプションを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="e8f90-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="e8f90-140">[製品の詳細] ページの [アドオン] セクション **で、[** アドオンの管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8f90-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="e8f90-141">[アドオン **の管理] ウィンドウの**[アドオン] リストから **、[365 Officeストレージ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8f90-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="e8f90-142">[数量 **]** テキスト ボックスに、サブスクリプションに必要な記憶域の GB の数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e8f90-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="e8f90-143">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8f90-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="e8f90-144">私のプランは Office 365 Extra File Storage の対象ですか。</span><span class="sxs-lookup"><span data-stu-id="e8f90-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="e8f90-145">Office 365 Extra File Storage は、次のサブスクリプションでご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="e8f90-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="e8f90-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e8f90-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="e8f90-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="e8f90-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="e8f90-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e8f90-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="e8f90-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="e8f90-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="e8f90-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="e8f90-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="e8f90-151">Office SharePoint プラン 1 を使用した Web の詳細</span><span class="sxs-lookup"><span data-stu-id="e8f90-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="e8f90-152">Office SharePoint プラン 2 を使用した Web の詳細</span><span class="sxs-lookup"><span data-stu-id="e8f90-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="e8f90-153">SharePoint Online プラン 1</span><span class="sxs-lookup"><span data-stu-id="e8f90-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="e8f90-154">SharePoint Online プラン 2</span><span class="sxs-lookup"><span data-stu-id="e8f90-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="e8f90-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="e8f90-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="e8f90-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="e8f90-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="e8f90-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="e8f90-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="e8f90-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="e8f90-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="e8f90-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e8f90-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="e8f90-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="e8f90-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="e8f90-161">Office 365 Extra File Storage は、GCC、GCC High、DOD プランでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="e8f90-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="e8f90-162">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="e8f90-162">Related content</span></span>

<span data-ttu-id="e8f90-163">[サイトストレージの制限を管理](/sharepoint/manage-site-collection-storage-limits) する (記事)</span><span class="sxs-lookup"><span data-stu-id="e8f90-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="e8f90-164">[OneDrive ユーザーの既定の記憶域を設定する](/onedrive/set-default-storage-space)(記事)</span><span class="sxs-lookup"><span data-stu-id="e8f90-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>
