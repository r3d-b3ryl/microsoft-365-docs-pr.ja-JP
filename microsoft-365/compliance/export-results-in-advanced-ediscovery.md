---
title: Advanced eDiscovery で結果をエクスポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: 'エクスポート バッチのパラメーターを指定する手順など、Advanced eDiscovery から結果をエクスポートするためのオプションを定義する方法について説明します。 '
ms.openlocfilehash: 2929b183c7c0f3f132cc40738c18e2b4859a49a6
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662912"
---
# <a name="export-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="68890-103">Advanced eDiscovery (クラシック) で結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="68890-103">Export results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="68890-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="68890-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="68890-106">このトピックでは、Advanced eDiscovery Export Setup オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="68890-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="68890-107">**このトピックの内容**</span><span class="sxs-lookup"><span data-stu-id="68890-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="68890-108">エクスポート バッチとセッションの定義</span><span class="sxs-lookup"><span data-stu-id="68890-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="68890-109">増分エクスポートと追加エクスポート</span><span class="sxs-lookup"><span data-stu-id="68890-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="68890-110">バッチ エクスポート パラメーターを設定する</span><span class="sxs-lookup"><span data-stu-id="68890-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="68890-111">レポート出力ファイルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="68890-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="68890-112">エクスポート バッチとセッションの定義</span><span class="sxs-lookup"><span data-stu-id="68890-112">Defining export batches and sessions</span></span>
<span data-ttu-id="68890-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="68890-113"><a name="BK_Define"> </a></span></span>

<span data-ttu-id="68890-114">エクスポート バッチを使用すると、一連の定義済みパラメーターを使用してエクスポート処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="68890-114">An export batch allows export processing using a set of defined parameters.</span></span> <span data-ttu-id="68890-115">Advanced eDiscovery を使用すると、バッチを定義して各エクスポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="68890-115">Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="68890-116">パラメーターはエクスポート バッチごとに定義されます。</span><span class="sxs-lookup"><span data-stu-id="68890-116">Parameters are defined per export batch.</span></span> <span data-ttu-id="68890-117">ケースの最初のバッチに対して、"Export batch 01" という名前のバッチが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="68890-117">A batch named "Export batch 01" is created by default for the first batch of a case.</span></span> <span data-ttu-id="68890-118">バッチの名前と説明を編集できます。</span><span class="sxs-lookup"><span data-stu-id="68890-118">You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="68890-119">エクスポート セッションは、エクスポート バッチ内での Advanced eDiscovery Export の実行です。</span><span class="sxs-lookup"><span data-stu-id="68890-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="68890-120">増分エクスポートと追加エクスポート</span><span class="sxs-lookup"><span data-stu-id="68890-120">Incremental and additional exports</span></span>
<span data-ttu-id="68890-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="68890-121"><a name="BK_IncrementalReports"> </a></span></span>

<span data-ttu-id="68890-122">エクスポート バッチ内で複数のエクスポート セッションを実行して、同じエクスポート テンプレートとパラメーターに基づいて一貫した結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="68890-122">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters.</span></span> <span data-ttu-id="68890-123">バッチ内のセッションごとに、新しく処理されたケース データの分析をエクスポートし、各データを "段階的に" 処理できます。</span><span class="sxs-lookup"><span data-stu-id="68890-123">For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="68890-124">別のパラメーター セットを使用してエクスポートするには、最初に新しいバッチを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68890-124">In order to export using a different set of parameters, you first need to create a new batch.</span></span> <span data-ttu-id="68890-125">新しいバッチの最初のセッションでは、これらのファイルが 1 つ以上のインポートでインポートおよび処理されたかどうかに関して、これまでに処理されたファイルの結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="68890-125">The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports.</span></span> <span data-ttu-id="68890-126">各バッチは、ピボット、類似性、包括性などを再計算します。セッションはバッチに定義されたパラメーターを使用し、セッションの実行ごとにピボット、類似性、包括性などを再計算しません。</span><span class="sxs-lookup"><span data-stu-id="68890-126">Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="68890-127">たとえば、ケースがインポートされ、そのデータが分析されたとします。</span><span class="sxs-lookup"><span data-stu-id="68890-127">For example, assume a case was imported and its data analyzed.</span></span> <span data-ttu-id="68890-128">増分データの Near-duplicates と Email Threading の結果を取得するには、以前にデータのエクスポートに使用したのと同じバッチで [エクスポート セッションの作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68890-128">In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="68890-129">バッチ エクスポート パラメーターを設定する</span><span class="sxs-lookup"><span data-stu-id="68890-129">Set up batch export parameters</span></span>
<span data-ttu-id="68890-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="68890-130"><a name="BK_SetUpExport"> </a></span></span>

