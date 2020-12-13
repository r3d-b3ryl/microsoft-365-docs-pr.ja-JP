---
title: Advanced eDiscovery でプロセス モジュールの結果を表示する
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: タスクの状態やプロセスの概要など、Advanced eDiscovery で実行されるプロセス モジュールの結果を見つける方法について説明します。
ms.openlocfilehash: 73699d77e305055f6c2dc444fff00fb714b458cd
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663266"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="96866-103">プロセス モジュールの結果を Advanced eDiscovery (クラシック) で表示する</span><span class="sxs-lookup"><span data-stu-id="96866-103">View Process module results in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="96866-104">準備 **プロセス** \> **が開始** された後、進行状況と結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="96866-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="96866-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="96866-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="96866-107">タスクの状態を処理する</span><span class="sxs-lookup"><span data-stu-id="96866-107">Process task status</span></span>

<span data-ttu-id="96866-108">[**プロセス** \> **の準備の** 結果] ページには、次の例に示すように、現在の状態 (プロセスが現在実行中の場合) または最後のプロセス状態タスクの状態 \> が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![プロセス モジュールのタスクの進捗状況](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="96866-110">表示されるタスクは、選択されている [プロセス] オプションによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="96866-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="96866-111">**Inventory**: Advanced eDiscovery は、プロセス用に選択されたファイルを反復処理し、基本的なデータ収集を実行します。</span><span class="sxs-lookup"><span data-stu-id="96866-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="96866-112">**署名の計算**: MD5 デジタル署名を計算します。</span><span class="sxs-lookup"><span data-stu-id="96866-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="96866-113">**複合抽出**: 複合ファイル (PST、ZIP、MSG など) から内部ファイルまたは含まれているファイルを再帰的に抽出します。</span><span class="sxs-lookup"><span data-stu-id="96866-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="96866-114">抽出されたファイルは、ケースのケース フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="96866-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="96866-115">**データベースの同期**: 内部データベース プロセス。</span><span class="sxs-lookup"><span data-stu-id="96866-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="96866-116">**ファイル コピー**: プロセス ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="96866-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="96866-117">[ファイルのコピー] オプションが選択されている場合でも、このタスクは常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="96866-118">**テキスト抽出**: ネイティブ ファイルがある場合、Advanced eDiscovery は DTSearch を使用してこれらのファイルからテキストを抽出します。</span><span class="sxs-lookup"><span data-stu-id="96866-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="96866-119">抽出されたこれらのファイルのテキストは、ケース フォルダーにテキスト ファイルとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="96866-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="96866-120">**メタデータの更新**: 読み込まれたメタデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="96866-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="96866-121">**最終処理**: 読み込まれたケース ファイルのデータを最終処理する内部処理 (エラー ファイルや成功ファイルの特定など)。</span><span class="sxs-lookup"><span data-stu-id="96866-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="96866-122">タスクの状態: タスクの完了後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="96866-123">タスクの実行中は、実行期間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96866-124">完了したタスクには、処理を完了したファイルまたはエラーのあるファイルの合計も含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="96866-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="96866-125">"キャンセル" は、プロセスの実行を停止し、前のデータ群または保存された処理済みデータにロールバックするロールバック オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="96866-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="96866-126">ロールバックは、処理されたデータをすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="96866-126">Rollback clears all processed data.</span></span> <span data-ttu-id="96866-127">処理されたデータが失われたくない場合 (たとえば、これらのファイルを再読み込みする場合) は、このウィンドウの [キャンセル] オプションを選択してロールバックしない選択をします。</span><span class="sxs-lookup"><span data-stu-id="96866-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="96866-128">プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="96866-128">Process summary</span></span>

<span data-ttu-id="96866-129">[プロセス結果処理の準備] の概要では、正常なファイル処理とエラー結果に従って、読み込まれたファイルの結果の \> \> \> 内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="96866-130">次のように、ウィンドウにはインポートされたファイル統計のグラフィック表示が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="96866-131">**プロセスの概要は** d: ケース内のすべてのファイルを蓄積します。</span><span class="sxs-lookup"><span data-stu-id="96866-131">**Process summary accumulate** d: All files in the case.</span></span>
    
- <span data-ttu-id="96866-132">**最後のプロセスの概要**: 最後のセッションまたはアクションから読み込まれたファイル。</span><span class="sxs-lookup"><span data-stu-id="96866-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="96866-133">**家族の最後**: ケース内の家族情報 (場合)。</span><span class="sxs-lookup"><span data-stu-id="96866-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="96866-134">シード **ファイル** が追加された場合は、ファイルに対して定義された問題ごとにシード ファイルの数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="96866-135">シード ファイルのマーキング **が失敗** した場合は、そのマークも示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="96866-136">事前 **にタグ付け** されたファイルが追加された場合、ファイルに対して定義された問題ごとに、事前にタグ付けされたファイルの数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="96866-137">事前にタグ付 **けされたファイルの** マーキングが失敗した場合も、そのマークは示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![プロセス モジュールの概要](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="96866-139">積み上がったグラフと最後のグラフのプロセス サマリー</span><span class="sxs-lookup"><span data-stu-id="96866-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="96866-140">左側のバーには、ソースと抽出されたファイルが含まれています。すべてのファイルが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="96866-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="96866-141">右側のバー (処理) には、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="96866-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="96866-142">読み込みエラーが発生したファイル</span><span class="sxs-lookup"><span data-stu-id="96866-142">Files with load errors</span></span>
    
- <span data-ttu-id="96866-143">ファイルが正常に読み込まれます。次のものが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="96866-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="96866-144">**既存 :** 以前に読み込まれ、再び読み込まれるファイル (重複を含む)</span><span class="sxs-lookup"><span data-stu-id="96866-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="96866-145">**テキスト**: テキストを含む一意のファイル。</span><span class="sxs-lookup"><span data-stu-id="96866-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="96866-146">**テキスト以外**: 空のテキスト ファイル、空のネイティブ テキスト ファイル、ネイティブの非テキスト ファイル。</span><span class="sxs-lookup"><span data-stu-id="96866-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="96866-147">**重複する** s: テキストを含むファイルを複製します。</span><span class="sxs-lookup"><span data-stu-id="96866-147">**Duplicate** s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="96866-148">最後のプロセス エラー</span><span class="sxs-lookup"><span data-stu-id="96866-148">Last process errors</span></span>

<span data-ttu-id="96866-149">[Prepare Process Results Last process errors] (プロセスの最後の処理エラーの準備) に、最後に実行されたセッションまたはアクションのエラー \> \> \> の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96866-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![プロセス モジュールのエラー](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="96866-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="96866-151">See also</span></span>

[<span data-ttu-id="96866-152">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="96866-152">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="96866-153">プロセス モジュールの実行とデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="96866-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

