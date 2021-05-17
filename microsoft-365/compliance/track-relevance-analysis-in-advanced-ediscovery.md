---
title: 高度な電子情報開示での関連性分析の追跡
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
description: 高度な電子情報開示のケースの問題に関する関連性トレーニングの状態と結果を表示および解釈する方法について説明します。
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769182"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="1e81c-103">高度な電子情報開示での関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="1e81c-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="1e81c-104">Advanced eDiscovery では、[関連性の追跡] タブには、[タグ] タブで実行される関連性トレーニングの計算された有効性が表示され、関連性の反復トレーニング プロセスで実行する次の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="1e81c-105">関連性トレーニングの状態の追跡</span><span class="sxs-lookup"><span data-stu-id="1e81c-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="1e81c-106">以下の問題名ダイアログの次の例に示すように、ケースの問題に関する関連性トラックで次の **詳細を** 表示します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="1e81c-107">**評価**: この進行状況インジケーターは、この時点で行われた関連性トレーニングが誤差のマージンの観点から評価目標を達成した度合いを示します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="1e81c-108">関連性トレーニングの結果の豊富さも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="1e81c-109">**トレーニング**: この色分けされた進行状況インジケーターとツール ヒントは、関連性トレーニング結果の安定性と、各問題にタグ付けされた関連性トレーニング サンプルの数を示す数値スケールを示します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="1e81c-110">専門家は、反復的な関連性トレーニング プロセスの進捗状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="1e81c-111">**バッチ計算**: この進行状況インジケーターは、バッチ計算の完了に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="1e81c-112">**次の手順**: 実行する次の手順の推奨事項を表示します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="1e81c-113">この例では、正常に完了した問題の評価が、完了した色の進行状況インジケーターとチェックマークで示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="1e81c-114">タグ付けは進行中ですが、ケースは依然として不安定と見なされます (ツール ヒントにも安定性の状態が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="1e81c-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="1e81c-115">次の手順の推奨事項は「トレーニング」です。</span><span class="sxs-lookup"><span data-stu-id="1e81c-115">The next step recommendation is "Training".</span></span> 
  
    ![関連性トラックのトレーニングのステップ 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="1e81c-117">展開されたビューには、追加情報とオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="1e81c-118">表示される現在のエラーマージンは、既存の (既にタグ付けされている) 評価ファイルを考えると、評価の現在の状態でのリコールの誤差マージンです。</span><span class="sxs-lookup"><span data-stu-id="1e81c-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="1e81c-119">評価ステージは、問題ごとに [評価]チェック ボックスをオフにし、[すべての問題] をクリアすることで回避できます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="1e81c-120">ただし、その結果、この問題に関する統計情報はありません。</span><span class="sxs-lookup"><span data-stu-id="1e81c-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="1e81c-121">>チェック ボックス **をオフ** にできるのは、評価が実行される前のみです。</span><span class="sxs-lookup"><span data-stu-id="1e81c-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="1e81c-122">ケースに複数の問題が存在する場合、各問題のチェック ボックスがオフの場合にのみ評価がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="1e81c-123">ファイルの最初のサンプル セットで評価が完了しない場合、評価は、より多くのファイルにタグ付けする次の手順になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e81c-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="1e81c-124">関連性 **トラック** \> **では、** トレーニング進行状況インジケーターとツール ヒントは、安定性に達するために必要な追加サンプルの推定数を示します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="1e81c-125">この見積もりは、必要な追加のトレーニングのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![関連性トラックのトレーニング](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="1e81c-127">タグ付けが完了したら、トレーニングを続行する必要がある場合は、[トレーニング] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e81c-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="1e81c-128">追加のトレーニングのために、読み込まれたファイル セットからファイルの別のサンプル セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="1e81c-129">その後、[タグ] タブに戻り、さらに多くのファイルにタグを付け、トレーニングします。</span><span class="sxs-lookup"><span data-stu-id="1e81c-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="1e81c-130">安定したトレーニング レベルに達する</span><span class="sxs-lookup"><span data-stu-id="1e81c-130">Reaching stable training levels</span></span>

<span data-ttu-id="1e81c-131">評価ファイルが安定したレベルのトレーニングを達成した後、高度な電子情報開示はバッチ計算の準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="1e81c-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e81c-132">通常、3 つの安定したトレーニング サンプルの後、次の手順は "バッチ計算" です。</span><span class="sxs-lookup"><span data-stu-id="1e81c-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="1e81c-133">たとえば、以前のサンプルからのファイルのタグ付けに変更が加えられた場合や、シード ファイルが追加された場合など、例外が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e81c-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="1e81c-134">バッチ計算の実行</span><span class="sxs-lookup"><span data-stu-id="1e81c-134">Performing Batch calculation</span></span>

<span data-ttu-id="1e81c-135">バッチ計算は、トレーニングが正常に完了した後の次の手順として実行されます (進行状況バーに安定したトレーニング状態が表示されると、ツール ヒントにチェックマークと安定した状態が表示されます)。バッチ計算は、ファイルの関連性を評価し、関連性スコアを割り当てるには、関連性トレーニング中に取得した知識をファイルの母集団全体に適用します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="1e81c-136">複数の問題がある場合は、問題ごとにバッチ計算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="1e81c-137">バッチ計算中、すべてのファイルの処理中に進行状況が監視されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="1e81c-138">ここでは、推奨される次の手順は "None" であり、この時点で追加の反復的な関連性トレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1e81c-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="1e81c-139">次のフェーズは、[ **関連性の決定] \> タブ** です。</span><span class="sxs-lookup"><span data-stu-id="1e81c-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="1e81c-140">バッチ計算後に新しいファイルをインポートする場合、管理者はインポートしたファイルを新しい読み込み量に追加できます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e81c-141">バッチ計算中に **[キャンセル]** をクリックすると、既に実行された処理が保存されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="1e81c-142">バッチ計算を再度実行すると、最後に実行されたポイントから処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="1e81c-143">タグ付けの一貫性の評価</span><span class="sxs-lookup"><span data-stu-id="1e81c-143">Assessing tagging consistency</span></span>

<span data-ttu-id="1e81c-144">ファイルのタグ付けに不整合がある場合は、分析に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e81c-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="1e81c-145">高度な電子情報開示タグ付けの一貫性プロセスは、結果が最適ではない場合や一貫性が疑わしい場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="1e81c-146">タグが一貫性のない可能性があるファイルの一覧が返され、必要に応じて確認および再タグ付けできます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e81c-147">評価後の 7 つ以上のトレーニング ラウンドの後、タグ付けの一貫性は、[関連性トラックの問題] [詳細な結果] \>  \>  \> **トレーニングの** 進行状況 \> **で確認できます**。</span><span class="sxs-lookup"><span data-stu-id="1e81c-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="1e81c-148">このレビューは、一度に 1 つの問題に対して行われます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="1e81c-149">[ **関連性の \> 追跡]** で、問題の行を展開します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="1e81c-150">[次へ] ステップの右側 **にある [変更**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e81c-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="1e81c-151">7 **つのトレーニング サンプルの後** の [ **次** のステップ] オプションとして [タグの不整合] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e81c-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="1e81c-152">[タグ **の不整合] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1e81c-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="1e81c-153">[ **タグ]** タブが開き、必要に応じて再タグ付けする不整合の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="1e81c-154">[計算 **] を** クリックして変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="1e81c-155">タグの不整合の後の次の手順は"Training" です。</span><span class="sxs-lookup"><span data-stu-id="1e81c-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="1e81c-156">関連性の結果の表示と使用</span><span class="sxs-lookup"><span data-stu-id="1e81c-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="1e81c-157">[関連性 **の追跡] \> タブ** で、問題の行を展開し、[詳細な結果] の横にある **[表示**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e81c-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="1e81c-158">[詳細な結果] ウィンドウは、以下に示すように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![関連性トレーニングの詳細な結果](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="1e81c-160">タグ付けの概要</span><span class="sxs-lookup"><span data-stu-id="1e81c-160">Tagging summary</span></span>

 <span data-ttu-id="1e81c-161">以下に示す例では、タグ付けサマリーには、評価、トレーニング、キャッチアップ ファイルの各タグ付けプロセスの合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![関連性トラックのタグ付けの概要](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="1e81c-163">キーワード</span><span class="sxs-lookup"><span data-stu-id="1e81c-163">Keywords</span></span>

<span data-ttu-id="1e81c-164">キーワードは、ファイルが関連するかどうかを示す重要な指標として、Advanced eDiscovery によって識別されるファイル内の一意の文字列、単語、語句、または一連の単語です。</span><span class="sxs-lookup"><span data-stu-id="1e81c-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="1e81c-165">"Include" columns list keyword and weights in files the relevant, and the "Exclude" columns lists keywords and the exclude" columns lists keywords and weights in files tagged in not relevant.</span><span class="sxs-lookup"><span data-stu-id="1e81c-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="1e81c-166">高度な電子情報開示では、負または正のキーワードの重み値が割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="1e81c-167">重み付けが大きいほど、バッチ計算時にキーワードが表示されるファイルに高い関連性スコアが割り当てられる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1e81c-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="1e81c-168">キーワードの高度な電子情報開示リストを使用して、専門家によって作成されたリストを補完したり、ファイル レビュー プロセスの任意の時点で間接的なサニティ チェックとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="1e81c-169">トレーニングの進捗状況</span><span class="sxs-lookup"><span data-stu-id="1e81c-169">Training progress</span></span>

<span data-ttu-id="1e81c-170">[ **トレーニングの進行状況]** ウィンドウには、以下の例に示すように、トレーニング進行状況グラフと品質インジケーターの表示が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![関連性トラックのトレーニングの進捗状況](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="1e81c-172">**トレーニング品質インジケーター**: タグ付けの一貫性の評価を次のように表示します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="1e81c-173">**良い**: ファイルは一貫してタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="1e81c-174">(緑色の光が表示されます)</span><span class="sxs-lookup"><span data-stu-id="1e81c-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="1e81c-175">**中**: 一部のファイルに一貫性のないタグが付く場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e81c-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="1e81c-176">(黄色の光が表示されます)</span><span class="sxs-lookup"><span data-stu-id="1e81c-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="1e81c-177">**警告**: 多くのファイルに一貫性のないタグが付く場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e81c-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="1e81c-178">(赤色の光が表示されます)</span><span class="sxs-lookup"><span data-stu-id="1e81c-178">(Red light displayed)</span></span>

<span data-ttu-id="1e81c-179">**トレーニングの進行状況グラフ**: 多くの関連性トレーニング サイクル後の関連性トレーニングの安定性の度合いを、F-measure 値と比較して示します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="1e81c-180">グラフを左から右に移動すると、信頼区間が狭く、高度な電子情報開示の関連性によって F メジャーと共に使用され、関連性トレーニングの結果が最適化される安定性を判断します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e81c-181">関連性は F2 を使用し、呼び出しは精度の 2 倍の重みを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1e81c-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="1e81c-182">リッチ度が高い (25% を超える) 場合、関連性は F1 (1:1 比率) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e81c-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="1e81c-183">F-measure 比率は、[関連性の設定] [ **詳細設定]** \> **で構成できます**。</span><span class="sxs-lookup"><span data-stu-id="1e81c-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="1e81c-184">バッチ計算の結果</span><span class="sxs-lookup"><span data-stu-id="1e81c-184">Batch calculation results</span></span>

<span data-ttu-id="1e81c-185">[ **バッチ計算結果] ウィンドウ** には、関連性のスコアが付いたファイルの数が次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="1e81c-186">**Success**</span><span class="sxs-lookup"><span data-stu-id="1e81c-186">**Success**</span></span>
  
- <span data-ttu-id="1e81c-187">**Empty**: テキストを含めない (スペース/タブのみなど)</span><span class="sxs-lookup"><span data-stu-id="1e81c-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="1e81c-188">**失敗 :** サイズが大きすぎるか読み取れなかのため</span><span class="sxs-lookup"><span data-stu-id="1e81c-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="1e81c-189">**無視**: サイズが大きすぎる場合</span><span class="sxs-lookup"><span data-stu-id="1e81c-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="1e81c-190">**Nebulous**: 無意味なテキストが含まれているか、問題に関連する機能が含まれている</span><span class="sxs-lookup"><span data-stu-id="1e81c-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e81c-191">空、失敗、無視、または Nebulous は、関連性スコア -1 を受け取る。</span><span class="sxs-lookup"><span data-stu-id="1e81c-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="1e81c-192">トレーニング統計</span><span class="sxs-lookup"><span data-stu-id="1e81c-192">Training statistics</span></span>

<span data-ttu-id="1e81c-193">[ **トレーニング統計] ウィンドウ** には、高度な電子情報開示関連性トレーニングの結果に基づいて統計とグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![関連性トラックのトレーニング統計情報](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="1e81c-195">このビューには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-195">This view shows the following:</span></span>
  
- <span data-ttu-id="1e81c-196">**レビューリコール比**: 仮定的に線形レビューの関連性スコアに従った結果の比較。</span><span class="sxs-lookup"><span data-stu-id="1e81c-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="1e81c-197">レビュー セットのサイズ セットを考えると、呼び出しは推定されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="1e81c-198">**パラメーター**: ケース全体のファイルの母集団に関連するレビュー セットに関連する累積計算された統計情報。</span><span class="sxs-lookup"><span data-stu-id="1e81c-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="1e81c-199">**レビュー**: このカットオフに基づいて確認するファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="1e81c-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="1e81c-200">**呼び** 出し : レビュー セット内の関連するファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="1e81c-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="1e81c-201">**関連性スコアによる配布**: 左の濃い灰色の表示のファイルは、カットオフ スコアの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="1e81c-202">ツール ヒントには、関連性スコアと、ファイルの合計に関連するレビュー ファイル セット内のファイルの関連割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e81c-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
