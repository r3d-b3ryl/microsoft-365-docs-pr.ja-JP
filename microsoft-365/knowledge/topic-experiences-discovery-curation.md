---
title: 'トピック エクスペリエンスのトピックの検出とキュレーション (プレビュー) '
description: トピックの検出方法の概要。
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ea0bbc1f7d34ff01fcf446bfa4bbd0b95f310c4c
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976169"
---
# <a name="topic-experiences-discovery-and-curation-preview"></a><span data-ttu-id="96570-103">トピック エクスペリエンスの検出とキュレーション (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="96570-103">Topic Experiences discovery and curation (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="96570-104">この記事の内容は、Project の Private Preview 用です。</span><span class="sxs-lookup"><span data-stu-id="96570-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="96570-105">[Project Cortexについてもっと理解しよう](https://aka.ms/projectcortex)</span><span class="sxs-lookup"><span data-stu-id="96570-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="96570-106">トピック エクスペリエンスは、知識情報を Microsoft 365 環境の知識に変換します。</span><span class="sxs-lookup"><span data-stu-id="96570-106">Topic Experiences converts knowledge information to knowledge in your Microsoft 365 environment.</span></span> <span data-ttu-id="96570-107">見慣れない用語が見つかったドキュメントやサイト ページを読む経験は豊富です。</span><span class="sxs-lookup"><span data-stu-id="96570-107">We've all experienced reading through documents and site pages where we encounter terms we are unfamiliar with.</span></span> <span data-ttu-id="96570-108">多くの場合、より多くの情報を検索するために貴重な時間を費やすために行っているのを停止します。</span><span class="sxs-lookup"><span data-stu-id="96570-108">Many times we stop what we are doing to spend precious time searching for more information.</span></span>

<span data-ttu-id="96570-109">トピック エクスペリエンスの機能は、Microsoft Graph と AI を使用して組織内 **のトピック** を特定する方法です。</span><span class="sxs-lookup"><span data-stu-id="96570-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span></span>  <span data-ttu-id="96570-110">トピックとは、組織にとって特定の意味を持つ語句または用語で、ユーザーが Wiki ページを表示できると便利です。</span><span class="sxs-lookup"><span data-stu-id="96570-110">A topic is a phrase or term that has a specific meaning to an organization, where users would benefit by being able to view a wiki page about it.</span></span> <span data-ttu-id="96570-111">AI はトピックに接続されている人やコンテンツを検索し、十分に検出された場合は推奨トピックになります。</span><span class="sxs-lookup"><span data-stu-id="96570-111">AI searches for people and content connected to the topic, and if enough it discovered, it becomes a suggested topic.</span></span>

<span data-ttu-id="96570-112">AI によって生成されたトピック情報は、次を含む **トピック ページ** に追加されます。</span><span class="sxs-lookup"><span data-stu-id="96570-112">The AI generated topic information is added to a **Topic page**, which can contain:</span></span>
- <span data-ttu-id="96570-113">トピックの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="96570-113">A short description of the topic.</span></span>
- <span data-ttu-id="96570-114">トピックの代替名。</span><span class="sxs-lookup"><span data-stu-id="96570-114">Alternate names for the topic.</span></span>
- <span data-ttu-id="96570-115">トピックの詳細を知っている可能性があるユーザー。</span><span class="sxs-lookup"><span data-stu-id="96570-115">People who might know more about the topic.</span></span>
- <span data-ttu-id="96570-116">トピックに関連する可能性があるサイト、ファイル、およびページ。</span><span class="sxs-lookup"><span data-stu-id="96570-116">Sites, files, and pages that might be related to the topic.</span></span>

<span data-ttu-id="96570-117">トピックエクスペリエンスでは、テナント内のすべての SharePoint モダン サイト ページでトピックのすべてのインスタンスが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="96570-117">Topic experiences then makes sure that every instance of a topic is highlighted on all SharePoint modern site pages in your tenant.</span></span> <span data-ttu-id="96570-118">ユーザーがトピックの詳細を知りたがっている場合は、強調表示されているトピックを選択して、簡単な説明を提供する **トピック** の概要カードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="96570-118">When a user is curious to learn more about a topic, they can select the highlighted topic to view a **Topic summary** card that provides a short description.</span></span> <span data-ttu-id="96570-119">さらに詳しく知りたい場合は、概要で [トピックの詳細] リンクを選択して、詳細なトピック ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="96570-119">And if they want to learn more, they can select a **Topic details** link in the summary to open the detailed topic page.</span></span>

![トピックのハイライト](../media/knowledge-management/saturn.png) </br>

<span data-ttu-id="96570-121">さらに、ユーザーは Microsoft Search を使用してトピックを検索できます。</span><span class="sxs-lookup"><span data-stu-id="96570-121">Additionally, users will also be able to find topics through Microsoft Search.</span></span>


## <a name="topic-curation"></a><span data-ttu-id="96570-122">トピックの作成</span><span class="sxs-lookup"><span data-stu-id="96570-122">Topic curation</span></span>

<span data-ttu-id="96570-123">トピック エクスペリエンスは、トピックの品質を向上させる人間の "キュレーション" を歓迎します。</span><span class="sxs-lookup"><span data-stu-id="96570-123">Topic Experiences welcomes human "curation" to improve the quality of your topics.</span></span> <span data-ttu-id="96570-124">AI は最初にトピックを識別して提案しますが、投稿者からコンテンツを手動で更新し、AI によって生成されたコンテンツに対するユーザーからの確認、トピックの有用性に関するフィードバックはすべて不可欠です。</span><span class="sxs-lookup"><span data-stu-id="96570-124">While AI initially identifies and suggests topics, manually made updates to content from contributors, confirmation from users for AI generated content, and feedback on the usefulness of topics are all essential.</span></span>

- <span data-ttu-id="96570-125">AI が生成したトピック ("推奨トピック") は、組織内のナレッジ **マネージャーが確認** できます。</span><span class="sxs-lookup"><span data-stu-id="96570-125">AI generated topics ("suggested topics") can be reviewed by **knowledge managers** in your organization.</span></span> <span data-ttu-id="96570-126">トピック センターの [トピックの管理] ページでは、トピックを有効として確認するか、拒否して表示を拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="96570-126">In the Manage Topics page in the Topic Center, they can choose to confirm them as valid, or reject them to prevent them from being viewed.</span></span>

- <span data-ttu-id="96570-127">ライセンスを取得 *したユーザー* に対してトピックの作成と編集のアクセス許可を割り当て、必要に応じて既存のトピックを変更したり、新しいトピックを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="96570-127">You can assign *Create and edit topics* permissions to any of your licensed users so that they can make changes to existing topics or create new topics when needed.</span></span> 

- <span data-ttu-id="96570-128">トピック (トピック閲覧者) に対する読み取りアクセス権しか持てないユーザーでも、特定のトピックの役に立つ内容を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96570-128">Even users who only have read access to topic (topic viewers) will be asked to verify the usefulness of specific topics.</span></span>

<span data-ttu-id="96570-129">人間のキュレーションを使用する場合でも、AI はトピックに関する情報を継続的に探し、人間による検証を探します。</span><span class="sxs-lookup"><span data-stu-id="96570-129">Even with human curation, AI will continually look for more information about topics, and will look for human verification.</span></span> <span data-ttu-id="96570-130">たとえば、AI がトピックの専門家としてピン留めする必要がある人物だと考える場合、この確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96570-130">For example, if AI thinks you are a person that should be pinned as an expert on a topic, it will ask you to confirm this.</span></span> 

















## <a name="see-also"></a><span data-ttu-id="96570-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="96570-131">See also</span></span>



  






