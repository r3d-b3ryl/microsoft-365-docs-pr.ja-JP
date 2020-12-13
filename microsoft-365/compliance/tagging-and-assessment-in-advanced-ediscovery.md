---
title: Advanced eDiscovery でのタグ付けと評価
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: ファイルのタグ付け、Advanced eDiscovery での評価結果の確認など、Assessment トレーニングを実行する手順を確認します。
ms.openlocfilehash: c8c6f82e7cfb3e2eddcc482039582ea27a702494
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663462"
---
# <a name="tagging-and-assessment-in-advanced-ediscovery-classic"></a><span data-ttu-id="ea377-103">Advanced eDiscovery のタグ付けと評価 (クラシック)</span><span class="sxs-lookup"><span data-stu-id="ea377-103">Tagging and Assessment in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="ea377-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="ea377-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ea377-106">このセクションでは、Advanced eDiscovery Relevance Assessment モジュールの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea377-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="ea377-107">Assessment のトレーニングと分析の実行</span><span class="sxs-lookup"><span data-stu-id="ea377-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="ea377-108">[関連性 **トラック] タブ \> で** 、[Assessment] **をクリック** してケース評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="ea377-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="ea377-109">この手順の例では、500 ファイルのサンプル評価セットが作成され、[タグ]タブが表示されます。このタブには、タグ パネル、表示されたファイルコンテンツ、その他のタグ付けオプションが含まれるものがあります。</span><span class="sxs-lookup"><span data-stu-id="ea377-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![評価ための [関連性タグ] タブ](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="ea377-111">サンプル内の各ファイルを確認し、各ケースの問題に対するファイルの関連性を決定し、[タグ付け] パネル ウィンドウの [関連 (R)、Not  relevant (NR)、Skip] ボタンを使用してファイルにタグを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea377-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="ea377-112">評価には、500 のタグ付きファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea377-112">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="ea377-113">ファイルが "スキップ" された場合は、タグ付けするファイルが多く表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-113">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="ea377-114">サンプル内のすべてのファイルにタグ付けした後、[計算] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ea377-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="ea377-115">Assessment の現在のエラーの余白と豊富さが計算され、[関連トラック] タブに表示されます。次に示すように、問題ごとに詳細が展開されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-115">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="ea377-116">このダイアログの詳細については、後の「Assessment の結果の確認」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="ea377-116">More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![関連性トラック - 評価](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="ea377-118">既定では、問題の Assessment 進行状況インジケーターが完了したら、既定の次の手順に進み、評価サンプルがレビューされ、十分な関連ファイルにタグが付けられたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ea377-118">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="ea377-119">>それ以外の場合は、[追跡] タブの結果を表示し、エラーの余白と次の手順を制御する場合は、[次のステップ]の隣にある [変更] をクリックし、[評価の続行] を選択して **、[OK]** をクリックします。  </span><span class="sxs-lookup"><span data-stu-id="ea377-119">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="ea377-120">**[Assessment]** チェック ボックスの右側にある [**変更]** をクリックして、問題ごとの評価パラメーターを表示および指定します。</span><span class="sxs-lookup"><span data-stu-id="ea377-120">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="ea377-121">次 **の例に示** すように、各問題の Assessment レベル ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-121">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![評価レベルのケースの問題](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="ea377-123">問題の次のパラメーターが計算され、[評価レベル] ダイアログ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="ea377-124">**取り消し予測の** 対象誤差余白 : この値に基づいて、レビューに必要な追加ファイルの推定数が計算されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-124">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="ea377-125">取り消しに使用される余白は 75% を超え、信頼度は 95% です。</span><span class="sxs-lookup"><span data-stu-id="ea377-125">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="ea377-126">**必要な追加の** 評価ファイル : 現在のエラー余白の要件が満たされていない場合に必要なファイルの数を示します。</span><span class="sxs-lookup"><span data-stu-id="ea377-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="ea377-127">現在のエラー余白を調整し、(問題ごとに) 異なるエラー余白の効果を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea377-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="ea377-128">[問題 **の選択] ボックスの** 一覧で、問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea377-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="ea377-129">取 **り消し見積もりの目標誤差余白に、新** しい値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea377-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="ea377-130">[ **値の更新]** をクリックして、調整の影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="ea377-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="ea377-131">[Assessment **レベル]** ダイアログで **[詳細設定] をクリック** すると、次の追加パラメーターと詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![[評価レベルのケースの問題] 詳細ビュー](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="ea377-133">**予想されるリッチ** 度 : 現在の評価結果に従って予想される豊富さ</span><span class="sxs-lookup"><span data-stu-id="ea377-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="ea377-134">**想定される取り消** しの場合: 既定では、目標誤差の余白は 75% を超え、取り消しに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-134">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="ea377-135">この **パラメーターを** 変更し、別の範囲の取り消し値でエラーの余白を制御する場合は、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea377-135">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="ea377-136">**信頼度**: 既定では、信頼度の推奨誤差幅は 95% です。</span><span class="sxs-lookup"><span data-stu-id="ea377-136">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="ea377-137">この **パラメーターを変更** する場合は、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea377-137">Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="ea377-138">**予想されるリッチ 度のエラー余白**: 更新された値を基に、すべての追加の評価ファイルを確認した後の、リッチ度のエラーの予想される余白です。</span><span class="sxs-lookup"><span data-stu-id="ea377-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="ea377-139">**必要な追加の** 評価ファイル : 更新された値を基に、ターゲットに到達するために確認する必要がある追加の評価ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="ea377-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="ea377-140">**必要な評価ファイルの合計**: 更新された値を基に、レビューに必要な評価ファイルの合計。</span><span class="sxs-lookup"><span data-stu-id="ea377-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="ea377-141">**評価における関連** ファイルの予想数 : 更新された値を基に、すべての追加評価ファイルがレビューされた後の評価全体の関連ファイルの予想数。</span><span class="sxs-lookup"><span data-stu-id="ea377-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="ea377-142">パラメーター **が変更されている場合は、[値の** 再計算] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea377-142">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="ea377-143">完了したら、問題が 1 つある場合は **、[OK]** をクリックして変更を保存します (確認または変更する問題が複数ある場合は [次へ] をクリックし、[完了]**をクリック** します)。</span><span class="sxs-lookup"><span data-stu-id="ea377-143">When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="ea377-144">複数の問題がある場合、すべての問題が確認または調整された後、次の例に示すように **、Assessment** レベル: 概要ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![評価レベルの概要](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="ea377-146">評価が正常に完了したら、関連性トレーニングの次のステージに進みます。</span><span class="sxs-lookup"><span data-stu-id="ea377-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="ea377-147">評価結果の確認</span><span class="sxs-lookup"><span data-stu-id="ea377-147">Reviewing assessment results</span></span>

