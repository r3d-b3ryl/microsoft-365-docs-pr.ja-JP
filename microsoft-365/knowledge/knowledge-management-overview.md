---
title: ナレッジ管理の概要 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex のナレッジ管理の概要。
ms.openlocfilehash: 99b0d0ece9ef8271666b1978db7947f3e3f2a4e8
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540075"
---
# <a name="knowledge-management-0verview-preview"></a><span data-ttu-id="73875-103">ナレッジマネジメント 0verview (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="73875-103">Knowledge management 0verview (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="73875-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="73875-104">The content in this article is for Project Cortex Private Preview.</span></span> [<span data-ttu-id="73875-105">詳細については、「Project Cortex」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73875-105">Find out more about Project Cortex</span></span>](https://aka.ms/projectcortex) 

<span data-ttu-id="73875-106">ナレッジ管理では、microsoft AI テクノロジ、Microsoft 365、Delve、検索、およびその他のコンポーネントとサービスを使用して、Microsoft 365 環境でナレッジネットワークを構築します。</span><span class="sxs-lookup"><span data-stu-id="73875-106">Knowledge management uses Microsoft AI technology, Microsoft 365, Delve, Search, and other components and services to build a knowledge network in your Microsoft 365 environment.</span></span> 

   ![ナレッジ管理フロー](../media/content-understanding/knowledge-management-flowchart.png) </br> 

<span data-ttu-id="73875-108">これは、Outlook、Teams、SharePoint など、毎日使用するアプリでユーザーに情報を配信することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="73875-108">It's goal is to deliver information to you users in apps they use everyday, such as Outlook, Teams, and SharePoint.</span></span>

<span data-ttu-id="73875-109">たとえば、ユーザーの電子メール、SharePoint サイト、または Teams の会話に、わかりやすい用語が表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="73875-109">For example, users see unfamiliar terms in their emails, SharePoint sites, or in Teams conversations, that they want to know more about.</span></span> <span data-ttu-id="73875-110">ナレッジ管理は、AI を使用してこれらの**トピック**を自動的に検索して識別し、それらに関する情報 (短い説明、トピックの対象者の専門家、およびそれに関連するサイト、ファイル、ページなど) をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="73875-110">Knowledge management uses AI to automatically searches for and identifies these **topics**, and compiles information about them, such as a short description, subject matter experts on the topic, and sites, files, and pages that are related to it.</span></span> <span data-ttu-id="73875-111">必要に応じて、トピック情報を更新するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="73875-111">You can choose to update the topic information as needed.</span></span> <span data-ttu-id="73875-112">その後、ユーザーがトピックを利用できるようにすることができます。つまり、Outlook、Teams、SharePoint などのアプリに表示されるトピックのすべてのインスタンスについて、テキストが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="73875-112">You can then make the topics available to your users, which means that for every instance of the topic that appears in apps such as Outlook, Teams, and SharePoint, the text will be highlighted.</span></span> <span data-ttu-id="73875-113">トピックの詳細については、トピックを選択して詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="73875-113">Users can choose to select the topic to learn more about it through the topic details.</span></span>


## <a name="topic-discovery"></a><span data-ttu-id="73875-114">トピックの検出</span><span class="sxs-lookup"><span data-stu-id="73875-114">Topic discovery</span></span>

<span data-ttu-id="73875-115">ナレッジ管理は、Microsoft AI テクノロジを使用して、Office 365 環境の**トピック**を検索します。</span><span class="sxs-lookup"><span data-stu-id="73875-115">Knowledge Management uses Microsoft AI technology to search for **topics** in your Office 365 environment.</span></span>

<span data-ttu-id="73875-116">トピックは、意味のある、または重要な語句または用語です。</span><span class="sxs-lookup"><span data-stu-id="73875-116">A topic is a phrase or term that is organizationally significant or important.</span></span> <span data-ttu-id="73875-117">組織にとっては特定の意味があります。また、それに関連するリソースがあります。これにより、ユーザーはそれを理解し、より詳細な情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="73875-117">It has a specific meaning to the organization, and has resources related to it that can help people understand what it is and find more information about it.</span></span>

<span data-ttu-id="73875-118">トピックが検出されると、次のようなトピック検出によって収集された情報を含むトピック**ページ**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="73875-118">When a topic is discovered, a **topic page** is created for it that contains information that was gathered through topic discovery, such as:</span></span>

- <span data-ttu-id="73875-119">トピックの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="73875-119">A short description of the topic.</span></span>
- <span data-ttu-id="73875-120">トピックについて精通している可能性があるユーザー。</span><span class="sxs-lookup"><span data-stu-id="73875-120">Users who might be knowledgeable about the topic.</span></span>
- <span data-ttu-id="73875-121">トピックに関連するファイル、ページ、およびサイト。</span><span class="sxs-lookup"><span data-stu-id="73875-121">Files, pages, and sites that are related to the topic.</span></span>


## <a name="topic-management"></a><span data-ttu-id="73875-122">トピック管理</span><span class="sxs-lookup"><span data-stu-id="73875-122">Topic management</span></span>

<span data-ttu-id="73875-123">トピック管理は、組織の**トピックセンター**で行われます。</span><span class="sxs-lookup"><span data-stu-id="73875-123">Topic management is done in your organization's **topic center**.</span></span> <span data-ttu-id="73875-124">トピックセンターサイトはセットアップ時に作成され、組織のためのナレッジセンターとして機能します。</span><span class="sxs-lookup"><span data-stu-id="73875-124">The topic center site is created during setup and serves as your center of knowledge for your organization.</span></span> <span data-ttu-id="73875-125">ここには、環境で検出されたすべてのトピックの一覧と、これらのトピックに対して作成されたすべてのトピックページが含まれています。</span><span class="sxs-lookup"><span data-stu-id="73875-125">It will contain a list of all topics that were discovered in your environment, as well as all topic pages that were created for these topics.</span></span> 

