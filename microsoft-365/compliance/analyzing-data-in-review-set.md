---
title: 高度な電子情報開示のレビューセットのデータを分析する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0f9cb386ce57d6581ade5caa05e029511100d9b3
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42556785"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="5661f-102">高度な電子情報開示のレビューセットのデータを分析する</span><span class="sxs-lookup"><span data-stu-id="5661f-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="5661f-103">収集されたドキュメントの数が多い場合は、それらをすべて確認するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="5661f-103">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="5661f-104">Advanced eDiscovery には、ドキュメントを分析して、情報が失われずにレビューされるドキュメントのボリュームを減らし、一貫性のある方法でドキュメントを整理するのに役立つさまざまなツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5661f-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="5661f-105">これらの機能の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5661f-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="5661f-106">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="5661f-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="5661f-107">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="5661f-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="5661f-108">テーマ</span><span class="sxs-lookup"><span data-stu-id="5661f-108">Themes</span></span>](themes.md)

<span data-ttu-id="5661f-109">レビューセット内のデータを分析するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5661f-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="5661f-110">ケースの分析設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5661f-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="5661f-111">詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5661f-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="5661f-112">分析するレビューセットを開きます。</span><span class="sxs-lookup"><span data-stu-id="5661f-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="5661f-113">[**レビューセットの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5661f-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="5661f-114">[**レビューセットの分析を実行**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5661f-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="5661f-115">ケースの [**ジョブ**] タブで、分析の進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5661f-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="5661f-116">分析が完了したら、analytics レポートを表示し、分析の出力に対してレビューセット内のクエリを実行し ([レビューセット内のクエリ](review-set-search.md)を参照)、特定のドキュメントの関連ドキュメントを表示できます (「[レビューセット内のデータ](reviewing-data-in-review-set.md)のレビュー」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5661f-116">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="5661f-117">分析レポート</span><span class="sxs-lookup"><span data-stu-id="5661f-117">Analytics report</span></span>

<span data-ttu-id="5661f-118">レビューセットの分析レポートを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5661f-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="5661f-119">レビューセットを開きます。</span><span class="sxs-lookup"><span data-stu-id="5661f-119">Open the review set.</span></span>

2. <span data-ttu-id="5661f-120">[**レビューセットの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5661f-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="5661f-121">[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5661f-121">Click **View report**.</span></span>

<span data-ttu-id="5661f-122">レポートには、分析から7つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="5661f-122">The report has seven components from analysis:</span></span>

- <span data-ttu-id="5661f-123">**ターゲットの作成:** レビューセットに含まれている電子メールメッセージ、添付ファイル、およびルースドキュメントの数。</span><span class="sxs-lookup"><span data-stu-id="5661f-123">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="5661f-124">**ドキュメント (添付ファイルを除く):** ピボットされた非圧縮ドキュメントの数、ピボットの一意の重複、または別のドキュメントの正確な複製。</span><span class="sxs-lookup"><span data-stu-id="5661f-124">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="5661f-125">**メール:** Inclusives の電子メールメッセージ数、包括的なコピー、包括 minuses、または上記のいずれでもないもの。</span><span class="sxs-lookup"><span data-stu-id="5661f-125">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="5661f-126">**添付ファイル:** レビューセット内の別の電子メール添付ファイルの一意の、または重複する電子メール添付ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="5661f-126">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="5661f-127">**種類別のファイル数:** ファイル拡張子で識別されるファイルの数。</span><span class="sxs-lookup"><span data-stu-id="5661f-127">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="5661f-128">**ソース別のドキュメント:** 元のデータソースによってコンテンツの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5661f-128">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="5661f-129">**プロセスによって集約**されたドキュメント:レビューによるコンテンツの概要セットのプロセス。</span><span class="sxs-lookup"><span data-stu-id="5661f-129">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
