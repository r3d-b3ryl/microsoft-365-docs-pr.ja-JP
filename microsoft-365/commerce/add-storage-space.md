---
title: サブスクリプションの記憶領域を追加する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Microsoft 365 サブスクリプションでファイル ストレージを追加および削減する方法について説明します。 追加のファイル ストレージを使用すると、SharePoint Online と OneDrive にさらに多くのコンテンツを格納できます。
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114909"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="0c07d-104">サブスクリプションの記憶領域を追加する</span><span class="sxs-lookup"><span data-stu-id="0c07d-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0c07d-105">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="0c07d-105">The admin center is changing.</span></span> <span data-ttu-id="0c07d-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c07d-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="0c07d-107">SharePoint Online サイト コレクションの容量が不足し始めた場合、ご使用のプランが対象に含まれている場合は、サブスクリプションに容量を追加できます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="0c07d-108">利用可能なアドオンの一覧に **Office 365 Extra File Storage** が表示されない場合は、プランが対象とされていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="0c07d-109">詳細については、「プランが対象 [ですか?」を参照してください。](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="0c07d-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="0c07d-110">ボリューム ライセンスまたは CSP を通じてサブスクリプションを購入した場合、組織の Office **365 Extra File Storage** を Microsoft から直接購入することはできません。</span><span class="sxs-lookup"><span data-stu-id="0c07d-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="0c07d-111">サポートについては、担当の担当者またはパートナーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0c07d-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0c07d-112">開始する前に</span><span class="sxs-lookup"><span data-stu-id="0c07d-112">Before you begin</span></span>

<span data-ttu-id="0c07d-113">この記事のタスクを実行するには、グローバル管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c07d-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="0c07d-114">詳細については、[「管理者の役割について」](../admin/add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c07d-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="0c07d-115">利用可能な記憶域の表示</span><span class="sxs-lookup"><span data-stu-id="0c07d-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0c07d-116">SharePoint 管理センターで、[アクティブなサイト<a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a>] ページに移動し、組織の管理者権限を持つ[アカウントでサインイン](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="0c07d-117">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="0c07d-118">組織が Office 365 で複数地域を構成している場合は、すべての地域の場所で使用される記憶域の量もバーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="0c07d-120">記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。</span><span class="sxs-lookup"><span data-stu-id="0c07d-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0c07d-121">グローバル管理者または SharePoint 管理者としてサインインし、[管理] タイルを選択して管理 https://portal.office.de センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="0c07d-122">ページにアクセスするアクセス許可を持たなかったというメッセージが表示された場合は、組織に Microsoft 365 管理者のアクセス許可が付与されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="0c07d-123">左側のウィンドウの [**管理センター**] で、[**SharePoint**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="0c07d-124">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="0c07d-125">新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="0c07d-126">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="0c07d-128">記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。</span><span class="sxs-lookup"><span data-stu-id="0c07d-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0c07d-129">グローバル管理者または SharePoint 管理者としてサインインし、[管理] タイルを選択して管理 https://login.partner.microsoftonline.cn/ センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="0c07d-130">(ページにアクセスするアクセス許可が付与されていないというメッセージが表示される場合は、組織に Microsoft 365 管理者のアクセス許可が付与されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="0c07d-131">左側のウィンドウの [**管理センター**] で、[**SharePoint**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="0c07d-132">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="0c07d-133">新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="0c07d-134">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="0c07d-136">記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。</span><span class="sxs-lookup"><span data-stu-id="0c07d-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="0c07d-137">使用している記憶域の容量を決定した後、サブスクリプションの記憶域を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="0c07d-138">記憶域を追加するために必要なコストを確認するには、この記事の手順に従い、購入する前に価格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="0c07d-139">サイト コレクションの記憶域制限の設定については、「サイト コレクションの記憶域の制限を [管理する」を参照してください](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)。</span><span class="sxs-lookup"><span data-stu-id="0c07d-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="0c07d-140">サブスクリプションにストレージを追加する</span><span class="sxs-lookup"><span data-stu-id="0c07d-140">Add storage to your subscription</span></span>

<span data-ttu-id="0c07d-141">サブスクリプションの追加ストレージをまだ購入していない場合は、購入できます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0c07d-142">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="0c07d-143">[サービスの購入] ページの下部 **で** 、[アドオン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="0c07d-144">Select **Office 365 Extra File Storage**.</span><span class="sxs-lookup"><span data-stu-id="0c07d-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="0c07d-145">[Office **365 Extra File Storage]** ページで、基本サブスクリプションを選択し、追加するストレージのギガバイト数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="0c07d-146">[今 **すぐチェックアウト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="0c07d-147">On the **How does this look?** page, verify the number of gbs of storage you selected, review the pricing information, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="0c07d-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="0c07d-148">[注文 **の完了] ページ** で、合計を確認します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="0c07d-149">変更が必要な場合は、[順序の編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="0c07d-150">注文に与信チェックが必要な場合は、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0c07d-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="0c07d-151">完了したら、[注文を管理ホームに移動 \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0c07d-152">管理センターで、[課金サブスクリプション] \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">ページに移動</a>します。  </span><span class="sxs-lookup"><span data-stu-id="0c07d-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="0c07d-153">[ **サブスクリプション] ページ** で、記憶域を追加するサブスクリプションを選択し、[アドオン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="0c07d-155">アドオンが表示されていない場合に、サブスクリプションがパートナー経由で購入された場合は、ボリューム ライセンス サービス センター **(VLSC) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="0c07d-156">[ **アドオンの購入] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-156">Select **Buy add-ons**.</span></span>

    ![管理センターの [サブスクリプション] ページにある [アドオン] リンクを購入します。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="0c07d-158">[サービス **の購入]** ページで **、365** Extra File Storage をOfficeまたはタップし、[今すぐ購入] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="0c07d-159">必要なユーザー ライセンスの数を入力し、表示されている場合は基本サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="0c07d-160">[今 **すぐチェックアウト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="0c07d-161">On the **How does this look?** page, verify the number of gbs of storage you selected, review the pricing information, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="0c07d-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="0c07d-162">[注文 **の完了] ページで** 、[注文] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0c07d-163">管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[サブスクリプション]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="0c07d-164">[ **サブスクリプション] ページ** で、記憶域を追加するサブスクリプションを選択し、[アドオン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="0c07d-166">アドオンが表示されていない場合に、サブスクリプションがパートナー経由で購入された場合は、ボリューム ライセンス サービス センター **(VLSC) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="0c07d-167">[ **アドオンの購入] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-167">Select **Buy add-ons**.</span></span>

    ![管理センターの [サブスクリプション] ページにある [アドオン] リンクを購入します。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="0c07d-169">[サービス **の購入]** ページで **、[365** Extra File Storage] をOfficeまたはタップし、[今すぐ購入] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="0c07d-170">必要なユーザー ライセンスの数を入力し、表示されている場合は基本サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="0c07d-171">[今 **すぐチェックアウト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="0c07d-172">On the **How does this look?** page, verify the number of gbs of storage you selected, review the pricing information, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="0c07d-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="0c07d-173">[注文 **の完了] ページで** 、[注文] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="0c07d-174">容量を増やす、または減らす</span><span class="sxs-lookup"><span data-stu-id="0c07d-174">Increase or decrease storage</span></span>

<span data-ttu-id="0c07d-175">**Office 365** Extra File Storage アドオンを介して追加のファイル ストレージを既に購入している場合は、次の手順を使用して、サブスクリプションの追加の記憶域を増減できます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="0c07d-176">記憶域を 1 GB まで減らします。</span><span class="sxs-lookup"><span data-stu-id="0c07d-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="0c07d-177">追加の記憶領域を削除するには、サポートにお [問い合わせください](../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="0c07d-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0c07d-178">管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="0c07d-179">[製品 **] タブ** で、新しい Office **365 Extra File Storage** アドオンを含むサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="0c07d-180">製品の詳細ページの [アドオン] セクションで、[アドオンの管理]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="0c07d-181">[アドオン **の管理]** ウィンドウの [アドオン] ボックスの一覧で **、[365 extra File Storage] Officeを選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="0c07d-182">[ **数量]** テキスト ボックスに、サブスクリプションに使用する記憶域の GB 数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="0c07d-183">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0c07d-184">管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[サブスクリプション]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="0c07d-185">[サブスクリプション **] ページで** 、[アドオン **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="0c07d-187">アドオンが表示されていない場合に、サブスクリプションがパートナー経由で購入された場合は、ボリューム ライセンス サービス センター **(VLSC) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="0c07d-188">[Office **365 Extra File Storage]** で、[数量の変更 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="0c07d-190">右側のウィンドウで、必要なギガバイトの総数を入力し、[送信] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="0c07d-191">たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="0c07d-192">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0c07d-193">管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[サブスクリプション]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="0c07d-194">[サブスクリプション **] ページで** 、[アドオン **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="0c07d-196">アドオンが表示されていない場合に、サブスクリプションがパートナー経由で購入された場合は、ボリューム ライセンス サービス センター **(VLSC) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="0c07d-197">[Office **365 Extra File Storage]** で、[数量の変更 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="0c07d-199">右側のウィンドウで、必要なギガバイトの総数を入力し、[送信] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0c07d-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="0c07d-200">たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="0c07d-201">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c07d-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="0c07d-202">私のプランは Office 365 Extra File Storage の対象ですか。</span><span class="sxs-lookup"><span data-stu-id="0c07d-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="0c07d-203">Office 365 Extra File Storage は、次のサブスクリプションでご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="0c07d-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="0c07d-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="0c07d-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="0c07d-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="0c07d-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="0c07d-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="0c07d-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="0c07d-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="0c07d-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="0c07d-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="0c07d-209">Office SharePoint プラン 1 を使用する Web の場合</span><span class="sxs-lookup"><span data-stu-id="0c07d-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="0c07d-210">Office SharePoint プラン 2 を使用する Web の場合</span><span class="sxs-lookup"><span data-stu-id="0c07d-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="0c07d-211">SharePoint Online プラン 1</span><span class="sxs-lookup"><span data-stu-id="0c07d-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="0c07d-212">SharePoint Online プラン 2</span><span class="sxs-lookup"><span data-stu-id="0c07d-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="0c07d-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="0c07d-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="0c07d-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="0c07d-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="0c07d-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0c07d-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="0c07d-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="0c07d-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="0c07d-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0c07d-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="0c07d-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="0c07d-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="0c07d-219">Office 365 Extra File Storage は、GCC、GCC High、DOD プランでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="0c07d-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="0c07d-220">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="0c07d-220">Related content</span></span>

<span data-ttu-id="0c07d-221">[サイトの記憶域の制限を管理](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) する (記事)</span><span class="sxs-lookup"><span data-stu-id="0c07d-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="0c07d-222">[OneDrive ユーザーの既定の記憶領域を設定する](https://docs.microsoft.com/onedrive/set-default-storage-space)(記事)</span><span class="sxs-lookup"><span data-stu-id="0c07d-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