<span data-ttu-id="68890-131">電子情報開示エクスポート ツールは、Advanced eDiscovery からローカル コンピューターに検索結果をエクスポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="68890-131">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer.</span></span>
  
1. <span data-ttu-id="68890-132">Advanced eDiscovery で、ケースを選択し、[セットアップのエクスポート **] をクリック** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="68890-132">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="68890-133">[バッチ **のエクスポート] ボックス** の一覧で、バッチ名を選択するか、結果をエクスポート バッチ 01 (既定のバッチ) にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="68890-133">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="68890-134">既存のケースに追加した新しいファイルの結果をエクスポートするには、現在のバッチを続行します。</span><span class="sxs-lookup"><span data-stu-id="68890-134">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="68890-135">バッチでセッションを作成するには、同じバッチ番号を選択し、[エクスポート セッションの作成] をクリックします。このオプションを使用すると、前のバッチと同じパラメーターを増分形式でエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="68890-135">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="68890-136">新しいバッチにエクスポートするには、[追加] アイコンをクリックし、バッチ名に新しい名前を入力 (または既定の名前を受け入れる) と、Batch の説明に説明 ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) **を入力します**。 </span><span class="sxs-lookup"><span data-stu-id="68890-136">To export to a new batch, click **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="68890-137">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68890-137">Click **OK**.</span></span>
    
    - <span data-ttu-id="68890-138">バッチ名または説明を編集するには、[エクスポート] バッチで名前を選択し、[編集] アイコンをクリックして、 ![ ](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png) フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="68890-138">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="68890-139">エクスポート バッチのセッションを実行した後は、削除できません。</span><span class="sxs-lookup"><span data-stu-id="68890-139">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="68890-140">また、最初のセッションを実行すると、一部のパラメーターのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="68890-140">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="68890-141">重複するエクスポート バッチを作成するには、[重複するエクスポート バッチを作成する] を選択し、重複するバッチの名前と説明をパネル ![ ](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) に入力します。</span><span class="sxs-lookup"><span data-stu-id="68890-141">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="68890-142">エクスポート バッチを削除するには、[エクスポート バッチの **削除**] ![ アイコンを選択します ](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) 。</span><span class="sxs-lookup"><span data-stu-id="68890-142">To delete an export batch, choose **Delete** ![Delete an export batch icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="68890-143">バッチの履歴を表示するには、[バッチ履歴の表示 **履歴**] ![ アイコンを選択します ](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg) 。</span><span class="sxs-lookup"><span data-stu-id="68890-143">To view the history of a batch, choose **Batch history** ![View history icon](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="68890-144">[**母集団]** で、エクスポート バッチの設定を微調整する場合は、[関連性のカットオフ スコアの上のファイルのみを含める] または [エクスポート バッチの絞り込み] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="68890-144">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="68890-145">[関連度カット **オフ スコアの上に** ファイルのみを含める] を選択すると、問題 **が** 有効になります。</span><span class="sxs-lookup"><span data-stu-id="68890-145">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled.</span></span> <span data-ttu-id="68890-146">ファイルの関連性スコアが、選択した問題のカットオフ スコアより高い場合は、[レビュー用] フィルターによって除外されていない限り、ファイルがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="68890-146">If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="68890-147">[絞り込み **エクスポート バッチ**] を選択した場合、[レビュー用] フィールドのラジオ ボタンで **De-dupe** と Filter が有効になります。</span><span class="sxs-lookup"><span data-stu-id="68890-147">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled.</span></span> <span data-ttu-id="68890-148">**De-dupe** を選択した場合、重複するファイルは、定義されているポリシー [ケース レベル (既定) に従ってフィルター処理されます。大文字と小文字を区別して重複するファイルのすべてのセットから、1 つのファイルを含むすべてのファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="68890-148">If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="68890-149">保管担当者レベル: 同じ保管担当者の重複するファイルのすべてのセットから、1 つのファイルを含むすべてのファイルが重複を排除されます。エクスポート出力には、すべての重複ファイルのレコードが含まれている。</span><span class="sxs-lookup"><span data-stu-id="68890-149">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files.</span></span> <span data-ttu-id="68890-150">[確認用 **] フィールドでフィルター** を選択した場合は、[メタデータ] の下の [変更] を選択して **[レビュー用]** フィールドの設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="68890-150">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="68890-151">パッケージ **コンテンツにソース ファイルを含** めるには、[入力ファイルを含める] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68890-151">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="68890-152">この設定をオフにすると、エクスポート プロセスを高速化できます。</span><span class="sxs-lookup"><span data-stu-id="68890-152">You can clear this setting to speed up the export process.</span></span> <span data-ttu-id="68890-153">ネイティブ ファイルは、いずれにしてもエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="68890-153">Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="68890-154">[**メタデータ] で**、[テンプレートのエクスポート]の一覧から次のオプションを選択します (セッションごとに 1 回)。</span><span class="sxs-lookup"><span data-stu-id="68890-154">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="68890-155">**標準**: データ項目、メタデータ、およびプロパティの基本セット。</span><span class="sxs-lookup"><span data-stu-id="68890-155">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="68890-156">このオプションは、インポート データが Advanced eDiscovery で既に処理され、エクスポート データがファイルが既に含まれているシステムにアップロードされる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="68890-156">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="68890-157">既定では、エクスポート テンプレート列が作成され、設定されます。</span><span class="sxs-lookup"><span data-stu-id="68890-157">By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="68890-158">**すべて**: すべての処理データ、分析スコア、関連性スコアを含む標準メタデータの完全なセット。</span><span class="sxs-lookup"><span data-stu-id="68890-158">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="68890-159">このテンプレートは、Advanced eDiscovery が処理を実行し、ファイル データが初めて外部システムにアップロードされる場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="68890-159">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="68890-160">**問題 :**[ **すべての問題] を選択するか** 、作成した特定の問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="68890-160">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="68890-161">**[Destination] の下**:</span><span class="sxs-lookup"><span data-stu-id="68890-161">Under **Destination**:</span></span>
    
    - <span data-ttu-id="68890-162">**ローカル コンピューターへのダウンロード**</span><span class="sxs-lookup"><span data-stu-id="68890-162">**Download to local machine**</span></span>
    
    - <span data-ttu-id="68890-163">**ユーザー定義の Azure BLOB への** エクスポート: このチェック ボックスがオンの場合は、コンテナー URL と SAS トークンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="68890-163">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="68890-164">エクスポート パッケージをユーザー定義の Azure BLOB に保存すると、データは Advanced eDiscovery によって管理されなくなりました。Azure BLOB によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="68890-164">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob.</span></span> <span data-ttu-id="68890-165">つまり、ケースを削除しても、エクスポートされたファイルは Azure BLOB に残ります。</span><span class="sxs-lookup"><span data-stu-id="68890-165">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="68890-166">**将来のエクスポート セッション** 用に SAS トークンを保存する : オンにした場合、SAS トークンは将来使用するために Advanced eDiscovery の内部データベースで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="68890-166">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="68890-167">現在、SAS トークンの有効期限は 1 か月後です。</span><span class="sxs-lookup"><span data-stu-id="68890-167">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="68890-168">1 か月以上後にダウンロードする場合は、最後のセッションを元に戻す必要があります。その後、もう一度エクスポートします。</span><span class="sxs-lookup"><span data-stu-id="68890-168">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="68890-169">[ **変更] を** クリックして、[レビュー用] フィールドの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="68890-169">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    ![エクスポート バッチのレビュー フィールド設定の設定](../media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="68890-171">[ **レビュー フィールドの設定] の**[ **シナリオ** の選択] のドロップダウン リストで、レビューのシナリオと範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="68890-171">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review.</span></span> <span data-ttu-id="68890-172">設定は、選択内容に基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="68890-172">The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="68890-173">**すべて確認** (既定): すべてのメール、添付ファイル、およびドキュメントが既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="68890-173">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="68890-174">**セット内のすべての一** 意のコンテンツを確認します。包括的で一意のコピー、メール セット レベルの一意の添付ファイル、完全に重複しているすべてのセットの代表的な添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="68890-174">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="68890-175">**セット内のすべての一** 意のコンテンツを確認します。包括的なコピーはありません。包括的な添付ファイル、メール セット レベルの一意の添付ファイル、完全に重複しているすべてのセットの代表的な添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="68890-175">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="68890-176">**すべての一意のコンテンツと関連** するファミリ ファイルを確認します。包括性、メール セット レベルの一意の添付ファイル、完全に重複しているすべてのセットの代表的な添付ファイルは、ファミリ ファイルを含むまで展開されます。</span><span class="sxs-lookup"><span data-stu-id="68890-176">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="68890-177">**ユーザー** 設定 (ダイアログのオプションを定義できます): 既定では、現在の選択を維持し、すべてのダイアログ オプションを有効にして、選択を許可します。</span><span class="sxs-lookup"><span data-stu-id="68890-177">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection.</span></span> <span data-ttu-id="68890-178">このオプションを選択すると、メール、ドキュメント、添付ファイル、その他の設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="68890-178">If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="68890-179">[ **メール] で**、エクスポートするメールを選択します。</span><span class="sxs-lookup"><span data-stu-id="68890-179">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="68890-180">**すべてのメール**: (既定) すべてのメールが選択されます。</span><span class="sxs-lookup"><span data-stu-id="68890-180">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="68890-181">**包括的な** メール: 包括的なメールはスレッドの最後のメールであり、スレッドからの他のすべてのメールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="68890-181">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="68890-182">**包括的で一意のコピー**: 同じ件名、本文、添付ファイルを含む包括的なコピー一意の包括的なコピーは、これらの電子メールの一意のコピーです。</span><span class="sxs-lookup"><span data-stu-id="68890-182">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="68890-183">[ **ドキュメント] で**、エクスポートするドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="68890-183">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="68890-184">**すべてのドキュメント**: (既定) すべてのドキュメントが選択されます。</span><span class="sxs-lookup"><span data-stu-id="68890-184">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="68890-185">**ピボット**: ほぼ重複するセットの代表的なファイルとして選択されます。通常、このファイルは、セットを確認するときにベースラインとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="68890-185">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="68890-186">**完全に重複する各セットの** 代表的な例: 一意の近重複ファイル (ピボットを含む)。</span><span class="sxs-lookup"><span data-stu-id="68890-186">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="68890-187">[ **添付ファイル**] で、エクスポートする添付ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="68890-187">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="68890-188">**すべての添付ファイル**: (既定) すべての添付ファイルが選択されます。</span><span class="sxs-lookup"><span data-stu-id="68890-188">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="68890-189">**ケース レベルでの一意の添付ファイル**: 指定したケース内の一意の添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="68890-189">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="68890-190">**電子メール セット レベルでの一意の** 添付ファイル : 指定された電子メール ケース内の一意の添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="68890-190">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="68890-191"> **[Micellaneous] で**、[添付ファイルをドキュメントとして扱う]、[メールをドキュメントとして扱う]、または [展開してファミリ ファイルを含める] を **選択できます**。</span><span class="sxs-lookup"><span data-stu-id="68890-191">Under **Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**.</span></span> <span data-ttu-id="68890-192">[展開] を **選択して** ファミリ ファイルを含める場合、レビューのフラグが設定された各ファイルに対して、同じファミリのすべてのファイルにもフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="68890-192">When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="68890-193">[ **保存] を** 選択して設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="68890-193">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="68890-194">エクスポート パラメーターを指定した後、エクスポート バッチを開始するには、[エクスポート セッションの作成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="68890-194">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="68890-195">エクスポート中、状態はタスクの状態 **で表示されます**。</span><span class="sxs-lookup"><span data-stu-id="68890-195">During export, the status is displayed in **Task status**.</span></span> <span data-ttu-id="68890-196">結果はエクスポートの概要 **に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="68890-196">The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="68890-197">[ファイル **のダウンロード] ウィンドウで** 、[クリップボードに **コピー** ] をクリックして Export キーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="68890-197">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![ファイルをダウンロードする](../media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="68890-199">[閉じる] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68890-199">Click **Close**.</span></span> 
    
    <span data-ttu-id="68890-200">電子情報開示エクスポート ツールが開始されます。</span><span class="sxs-lookup"><span data-stu-id="68890-200">The eDiscovery Export Tool is started.</span></span>
    
    ![電子情報開示のエクスポート ツール](../media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="68890-202">電子情報開示 **エクスポート ツールで、**</span><span class="sxs-lookup"><span data-stu-id="68890-202">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="68890-203">ソース **への接続に** 使用する共有アクセス署名を貼り付け、手順 7 でクリップボードにコピーした Export キーを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="68890-203">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that you copied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="68890-204">[ **参照]** をクリックして、ダウンロードしたエクスポート ファイルをローカル コンピューターに保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="68890-204">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="68890-205">[スタート **] をクリックします**。エクスポート ファイルがローカル コンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="68890-205">Click **Start**.The export files are downloaded to the local machine.</span></span> <span data-ttu-id="68890-206">手順 4 でユーザー定義 **Azure BLOB** へのエクスポートを選択した場合、セッションは選択した BLOB ストレージ URL の宛先にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="68890-206">If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="68890-207">エクスポート レポートのフィールドの詳細については、「レポート フィールドのエクスポート」 [を参照してください](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="68890-207">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="68890-208">レポート出力ファイルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="68890-208">Export report output files</span></span>
<span data-ttu-id="68890-209"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="68890-209"><a name="BK_ExportOutputFIles"> </a></span></span>

<span data-ttu-id="68890-210">次の表に、エクスポート バッチの実行時に生成される出力ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="68890-210">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="68890-211">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="68890-211">**File name**</span></span>|<span data-ttu-id="68890-212">**ファイルの種類**</span><span class="sxs-lookup"><span data-stu-id="68890-212">**File type**</span></span>|<span data-ttu-id="68890-213">**説明**</span><span class="sxs-lookup"><span data-stu-id="68890-213">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="68890-214">エクスポートの概要</span><span class="sxs-lookup"><span data-stu-id="68890-214">Export summary</span></span>  <br/> |<span data-ttu-id="68890-215">csv</span><span class="sxs-lookup"><span data-stu-id="68890-215">csv</span></span>  <br/> |<span data-ttu-id="68890-216">電子情報開示エクスポート ツールによって生成されたログ ファイル。</span><span class="sxs-lookup"><span data-stu-id="68890-216">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="68890-217">トレース</span><span class="sxs-lookup"><span data-stu-id="68890-217">Trace</span></span>  <br/> |<span data-ttu-id="68890-218">txt</span><span class="sxs-lookup"><span data-stu-id="68890-218">txt</span></span>  <br/> |<span data-ttu-id="68890-219">電子情報開示エクスポート ツールによって生成されたログ ファイル。</span><span class="sxs-lookup"><span data-stu-id="68890-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="68890-220">抽出されたテキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="68890-220">Extracted text files</span></span>  <br/> |<span data-ttu-id="68890-221">ファイル フォルダー</span><span class="sxs-lookup"><span data-stu-id="68890-221">File folder</span></span>  <br/> |<span data-ttu-id="68890-222">エクスポートされたファイルの抽出されたテキスト ファイルを含むフォルダー。</span><span class="sxs-lookup"><span data-stu-id="68890-222">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="68890-223">入力ファイルまたはネイティブ ファイル</span><span class="sxs-lookup"><span data-stu-id="68890-223">Input or native files</span></span>  <br/> |<span data-ttu-id="68890-224">ファイル フォルダー</span><span class="sxs-lookup"><span data-stu-id="68890-224">File folder</span></span>  <br/> |<span data-ttu-id="68890-225">エクスポートされたファイルのネイティブ ファイルと入力ファイルを含むフォルダー。</span><span class="sxs-lookup"><span data-stu-id="68890-225">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="68890-226">エクスポート リスト</span><span class="sxs-lookup"><span data-stu-id="68890-226">Export list</span></span>  <br/> |<span data-ttu-id="68890-227">xlsx</span><span class="sxs-lookup"><span data-stu-id="68890-227">xlsx</span></span>  <br/> |<span data-ttu-id="68890-228">xlsx 形式でエクスポートされたファイルのメタデータ。</span><span class="sxs-lookup"><span data-stu-id="68890-228">Exported files metadata in xlsx format.</span></span> <span data-ttu-id="68890-229">ファイル内のフィールドは、ユーザーが選択してエクスポートするテンプレートに従います。</span><span class="sxs-lookup"><span data-stu-id="68890-229">Fields in files are according to template user selects to export.</span></span> <span data-ttu-id="68890-230">必要に応じて、複数のファイルが作成され、それぞれに 100 から 150K の行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="68890-230">If needed, several files are created, each contains 100-150K rows.</span></span> <span data-ttu-id="68890-231">特定の値に含まれる文字数が Excel セルに含まれる文字数を超える場合 (現在の制限は 32,767 文字)、値は許容される最大長までトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="68890-231">If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed.</span></span> <span data-ttu-id="68890-232">値がトリミングされた場合、セルの背景色は赤でユーザーに示されます。""電子メール参加者" は、メールが大量の配布に送信された場合に、長さの制限を超える可能性があるフィールドの例です。</span><span class="sxs-lookup"><span data-stu-id="68890-232">If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution.</span></span> <span data-ttu-id="68890-233">出力フィールド [の詳細については、「](export-report-fields-in-advanced-ediscovery.md) レポート フィールドのエクスポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68890-233">See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.</span></span>  <br/> |
|<span data-ttu-id="68890-234">ファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="68890-234">Load file</span></span>  <br/> |<span data-ttu-id="68890-235">csv</span><span class="sxs-lookup"><span data-stu-id="68890-235">csv</span></span>  <br/> |<span data-ttu-id="68890-236">ファイルメタデータを csv 形式でエクスポートして、別のアプリケーションに読み込む。</span><span class="sxs-lookup"><span data-stu-id="68890-236">Exported files metadata in csv format for loading into a different application.</span></span> <span data-ttu-id="68890-237">ファイル内のフィールドは、ユーザーが選択してエクスポートするテンプレートに従います。</span><span class="sxs-lookup"><span data-stu-id="68890-237">Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="68890-238">成功インジケーター</span><span class="sxs-lookup"><span data-stu-id="68890-238">Success indicator</span></span>  <br/> |<span data-ttu-id="68890-239">txt</span><span class="sxs-lookup"><span data-stu-id="68890-239">txt</span></span>  <br/> |<span data-ttu-id="68890-240">サードパーティの Azure BLOB にエクスポートするときにのみ作成されます。</span><span class="sxs-lookup"><span data-stu-id="68890-240">Only created when exporting to a 3rd party Azure blob.</span></span> <span data-ttu-id="68890-241">エクスポートが完全に成功すると、ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="68890-241">If export succeed completely, the file will be created.</span></span> <span data-ttu-id="68890-242">エラーが発生した場合、または部分的に成功した場合、ファイルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="68890-242">In case of failure, or partial success the file will not be created.</span></span> <span data-ttu-id="68890-243">ファイルはルート フォルダーに作成され、さまざまなエクスポート バッチ/セッションの状態に対する自動追跡が可能になります。</span><span class="sxs-lookup"><span data-stu-id="68890-243">File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses.</span></span> <span data-ttu-id="68890-244">これは空のファイルです。</span><span class="sxs-lookup"><span data-stu-id="68890-244">This is an empty file.</span></span> <span data-ttu-id="68890-245">名前は次TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt。</span><span class="sxs-lookup"><span data-stu-id="68890-245">Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="68890-246">関連項目</span><span class="sxs-lookup"><span data-stu-id="68890-246">See also</span></span>

[<span data-ttu-id="68890-247">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="68890-247">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="68890-248">バッチ履歴の表示と過去の結果のエクスポート</span><span class="sxs-lookup"><span data-stu-id="68890-248">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="68890-249">Advanced eDiscovery のクイック セットアップ</span><span class="sxs-lookup"><span data-stu-id="68890-249">Quick setup for Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="68890-250">レポート フィールドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="68890-250">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
