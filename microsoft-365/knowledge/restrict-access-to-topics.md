---
title: トピックへのアクセスを制限する
description: トピックが検出されるのを防ぐために除外する方法。
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
ms.openlocfilehash: f7e8406ee7090387d4500f69955330466f28c6c0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976147"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="47d08-103">トピック エクスペリエンスのトピックへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="47d08-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="47d08-104">トピック エクスペリエンスでは、組織内の関係者は、特定のトピックが検出され、ライセンスされたユーザーに公開されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47d08-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="47d08-105">たとえば、まだ情報を公開しないプロジェクトに取り組む場合があります。</span><span class="sxs-lookup"><span data-stu-id="47d08-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="47d08-106">サイトOffice、その他のリソースに対する 365 のアクセス許可を使用すると、トピック エクスペリエンスのユーザーはトピック内の機密情報を表示することはできませんが、特定のトピックが検出されるのを防ぐための追加のセーフガードがあります。</span><span class="sxs-lookup"><span data-stu-id="47d08-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="47d08-107">ナレッジ管理者はナレッジ ネットワークの設定を制御してトピックが検出されるのを防ぐ一方で、ナレッジ マネージャーや他の関係者は、この作業を共同で行う方法を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="47d08-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="47d08-108">この記事では、AI を介してトピックが識別されるのを防ぐ方法や、環境内で追加のセキュリティ保護として見なされる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47d08-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="47d08-109">トピック エクスペリエンスでは、トピック内でユーザーが Office 365 のアクセス許可を介してアクセスできない内容を表示することは許可されません。</span><span class="sxs-lookup"><span data-stu-id="47d08-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="47d08-110">ユーザーがトピックを表示できる場合でも、表示する Office 365 のアクセス許可を持たなくても、そのユーザーのファイル、サイト、およびページは表示されません。</span><span class="sxs-lookup"><span data-stu-id="47d08-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="47d08-111">機密ファイルへのアクセス許可が正しく設定されていることを確認することは、主なセキュリティ保護策である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47d08-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="47d08-112">トピックが特定されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="47d08-112">Prevent topics from being identified</span></span>

<span data-ttu-id="47d08-113">ナレッジ管理者は、最初のインデックス作成で特定のトピックが見つからないのを防ぐことで、特定のトピックへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="47d08-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="47d08-114">これを行うには、Microsoft 365 管理センターのナレッジ ネットワークの管理設定に 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="47d08-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="47d08-115">[トピックの検出から除外する SharePoint](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)サイトを選択する : この設定を使用すると、特定の SharePoint サイトがトピックに対してクロールされるのを防ぐのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="47d08-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="47d08-116">[名前でトピックを除外](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)する : 管理者は、この設定を使用して、特定のトピックが名前で検出されるのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="47d08-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="47d08-117">サポート技術情報ネットワークの管理者設定では、管理者は CSV ファイルで除外するトピックの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="47d08-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="47d08-118">トピック名と完全に一致するトピックまたは部分的に一致するトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="47d08-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="47d08-119">特定のユーザーによってトピックが表示されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="47d08-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="47d08-120">ナレッジ管理者は、組織内 [のトピックを表示できるユーザーを選択することもできます](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)。</span><span class="sxs-lookup"><span data-stu-id="47d08-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="47d08-121">この設定では、すべてのトピックを表示できるライセンスユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="47d08-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="47d08-122">たとえば、パイロット環境では、小規模なユーザー グループだけがトピックを表示できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="47d08-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="47d08-123">トピックを表示から削除する</span><span class="sxs-lookup"><span data-stu-id="47d08-123">Remove topics from being viewed</span></span>

<span data-ttu-id="47d08-124">ナレッジ マネージャーは、トピック [を削除](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) して、ユーザーに表示されなくなったトピックを削除できます。</span><span class="sxs-lookup"><span data-stu-id="47d08-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="47d08-125">トピック センター **の [** トピックの管理] ページで、ナレッジ マネージャーは特定のトピックを拒否して表示を防ぐことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="47d08-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="47d08-126">トピックが推奨または確認済み状態の場合に関係なく、トピックを削除できます。</span><span class="sxs-lookup"><span data-stu-id="47d08-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="47d08-127">削除されたトピックは、必要に応じて後で表示可能なトピックとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="47d08-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="47d08-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="47d08-128">See also</span></span>



  






