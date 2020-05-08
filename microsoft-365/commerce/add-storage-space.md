---
title: サブスクリプションのストレージ領域を追加する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEU150
- GEA150
- GSP150
ms.assetid: 96ea3533-de64-4b01-839a-c560875a662c
description: Microsoft 365 サブスクリプションでファイルストレージを追加および削減する方法について説明します。 追加のファイルストレージを使用すると、SharePoint Online および OneDrive により多くのコンテンツを格納できます。
ms.openlocfilehash: 921fd4a232d288971150a3379b138613f009f9dc
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140968"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="95d5d-104">サブスクリプションのストレージ領域を追加する</span><span class="sxs-lookup"><span data-stu-id="95d5d-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="95d5d-105">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="95d5d-105">The admin center is changing.</span></span> <span data-ttu-id="95d5d-106">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95d5d-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="95d5d-107">SharePoint Online サイト コレクションの容量が不足し始めた場合、ご使用のプランが対象に含まれている場合は、サブスクリプションに容量を追加できます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="95d5d-108">使用可能なアドオンの一覧に**Office 365 の追加ファイルストレージ**が表示されない場合は、プランが対象外であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="95d5d-109">詳細については、「[プランの対象の有無](#is-my-plan-eligible-for-office-365-extra-file-storage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95d5d-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="95d5d-110">利用可能な記憶域を表示する</span><span class="sxs-lookup"><span data-stu-id="95d5d-110">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="95d5d-111">[新しい SharePoint 管理センターの [アクティブなサイト] ページ](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true)に移動し、組織の[管理者権限](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)が付与されているアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="95d5d-111">Go to the [Active sites page of the new SharePoint admin center](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true), and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="95d5d-112">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-112">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="95d5d-113">(組織の Office 365 で Multi-Geo が構成されている場合、バーにはすべての地理的な場所で使用されている記憶域の容量も表示されます。)</span><span class="sxs-lookup"><span data-stu-id="95d5d-113">(If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.)</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="95d5d-114">グローバルまたはhttps://portal.office.de SharePoint 管理者としてにサインインし、[管理者] タイルを選択して、管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-114">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="95d5d-115">(ページへのアクセス許可がないことを示すメッセージが表示される場合、組織で Microsoft 365 管理者のアクセス許可を持っていません)。</span><span class="sxs-lookup"><span data-stu-id="95d5d-115">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="95d5d-116">左側のウィンドウの [**管理センター**] で、[ **SharePoint**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-116">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="95d5d-117">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-117">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="95d5d-118">新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-118">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="95d5d-119">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-119">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="95d5d-120">グローバルまたはhttps://login.partner.microsoftonline.cn/ SharePoint 管理者としてにサインインし、[管理者] タイルを選択して、管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-120">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="95d5d-121">(ページへのアクセス許可がないことを示すメッセージが表示される場合、組織で Microsoft 365 管理者のアクセス許可を持っていません)。</span><span class="sxs-lookup"><span data-stu-id="95d5d-121">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="95d5d-122">左側のウィンドウの [**管理センター**] で、[ **SharePoint**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-122">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="95d5d-123">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-123">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="95d5d-124">新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-124">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="95d5d-125">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-125">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

::: moniker-end

![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

> [!NOTE]
> <span data-ttu-id="95d5d-127">記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。</span><span class="sxs-lookup"><span data-stu-id="95d5d-127">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="95d5d-128">使用している記憶域の容量を決定したら、サブスクリプションの記憶域を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-128">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="95d5d-129">記憶域を追加するためにどのくらいのコストがかかるかを確認するには、この記事の手順に従って、購入する前に価格情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="95d5d-129">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="95d5d-130">サイトコレクションの記憶域の制限を設定する方法については、「[サイトコレクションの記憶域の制限を管理](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95d5d-130">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="95d5d-131">サブスクリプションにストレージを追加する</span><span class="sxs-lookup"><span data-stu-id="95d5d-131">Add storage to your subscription</span></span>

<span data-ttu-id="95d5d-132">サブスクリプションのために特別なストレージをまだ購入していない場合は、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-132">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="95d5d-133">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

2. <span data-ttu-id="95d5d-134">[**サービスを購入**する] ページの下部で、 **[アドオン] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-134">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>

3. <span data-ttu-id="95d5d-135">[ **Office 365 その他のファイル記憶域**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-135">Select **Office 365 Extra File Storage**.</span></span>

4. <span data-ttu-id="95d5d-136">[ **Office 365 追加ファイル記憶域**] ページで、[基本サブスクリプション] を選択し、追加する記憶域の gb 数を入力します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-136">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>

5. <span data-ttu-id="95d5d-137">[**今すぐチェックアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-137">Select **Check out now**.</span></span>

6. <span data-ttu-id="95d5d-138">[**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-138">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="95d5d-139">[**注文の完了**] ページで、合計値を確認します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-139">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="95d5d-140">変更を加える必要がある場合は、[**順序の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-140">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="95d5d-141">注文で貸方の確認が必要な場合は、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="95d5d-141">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="95d5d-142">完了したら、[**注文** \> ] [**管理者のホーム] に移動**します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-142">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="95d5d-143">管理センターで、[**課金** \><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。  </span><span class="sxs-lookup"><span data-stu-id="95d5d-143">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="95d5d-144">[**サブスクリプション**] ページで、ストレージスペースを追加するサブスクリプションを選択し、[アドオン]**を選択します。**</span><span class="sxs-lookup"><span data-stu-id="95d5d-144">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="95d5d-146">**アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-146">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="95d5d-147">[アドオンの**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-147">Select **Buy add-ons**.</span></span>

    ![管理センターの [サブスクリプション] ページで、[アドオンの購入] リンクをオンにします。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="95d5d-149">[**購入サービス**] ページで、[ **Office 365 追加のファイルストレージ**] をマウス上またはタップし、[**今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-149">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="95d5d-150">必要なユーザーライセンス数を入力し、表示された場合は、基本サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-150">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="95d5d-151">[**今すぐチェックアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-151">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="95d5d-152">[**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-152">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="95d5d-153">[**注文の完了**] ページで、[**注文**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-153">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="95d5d-154">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-154">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="95d5d-155">[**サブスクリプション**] ページで、ストレージスペースを追加するサブスクリプションを選択し、[アドオン]**を選択します。**</span><span class="sxs-lookup"><span data-stu-id="95d5d-155">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="95d5d-157">**アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-157">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="95d5d-158">[アドオンの**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-158">Select **Buy add-ons**.</span></span>

    ![管理センターの [サブスクリプション] ページで、[アドオンの購入] リンクをオンにします。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="95d5d-160">[**購入サービス**] ページで、[ **Office 365 追加のファイルストレージ**] をマウス上またはタップし、[**今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-160">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="95d5d-161">必要なユーザーライセンス数を入力し、表示された場合は、基本サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-161">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="95d5d-162">[**今すぐチェックアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-162">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="95d5d-163">[**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-163">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="95d5d-164">[**注文の完了**] ページで、[**注文**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-164">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="95d5d-165">容量を増やす、または減らす</span><span class="sxs-lookup"><span data-stu-id="95d5d-165">Increase or decrease storage</span></span>

<span data-ttu-id="95d5d-166">**Office 365 追加ファイル記憶域**アドオンを使用して、追加のファイル記憶域を既に購入している場合は、以下の手順を使用してサブスクリプションの追加の記憶域を増加または減少させることができます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-166">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="95d5d-167">記憶域を1ギガバイトまで減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-167">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="95d5d-168">その他の記憶領域をすべて削除するには、[サポートに連絡](../admin/contact-support-for-business-products.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95d5d-168">To remove all of the extra storage space, you need to [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="95d5d-169">管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品</a>の**請求** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-169">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="95d5d-170">**Office 365 追加ファイル記憶域**アドオンを含むサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-170">Choose the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>

3. <span data-ttu-id="95d5d-171">[**アドオン] を選択し、[\*\*\*\*数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-171">Select **Add-ons**, then choose **Change quantity**.</span></span>

4. <span data-ttu-id="95d5d-172">[**ギガバイトの追加/削除**] ウィンドウで、サブスクリプションに使用する合計ギガバイト数を入力し、[**変更の送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-172">In the **Add/Remove gigabytes** pane, enter the total gigabytes you want for the subscription, then select **Submit change**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="95d5d-173">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-173">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="95d5d-174">[**サブスクリプション**] ページで、 **[アドオン] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-174">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="95d5d-176">**アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-176">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="95d5d-177">[ **Office 365 その他のファイル記憶域**] で、[**数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-177">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="95d5d-179">右側のウィンドウで、必要な合計ギガバイト数を入力し、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-179">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="95d5d-180">たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-180">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="95d5d-181">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-181">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="95d5d-182">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-182">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="95d5d-183">[**サブスクリプション**] ページで、 **[アドオン] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-183">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="95d5d-185">**アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-185">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="95d5d-186">[ **Office 365 その他のファイル記憶域**] で、[**数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-186">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="95d5d-188">右側のウィンドウで、必要な合計ギガバイト数を入力し、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-188">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="95d5d-189">たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-189">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="95d5d-190">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d5d-190">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="95d5d-191">私のプランは Office 365 Extra File Storage の対象ですか。</span><span class="sxs-lookup"><span data-stu-id="95d5d-191">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="95d5d-192">Office 365 Extra File Storage は、次のサブスクリプションでご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-192">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="95d5d-193">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="95d5d-193">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="95d5d-194">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="95d5d-194">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="95d5d-195">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="95d5d-195">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="95d5d-196">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="95d5d-196">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="95d5d-197">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="95d5d-197">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="95d5d-198">SharePoint プラン1を使用した web 用 Office</span><span class="sxs-lookup"><span data-stu-id="95d5d-198">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="95d5d-199">SharePoint プラン2を使用した web 用 Office</span><span class="sxs-lookup"><span data-stu-id="95d5d-199">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="95d5d-200">SharePoint Online プラン 1</span><span class="sxs-lookup"><span data-stu-id="95d5d-200">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="95d5d-201">SharePoint Online プラン 2</span><span class="sxs-lookup"><span data-stu-id="95d5d-201">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="95d5d-202">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="95d5d-202">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="95d5d-203">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="95d5d-203">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="95d5d-204">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="95d5d-204">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="95d5d-205">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="95d5d-205">Microsoft 365 E3</span></span>

- <span data-ttu-id="95d5d-206">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="95d5d-206">Microsoft 365 E5</span></span>

- <span data-ttu-id="95d5d-207">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="95d5d-207">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="95d5d-208">Office 365 の特別なファイル記憶域は、GCC、GCC High、および DOD プランでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="95d5d-208">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>
