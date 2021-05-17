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
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500877"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="047ad-103">Microsoft Viva Topics のトピックへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="047ad-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="047ad-104">Microsoft Viva では、組織内の関係者は、特定のトピックが検出され、ライセンスを受け取ったユーザーに公開されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="047ad-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="047ad-105">たとえば、まだ情報を公開しないプロジェクトに取り組む場合があります。</span><span class="sxs-lookup"><span data-stu-id="047ad-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="047ad-106">サイトOffice 365、ファイル、その他のリソースに対するアクセス許可を使用すると、Topic Experiences ユーザーはトピック内の機密情報を表示することはできませんが、特定のトピックが検出されるのを防ぐための追加のセーフガードがあります。</span><span class="sxs-lookup"><span data-stu-id="047ad-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="047ad-107">ナレッジ管理者が設定を制御してトピックが検出されるのを防ぐ一方で、ナレッジ マネージャーや他の利害関係者は、作業を共同で行う方法を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="047ad-107">While knowledge admins control the settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="047ad-108">この記事では、トピックが AI を介して識別されるのを防ぐ方法、または環境内で追加のセキュリティ保護手段として表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="047ad-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="047ad-109">ビバ トピックでは、ユーザーがトピック内のアクセス許可を使用してアクセスできない内容を表示することは許可Office 365です。</span><span class="sxs-lookup"><span data-stu-id="047ad-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="047ad-110">ユーザーがトピックを表示できる場合でも、そのユーザーのファイル、サイト、およびページには、Office 365アクセス許可が付与されていないと、ユーザーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="047ad-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="047ad-111">機密性の高いファイルに対するアクセス許可が正しく設定されていることを確認することは、主なセキュリティ保護策である必要があります。</span><span class="sxs-lookup"><span data-stu-id="047ad-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="047ad-112">トピックが識別されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="047ad-112">Prevent topics from being identified</span></span>

<span data-ttu-id="047ad-113">ナレッジ管理者は、最初のインデックス作成で特定のトピックが見つからないのを防ぐことで、特定のトピックへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="047ad-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="047ad-114">このタスクを実行するには、管理センターの [ビバ トピック] 管理Microsoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="047ad-114">There are two ways to do this task in the Viva Topics admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="047ad-115">[トピックSharePoint除外](./topic-experiences-discovery.md#select-sharepoint-topic-sources)するサイトを選択します。この設定を使用すると、特定のサイトがトピックSharePointクロールされるのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="047ad-115">[Select SharePoint sites to exclude from topic discovery](./topic-experiences-discovery.md#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="047ad-116">[名前でトピックを除外する](./topic-experiences-discovery.md#exclude-topics-by-name): 管理者は、この設定を使用して、特定のトピックが名前で検出されるのを防ぐ場合があります。</span><span class="sxs-lookup"><span data-stu-id="047ad-116">[Exclude topics by name](./topic-experiences-discovery.md#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="047ad-117">ビバ トピックの管理設定では、管理者は CSV ファイルで除外するトピックの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="047ad-117">In the Viva Topics admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="047ad-118">トピック名に完全一致または部分的に一致するトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="047ad-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="047ad-119">トピックが特定のユーザーによって表示されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="047ad-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="047ad-120">ナレッジ管理者は、組織内 [のトピックを表示できるユーザーを選択することもできます](./topic-experiences-knowledge-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="047ad-120">Knowledge admins can also [select who can view topics in your organization](./topic-experiences-knowledge-rules.md).</span></span> <span data-ttu-id="047ad-121">この設定では、すべてのトピックを表示できるライセンスユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="047ad-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="047ad-122">たとえば、パイロット環境では、小さなグループのユーザーだけがトピックを表示できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="047ad-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="047ad-123">トピックを表示から削除する</span><span class="sxs-lookup"><span data-stu-id="047ad-123">Remove topics from being viewed</span></span>

<span data-ttu-id="047ad-124">ナレッジ マネージャーは、ユーザー [がトピックを表示](./manage-topics.md) できなくなった場合に、トピックを削除できます。</span><span class="sxs-lookup"><span data-stu-id="047ad-124">Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them.</span></span> <span data-ttu-id="047ad-125">トピック センター **の [トピックの** 管理] ページで、ナレッジ マネージャーは特定のトピックを拒否して表示を防止できます。 </span><span class="sxs-lookup"><span data-stu-id="047ad-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="047ad-126">トピックは、提案または確認済み状態の場合に関係なく削除できます。</span><span class="sxs-lookup"><span data-stu-id="047ad-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="047ad-127">削除されたトピックは、必要に応じて表示可能なトピックとして後で追加できます。</span><span class="sxs-lookup"><span data-stu-id="047ad-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="047ad-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="047ad-128">See also</span></span>



