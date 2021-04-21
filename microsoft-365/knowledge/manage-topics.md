---
title: Microsoft Viva Topics のトピック センターでトピックを管理する
description: トピック センターでトピックを管理する方法。
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 4532f5685fdde7c89ca59e5c22e1ad8afdf2b112
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904036"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="d8411-103">Microsoft Viva Topics のトピック センターでトピックを管理する</span><span class="sxs-lookup"><span data-stu-id="d8411-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="d8411-104">ビバ トピック センターでは、ナレッジ マネージャーが[トピックの管理] ページを表示して、ナレッジ管理者が指定したソースの場所で特定されたトピックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![トピック センター](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="d8411-106">ナレッジ マネージャーは、さまざまなトピック ライフサイクル ステージを通じて、検出されたトピックをガイドするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8411-106">Knowledge managers help to guide discovered topics through the various topic lifecycle stages:</span></span>

- <span data-ttu-id="d8411-107">**推奨 :** トピックは AI によって識別され、十分なサポート リソース、接続、およびプロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="d8411-107">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="d8411-108">**確認** 済み: AI によって提案されたトピックが検証されます。</span><span class="sxs-lookup"><span data-stu-id="d8411-108">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="d8411-109">検証は、ナレッジ マネージャーからの確認によって行われます。</span><span class="sxs-lookup"><span data-stu-id="d8411-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="d8411-110">さらに、トピック カードのフィードバック メカニズムを介してエンド ユーザーから正の正の 2 票が届く場合は、トピックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-110">Additionally, a topic can be confirmed if there is a net positive 2 votes from end users received via the feedback mechanisms on the topic card.</span></span>
- <span data-ttu-id="d8411-111">**発行** 済み : 確認済みトピックで、品質を向上させるために手動で編集が行われた。</span><span class="sxs-lookup"><span data-stu-id="d8411-111">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="d8411-112">**削除**: トピックはナレッジ マネージャーによって拒否され、閲覧者には表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d8411-112">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="d8411-113">トピックは、削除 (推奨、確認、または公開) を行う場合、任意の状態にできます。</span><span class="sxs-lookup"><span data-stu-id="d8411-113">The topic can be in any state when it is removed (suggested, confirmed, or published).</span></span> <span data-ttu-id="d8411-114">発行済みトピックを削除すると、キュアされた詳細を含むページは、トピック センターのページ ライブラリを使用して手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8411-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![トピック ライフサイクル グラフ](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="d8411-116">[トピックの管理] ページでは、各ナレッジ マネージャーは、トピックに接続されている基になるファイルとページにアクセスできるトピックのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-116">On the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="d8411-117">このアクセス許可のトリミングは、[提案済み]、[確認済み]、[削除済み]、および [発行済み] タブに表示されるトピックの一 **覧に\*\*\*\*反映** されます。 </span><span class="sxs-lookup"><span data-stu-id="d8411-117">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Removed**, and **Published** tabs.</span></span> <span data-ttu-id="d8411-118">ただし、このトピックでは、アクセス許可に関係なく、組織内の合計カウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8411-118">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8411-119">要件</span><span class="sxs-lookup"><span data-stu-id="d8411-119">Requirements</span></span>

<span data-ttu-id="d8411-120">トピック センターでトピックを管理するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8411-120">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="d8411-121">Viva Topics ライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="d8411-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="d8411-122">[トピックを [**管理できるユーザー] 権限を持**](./topic-experiences-user-permissions.md) つ。</span><span class="sxs-lookup"><span data-stu-id="d8411-122">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="d8411-123">ナレッジ管理者は、ビバ トピックのアクセス許可設定でユーザーにこのアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="d8411-124">トピックを管理できるユーザー権限がない限り、トピック センターの [トピックの管理] ページ **を表示** することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8411-124">You will not be able to view the Manage Topics page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="d8411-125">トピック センターでは、ナレッジ マネージャーは、指定したソースの場所で特定されたトピックを確認し、確認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-125">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="d8411-126">ナレッジ マネージャーは、トピックの検出で新しいトピック ページが見つからない場合は新しいトピック ページを作成して発行したり、更新する必要がある場合は既存のトピック ページを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8411-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="d8411-127">推奨されるトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="d8411-127">Review suggested topics</span></span>

<span data-ttu-id="d8411-128">トピック センターの [トピックの管理] ページで、指定した SharePoint ソースの場所で検出されたトピックが [提案] タブ **に表示** されます。必要に応じて、ナレッジ マネージャーは未確認のトピックを確認し、確認または拒否を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-128">On the topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![推奨されるトピック](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="d8411-130">提案されたトピックを確認するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8411-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="d8411-131">[トピックの **管理]** ページで、[提案] タブ **を** 選択し、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d8411-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="d8411-132">トピック ページで、トピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8411-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="d8411-133">編集内容を公開すると、このトピックは [発行済み] タブ **に移動** されます。</span><span class="sxs-lookup"><span data-stu-id="d8411-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="d8411-134">トピックを確認した後、[トピックの管理] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d8411-134">After reviewing the topic, go back to the Manage Topics page.</span></span> <span data-ttu-id="d8411-135">選択したトピックでは、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="d8411-136">チェック マークを選択してトピックを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8411-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="d8411-137">トピックを **拒否する場合は、x** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8411-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="d8411-138">確認済みトピックは提案リスト **から削除** され、確認済みリストに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d8411-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="d8411-139">拒否されたトピックは提案リスト **から削除** され、[削除] タブに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d8411-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="d8411-140">品質スコア</span><span class="sxs-lookup"><span data-stu-id="d8411-140">Quality score</span></span>

<span data-ttu-id="d8411-141">[推奨トピック] ページに表示される各トピックには、品質スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d8411-141">Each topic that appears on your Suggested Topics page has a quality score assigned to it.</span></span> <span data-ttu-id="d8411-142">品質スコアは、平均的なユーザーがトピックに関する情報に対して表示する情報の量を反映しています。各ユーザーは、トピック内の情報に対するアクセス許可または権限が付与されていない可能性があるという理由で、多かれ少なかれ情報を表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8411-142">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="d8411-143">品質スコアは、最も多くの情報を含むトピックに関する洞察を得るのに役立ち、手動で編集する必要があるトピックを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8411-143">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="d8411-144">たとえば、品質スコアが低いトピックは、一部のユーザーがトピックに含まれているファイルやサイトに関連付ける SharePoint アクセス許可を持たない場合です。</span><span class="sxs-lookup"><span data-stu-id="d8411-144">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="d8411-145">その後、投稿者はトピックを編集して(必要に応じて)情報を含め、トピックを表示できるすべてのユーザーに表示できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="d8411-146">インプレッション数</span><span class="sxs-lookup"><span data-stu-id="d8411-146">Impressions</span></span>

<span data-ttu-id="d8411-147">[ **インプレッション数]** 列には、トピックがエンド ユーザーに表示された回数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8411-147">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="d8411-148">これには、検索のトピック回答カードやトピックのハイライトを通じたビューが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8411-148">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="d8411-149">これらのトピックのクリックスルーは反映されませんが、トピックが表示されています。</span><span class="sxs-lookup"><span data-stu-id="d8411-149">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="d8411-150">[**インプレッション] 列** には、[トピックの管理] ページの [提案済み]、[確認済み **]、[発行** 済み]、および **[** 削除済み] タブのトピックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8411-150">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the Manage Topics page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="d8411-151">確認済みトピック</span><span class="sxs-lookup"><span data-stu-id="d8411-151">Confirmed topics</span></span>

<span data-ttu-id="d8411-152">[トピックの管理] ページで、指定した SharePoint ソースの場所で検出され、カード フィードバック メカニズムを介して、2 人以上のネットで確認されたナレッジ マネージャーまたは "クラウドソース" によって確認されたトピック (否定的なユーザー投票と肯定的なユーザー投票のバランスを取る) が[確認済み] タブに表示されます。必要に応じて、トピックを管理する権限を持つユーザーは、確認済みトピックを確認し、拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="d8411-152">On the Manage Topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="d8411-153">確認済みトピックを確認するには、次の項目を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8411-153">To review a confirmed topic:</span></span>

1. <span data-ttu-id="d8411-154">[確認済 **み]** タブで、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d8411-154">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="d8411-155">トピック ページで、トピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8411-155">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="d8411-156">確認済みトピックを拒否することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8411-156">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="d8411-157">これを行うには、[確認済み] タブで選択したトピックに移動し、トピックを拒否する場合は **x** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8411-157">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="d8411-158">発行済みトピック</span><span class="sxs-lookup"><span data-stu-id="d8411-158">Published topics</span></span>
<span data-ttu-id="d8411-159">公開されたトピックは編集され、特定の情報がページに遭遇したユーザーに常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8411-159">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="d8411-160">手動で作成したトピックもここに示します。</span><span class="sxs-lookup"><span data-stu-id="d8411-160">Manually created topics are listed here as well.</span></span>

   ![トピックの管理](../media/knowledge-management/manage-topics-new.png) </br>
