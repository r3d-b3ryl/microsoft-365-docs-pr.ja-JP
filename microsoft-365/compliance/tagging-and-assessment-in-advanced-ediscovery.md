---
title: 高度な電子情報開示でのタグ付けと評価
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: ファイルのタグ付け、高度な電子情報開示での評価結果の確認など、評価トレーニングを実行する手順を確認します。
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769192"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="ea051-103">高度な電子情報開示の関連性モジュールでのタグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="ea051-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="ea051-104">このセクションでは、高度な電子情報開示の関連性モジュールの Assessment の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea051-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="ea051-105">評価のトレーニングと分析の実行</span><span class="sxs-lookup"><span data-stu-id="ea051-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="ea051-106">[関連性の **追跡] タブ \> で** 、[評価] **をクリックして** ケース評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="ea051-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="ea051-107">この手順の例では、500 ファイルのサンプル評価セットが作成され、[タグ]タブが表示されます。これには、[タグ] パネル、表示されるファイルコンテンツ、その他のタグ付けオプションが含まれる。</span><span class="sxs-lookup"><span data-stu-id="ea051-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![評価ための [関連性タグ] タブ](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="ea051-109">サンプル内の各ファイルを確認し、各ケースの問題に対するファイルの関連性を判断し、[タグ付け] パネル ウィンドウの [関連性 ] (R)、関連しない (NR) ボタン、および [スキップ] ボタンを使用してファイルにタグを付けることができます。 </span><span class="sxs-lookup"><span data-stu-id="ea051-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="ea051-110">評価には、500 のタグ付きファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea051-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="ea051-111">ファイルが "スキップ" の場合は、タグ付けするファイルが多く表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="ea051-112">サンプル内のすべてのファイルにタグ付けした後、[計算] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ea051-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="ea051-113">評価の現在のエラーマージンとリッチネスは、以下に示すように、問題ごとに詳細を拡張して、[関連性トラック] タブに計算され表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="ea051-114">このダイアログの詳細については、「評価結果の確認 [」セクションで説明](#reviewing-assessment-results) します。</span><span class="sxs-lookup"><span data-stu-id="ea051-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![関連性トラック - 評価](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="ea051-116">既定では、問題の評価進捗インジケーターが完了したら、既定の [次へ] に進み、評価サンプルがレビューされ、関連するファイルに十分なタグが付けられたことを示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea051-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="ea051-117">>それ以外の場合は、[トラック] タブの結果を表示し、エラーの余白と次の手順を制御する場合は、[次のステップ]の横にある [変更] をクリックし、[評価の続行] を選択し **、[OK]** をクリックします。  </span><span class="sxs-lookup"><span data-stu-id="ea051-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="ea051-118">[ **評価]** チェック ボックスの右側にある [ **変更** ] をクリックして、問題ごとの評価パラメーターを表示および指定します。</span><span class="sxs-lookup"><span data-stu-id="ea051-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="ea051-119">次 **の例に** 示すように、各問題の評価レベル ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![評価レベルのケースの問題](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="ea051-121">問題の次のパラメーターが計算され、[評価レベル] ダイアログ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="ea051-122">**リコールの推定値の目標** 誤差幅 : この値に基づいて、確認に必要な追加ファイルの推定数が計算されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="ea051-123">リコールに使用されるマージンは 75% を超え、信頼度は 95% です。</span><span class="sxs-lookup"><span data-stu-id="ea051-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="ea051-124">**必要な追加の評価ファイル**: 現在のエラー マージンの要件が満たされていない場合に必要なファイルの数を示します。</span><span class="sxs-lookup"><span data-stu-id="ea051-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="ea051-125">現在のエラーマージンを調整し、異なる誤差マージンの影響を確認するには (問題ごとに):</span><span class="sxs-lookup"><span data-stu-id="ea051-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="ea051-126">[問題 **の選択] ボックスの** 一覧で、問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea051-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="ea051-127">[ **呼び出しの推定値の目標誤差幅]** に、新しい値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea051-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="ea051-128">[ **値の更新] を** クリックして、調整の影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="ea051-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="ea051-129">[ **評価レベル]** ダイアログの **[詳細設定] をクリック** して、次の追加のパラメーターと詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="ea051-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![[評価レベルのケースの問題] 詳細ビュー](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="ea051-131">**推定リッチ度**: 現在の評価結果に従って推定されるリッチネス</span><span class="sxs-lookup"><span data-stu-id="ea051-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="ea051-132">**想定されるリコール** の場合: 既定では、目標誤差余白は 75% を超すリコールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="ea051-133">この **パラメーターを** 変更し、別の範囲のリコール値の誤差幅を制御する場合は、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea051-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="ea051-134">**信頼度**: 既定では、信頼度の推奨誤差幅は 95% です。</span><span class="sxs-lookup"><span data-stu-id="ea051-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="ea051-135">このパラメーター **を変更** する場合は、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea051-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="ea051-136">**予想されるリッチエラーマージン**: 更新された値を考えると、追加の評価ファイルすべてがレビューされた後、これはリッチネスの予想誤差幅です。</span><span class="sxs-lookup"><span data-stu-id="ea051-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="ea051-137">**必要な追加の評価** ファイル: 更新された値を指定すると、ターゲットに到達するために確認する必要がある追加の評価ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="ea051-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="ea051-138">**必要な評価ファイルの合計**: 更新された値を指定すると、レビューに必要な評価ファイルの合計。</span><span class="sxs-lookup"><span data-stu-id="ea051-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="ea051-139">**評価の関連ファイル** の予想数 : 更新された値を指定すると、すべての追加の評価ファイルが確認された後の評価全体の関連ファイルの予想数。</span><span class="sxs-lookup"><span data-stu-id="ea051-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="ea051-140">パラメーター **が変更された場合は、[値の** 再計算] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea051-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="ea051-141">完了したら、1 つの問題がある場合は **、[OK]** をクリックして変更を保存します (確認または変更する複数の問題がある場合は [次へ] をクリックし、[完了] を **クリックします**)。</span><span class="sxs-lookup"><span data-stu-id="ea051-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="ea051-142">複数の問題がある場合、すべての問題が確認または調整された後、次の例に示すように、評価レベル **:** 概要ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![評価レベルの概要](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="ea051-144">評価が正常に完了したら、関連性トレーニングの次の段階に進みます。</span><span class="sxs-lookup"><span data-stu-id="ea051-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="ea051-145">評価結果の確認</span><span class="sxs-lookup"><span data-stu-id="ea051-145">Reviewing assessment results</span></span>

<span data-ttu-id="ea051-146">評価サンプルがタグ付けされた後、評価結果が計算され、[関連性の追跡] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="ea051-147">次の結果が展開されたトラック表示に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="ea051-148">リコール見積もりの評価現在の誤差率</span><span class="sxs-lookup"><span data-stu-id="ea051-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="ea051-149">推定豊富さ</span><span class="sxs-lookup"><span data-stu-id="ea051-149">Estimated richness</span></span>

- <span data-ttu-id="ea051-150">必要な追加の評価ファイル (レビュー用)</span><span class="sxs-lookup"><span data-stu-id="ea051-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="ea051-151">現在のエラーマージンの評価は、Advanced eDiscovery によって推奨されるエラー マージンです。</span><span class="sxs-lookup"><span data-stu-id="ea051-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="ea051-152">"必要な追加の評価ファイル" に表示される番号は、その推奨事項に対応します。</span><span class="sxs-lookup"><span data-stu-id="ea051-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="ea051-153">[評価の進行状況] インジケーターは、現在のエラーマージンを考えると、評価の完了レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="ea051-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="ea051-154">評価が進行中の場合、ユーザーは別の評価サンプルにタグを付けします。</span><span class="sxs-lookup"><span data-stu-id="ea051-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="ea051-155">評価の進行状況インジケーターに評価が完了として表示された場合、評価サンプルのレビューが完了し、十分な関連ファイルがタグ付けされたという意味です。</span><span class="sxs-lookup"><span data-stu-id="ea051-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="ea051-156">展開された [トラック] 画面には、推奨される次の手順、評価の統計、および詳細な結果へのアクセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea051-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="ea051-157">リッチ度が非常に低い場合、有用な統計を生成するために関連するファイルの数を最小限に抑えるのに必要な追加の評価ファイルの数は非常に多いです。</span><span class="sxs-lookup"><span data-stu-id="ea051-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="ea051-158">高度な電子情報開示では、トレーニングへの移行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea051-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="ea051-159">評価の進行状況インジケーターは網掛けされ、統計情報は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ea051-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="ea051-160">統計的に基づく安定化がない場合、精度と信頼度のレベルが低い結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ea051-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="ea051-161">ただし、これらの結果は、見つかった関連ファイルの割合を知る必要がない場合に、関連するファイルを検索するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea051-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="ea051-162">同様に、この状態を使用して、関連性スコアが特定の問題に関連するファイルへのアクセスを加速する可能性がある、リッチ度の低い問題をトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="ea051-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="ea051-163">[関連性 **の追跡] \> タブ** の [展開された問題] 表示で、次の表示オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea051-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="ea051-164">[次の手順 **:** タグ付け] などの推奨される次の手順は、右側の [変更] ボタンをクリックし、[次へ] で別の手順を選択することで回避できます (問題 **ごとに)。**</span><span class="sxs-lookup"><span data-stu-id="ea051-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="ea051-165">評価の進行状況インジケーターが完了していない場合、評価は、より多くの評価ファイルにタグを付け、統計の精度を高める次の推奨オプションになります。</span><span class="sxs-lookup"><span data-stu-id="ea051-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="ea051-166">[変更] をクリックし、[評価レベル] ダイアログで [リコールの推定値のターゲット 誤差余白] を変更し、[値の更新] をクリックすることで、エラーマージンを変更して影響 **を評価できます**。 </span><span class="sxs-lookup"><span data-stu-id="ea051-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="ea051-167">また、このダイアログでは、[詳細設定] をクリックして、高度なオプションを **表示できます**。</span><span class="sxs-lookup"><span data-stu-id="ea051-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="ea051-168">[表示] をクリックすると、追加の評価レベルの統計情報とその影響を **表示できます**。</span><span class="sxs-lookup"><span data-stu-id="ea051-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="ea051-169">表示される [詳細結果] ダイアログで、500 以上のタグ付き評価ファイルが含まれますが、少なくとも 18 のファイルが問題に関連するタグ付けされている場合、問題ごとに統計情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea051-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
