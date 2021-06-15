---
title: Microsoft Viva Topics のセキュリティとプライバシー
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft Viva Topics のセキュリティとプライバシーを計画する方法について説明します。
ms.openlocfilehash: b8c82b1914df739ea9086a4ce1585733a7b6d854
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925493"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a><span data-ttu-id="59a52-103">Microsoft Viva Topics のセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="59a52-103">Microsoft Viva Topics security and privacy</span></span>

<span data-ttu-id="59a52-104">トピックでは、Microsoft 365 の既存のコンテンツ セキュリティ機能と管理コントロールを使用して、組織内のユーザーに表示される AI 生成コンテンツを制御します。</span><span class="sxs-lookup"><span data-stu-id="59a52-104">Topics uses existing content security features in Microsoft 365, along with administrative controls, to control what AI-generated content is shown to users in your organization.</span></span> <span data-ttu-id="59a52-105">これは、特定のユーザーがトピックMicrosoft 365表示できる内容を決定するセキュリティ設定 (サイト、ファイル、およびフォルダーへのアクセス許可) と Topics 管理設定の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="59a52-105">It is the combination of Microsoft 365 security settings (permissions to sites, files, and folders) and Topics admin settings that determine what a given user can see in topics.</span></span>

<span data-ttu-id="59a52-106">トピックを設定しても、組織内のコンテンツに対する既存のアクセス制御は一切変更されません。</span><span class="sxs-lookup"><span data-stu-id="59a52-106">Setting up Topics does not modify any existing access controls on content in your organization.</span></span> <span data-ttu-id="59a52-107">ユーザーには、そのユーザーが既にアクセス権を持っているコンテンツのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-107">Users will only see what they already have access to.</span></span>

