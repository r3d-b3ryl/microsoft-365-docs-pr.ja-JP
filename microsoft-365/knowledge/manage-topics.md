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
ms.openlocfilehash: f2429b0ffdd4a238bc9322ae9199eebbbfd407b5
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651161"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="20216-103">Microsoft Viva Topics のトピック センターでトピックを管理する</span><span class="sxs-lookup"><span data-stu-id="20216-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="20216-104">ビバ トピック センターでは、ナレッジ マネージャーが[トピックの管理] ページを表示して、ナレッジ管理者が指定したソースの場所で特定されたトピックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="20216-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![トピック センター](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="20216-106">トピック ステージ</span><span class="sxs-lookup"><span data-stu-id="20216-106">Topic stages</span></span>

<span data-ttu-id="20216-107">ナレッジ マネージャーは、さまざまなトピック ライフサイクル ステージ (推奨、確認済み、発行済み、削除済 **み)** を通じて、検出されたトピックをガイド **するのに役立ちます**。</span><span class="sxs-lookup"><span data-stu-id="20216-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![トピック ライフサイクル グラフ](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="20216-109">**提案済み**: AI によって特定されたトピックであり、十分な裏付けとなるリソース、コネクション、プロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="20216-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="20216-110">(これらは、UI で **推奨トピック** としてマークされます)。</span><span class="sxs-lookup"><span data-stu-id="20216-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="20216-111">**確認** 済み: AI によって検出され、検証されたトピック。</span><span class="sxs-lookup"><span data-stu-id="20216-111">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="20216-112">トピックの検証は、次のいずれかの場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="20216-112">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="20216-113">ナレッジ マネージャーがトピックを確認します。</span><span class="sxs-lookup"><span data-stu-id="20216-113">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="20216-114">ナレッジ マネージャーは [、[トピックの管理] ページ](manage-topics.md#confirmed-topics) で **トピックを確認** します。</span><span class="sxs-lookup"><span data-stu-id="20216-114">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="20216-115">複数のユーザーがトピックを確認します。</span><span class="sxs-lookup"><span data-stu-id="20216-115">Multiple users confirm a topic.</span></span> <span data-ttu-id="20216-116">トピック カードのフィードバック メカニズムを使用して投票したユーザーから受け取った 2 つの肯定的な投票のネットが必要です。</span><span class="sxs-lookup"><span data-stu-id="20216-116">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="20216-117">たとえば、1 人のユーザーが肯定的に投票し、1 人のユーザーが特定のトピックに対して否定的な投票を行った場合でも、そのトピックを確認するには、さらに 2 つの肯定的な投票が必要になります。</span><span class="sxs-lookup"><span data-stu-id="20216-117">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="20216-118">**発行** 済み : キュアされたトピック。</span><span class="sxs-lookup"><span data-stu-id="20216-118">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="20216-119">品質を向上させるために手動で編集が行われたか、ユーザーによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="20216-119">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="20216-120">**削除**: 拒否され、閲覧者に表示されなくなったトピック。</span><span class="sxs-lookup"><span data-stu-id="20216-120">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="20216-121">トピックは、任意の状態 (推奨、確認、または公開) で削除できます。</span><span class="sxs-lookup"><span data-stu-id="20216-121">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="20216-122">トピックの削除は、次のいずれかの場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="20216-122">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="20216-123">ナレッジ マネージャーがトピックを削除します。</span><span class="sxs-lookup"><span data-stu-id="20216-123">A knowledge manager removes a topic.</span></span> <span data-ttu-id="20216-124">ナレッジ マネージャーは、[トピックの管理] ページで **トピックを削除** します。</span><span class="sxs-lookup"><span data-stu-id="20216-124">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="20216-125">トピック カードのフィードバック メカニズムを使用して、複数のユーザーが否定的な票を投じます。</span><span class="sxs-lookup"><span data-stu-id="20216-125">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="20216-126">トピックを削除するには、ユーザーから受け取った 2 つの負の投票の正味が必要です。</span><span class="sxs-lookup"><span data-stu-id="20216-126">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="20216-127">たとえば、1 人のユーザーが否定的な投票を行い、1 人のユーザーが特定のトピックに対して正の投票を行った場合でも、そのトピックを削除するには、さらに 2 つの否定的な投票が必要になります。</span><span class="sxs-lookup"><span data-stu-id="20216-127">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="20216-128">発行済みトピックを削除すると、キュアされた詳細を含むページは、トピック センターのページ ライブラリを使用して手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20216-128">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="20216-129">[トピック **の管理]** ページでは、各ナレッジ マネージャーは、トピックに接続されている基になるファイルとページにアクセスできるトピックのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="20216-129">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="20216-130">このアクセス許可のトリミングは、[提案済み]、[確認済み]、[発行済み]、および [削除済み] タブに表示されるトピックの一覧に **反映** されます。 </span><span class="sxs-lookup"><span data-stu-id="20216-130">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="20216-131">ただし、このトピックでは、アクセス許可に関係なく、組織内の合計カウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20216-131">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="20216-132">要件</span><span class="sxs-lookup"><span data-stu-id="20216-132">Requirements</span></span>

