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
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107520"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="7e403-103">Microsoft のトピックのセキュリティ トリミング</span><span class="sxs-lookup"><span data-stu-id="7e403-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="7e403-104">ユーザーは、既存の 365 のアクセス許可によってOfficeトピックの情報を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="7e403-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="7e403-105">ユーザーがトピック ページに表示する情報 (SharePoint サイト、ドキュメント、ファイルなど) はすべて、既に表示が許可されている情報です。</span><span class="sxs-lookup"><span data-stu-id="7e403-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="7e403-106">トピックでは、既存のアクセス許可は変更されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="7e403-107">2 人のユーザーが同じトピックに対して異なるビューを持つ理由</span><span class="sxs-lookup"><span data-stu-id="7e403-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="7e403-108">AI または手動によるキュレーションを使用してトピックを作成する場合は、トピックの説明、代替名、トピックに関連付けられているユーザー、およびトピックに関連するサイト、ページ、およびファイルを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="7e403-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="7e403-109">この情報をトピック ページに表示すると、同じトピックを表示している 2 人のユーザーに同じ情報が表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e403-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="7e403-110">たとえば、User 1 が [Neptune] トピック ページを表示すると、このトピック ページのビューが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e403-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![ユーザー 1 の Neptune トピック](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="7e403-112">ただし、User 2 が同じ Neptune トピック ページを参照すると、そのビューは User 1 とは異なります。</span><span class="sxs-lookup"><span data-stu-id="7e403-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="7e403-113">ユーザー 2 は、トピック ページの固定ファイルとページ セクションに *DG-2000 製品* の概要ファイルを表示できます。これはユーザー 1 には表示されません。 </span><span class="sxs-lookup"><span data-stu-id="7e403-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![ユーザー 2 の Neptune トピック](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="7e403-115">同じトピックでユーザーに表示される内容の違いは、ユーザーが関連するサイトまたはファイルを表示するための Office 365 アクセス許可を持たないことです。</span><span class="sxs-lookup"><span data-stu-id="7e403-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="7e403-116">「トピック」では、トピック内のアイテムに設定されているアクセス許可が尊重され、トピックへのアクセスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7e403-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="7e403-117">この例では、ユーザー 1 にはファイルを表示する Office 365 アクセス許可が付与されていないので、User 1 は Neptune のトピック ページで *DG-2000* 製品概要ファイルを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="7e403-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="7e403-118">ユーザーが役立つ情報をトピックに十分に表示できない場合、そのトピックはユーザーが利用できません。</span><span class="sxs-lookup"><span data-stu-id="7e403-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="7e403-119">この場合、強調表示されたトピックはユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="7e403-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="7e403-120">このトピックで役立つ情報に対するアクセス許可を持つ別のユーザーは、このトピックを参照できます。</span><span class="sxs-lookup"><span data-stu-id="7e403-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="7e403-121">ナレッジ マネージャーおよびトピックの投稿者向けトピックのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7e403-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="7e403-122">トピックを管理するアクセス許可が割り当てられているユーザー (ナレッジ マネージャー) は、トピック内に表示するアクセス許可を持つ情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7e403-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="7e403-123">同様に、トピックのアクセス許可 (トピックの投稿者) を作成および編集したユーザーは、トピック内で表示するアクセス許可を持つ情報のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7e403-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="7e403-124">AI と手動で選択されたトピック情報</span><span class="sxs-lookup"><span data-stu-id="7e403-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="7e403-125">トピックには、AI によって生成される情報と、トピックの投稿者またはナレッジ マネージャーによって追加または編集された情報を含めできます。</span><span class="sxs-lookup"><span data-stu-id="7e403-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="7e403-126">AI によって追加されたトピック内の情報は、ソース コンテンツにアクセスできるユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="7e403-127">トピック投稿者またはナレッジ マネージャーによって手動で追加または編集された情報は、トピックを参照できるすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-127">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="7e403-128">次の表では、ユーザー (トピック閲覧者、投稿者、ナレッジ マネージャー) がアクセス許可に基づいて特定のトピックで表示できる内容を示します。</span><span class="sxs-lookup"><span data-stu-id="7e403-128">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="7e403-129">トピック 項目</span><span class="sxs-lookup"><span data-stu-id="7e403-129">Topic item</span></span>|<span data-ttu-id="7e403-130">ユーザーに表示される情報</span><span class="sxs-lookup"><span data-stu-id="7e403-130">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="7e403-131">トピック名</span><span class="sxs-lookup"><span data-stu-id="7e403-131">Topic name</span></span>|<span data-ttu-id="7e403-132">ユーザーは、トピック センターですべてのトピックのトピック名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7e403-132">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="7e403-133">一部のトピックは、ユーザーとの関連性が低い場合には表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e403-133">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="7e403-134">トピックの説明</span><span class="sxs-lookup"><span data-stu-id="7e403-134">Topic description</span></span>|<span data-ttu-id="7e403-135">AI によって生成された説明は、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-135">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="7e403-136">手動で入力または編集した説明は、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-136">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="7e403-137">ユーザー</span><span class="sxs-lookup"><span data-stu-id="7e403-137">People</span></span>|<span data-ttu-id="7e403-138">ピン留めされたユーザーは、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-138">Pinned people are visible to all users.</span></span> <span data-ttu-id="7e403-139">提案されたユーザーは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-139">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="7e403-140">Files</span><span class="sxs-lookup"><span data-stu-id="7e403-140">Files</span></span>|<span data-ttu-id="7e403-141">ファイルは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-141">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="7e403-142">ページ</span><span class="sxs-lookup"><span data-stu-id="7e403-142">Pages</span></span>|<span data-ttu-id="7e403-143">ページは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-143">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="7e403-144">サイト</span><span class="sxs-lookup"><span data-stu-id="7e403-144">Sites</span></span>|<span data-ttu-id="7e403-145">サイトは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e403-145">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="7e403-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e403-146">See also</span></span>

