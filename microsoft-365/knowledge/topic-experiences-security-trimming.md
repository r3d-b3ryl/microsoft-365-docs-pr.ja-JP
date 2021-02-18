---
title: Microsoft のトピックのセキュリティ トリミング
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
description: セキュリティを使用してトピックを表示する方法の概要。
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279334"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="68a46-103">Microsoft のトピックのセキュリティ トリミング</span><span class="sxs-lookup"><span data-stu-id="68a46-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="68a46-104">ユーザーは、既存の 365 のアクセス許可によってOfficeトピックの情報を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="68a46-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="68a46-105">トピック ページでユーザーに表示される情報 (SharePoint サイト、ドキュメント、ファイルなど) はすべて、既に表示が許可されている情報です。</span><span class="sxs-lookup"><span data-stu-id="68a46-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="68a46-106">トピックでは、既存のアクセス許可は変更されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="68a46-107">2 人のユーザーが同じトピックに対して異なるビューを持つ理由</span><span class="sxs-lookup"><span data-stu-id="68a46-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="68a46-108">AI または手動によるキュレーションを使用してトピックを作成する場合は、トピックの説明、代替名、トピックに関連付けられているユーザー、およびトピックに関連するサイト、ページ、およびファイルを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="68a46-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="68a46-109">この情報をトピック ページで表示すると、同じトピックを表示している 2 人のユーザーに同じ情報が表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68a46-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="68a46-110">たとえば、User 1 が Neptune トピック ページを表示すると、このトピック ページのビューが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="68a46-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![ユーザー 1 の Neptune トピック](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="68a46-112">ただし、User 2 が同じ Neptune トピック ページを参照すると、そのビューは User 1 とは異なります。</span><span class="sxs-lookup"><span data-stu-id="68a46-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="68a46-113">ユーザー 2 は、トピック ページの固定ファイルとページ セクションに *DG-2000 製品* の概要ファイルを表示できます。これはユーザー 1 には表示されません。 </span><span class="sxs-lookup"><span data-stu-id="68a46-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![ユーザー 2 の Neptune トピック](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="68a46-115">同じトピックでユーザーに表示される内容の違いは、ユーザーが関連するサイトまたはファイルを表示するための Office 365 アクセス許可を持たないことです。</span><span class="sxs-lookup"><span data-stu-id="68a46-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="68a46-116">「トピック」では、トピック内のアイテムに設定されているアクセス許可が尊重され、トピックへのアクセスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="68a46-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="68a46-117">この例では、ユーザー 1 にはファイルを表示する Office 365 アクセス許可が付与されていないので、User 1 は Neptune のトピック ページで *DG-2000* 製品概要ファイルを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="68a46-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="68a46-118">ユーザーが役立つ情報をトピックに十分に表示できない場合、そのトピックはユーザーが利用できません。</span><span class="sxs-lookup"><span data-stu-id="68a46-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="68a46-119">この場合、強調表示されたトピックはユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="68a46-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="68a46-120">このトピックで役立つ情報に対するアクセス許可を持つ別のユーザーは、このトピックを参照できます。</span><span class="sxs-lookup"><span data-stu-id="68a46-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="68a46-121">ナレッジ マネージャーおよびトピック投稿者のトピックのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="68a46-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="68a46-122">トピックを管理するアクセス許可が割り当てられているユーザー (ナレッジ マネージャー) は、トピック内に表示するアクセス許可を持つ情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="68a46-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="68a46-123">同様に、トピックのアクセス許可 (トピックの投稿者) を作成および編集したユーザーは、トピック内で表示するアクセス許可を持つ情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="68a46-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="68a46-124">AI と手動で選択されたトピック情報</span><span class="sxs-lookup"><span data-stu-id="68a46-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="68a46-125">トピックには、AI によって生成される情報と、トピックの投稿者またはナレッジ マネージャーによって追加または編集された情報を含めできます。</span><span class="sxs-lookup"><span data-stu-id="68a46-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="68a46-126">AI によって追加されたトピック内の情報は、ソース コンテンツにアクセスできるユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="68a46-127">トピックの作成者またはナレッジ マネージャーによって手動で追加または編集されたトピックの説明とユーザー情報は、トピックを表示できるすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="68a46-128">ファイル、ページ、サイトは、手動で追加または追加した場合でも、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="68a46-129">次の表では、ユーザー (トピック閲覧者、投稿者、ナレッジ マネージャー) がアクセス許可に基づいて特定のトピックで表示できる内容を示します。</span><span class="sxs-lookup"><span data-stu-id="68a46-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="68a46-130">トピック アイテム</span><span class="sxs-lookup"><span data-stu-id="68a46-130">Topic item</span></span>|<span data-ttu-id="68a46-131">ユーザーに表示される情報</span><span class="sxs-lookup"><span data-stu-id="68a46-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="68a46-132">トピック名</span><span class="sxs-lookup"><span data-stu-id="68a46-132">Topic name</span></span>|<span data-ttu-id="68a46-133">ユーザーは、トピック センターですべてのトピックのトピック名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="68a46-133">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="68a46-134">一部のトピックは、ユーザーとの関連性が低い場合には表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="68a46-134">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="68a46-135">トピックの説明</span><span class="sxs-lookup"><span data-stu-id="68a46-135">Topic description</span></span>|<span data-ttu-id="68a46-136">AI によって生成された説明は、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="68a46-137">手動で入力または編集した説明は、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="68a46-138">連絡先</span><span class="sxs-lookup"><span data-stu-id="68a46-138">People</span></span>|<span data-ttu-id="68a46-139">ピン留めされたユーザーは、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="68a46-140">候補のユーザーは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="68a46-141">ファイル</span><span class="sxs-lookup"><span data-stu-id="68a46-141">Files</span></span>|<span data-ttu-id="68a46-142">ファイルは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="68a46-143">ページ</span><span class="sxs-lookup"><span data-stu-id="68a46-143">Pages</span></span>|<span data-ttu-id="68a46-144">ページは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="68a46-145">サイト</span><span class="sxs-lookup"><span data-stu-id="68a46-145">Sites</span></span>|<span data-ttu-id="68a46-146">サイトは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="68a46-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="68a46-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="68a46-147">See also</span></span>

