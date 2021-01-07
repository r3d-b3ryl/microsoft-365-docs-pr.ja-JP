---
title: Advanced eDiscovery での関連性分析の追跡
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Advanced eDiscovery でケースの問題に関する関連性トレーニングの状態と結果を表示および解釈する方法について説明します。
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769182"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="dabdc-103">Advanced eDiscovery での関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="dabdc-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="dabdc-104">Advanced eDiscovery の [関連度トラック] タブには、[タグ] タブで実行された関連性トレーニングの計算された有効性が表示され、関連性における反復的なトレーニング プロセスの次のステップが示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="dabdc-105">関連性トレーニングの状態の追跡</span><span class="sxs-lookup"><span data-stu-id="dabdc-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="dabdc-106">以下の [問題名] ダイアログの次の例に示すように、ケースの問題の関連トラックで次の詳細 **を** 表示します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="dabdc-107">**Assessment**: この進行状況インジケーターは、この時点で実行された関連性トレーニングがエラーの余白の観点から評価目標を達成した度合いを示します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="dabdc-108">関連性トレーニングの結果の豊富さも表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="dabdc-109">**トレーニング**: この色分けされた進行状況インジケーターとツール ヒントは、関連性トレーニング結果の安定性と、各問題にタグ付けされた関連性トレーニング サンプルの数を示す数値スケールを示します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="dabdc-110">専門家は、反復的な関連性トレーニング プロセスの進行状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="dabdc-111">**バッチ計算**: この進行状況インジケーターは、バッチ計算の完了に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="dabdc-112">**次の手順**: 実行する次の手順の推奨事項を表示します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="dabdc-113">この例では、問題に対して正常に完了した Assessment が表示され、完了した色の進行状況インジケーターとチェックマークで示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="dabdc-114">タグ付けは進行中ですが、ケースは不安定と見なされます (安定性の状態もツール ヒントに表示されます)。</span><span class="sxs-lookup"><span data-stu-id="dabdc-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="dabdc-115">次の手順の推奨事項は「トレーニング」です。</span><span class="sxs-lookup"><span data-stu-id="dabdc-115">The next step recommendation is "Training".</span></span> 
  
    ![関連性トラックのトレーニングのステップ 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="dabdc-117">展開されたビューには、追加の情報とオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="dabdc-118">表示される現在のエラー余白は、既存の (既にタグが付けられた) 評価ファイルを基に、現在の評価の状態における取り消しのエラー余白です。</span><span class="sxs-lookup"><span data-stu-id="dabdc-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="dabdc-119">Assessment ステージは、問題ごとに Assessmentチェック ボックスをオフにし、次に "すべての問題" に対してオフにすることでバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="dabdc-120">ただし、その結果、この問題に関する統計情報はありません。</span><span class="sxs-lookup"><span data-stu-id="dabdc-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="dabdc-121">>チェック **ボックスを** オフにできるのは、評価が実行される前のみです。</span><span class="sxs-lookup"><span data-stu-id="dabdc-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="dabdc-122">1 つのケースに複数の問題が存在する場合、問題ごとにチェック ボックスがオフの場合にのみ評価がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="dabdc-123">ファイルの最初のサンプル セットで評価が完了しない場合、より多くのファイルにタグ付けする次の手順が評価になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dabdc-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="dabdc-124">関連性 **トラック** \> **では、** トレーニングの進行状況インジケーターとツール ヒントは、安定性に到達するために必要な追加サンプルの推定数を示します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="dabdc-125">この見積もりは、必要な追加のトレーニングのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![関連性トラックのトレーニング](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="dabdc-127">タグ付けが完了し、トレーニングを継続する必要がある場合は、[トレーニング] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="dabdc-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="dabdc-128">追加のトレーニングのために、読み込まれたファイル セットからファイルの別のサンプル セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="dabdc-129">その後、[タグ] タブに戻り、タグを付け、さらに多くのファイルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="dabdc-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="dabdc-130">安定したトレーニング レベルに達する</span><span class="sxs-lookup"><span data-stu-id="dabdc-130">Reaching stable training levels</span></span>

<span data-ttu-id="dabdc-131">評価ファイルが安定したレベルのトレーニングを完了すると、Advanced eDiscovery はバッチ計算の準備が整います。</span><span class="sxs-lookup"><span data-stu-id="dabdc-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dabdc-132">通常、3 つの安定したトレーニング サンプルの後、次の手順は 「バッチ計算」です。</span><span class="sxs-lookup"><span data-stu-id="dabdc-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="dabdc-133">たとえば、以前のサンプルからファイルのタグ付けに変更が加えらた場合や、シード ファイルが追加された場合など、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dabdc-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="dabdc-134">バッチ計算の実行</span><span class="sxs-lookup"><span data-stu-id="dabdc-134">Performing Batch calculation</span></span>

<span data-ttu-id="dabdc-135">バッチ計算は、トレーニングが正常に完了した後の次の手順として実行されます (進行状況バーに安定したトレーニング状態が表示されると、ツール ヒントにチェックマークと安定した状態が表示されます)。バッチ計算は、ファイルの関連性を評価し、関連性スコアを割り当てる、関連度トレーニング中に取得した知識をファイルの母集団全体に適用します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="dabdc-136">複数の問題がある場合は、問題ごとにバッチ計算が行われます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="dabdc-137">バッチ計算中は、すべてのファイルの処理中に進行状況が監視されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="dabdc-138">ここで推奨される次の手順は "None" で、この時点で追加の反復的な関連性トレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dabdc-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="dabdc-139">次のフェーズは、[関連性 **の決定] \> タブ** です。</span><span class="sxs-lookup"><span data-stu-id="dabdc-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="dabdc-140">バッチ計算後に新しいファイルをインポートする場合、管理者はインポートしたファイルを新しい負荷に追加できます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dabdc-141">バッチ計算中に **[キャンセル** ] をクリックすると、既に実行された処理が保存されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="dabdc-142">バッチ計算を再度実行すると、最後に実行された時点から処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="dabdc-143">タグ付けの一貫性の評価</span><span class="sxs-lookup"><span data-stu-id="dabdc-143">Assessing tagging consistency</span></span>

<span data-ttu-id="dabdc-144">ファイルのタグ付けに不整合がある場合は、分析に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dabdc-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="dabdc-145">Advanced eDiscovery タグ付けの一貫性プロセスは、結果が最適ではない場合や一貫性が疑わしい場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="dabdc-146">一貫性のないタグが付けられた可能性があるファイルの一覧が返され、必要に応じて確認と再タグ付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dabdc-147">評価後に 7 回以上のトレーニング ラウンドを行った後、タグ付けの一貫性を関連トラックの問題 \>  \>  \> **の詳細な結果トレーニングの** 進行状況 \> **に表示できます**。</span><span class="sxs-lookup"><span data-stu-id="dabdc-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="dabdc-148">このレビューは、一度に 1 つの問題に対して行われます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="dabdc-149">関連性 **トラックで \> 、** 問題の行を展開します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="dabdc-150">次の手順の右側 **にある [変更]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="dabdc-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="dabdc-151">7 **つのトレーニング サンプルの\*\*\*\*後、[次** の手順] オプションとして [タグの不整合] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dabdc-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="dabdc-152">[タグ **の不整合] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dabdc-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="dabdc-153">[ **タグ]** タブが開き、必要に応じて再タグ付けする不整合の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="dabdc-154">[計算 **] を** クリックして変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="dabdc-155">タグ付けの不整合の後の次の手順は、"トレーニング" です。</span><span class="sxs-lookup"><span data-stu-id="dabdc-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="dabdc-156">関連性の結果の表示と使用</span><span class="sxs-lookup"><span data-stu-id="dabdc-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="dabdc-157">[関連性 **トラック] \> タブ** で、問題の行を展開し、[詳細な結果] の横にある **[表示**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="dabdc-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="dabdc-158">詳細な結果ウィンドウは、以下に示すように表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![関連性トレーニングの詳細な結果](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="dabdc-160">タグ付けの概要</span><span class="sxs-lookup"><span data-stu-id="dabdc-160">Tagging summary</span></span>

 <span data-ttu-id="dabdc-161">次に示す例では、 **タグ** 付けサマリーには、Assessment、Training、Catch-up ファイルの各タグ付けプロセスの合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![関連性トラックのタグ付けの概要](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="dabdc-163">キーワード</span><span class="sxs-lookup"><span data-stu-id="dabdc-163">Keywords</span></span>

<span data-ttu-id="dabdc-164">キーワードとは、ファイルが関連するかどうかを示す重要なインジケーターとして Advanced eDiscovery によって識別されるファイル内の一意の文字列、単語、語句、または一連の単語です。</span><span class="sxs-lookup"><span data-stu-id="dabdc-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="dabdc-165">"含める" 列には、関連としてタグ付けされたファイル内のキーワードと重み、および "除外" 列には、関連ではないとしてタグ付けされたファイル内のキーワードと重みが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="dabdc-166">Advanced eDiscovery は、負または正のキーワードの重み値を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dabdc-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="dabdc-167">重み付けが大きいほど、バッチ計算時にキーワードが表示されるファイルに割り当てられる関連性スコアが高くなります。</span><span class="sxs-lookup"><span data-stu-id="dabdc-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="dabdc-168">キーワードの Advanced eDiscovery リストを使用すると、ファイル レビュー プロセスの任意の時点で、エキスパートによって作成されたリストを補完したり、間接的なサニティ チェックとして作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="dabdc-169">トレーニングの進捗状況</span><span class="sxs-lookup"><span data-stu-id="dabdc-169">Training progress</span></span>

<span data-ttu-id="dabdc-170">トレーニング **の進行状況ウィンドウ** には、以下の例に示すように、トレーニングの進行状況グラフと品質インジケーターの表示が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dabdc-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![関連性トラックのトレーニングの進捗状況](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="dabdc-172">**トレーニング品質インジケーター**: タグ付けの一貫性の評価を次のように表示します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="dabdc-173">**良** い: ファイルは一貫してタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="dabdc-174">(緑色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="dabdc-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="dabdc-175">**中**: 一部のファイルに一貫性のないタグが付けられた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dabdc-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="dabdc-176">(黄色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="dabdc-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="dabdc-177">**警告**: 多くのファイルに一貫性のないタグが付けられた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dabdc-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="dabdc-178">(赤色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="dabdc-178">(Red light displayed)</span></span>

<span data-ttu-id="dabdc-179">**トレーニングの進行状況グラフ**: F 測定値と比較した多くの関連性トレーニング サイクル後の関連性トレーニングの安定性の程度を示します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="dabdc-180">グラフを左から右に移動すると、信頼区間は絞り込み、F メジャーと共に Advanced eDiscovery Relevance によって使用され、関連性トレーニングの結果が最適化された場合の安定性を判断します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dabdc-181">関連性では F2 が使用されます。F 測定指標では、呼び出しの重み付けは精度の 2 倍です。</span><span class="sxs-lookup"><span data-stu-id="dabdc-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="dabdc-182">リッチ度が高い (25% を超える) 場合、関連性は F1 (1:1 の比率) を使用します。</span><span class="sxs-lookup"><span data-stu-id="dabdc-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="dabdc-183">F 測定値の比率は、[関連性の設定] の [詳細設定 **]** \> **で構成できます**。</span><span class="sxs-lookup"><span data-stu-id="dabdc-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="dabdc-184">バッチ計算の結果</span><span class="sxs-lookup"><span data-stu-id="dabdc-184">Batch calculation results</span></span>

<span data-ttu-id="dabdc-185">バッチ **計算の結果ウィンドウ** には、次のように関連性のスコアが付いたファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="dabdc-186">**Success**</span><span class="sxs-lookup"><span data-stu-id="dabdc-186">**Success**</span></span>
  
- <span data-ttu-id="dabdc-187">**空**: テキストを含めることはできません (スペース/タブのみなど)</span><span class="sxs-lookup"><span data-stu-id="dabdc-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="dabdc-188">**Failed**: Due to excessive size or could not be read</span><span class="sxs-lookup"><span data-stu-id="dabdc-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="dabdc-189">**無視**: サイズが大きすぎる</span><span class="sxs-lookup"><span data-stu-id="dabdc-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="dabdc-190">**Nebulous**: 意味のないテキストが含まれているか、問題に関連する機能が含まれている</span><span class="sxs-lookup"><span data-stu-id="dabdc-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="dabdc-191">空、失敗、無視、または Nebulous は、-1 の関連性スコアを受け取る。</span><span class="sxs-lookup"><span data-stu-id="dabdc-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="dabdc-192">トレーニング統計</span><span class="sxs-lookup"><span data-stu-id="dabdc-192">Training statistics</span></span>

<span data-ttu-id="dabdc-193">[ **トレーニング統計]** ウィンドウには、Advanced eDiscovery Relevance トレーニングの結果に基づいて統計情報とグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![関連性トラックのトレーニング統計情報](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="dabdc-195">このビューには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-195">This view shows the following:</span></span>
  
- <span data-ttu-id="dabdc-196">**レビューリコール率**: 仮定的に線形レビューの関連性スコアに従った結果の比較。</span><span class="sxs-lookup"><span data-stu-id="dabdc-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="dabdc-197">レビュー セットのサイズが設定されている場合、取り消しは推定されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="dabdc-198">**パラメーター**: ケース全体のファイルの母集団に関連するレビュー セットに関連する累積計算された統計情報。</span><span class="sxs-lookup"><span data-stu-id="dabdc-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="dabdc-199">**Review**: このカットオフに基づいて確認するファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="dabdc-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="dabdc-200">**取** り消し : レビュー セット内の関連ファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="dabdc-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="dabdc-201">**関連性スコアによる配布**: 左に濃い灰色の表示のファイルがカットオフ スコアより下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="dabdc-202">ツール ヒントには、ファイルの合計に関連する、レビュー ファイル セット内のファイルの関連性スコアと関連する割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dabdc-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