<span data-ttu-id="20216-133">トピック センターでトピックを管理するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="20216-133">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="20216-134">Viva トピック ライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="20216-134">Have a Viva Topics license.</span></span>

- <span data-ttu-id="20216-135">トピックのWho [**を管理する権限を持**](./topic-experiences-user-permissions.md)つ。</span><span class="sxs-lookup"><span data-stu-id="20216-135">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="20216-136">ナレッジ管理者は、Viva トピックでのトピックに関するアクセス許可の設定でユーザーにこのアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="20216-136">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="20216-137">トピックを管理できるユーザー権限がない限り、トピック センターの [トピックの管理]**ページWho表示** することはできません。</span><span class="sxs-lookup"><span data-stu-id="20216-137">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="20216-138">トピック センターでは、ナレッジ マネージャーは、指定したソースの場所で特定されたトピックを確認し、確認または削除できます。</span><span class="sxs-lookup"><span data-stu-id="20216-138">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="20216-139">ナレッジ マネージャーは、トピックの検出で新しいトピック ページが見つからない場合は新しいトピック ページを作成して発行したり、更新する必要がある場合は既存のトピック ページを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="20216-139">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="20216-140">推奨されるトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="20216-140">Review suggested topics</span></span>

<span data-ttu-id="20216-141">[トピック **の管理]** ページで、指定したソースの場所でSharePointされたトピックが [提案] タブ **に表示** されます。必要に応じて、ナレッジ マネージャーは未確認のトピックを確認し、確認または削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="20216-141">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![推奨されるトピック](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="20216-143">提案されたトピックを確認するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="20216-143">To review a suggested topic:</span></span>

1. <span data-ttu-id="20216-144">[トピックの **管理]** ページで、[提案] タブ **を** 選択し、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="20216-144">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="20216-145">トピック ページで、トピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20216-145">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="20216-146">編集内容を公開すると、このトピックは [発行済み] タブ **に移動** されます。</span><span class="sxs-lookup"><span data-stu-id="20216-146">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="20216-147">トピックを確認した後、[トピックの管理] **ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="20216-147">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="20216-148">選択したトピックについて、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="20216-148">For the selected topic, you can:</span></span>

   - <span data-ttu-id="20216-149">チェック マークを選択してトピックを承認します。</span><span class="sxs-lookup"><span data-stu-id="20216-149">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="20216-150">トピックを **削除する** 場合は、x を選択します。</span><span class="sxs-lookup"><span data-stu-id="20216-150">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="20216-151">確認済みトピックは提案リスト **から削除** され、確認済みリストに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="20216-151">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="20216-152">削除されたトピックは提案リスト **から削除** され、[削除] タブに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="20216-152">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="20216-153">品質スコア</span><span class="sxs-lookup"><span data-stu-id="20216-153">Quality score</span></span>

<span data-ttu-id="20216-154">[提案されたトピック] ページに表示 **される各** トピックには、品質スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="20216-154">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="20216-155">品質スコアは、平均的なユーザーがトピックに関する情報に対して表示する情報の量を反映しています。各ユーザーは、トピック内の情報に対するアクセス許可または権限が付与されていない可能性があるという理由で、多かれ少なかれ情報を表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20216-155">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="20216-156">品質スコアは、最も多くの情報を含むトピックに関する洞察を得るのに役立ち、手動で編集する必要があるトピックを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20216-156">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="20216-157">たとえば、品質スコアが低いトピックは、一部のユーザーがトピックに含まれているファイルまたはサイトに関連する SharePoint アクセス許可を持たない場合です。</span><span class="sxs-lookup"><span data-stu-id="20216-157">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="20216-158">投稿者はトピックを編集して情報を含めることができ (適切な場合)、その後そのトピックを閲覧可能なすべてのユーザーがトピックを閲覧できるようになります。</span><span class="sxs-lookup"><span data-stu-id="20216-158">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="20216-159">インプレッション</span><span class="sxs-lookup"><span data-stu-id="20216-159">Impressions</span></span>

<span data-ttu-id="20216-160">[ **インプレッション数]** 列には、トピックがエンド ユーザーに表示された回数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20216-160">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="20216-161">これには、検索のトピック回答カードやトピックのハイライトを通じたビューが含まれます。</span><span class="sxs-lookup"><span data-stu-id="20216-161">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="20216-162">これらのトピックのクリックスルーは反映されませんが、トピックが表示されています。</span><span class="sxs-lookup"><span data-stu-id="20216-162">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="20216-163">[**トピックの管理]** ページの [提案済み] タブ、[確認済み] タブ、[**発行** 済み] タブ、および [削除済み] タブにトピックの [インプレッション数]**列が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="20216-163">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="20216-164">承認済みトピック</span><span class="sxs-lookup"><span data-stu-id="20216-164">Confirmed topics</span></span>

<span data-ttu-id="20216-165">[トピックの管理] ページで、指定した SharePoint ソースの場所で検出され、2 人以上のネットで確認されたナレッジ マネージャーまたは "クラウドソース" によって確認されたトピック (負のユーザー投票と肯定的なユーザー投票のバランスを取る) が、カード フィードバック メカニズムを通じて [確認済み] タブに一覧表示されます。必要に応じて、トピックを管理する権限を持つユーザーは、確認済みトピックを確認し、拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="20216-165">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="20216-166">承認済みトピックを確認するには:</span><span class="sxs-lookup"><span data-stu-id="20216-166">To review a confirmed topic:</span></span>

1. <span data-ttu-id="20216-167">**[承認済み]** タブで、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="20216-167">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="20216-168">トピック ページで、トピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20216-168">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="20216-169">確認済みトピックを拒否することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="20216-169">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="20216-170">これを行うには、[確認済み] タブで選択したトピックに移動し、トピックを拒否する場合は **x** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20216-170">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="20216-171">公開済みトピック</span><span class="sxs-lookup"><span data-stu-id="20216-171">Published topics</span></span>

<span data-ttu-id="20216-172">公開されたトピックは編集され、特定の情報がページに遭遇したユーザーに常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="20216-172">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="20216-173">手動で作成したトピックもこちらに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="20216-173">Manually created topics are listed here as well.</span></span>

   ![トピックの管理](../media/knowledge-management/manage-topics-new.png)

## <a name="topic-count-dashboard"></a><span data-ttu-id="20216-175">トピック数ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="20216-175">Topic count dashboard</span></span>

<span data-ttu-id="20216-176">ダッシュボード ビューのこのグラフでは、Viva Topics トピック センターのトピック数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="20216-176">This chart in the dashboard view lets you see the number of topics in your Viva Topics topic center.</span></span> <span data-ttu-id="20216-177">このグラフには、トピックライフサイクルステージごとのトピック数が表示され、トピック数が時間の流れによってどのように推移したのかも示されています。</span><span class="sxs-lookup"><span data-stu-id="20216-177">The chart shows the topic counts per topic lifecycle stage and also shows how topic counts have trended over time.</span></span> <span data-ttu-id="20216-178">ナレッジ マネージャーは、AI によって新しいトピックが検出される速度と、ナレッジ マネージャーまたはユーザー アクションによってトピックが確認または公開される速度を視覚的に監視できます。</span><span class="sxs-lookup"><span data-stu-id="20216-178">Knowledge managers can visually monitor the rate at which new topics are being discovered by AI and the rate at which topics are getting confirmed or published by the knowledge manager or user actions.</span></span>

<span data-ttu-id="20216-179">ナレッジ マネージャーは、[トピックの管理] ページのトピックの一覧で表されるトピックの数がダッシュボードに表示される数とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="20216-179">Knowledge managers might see a different count of topics represented in the list of topics on the **Manage topics** page than they see in the dashboard.</span></span> <span data-ttu-id="20216-180">これは、ナレッジ マネージャーがすべてのトピックにアクセスできない可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="20216-180">This is because a knowledge manager might not have access to all topics.</span></span> <span data-ttu-id="20216-181">ダッシュボード ビューに表示されるカウントは、アクセス許可トリミングを適用する前に行います。</span><span class="sxs-lookup"><span data-stu-id="20216-181">The count presented in the dashboard view is taken before applying permission-trimming.</span></span> 

   ![トピック数ダッシュボードのスクリーンショット](../media/knowledge-management/topic-count-dashboard.png)
