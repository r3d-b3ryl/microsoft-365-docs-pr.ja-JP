---
title: 'トピック エクスペリエンス (プレビュー) のトピック センターでトピックを管理する '
description: トピック センターでトピックを管理する方法。
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 371ccc16e787b331f42026dec48e5e3113b2b172
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976193"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="150f3-103">トピック センターでトピックを管理する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="150f3-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="150f3-104">この記事の内容は、Project の Private Preview 用です。</span><span class="sxs-lookup"><span data-stu-id="150f3-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="150f3-105">[Project Cortexについてもっと理解しよう](https://aka.ms/projectcortex)</span><span class="sxs-lookup"><span data-stu-id="150f3-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="150f3-106">トピック センターでは、ナレッジ マネージャーは [トピックの管理] ページを表示して、ナレッジ管理者が指定した SharePoint ソースの場所で識別されたトピックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="150f3-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![トピック センター](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="150f3-108">ナレッジ マネージャーは、検出されたトピックを、トピックが次のトピックのライフサイクルを通じてガイドするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="150f3-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="150f3-109">推奨: トピックは AI によって識別され、トピックのしきい値を満たすのに十分なサポート リソース、接続、およびプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="150f3-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="150f3-110">確認済み: AI によって提案されたトピックが検証されます。</span><span class="sxs-lookup"><span data-stu-id="150f3-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="150f3-111">検証は、ナレッジ管理者からの確認によって行われます。また、少なくとも 2 人のユーザーがトピックの有効なフィードバックを通じて肯定的なフィードバックを寄せた場合は、トピックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="150f3-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="150f3-112">削除: トピックはナレッジ管理者によって拒否され、閲覧者には表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="150f3-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="150f3-113">トピックは、削除された場合 (推奨または確認済み) に任意の状態にできます。</span><span class="sxs-lookup"><span data-stu-id="150f3-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="150f3-114">公開: 手動で更新された確認済みトピック。</span><span class="sxs-lookup"><span data-stu-id="150f3-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![トピック ライフサイクル のグラフ](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="150f3-116">要件</span><span class="sxs-lookup"><span data-stu-id="150f3-116">Requirements</span></span>

<span data-ttu-id="150f3-117">トピック センターでトピックを管理するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="150f3-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="150f3-118">トピック エクスペリエンス のライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="150f3-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="150f3-119">トピックを管理できる [**ユーザーへのアクセス許可を持っている**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)。</span><span class="sxs-lookup"><span data-stu-id="150f3-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="150f3-120">ナレッジ管理者は、サポート技術情報のトピックのアクセス許可の設定で、ユーザーにこのアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="150f3-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="150f3-121">トピックを管理できるユーザー権限がない限り、トピック センターの [トピックの管理] **ページを表示** することはできません。</span><span class="sxs-lookup"><span data-stu-id="150f3-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="150f3-122">トピック センターでは、ナレッジ マネージャーは、指定した SharePoint ソースの場所で特定されたトピックを確認し、確認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="150f3-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="150f3-123">ナレッジ マネージャーは、新しいトピック ページがトピックの検出で見つからない場合は作成して発行したり、更新が必要な場合は既存のトピック ページを編集したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="150f3-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="150f3-124">推奨されるトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="150f3-124">Review suggested topics</span></span>

<span data-ttu-id="150f3-125">トピック センターの [トピックの管理] ページでは、指定した SharePoint ソースの場所で検出されたトピックが [候補] タブ **に表示** されます。ナレッジ マネージャーは未確認のトピックを確認し、確認または拒否を選択できます。</span><span class="sxs-lookup"><span data-stu-id="150f3-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="150f3-126">推奨されるトピックを確認するには:</span><span class="sxs-lookup"><span data-stu-id="150f3-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="150f3-127">[トピック **の管理]** ページで [ **候補** ] タブを選択し、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="150f3-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="150f3-128">トピック ページでトピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150f3-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="150f3-129">トピックを確認した後、[トピックの管理] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="150f3-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="150f3-130">選択したトピックでは、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="150f3-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="150f3-131">チェック マークを選択してトピックを確認します。</span><span class="sxs-lookup"><span data-stu-id="150f3-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="150f3-132">トピックを **拒否する場合は、x** を選択します。</span><span class="sxs-lookup"><span data-stu-id="150f3-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="150f3-133">確認済みトピックは候補リスト **から削除** され、確認済みリストに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="150f3-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="150f3-134">拒否されたトピックは [候補] リスト **から削除** され、[削除] タブに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="150f3-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="150f3-135">確認済みトピック</span><span class="sxs-lookup"><span data-stu-id="150f3-135">Confirmed topics</span></span>

<span data-ttu-id="150f3-136">[トピックの管理] ページでは、指定した SharePoint ソースの場所で検出され、カード フィードバック メカニズムによって 2 人以上のユーザーによって確認されたナレッジ マネージャーまたは "クラウド ソース"によって確認されたトピックが[確認済み] タブに一覧表示されます。必要に応じて、トピックを管理する権限を持つユーザーは、確認済みトピックを確認し、拒否することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="150f3-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="150f3-137">確認済みトピックを確認するには:</span><span class="sxs-lookup"><span data-stu-id="150f3-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="150f3-138">[ **確認済み]** タブで、トピックを選択してトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="150f3-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="150f3-139">トピック ページでトピック ページを確認し、ページに変更を加える必要がある場合は [編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150f3-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="150f3-140">確認済みトピックを拒否することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="150f3-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="150f3-141">これを行うには、確認済みリストで選択したトピックに移動し、トピックを拒否する場合は **x** を選択します。</span><span class="sxs-lookup"><span data-stu-id="150f3-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="150f3-142">公開されたトピック</span><span class="sxs-lookup"><span data-stu-id="150f3-142">Published topics</span></span>
<span data-ttu-id="150f3-143">公開されたトピックは編集され、ページにアクセスしたユーザーに特定の情報が常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="150f3-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="150f3-144">手動で作成したトピックの一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="150f3-144">Manually created topics are listed here.</span></span>




