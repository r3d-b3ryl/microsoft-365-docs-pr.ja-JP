---
title: Microsoft Viva Topics のトピック センターでトピックを管理する
description: トピック センターでトピックを管理する方法。
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: e2cbf62339e2ade240474fed9db86e68dc0b3bb4
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760124"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="cef40-103">Microsoft Viva Topics のトピック センターでトピックを管理する</span><span class="sxs-lookup"><span data-stu-id="cef40-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="cef40-104">Viva Topics トピック センターでは、ナレッジ マネージャーが[トピックの管理] ページを表示して、ナレッジ管理者が指定した SharePoint ソースの場所で特定されたトピックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![トピック センター](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="cef40-106">ナレッジ マネージャーは、トピックが次のトピックのライフサイクルを通じて、検出されたトピックをガイドするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cef40-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="cef40-107">**推奨 :** トピックは AI によって識別され、十分なサポート リソース、接続、およびプロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="cef40-107">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="cef40-108">**確認** 済み: AI によって提案されたトピックが検証されます。</span><span class="sxs-lookup"><span data-stu-id="cef40-108">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="cef40-109">検証は、ナレッジ マネージャーからの確認によって行われます。</span><span class="sxs-lookup"><span data-stu-id="cef40-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="cef40-110">さらに、少なくとも 2 人のユーザーがトピック カードに関するフィードバックの質問を通じて肯定的なフィードバックを与える場合は、トピックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="cef40-111">**発行** 済み : 確認済みトピックで、品質を向上させるために手動で編集が行われた。</span><span class="sxs-lookup"><span data-stu-id="cef40-111">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="cef40-112">**削除**: トピックはナレッジ マネージャーによって拒否され、閲覧者には表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cef40-112">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="cef40-113">トピックは、削除 (推奨、確認、または公開) を行う場合、任意の状態にできます。</span><span class="sxs-lookup"><span data-stu-id="cef40-113">The topic can be in any state when it is removed (suggested, confirmed, or published).</span></span> <span data-ttu-id="cef40-114">発行済みトピックを削除すると、キュアされた詳細を含むページは、トピック センターのページ ライブラリを使用して手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef40-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![トピック ライフサイクル グラフ](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="cef40-116">[トピックの管理] ページでは、各ナレッジ マネージャーは、トピックのファイルとページにアクセスできるトピックのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-116">On the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="cef40-117">これは、[提案済み]、[確認済み]、[削除済み]、および [発行済み] の各タブに表示される **トピックに\*\*\*\*反映** されます。</span><span class="sxs-lookup"><span data-stu-id="cef40-117">This will be reflected in the topics that are listed under the **Suggested**, **Confirmed**, **Removed**, and **Published** tabs.</span></span> <span data-ttu-id="cef40-118">ただし、このトピックの数は、組織内の合計カウントを示します。</span><span class="sxs-lookup"><span data-stu-id="cef40-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="cef40-119">要件</span><span class="sxs-lookup"><span data-stu-id="cef40-119">Requirements</span></span>

<span data-ttu-id="cef40-120">トピック センターでトピックを管理するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef40-120">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="cef40-121">Viva Topics ライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="cef40-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="cef40-122">[トピックを [**管理できるユーザー] 権限を持**](./topic-experiences-user-permissions.md) つ。</span><span class="sxs-lookup"><span data-stu-id="cef40-122">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="cef40-123">ナレッジ管理者は、ビバ トピックのアクセス許可設定でユーザーにこのアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="cef40-124">トピックを管理できるユーザー権限がない限り、トピック センターの [トピックの管理] ページ **を表示** することはできません。</span><span class="sxs-lookup"><span data-stu-id="cef40-124">You will not be able to view the Manage Topics page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="cef40-125">トピック センターでは、ナレッジ マネージャーは、指定した SharePoint ソースの場所で特定されたトピックを確認し、確認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="cef40-126">ナレッジ マネージャーは、トピックの検出で新しいトピック ページが見つからない場合は新しいトピック ページを作成して発行したり、更新する必要がある場合は既存のトピック ページを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="cef40-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="cef40-127">推奨されるトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="cef40-127">Review suggested topics</span></span>

<span data-ttu-id="cef40-128">トピック センターの [トピックの管理] ページで、指定した SharePoint ソースの場所で検出されたトピックが [提案] タブ **に表示** されます。必要に応じて、ナレッジ マネージャーは未確認のトピックを確認し、確認または拒否を選択できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-128">On the topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![推奨されるトピック](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="cef40-130">提案されたトピックを確認するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="cef40-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="cef40-131">[トピックの **管理]** ページで、[提案] タブ **を** 選択し、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="cef40-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="cef40-132">トピック ページで、トピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cef40-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="cef40-133">編集内容を公開すると、このトピックは [発行済み] タブ **に移動** されます。</span><span class="sxs-lookup"><span data-stu-id="cef40-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="cef40-134">トピックを確認した後、[トピックの管理] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="cef40-134">After reviewing the topic, go back to the Manage Topics page.</span></span> <span data-ttu-id="cef40-135">選択したトピックでは、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="cef40-136">チェック マークを選択してトピックを確認します。</span><span class="sxs-lookup"><span data-stu-id="cef40-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="cef40-137">トピックを **拒否する場合は、x** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cef40-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="cef40-138">確認済みトピックは提案リスト **から削除** され、確認済みリストに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="cef40-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="cef40-139">拒否されたトピックは提案リスト **から削除** され、[削除] タブに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="cef40-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="cef40-140">品質スコア</span><span class="sxs-lookup"><span data-stu-id="cef40-140">Quality score</span></span>

<span data-ttu-id="cef40-141">[推奨トピック] ページに表示される各トピックには、品質スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cef40-141">Each topic that appears on your Suggested Topics page has a quality score assigned to it.</span></span> <span data-ttu-id="cef40-142">品質スコアは、平均的なユーザーがトピックに関する情報に対して表示する情報の量を反映しています。各ユーザーは、トピック内の情報に対するアクセス許可または権限が付与されていない可能性があるという理由で、多かれ少なかれ情報を表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cef40-142">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="cef40-143">品質スコアは、最も多くの情報を含むトピックに関する洞察を得るのに役立ち、手動で編集する必要があるトピックを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cef40-143">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="cef40-144">たとえば、品質スコアが低いトピックは、一部のユーザーがトピックに含まれているファイルやサイトに関連付ける SharePoint アクセス許可を持たない場合です。</span><span class="sxs-lookup"><span data-stu-id="cef40-144">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="cef40-145">その後、投稿者はトピックを編集して(必要に応じて)情報を含め、トピックを表示できるすべてのユーザーに表示できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="cef40-146">品質スコアの範囲は 1 ~ 100 です。</span><span class="sxs-lookup"><span data-stu-id="cef40-146">The quality score could range from 1 to 100.</span></span> <span data-ttu-id="cef40-147">新しく検出されたトピックの品質スコアは、2 人以上のユーザーが表示するまで 0 です。</span><span class="sxs-lookup"><span data-stu-id="cef40-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="cef40-148">各ユーザーの品質スコアは、特定のユーザーに対して表示されるコンテンツの量など、AI によって生成されるコンテンツに対するセキュリティ トリミングが各トピック ページで行う際にユーザーのアクセス許可を制御されるなど、多くの要因によって決まります。</span><span class="sxs-lookup"><span data-stu-id="cef40-148">Each user's quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="cef40-149">[推奨されるトピック] タブに表示 **される** 品質スコアは、各ユーザーの個々のスコアの平均です。</span><span class="sxs-lookup"><span data-stu-id="cef40-149">The quality score shown on the **Suggested** topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="cef40-150">インプレッション数</span><span class="sxs-lookup"><span data-stu-id="cef40-150">Impressions</span></span>

<span data-ttu-id="cef40-151">[ **インプレッション数]** 列には、トピックがエンド ユーザーに表示された回数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cef40-151">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="cef40-152">これには、検索のトピック カード、トピックのハイライト、トピック センター ビューを通じたビューが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cef40-152">This includes views through topic cards in search, through topic highlights, and through topic center views.</span></span> <span data-ttu-id="cef40-153">これらのトピックのクリックスルーは反映されませんが、トピックが表示されています。</span><span class="sxs-lookup"><span data-stu-id="cef40-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="cef40-154">[**インプレッション] 列** には、[トピックの管理] ページの [提案済み]、[確認済み **]、[発行** 済み]、および **[** 削除済み] タブのトピックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cef40-154">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the Manage Topics page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="cef40-155">確認済みトピック</span><span class="sxs-lookup"><span data-stu-id="cef40-155">Confirmed topics</span></span>

<span data-ttu-id="cef40-156">[トピックの管理] ページで、指定した SharePoint ソースの場所で検出され、カード フィードバック メカニズムを介して 2 人以上が確認したナレッジ マネージャーまたは "クラウドソース"によって確認されたトピックが [確認済み] タブに一覧表示されます。必要に応じて、トピックを管理する権限を持つユーザーは、確認済みトピックを確認し、拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="cef40-156">On the Manage Topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="cef40-157">確認済みトピックを確認するには、次の項目を使用します。</span><span class="sxs-lookup"><span data-stu-id="cef40-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="cef40-158">[確認済 **み]** タブで、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="cef40-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="cef40-159">トピック ページで、トピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cef40-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="cef40-160">確認済みトピックを拒否することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="cef40-160">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="cef40-161">これを行うには、[確認済み] タブで選択したトピックに移動し、トピックを拒否する場合は **x** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cef40-161">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="cef40-162">発行済みトピック</span><span class="sxs-lookup"><span data-stu-id="cef40-162">Published topics</span></span>
<span data-ttu-id="cef40-163">公開されたトピックは編集され、特定の情報がページに遭遇したユーザーに常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cef40-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="cef40-164">手動で作成したトピックもここに示します。</span><span class="sxs-lookup"><span data-stu-id="cef40-164">Manually created topics are listed here as well.</span></span>

   ![トピックの管理](../media/knowledge-management/manage-topics-new.png) </br>