<span data-ttu-id="59a52-108">この記事では、セキュリティの観点からトピックがどのように機能し、ナレッジ管理者とナレッジ マネージャーがトピックの表示を制御する必要があるオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="59a52-108">This article describes how Topics works from a security perspective and the options that knowledge administrators and knowledge managers have to control topic visibility.</span></span> <span data-ttu-id="59a52-109">トピックの計画の一環として、この [記事をお読みください](plan-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="59a52-109">Read this article as part of your [planning for Topics](plan-topic-experiences.md).</span></span>

<span data-ttu-id="59a52-110">この記事を読む前に、[トピック](topic-experiences-overview.md)とは[](topic-center-overview.md)何か、トピック センター [](manage-topics.md) 、トピック センターのトピックを操作する方法について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="59a52-110">You should be familiar with [what Topics is](topic-experiences-overview.md), the [topic center](topic-center-overview.md), and how to [work with topics in the topic center](manage-topics.md) before you read this article.</span></span>

## <a name="what-users-can-see-in-topics"></a><span data-ttu-id="59a52-111">トピックでユーザーに表示できる内容</span><span class="sxs-lookup"><span data-stu-id="59a52-111">What users can see in topics</span></span>

<span data-ttu-id="59a52-112">トピックを表示するには、次の項目を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59a52-112">To see topics, a user must:</span></span>

- <span data-ttu-id="59a52-113">Viva Topics ライセンスを持つ</span><span class="sxs-lookup"><span data-stu-id="59a52-113">Have a Viva Topics license</span></span>
- <span data-ttu-id="59a52-114">トピック ビューアー [、投稿者](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)、または [ナレッジ マネージャーになる](topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="59a52-114">Be a [topic viewer](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [contributor, or knowledge manager](topic-experiences-user-permissions.md)</span></span>

<span data-ttu-id="59a52-115">これら 2 つの機能により、ユーザーはトピック センターにアクセスし、ハイライトとトピック カードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="59a52-115">These two things give users view access to the topic center and allow them to see highlights and topic cards.</span></span>

<span data-ttu-id="59a52-116">トピック投稿者には、 [トピックの作成](topic-experiences-user-permissions.md) と編集のアクセス許可が追加され、ナレッジ マネージャーはトピックを確認または削除できます。</span><span class="sxs-lookup"><span data-stu-id="59a52-116">Topic contributors additionally have [create and edit](topic-experiences-user-permissions.md) permissions for topics, and knowledge managers can confirm or remove topics.</span></span>

<span data-ttu-id="59a52-117">トピックが最初に検出された場合、ナレッジ マネージャーはトピック センターでトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="59a52-117">When a topic is first discovered, knowledge managers can see it in the topic center.</span></span> <span data-ttu-id="59a52-118">トピックの完成度と関連性に応じて、トピック 閲覧者はトピック カードに表示されるトピックを表示する場合と表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="59a52-118">Depending on the completeness and relevance of the topic, topic viewers may or may not see the topic presented in topic cards.</span></span>

<span data-ttu-id="59a52-119">トピックには、AI によって生成された情報と、トピック投稿者またはナレッジ マネージャーによって追加または編集された情報を含めできます。</span><span class="sxs-lookup"><span data-stu-id="59a52-119">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

- <span data-ttu-id="59a52-120">AI によって追加されたトピックの情報は、ソース コンテンツにアクセスできるユーザーにしか表示されません。</span><span class="sxs-lookup"><span data-stu-id="59a52-120">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
- <span data-ttu-id="59a52-121">トピック投稿者またはナレッジ マネージャーによって手動で追加または編集されたテキストは、トピックを表示できるすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-121">Text that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="59a52-122">トピック ビューアーと投稿者は、トピック センターで確認済みトピックと発行済みトピックの一覧を表示できますが、特定のユーザーに表示されるトピックの詳細は、ソース 資料に対するアクセス許可と、トピックが手動で編集されたかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="59a52-122">Topic viewers and contributors can see the list of confirmed and published topics in the topic center, but the topic details that a given person can see depends on the permissions that they have to the source material and on whether the topic has been manually edited.</span></span>

<span data-ttu-id="59a52-123">次の表は、ユーザー (トピック 閲覧者、投稿者、ナレッジ マネージャー) が、アクセス許可に基づいて特定のトピックで表示できる内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="59a52-123">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="59a52-124">トピック項目</span><span class="sxs-lookup"><span data-stu-id="59a52-124">Topic item</span></span>|<span data-ttu-id="59a52-125">ユーザーに表示される内容</span><span class="sxs-lookup"><span data-stu-id="59a52-125">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="59a52-126">トピック名</span><span class="sxs-lookup"><span data-stu-id="59a52-126">Topic name</span></span>|<span data-ttu-id="59a52-127">ユーザーはトピック センターでトピックのトピック名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="59a52-127">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="59a52-128">一部のトピックは、ユーザーがソース コンテンツに対するアクセス許可を持たなかったり、ユーザーとの関連性が低い場合に表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="59a52-128">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="59a52-129">トピックの説明</span><span class="sxs-lookup"><span data-stu-id="59a52-129">Topic description</span></span>|<span data-ttu-id="59a52-130">AI で生成された説明は、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-130">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="59a52-131">手動で入力または編集された説明は、すべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-131">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="59a52-132">連絡先</span><span class="sxs-lookup"><span data-stu-id="59a52-132">People</span></span>|<span data-ttu-id="59a52-133">ピン留めされた連絡先はすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-133">Pinned people are visible to all users.</span></span> <span data-ttu-id="59a52-134">提案された連絡先は、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-134">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="59a52-135">ファイル</span><span class="sxs-lookup"><span data-stu-id="59a52-135">Files</span></span>|<span data-ttu-id="59a52-136">ファイルは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-136">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="59a52-137">ページ</span><span class="sxs-lookup"><span data-stu-id="59a52-137">Pages</span></span>|<span data-ttu-id="59a52-138">ページは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-138">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="59a52-139">サイト</span><span class="sxs-lookup"><span data-stu-id="59a52-139">Sites</span></span>|<span data-ttu-id="59a52-140">サイトは、ソース コンテンツに対するアクセス許可を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a52-140">Sites are only visible to users who have permissions to the source content.</span></span>|

## <a name="users-personal-and-private-data"></a><span data-ttu-id="59a52-141">ユーザーの個人データと個人データ</span><span class="sxs-lookup"><span data-stu-id="59a52-141">Users' personal and private data</span></span>

<span data-ttu-id="59a52-142">Viva Topics は、指定したサイトSharePointトピックのみを検出します。</span><span class="sxs-lookup"><span data-stu-id="59a52-142">Viva Topics only discovers topics in the SharePoint sites that you specify.</span></span> <span data-ttu-id="59a52-143">個人用メールやメールなどのユーザーの個人用OneDriveは含まれません。</span><span class="sxs-lookup"><span data-stu-id="59a52-143">Users’ personal storage such as personal mail or OneDrive is not included.</span></span>

## <a name="best-practices"></a><span data-ttu-id="59a52-144">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="59a52-144">Best practices</span></span>

<span data-ttu-id="59a52-145">トピックでは、コンテンツに対する既存のアクセス許可に基づいてユーザーに情報を提示します。</span><span class="sxs-lookup"><span data-stu-id="59a52-145">Topics presents information to users based on their existing permissions to content.</span></span> <span data-ttu-id="59a52-146">Microsoft 365は、機密性の高いコンテンツが適切なユーザーに制限されるさまざまな方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="59a52-146">Microsoft 365 provides a variety of ways to ensure that sensitive content is restricted to appropriate users.</span></span> <span data-ttu-id="59a52-147">標準的なチームまたはサイトのアクセス許可を超えて、機密ラベルまたは[](../compliance/dlp-learn-about-dlp.md)データ損失防止を使用して、コンテンツへの[](/azure/active-directory/governance/access-reviews-overview)アクセスを制限し、ユーザーによる機密情報へのアクセスを定期的に確認できます。 [](../compliance/sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="59a52-147">Beyond standard team or site permissions, you can use [sensitivity labels](../compliance/sensitivity-labels.md) or [data loss prevention](../compliance/dlp-learn-about-dlp.md) to restrict access to content and [access reviews](/azure/active-directory/governance/access-reviews-overview) to periodically review user access to sensitive information.</span></span>

<span data-ttu-id="59a52-148">これらのツールを使用して、コンテンツのアクセス許可が組織内で適切に設定されるのを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59a52-148">We recommend that you use these tools to ensure that your content permissions are set appropriately inside your organization.</span></span> <span data-ttu-id="59a52-149">その後、トピック エクスペリエンスにより、有用で適切な情報をユーザーに提供することができます。</span><span class="sxs-lookup"><span data-stu-id="59a52-149">Topic experiences can then provide useful and appropriate information to your users.</span></span>

<span data-ttu-id="59a52-150">トピック エクスペリエンスから完全に除外するトピックがある場合は、次の方法も実行できます。</span><span class="sxs-lookup"><span data-stu-id="59a52-150">If there are topics that you want to exclude entirely from topic experiences, you can also:</span></span>

- <span data-ttu-id="59a52-151">[トピック検出からSharePointサイトを除外します](topic-experiences-discovery.md#select-sharepoint-topic-sources)。</span><span class="sxs-lookup"><span data-stu-id="59a52-151">[Exclude sensitive SharePoint sites from topic discovery](topic-experiences-discovery.md#select-sharepoint-topic-sources).</span></span> <span data-ttu-id="59a52-152">これらのサイトのコンテンツは、トピックのエクスペリエンスに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="59a52-152">Content in these sites will not appear in topic experiences.</span></span>

- <span data-ttu-id="59a52-153">[トピックを名前で除外します](topic-experiences-discovery.md#exclude-topics-by-name)。</span><span class="sxs-lookup"><span data-stu-id="59a52-153">[Exclude topics by name](topic-experiences-discovery.md#exclude-topics-by-name).</span></span> <span data-ttu-id="59a52-154">明示的に除外されたトピックは、トピックのエクスペリエンスに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="59a52-154">Topics explicitly excluded will not appear in topic experiences.</span></span>

- <span data-ttu-id="59a52-155">ナレッジ マネージャーにトピック センターのトピックを削除します。</span><span class="sxs-lookup"><span data-stu-id="59a52-155">Have knowledge managers remove topics in the topic center.</span></span>

<span data-ttu-id="59a52-156">さらに、次のベスト プラクティスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59a52-156">Additionally, we recommend these best practices:</span></span>

- <span data-ttu-id="59a52-157">組織の異なる領域からナレッジ マネージャーを募集します。</span><span class="sxs-lookup"><span data-stu-id="59a52-157">Recruit knowledge managers from different areas of your organization.</span></span> <span data-ttu-id="59a52-158">さまざまな専門知識を持つナレッジ マネージャーと、AI が使用する基になるコンテンツへのアクセスを持つことは、ユーザーにとって最も有用な知識をキュレートし、見つかった場合に機密情報を削除するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="59a52-158">Having knowledge managers with a variety of expertise - and access to the underlying content used by AI - can help you curate the most useful knowledge for your users and remove sensitive information if found.</span></span>

- <span data-ttu-id="59a52-159">変更を要求するワークフローを設定します。</span><span class="sxs-lookup"><span data-stu-id="59a52-159">Set up a workflow for requesting changes.</span></span> <span data-ttu-id="59a52-160">ナレッジ マネージャーまたはチームまたはサイトの所有者は、新しいプロジェクトが組織内で開始される場合や、不適切なアクセス許可設定を持つコンテンツが見つかった場合に、トピックやサイトの除外を要求できるプロセスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59a52-160">Knowledge managers or team or site owners should have a process by which they can request exclusion of topics or sites as new projects are started within your organization or if they find content with inappropriate permissions settings.</span></span>

- <span data-ttu-id="59a52-161">トピックの説明を作成する際は、対象ユーザーと情報の秘密度に注意します。</span><span class="sxs-lookup"><span data-stu-id="59a52-161">Be aware of the audience and the sensitivity of information when creating topic descriptions.</span></span> <span data-ttu-id="59a52-162">これらの説明は、トピックのソース コンテンツに対するアクセス許可を持たないユーザーに表示されるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="59a52-162">These descriptions may be visible to users who don't have permissions to the source content for the topic.</span></span>

<span data-ttu-id="59a52-163">個々のトピック ページに対するアクセス許可を変更して、特定のユーザー グループにアクセスを絞り込むこともできますが、必要になる管理作業が多いため、この方法はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="59a52-163">While you can change the permissions on individual topic pages to narrow access to a specific group of users, we don't recommend this approach because of the high degree of administrative effort required.</span></span>

## <a name="see-also"></a><span data-ttu-id="59a52-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="59a52-164">See also</span></span>

[<span data-ttu-id="59a52-165">3 層の保護を使って Teams を構成する</span><span class="sxs-lookup"><span data-stu-id="59a52-165">Configure Teams with three tiers of protection</span></span>](../solutions/configure-teams-three-tiers-protection.md)

[<span data-ttu-id="59a52-166">トピック エクスペリエンスの計画</span><span class="sxs-lookup"><span data-stu-id="59a52-166">Plan topic experiences</span></span>](plan-topic-experiences.md)

[<span data-ttu-id="59a52-167">トピック エクスペリエンスを設定する</span><span class="sxs-lookup"><span data-stu-id="59a52-167">Set up topic experiences</span></span>](set-up-topic-experiences.md)
