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
description: 高度な電子情報開示ケースを分析する際にドキュメントセットを整理するために使用できるツールについて説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87788e444a5ef671586567510448dab8b9deddcd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033821"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="818ab-103">高度な電子情報開示のレビューセットのデータを分析する</span><span class="sxs-lookup"><span data-stu-id="818ab-103">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="818ab-104">収集されたドキュメントの数が多い場合は、それらをすべて確認するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="818ab-104">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="818ab-105">Advanced eDiscovery には、ドキュメントを分析して、情報が失われずにレビューされるドキュメントのボリュームを減らし、一貫性のある方法でドキュメントを整理するのに役立つさまざまなツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="818ab-105">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="818ab-106">これらの機能の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="818ab-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="818ab-107">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="818ab-107">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="818ab-108">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="818ab-108">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="818ab-109">テーマ</span><span class="sxs-lookup"><span data-stu-id="818ab-109">Themes</span></span>](themes.md)

<span data-ttu-id="818ab-110">レビューセット内のデータを分析するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="818ab-110">To analyze data in a review set:</span></span>

1. <span data-ttu-id="818ab-111">ケースの分析設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="818ab-111">Configure analytics settings for your case.</span></span> <span data-ttu-id="818ab-112">詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="818ab-112">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="818ab-113">分析するレビューセットを開きます。</span><span class="sxs-lookup"><span data-stu-id="818ab-113">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="818ab-114">[**レビューセットの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="818ab-114">Click **Manage review set**.</span></span>

4. <span data-ttu-id="818ab-115">[**レビューセットの分析を実行**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="818ab-115">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="818ab-116">ケースの [**ジョブ**] タブで、分析の進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="818ab-116">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="818ab-117">分析が完了したら、analytics レポートを表示し、分析の出力に対してレビューセット内のクエリを実行し ([レビューセット内のクエリ](review-set-search.md)を参照)、特定のドキュメントの関連ドキュメントを表示できます (「[レビューセット内のデータ](reviewing-data-in-review-set.md)のレビュー」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="818ab-117">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="818ab-118">分析レポート</span><span class="sxs-lookup"><span data-stu-id="818ab-118">Analytics report</span></span>

<span data-ttu-id="818ab-119">レビューセットの分析レポートを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="818ab-119">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="818ab-120">レビューセットを開きます。</span><span class="sxs-lookup"><span data-stu-id="818ab-120">Open the review set.</span></span>

2. <span data-ttu-id="818ab-121">[**レビューセットの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="818ab-121">Click **Manage review set**.</span></span>

3. <span data-ttu-id="818ab-122">[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="818ab-122">Click **View report**.</span></span>

<span data-ttu-id="818ab-123">レポートには、分析から7つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="818ab-123">The report has seven components from analysis:</span></span>

- <span data-ttu-id="818ab-124">**ターゲットの作成:** レビューセットに含まれている電子メールメッセージ、添付ファイル、およびルースドキュメントの数。</span><span class="sxs-lookup"><span data-stu-id="818ab-124">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="818ab-125">**ドキュメント (添付ファイルを除く):** ピボットされた非圧縮ドキュメントの数、ピボットの一意の重複、または別のドキュメントの正確な複製。</span><span class="sxs-lookup"><span data-stu-id="818ab-125">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="818ab-126">**メール:** Inclusives の電子メールメッセージ数、包括的なコピー、包括 minuses、または上記のいずれでもないもの。</span><span class="sxs-lookup"><span data-stu-id="818ab-126">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="818ab-127">**添付ファイル:** レビューセット内の別の電子メール添付ファイルの一意の、または重複する電子メール添付ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="818ab-127">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="818ab-128">**種類別のファイル数:** ファイル拡張子で識別されるファイルの数。</span><span class="sxs-lookup"><span data-stu-id="818ab-128">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="818ab-129">**ソース別のドキュメント:** 元のデータソースによってコンテンツの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="818ab-129">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="818ab-130">**プロセスによって集約**されたドキュメント:レビューによるコンテンツの概要セットのプロセス。</span><span class="sxs-lookup"><span data-stu-id="818ab-130">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
