---
title: EDRM との高度な電子情報開示の配置
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
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の Advanced eDiscovery の組み込みのワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに合わせて調整されます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727490"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="b1eda-103">電子情報開示参照モデルとの高度な電子情報開示の配置</span><span class="sxs-lookup"><span data-stu-id="b1eda-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="b1eda-104">Microsoft 365 の Advanced eDiscovery の組み込みのワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![電子探索参照モデル (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="b1eda-106">(画像ソース提供:edrm.net。</span><span class="sxs-lookup"><span data-stu-id="b1eda-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="b1eda-107">ソース イメージは、クリエイティブ コモンズ アトリビューション 3.0 [報告されていないライセンス] で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="b1eda-108">高度な電子情報開示が EDRM ワークフローをサポートする方法は次の高レベルです。</span><span class="sxs-lookup"><span data-stu-id="b1eda-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="b1eda-109">**ID。**</span><span class="sxs-lookup"><span data-stu-id="b1eda-109">**Identification.**</span></span> <span data-ttu-id="b1eda-110">調査に関心のある潜在的な人物を特定した後、高度な電子情報開示ケースに保管担当者 (データ保管担当者とも呼ばれる)を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="b1eda-111">ユーザーが保管担当者として追加された後、保管担当者のドキュメントを保存、収集、および確認するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="b1eda-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="b1eda-112">**保持。**</span><span class="sxs-lookup"><span data-stu-id="b1eda-112">**Preservation.**</span></span> <span data-ttu-id="b1eda-113">調査に関連するデータを保持および保護するために、Advanced eDiscovery を使用すると、ケース内の保管担当者に関連付けられたデータ ソースに法的なホールドを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="b1eda-114">保管以外のデータを保留に設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="b1eda-115">高度な電子情報開示には、通信ワークフローも組み込みなので、法的保持通知を保管担当者に送信し、確認応答を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="b1eda-116">**コレクション。**</span><span class="sxs-lookup"><span data-stu-id="b1eda-116">**Collection.**</span></span> <span data-ttu-id="b1eda-117">調査に関連するデータ ソースを特定 (および保存) した後、ケースに関連する可能性のある保管データ ソース (および該当する場合は保管されていないデータ ソース) のライブ データを高度な電子情報開示検索で組み込みの検索ツールを使用して収集できます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="b1eda-118">**処理。**</span><span class="sxs-lookup"><span data-stu-id="b1eda-118">**Processing.**</span></span> <span data-ttu-id="b1eda-119">ケースに関連するすべてのデータを収集した後、次の手順でケースを処理して、詳細なレビューと分析を行います。</span><span class="sxs-lookup"><span data-stu-id="b1eda-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="b1eda-120">Advanced eDiscovery では、コレクション フェーズで識別したインプレイス データが Azure Storage の場所 (レビュー セットと呼ばれる) にコピーされ、ケース データの静的ビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="b1eda-121">**確認します。**</span><span class="sxs-lookup"><span data-stu-id="b1eda-121">**Review.**</span></span> <span data-ttu-id="b1eda-122">データをレビュー セットに追加した後、特定のドキュメントを表示し、追加のクエリを実行して、データをケースに最も関連のあるものに減らします。</span><span class="sxs-lookup"><span data-stu-id="b1eda-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="b1eda-123">また、特定のドキュメントに注釈を付け、タグ付けできます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="b1eda-124">**分析。**</span><span class="sxs-lookup"><span data-stu-id="b1eda-124">**Analysis.**</span></span> <span data-ttu-id="b1eda-125">高度な電子情報開示には、調査に関連していないと判断したレビュー セットからデータをさらに作成するのに役立つ統合分析ツールが提供されています。</span><span class="sxs-lookup"><span data-stu-id="b1eda-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="b1eda-126">関連するデータの量を減らすだけでなく、Advance eDiscovery を使用すると、コンテンツを整理してレビュー プロセスをより簡単かつ効率的に行って、法的レビューコストを節約できます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="b1eda-127">**実稼働** と **プレゼンテーション。**</span><span class="sxs-lookup"><span data-stu-id="b1eda-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="b1eda-128">準備ができたら、法的レビュー用のレビュー セットからドキュメントをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="b1eda-129">ドキュメントをネイティブ形式または EDRM で指定した形式でエクスポートして、サードパーティのレビュー アプリケーションにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b1eda-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="b1eda-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b1eda-130">More information</span></span>

<span data-ttu-id="b1eda-131">Advanced eDiscovery の使用を開始するには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1eda-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="b1eda-132">Advanced eDiscovery を設定する</span><span class="sxs-lookup"><span data-stu-id="b1eda-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="b1eda-133">高度な電子情報開示ケースの作成と管理</span><span class="sxs-lookup"><span data-stu-id="b1eda-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)