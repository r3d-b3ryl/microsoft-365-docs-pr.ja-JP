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
description: Office 365 サブスクリプションでファイルストレージを追加して削減する方法について説明します。 追加のファイルストレージを使用すると、SharePoint Online および OneDrive により多くのコンテンツを格納できます。
ms.openlocfilehash: 64e98ff830b592b12e25620e4c2e89e09a161a3e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354848"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="c2c98-104">サブスクリプションのストレージ領域を追加する</span><span class="sxs-lookup"><span data-stu-id="c2c98-104">Add storage space for your subscription</span></span>

<span data-ttu-id="c2c98-105">SharePoint Online サイトコレクションのストレージが不足し始めた場合は、プランが該当する場合に、サブスクリプションにストレージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="c2c98-106">使用可能なアドオンの一覧に**Office 365 の追加ファイルストレージ**が表示されない場合は、プランが対象外であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="c2c98-107">詳細については、「[プランの対象の有無](#is-my-plan-eligible-for-office-365-extra-file-storage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2c98-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="c2c98-108">使用可能な記憶域を表示する</span><span class="sxs-lookup"><span data-stu-id="c2c98-108">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c2c98-109">グローバル管理者または SharePoint 管理者として https://admin.microsoft.com にサインインします。(ページにアクセスする権限がないというメッセージが表示される場合は、組織には Office 365 管理者権限がありません。)</span><span class="sxs-lookup"><span data-stu-id="c2c98-109">Sign in to https://admin.microsoft.com as a global or SharePoint admin. (If you see a message that you don't have permission to access the page, you don't have Office 365 administrator permissions in your organization.)</span></span>
    
2. <span data-ttu-id="c2c98-110">左側のウィンドウの [**管理センター**] で、[ **SharePoint**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-110">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c2c98-111">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-111">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span> 
    
3. <span data-ttu-id="c2c98-112">新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-112">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c2c98-113">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-113">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="c2c98-114">(組織の Office 365 で Multi-Geo が構成されている場合、バーにはすべての地理的な場所で使用されている記憶域の容量も表示されます。)</span><span class="sxs-lookup"><span data-stu-id="c2c98-114">(If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.)</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c2c98-115">グローバルまたはhttps://portal.office.de SharePoint 管理者としてにサインインし、[管理者] タイルを選択して、管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-115">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="c2c98-116">(ページへのアクセス許可がないことを示すメッセージが表示される場合、組織で Office 365 管理者のアクセス許可を持っていません)。</span><span class="sxs-lookup"><span data-stu-id="c2c98-116">(If you see a message that you don't have permission to access the page, you don't have Office 365 administrator permissions in your organization.)</span></span>
    
2. <span data-ttu-id="c2c98-117">左側のウィンドウの [**管理センター**] で、[ **SharePoint**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-117">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c2c98-118">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-118">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span> 
    
3. <span data-ttu-id="c2c98-119">新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-119">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c2c98-120">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-120">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c2c98-121">グローバルまたはhttps://login.partner.microsoftonline.cn/ SharePoint 管理者としてにサインインし、[管理者] タイルを選択して、管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-121">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="c2c98-122">(ページへのアクセス許可がないことを示すメッセージが表示される場合、組織で Office 365 管理者のアクセス許可を持っていません)。</span><span class="sxs-lookup"><span data-stu-id="c2c98-122">(If you see a message that you don't have permission to access the page, you don't have Office 365 administrator permissions in your organization.)</span></span>
     
2. <span data-ttu-id="c2c98-123">左側のウィンドウの [**管理センター**] で、[ **SharePoint**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c2c98-124">従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span> 
    
3. <span data-ttu-id="c2c98-125">新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c2c98-126">ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

::: moniker-end


![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

> [!NOTE]
> <span data-ttu-id="c2c98-128">記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。</span><span class="sxs-lookup"><span data-stu-id="c2c98-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span> 

<span data-ttu-id="c2c98-129">使用している記憶域の容量を決定したら、サブスクリプションの記憶域を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-129">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="c2c98-130">記憶域を追加するためにどのくらいのコストがかかるかを確認するには、この記事の手順に従って、購入する前に価格情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c2c98-130">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="c2c98-131">サイトコレクションの記憶域の制限を設定する方法については、「[サイトコレクションの記憶域の制限を管理](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2c98-131">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="c2c98-132">サブスクリプションにストレージを追加する</span><span class="sxs-lookup"><span data-stu-id="c2c98-132">Add storage to your subscription</span></span>

<span data-ttu-id="c2c98-133">サブスクリプションのために特別なストレージをまだ購入していない場合は、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-133">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="c2c98-134">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-134">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="c2c98-135">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

2. <span data-ttu-id="c2c98-136">[**サービスを購入**する] ページの下部で、 **[アドオン] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-136">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>

3. <span data-ttu-id="c2c98-137">[ **Office 365 その他のファイル記憶域**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-137">Select **Office 365 Extra File Storage**.</span></span>

4. <span data-ttu-id="c2c98-138">[ **Office 365 追加ファイル記憶域**] ページで、[基本サブスクリプション] を選択し、追加する記憶域の gb 数を入力します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-138">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>

5. <span data-ttu-id="c2c98-139">[**今すぐチェックアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-139">Select **Check out now**.</span></span>

6. <span data-ttu-id="c2c98-140">[**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-140">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c2c98-141">[**注文の完了**] ページで、合計値を確認します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-141">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="c2c98-142">変更を加える必要がある場合は、[**順序の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-142">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="c2c98-143">注文で貸方の確認が必要な場合は、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c2c98-143">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="c2c98-144">完了したら、[**注文** \> ] [**管理者のホーム] に移動**します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-144">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c2c98-145">管理センターで、[**課金** \><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。  </span><span class="sxs-lookup"><span data-stu-id="c2c98-145">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c2c98-146">[**サブスクリプション**] ページで、ストレージスペースを追加するサブスクリプションを選択し、[アドオン]**を選択します。**</span><span class="sxs-lookup"><span data-stu-id="c2c98-146">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c2c98-148">**アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-148">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c2c98-149">[アドオンの**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-149">Select **Buy add-ons**.</span></span>

    ![管理センターの [サブスクリプション] ページで、[アドオンの購入] リンクをオンにします。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="c2c98-151">[**購入サービス**] ページで、[ **Office 365 追加のファイルストレージ**] をマウス上またはタップし、[**今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-151">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="c2c98-152">必要なユーザーライセンス数を入力し、表示された場合は、基本サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-152">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="c2c98-153">[**今すぐチェックアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-153">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="c2c98-154">[**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-154">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c2c98-155">[**注文の完了**] ページで、[**注文**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-155">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c2c98-156">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-156">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c2c98-157">[**サブスクリプション**] ページで、ストレージスペースを追加するサブスクリプションを選択し、[アドオン]**を選択します。**</span><span class="sxs-lookup"><span data-stu-id="c2c98-157">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c2c98-159">**アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-159">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c2c98-160">[アドオンの**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-160">Select **Buy add-ons**.</span></span>

    ![管理センターの [サブスクリプション] ページで、[アドオンの購入] リンクをオンにします。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="c2c98-162">[**購入サービス**] ページで、[ **Office 365 追加のファイルストレージ**] をマウス上またはタップし、[**今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-162">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="c2c98-163">必要なユーザーライセンス数を入力し、表示された場合は、基本サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-163">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="c2c98-164">[**今すぐチェックアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-164">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="c2c98-165">[**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-165">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c2c98-166">[**注文の完了**] ページで、[**注文**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-166">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end


## <a name="increase-or-decrease-storage"></a><span data-ttu-id="c2c98-167">ストレージを拡大または縮小する</span><span class="sxs-lookup"><span data-stu-id="c2c98-167">Increase or decrease storage</span></span>

<span data-ttu-id="c2c98-168">**Office 365 追加ファイル記憶域**アドオンを使用して、追加のファイル記憶域を既に購入している場合は、以下の手順を使用してサブスクリプションの追加の記憶域を増加または減少させることができます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-168">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="c2c98-169">記憶域を1ギガバイトまで減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-169">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="c2c98-170">その他の記憶領域をすべて削除するには、[サポートに連絡](../admin/contact-support-for-business-products.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2c98-170">To remove all of the extra storage space, you need to [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="c2c98-171">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-171">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="c2c98-172">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-172">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="c2c98-173">**Office 365 追加ファイル記憶域**アドオンを含むサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-173">Choose the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>

3. <span data-ttu-id="c2c98-174">[**アドオン] を選択し、[\*\*\*\*数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-174">Select **Add-ons**, then choose **Change quantity**.</span></span>

4. <span data-ttu-id="c2c98-175">[**ギガバイトの追加/削除**] ウィンドウで、サブスクリプションに使用する合計ギガバイト数を入力し、[**変更の送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-175">In the **Add/Remove gigabytes** pane, enter the total gigabytes you want for the subscription, then select **Submit change**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c2c98-176">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-176">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>


2. <span data-ttu-id="c2c98-177">[**サブスクリプション**] ページで、 **[アドオン] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-177">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c2c98-179">**アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-179">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c2c98-180">[ **Office 365 その他のファイル記憶域**] で、[**数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-180">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="c2c98-182">右側のウィンドウで、必要な合計ギガバイト数を入力し、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-182">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="c2c98-183">たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-183">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="c2c98-184">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-184">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c2c98-185">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-185">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c2c98-186">[**サブスクリプション**] ページで、 **[アドオン] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-186">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c2c98-188">**アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-188">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c2c98-189">[ **Office 365 その他のファイル記憶域**] で、[**数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-189">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="c2c98-191">右側のウィンドウで、必要な合計ギガバイト数を入力し、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-191">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="c2c98-192">たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-192">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="c2c98-193">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2c98-193">Select **Close**.</span></span>

::: moniker-end



## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="c2c98-194">私のプランは Office 365 Extra File Storage の対象ですか。</span><span class="sxs-lookup"><span data-stu-id="c2c98-194">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="c2c98-195">Office 365 Extra File Storage は、次のサブスクリプションでご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-195">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="c2c98-196">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c2c98-196">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="c2c98-197">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="c2c98-197">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="c2c98-198">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c2c98-198">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="c2c98-199">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="c2c98-199">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="c2c98-200">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="c2c98-200">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="c2c98-201">SharePoint プラン1を使用した web 用 Office</span><span class="sxs-lookup"><span data-stu-id="c2c98-201">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="c2c98-202">SharePoint プラン2を使用した web 用 Office</span><span class="sxs-lookup"><span data-stu-id="c2c98-202">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="c2c98-203">SharePoint Online プラン 1</span><span class="sxs-lookup"><span data-stu-id="c2c98-203">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="c2c98-204">SharePoint Online プラン 2</span><span class="sxs-lookup"><span data-stu-id="c2c98-204">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="c2c98-205">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="c2c98-205">Office 365 Business Essentials</span></span>

- <span data-ttu-id="c2c98-206">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c2c98-206">Office 365 Business Premium</span></span>

- <span data-ttu-id="c2c98-207">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="c2c98-207">Microsoft 365 Business</span></span>

- <span data-ttu-id="c2c98-208">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="c2c98-208">Microsoft 365 E3</span></span>

- <span data-ttu-id="c2c98-209">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c2c98-209">Microsoft 365 E5</span></span>

- <span data-ttu-id="c2c98-210">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="c2c98-210">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="c2c98-211">Office 365 の特別なファイル記憶域は、GCC、GCC High、および DOD プランでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2c98-211">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>