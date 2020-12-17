---
title: トピック エクスペリエンスのセキュリティ トリミング (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: セキュリティを使用してトピックを表示する方法の概要。
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698952"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="a53fd-103">トピック エクスペリエンスのセキュリティ トリミング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a53fd-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="a53fd-104">この記事の内容は、Project の Private Preview 用です。</span><span class="sxs-lookup"><span data-stu-id="a53fd-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="a53fd-105">[Project Cortexについてもっと理解しよう](https://aka.ms/projectcortex)</span><span class="sxs-lookup"><span data-stu-id="a53fd-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="a53fd-106">トピック エクスペリエンスでは、ユーザーは既存の Office 365 のアクセス許可によって表示できないトピックの情報を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="a53fd-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="a53fd-107">ユーザーがトピック ページに表示する情報 (SharePoint サイト、ドキュメント、ファイルなど) はすべて、既に表示が許可されている情報です。</span><span class="sxs-lookup"><span data-stu-id="a53fd-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="a53fd-108">トピック エクスペリエンスは、既存のアクセス許可に変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="a53fd-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="a53fd-109">2 人のユーザーが同じトピックに対して異なるビューを持つ理由</span><span class="sxs-lookup"><span data-stu-id="a53fd-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="a53fd-110">AI または手動によるキュレーションを使用してトピックを作成する場合は、トピックの説明、代替名、トピックに関連付けられているユーザー、およびトピックに関連するサイト、ページ、およびファイルを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="a53fd-111">この情報をトピック ページに表示すると、同じトピックを表示している 2 人のユーザーに同じ情報が表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a53fd-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="a53fd-112">たとえば、User 1 が [Neptune] トピック ページを表示すると、そのトピックページに表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a53fd-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![ユーザー 1 の Neptune トピック](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="a53fd-114">ただし、User 2 が同じ Neptune トピック ページを参照すると、ユーザー 1 とはビューが異なります。</span><span class="sxs-lookup"><span data-stu-id="a53fd-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="a53fd-115">ユーザー 2 は、トピック ページの固定ファイルとページ セクションに *DG-2000 製品* の概要ファイルを表示できます。これはユーザー 1 には表示されません。 </span><span class="sxs-lookup"><span data-stu-id="a53fd-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![ユーザー 2 のネプツネトピック](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="a53fd-117">同じトピックでユーザーに表示される内容の違いは、ユーザーが関連するサイトまたはファイルを表示するための Office 365 アクセス許可を持たないことです。</span><span class="sxs-lookup"><span data-stu-id="a53fd-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="a53fd-118">トピック エクスペリエンスでは、トピック内のアイテムに設定されているアクセス許可が尊重され、トピックへのアクセスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a53fd-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="a53fd-119">この例では、ユーザー 1 にはファイルを表示する Office 365 アクセス許可が付与されていないので、User 1 は Neptune のトピック ページで *DG-2000* 製品概要ファイルを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="a53fd-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="a53fd-120">ユーザーが役立つ情報をトピックに十分に表示できない場合、そのトピックはユーザーが利用できません。</span><span class="sxs-lookup"><span data-stu-id="a53fd-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="a53fd-121">この場合、強調表示されたトピックは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a53fd-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="a53fd-122">ただし、このトピックで役立つ情報に対するアクセス許可を持つ別のユーザーは、このトピックを参照できます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="a53fd-123">ナレッジ マネージャーおよびトピック投稿者のトピックのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a53fd-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="a53fd-124">トピックを管理するアクセス許可が割り当てられているユーザー (ナレッジ マネージャー) は、トピック内に表示するアクセス許可を持つ情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="a53fd-125">同様に、トピックのアクセス許可 (トピックの投稿者) を作成および編集したユーザーは、トピック内で表示するアクセス許可を持つ情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="a53fd-126">AI と手動で選択されたトピック情報</span><span class="sxs-lookup"><span data-stu-id="a53fd-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="a53fd-127">トピックには、AI によって生成される情報と、トピックの投稿者またはナレッジ マネージャーによって追加または編集された情報を含めできます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="a53fd-128">AI によって追加されたトピック内の情報は、ソース コンテンツにアクセスできるユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="a53fd-129">トピック投稿者またはナレッジ マネージャーによって手動で追加または編集された情報は、トピックを参照できるすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="a53fd-130">次の表では、ユーザー (トピック閲覧者、投稿者、ナレッジ マネージャー) がアクセス許可に基づいて特定のトピックで表示できる内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a53fd-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="a53fd-131">トピック アイテム</span><span class="sxs-lookup"><span data-stu-id="a53fd-131">Topic item</span></span>|<span data-ttu-id="a53fd-132">ユーザーに表示される情報</span><span class="sxs-lookup"><span data-stu-id="a53fd-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="a53fd-133">トピック名</span><span class="sxs-lookup"><span data-stu-id="a53fd-133">Topic name</span></span>|<span data-ttu-id="a53fd-134">ユーザーは、トピック センターですべてのトピックのトピック名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="a53fd-135">一部のトピックは、ユーザーとの関連性が低い場合には表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a53fd-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="a53fd-136">トピックの説明</span><span class="sxs-lookup"><span data-stu-id="a53fd-136">Topic description</span></span>|<span data-ttu-id="a53fd-137">AI によって生成された説明は、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="a53fd-138">手動で入力または編集した説明は、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="a53fd-139">ユーザー</span><span class="sxs-lookup"><span data-stu-id="a53fd-139">People</span></span>|<span data-ttu-id="a53fd-140">ピン留めされたユーザーは、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="a53fd-141">候補のユーザーは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="a53fd-142">Files</span><span class="sxs-lookup"><span data-stu-id="a53fd-142">Files</span></span>|<span data-ttu-id="a53fd-143">ファイルは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="a53fd-144">ページ</span><span class="sxs-lookup"><span data-stu-id="a53fd-144">Pages</span></span>|<span data-ttu-id="a53fd-145">ページは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="a53fd-146">サイト</span><span class="sxs-lookup"><span data-stu-id="a53fd-146">Sites</span></span>|<span data-ttu-id="a53fd-147">サイトは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a53fd-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="a53fd-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="a53fd-148">See also</span></span>

