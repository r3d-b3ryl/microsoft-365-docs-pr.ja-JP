---
title: Microsoft Viva Topics セキュリティ トリミング
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: トピックの表示にセキュリティを使用する方法の概要。
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939625"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="a2ff3-103">Microsoft Viva Topics セキュリティ トリミング</span><span class="sxs-lookup"><span data-stu-id="a2ff3-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="a2ff3-104">[ビバ トピック] ユーザーは、既存のユーザーのアクセス許可によって表示Office 365情報を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="a2ff3-105">ユーザーがトピック ページに表示する情報 (SharePoint、ドキュメント、ファイルなど) は、既に表示が許可されている情報です。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="a2ff3-106">Viva Topics は、既存のアクセス許可に変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="a2ff3-107">2 人のユーザーが同じトピックの異なるビューを持つ理由</span><span class="sxs-lookup"><span data-stu-id="a2ff3-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="a2ff3-108">AI または手動キュレーションを使用してトピックを作成する場合は、トピックの説明、代替名、トピックに関連付けられたユーザー、トピックに関連するサイト、ページ、ファイルを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="a2ff3-109">この情報をトピック ページで表示すると、同じトピックを表示している 2 人のユーザーが同じ情報を表示しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="a2ff3-110">たとえば、ユーザー 1 が Neptune トピック ページを表示すると、トピック ページのこのビューが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![ユーザー 1 の Neptune トピック](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="a2ff3-112">ただし、ユーザー 2 が同じ Neptune トピック ページを見た場合、そのビューはユーザー 1 とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="a2ff3-113">ユーザー 2 は、トピック ページの [ピン留めされたファイルとページ] セクションに *DG-2000* 製品概要ファイルを表示できます。これはユーザー 1 には表示されません。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![ユーザー 2 の Neptune トピック](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="a2ff3-115">同じトピックでユーザーに表示される内容の違いは、ユーザーが関連するサイトまたはファイルを表示Office 365アクセス許可を持たないのでです。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="a2ff3-116">Viva Topics は、トピック内のアイテムに設定されているアクセス許可を尊重し、アクセス権を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="a2ff3-117">この例では、ユーザー 1 にはファイルを表示するための Office 365 アクセス許可が付与されていないので、ユーザー 1 は Neptune のトピック ページで *DG-2000* 製品概要ファイルを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="a2ff3-118">ユーザーが有用なトピックに十分な情報を表示できない場合、そのトピックはユーザーが利用できません。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="a2ff3-119">この場合、強調表示されているトピックは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="a2ff3-120">トピックの詳細に対するアクセス許可を持つ別のユーザーが役立つ場合は、トピックを参照できます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="a2ff3-121">ナレッジ マネージャーとトピック投稿者のトピックのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a2ff3-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="a2ff3-122">トピックを管理するためのアクセス許可が割り当てられているユーザー (ナレッジ マネージャー) は、トピック内で表示するアクセス許可を持つ情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="a2ff3-123">同様に、トピックのアクセス許可 (トピック投稿者) を作成および編集しているユーザーは、トピック内で表示するアクセス許可を持つ情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="a2ff3-124">AI と手動で調整されたトピック情報</span><span class="sxs-lookup"><span data-stu-id="a2ff3-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="a2ff3-125">トピックには、AI によって生成された情報と、トピック投稿者またはナレッジ マネージャーによって追加または編集された情報を含めできます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="a2ff3-126">AI によって追加されたトピック内の情報は、ソース コンテンツにアクセスできるユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="a2ff3-127">トピック投稿者またはナレッジ マネージャーによって手動で追加または編集されたトピックの説明とユーザー情報は、トピックを表示できるすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="a2ff3-128">ファイル、ページ、およびサイトは、AI によって手動で追加または追加されたかどうかに関して、ソース コンテンツへのアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="a2ff3-129">次の表は、ユーザー (トピック 閲覧者、投稿者、ナレッジ マネージャー) が、アクセス許可に基づいて特定のトピックで表示できる内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="a2ff3-130">トピック項目</span><span class="sxs-lookup"><span data-stu-id="a2ff3-130">Topic item</span></span>|<span data-ttu-id="a2ff3-131">ユーザーに表示される内容</span><span class="sxs-lookup"><span data-stu-id="a2ff3-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="a2ff3-132">トピック名</span><span class="sxs-lookup"><span data-stu-id="a2ff3-132">Topic name</span></span>|<span data-ttu-id="a2ff3-133">ユーザーはトピック センターでトピックのトピック名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="a2ff3-134">一部のトピックは、ユーザーがソース コンテンツに対するアクセス許可を持たなかったり、ユーザーとの関連性が低い場合に表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="a2ff3-135">トピックの説明</span><span class="sxs-lookup"><span data-stu-id="a2ff3-135">Topic description</span></span>|<span data-ttu-id="a2ff3-136">AI で生成された説明は、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="a2ff3-137">手動で入力または編集された説明は、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="a2ff3-138">連絡先</span><span class="sxs-lookup"><span data-stu-id="a2ff3-138">People</span></span>|<span data-ttu-id="a2ff3-139">ピン留めされた連絡先はすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="a2ff3-140">提案された連絡先は、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="a2ff3-141">ファイル</span><span class="sxs-lookup"><span data-stu-id="a2ff3-141">Files</span></span>|<span data-ttu-id="a2ff3-142">ファイルは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="a2ff3-143">ページ</span><span class="sxs-lookup"><span data-stu-id="a2ff3-143">Pages</span></span>|<span data-ttu-id="a2ff3-144">ページは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="a2ff3-145">サイト</span><span class="sxs-lookup"><span data-stu-id="a2ff3-145">Sites</span></span>|<span data-ttu-id="a2ff3-146">サイトは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2ff3-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="a2ff3-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2ff3-147">See also</span></span>

