---
title: Microsoft Search を使用して Microsoft Viva のトピックを検索する
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Microsoft Viva でトピックを検索する方法について説明します。
ms.openlocfilehash: 1739923c95b42f192bb2e285245f72c3e09e1c30
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925930"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a><span data-ttu-id="74716-103">Microsoft Search を使用して Microsoft Viva のトピックを検索する</span><span class="sxs-lookup"><span data-stu-id="74716-103">Use Microsoft Search to find topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="74716-104">ビバ トピックのユーザーは、SharePoint サイトのトピックのハイライトを通じてトピックを見つける一方で、Microsoft Search を通じてトピックを検索できます。</span><span class="sxs-lookup"><span data-stu-id="74716-104">While Viva Topics users can find topics through topic highlights in their SharePoint sites, they can also find them through Microsoft Search.</span></span> 

## <a name="topic-answer"></a><span data-ttu-id="74716-105">トピックの回答</span><span class="sxs-lookup"><span data-stu-id="74716-105">Topic Answer</span></span>

<span data-ttu-id="74716-106">Microsoft Search で特定のトピック ("Saturn" など) を検索すると、トピックが存在し、見つかった場合は、回答候補形式で結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74716-106">When you search for a specific topic in Microsoft Search (for example, "Saturn"), if a topic exists and is found, it will display the result in the Answers suggestion format.</span></span>

<span data-ttu-id="74716-107">トピックの回答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74716-107">The topic answer will display:</span></span>
- <span data-ttu-id="74716-108">トピック名</span><span class="sxs-lookup"><span data-stu-id="74716-108">Topic name</span></span>
- <span data-ttu-id="74716-109">代替名: トピックの代替名または頭字語。</span><span class="sxs-lookup"><span data-stu-id="74716-109">Alternate names: Alternate names or acronyms for the topic.</span></span>
- <span data-ttu-id="74716-110">定義: AI によって提供されるトピックの説明、またはユーザーが手動で追加したトピックの説明。</span><span class="sxs-lookup"><span data-stu-id="74716-110">Definition: Description of the topic provided by AI or manually added by a person.</span></span>
- <span data-ttu-id="74716-111">推奨ユーザーまたはピン留めされたユーザー: AI によって提案されたユーザー、またはユーザーがトピックにピン留めしたユーザー</span><span class="sxs-lookup"><span data-stu-id="74716-111">Suggested or Pinned people: People suggested by AI or pinned to the topic by a person</span></span>
- <span data-ttu-id="74716-112">推奨リソースまたはピン留めされたリソース: AI によって提案されたファイル、ページ、またはサイト、またはユーザーによってトピックにピン留めされたサイト。</span><span class="sxs-lookup"><span data-stu-id="74716-112">Suggested or Pinned resources: Files, pages, or sites either suggested by AI or pinned to the topic by a person.</span></span> 

   ![検索のトピック](../media/knowledge-management/search-topic-answer.png) 

<span data-ttu-id="74716-114">トピック の応答カードが表示されない場合でも、トピック ページを検索結果に表示できます。</span><span class="sxs-lookup"><span data-stu-id="74716-114">The topic page can display in the search results even if the topic answer card doesn't appear.</span></span>


## <a name="acronyms"></a><span data-ttu-id="74716-115">頭字語</span><span class="sxs-lookup"><span data-stu-id="74716-115">Acronyms</span></span>

<span data-ttu-id="74716-116">Viva Topics では、トピックを手動で編集して、トピックの頭字語を代替名として <b>含めできます</b>。</span><span class="sxs-lookup"><span data-stu-id="74716-116">In Viva Topics, you can manually edit a topic to include an acronym for it as an <b>Alternate Name</b>.</span></span> <span data-ttu-id="74716-117">これにより、トピックの頭字語のみを使用して検索しているユーザーは、Microsoft Search を通じてトピックの回答を検索できます。</span><span class="sxs-lookup"><span data-stu-id="74716-117">This allows a user who is searching by only the topic's acronym to find the topic answer through Microsoft Search.</span></span>

