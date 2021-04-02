---
title: Microsoft Defender ATP でカスタム検出ルールを表示および管理する
ms.reviewer: ''
description: カスタム検出ルールを表示および管理する方法について説明します。
keywords: カスタム検出、表示、管理、アラート、編集、オンデマンドでの実行、検出ルール、高度な狩猟、ハント、クエリ、応答アクション、mdatp、microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498753"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="d8a07-104">検出ルールの表示と管理</span><span class="sxs-lookup"><span data-stu-id="d8a07-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d8a07-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d8a07-105">**Applies to:**</span></span>
- [<span data-ttu-id="d8a07-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d8a07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8a07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8a07-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d8a07-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d8a07-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d8a07-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d8a07-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d8a07-110">既存のカスタム検出 [ルールを管理して](custom-detection-rules.md) 、脅威を効果的に検出し、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8a07-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="d8a07-111">ルールの一覧を表示し、以前の実行を確認し、トリガーしたアラートを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8a07-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="d8a07-112">必要に応じてルールを実行して変更できます。</span><span class="sxs-lookup"><span data-stu-id="d8a07-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="d8a07-113">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d8a07-113">Required permissions</span></span>

<span data-ttu-id="d8a07-114">カスタム検出を作成または管理するには、 [役割に](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) セキュリティ設定の管理権限 **が必要** です。</span><span class="sxs-lookup"><span data-stu-id="d8a07-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="d8a07-115">既存のルールの表示</span><span class="sxs-lookup"><span data-stu-id="d8a07-115">View existing rules</span></span>

<span data-ttu-id="d8a07-116">既存のすべてのカスタム検出ルールを表示するには、[設定] [カスタム検出  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d8a07-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="d8a07-117">ページには、次の実行情報を含むすべてのルールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8a07-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="d8a07-118">**Last run**—クエリの一致を確認し、アラートを生成するルールが最後に実行された場合</span><span class="sxs-lookup"><span data-stu-id="d8a07-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="d8a07-119">**最終実行の状態**:ルールが正常に実行されたかどうか</span><span class="sxs-lookup"><span data-stu-id="d8a07-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="d8a07-120">**次の実行**— 次のスケジュールされた実行</span><span class="sxs-lookup"><span data-stu-id="d8a07-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="d8a07-121">**Status**—ルールが有効または無効になっているかどうか</span><span class="sxs-lookup"><span data-stu-id="d8a07-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="d8a07-122">ルールの詳細の表示、ルールの変更、およびルールの実行</span><span class="sxs-lookup"><span data-stu-id="d8a07-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="d8a07-123">カスタム検出ルールに関する包括的な情報を表示するには、[設定のカスタム検出] のルールの一覧からルールの **名前**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8a07-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="d8a07-124">選択したルールに関するページには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8a07-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="d8a07-125">アラート、実行状態、およびスコープの詳細を含む、ルールに関する一般的な情報</span><span class="sxs-lookup"><span data-stu-id="d8a07-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="d8a07-126">トリガーされたアラートの一覧</span><span class="sxs-lookup"><span data-stu-id="d8a07-126">List of triggered alerts</span></span>
- <span data-ttu-id="d8a07-127">トリガーされたアクションの一覧</span><span class="sxs-lookup"><span data-stu-id="d8a07-127">List of triggered actions</span></span>

<span data-ttu-id="d8a07-128">![カスタム検出ルール ページ](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="d8a07-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="d8a07-129">*カスタム検出ルール ページ*</span><span class="sxs-lookup"><span data-stu-id="d8a07-129">*Custom detection rule page*</span></span>

<span data-ttu-id="d8a07-130">また、このページからルールに対して次のアクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8a07-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="d8a07-131">**Run**—ルールを直ちに実行します。</span><span class="sxs-lookup"><span data-stu-id="d8a07-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="d8a07-132">このアクションでは、次の実行の間隔もリセットされます。</span><span class="sxs-lookup"><span data-stu-id="d8a07-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="d8a07-133">**Edit**—クエリを変更せずにルールを変更する</span><span class="sxs-lookup"><span data-stu-id="d8a07-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="d8a07-134">**クエリの変更**—高度な検索でクエリを編集する</span><span class="sxs-lookup"><span data-stu-id="d8a07-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="d8a07-135">**有効にする**  / **無効にする**-ルールを有効にするか、ルールの実行を停止する</span><span class="sxs-lookup"><span data-stu-id="d8a07-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="d8a07-136">**Delete**—ルールをオフにし、削除する</span><span class="sxs-lookup"><span data-stu-id="d8a07-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="d8a07-137">テーブル内のアイテムに関する情報をすばやく表示し、アクションを実行するには、表の左側にある [&#10003;] の選択列を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8a07-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8a07-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8a07-138">Related topics</span></span>
- [<span data-ttu-id="d8a07-139">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="d8a07-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="d8a07-140">検出ルールの作成</span><span class="sxs-lookup"><span data-stu-id="d8a07-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="d8a07-141">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="d8a07-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d8a07-142">アラートの表示と整理</span><span class="sxs-lookup"><span data-stu-id="d8a07-142">View and organize alerts</span></span>](alerts-queue.md)
