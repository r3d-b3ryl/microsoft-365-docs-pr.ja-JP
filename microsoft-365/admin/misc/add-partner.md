---
title: サブスクリプション アドバイザー パートナーを追加、変更、または削除する
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: サブスクリプションからパートナーを購入、変更、またはMicrosoft 365の時点でレコードのパートナーを追加します。
ms.openlocfilehash: e21c324bc84e360b80deae2abeec610e73834819
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624527"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="67d66-103">サブスクリプション アドバイザー パートナーを追加、変更、または削除する</span><span class="sxs-lookup"><span data-stu-id="67d66-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="67d66-104">この記事は、中国Office 365 21Vianet が運営するサービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="67d66-104">This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="67d66-105">21Vianet パートナーが自分のサブスクリプションを管理Office 365組織向けです。</span><span class="sxs-lookup"><span data-stu-id="67d66-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="67d66-106">サブスクリプション アドバイザーとなっている Microsoft の認定パートナーは、サブスクリプションのセットアップと保守を行うために必要な販売、サポート、技術専門分野の知識を提供します。</span><span class="sxs-lookup"><span data-stu-id="67d66-106">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="67d66-107">サブスクリプション アドバイザー パートナーは、サブスクリプション を購入するときに、または別のMicrosoft 365パートナーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="67d66-107">You can add a subscription advisor partner as a partner of record when you purchase Microsoft 365 or at another time.</span></span> <span data-ttu-id="67d66-108">また、現在パートナーがいない場合は、[Microsoft Pinpoint](https://pinpoint.microsoft.com) の Web サイトで見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="67d66-108">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="67d66-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="67d66-109">Before you begin</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="67d66-110">選択するパートナーは、使用Microsoft サービスサービスを使用する国または地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="67d66-110">The partner you choose depends on the Microsoft services you use and the country or region where you'll use those services.</span></span> <span data-ttu-id="67d66-111">サブスクリプションのパートナーを追加、またはパートナーを変更する場合は、最初にパートナーの Microsoft Partner ID をパートナーにたずねて入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67d66-111">If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="67d66-p104">サブスクリプション アドバイザーとなっている Microsoft の認定パートナーは、サブスクリプションのセットアップと保守を行うために必要な販売、サポート、技術専門分野の知識を提供します。サブスクリプション アドバイザー パートナーは、Office 365 の購入時などに、レコードのパートナーとして追加できます。また、現在パートナーがいない場合は、[Microsoft Pinpoint](https://pinpoint.microsoft.com) の Web サイトで見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="67d66-p104">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription. You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time. If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="67d66-p105">選択するパートナーは、使用中の Office 365 サービス、およびサービスを使っている国または地域によって異なります。サブスクリプションのパートナーを追加、またはパートナーを変更する場合は、最初にパートナーの Microsoft Partner ID をパートナーにたずねて入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67d66-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="67d66-117">Office 365 の管理者は、ユーザーの作成または編集、ユーザー パスワードのリセット、ユーザー ライセンスの管理、ドメインの管理、組織内の他のユーザーへの管理者権限の割り当てなどの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="67d66-117">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="67d66-118">ただし、他のユーザーにこれらの管理タスクを実行する必要がある場合は、パートナー関係を作成して、この役割を 21Vianet の承認されたパートナーに委任できます。</span><span class="sxs-lookup"><span data-stu-id="67d66-118">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="67d66-119">購入時にパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="67d66-119">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="67d66-120">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="67d66-121">購入する製品を選択し、[購入] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-121">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="67d66-122">新しいパートナーを追加するには、[注文に関するサポート **が必要ですか?** ] を展開し **、[Microsoft パートナーからサポートを受ける] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-122">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="67d66-123">[プロバイダー] ページの手順に従って、パートナーを検索するか、パートナーと一致します。</span><span class="sxs-lookup"><span data-stu-id="67d66-123">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="67d66-124">パートナーが既にある場合は、チェックアウト ウィザードの 2 番目の手順で、右側のウィンドウの [パートナー情報] で、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-124">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="67d66-p107">追加するパートナーの Microsoft パートナー ID を入力します。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="67d66-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="67d66-127">ウィザードの残りの手順を完了してサブスクリプションの購入を終了します。</span><span class="sxs-lookup"><span data-stu-id="67d66-127">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="67d66-128">購入時にパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="67d66-128">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="67d66-129">管理センター [で、[](https://go.microsoft.com/fwlink/p/?linkid=848041)課金の購入サービス **]** \> **ページに移動**  します。</span><span class="sxs-lookup"><span data-stu-id="67d66-129">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
2. <span data-ttu-id="67d66-130">購入する製品を選択し、[購入] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-130">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="67d66-131">新しいパートナーを追加するには、[注文に関するサポート **が必要ですか?** ] を展開し **、[Microsoft パートナーからサポートを受ける] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-131">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="67d66-132">[プロバイダー] ページの手順に従って、パートナーを検索するか、パートナーと一致します。</span><span class="sxs-lookup"><span data-stu-id="67d66-132">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="67d66-133">パートナーが既にある場合は、チェックアウト ウィザードの 2 番目の手順で、右側のウィンドウの [パートナー情報] で、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-133">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="67d66-p108">追加するパートナーの Microsoft パートナー ID を入力します。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="67d66-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="67d66-136">ウィザードの残りの手順を完了してサブスクリプションの購入を終了します。</span><span class="sxs-lookup"><span data-stu-id="67d66-136">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="67d66-137">既存のサブスクリプションにパートナーを追加する</span><span class="sxs-lookup"><span data-stu-id="67d66-137">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="67d66-138">管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="67d66-139">[製品 **] タブ** で、編集するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-139">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="67d66-140">[サブスクリプションの詳細] ページの [パートナー情報] **で**、パートナー ネットワーク **ID を入力します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-140">On the subscription details page, under **Partner information**, type the **Partner Network ID**.</span></span> <span data-ttu-id="67d66-141">パートナーの Microsoft パートナー ネットワーク ID を取得するには、パートナーに確認を求める必要があります。</span><span class="sxs-lookup"><span data-stu-id="67d66-141">You can get the partner's Microsoft Partner Network ID by asking the partner for it.</span></span>
4. <span data-ttu-id="67d66-142">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-142">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="67d66-143">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-143">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="67d66-144">複数のサブスクリプションがある場合は、編集するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-144">If you have more than one subscription, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="67d66-145">右側のサブスクリプション コストの下で、[レコードのパートナーの追加] の 3 つの点 (>) を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-145">On the right, under the subscription cost, select the three dots (more actions) > **Add partner of record**.</span></span>
4. <span data-ttu-id="67d66-p110">追加するパートナーの Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="67d66-p110">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
5. <span data-ttu-id="67d66-148">パートナー ID が [ **サブスクリプション**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="67d66-148">The partner ID displays on the **Subscriptions** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="67d66-149">このプロセスは、承認されたパートナーによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="67d66-149">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="67d66-150">パートナーは、レコードのパートナーとして機能するアクセス許可を与える必要がある場合に、メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="67d66-150">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span>
  
<span data-ttu-id="67d66-151">このオファーを受け入れるには</span><span class="sxs-lookup"><span data-stu-id="67d66-151">To accept this offer</span></span>
  
1. <span data-ttu-id="67d66-152">メールでパートナーの用語を読む。</span><span class="sxs-lookup"><span data-stu-id="67d66-152">Read the partner's terms in the email.</span></span>
2. <span data-ttu-id="67d66-153">契約を承認するには、リンクを選択します。リンク先の承認ページに移動Office 365。</span><span class="sxs-lookup"><span data-stu-id="67d66-153">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
3. <span data-ttu-id="67d66-154">[ **パートナーの関係] で**、[ **は** い] を選択して、代理管理者としてパートナーを承認し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-154">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
4. <span data-ttu-id="67d66-155">パートナー関係のオファーに試用版サブスクリプションまたは購入オファーが含む場合は、試用版またはサブスクリプション アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="67d66-155">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>

::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="67d66-156">サブスクリプションのパートナーを変更する</span><span class="sxs-lookup"><span data-stu-id="67d66-156">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="67d66-157">管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-157">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="67d66-158">[サブスクリプションの詳細] ページの [パートナー情報] **で**、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-158">On the subscriptions details page, under **Partner information**, select **Remove**.</span></span>
3. <span data-ttu-id="67d66-159">新しい **パートナーの Microsoft パートナー ネットワーク ID** を入力します。</span><span class="sxs-lookup"><span data-stu-id="67d66-159">Type the **Microsoft Partner Network ID** for the new partner.</span></span> <span data-ttu-id="67d66-160">パートナーに Microsoft パートナー ID についてたずね、パートナー ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="67d66-160">You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
4. <span data-ttu-id="67d66-161">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-161">Select **Add**.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="67d66-162">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-162">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="67d66-163">複数のサブスクリプションがある場合は、編集するサブスクリプションの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-163">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="67d66-164">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67d66-164">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="67d66-p113">追加するパートナーの新しい Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="67d66-p113">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="67d66-167">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-167">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="67d66-168">複数のサブスクリプションがある場合は、編集するサブスクリプションの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-168">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="67d66-169">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67d66-169">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="67d66-p114">追加するパートナーの新しい Microsoft パートナー ID を入力し、[ **ID の確認**]、[ **送信**] の順に選びます。パートナーの Microsoft パートナー ID は、パートナーにたずねることで入手できます。</span><span class="sxs-lookup"><span data-stu-id="67d66-p114">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

## <a name="view-your-partner-relationships"></a><span data-ttu-id="67d66-172">パートナー リレーションシップを表示する</span><span class="sxs-lookup"><span data-stu-id="67d66-172">View your partner relationships</span></span>

- <span data-ttu-id="67d66-173">管理センターで、[パートナーの関係]**ページ設定**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="67d66-173">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="67d66-174">パートナーは、このページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="67d66-174">Your partners are listed on this page.</span></span>

  <span data-ttu-id="67d66-175">パートナーがいない場合は、「ここには何もありません」というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="67d66-175">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="67d66-176">サブスクリプションからパートナーを削除する</span><span class="sxs-lookup"><span data-stu-id="67d66-176">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="67d66-177">管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-177">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="67d66-178">[製品 **] タブ** で、編集するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-178">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="67d66-179">[サブスクリプションの詳細] ページの [パートナー情報] **で、[** 削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67d66-179">On the subscription details page, under **Partner information**, select **Remove**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="67d66-180">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-180">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="67d66-181">複数のサブスクリプションがある場合は、編集するサブスクリプションの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-181">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="67d66-182">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67d66-182">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="67d66-183">[ **パートナー情報**] ページの [ **パートナー ID**] チェック ボックスをオフにし、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67d66-183">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="67d66-184">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="67d66-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="67d66-185">複数のサブスクリプションがある場合は、編集するサブスクリプションの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="67d66-185">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="67d66-186">[ **パートナー ID**] の下で、[ **レコードのパートナーの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67d66-186">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="67d66-187">[ **パートナー情報**] ページの [ **パートナー ID**] チェック ボックスをオフにし、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67d66-187">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>

::: moniker-end

## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="67d66-188">再販業者関係を削除する</span><span class="sxs-lookup"><span data-stu-id="67d66-188">Remove a reseller relationship</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="67d66-189">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="67d66-189">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="67d66-190">再販業者の関係を削除している場合、[ **削除** ] オプションが淡色表示されるため、再販業者パートナーに依頼して次の手順に従う必要があります。 [顧客との再販業者関係の削除](/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="67d66-190">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="67d66-191">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="67d66-191">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="67d66-192">再販業者の関係を削除している場合、[ **削除** ] オプションが淡色表示されるため、再販業者パートナーに依頼して次の手順に従う必要があります。 [顧客との再販業者関係の削除](/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="67d66-192">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="67d66-193">再販業者関係を自分で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="67d66-193">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="67d66-194">次の手順に従ってリセラー パートナーに問い合わせする必要があります。 パートナーとのリセラー [関係を削除します](/partner-center/remove-a-relationship)。</span><span class="sxs-lookup"><span data-stu-id="67d66-194">You will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-content"></a><span data-ttu-id="67d66-195">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="67d66-195">Related content</span></span>

<span data-ttu-id="67d66-196">[パートナーまたはリセラー Microsoft 365探す](../manage/find-your-partner-or-reseller.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="67d66-196">[Find your Microsoft 365 partner or reseller](../manage/find-your-partner-or-reseller.md) (article)</span></span>\
<span data-ttu-id="67d66-197">[ビジネス向けMicrosoft 365のセットアップを計画](../setup/plan-your-setup.md)する (記事)</span><span class="sxs-lookup"><span data-stu-id="67d66-197">[Plan your setup of Microsoft 365 for business](../setup/plan-your-setup.md) (article)</span></span>