---
title: Advanced eDiscovery でのタグ付けと関連性のトレーニング
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Advanced eDiscovery の関連度トレーニング ステージで、タグを付け、40 ファイルのトレーニング サンプルを使用する手順について説明します。
ms.openlocfilehash: d576b0a907a4c12eabe4f3cba9846de670b0ee12
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663452"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery-classic"></a><span data-ttu-id="624d1-103">Advanced eDiscovery (クラシック) でのタグ付けと関連性のトレーニング</span><span class="sxs-lookup"><span data-stu-id="624d1-103">Tagging and Relevance training in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="624d1-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="624d1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="624d1-106">このトピックでは、Advanced eDiscovery Relevance トレーニング モジュールを操作する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="624d1-106">This topic describes the procedure for working with the Advanced eDiscovery Relevance training module.</span></span> 
  
<span data-ttu-id="624d1-107">Advanced eDiscovery で Assessment が完了し、関連性トレーニング ステージに入った後、40 ファイルのトレーニング サンプルがタグ付けのために [タグ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-107">After Assessment is completed in Advanced eDiscovery, and you enter the Relevance training stage, a training sample of 40 files is brought into the Tag tab for tagging.</span></span> 
  
## <a name="performing-relevance-training"></a><span data-ttu-id="624d1-108">関連性トレーニングの実行</span><span class="sxs-lookup"><span data-stu-id="624d1-108">Performing Relevance training</span></span>

1. <span data-ttu-id="624d1-109">[関連 **タグ] \> タブ** では、既定で [タグ] ウィンドウが左側のウィンドウに表示され、サンプル ファイルがタグ付け用に一度に 1 つ表示されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-109">In the **Relevance \> Tag** tab, the Tagging pane is displayed by default in the left pane and the sample files are displayed, one at a time for tagging.</span></span> 
    
    ![関連性タグ パネル](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    <span data-ttu-id="624d1-111">[ **タグ]** タブに、ファイルの表示名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-111">In the **Tag** tab, the file's display name is shown.</span></span> <span data-ttu-id="624d1-112">パス、メールの件名、タイトル、またはユーザー定義の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="624d1-112">This could be the path, email subject, title, or user-defined name.</span></span> <span data-ttu-id="624d1-113">ID、ファイル パス、またはテキスト パスは、ファイルのパスを右クリックしてコピーできます。</span><span class="sxs-lookup"><span data-stu-id="624d1-113">The ID, file path or text path can be copied by right-clicking on the file's path.</span></span> 
    
    <span data-ttu-id="624d1-114">[タグ] タブのタグ付け統計情報には、ファイルのサンプル番号 (左側のウィンドウの上部)、サンプル内の合計ファイルから現在表示されているファイルの数 (右側のウィンドウの下部)、およびサンプル内のタグ付けされたファイルの現在の総数 (左側のウィンドウの下部) が表示されます。これは、ファイルにタグを付けると変化します。</span><span class="sxs-lookup"><span data-stu-id="624d1-114">The **Tag** tab tagging statistics show the file sample number (at the top of the left pane), the number of the currently displayed file out of the total files in the sample (bottom of right pane), and the current total number of tagged files in the sample (bottom of the left pane), which changes as you tag files.</span></span> <span data-ttu-id="624d1-115">これは、Assessment、Training、Catch-up、Test など、行われたすべての関連性タグに適用されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-115">This applies for any Relevance tagging done, whether in Assessment, Training, Catch-up, or Test.</span></span> 
    
    <span data-ttu-id="624d1-116">コメント、タグ、およびファミリ ファイルの存在を示すアイコンは、ファイルの上のバーのファイル ビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-116">Icons indicating the existence of comments, tags, and family files are displayed in the file view in a bar above the file.</span></span>
    
2. <span data-ttu-id="624d1-117">次の表に示すように、[タグ付け] オプション アイコン ボタンまたはキーボード ショートカットを使用して、ケースの問題に対するファイルの関連性を確認し、ファイルにタグを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="624d1-117">Determine the file's relevance for the case issue and tag the file using either the Tagging option icon buttons or keyboard shortcuts, as shown in the following table:</span></span>

|<span data-ttu-id="624d1-118">**タグ付けオプション**</span><span class="sxs-lookup"><span data-stu-id="624d1-118">**Tagging option**</span></span>|<span data-ttu-id="624d1-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="624d1-119">**Description**</span></span>|<span data-ttu-id="624d1-120">**ショートカット キー**</span><span class="sxs-lookup"><span data-stu-id="624d1-120">**Keyboard shortcut**</span></span>|<span data-ttu-id="624d1-121">**複数の問題の場合 - 一括タグのキーボード ショートカット**</span><span class="sxs-lookup"><span data-stu-id="624d1-121">**For multiple issues - bulk tag keyboard shortcut**</span></span>|
|-----|-----|-----|-----|
|<span data-ttu-id="624d1-122">R</span><span class="sxs-lookup"><span data-stu-id="624d1-122">R</span></span>  <br/> |<span data-ttu-id="624d1-123">関連</span><span class="sxs-lookup"><span data-stu-id="624d1-123">Relevant</span></span>  <br/> |<span data-ttu-id="624d1-124">Z</span><span class="sxs-lookup"><span data-stu-id="624d1-124">Z</span></span>  <br/> |<span data-ttu-id="624d1-125">Shift + Z</span><span class="sxs-lookup"><span data-stu-id="624d1-125">Shift + Z</span></span>  <br/> |
|<span data-ttu-id="624d1-126">NR</span><span class="sxs-lookup"><span data-stu-id="624d1-126">NR</span></span>  <br/> |<span data-ttu-id="624d1-127">関連しない</span><span class="sxs-lookup"><span data-stu-id="624d1-127">Not relevant</span></span>  <br/> |<span data-ttu-id="624d1-128">X</span><span class="sxs-lookup"><span data-stu-id="624d1-128">X</span></span>  <br/> |<span data-ttu-id="624d1-129">Shift + X</span><span class="sxs-lookup"><span data-stu-id="624d1-129">Shift + X</span></span>  <br/> |
|<span data-ttu-id="624d1-130">Skip</span><span class="sxs-lookup"><span data-stu-id="624d1-130">Skip</span></span>  <br/> |<span data-ttu-id="624d1-131">Skip</span><span class="sxs-lookup"><span data-stu-id="624d1-131">Skip</span></span>  <br/> |<span data-ttu-id="624d1-132">C</span><span class="sxs-lookup"><span data-stu-id="624d1-132">C</span></span>  <br/> |<span data-ttu-id="624d1-133">Shift + A</span><span class="sxs-lookup"><span data-stu-id="624d1-133">Shift + A</span></span>  <br/> |
   
  - <span data-ttu-id="624d1-134">1 つのファイルに複数の問題が存在する場合、1 つの問題にタグ付けした後、選択内容は次の問題に移動します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="624d1-134">When multiple issues exist for a file, after tagging one issue, the selection moves to the next issue (if any).</span></span> 
    
  - <span data-ttu-id="624d1-135">タグ付け中に関連ファイルを識別するために、管理者またはケース 管理者がキーワードを強調表示するときに定義したキーワード (関連性セットアップの強調表示されたキーワード) が (指定された色で) 表示されます。 \></span><span class="sxs-lookup"><span data-stu-id="624d1-135">Keywords that were defined by the Administrator or Case manager when highlighting keywords (Relevance setup \> Highlighted keywords), will be displayed (in specified colors) to help identify relevant files while tagging.</span></span> <span data-ttu-id="624d1-136">キーワードに二重下線がある場合は、クリックすると、キーワードの説明を含むツール ヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="624d1-136">If a keyword has a double underline, it can be clicked to display a tool-tip with the keyword's description.</span></span> 
    
    <span data-ttu-id="624d1-137">必要に応じて、[タグ] **タブで** [タグの設定] **をクリックして** 、次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="624d1-137">Optionally, in the **Tag** tab, click **Tag settings** to set the following options:</span></span> 
    
    ![関連性タグの設定](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - <span data-ttu-id="624d1-139">**一** 括タグ : このオプションを使用して、ファイルに対して複数の問題を割り当てるには、[すべて] を選択して、選択したファイルのタグをすべての問題に対して設定するか (既にタグ付けされている問題を上書きする)、または [残り] を選択してタグをタグ付けされていない残りの問題に適用します。</span><span class="sxs-lookup"><span data-stu-id="624d1-139">**Bulk tag**: Use this option to assign multiple issues for a file by selecting **All** to set the tag for the selected file for all issues (overrides already tagged issues) or by selecting **The rest** to apply the tag to the remaining untagged issues.</span></span> <span data-ttu-id="624d1-140">選択したオプションは、そのユーザーによって変更されるまで、このユーザーのすべてのケースに対して有効です (ユーザーごとの設定は、すべてのユーザーの場合に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="624d1-140">The selected option remains in effect for all of this user's cases until changed by that user (setting is per user for all the user's cases).</span></span> 
    
  - <span data-ttu-id="624d1-141">**自動タグ**: 1 つの関連タグの後にファイルのその他の問題を [関連しない] として設定するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="624d1-141">**Auto tag**: Select this check box to set other issues for a file as Not relevant after a single Relevant tagging.</span></span>
    
  - <span data-ttu-id="624d1-142">**自動進** む : 最後の問題またはタグ付けされていない問題のみをタグ付けするときに、表示されたファイルの選択を次のファイルに移動するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="624d1-142">**Auto advance**: Select this check box to move the displayed file selection to the next file when tagging the last or only untagged issue.</span></span> 
    
    <span data-ttu-id="624d1-143">スキップされたファイルは、関連性トレーニングと関連性スコアリングの目的では考慮されません。</span><span class="sxs-lookup"><span data-stu-id="624d1-143">Skipped files will not be considered for Relevance training and Relevance scoring purposes.</span></span>
    
3. <span data-ttu-id="624d1-144">ファイルに関連付けられた自由形式のコメントは、左側のウィンドウのドロップダウン リストの **[コメント** ] オプションを使用して表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="624d1-144">Free-text comments, associated with a file, can be viewed and edited via the **Comment** option in the left pane drop-down list.</span></span> <span data-ttu-id="624d1-145">(省略可能)</span><span class="sxs-lookup"><span data-stu-id="624d1-145">(optional)</span></span> 
    
4. <span data-ttu-id="624d1-146">タグ付けのガイドラインは、左側のウィンドウのドロップダウン リストで [タグ付けガイドライン] オプションを選択することで表示できます。</span><span class="sxs-lookup"><span data-stu-id="624d1-146">Guidelines for tagging can be viewed by selecting the **Tagging guidelines** option in the left pane drop-down list.</span></span> 
    
5. <span data-ttu-id="624d1-147">リスト内のすべてのファイルのタグ付けを完了し、結果を計算する準備ができたら、[計算] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624d1-147">After you finish tagging all files in the list and are ready to calculate the results, click **Calculate**.</span></span> <span data-ttu-id="624d1-148">[ **トラック]** タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-148">The **Track** tab is displayed.</span></span> 
    
## <a name="working-with-the-sample-files-list"></a><span data-ttu-id="624d1-149">サンプル ファイル の一覧を操作する</span><span class="sxs-lookup"><span data-stu-id="624d1-149">Working with the sample files list</span></span>

<span data-ttu-id="624d1-150">サンプル ファイルの一覧では、トレーニング サンプル内のファイルの一覧を表示し、1 つ以上のファイルに対してさまざまなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="624d1-150">The sample files list allows you to view a list of the files in a training sample and perform various action on one or more files.</span></span> <span data-ttu-id="624d1-151">[関連 **タグ]** タブの左側の [サンプル ファイル] ウィンドウには \> 、Assessment、Training、Catch-up、および Inconsistencies の各プロセスで処理するサンプル ファイルの一覧が表示されます。 </span><span class="sxs-lookup"><span data-stu-id="624d1-151">In the **Relevance** \> **Tag** tab, the **Sample files** left pane displays a list of sample files for processing with Assessment, Training, Catch-up, and Inconsistencies processes.</span></span> 
  
1. <span data-ttu-id="624d1-152">[関連性 **タグ] \> タブ** で、左側のウィンドウのドロップダウン リストからサンプル ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="624d1-152">In the **Relevance \> Tag** tab, select the Sample files in the left pane drop-down list.</span></span> <span data-ttu-id="624d1-153">サンプル ファイルが左側のウィンドウに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-153">The sample files are listed in the left pane.</span></span> 
    
    ![関連性タグのサンプル ファイル一覧](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. <span data-ttu-id="624d1-155">[サンプル] ボックスまたは [ファイル] ボックスに番号を入力または選択して、特定のサンプルまたはファイル **番号\*\*\*\*を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="624d1-155">Select a specific sample or file number by entering or selecting its number in the **Sample** or **File** boxes.</span></span> 
    
  -   - <span data-ttu-id="624d1-156">ファイル シーケンス番号は、[タグ] タブに表示されるファイル一覧の左側の列に **表示** されます。ヘッダーをクリックすると、ファイルの元の表示順序が元の順序に戻されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-156">A file sequence number is listed in the left column of the displayed file list on the **Tag** tab. By clicking the header, the original displayed order of the files returns to its original order.</span></span> 
    
  - <span data-ttu-id="624d1-157">ファイル行をクリックすると、右側のウィンドウに内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="624d1-157">Clicking on a file row displays its content in the right pane.</span></span>
    
  - <span data-ttu-id="624d1-158">下のメニュー バーオプションを使用して、現在のサンプルのファイル間を移動します。</span><span class="sxs-lookup"><span data-stu-id="624d1-158">Navigate between files in the current sample by using the lower menu bar options.</span></span> <span data-ttu-id="624d1-159">さらに、ナビゲーション キーボード ショートカットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="624d1-159">In addition, navigational keyboard shortcuts are available:</span></span>
    
    <span data-ttu-id="624d1-160">サンプルの最初のファイルに移動するには、Shift + Ctrl + \<</span><span class="sxs-lookup"><span data-stu-id="624d1-160">To navigate to the first file in the sample: Shift + Ctrl + \<</span></span>
    
    <span data-ttu-id="624d1-161">サンプルの前のファイルに移動するには:Shift + \<</span><span class="sxs-lookup"><span data-stu-id="624d1-161">To navigate to the previous file in the sample: Shift + \<</span></span>
    
    <span data-ttu-id="624d1-162">サンプル内の次のファイルに移動するには:Shift + \></span><span class="sxs-lookup"><span data-stu-id="624d1-162">To navigate to the next file in the sample: Shift + \></span></span>
    
    <span data-ttu-id="624d1-163">サンプルの最後のファイルに移動するには:Shift + Ctrl + \></span><span class="sxs-lookup"><span data-stu-id="624d1-163">To navigate to the last file in the sample: Shift + Ctrl + \></span></span>
    
## <a name="see-also"></a><span data-ttu-id="624d1-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="624d1-164">See also</span></span>

[<span data-ttu-id="624d1-165">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="624d1-165">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="624d1-166">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="624d1-166">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="624d1-167">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="624d1-167">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="624d1-168">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="624d1-168">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="624d1-169">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="624d1-169">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="624d1-170">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="624d1-170">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

