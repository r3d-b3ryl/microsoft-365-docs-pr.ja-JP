---
title: Microsoft のトピックのセキュリティとプライバシー
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft 多くのトピックのセキュリティとプライバシーを計画する方法について説明します。
ms.openlocfilehash: be5be01bce117a80bd95ee268c193889eccea67f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107794"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a><span data-ttu-id="3900a-103">Microsoft のトピックのセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="3900a-103">Microsoft Viva Topics security and privacy</span></span>

<span data-ttu-id="3900a-104">トピックでは、Microsoft 365 の既存のコンテンツ セキュリティ機能と管理コントロールを使用して、組織内のユーザーに表示される AI 生成コンテンツを制御します。</span><span class="sxs-lookup"><span data-stu-id="3900a-104">Topics uses existing content security features in Microsoft 365, along with administrative controls, to control what AI-generated content is shown to users in your organization.</span></span> <span data-ttu-id="3900a-105">Microsoft 365 のセキュリティ設定 (サイト、ファイル、フォルダーに対するアクセス許可) と Topics 管理設定の組み合わせによって、特定のユーザーがトピックに表示できる内容を決定します。</span><span class="sxs-lookup"><span data-stu-id="3900a-105">It is the combination of Microsoft 365 security settings (permissions to sites, files, and folders) and Topics admin settings that determine what a given user can see in topics.</span></span>

<span data-ttu-id="3900a-106">トピックを設定しても、組織内のコンテンツに対する既存のアクセス制御は変更されない。</span><span class="sxs-lookup"><span data-stu-id="3900a-106">Setting up Topics does not modify any existing access controls on content in your organization.</span></span> <span data-ttu-id="3900a-107">ユーザーには、既にアクセス権を持っているものだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-107">Users will only see what they already have access to.</span></span>

<span data-ttu-id="3900a-108">この記事では、セキュリティの観点からトピックがどのように機能し、ナレッジ管理者およびナレッジ マネージャーがトピックの可視性を制御するために必要なオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3900a-108">This article describes how Topics works from a security perspective and the options that knowledge administrators and knowledge managers have to control topic visibility.</span></span> <span data-ttu-id="3900a-109">トピックの計画の一環として、この [記事をお読みください](plan-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="3900a-109">Read this article as part of your [planning for Topics](plan-topic-experiences.md).</span></span>

<span data-ttu-id="3900a-110">この記事を読む前に、[トピック](topic-experiences-overview.md)の[](topic-center-overview.md)内容、トピック センター、[](manage-topics.md)トピック センターのトピックの操作方法について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3900a-110">You should be familiar with [what Topics is](topic-experiences-overview.md), the [topic center](topic-center-overview.md), and how to [work with topics in the topic center](manage-topics.md) before you read this article.</span></span>

## <a name="what-users-can-see-in-topics"></a><span data-ttu-id="3900a-111">トピックでユーザーに表示できる内容</span><span class="sxs-lookup"><span data-stu-id="3900a-111">What users can see in topics</span></span>

<span data-ttu-id="3900a-112">トピックを表示するには、ユーザーは次の条件を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3900a-112">To see topics, a user must:</span></span>

