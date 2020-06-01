---
title: サブスクリプション アドバイザー パートナーを追加、変更、または削除する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: サブスクリプションアドバイザーパートナーを Microsoft 365 の購入時にレコードのパートナーとして追加する方法、パートナーを変更する方法、またはサブスクリプションからパートナーを削除する方法について説明します。
ms.openlocfilehash: 4ab02e95c2a2330e95f8a54f717e38025d04714c
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432197"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="39540-103">サブスクリプション アドバイザー パートナーを追加、変更、または削除する</span><span class="sxs-lookup"><span data-stu-id="39540-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

 <span data-ttu-id="39540-104">**メモ**この記事は、中国で21Vianet が運営する Office 365 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="39540-104">**Note** This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="39540-105">これは、21Vianet パートナーが自分の Office 365 サブスクリプションを管理できるようにする組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="39540-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span> 

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="39540-106">サブスクリプション アドバイザーとなっている Microsoft の認定パートナーは、サブスクリプションのセットアップと保守を行うために必要な販売、サポート、技術専門分野の知識を提供します。</span><span class="sxs-lookup"><span data-stu-id="39540-106">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="39540-107">Microsoft 365 または別のユーザーを購入する際に、サブスクリプションアドバイザーパートナーをレコードのパートナーとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="39540-107">You can add a subscription advisor partner as a partner of record when you purchase Microsoft 365 or at another time.</span></span> <span data-ttu-id="39540-108">また、現在パートナーがいない場合は、[Microsoft Pinpoint](https://pinpoint.microsoft.com) の Web サイトで見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="39540-108">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span> 

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="39540-109">選択するパートナーは、使用する Microsoft サービスと、それらのサービスを使用する国または地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="39540-109">The partner you choose depends on the Microsoft services you use and the country or region where you'll use those services.</span></span> <span data-ttu-id="39540-110">サブスクリプションのパートナーを追加、またはパートナーを変更する場合は、最初にパートナーの Microsoft Partner ID をパートナーにたずねて入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39540-110">If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="39540-p104">サブスクリプション アドバイザーとなっている Microsoft の認定パートナーは、サブスクリプションのセットアップと保守を行うために必要な販売、サポート、技術専門分野の知識を提供します。サブスクリプション アドバイザー パートナーは、Office 365 の購入時などに、レコードのパートナーとして追加できます。また、現在パートナーがいない場合は、[Microsoft Pinpoint](https://pinpoint.microsoft.com) の Web サイトで見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="39540-p104">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription. You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time. If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="39540-p105">選択するパートナーは、使用中の Office 365 サービス、およびサービスを使っている国または地域によって異なります。サブスクリプションのパートナーを追加、またはパートナーを変更する場合は、最初にパートナーの Microsoft Partner ID をパートナーにたずねて入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39540-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="39540-116">Office 365 の管理者として、ユーザーの作成または編集、ユーザーのパスワードのリセット、ユーザーライセンスの管理、ドメインの管理、組織内の他のユーザーへの管理者アクセス許可の割り当てなどの作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="39540-116">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="39540-117">ただし、他のユーザーがこれらの管理タスクを実行できるようにする場合は、パートナー関係を作成することで、その役割を21Vianet の承認済みパートナーに委任できます。</span><span class="sxs-lookup"><span data-stu-id="39540-117">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="39540-118">購入時にパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="39540-118">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="39540-119">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
    
2. <span data-ttu-id="39540-120">購入する製品を選択し、[**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-120">Select the product you want to purchase, and then select **Buy**.</span></span>
  
3. <span data-ttu-id="39540-121">新しいパートナーを追加するには、[**注文に関するヘルプが必要ですか?** ] をクリックし、[ **Microsoft パートナーからサポートを受ける**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-121">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="39540-122">[プロバイダー] ページの手順に従って、を検索するか、パートナーとの照合を行います。</span><span class="sxs-lookup"><span data-stu-id="39540-122">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
    
4. <span data-ttu-id="39540-123">パートナーが既に存在する場合は、チェックアウトウィザードの2番目の手順で、右側のウィンドウの [パートナー情報] の下にある [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-123">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>

5. <span data-ttu-id="39540-p107">追加するパートナーの Microsoft パートナー ID を入力します。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="39540-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

6. <span data-ttu-id="39540-126">ウィザードの残りの手順を完了してサブスクリプションの購入を終了します。</span><span class="sxs-lookup"><span data-stu-id="39540-126">Complete the rest of the wizard to finish buying your subscriptions.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="39540-127">購入時にパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="39540-127">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="39540-128">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=848041)で、[**請求** \> **書購入サービス**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-128">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
    
2. <span data-ttu-id="39540-129">購入する製品を選択し、[**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-129">Select the product you want to purchase, and then select **Buy**.</span></span>
  
3. <span data-ttu-id="39540-130">新しいパートナーを追加するには、[**注文に関するヘルプが必要ですか?** ] をクリックし、[ **Microsoft パートナーからサポートを受ける**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-130">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="39540-131">[プロバイダー] ページの手順に従って、を検索するか、パートナーとの照合を行います。</span><span class="sxs-lookup"><span data-stu-id="39540-131">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
    
4. <span data-ttu-id="39540-132">パートナーが既に存在する場合は、チェックアウトウィザードの2番目の手順で、右側のウィンドウの [パートナー情報] の下にある [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-132">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>

5. <span data-ttu-id="39540-p108">追加するパートナーの Microsoft パートナー ID を入力します。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="39540-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

6. <span data-ttu-id="39540-135">ウィザードの残りの手順を完了してサブスクリプションの購入を終了します。</span><span class="sxs-lookup"><span data-stu-id="39540-135">Complete the rest of the wizard to finish buying your subscriptions.</span></span> 
    
::: moniker-end


## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="39540-136">既存のサブスクリプションにパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="39540-136">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="39540-137">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-137">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
    
2. <span data-ttu-id="39540-138">複数のサブスクリプションを持っている場合は、編集するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-138">If you have more than one subscription, select the subscription you want to edit.</span></span>
  
3. <span data-ttu-id="39540-139">[サブスクリプション] ページで、[**パートナー** ] タブを選択し、追加するパートナーのパートナーネットワーク id を入力します。パートナーのパートナーの id を取得するには、パートナーに依頼します。</span><span class="sxs-lookup"><span data-stu-id="39540-139">On the subscription page, select the **Partner** tab, and then type the Partner Network ID for the partner you're adding You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
    
4. <span data-ttu-id="39540-140">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-140">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="39540-141">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-141">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
    
2. <span data-ttu-id="39540-142">複数のサブスクリプションを持っている場合は、編集するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-142">If you have more than one subscription, select the subscription you want to edit.</span></span>
  
3. <span data-ttu-id="39540-143">右側の [サブスクリプションコスト] で、[**その他のアクション**] [ > **レコードのパートナーを追加**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-143">On the right, under the subscription cost, choose **More actions** > **Add partner of record**.</span></span>

4. <span data-ttu-id="39540-p109">追加するパートナーの Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="39540-p109">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

5. <span data-ttu-id="39540-146">パートナー ID が [ **サブスクリプション**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="39540-146">The partner ID displays on the **Subscriptions** page.</span></span>
    
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="39540-147">このプロセスは、認定パートナーによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="39540-147">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="39540-148">パートナーから電子メールが送信され、レコードのパートナーとして機能するためのアクセス許可を付与する必要があるかどうかを尋ねられます。</span><span class="sxs-lookup"><span data-stu-id="39540-148">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span> 
  
<span data-ttu-id="39540-149">このオファーを承諾するには</span><span class="sxs-lookup"><span data-stu-id="39540-149">To accept this offer</span></span>
  
1. <span data-ttu-id="39540-150">電子メール内のパートナーの用語を読んでください。</span><span class="sxs-lookup"><span data-stu-id="39540-150">Read the partner's terms in the email.</span></span>
    
2. <span data-ttu-id="39540-151">契約を承認するには、Office 365 の認証ページに移行するリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-151">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
    
3. <span data-ttu-id="39540-152">[**パートナー関係**] で、[**はい]** を選択してパートナーが代理管理者になることを承認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39540-152">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
    
4. <span data-ttu-id="39540-153">パートナー関係のオファーに試用版サブスクリプションまたは購入提案が付属していた場合は、試用版またはサブスクリプション版のアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="39540-153">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>
    
::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="39540-154">サブスクリプションのパートナーを変更する</span><span class="sxs-lookup"><span data-stu-id="39540-154">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="39540-155">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-155">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
    
2. <span data-ttu-id="39540-156">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-156">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="39540-157">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-157">Under the **Partner ID**, select **Edit partner of record**.</span></span>
  
4. <span data-ttu-id="39540-p111">追加するパートナーの新しい Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="39540-p111">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="39540-160">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-160">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
  
2. <span data-ttu-id="39540-161">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-161">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="39540-162">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-162">Under the **Partner ID**, select **Edit partner of record**.</span></span>
  
4. <span data-ttu-id="39540-p112">追加するパートナーの新しい Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="39540-p112">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>   

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="39540-165">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-165">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>
  
2. <span data-ttu-id="39540-166">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-166">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="39540-167">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-167">Under the **Partner ID**, select **Edit partner of record**.</span></span>
  
4. <span data-ttu-id="39540-p113">追加するパートナーの新しい Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="39540-p113">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>   

::: moniker-end


## <a name="view-your-partner-relationships"></a><span data-ttu-id="39540-170">パートナー リレーションシップを表示する</span><span class="sxs-lookup"><span data-stu-id="39540-170">View your partner relationships</span></span>

- <span data-ttu-id="39540-171">管理センターで、[ **Settings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">パートナー関係</a>の設定] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-171">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="39540-172">パートナーがこのページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="39540-172">Your partners are listed on this page.</span></span> 
  
  <span data-ttu-id="39540-173">パートナーがいない場合は、「何も存在しません」というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39540-173">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="39540-174">サブスクリプションからパートナーを削除する</span><span class="sxs-lookup"><span data-stu-id="39540-174">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

1.  <span data-ttu-id="39540-175">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-175">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
    
2. <span data-ttu-id="39540-176">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-176">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="39540-177">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-177">Under the **Partner ID**, select **Edit partner of record**.</span></span>
    
6. <span data-ttu-id="39540-178">[ **パートナー情報**] ページの [ **パートナー ID**] チェック ボックスをオフにし、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39540-178">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="39540-179">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-179">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="39540-180">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-180">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="39540-181">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-181">Under the **Partner ID**, select **Edit partner of record**.</span></span>
    
6. <span data-ttu-id="39540-182">[ **パートナー情報**] ページの [ **パートナー ID**] チェック ボックスをオフにし、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39540-182">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="39540-183">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="39540-183">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="39540-184">サブスクリプションが複数ある場合は、編集するサブスクリプションの名前を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-184">If you have multiple subscriptions, select the name of the subscription you want to edit.</span></span>
    
3. <span data-ttu-id="39540-185">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="39540-185">Under the **Partner ID**, select **Edit partner of record**.</span></span>
    
6. <span data-ttu-id="39540-186">[ **パートナー情報**] ページの [ **パートナー ID**] チェック ボックスをオフにし、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39540-186">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>

::: moniker-end

  
## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="39540-187">再販業者関係を削除する</span><span class="sxs-lookup"><span data-stu-id="39540-187">Remove a reseller relationship</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="39540-188">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="39540-188">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="39540-189">再販業者の関係を削除している場合、[ **削除** ] オプションが淡色表示されるため、再販業者パートナーに依頼して次の手順に従う必要があります。 [顧客との再販業者関係の削除](https://docs.microsoft.com/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="39540-189">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](https://docs.microsoft.com/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="39540-190">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="39540-190">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="39540-191">再販業者の関係を削除している場合、[ **削除** ] オプションが淡色表示されるため、再販業者パートナーに依頼して次の手順に従う必要があります。 [顧客との再販業者関係の削除](https://docs.microsoft.com/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="39540-191">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](https://docs.microsoft.com/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="39540-192">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="39540-192">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="39540-193">再販業者の関係を削除している場合、[ **削除** ] オプションが淡色表示されるため、再販業者パートナーに依頼して次の手順に従う必要があります。 [顧客との再販業者関係の削除](https://docs.microsoft.com/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="39540-193">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](https://docs.microsoft.com/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="39540-194">関連記事</span><span class="sxs-lookup"><span data-stu-id="39540-194">Related articles</span></span>

[<span data-ttu-id="39540-195">Microsoft 365 パートナーまたは販売店を検索する</span><span class="sxs-lookup"><span data-stu-id="39540-195">Find your Microsoft 365 partner or reseller</span></span>](../manage/find-your-partner-or-reseller.md)
