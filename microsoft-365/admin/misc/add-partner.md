---
title: サブスクリプション アドバイザー パートナーを追加、変更、または削除する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: Office 365 の購入時に、レコードのパートナーとしてサブスクリプションアドバイザーパートナーを追加する方法、パートナーを変更する方法、またはサブスクリプションからパートナーを削除する方法について説明します。
ms.openlocfilehash: 2afe5adebe1c0a47cae896d19219b97b70e453a4
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361582"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="cd128-103">サブスクリプション アドバイザー パートナーを追加、変更、または削除する</span><span class="sxs-lookup"><span data-stu-id="cd128-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

 <span data-ttu-id="cd128-104">**メモ**この記事は、中国で21Vianet が運営する Office 365 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd128-104">**Note** This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="cd128-105">これは、21Vianet パートナーが自分の Office 365 サブスクリプションを管理できるようにする組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="cd128-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span> 

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="cd128-p102">サブスクリプション アドバイザーとなっている Microsoft の認定パートナーは、サブスクリプションのセットアップと保守を行うために必要な販売、サポート、技術専門分野の知識を提供します。サブスクリプション アドバイザー パートナーは、Office 365 の購入時などに、レコードのパートナーとして追加できます。また、現在パートナーがいない場合は、[Microsoft Pinpoint](https://pinpoint.microsoft.com) の Web サイトで見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="cd128-p102">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription. You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time. If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span> 

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="cd128-p103">選択するパートナーは、使用中の Office 365 サービス、およびサービスを使っている国または地域によって異なります。サブスクリプションのパートナーを追加、またはパートナーを変更する場合は、最初にパートナーの Microsoft Partner ID をパートナーにたずねて入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd128-p103">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cd128-p104">サブスクリプション アドバイザーとなっている Microsoft の認定パートナーは、サブスクリプションのセットアップと保守を行うために必要な販売、サポート、技術専門分野の知識を提供します。サブスクリプション アドバイザー パートナーは、Office 365 の購入時などに、レコードのパートナーとして追加できます。また、現在パートナーがいない場合は、[Microsoft Pinpoint](https://pinpoint.microsoft.com) の Web サイトで見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="cd128-p104">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription. You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time. If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cd128-p105">選択するパートナーは、使用中の Office 365 サービス、およびサービスを使っている国または地域によって異なります。サブスクリプションのパートナーを追加、またはパートナーを変更する場合は、最初にパートナーの Microsoft Partner ID をパートナーにたずねて入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd128-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cd128-116">Office 365 の管理者として、ユーザーの作成または編集、ユーザーのパスワードのリセット、ユーザーライセンスの管理、ドメインの管理、組織内の他のユーザーへの管理者アクセス許可の割り当てなどの作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cd128-116">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="cd128-117">ただし、他のユーザーがこれらの管理タスクを実行できるようにする場合は、パートナー関係を作成することで、その役割を21Vianet の承認済みパートナーに委任できます。</span><span class="sxs-lookup"><span data-stu-id="cd128-117">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="cd128-118">購入時にパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="cd128-118">Add a partner at the time of purchase</span></span>

> [!NOTE]
> <span data-ttu-id="cd128-119">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd128-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="cd128-120">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
    
2. <span data-ttu-id="cd128-121">購入する製品を選択し、[**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-121">Select the product you want to purchase, and then select **Buy**.</span></span>
  
3. <span data-ttu-id="cd128-122">新しいパートナーを追加するには、[**注文に関するヘルプが必要ですか?** ] をクリックし、[ **Microsoft パートナーからサポートを受ける**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-122">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="cd128-123">[プロバイダー] ページの手順に従って、を検索するか、パートナーとの照合を行います。</span><span class="sxs-lookup"><span data-stu-id="cd128-123">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
    
4. <span data-ttu-id="cd128-124">パートナーが既に存在する場合は、チェックアウトウィザードの2番目の手順で、右側のウィンドウの [パートナー情報] の下にある [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-124">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>

5. <span data-ttu-id="cd128-p107">追加するパートナーの Microsoft パートナー ID を入力します。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd128-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

6. <span data-ttu-id="cd128-127">ウィザードの残りの手順を完了してサブスクリプションの購入を終了します。</span><span class="sxs-lookup"><span data-stu-id="cd128-127">Complete the rest of the wizard to finish buying your subscriptions.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="cd128-128">購入時にパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="cd128-128">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="cd128-129">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=848041)で、[**請求** \> **書購入サービス**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-129">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
    
2. <span data-ttu-id="cd128-130">購入する製品を選択し、[**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-130">Select the product you want to purchase, and then select **Buy**.</span></span>
  
3. <span data-ttu-id="cd128-131">新しいパートナーを追加するには、[**注文に関するヘルプが必要ですか?** ] をクリックし、[ **Microsoft パートナーからサポートを受ける**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-131">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="cd128-132">[プロバイダー] ページの手順に従って、を検索するか、パートナーとの照合を行います。</span><span class="sxs-lookup"><span data-stu-id="cd128-132">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
    
4. <span data-ttu-id="cd128-133">パートナーが既に存在する場合は、チェックアウトウィザードの2番目の手順で、右側のウィンドウの [パートナー情報] の下にある [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-133">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>

5. <span data-ttu-id="cd128-p108">追加するパートナーの Microsoft パートナー ID を入力します。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd128-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

6. <span data-ttu-id="cd128-136">ウィザードの残りの手順を完了してサブスクリプションの購入を終了します。</span><span class="sxs-lookup"><span data-stu-id="cd128-136">Complete the rest of the wizard to finish buying your subscriptions.</span></span> 
    
::: moniker-end


## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="cd128-137">既存のサブスクリプションにパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="cd128-137">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="cd128-138">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd128-138">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="cd128-139">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-139">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>
    
2. <span data-ttu-id="cd128-140">複数のサブスクリプションを持っている場合は、編集するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-140">If you have more than one subscription, select the subscription you want to edit.</span></span>
  
3. <span data-ttu-id="cd128-141">[サブスクリプション] ページで、[**パートナー** ] タブを選択し、追加するパートナーのパートナーネットワーク id を入力します。パートナーのパートナーの id を取得するには、パートナーに依頼します。</span><span class="sxs-lookup"><span data-stu-id="cd128-141">On the subscription page, select the **Partner** tab, and then type the Partner Network ID for the partner you're adding You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
    
4. <span data-ttu-id="cd128-142">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-142">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cd128-143">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-143">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
    
2. <span data-ttu-id="cd128-144">複数のサブスクリプションを持っている場合は、編集するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-144">If you have more than one subscription, select the subscription you want to edit.</span></span>
  
3. <span data-ttu-id="cd128-145">右側の [サブスクリプションコスト] で、[**その他のアクション** > ] [**レコードのパートナーを追加**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-145">On the right, under the subscription cost, choose **More actions** > **Add partner of record**.</span></span>

4. <span data-ttu-id="cd128-p109">追加するパートナーの Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd128-p109">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

5. <span data-ttu-id="cd128-148">パートナー ID が [ **サブスクリプション**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd128-148">The partner ID displays on the **Subscriptions** page.</span></span>
    
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cd128-149">このプロセスは、認定パートナーによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="cd128-149">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="cd128-150">パートナーから電子メールが送信され、レコードのパートナーとして機能するためのアクセス許可を付与する必要があるかどうかを尋ねられます。</span><span class="sxs-lookup"><span data-stu-id="cd128-150">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span> 
  
<span data-ttu-id="cd128-151">このオファーを承諾するには</span><span class="sxs-lookup"><span data-stu-id="cd128-151">To accept this offer</span></span>
  
1. <span data-ttu-id="cd128-152">電子メール内のパートナーの用語を読んでください。</span><span class="sxs-lookup"><span data-stu-id="cd128-152">Read the partner's terms in the email.</span></span>
    
2. <span data-ttu-id="cd128-153">契約を承認するには、Office 365 の認証ページに移行するリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-153">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
    
3. <span data-ttu-id="cd128-154">[**パートナー関係**] で、[**はい]** を選択してパートナーが代理管理者になることを承認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd128-154">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
    
4. <span data-ttu-id="cd128-155">パートナー関係のオファーに試用版サブスクリプションまたは購入提案が付属していた場合は、試用版またはサブスクリプション版のアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd128-155">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>
    
::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="cd128-156">サブスクリプションのパートナーを変更する</span><span class="sxs-lookup"><span data-stu-id="cd128-156">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="cd128-157">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd128-157">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="cd128-158">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-158">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>
    
2. <span data-ttu-id="cd128-159">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-159">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="cd128-160">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-160">Under the **Partner ID**, select **Edit partner of record**.</span></span>
  
4. <span data-ttu-id="cd128-p111">追加するパートナーの新しい Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd128-p111">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cd128-163">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
  
2. <span data-ttu-id="cd128-164">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-164">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="cd128-165">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-165">Under the **Partner ID**, select **Edit partner of record**.</span></span>
  
4. <span data-ttu-id="cd128-p112">追加するパートナーの新しい Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd128-p112">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>   

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cd128-168">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-168">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>
  
2. <span data-ttu-id="cd128-169">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-169">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="cd128-170">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-170">Under the **Partner ID**, select **Edit partner of record**.</span></span>
  
4. <span data-ttu-id="cd128-p113">追加するパートナーの新しい Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd128-p113">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>   

::: moniker-end


## <a name="view-your-partner-relationships"></a><span data-ttu-id="cd128-173">パートナー リレーションシップを表示する</span><span class="sxs-lookup"><span data-stu-id="cd128-173">View your partner relationships</span></span>

- <span data-ttu-id="cd128-174">管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">パートナー関係</a>の**設定** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-174">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="cd128-175">パートナーがこのページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd128-175">Your partners are listed on this page.</span></span> 
  
  <span data-ttu-id="cd128-176">パートナーがいない場合は、「何も存在しません」というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd128-176">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="cd128-177">サブスクリプションからパートナーを削除する</span><span class="sxs-lookup"><span data-stu-id="cd128-177">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="cd128-178">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd128-178">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1.  <span data-ttu-id="cd128-179">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-179">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>
    
2. <span data-ttu-id="cd128-180">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-180">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="cd128-181">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-181">Under the **Partner ID**, select **Edit partner of record**.</span></span>
    
6. <span data-ttu-id="cd128-182">[ **パートナー情報**] ページの [ **パートナー ID**] チェック ボックスをオフにし、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd128-182">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cd128-183">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-183">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="cd128-184">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-184">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="cd128-185">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-185">Under the **Partner ID**, select **Edit partner of record**.</span></span>
    
6. <span data-ttu-id="cd128-186">[ **パートナー情報**] ページの [ **パートナー ID**] チェック ボックスをオフにし、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd128-186">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cd128-187">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cd128-187">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="cd128-188">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-188">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="cd128-189">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd128-189">Under the **Partner ID**, select **Edit partner of record**.</span></span>
    
6. <span data-ttu-id="cd128-190">[ **パートナー情報**] ページの [ **パートナー ID**] チェック ボックスをオフにし、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd128-190">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>

::: moniker-end

  
## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="cd128-191">再販業者関係を削除する</span><span class="sxs-lookup"><span data-stu-id="cd128-191">Remove a reseller relationship</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="cd128-192">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd128-192">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="cd128-193">再販業者の関係を削除している場合、[ **削除** ] オプションが淡色表示されるため、再販業者パートナーに依頼して次の手順に従う必要があります。 [顧客との再販業者関係の削除](https://docs.microsoft.com/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="cd128-193">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](https://docs.microsoft.com/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cd128-194">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd128-194">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="cd128-195">再販業者の関係を削除している場合、[ **削除** ] オプションが淡色表示されるため、再販業者パートナーに依頼して次の手順に従う必要があります。 [顧客との再販業者関係の削除](https://docs.microsoft.com/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="cd128-195">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](https://docs.microsoft.com/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cd128-196">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd128-196">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="cd128-197">再販業者の関係を削除している場合、[ **削除** ] オプションが淡色表示されるため、再販業者パートナーに依頼して次の手順に従う必要があります。 [顧客との再販業者関係の削除](https://docs.microsoft.com/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="cd128-197">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](https://docs.microsoft.com/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="cd128-198">関連記事</span><span class="sxs-lookup"><span data-stu-id="cd128-198">Related articles</span></span>

[<span data-ttu-id="cd128-199">Office 365 パートナーまたは販売店を検索する</span><span class="sxs-lookup"><span data-stu-id="cd128-199">Find your Office 365 partner or reseller</span></span>](../manage/find-your-partner-or-reseller.md)