<span data-ttu-id="74716-118">[頭字語の回答は](/microsoftsearch/manage-acronyms) 、Microsoft Search によって提供される機能であり、ビバ トピックとは別に管理されます。</span><span class="sxs-lookup"><span data-stu-id="74716-118">[Acronym Answers](/microsoftsearch/manage-acronyms) is a feature provided though Microsoft Search and is managed separately from Viva Topics.</span></span>

## <a name="bookmarks-and-topics"></a><span data-ttu-id="74716-119">ブックマークとトピック</span><span class="sxs-lookup"><span data-stu-id="74716-119">Bookmarks and topics</span></span>

<span data-ttu-id="74716-120">[ブックマークは](/microsoftsearch/manage-bookmarks) 、ユーザーが検索だけで重要なサイトやツールをすばやく見つけるのに役立つ Microsoft Search 機能です (たとえば、Microsoft 365 テナント外の外部サイトの旅行予約ツール)。</span><span class="sxs-lookup"><span data-stu-id="74716-120">[Bookmarks](/microsoftsearch/manage-bookmarks) are a Microsoft Search feature that help people quickly find important sites and tools with just a search (for example, a travel booking tool on an external site outside of their Microsoft 365 tenant).</span></span> <span data-ttu-id="74716-121">これらは、Microsoft 365 管理センターの検索管理者によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="74716-121">They're created by search admins in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="74716-122">出張の予約に関する情報をお探しのユーザー向け:</span><span class="sxs-lookup"><span data-stu-id="74716-122">For users who are looking for information about booking a trip for work:</span></span>

- <span data-ttu-id="74716-123">一部のユーザーが旅行ツール名 ("Concur" など) を知っている場合は、外部サイトに直接移動するブックマークを作成する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="74716-123">If some users know the travel tool name (for example, "Concur"), it's easier to create a bookmark to go directly to the external site.</span></span>
- <span data-ttu-id="74716-124">一般的に "旅行" を検索するユーザーの場合は、「旅行」に関するトピックを作成します。そのトピックには、表示される情報が含されます。</span><span class="sxs-lookup"><span data-stu-id="74716-124">For users who search generally for "travel", create a topic on "Travel" that has the information they expect to see.</span></span> <span data-ttu-id="74716-125">トピックの説明で Concur 外部サイトへのリンクを追加する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="74716-125">Consider adding a link to the Concur external site in the description of the topic.</span></span> <span data-ttu-id="74716-126">リンクが Microsoft 365 テナントでホストされている内部旅行予約サイトにリンクされている場合は、"ピン留めされたリソース" に追加できます。</span><span class="sxs-lookup"><span data-stu-id="74716-126">If the link is instead to an internal travel booking site hosted on the Microsoft 365 tenant, you can add it to the “Pinned Resources”.</span></span>
 
### <a name="search-results-priority"></a><span data-ttu-id="74716-127">検索結果の優先度</span><span class="sxs-lookup"><span data-stu-id="74716-127">Search results priority</span></span> 
 
<span data-ttu-id="74716-128">ユーザー検索エクスペリエンスでは、ユーザーが "旅行" のような用語を検索すると、検索結果は Microsoft Search で次の優先度で表示されます。</span><span class="sxs-lookup"><span data-stu-id="74716-128">In the users search experience, when a user searches for a term like “travel”, search results will display in the following priority in Microsoft Search</span></span>
1. <span data-ttu-id="74716-129">発行済みトピックまたは確認済みトピック</span><span class="sxs-lookup"><span data-stu-id="74716-129">Published or Confirmed topics</span></span> 
2. <span data-ttu-id="74716-130">ブックマーク</span><span class="sxs-lookup"><span data-stu-id="74716-130">Bookmarks</span></span>
3. <span data-ttu-id="74716-131">推奨されるトピック</span><span class="sxs-lookup"><span data-stu-id="74716-131">Suggested topics</span></span>