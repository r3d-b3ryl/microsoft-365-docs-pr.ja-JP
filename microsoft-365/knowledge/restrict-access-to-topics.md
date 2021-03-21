---
title: Microsoft Viva Topics のトピックへのアクセスを制限する
description: トピックが検出されるのを防ぐためにトピックを除外する方法。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: dc344e0263bab287133ddb01ecab262440eb9e10
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925954"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="cd94d-103">Microsoft Viva Topics のトピックへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="cd94d-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="cd94d-104">Microsoft Viva では、組織内の関係者は、特定のトピックが検出され、ライセンスを受け取ったユーザーに公開されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd94d-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="cd94d-105">たとえば、まだ情報を公開しないプロジェクトに取り組む場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd94d-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="cd94d-106">サイトOffice、ファイル、その他のリソースに対する 365 のアクセス許可を使用すると、トピック エクスペリエンス ユーザーはトピック内の機密情報を表示することはできませんが、特定のトピックが検出されるのを防ぐための追加のセーフガードがあります。</span><span class="sxs-lookup"><span data-stu-id="cd94d-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="cd94d-107">ナレッジ管理者はナレッジ ネットワーク設定を制御してトピックが検出されるのを防ぐ一方で、ナレッジ マネージャーや他の関係者は、作業を共同で行う方法を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd94d-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="cd94d-108">この記事では、トピックが AI を介して識別されるのを防ぐ方法、または環境内で追加のセキュリティ保護手段として表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd94d-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="cd94d-109">ビバ トピックでは、ユーザーが 365 件のアクセス許可を使用してアクセスできないトピックを表示することはOffice重要です。</span><span class="sxs-lookup"><span data-stu-id="cd94d-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="cd94d-110">ユーザーがトピックを表示できる場合でも、Office 365 の表示権限を持つユーザーのファイル、サイト、ページは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cd94d-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="cd94d-111">機密性の高いファイルに対するアクセス許可が正しく設定されていることを確認することは、主なセキュリティ保護策である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd94d-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="cd94d-112">トピックが識別されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="cd94d-112">Prevent topics from being identified</span></span>

<span data-ttu-id="cd94d-113">ナレッジ管理者は、最初のインデックス作成で特定のトピックが見つからないのを防ぐことで、特定のトピックへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="cd94d-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="cd94d-114">このタスクを実行するには、Microsoft 365 管理センターのナレッジ ネットワーク管理者設定で 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="cd94d-114">There are two ways to do this task in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="cd94d-115">[[トピックの検出から除外する SharePoint](./topic-experiences-discovery.md#select-sharepoint-topic-sources)サイト] を選択します。この設定を使用すると、特定の SharePoint サイトがトピックに対してクロールされるのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="cd94d-115">[Select SharePoint sites to exclude from topic discovery](./topic-experiences-discovery.md#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="cd94d-116">[名前でトピックを除外する](./topic-experiences-discovery.md#exclude-topics-by-name): 管理者は、この設定を使用して、特定のトピックが名前で検出されるのを防ぐ場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd94d-116">[Exclude topics by name](./topic-experiences-discovery.md#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="cd94d-117">ナレッジ ネットワークの管理者設定では、管理者は CSV ファイルで除外するトピックの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="cd94d-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="cd94d-118">トピック名に完全一致または部分的に一致するトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="cd94d-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="cd94d-119">トピックが特定のユーザーによって表示されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="cd94d-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="cd94d-120">ナレッジ管理者は、組織内 [のトピックを表示できるユーザーを選択することもできます](./topic-experiences-knowledge-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="cd94d-120">Knowledge admins can also [select who can view topics in your organization](./topic-experiences-knowledge-rules.md).</span></span> <span data-ttu-id="cd94d-121">この設定では、すべてのトピックを表示できるライセンスユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="cd94d-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="cd94d-122">たとえば、パイロット環境では、小さなグループのユーザーだけがトピックを表示できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd94d-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="cd94d-123">トピックを表示から削除する</span><span class="sxs-lookup"><span data-stu-id="cd94d-123">Remove topics from being viewed</span></span>

<span data-ttu-id="cd94d-124">ナレッジ マネージャーは、ユーザー [がトピックを表示](./manage-topics.md) できなくなった場合に、トピックを削除できます。</span><span class="sxs-lookup"><span data-stu-id="cd94d-124">Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them.</span></span> <span data-ttu-id="cd94d-125">トピック センター **の [トピックの** 管理] ページで、ナレッジ マネージャーは特定のトピックを拒否して表示を防止できます。 </span><span class="sxs-lookup"><span data-stu-id="cd94d-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="cd94d-126">トピックは、提案または確認済み状態の場合に関係なく削除できます。</span><span class="sxs-lookup"><span data-stu-id="cd94d-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="cd94d-127">削除されたトピックは、必要に応じて表示可能なトピックとして後で追加できます。</span><span class="sxs-lookup"><span data-stu-id="cd94d-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="cd94d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd94d-128">See also</span></span>