- <span data-ttu-id="3900a-113">多くのトピックのライセンスを持っている</span><span class="sxs-lookup"><span data-stu-id="3900a-113">Have a Viva Topics license</span></span>
- <span data-ttu-id="3900a-114">トピック閲覧[者、投稿者](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)[、またはナレッジ マネージャーになる](topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="3900a-114">Be a [topic viewer](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [contributor, or knowledge manager](topic-experiences-user-permissions.md)</span></span>

<span data-ttu-id="3900a-115">これら 2 つの機能により、ユーザーはトピック センターにアクセスし、ハイライトとトピック カードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3900a-115">These two things give users view access to the topic center and allow them to see highlights and topic cards.</span></span>

<span data-ttu-id="3900a-116">また、トピックの投稿者はトピック [の作成](topic-experiences-user-permissions.md) と編集のアクセス許可を持ち、ナレッジ マネージャーはトピックを確認または削除できます。</span><span class="sxs-lookup"><span data-stu-id="3900a-116">Topic contributors additionally have [create and edit](topic-experiences-user-permissions.md) permissions for topics, and knowledge managers can confirm or remove topics.</span></span>

<span data-ttu-id="3900a-117">トピックが初めて検出された場合、ナレッジ マネージャーはトピック センターでトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3900a-117">When a topic is first discovered, knowledge managers can see it in the topic center.</span></span> <span data-ttu-id="3900a-118">トピックの完成度と関連性によっては、トピック の閲覧者にトピック カードに示されているトピックが表示される場合と表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3900a-118">Depending on the completeness and relevance of the topic, topic viewers may or may not see the topic presented in topic cards.</span></span>

<span data-ttu-id="3900a-119">トピックには、AI によって生成される情報と、トピックの投稿者またはナレッジ マネージャーによって追加または編集された情報を含めできます。</span><span class="sxs-lookup"><span data-stu-id="3900a-119">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

- <span data-ttu-id="3900a-120">AI によって追加されたトピック内の情報は、ソース コンテンツにアクセスできるユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-120">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
- <span data-ttu-id="3900a-121">トピック投稿者またはナレッジ マネージャーによって手動で追加または編集されたテキストは、トピックを表示できるすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-121">Text that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="3900a-122">トピック閲覧者と投稿者は、確認済みおよび公開されたトピックの一覧をトピック センターで確認できますが、特定のユーザーに表示されるトピックの詳細は、ソース 資料に対するアクセス許可と、トピックが手動で編集されたかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3900a-122">Topic viewers and contributors can see the list of confirmed and published topics in the topic center, but the topic details that a given person can see depends on the permissions that they have to the source material and on whether the topic has been manually edited.</span></span>

<span data-ttu-id="3900a-123">次の表では、ユーザー (トピック閲覧者、投稿者、ナレッジ マネージャー) がアクセス許可に基づいて特定のトピックで表示できる内容を示します。</span><span class="sxs-lookup"><span data-stu-id="3900a-123">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="3900a-124">トピック 項目</span><span class="sxs-lookup"><span data-stu-id="3900a-124">Topic item</span></span>|<span data-ttu-id="3900a-125">ユーザーに表示される情報</span><span class="sxs-lookup"><span data-stu-id="3900a-125">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="3900a-126">トピック名</span><span class="sxs-lookup"><span data-stu-id="3900a-126">Topic name</span></span>|<span data-ttu-id="3900a-127">ユーザーは、トピック センターですべてのトピックのトピック名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3900a-127">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="3900a-128">一部のトピックは、ユーザーとの関連性が低い場合には表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3900a-128">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="3900a-129">トピックの説明</span><span class="sxs-lookup"><span data-stu-id="3900a-129">Topic description</span></span>|<span data-ttu-id="3900a-130">AI によって生成された説明は、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-130">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="3900a-131">手動で入力または編集した説明は、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-131">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="3900a-132">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3900a-132">People</span></span>|<span data-ttu-id="3900a-133">ピン留めされたユーザーは、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-133">Pinned people are visible to all users.</span></span> <span data-ttu-id="3900a-134">提案されたユーザーは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-134">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="3900a-135">Files</span><span class="sxs-lookup"><span data-stu-id="3900a-135">Files</span></span>|<span data-ttu-id="3900a-136">ファイルは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-136">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="3900a-137">ページ</span><span class="sxs-lookup"><span data-stu-id="3900a-137">Pages</span></span>|<span data-ttu-id="3900a-138">ページは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-138">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="3900a-139">サイト</span><span class="sxs-lookup"><span data-stu-id="3900a-139">Sites</span></span>|<span data-ttu-id="3900a-140">サイトは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900a-140">Sites are only visible to users who have permissions to the source content.</span></span>|

## <a name="best-practices"></a><span data-ttu-id="3900a-141">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3900a-141">Best practices</span></span>

<span data-ttu-id="3900a-142">トピックでは、コンテンツに対する既存のアクセス許可に基づいて、ユーザーに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3900a-142">Topics presents information to users based on their existing permissions to content.</span></span> <span data-ttu-id="3900a-143">Microsoft 365 には、機密性の高いコンテンツが適切なユーザーに制限されるさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="3900a-143">Microsoft 365 provides a variety of ways to ensure that sensitive content is restricted to appropriate users.</span></span> <span data-ttu-id="3900a-144">標準的なチームまたはサイトのアクセス許可を超えて、機密ラベルまたは[](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)データ損失防止を使用して、コンテンツおよび[](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)アクセス レビューへのアクセスを制限して、機密情報へのユーザー アクセスを定期的に確認できます。 [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)</span><span class="sxs-lookup"><span data-stu-id="3900a-144">Beyond standard team or site permissions, you can use [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) or [data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to restrict access to content and [access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) to periodically review user access to sensitive information.</span></span>

<span data-ttu-id="3900a-145">これらのツールを使用して、コンテンツのアクセス許可が組織内で適切に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3900a-145">We recommend that you use these tools to ensure that your content permissions are set appropriately inside your organization.</span></span> <span data-ttu-id="3900a-146">トピック エクスペリエンスは、有用で適切な情報をユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="3900a-146">Topic experiences can then provide useful and appropriate information to your users.</span></span>

<span data-ttu-id="3900a-147">トピックエクスペリエンスから完全に除外するトピックがある場合は、次の方法も実行できます。</span><span class="sxs-lookup"><span data-stu-id="3900a-147">If there are topics that you want to exclude entirely from topic experiences, you can also:</span></span>

- <span data-ttu-id="3900a-148">[機密性の高い SharePoint サイトをトピックの検出から除外します](topic-experiences-discovery.md#select-sharepoint-topic-sources)。</span><span class="sxs-lookup"><span data-stu-id="3900a-148">[Exclude sensitive SharePoint sites from topic discovery](topic-experiences-discovery.md#select-sharepoint-topic-sources).</span></span> <span data-ttu-id="3900a-149">これらのサイトのコンテンツは、トピック エクスペリエンスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="3900a-149">Content in these sites will not appear in topic experiences.</span></span>

- <span data-ttu-id="3900a-150">[名前でトピックを除外します](topic-experiences-discovery.md#exclude-topics-by-name)。</span><span class="sxs-lookup"><span data-stu-id="3900a-150">[Exclude topics by name](topic-experiences-discovery.md#exclude-topics-by-name).</span></span> <span data-ttu-id="3900a-151">明示的に除外されたトピックは、トピックエクスペリエンスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="3900a-151">Topics explicitly excluded will not appear in topic experiences.</span></span>

- <span data-ttu-id="3900a-152">ナレッジ マネージャーにトピック センターのトピックを削除する。</span><span class="sxs-lookup"><span data-stu-id="3900a-152">Have knowledge managers remove topics in the topic center.</span></span>

<span data-ttu-id="3900a-153">さらに、次のベスト プラクティスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3900a-153">Additionally, we recommend these best practices:</span></span>

- <span data-ttu-id="3900a-154">組織の異なる領域からナレッジ マネージャーを募集します。</span><span class="sxs-lookup"><span data-stu-id="3900a-154">Recruit knowledge managers from different areas of your organization.</span></span> <span data-ttu-id="3900a-155">さまざまな専門知識を持つ知識マネージャーや、AI が使用する基礎となるコンテンツへのアクセス権を持つ知識マネージャーは、ユーザーにとって最も有用な知識を管理し、見つかった場合は機密情報を削除するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3900a-155">Having knowledge managers with a variety of expertise - and access to the underlying content used by AI - can help you curate the most useful knowledge for your users and remove sensitive information if found.</span></span>

- <span data-ttu-id="3900a-156">変更を要求するワークフローを設定します。</span><span class="sxs-lookup"><span data-stu-id="3900a-156">Set up a workflow for requesting changes.</span></span> <span data-ttu-id="3900a-157">ナレッジ マネージャーまたはチームまたはサイトの所有者は、組織内で新しいプロジェクトが開始された場合、または不適切なアクセス許可設定を持つコンテンツが見つけた場合に、トピックまたはサイトの除外を要求できるプロセスを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3900a-157">Knowledge managers or team or site owners should have a process by which they can request exclusion of topics or sites as new projects are started within your organization or if they find content with inappropriate permissions settings.</span></span>

- <span data-ttu-id="3900a-158">トピックの説明を作成する際は、対象ユーザーと情報の感度に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3900a-158">Be aware of the audience and the sensitivity of information when creating topic descriptions.</span></span> <span data-ttu-id="3900a-159">これらの説明は、トピックのソース コンテンツに対するアクセス許可を持たなかったユーザーに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3900a-159">These descriptions may be visible to users who don't have permissions to the source content for the topic.</span></span>

<span data-ttu-id="3900a-160">個々のトピック ページのアクセス許可を変更して、特定のユーザー グループへのアクセスを絞り込むすることもできますが、管理作業が高く必要なので、この方法はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="3900a-160">While you can change the permissions on individual topic pages to narrow access to a specific group of users, we don't recommend this approach because of the high degree of administrative effort required.</span></span>

## <a name="see-also"></a><span data-ttu-id="3900a-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="3900a-161">See also</span></span>

[<span data-ttu-id="3900a-162">3 層の保護を使って Teams を構成する</span><span class="sxs-lookup"><span data-stu-id="3900a-162">Configure Teams with three tiers of protection</span></span>](../solutions/configure-teams-three-tiers-protection.md)

[<span data-ttu-id="3900a-163">トピック エクスペリエンスの計画</span><span class="sxs-lookup"><span data-stu-id="3900a-163">Plan topic experiences</span></span>](plan-topic-experiences.md)

[<span data-ttu-id="3900a-164">トピック エクスペリエンスを設定する</span><span class="sxs-lookup"><span data-stu-id="3900a-164">Set up topic experiences</span></span>](set-up-topic-experiences.md)
