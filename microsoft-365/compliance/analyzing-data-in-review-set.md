---
title: Advanced eDiscovery のレビュー セット内のデータを分析する
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
description: Advanced eDiscovery ケースを分析するときにドキュメント セットを整理するために使用できるツールについて説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751372"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="f2f12-103">Advanced eDiscovery のレビュー セット内のデータを分析する</span><span class="sxs-lookup"><span data-stu-id="f2f12-103">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="f2f12-104">収集されたドキュメントの数が多い場合、すべてのドキュメントを確認するのは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2f12-104">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="f2f12-105">Advanced eDiscovery には、ドキュメントを分析して情報を損失することなくレビューするドキュメントの量を減らし、ドキュメントを一貫性のある方法で整理するためのツールが多数備えています。</span><span class="sxs-lookup"><span data-stu-id="f2f12-105">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="f2f12-106">これらの機能の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2f12-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="f2f12-107">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="f2f12-107">Near duplicate detection</span></span>](near-duplicate-detection-in-advanced-ediscovery.md)

- [<span data-ttu-id="f2f12-108">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="f2f12-108">Email threading</span></span>](email-threading-in-advanced-ediscovery.md)

- [<span data-ttu-id="f2f12-109">テーマ</span><span class="sxs-lookup"><span data-stu-id="f2f12-109">Themes</span></span>](themes-in-advanced-ediscovery.md)

<span data-ttu-id="f2f12-110">レビュー セット内のデータを分析するには:</span><span class="sxs-lookup"><span data-stu-id="f2f12-110">To analyze data in a review set:</span></span>

1. <span data-ttu-id="f2f12-111">ケースの分析設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f2f12-111">Configure analytics settings for your case.</span></span> <span data-ttu-id="f2f12-112">詳細については、「検索と分析 [の設定を構成する」を参照してください](configure-search-and-analytics-settings-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f2f12-112">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).</span></span>

2. <span data-ttu-id="f2f12-113">分析するレビュー セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2f12-113">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="f2f12-114">[レビュー **セットの管理] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2f12-114">Click **Manage review set**.</span></span>

4. <span data-ttu-id="f2f12-115">[ **レビュー セットの分析の実行] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2f12-115">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="f2f12-116">ケースの [ジョブ] タブで **分析の** 進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2f12-116">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="f2f12-117">分析が完了したら、分析レポートを表示し、分析の出力に対してレビュー セット内でクエリを実行し ([](review-set-search.md)レビュー セット内のクエリを参照)、特定のドキュメントの関連ドキュメントを表示できます (「[レビュー](reviewing-data-in-review-set.md)セット内のデータの確認」を参照)。</span><span class="sxs-lookup"><span data-stu-id="f2f12-117">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="f2f12-118">分析レポート</span><span class="sxs-lookup"><span data-stu-id="f2f12-118">Analytics report</span></span>

<span data-ttu-id="f2f12-119">レビュー セットの分析レポートを表示するには:</span><span class="sxs-lookup"><span data-stu-id="f2f12-119">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="f2f12-120">レビュー セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2f12-120">Open the review set.</span></span>

2. <span data-ttu-id="f2f12-121">[レビュー **セットの管理] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2f12-121">Click **Manage review set**.</span></span>

3. <span data-ttu-id="f2f12-122">[レポート **の表示] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f2f12-122">Click **View report**.</span></span>

<span data-ttu-id="f2f12-123">レポートには分析から 7 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="f2f12-123">The report has seven components from analysis:</span></span>

- <span data-ttu-id="f2f12-124">**対象となる母集団:** レビュー セットで見つかった電子メール メッセージ、添付ファイル、および緩やかなドキュメントの数。</span><span class="sxs-lookup"><span data-stu-id="f2f12-124">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="f2f12-125">**ドキュメント (添付ファイルを除く):** ピボット、ピボットの一意の近くの重複、または別のドキュメントの完全な複製である緩やかなドキュメントの数。</span><span class="sxs-lookup"><span data-stu-id="f2f12-125">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="f2f12-126">**メール:** 包括的なコピー、包括的なマイナス、または上記のいずれの電子メール メッセージも含めない電子メール メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="f2f12-126">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="f2f12-127">**添付ファイル:** レビュー セット内の別の電子メール添付ファイルの一意または重複する電子メールの添付ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="f2f12-127">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="f2f12-128">**ファイルの種類別の数:** ファイル拡張子で識別されるファイルの数。</span><span class="sxs-lookup"><span data-stu-id="f2f12-128">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="f2f12-129">**ソース別のドキュメント:** 元のデータ ソースによるコンテンツの概要。</span><span class="sxs-lookup"><span data-stu-id="f2f12-129">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="f2f12-130">**プロセス別に集計されたドキュメント:** レビュー セット プロセス別のコンテンツの概要。</span><span class="sxs-lookup"><span data-stu-id="f2f12-130">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
