---
title: プロセス モジュールを実行し、Advanced eDiscovery でデータを読み込む
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: セキュリティ コンプライアンス センターを使用して Advanced eDiscovery にアクセスし、ケースのプロセス モジュール &amp; を実行する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64172c0198418dbb0ba4d01a5adbd5aaef4c3a3b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662841"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a><span data-ttu-id="af624-103">プロセス モジュールを実行し、Advanced eDiscovery (クラシック) でデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="af624-103">Run the Process module and load data in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="af624-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="af624-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="af624-106">このセクションでは、Advanced eDiscovery プロセス モジュールの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="af624-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="af624-107">ファイル データに加えて、ファイルの種類、拡張子、場所またはパス、作成日時、作成者、保管担当者、件名などのメタデータを Advanced eDiscovery に読み込み、ケースごとに保存できます。</span><span class="sxs-lookup"><span data-stu-id="af624-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="af624-108">一部のメタデータは、ネイティブ ファイルが読み込まれる場合など、Advanced eDiscovery によって計算されます。</span><span class="sxs-lookup"><span data-stu-id="af624-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="af624-109">Advanced eDiscovery は、近重複グループや関連性スコアなどのシステム メタデータ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="af624-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="af624-110">管理者は、ファイル注釈などの他のメタデータを追加できます。</span><span class="sxs-lookup"><span data-stu-id="af624-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="af624-111">実行中のプロセス</span><span class="sxs-lookup"><span data-stu-id="af624-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="af624-112">バッチ番号はプロセス中にファイルに割り当てられるので、ファイルの追跡が可能になります。</span><span class="sxs-lookup"><span data-stu-id="af624-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="af624-113">バッチ番号を使用すると、プロセス バッチを再処理オプションとして識別できます。</span><span class="sxs-lookup"><span data-stu-id="af624-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="af624-114">バッチ番号とセッションによるフィルター処理には、追加のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af624-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="af624-115">プロセスを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af624-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="af624-116">[セキュリティを開く &amp; コンプライアンス センター](go-to-the-securitycompliance-center.md) 。</span><span class="sxs-lookup"><span data-stu-id="af624-116">[Open the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="af624-117">検索調査 **の &amp; 電子情報開示に** \> **移動し** 、[Advanced eDiscovery に移動] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="af624-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="af624-118">Advanced eDiscovery で、表示される [ケース] ページで適切なケースを選択し、[ケース **に移動] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="af624-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="af624-119">[ **プロセス** \> **セットアップの** \> **準備**] で、使用可能なコンテナーの一覧からコンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="af624-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![[プロセス] をクリックして検索結果をケースに追加する](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="af624-121">コンテナー **を** シード ファイルまたは事前タグ付けファイルとして追加する場合は、[詳細設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af624-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="af624-122">シード ファイルを使用して、リッチ度の低い問題 (通常は 2% 以下) のトレーニングを加速します。</span><span class="sxs-lookup"><span data-stu-id="af624-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="af624-123">シード ファイルの場合は、明確に関連するさまざまなファイルを選択し、問題ごとに約 20 ~ 50 のシードを処理します (シード ファイルが多すぎると関連性の結果が歪む可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="af624-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="af624-124">シード ファイルは、問題をトレーニングする同じユーザーが確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af624-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="af624-125">事前にタグ付けされたファイルを使用して、関連性トレーニングを自動化します。</span><span class="sxs-lookup"><span data-stu-id="af624-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="af624-126">少なくとも 1,500 のファイルにタグを付け、関連性の低いファイルに関連する割合は、関連性に追加されたコレクションと同じ値にしてください。</span><span class="sxs-lookup"><span data-stu-id="af624-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="af624-127">これらのファイルは手動でタグ付けする必要があります。タグ付けの品質に自信を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="af624-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![バッチ ファイルを処理する [詳細設定] ページのスクリーンショット](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="af624-129">シード セクション **で、次の処理を** 行います。</span><span class="sxs-lookup"><span data-stu-id="af624-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="af624-130">[ **シード ファイルとしてマーク] を選択して** 、コンテナーをシード ファイルとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="af624-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="af624-131">また、[For **issue]** ドロップダウンから、問題ごとに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="af624-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="af624-132">[タグ **] ドロップダウン** から **[関連]** または [関連しない **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af624-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="af624-133">ファイルをシードとして設定 **すると**、事前にタグ付けされたファイル **としてマークすることはできません**。</span><span class="sxs-lookup"><span data-stu-id="af624-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="af624-134">[事前 **にタグ付けされたファイル] セクションで、次の手順を実行** します。</span><span class="sxs-lookup"><span data-stu-id="af624-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="af624-135">[ **事前にタグ付けされたファイルとしてマーク] を選択** して、コンテナーを事前にタグ付けされたファイルとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="af624-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="af624-136">また、[For issue] ドロップダウンから、問題 **ごとに割り** 当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="af624-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="af624-137">[タグ **]** ドロップダウンから **[関連]** または [関連しない **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af624-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="af624-138">事前にタグ付 **けされたファイルを設定** すると、シードとしてマーク **することはできません**。</span><span class="sxs-lookup"><span data-stu-id="af624-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="af624-139">[電子 **メールのタグ付け] セクション** 。</span><span class="sxs-lookup"><span data-stu-id="af624-139">In the **Email tagging** section.</span></span> <span data-ttu-id="af624-140">シードまたは事前タグ付けとしてマークする処理済み電子メールの部分を設定します。</span><span class="sxs-lookup"><span data-stu-id="af624-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="af624-141">開始するには、[プロセス] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="af624-141">To begin, click **Process**.</span></span> <span data-ttu-id="af624-142">完了すると、プロセスの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af624-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="af624-143">(省略可能)データ ソースを特定の保管担当者に割り当てる必要がある場合は、**保管** 担当者の管理で保管担当者名を追加および編集し、保管担当者の割り当てで保管担当者を割り当 \>  \> **てできます**。</span><span class="sxs-lookup"><span data-stu-id="af624-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="af624-144">ケースに追加すると、もう一度処理できます。</span><span class="sxs-lookup"><span data-stu-id="af624-144">If you add to the case, then you can process again.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="af624-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="af624-145">Related topics</span></span>

[<span data-ttu-id="af624-146">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="af624-146">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="af624-147">プロセス モジュールの結果の表示</span><span class="sxs-lookup"><span data-stu-id="af624-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

