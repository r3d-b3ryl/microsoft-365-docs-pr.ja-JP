---
title: 高度な電子情報開示でのタグ付けと関連性トレーニング
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: 詳細な電子情報開示の関連性トレーニング段階で、40ファイルのトレーニングサンプルをタグ付けして操作する手順について説明します。
ms.openlocfilehash: 56ce30754e04d4a2adcf854093e603f93be5ae36
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936673"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery-classic"></a><span data-ttu-id="155e6-103">Advanced eDiscovery でのタグ付けと関連性トレーニング (クラシック)</span><span class="sxs-lookup"><span data-stu-id="155e6-103">Tagging and Relevance training in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="155e6-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="155e6-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="155e6-106">このトピックでは、高度な電子情報開示関連トレーニングモジュールを操作する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="155e6-106">This topic describes the procedure for working with the Advanced eDiscovery Relevance training module.</span></span> 
  
<span data-ttu-id="155e6-107">上級電子情報開示で評価が完了した後、関連性トレーニングステージを入力すると、40ファイルのトレーニングサンプルが [タグ] タブに表示され、タグ付けができます。</span><span class="sxs-lookup"><span data-stu-id="155e6-107">After Assessment is completed in Advanced eDiscovery, and you enter the Relevance training stage, a training sample of 40 files is brought into the Tag tab for tagging.</span></span> 
  
## <a name="performing-relevance-training"></a><span data-ttu-id="155e6-108">関連性トレーニングの実行</span><span class="sxs-lookup"><span data-stu-id="155e6-108">Performing Relevance training</span></span>

