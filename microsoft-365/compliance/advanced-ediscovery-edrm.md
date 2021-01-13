---
title: EDRM を使用した高度な電子情報開示の調整
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の Advanced eDiscovery の組み込みワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに沿っています。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841635"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="d30e2-103">電子情報開示参照モデルを使用した Advanced eDiscovery の配置</span><span class="sxs-lookup"><span data-stu-id="d30e2-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="d30e2-104">Microsoft 365 の Advanced eDiscovery の組み込みワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに沿っています。</span><span class="sxs-lookup"><span data-stu-id="d30e2-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![電子探索参照モデル (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="d30e2-106">(画像ソース: edrm.net。</span><span class="sxs-lookup"><span data-stu-id="d30e2-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="d30e2-107">ソース 画像は、Creative Commons Attribution 3.0 Unported License (Creative Commons Attribution 3.0 Unported License) で利用できます)。</span><span class="sxs-lookup"><span data-stu-id="d30e2-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="d30e2-108">大きなレベルでは、Advanced eDiscovery が EDRM ワークフローをサポートする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d30e2-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="d30e2-109">**Id。**</span><span class="sxs-lookup"><span data-stu-id="d30e2-109">**Identification.**</span></span> <span data-ttu-id="d30e2-110">調査に関心のある人物を特定した後、Advanced eDiscovery ケースにカストディアン (データ保管担当者とも呼ばれる)、調査に関連する情報を保持している可能性がある管理者として追加できます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="d30e2-111">ユーザーがカストディアンとして追加された後は、保管担当者のドキュメントを簡単に保持、収集、および確認できます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="d30e2-112">**保持。**</span><span class="sxs-lookup"><span data-stu-id="d30e2-112">**Preservation.**</span></span> <span data-ttu-id="d30e2-113">調査に関連するデータを保持および保護するために、Advanced eDiscovery を使用すると、ケース内の保管担当者に関連付けられているデータ ソースに法的情報保留を設定できます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="d30e2-114">保管されていないデータを保留に設定できます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="d30e2-115">Advanced eDiscovery には、法的情報保留通知を保管担当者に送信し、通知を追跡できる組み込みの通信ワークフローも用意されています。</span><span class="sxs-lookup"><span data-stu-id="d30e2-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="d30e2-116">**コレクションです。**</span><span class="sxs-lookup"><span data-stu-id="d30e2-116">**Collection.**</span></span> <span data-ttu-id="d30e2-117">調査に関連するデータ ソースを特定 (および保持) した後、Advanced eDiscovery 検索の組み込みの検索ツールを使用して、ケースに関連する可能性のある保管データ ソース (および該当する場合は保管されていないデータ ソース) からライブ データを収集できます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="d30e2-118">**処理。**</span><span class="sxs-lookup"><span data-stu-id="d30e2-118">**Processing.**</span></span> <span data-ttu-id="d30e2-119">ケースに関連するすべてのデータを収集した後、次の手順でケースを処理し、さらにレビューと分析を行います。</span><span class="sxs-lookup"><span data-stu-id="d30e2-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="d30e2-120">Advanced eDiscovery では、コレクション フェーズで特定したインセット データが Azure Storage の場所 (レビュー セットと呼ばれる) にコピーされ、ケース データの静的ビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="d30e2-121">**確認します。**</span><span class="sxs-lookup"><span data-stu-id="d30e2-121">**Review.**</span></span> <span data-ttu-id="d30e2-122">レビュー セットにデータが追加された後、特定のドキュメントを表示し、追加のクエリを実行して、データをケースに最も関連のあるものに減らします。</span><span class="sxs-lookup"><span data-stu-id="d30e2-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="d30e2-123">また、特定のドキュメントに注釈を付け、タグを付けできます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="d30e2-124">**分析。**</span><span class="sxs-lookup"><span data-stu-id="d30e2-124">**Analysis.**</span></span> <span data-ttu-id="d30e2-125">Advanced eDiscovery は、調査に関連していないと判断したレビュー セットからさらにデータを収集するのに役立つ統合分析ツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="d30e2-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="d30e2-126">Advance eDiscovery は、関連するデータの量を減らすだけでなく、コンテンツを整理してレビュー プロセスをより簡単かつ効率的に行え、法的レビューコストを節約するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="d30e2-127">**実稼働** および **プレゼンテーション。**</span><span class="sxs-lookup"><span data-stu-id="d30e2-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="d30e2-128">準備ができたら、法的レビュー用のレビュー セットからドキュメントをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="d30e2-129">ドキュメントは、ネイティブ形式または EDRM で指定された形式でエクスポートして、サード パーティ製のレビュー アプリケーションにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d30e2-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="d30e2-130">詳細</span><span class="sxs-lookup"><span data-stu-id="d30e2-130">More information</span></span>

<span data-ttu-id="d30e2-131">Advanced eDiscovery の使用を開始するには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d30e2-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="d30e2-132">Advanced eDiscovery のセットアップ</span><span class="sxs-lookup"><span data-stu-id="d30e2-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="d30e2-133">Advanced eDiscovery ケースの作成と管理</span><span class="sxs-lookup"><span data-stu-id="d30e2-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)