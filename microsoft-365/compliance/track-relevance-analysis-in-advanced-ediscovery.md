---
title: Advanced eDiscovery での関連性分析の追跡
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Advanced eDiscovery でケースの問題に関する関連性トレーニングの状態と結果を表示および解釈する方法について説明します。
ms.openlocfilehash: 889153b2d6587daee4212ab8f2b5ccb941e848a4
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760345"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="bd7cc-103">Advanced eDiscovery (クラシック) での関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="bd7cc-103">Track Relevance analysis in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="bd7cc-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="bd7cc-106">Advanced eDiscovery の [関連度トラック] タブには、[タグ] タブで実行された関連性トレーニングの計算された有効性が表示され、関連性における反復的なトレーニング プロセスの次のステップが示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="bd7cc-107">関連性トレーニングの状態の追跡</span><span class="sxs-lookup"><span data-stu-id="bd7cc-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="bd7cc-108">以下の [問題名] ダイアログの次の例に示すように、ケースの問題の関連トラックで次の詳細 **を** 表示します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="bd7cc-109">**Assessment**: この進行状況インジケーターは、この時点で実行された関連性トレーニングがエラーの余白の観点から評価目標を達成した度合いを示します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="bd7cc-110">関連性トレーニングの結果の豊富さも表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="bd7cc-111">**トレーニング**: この色分けされた進行状況インジケーターとツール ヒント表示は、関連性トレーニング結果の安定性と、各問題にタグ付けされた関連性トレーニング サンプルの数を示す数値スケールを示します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="bd7cc-112">専門家は、反復的な関連性トレーニング プロセスの進行状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="bd7cc-113">**バッチ計算**: この進行状況インジケーターは、バッチ計算の完了に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="bd7cc-114">**次の手順**: 実行する次の手順の推奨事項を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="bd7cc-115">この例では、問題に対して正常に完了した Assessment が表示され、完了した色の進行状況インジケーターとチェックマークで示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="bd7cc-116">タグ付けは進行中ですが、ケースは不安定と見なされます (安定性の状態もツール ヒントに表示されます)。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="bd7cc-117">次の手順の推奨事項は「トレーニング」です。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-117">The next step recommendation is "Training".</span></span> 
    
    ![関連性トラックのトレーニングのステップ 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="bd7cc-119">展開されたビューには、追加情報とオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="bd7cc-120">表示される現在のエラー余白は、既存の (既にタグが付けられた) 評価ファイルを基に、現在の評価の状態における取り消しのエラー余白です。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="bd7cc-121">Assessment ステージは、問題ごとに Assessmentチェック ボックスをオフにし、次に "すべての問題" に対してオフにすることでバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="bd7cc-122">ただし、その結果、この問題に関する統計情報はありません。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="bd7cc-123">>チェック **ボックスを** オフにできるのは、評価が実行される前のみです。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="bd7cc-124">1 つのケースに複数の問題が存在する場合、問題ごとにチェック ボックスがオフの場合にのみ評価がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="bd7cc-125">ファイルの最初のサンプル セットで評価が完了しない場合、より多くのファイルにタグ付けする次の手順が評価になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="bd7cc-126">関連性 **トラック** \> **では、** トレーニングの進行状況インジケーターとツール ヒントは、安定性に到達するために必要な追加サンプルの推定数を示します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="bd7cc-127">この見積もりは、必要な追加のトレーニングのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![関連性トラックのトレーニング](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="bd7cc-129">タグ付けが完了し、トレーニングを継続する必要がある場合は、[トレーニング] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="bd7cc-130">追加のトレーニングのために、読み込まれたファイル セットからファイルの別のサンプル セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="bd7cc-131">その後、[タグ] タブに戻り、タグを付け、さらに多くのファイルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="bd7cc-132">安定したトレーニング レベルに達する</span><span class="sxs-lookup"><span data-stu-id="bd7cc-132">Reaching stable training levels</span></span>

<span data-ttu-id="bd7cc-133">評価ファイルが安定したレベルのトレーニングを完了すると、Advanced eDiscovery はバッチ計算の準備が整います。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd7cc-134">通常、3 つの安定したトレーニング サンプルの後、次の手順は 「バッチ計算」です。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="bd7cc-135">たとえば、以前のサンプルからファイルのタグ付けに変更が加えらた場合や、シード ファイルが追加された場合など、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="bd7cc-136">バッチ計算の実行</span><span class="sxs-lookup"><span data-stu-id="bd7cc-136">Performing Batch calculation</span></span>

<span data-ttu-id="bd7cc-137">バッチ計算は、トレーニングが正常に完了した後の次の手順として実行されます (進行状況バーに安定したトレーニング状態が表示されると、ツール ヒントにチェックマークと安定した状態が表示されます)。バッチ計算は、ファイルの関連性を評価し、関連性スコアを割り当てるには、関連度トレーニング中に取得した知識をファイルの母集団全体に適用します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="bd7cc-138">複数の問題がある場合は、問題ごとにバッチ計算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="bd7cc-139">バッチの計算中に、すべてのファイルの処理中に進行状況が監視されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="bd7cc-140">ここで推奨される次の手順は "None" で、この時点で追加の反復的な関連性トレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="bd7cc-141">次のフェーズは、[関連性 **の決定] \> タブ** です。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="bd7cc-142">バッチ計算後に新しいファイルをインポートする場合、管理者はインポートしたファイルを新しい負荷に追加できます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd7cc-143">バッチ計算中に **[キャンセル** ] をクリックすると、既に実行された処理が保存されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="bd7cc-144">バッチ計算を再度実行すると、最後に実行された時点から処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="bd7cc-145">タグ付けの一貫性の評価</span><span class="sxs-lookup"><span data-stu-id="bd7cc-145">Assessing tagging consistency</span></span>

<span data-ttu-id="bd7cc-146">ファイルのタグ付けに不整合がある場合は、分析に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="bd7cc-147">Advanced eDiscovery タグ付けの一貫性プロセスは、結果が最適ではない場合や一貫性が疑わしい場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="bd7cc-148">一貫性のないタグが付けられた可能性があるファイルの一覧が返され、必要に応じて確認して再タグ付けできます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd7cc-149">評価に続く 7 回以上のトレーニング ラウンドの後、タグ付けの一貫性は、関連性トラックの問題の詳細な結果のトレーニングの進行状況に \>  \>  \>  \> **表示できます**。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="bd7cc-150">このレビューは、一度に 1 つの問題に対して行われます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="bd7cc-151">関連性 **トラックで \> 、** 問題の行を展開します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="bd7cc-152">次の手順の右側 **にある [変更]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="bd7cc-153">7 **つのトレーニング サンプルの\*\*\*\*後、[次** の手順] オプションとして [タグの不整合] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="bd7cc-154">[タグ **の不整合] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="bd7cc-155">[ **タグ]** タブが開き、必要に応じて再タグ付けする不整合の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="bd7cc-156">[計算 **] を** クリックして変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="bd7cc-157">タグ付けの不整合の後の次の手順は、"トレーニング" です。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="bd7cc-158">関連性の結果の表示と使用</span><span class="sxs-lookup"><span data-stu-id="bd7cc-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="bd7cc-159">[関連性 **トラック] \> タブ** で、問題の行を展開し、[詳細な結果] の横にある **[表示**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="bd7cc-160">詳細な結果ウィンドウは、以下に示すように表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![関連性トレーニングの詳細な結果](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="bd7cc-162">タグ付けの概要</span><span class="sxs-lookup"><span data-stu-id="bd7cc-162">Tagging summary</span></span>

 <span data-ttu-id="bd7cc-163">次に示す例では、 **タグ** 付けサマリーには、Assessment、Training、Catch-up ファイルの各タグ付けプロセスの合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![関連性トラックのタグ付けの概要](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="bd7cc-165">キーワード</span><span class="sxs-lookup"><span data-stu-id="bd7cc-165">Keywords</span></span>

<span data-ttu-id="bd7cc-166">キーワードとは、ファイルが関連するかどうかを示す重要なインジケーターとして Advanced eDiscovery によって識別されるファイル内の一意の文字列、単語、語句、または一連の単語です。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="bd7cc-167">"含める" 列には、関連としてタグ付けされたファイル内のキーワードと重み、および "除外" 列には、関連しないとしてタグ付けされたファイル内のキーワードと重みが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="bd7cc-168">Advanced eDiscovery は、負または正のキーワードの重み値を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="bd7cc-169">重み付けが高いほど、バッチ計算時にキーワードが表示されるファイルに割り当てられる関連性スコアが高くなります。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="bd7cc-170">Advanced eDiscovery のキーワードの一覧を使用すると、ファイル レビュー プロセスの任意の時点で、エキスパートによって作成されたリストや間接的なサニティ チェックとして作成されたリストを補完できます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="bd7cc-171">トレーニングの進捗状況</span><span class="sxs-lookup"><span data-stu-id="bd7cc-171">Training progress</span></span>

<span data-ttu-id="bd7cc-172">トレーニング **の進行状況ウィンドウ** には、以下の例に示すように、トレーニングの進行状況グラフと品質インジケーターの表示が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![関連性トラックのトレーニングの進捗状況](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="bd7cc-174">**トレーニング品質インジケーター**: タグ付けの一貫性の評価を次のように表示します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="bd7cc-175">**良** い: ファイルは一貫してタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="bd7cc-176">(緑色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="bd7cc-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="bd7cc-177">**中**: 一部のファイルに一貫性のないタグが付けられた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="bd7cc-178">(黄色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="bd7cc-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="bd7cc-179">**警告**: 多くのファイルに一貫性のないタグが付けられた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="bd7cc-180">(赤色のライトが表示されます)</span><span class="sxs-lookup"><span data-stu-id="bd7cc-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="bd7cc-181">**トレーニングの進行状況グラフ**: F 測定値と比較して、関連性トレーニング サイクルの数が経過した後の関連性トレーニングの安定性の程度を示します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="bd7cc-182">グラフを左から右に移動すると、信頼区間は絞り込み、F メジャーと共に Advanced eDiscovery Relevance によって使用され、関連性トレーニングの結果が最適化された場合の安定性を判断します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd7cc-183">関連性では F2 が使用されます。F 測定指標では、呼び出しの重み付けは精度の 2 倍です。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="bd7cc-184">リッチ度が高い (25% を超える) 場合、関連性は F1 (1:1 の比率) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="bd7cc-185">F 測定値の比率は、[関連性の設定] の [詳細設定 **]** \> **で構成できます**。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="bd7cc-186">バッチ計算の結果</span><span class="sxs-lookup"><span data-stu-id="bd7cc-186">Batch calculation results</span></span>

<span data-ttu-id="bd7cc-187">[ **バッチ計算の結果]** ウィンドウには、次のように、関連性のスコアが付いたファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="bd7cc-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="bd7cc-188">**Success**</span></span>
    
- <span data-ttu-id="bd7cc-189">**空**: テキストを含めることはできません (スペース/タブのみなど)</span><span class="sxs-lookup"><span data-stu-id="bd7cc-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="bd7cc-190">**Failed**: Due to excessive size or could not be read</span><span class="sxs-lookup"><span data-stu-id="bd7cc-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="bd7cc-191">**無視**: サイズが大きすぎる</span><span class="sxs-lookup"><span data-stu-id="bd7cc-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="bd7cc-192">**Nebulous**: 意味のないテキストが含まれているか、問題に関連する機能が含まれている</span><span class="sxs-lookup"><span data-stu-id="bd7cc-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="bd7cc-193">空、失敗、無視、または Nebulous は、-1 の関連性スコアを受け取る。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="bd7cc-194">トレーニング統計</span><span class="sxs-lookup"><span data-stu-id="bd7cc-194">Training statistics</span></span>

<span data-ttu-id="bd7cc-195">[ **トレーニング統計]** ウィンドウには、Advanced eDiscovery Relevance トレーニングの結果に基づいて統計情報とグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![関連性トラックのトレーニング統計情報](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="bd7cc-197">このビューには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-197">This view shows the following:</span></span>
  
- <span data-ttu-id="bd7cc-198">**レビューリコール率**: 仮定的に線形レビューの関連性スコアに従った結果の比較。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="bd7cc-199">レビュー セットのサイズが設定されている場合、取り消しは推定されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="bd7cc-200">**パラメーター**: ケース全体のファイルの母集団に関連するレビュー セットに関連する累積計算された統計情報。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="bd7cc-201">**Review**: このカットオフに基づいて確認するファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="bd7cc-202">**取** り消し : レビュー セット内の関連ファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="bd7cc-203">**関連性スコアによる配布**: 左に濃い灰色の表示のファイルは、カットオフ スコアの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="bd7cc-204">ツール ヒントには、ファイルの合計に関連する、レビュー ファイル セット内のファイルの関連性スコアと関連する割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7cc-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