<span data-ttu-id="73875-126">適切なアクセス許可を付与されたユーザーは、トピックセンターで次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="73875-126">Users who are provided the correct permissions will be able to do the following in the topic center:</span></span>

- <span data-ttu-id="73875-127">テナントで検出されたトピックを確認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="73875-127">Confirm or reject topics that were discovered in your tenant.</span></span>
- <span data-ttu-id="73875-128">必要に応じて、新しいトピックを手動で作成します (たとえば、十分な情報が得られなかった場合は、それを AI で検出するため)。</span><span class="sxs-lookup"><span data-stu-id="73875-128">Create new topics manually as needed (for example, if not enough information was provided for it to be discovered through AI).</span></span>
- <span data-ttu-id="73875-129">既存のトピックページを編集します。</span><span class="sxs-lookup"><span data-stu-id="73875-129">Edit existing topic pages.</span></span></br>

<span data-ttu-id="73875-130">詳細について[は、トピックセンターの「Work with topic](work-with-topics.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73875-130">See [Work with topic in the topic center](work-with-topics.md) for more information.</span></span>  


## <a name="admin-controls"></a><span data-ttu-id="73875-131">管理コントロール</span><span class="sxs-lookup"><span data-stu-id="73875-131">Admin controls</span></span>

<span data-ttu-id="73875-132">Microsoft 365 管理センターの管理者コントロールを使用すると、ナレッジネットワークを管理できます。</span><span class="sxs-lookup"><span data-stu-id="73875-132">Admin controls in the Microsoft 365 admin center  allow you to manage your knowledge network.</span></span> <span data-ttu-id="73875-133">これにより、Microsoft 365 グローバルまたは SharePoint 管理者が次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="73875-133">They allow a Microsoft 365 global or SharePoint admin to:</span></span>

- <span data-ttu-id="73875-134">組織内のどのユーザーが自分のクライアントアプリまたは SharePoint 検索結果でトピックを参照できるようにするかを制御します。</span><span class="sxs-lookup"><span data-stu-id="73875-134">Control which users in your organization are allowed to see topics in their client apps or in SharePoint search results.</span></span>
- <span data-ttu-id="73875-135">トピックを検索するためにどの SharePoint サイトをクロールするかを制御します。</span><span class="sxs-lookup"><span data-stu-id="73875-135">Control which SharePoint sites will be crawled to search for topics.</span></span>
- <span data-ttu-id="73875-136">トピックとして使用しない特定の用語を除外するようにトピック検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="73875-136">Configure topic discovery to exclude specific terms that you don't want to be a topic.</span></span>
- <span data-ttu-id="73875-137">トピックセンターでトピックを確認または拒否することができるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="73875-137">Control which users can to confirm or reject topics in the topic center.</span></span>
- <span data-ttu-id="73875-138">トピックセンターでトピックを作成および編集できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="73875-138">Control which users can create and edit topics in the topic center.</span></span>

<span data-ttu-id="73875-139">詳細については[、「ナレッジネットワークの管理](manage-knowledge-network.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73875-139">See [Manage your knowledge network](manage-knowledge-network.md) for more information.</span></span> 

## <a name="topic-curation"></a><span data-ttu-id="73875-140">トピック (curation</span><span class="sxs-lookup"><span data-stu-id="73875-140">Topic curation</span></span>

<span data-ttu-id="73875-141">AI は、環境内で変更が発生したときに、トピックを改善するための提案を継続的に提供していきます。</span><span class="sxs-lookup"><span data-stu-id="73875-141">AI will continually work to provide you suggestions to improve your topics as changes occur in your environment.</span></span>

<span data-ttu-id="73875-142">ユーザーが毎日の作業でトピックを参照できるようにするには、それらのユーザーに対して推奨事項を提案することができます。</span><span class="sxs-lookup"><span data-stu-id="73875-142">Users who you allow access to see topics in their daily work are allowed to make suggestions to improve them.</span></span> <span data-ttu-id="73875-143">たとえば、ユーザーがトピックページを表示し、正しくない情報や追加が必要な情報を確認すると、そのトピックページにあるリンクによって、情報を更新する要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="73875-143">For example, if a user views the topic page and sees information that is incorrect or needs to be added, a link on the topic page allows them to submit a request to update the information.</span></span>

<span data-ttu-id="73875-144">さらに、適切なアクセス許可を持つユーザーは、トピックに関連する Teams 会話などのアイテムにタグを付けて、特定のトピックに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="73875-144">Additionally, users with proper permissions can tag items such as Teams conversation that are relevant to a topic, and add them to a specific topic.</span></span>




## <a name="see-also"></a><span data-ttu-id="73875-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="73875-145">See also</span></span>
[<span data-ttu-id="73875-146">ナレッジ管理の設定</span><span class="sxs-lookup"><span data-stu-id="73875-146">Set up knowledge management</span></span>](set-up-knowledge-network.md)</br>
[<span data-ttu-id="73875-147">トピックセンターの概要</span><span class="sxs-lookup"><span data-stu-id="73875-147">Topic center overview</span></span>](topic-center-overview.md)