<span data-ttu-id="ea377-148">Assessment サンプルにタグが付けられた後、評価結果が計算され、[関連性トラック] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="ea377-149">展開されたトラック表示には、次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="ea377-150">取り消し見積もりの現在のエラー余白の評価</span><span class="sxs-lookup"><span data-stu-id="ea377-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="ea377-151">予想されるリッチさ</span><span class="sxs-lookup"><span data-stu-id="ea377-151">Estimated richness</span></span>
    
- <span data-ttu-id="ea377-152">追加の評価ファイルが必要 (レビュー用)</span><span class="sxs-lookup"><span data-stu-id="ea377-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="ea377-153">Assessment の現在のエラー余白は、Advanced eDiscovery で推奨されるエラー余白です。</span><span class="sxs-lookup"><span data-stu-id="ea377-153">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="ea377-154">"必要な追加の評価ファイル" に表示される番号は、その推奨事項に対応します。</span><span class="sxs-lookup"><span data-stu-id="ea377-154">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="ea377-155">Assessment の進行状況インジケーターは、現在のエラー余白を考えると、評価の完了レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="ea377-155">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="ea377-156">評価が進行中の場合、ユーザーは別の評価サンプルにタグを付けします。</span><span class="sxs-lookup"><span data-stu-id="ea377-156">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="ea377-157">評価の進行状況インジケーターが評価の完了を示す場合、つまり、評価サンプルのレビューが完了し、十分な関連ファイルにタグが付けられたという意味です。</span><span class="sxs-lookup"><span data-stu-id="ea377-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="ea377-158">展開されたトラックの表示には、推奨される次の手順、評価統計、および詳細な結果へのアクセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea377-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="ea377-159">リッチ度が非常に低い場合、有用な統計情報を生成するために最小限の関連ファイルに到達するために必要な追加の評価ファイルの数は非常に多くです。</span><span class="sxs-lookup"><span data-stu-id="ea377-159">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="ea377-160">Advanced eDiscovery では、トレーニングへの移行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea377-160">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="ea377-161">評価の進行状況インジケーターは網掛けされ、統計情報は利用できません。</span><span class="sxs-lookup"><span data-stu-id="ea377-161">The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="ea377-162">統計ベースの手ブレ補正がない場合、精度と信頼度のレベルが低い結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ea377-162">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="ea377-163">ただし、関連ファイルの検出率を知る必要がなっていない場合、これらの結果を使用して関連ファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ea377-163">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="ea377-164">同様に、この状態を使用して、リッチ度の低い問題をトレーニングできます。関連性スコアは、特定の問題に関連するファイルへのアクセスを加速できます。</span><span class="sxs-lookup"><span data-stu-id="ea377-164">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="ea377-165">[関連トラック] タブの展開された問題表示では、次の表示オプションを使用できます。 > 次の推奨される手順(次の手順: [次のステップ] など) は、右側の [変更] ボタンをクリックし、次の手順で別の手順を選択すると、問題ごとにバイパスできます。 **\>**</span><span class="sxs-lookup"><span data-stu-id="ea377-165">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="ea377-166">評価の進行状況インジケーターが完了していない場合、評価は、より多くの評価ファイルにタグを付け、統計情報の精度を高める次の推奨オプションになります。</span><span class="sxs-lookup"><span data-stu-id="ea377-166">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> <span data-ttu-id="ea377-167">>エラーの余白を変更し、その影響を評価するには、[変更] をクリックし、[評価レベル] ダイアログで、取り消し見積もりのターゲット エラー余白を変更し、[値の更新] をクリック **します。** </span><span class="sxs-lookup"><span data-stu-id="ea377-167">> You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="ea377-168">また、このダイアログでは、[詳細設定] をクリックして詳細オプションを **表示できます**。</span><span class="sxs-lookup"><span data-stu-id="ea377-168">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> <span data-ttu-id="ea377-169">>追加の評価レベルの統計情報とその影響を表示するには、[表示] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ea377-169">> You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="ea377-170">表示された詳細結果ダイアログでは、少なくとも 500 のタグ付けされた評価ファイルと少なくとも 18 のファイルが問題に関連するタグ付けされている場合に、問題ごとに統計情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea377-170">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ea377-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea377-171">See also</span></span>

[<span data-ttu-id="ea377-172">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="ea377-172">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ea377-173">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="ea377-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ea377-174">タグ付けと関連性のトレーニング</span><span class="sxs-lookup"><span data-stu-id="ea377-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ea377-175">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="ea377-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ea377-176">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="ea377-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ea377-177">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="ea377-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

