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
ms.openlocfilehash: 59581dce3701e622a1e2d7ed264370c9d92b3211
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327275"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="b9cbb-103">Microsoft Viva Topics のトピック センターでトピックを管理する</span><span class="sxs-lookup"><span data-stu-id="b9cbb-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="b9cbb-104">ビバ トピック センターでは、ナレッジ マネージャーが[トピックの管理] ページを表示して、ナレッジ管理者が指定したソースの場所で特定されたトピックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![トピック センター](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="b9cbb-106">トピック ステージ</span><span class="sxs-lookup"><span data-stu-id="b9cbb-106">Topic stages</span></span>

<span data-ttu-id="b9cbb-107">ナレッジ マネージャーは、さまざまなトピック ライフサイクル ステージ (推奨、確認済み、発行済み、削除済 **み)** を通じて、検出されたトピックをガイド **するのに役立ちます**。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![トピック ライフサイクル グラフ](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="b9cbb-109">**提案済み**: AI によって特定されたトピックであり、十分な裏付けとなるリソース、コネクション、プロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="b9cbb-110">(これらは、UI で **推奨トピック** としてマークされます)。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="b9cbb-111">**承認済み**: AI によって提案されたトピックが検証されました。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-111">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="b9cbb-112">トピックの検証は、ナレッジ マネージャーによって確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-112">Topic validation must be confirmed by a knowledge manager.</span></span> <span data-ttu-id="b9cbb-113">トピックを確認するには、トピック カードのフィードバック メカニズムを使用して投票したユーザーから受け取った 2 つの肯定的な票の正味が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-113">For a topic to be confirmed, there must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="b9cbb-114">たとえば、1 人のユーザーが肯定的に投票し、1 人のユーザーが特定のトピックに対して否定的な投票を行った場合でも、そのトピックを確認するには、さらに 2 つの肯定的な投票が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-114">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="b9cbb-115">**発行** 済み : 確認済みトピックで、品質を向上させるために手動で編集が行われた。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-115">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>

- <span data-ttu-id="b9cbb-116">**削除**: トピックはナレッジ マネージャーによって拒否され、閲覧者には表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-116">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="b9cbb-117">トピックは、任意の状態 (推奨、確認、または公開) で削除できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-117">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="b9cbb-118">トピックを削除するには、トピック カードのフィードバック メカニズムを使用して投票したユーザーから受け取った 2 つの負の投票の正味が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-118">For a topic to be removed, there must be a net of two negative votes received from users who voted using the feedback mechanisms on the topic card.</span></span> <span data-ttu-id="b9cbb-119">たとえば、1 人のユーザーが否定的な投票を行い、1 人のユーザーが特定のトピックに対して正の投票を行った場合でも、そのトピックを削除するには、さらに 2 つの否定的な投票が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-119">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span> <span data-ttu-id="b9cbb-120">発行済みトピックを削除すると、キュアされた詳細を含むページは、トピック センターのページ ライブラリを使用して手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-120">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

<span data-ttu-id="b9cbb-121">[トピック **の管理]** ページで、ナレッジ マネージャーは、トピックがユーザー投票によって確認されたか削除されたか、または特定のユーザーによって確認されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-121">On the **Manage topics** page, a knowledge manager can see whether a topic was confirmed or removed by user votes or by a specific person.</span></span> <span data-ttu-id="b9cbb-122">たとえば、ユーザー投票によって削除されたトピックの場合、その理由は [削除者] 列に、ユーザー名ではなくユーザー投票として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-122">For example, for topics removed by user votes, the reason is shown in the **Removed by** column as **User votes** rather than a person's name.</span></span> 

   ![[トピックの管理] ページのスクリーンショットで、削除されたトピックリストが表示され、ユーザー投票が強調表示されます。](../media/knowledge-management/removed-topics-user-votes.png) 

> [!Note] 
> <span data-ttu-id="b9cbb-124">[トピック **の管理]** ページでは、各ナレッジ マネージャーは、トピックに接続されている基になるファイルとページにアクセスできるトピックのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-124">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="b9cbb-125">このアクセス許可のトリミングは、[提案済み]、[確認済み]、[発行済み]、および [削除済み] タブに表示されるトピックの一覧に **反映** されます。 </span><span class="sxs-lookup"><span data-stu-id="b9cbb-125">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="b9cbb-126">ただし、このトピックでは、アクセス許可に関係なく、組織内の合計カウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-126">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9cbb-127">要件</span><span class="sxs-lookup"><span data-stu-id="b9cbb-127">Requirements</span></span>

<span data-ttu-id="b9cbb-128">トピック センターでトピックを管理するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-128">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="b9cbb-129">Viva トピック ライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-129">Have a Viva Topics license.</span></span>

- <span data-ttu-id="b9cbb-130">[トピックを [**管理できるユーザー] 権限を持**](./topic-experiences-user-permissions.md) つ。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-130">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="b9cbb-131">ナレッジ管理者は、Viva トピックでのトピックに関するアクセス許可の設定でユーザーにこのアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-131">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="b9cbb-132">トピックを管理できるユーザー権限がない限り、トピック センターの [トピックの管理] ページ **を表示** することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-132">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="b9cbb-133">トピック センターでは、ナレッジ マネージャーは、指定したソースの場所で特定されたトピックを確認し、確認または削除できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-133">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="b9cbb-134">ナレッジ マネージャーは、トピックの検出で新しいトピック ページが見つからない場合は新しいトピック ページを作成して発行したり、更新する必要がある場合は既存のトピック ページを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-134">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="b9cbb-135">推奨されるトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="b9cbb-135">Review suggested topics</span></span>

<span data-ttu-id="b9cbb-136">[トピック **の管理]** ページで、指定した SharePoint ソースの場所で検出されたトピックが [提案] タブ **に表示** されます。必要に応じて、ナレッジ マネージャーは未確認のトピックを確認し、確認または削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-136">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![推奨されるトピック](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="b9cbb-138">提案されたトピックを確認するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-138">To review a suggested topic:</span></span>

1. <span data-ttu-id="b9cbb-139">[トピックの **管理]** ページで、[提案] タブ **を** 選択し、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-139">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="b9cbb-140">トピック ページで、トピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-140">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="b9cbb-141">編集内容を公開すると、このトピックは [発行済み] タブ **に移動** されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-141">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="b9cbb-142">トピックを確認した後、[トピックの管理] **ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-142">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="b9cbb-143">選択したトピックでは、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-143">For the selected topic, you can:</span></span>

   - <span data-ttu-id="b9cbb-144">チェック マークを選択してトピックを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-144">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="b9cbb-145">トピックを **削除する** 場合は、x を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-145">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="b9cbb-146">確認済みトピックは提案リスト **から削除** され、確認済みリストに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-146">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="b9cbb-147">削除されたトピックは提案リスト **から削除** され、[削除] タブに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-147">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="b9cbb-148">品質スコア</span><span class="sxs-lookup"><span data-stu-id="b9cbb-148">Quality score</span></span>

<span data-ttu-id="b9cbb-149">[提案されたトピック] ページに表示 **される各** トピックには、品質スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-149">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="b9cbb-150">品質スコアは、平均的なユーザーがトピックに関する情報に対して表示する情報の量を反映しています。各ユーザーは、トピック内の情報に対するアクセス許可または権限が付与されていない可能性があるという理由で、多かれ少なかれ情報を表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-150">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="b9cbb-151">品質スコアは、最も多くの情報を含むトピックに関する洞察を得るのに役立ち、手動で編集する必要があるトピックを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-151">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="b9cbb-152">たとえば、品質スコアが低いトピックは、一部のユーザーがトピックに含まれているファイルやサイトに関連付ける SharePoint アクセス許可を持たない場合です。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-152">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="b9cbb-153">投稿者はトピックを編集して情報を含めることができ (適切な場合)、その後そのトピックを閲覧可能なすべてのユーザーがトピックを閲覧できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-153">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="b9cbb-154">インプレッション</span><span class="sxs-lookup"><span data-stu-id="b9cbb-154">Impressions</span></span>

<span data-ttu-id="b9cbb-155">[ **インプレッション数]** 列には、トピックがエンド ユーザーに表示された回数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-155">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="b9cbb-156">これには、検索のトピック回答カードやトピックのハイライトを通じたビューが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-156">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="b9cbb-157">これらのトピックのクリックスルーは反映されませんが、トピックが表示されています。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-157">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="b9cbb-158">[**トピックの管理]** ページの [提案済み] タブ、[確認済み] タブ、[**発行** 済み] タブ、および [削除済み] タブにトピックの [インプレッション数]**列が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-158">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="b9cbb-159">承認済みトピック</span><span class="sxs-lookup"><span data-stu-id="b9cbb-159">Confirmed topics</span></span>

<span data-ttu-id="b9cbb-160">[トピックの管理] ページで、指定した SharePoint ソースの場所で検出され、カード フィードバック メカニズムを介して、2 人以上のネットによって確認されたナレッジ マネージャーまたは "クラウドソース" によって確認されたトピック (否定的なユーザー投票と肯定的なユーザー投票のバランスを取る) が[確認済み] タブに表示されます。必要に応じて、トピックを管理する権限を持つユーザーは、確認済みトピックを確認し、拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-160">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="b9cbb-161">確認済みトピックを確認するには、次の項目を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-161">To review a confirmed topic:</span></span>

1. <span data-ttu-id="b9cbb-162">**[承認済み]** タブで、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-162">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="b9cbb-163">トピック ページで、トピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-163">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="b9cbb-164">確認済みトピックを拒否することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-164">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="b9cbb-165">これを行うには、[確認済み] タブで選択したトピックに移動し、トピックを拒否する場合は **x** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-165">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="b9cbb-166">公開済みトピック</span><span class="sxs-lookup"><span data-stu-id="b9cbb-166">Published topics</span></span>

<span data-ttu-id="b9cbb-167">公開されたトピックは編集され、特定の情報がページに遭遇したユーザーに常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-167">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="b9cbb-168">手動で作成したトピックもこちらに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9cbb-168">Manually created topics are listed here as well.</span></span>

   ![トピックの管理](../media/knowledge-management/manage-topics-new.png)