1. <span data-ttu-id="155e6-109">[**関連性 \> タグ**] タブの左側のウィンドウには、既定で [タグ] ウィンドウが表示され、サンプルファイルが一度に1つずつタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="155e6-109">In the **Relevance \> Tag** tab, the Tagging pane is displayed by default in the left pane and the sample files are displayed, one at a time for tagging.</span></span> 
    
    ![関連性タグ パネル](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    <span data-ttu-id="155e6-111">[**タグ**] タブには、ファイルの表示名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-111">In the **Tag** tab, the file's display name is shown.</span></span> <span data-ttu-id="155e6-112">これは、パス、電子メールの件名、タイトル、またはユーザー定義の名前にすることができます。</span><span class="sxs-lookup"><span data-stu-id="155e6-112">This could be the path, email subject, title, or user-defined name.</span></span> <span data-ttu-id="155e6-113">ID、ファイルパス、またはテキストパスは、ファイルのパスを右クリックするとコピーできます。</span><span class="sxs-lookup"><span data-stu-id="155e6-113">The ID, file path or text path can be copied by right-clicking on the file's path.</span></span> 
    
    <span data-ttu-id="155e6-114">**タグ**タブタグ付け統計情報には、ファイルのサンプル番号 (左側のウィンドウの上部)、現在表示されているファイルの数 (右ペインの下部)、サンプル内のタグ付きファイルの現在の総数 (左側のウィンドウの下部) が表示されます。これは、ファイルにタグを付けると変更されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-114">The **Tag** tab tagging statistics show the file sample number (at the top of the left pane), the number of the currently displayed file out of the total files in the sample (bottom of right pane), and the current total number of tagged files in the sample (bottom of the left pane), which changes as you tag files.</span></span> <span data-ttu-id="155e6-115">これは、評価、トレーニング、キャッチアップ、またはテストで行われるすべての関連性タグ付けに適用されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-115">This applies for any Relevance tagging done, whether in Assessment, Training, Catch-up, or Test.</span></span> 
    
    <span data-ttu-id="155e6-116">コメント、タグ、およびファミリーファイルの存在を示すアイコンは、ファイルの上のバーにあるファイルビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-116">Icons indicating the existence of comments, tags, and family files are displayed in the file view in a bar above the file.</span></span>
    
2. <span data-ttu-id="155e6-117">次の表に示すように、[タグ付け] オプションアイコンボタンまたはキーボードショートカットを使用して、ファイルの関連性を特定し、ファイルにタグを付けます。</span><span class="sxs-lookup"><span data-stu-id="155e6-117">Determine the file's relevance for the case issue and tag the file using either the Tagging option icon buttons or keyboard shortcuts, as shown in the following table:</span></span>

|<span data-ttu-id="155e6-118">**[タグ付け] オプション**</span><span class="sxs-lookup"><span data-stu-id="155e6-118">**Tagging option**</span></span>|<span data-ttu-id="155e6-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="155e6-119">**Description**</span></span>|<span data-ttu-id="155e6-120">**ショートカット キー**</span><span class="sxs-lookup"><span data-stu-id="155e6-120">**Keyboard shortcut**</span></span>|<span data-ttu-id="155e6-121">**複数の問題の場合-バルクタグのキーボードショートカット**</span><span class="sxs-lookup"><span data-stu-id="155e6-121">**For multiple issues - bulk tag keyboard shortcut**</span></span>|
|-----|-----|-----|-----|
|<span data-ttu-id="155e6-122">R</span><span class="sxs-lookup"><span data-stu-id="155e6-122">R</span></span>  <br/> |<span data-ttu-id="155e6-123">対応</span><span class="sxs-lookup"><span data-stu-id="155e6-123">Relevant</span></span>  <br/> |<span data-ttu-id="155e6-124">Z</span><span class="sxs-lookup"><span data-stu-id="155e6-124">Z</span></span>  <br/> |<span data-ttu-id="155e6-125">Shift + Z</span><span class="sxs-lookup"><span data-stu-id="155e6-125">Shift + Z</span></span>  <br/> |
|<span data-ttu-id="155e6-126">NR</span><span class="sxs-lookup"><span data-stu-id="155e6-126">NR</span></span>  <br/> |<span data-ttu-id="155e6-127">該当なし</span><span class="sxs-lookup"><span data-stu-id="155e6-127">Not relevant</span></span>  <br/> |<span data-ttu-id="155e6-128">X</span><span class="sxs-lookup"><span data-stu-id="155e6-128">X</span></span>  <br/> |<span data-ttu-id="155e6-129">Shift + X</span><span class="sxs-lookup"><span data-stu-id="155e6-129">Shift + X</span></span>  <br/> |
|<span data-ttu-id="155e6-130">Skip</span><span class="sxs-lookup"><span data-stu-id="155e6-130">Skip</span></span>  <br/> |<span data-ttu-id="155e6-131">Skip</span><span class="sxs-lookup"><span data-stu-id="155e6-131">Skip</span></span>  <br/> |<span data-ttu-id="155e6-132">C</span><span class="sxs-lookup"><span data-stu-id="155e6-132">C</span></span>  <br/> |<span data-ttu-id="155e6-133">Shift + A</span><span class="sxs-lookup"><span data-stu-id="155e6-133">Shift + A</span></span>  <br/> |
   
  - <span data-ttu-id="155e6-134">ファイルに複数の問題が存在する場合、1つの問題にタグ付けすると、選択範囲は次の問題に移動します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="155e6-134">When multiple issues exist for a file, after tagging one issue, the selection moves to the next issue (if any).</span></span> 
    
  - <span data-ttu-id="155e6-135">キーワードを強調表示するときに、管理者またはケースマネージャーによって定義されたキーワード (関連性 \> の設定の強調表示キーワード) は、タグ付け中に関連ファイルを識別するのに役立つように、指定された色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-135">Keywords that were defined by the Administrator or Case manager when highlighting keywords (Relevance setup \> Highlighted keywords), will be displayed (in specified colors) to help identify relevant files while tagging.</span></span> <span data-ttu-id="155e6-136">キーワードに二重下線がある場合は、それをクリックして、キーワードの説明を含むツールヒントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="155e6-136">If a keyword has a double underline, it can be clicked to display a tool-tip with the keyword's description.</span></span> 
    
    <span data-ttu-id="155e6-137">必要に応じて、[**タグ**] タブの [**タグ設定**] をクリックして、次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="155e6-137">Optionally, in the **Tag** tab, click **Tag settings** to set the following options:</span></span> 
    
    ![関連性タグの設定](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - <span data-ttu-id="155e6-139">[ **Bulk tag**]: このオプションを使用して、ファイルに複数の問題を割り当てるには、[**すべて**] を選択して、すべての問題について選択したファイルのタグを設定する (既にタグ付けされている問題を上書きする) か、**他**のタグの付いた問題にタグを適用するようにします。</span><span class="sxs-lookup"><span data-stu-id="155e6-139">**Bulk tag**: Use this option to assign multiple issues for a file by selecting **All** to set the tag for the selected file for all issues (overrides already tagged issues) or by selecting **The rest** to apply the tag to the remaining untagged issues.</span></span> <span data-ttu-id="155e6-140">選択されたオプションは、このユーザーのすべてのケースに対して、そのユーザーによって変更されるまで有効になります (設定は、すべてのユーザーのケースに対してユーザーごとに行われます)。</span><span class="sxs-lookup"><span data-stu-id="155e6-140">The selected option remains in effect for all of this user's cases until changed by that user (setting is per user for all the user's cases).</span></span> 
    
  - <span data-ttu-id="155e6-141">[**自動タグ**]: このチェックボックスをオンにすると、1つの関連するタグ付けの後に、ファイルに関連するその他の問題を設定できます。</span><span class="sxs-lookup"><span data-stu-id="155e6-141">**Auto tag**: Select this check box to set other issues for a file as Not relevant after a single Relevant tagging.</span></span>
    
  - <span data-ttu-id="155e6-142">[**自動繰り上げ**]: 最後のまたはタグなしの問題をタグ付けするときに、表示されているファイルの選択を次のファイルに移動するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="155e6-142">**Auto advance**: Select this check box to move the displayed file selection to the next file when tagging the last or only untagged issue.</span></span> 
    
    <span data-ttu-id="155e6-143">スキップされたファイルは、関連性のトレーニングや関連性のスコアリングの目的のために考慮されません。</span><span class="sxs-lookup"><span data-stu-id="155e6-143">Skipped files will not be considered for Relevance training and Relevance scoring purposes.</span></span>
    
3. <span data-ttu-id="155e6-144">ファイルに関連付けられている自由テキストコメントは、左ウィンドウのドロップダウンリストの [**コメント**] オプションを使用して表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="155e6-144">Free-text comments, associated with a file, can be viewed and edited via the **Comment** option in the left pane drop-down list.</span></span> <span data-ttu-id="155e6-145">(省略可能)</span><span class="sxs-lookup"><span data-stu-id="155e6-145">(optional)</span></span> 
    
4. <span data-ttu-id="155e6-146">タグ付けのガイドラインを表示するには、左側のウィンドウのドロップダウンリストで [**タグ付けのガイドライン**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="155e6-146">Guidelines for tagging can be viewed by selecting the **Tagging guidelines** option in the left pane drop-down list.</span></span> 
    
5. <span data-ttu-id="155e6-147">リスト内のすべてのファイルのタグ付けが終了し、結果を計算する準備ができたら、[**計算**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="155e6-147">After you finish tagging all files in the list and are ready to calculate the results, click **Calculate**.</span></span> <span data-ttu-id="155e6-148">[**トラック**] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-148">The **Track** tab is displayed.</span></span> 
    
## <a name="working-with-the-sample-files-list"></a><span data-ttu-id="155e6-149">サンプルファイルリストを使用する</span><span class="sxs-lookup"><span data-stu-id="155e6-149">Working with the sample files list</span></span>

<span data-ttu-id="155e6-150">サンプルファイルリストを使用すると、トレーニングサンプル内のファイルの一覧を表示し、1つ以上のファイルに対してさまざまなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="155e6-150">The sample files list allows you to view a list of the files in a training sample and perform various action on one or more files.</span></span> <span data-ttu-id="155e6-151">[**関連性** \> **タグ**] タブには、評価、トレーニング、キャッチアップ、および不整合のプロセスで処理するためのサンプルファイルの一覧が [**サンプルファイル**] 左ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-151">In the **Relevance** \> **Tag** tab, the **Sample files** left pane displays a list of sample files for processing with Assessment, Training, Catch-up, and Inconsistencies processes.</span></span> 
  
1. <span data-ttu-id="155e6-152">[**関連性 \> タグ**] タブで、左側のウィンドウのドロップダウンリストでサンプルファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="155e6-152">In the **Relevance \> Tag** tab, select the Sample files in the left pane drop-down list.</span></span> <span data-ttu-id="155e6-153">左側のウィンドウにサンプルファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-153">The sample files are listed in the left pane.</span></span> 
    
    ![関連性タグのサンプル ファイル一覧](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. <span data-ttu-id="155e6-155">**サンプル**または**ファイル**ボックスにその番号を入力または選択して、特定のサンプルまたはファイル番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="155e6-155">Select a specific sample or file number by entering or selecting its number in the **Sample** or **File** boxes.</span></span> 
    
  -   - <span data-ttu-id="155e6-156">ファイルシーケンス番号は、[**タグ**] タブの表示されるファイルの一覧の左側の列に表示されます。ヘッダーをクリックすると、ファイルの元の表示順が元の順序に戻ります。</span><span class="sxs-lookup"><span data-stu-id="155e6-156">A file sequence number is listed in the left column of the displayed file list on the **Tag** tab. By clicking the header, the original displayed order of the files returns to its original order.</span></span> 
    
  - <span data-ttu-id="155e6-157">ファイル行をクリックすると、右側のウィンドウにその内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="155e6-157">Clicking on a file row displays its content in the right pane.</span></span>
    
  - <span data-ttu-id="155e6-158">下のメニューバーオプションを使用して、現在のサンプルのファイル間を移動します。</span><span class="sxs-lookup"><span data-stu-id="155e6-158">Navigate between files in the current sample by using the lower menu bar options.</span></span> <span data-ttu-id="155e6-159">さらに、ナビゲーションキーボードショートカットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="155e6-159">In addition, navigational keyboard shortcuts are available:</span></span>
    
    <span data-ttu-id="155e6-160">サンプルの最初のファイルに移動するには、Shift + Ctrl +\<</span><span class="sxs-lookup"><span data-stu-id="155e6-160">To navigate to the first file in the sample: Shift + Ctrl + \<</span></span>
    
    <span data-ttu-id="155e6-161">サンプル内の前のファイルに移動するには、Shift +\<</span><span class="sxs-lookup"><span data-stu-id="155e6-161">To navigate to the previous file in the sample: Shift + \<</span></span>
    
    <span data-ttu-id="155e6-162">サンプル内の次のファイルに移動するには、Shift +\></span><span class="sxs-lookup"><span data-stu-id="155e6-162">To navigate to the next file in the sample: Shift + \></span></span>
    
    <span data-ttu-id="155e6-163">サンプルの最後のファイルに移動するには、Shift + Ctrl +\></span><span class="sxs-lookup"><span data-stu-id="155e6-163">To navigate to the last file in the sample: Shift + Ctrl + \></span></span>
    
## <a name="see-also"></a><span data-ttu-id="155e6-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="155e6-164">See also</span></span>

[<span data-ttu-id="155e6-165">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="155e6-165">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="155e6-166">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="155e6-166">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="155e6-167">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="155e6-167">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="155e6-168">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="155e6-168">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="155e6-169">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="155e6-169">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="155e6-170">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="155e6-170">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

