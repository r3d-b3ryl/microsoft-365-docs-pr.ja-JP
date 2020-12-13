---
title: Advanced eDiscovery での関連性分析のテスト
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: Advanced eDiscovery のバッチ計算後に [テスト] タブを使用して、処理の全体的な品質をテスト、比較、検証する方法について説明します。
ms.openlocfilehash: e408d79aac8015da210f983b7b388ace84fc383a
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663420"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="39564-103">Advanced eDiscovery (クラシック) での関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="39564-103">Test Relevance analysis in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="39564-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="39564-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="39564-106">Advanced eDiscovery の [テスト] タブでは、処理の全体的な品質をテスト、比較、検証できます。</span><span class="sxs-lookup"><span data-stu-id="39564-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="39564-107">これらのテストは、バッチ計算後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="39564-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="39564-108">専門家は、コレクション内のファイルにタグを付け、タグ付けされた各ファイルがケースに実際に関連するかどうかについて最終的な判断を下します。</span><span class="sxs-lookup"><span data-stu-id="39564-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="39564-109">単一および複数の問題のシナリオでは、テストは通常、問題ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="39564-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="39564-110">各テストの後に結果を表示し、指定したサンプル テスト ファイルを使用してテスト結果を再作業できます。</span><span class="sxs-lookup"><span data-stu-id="39564-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="39564-111">残りのテスト</span><span class="sxs-lookup"><span data-stu-id="39564-111">Testing the rest</span></span>

<span data-ttu-id="39564-112">「残りのテスト」テストは、カリングの決定を検証するために使用されます。たとえば、最終的な Advanced eDiscovery の結果に基づいて、特定の関連性カットオフ スコアの上にあるファイルのみを確認します。</span><span class="sxs-lookup"><span data-stu-id="39564-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="39564-113">エキスパートは、選択したカットオフ スコアの下にあるファイルのサンプルをレビューして、そのセット内の関連ファイルの数を評価します。</span><span class="sxs-lookup"><span data-stu-id="39564-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="39564-114">このテストでは、レビュー セットと残りの母集団の統計と比較を行います。</span><span class="sxs-lookup"><span data-stu-id="39564-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="39564-115">レビュー セットの結果は、トレーニング中に関連性によって計算されます。</span><span class="sxs-lookup"><span data-stu-id="39564-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="39564-116">結果には、次のような設定と入力パラメーターに基づく計算が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39564-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="39564-117">サンプル内のファイル数と、関連するファイルを特定したサンプル統計情報をテストします。</span><span class="sxs-lookup"><span data-stu-id="39564-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="39564-118">レビュー セットの Population パラメーターと残りの部分を表形式で比較します。たとえば、ファイル数、関連するファイルの推定数、予想されるリッチさ、および追加の関連ファイルを検索する平均コストなどです。</span><span class="sxs-lookup"><span data-stu-id="39564-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="39564-119">コスト パラメーターの設定は、管理者が設定できます。</span><span class="sxs-lookup"><span data-stu-id="39564-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="39564-120">[関連性テスト **] タブ \> を開** きます。</span><span class="sxs-lookup"><span data-stu-id="39564-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="39564-121">[テスト **] タブで** 、[新しいテスト] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39564-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="39564-122">次 **の例に** 示すように、[テストの作成] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39564-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![関連性テストの残りの結果](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="39564-124">[ **テスト名]** と [ **説明] に**、名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="39564-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="39564-125">[テストの **種類] ボックスの一覧** で、[ **残りのテスト] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="39564-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="39564-126">[問題 **] / [カテゴリ] の** 一覧で、問題名を選択します。</span><span class="sxs-lookup"><span data-stu-id="39564-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="39564-127">[読み **込み] ボックス** の一覧で、負荷を選択します。</span><span class="sxs-lookup"><span data-stu-id="39564-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="39564-128">[ **読み取り率**] で、既定値を受け入れるか、カットオフ関連性スコアの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="39564-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="39564-129">[ **サイズの設定]** または既定値を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="39564-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="39564-130">復元アイコンは既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="39564-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="39564-131">[タグ **付けの開始] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39564-131">Click **Start tagging**.</span></span> <span data-ttu-id="39564-132">テスト サンプルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="39564-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="39564-133">[関連タグ] タブの各ファイルを確認してタグ付 **\> け** し、完了したら [計算] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="39564-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="39564-134">[テスト] タブで、[結果の表示 **]** をクリックしてテスト結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="39564-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="39564-135">次の図に例を示します。</span><span class="sxs-lookup"><span data-stu-id="39564-135">An example is shown in the following figure.</span></span> 
    
    ![残りの結果をテストする](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="39564-137">上の図では、テーブルの **サンプル** パラメーター セクションに、エキスパートによってタグ付けされたサンプル内のファイル数と、そのサンプルで見つかった関連ファイルの数に関する詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="39564-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="39564-138">表の **[母** 集団のパラメーター] セクションには、選択した切り離しの下のスコアを持つファイルのレビュー セットの母集団と、選択した切り離しの上にスコアを持つファイルの "残りの" 母集団が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39564-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="39564-139">母集団ごとに、次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39564-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="39564-140">読み取り率 - 示された切り離しのファイルが含まれます</span><span class="sxs-lookup"><span data-stu-id="39564-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="39564-141">ファイルの総数</span><span class="sxs-lookup"><span data-stu-id="39564-141">The total number of files</span></span> 
    
- <span data-ttu-id="39564-142">関連するファイルの推定数</span><span class="sxs-lookup"><span data-stu-id="39564-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="39564-143">予想されるリッチさ</span><span class="sxs-lookup"><span data-stu-id="39564-143">The estimated richness</span></span> 
    
- <span data-ttu-id="39564-144">別の関連ファイルを検索する平均レビュー コスト</span><span class="sxs-lookup"><span data-stu-id="39564-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="39564-145">スライスのテスト</span><span class="sxs-lookup"><span data-stu-id="39564-145">Testing the slice</span></span>

<span data-ttu-id="39564-146">"スライスのテスト" テストは、"残りのテスト" テストと同様のテストを実行しますが、関連度の読み取り % で指定されたファイル セットのセグメントに対して実行します。</span><span class="sxs-lookup"><span data-stu-id="39564-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="39564-147">[関連性テスト **] タブ \> を開** きます。</span><span class="sxs-lookup"><span data-stu-id="39564-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="39564-148">[テスト **] タブで** 、[新しいテスト] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39564-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="39564-149">[ **テストの作成]** ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39564-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="39564-150">[ **テスト名] と** [ **説明] に** 情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="39564-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="39564-151">[テストの **種類] ボックスの一覧** で、[ **スライスのテスト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39564-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="39564-152">[問題 **] ボックス** の一覧で、問題名を選択します。</span><span class="sxs-lookup"><span data-stu-id="39564-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="39564-153">[読み **込み] ボックス** の一覧で、負荷を選択します。</span><span class="sxs-lookup"><span data-stu-id="39564-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="39564-154">[ **次の値の間の** 読み取り率] で、既定の低および高範囲の値を受け入れるか、カットオフ関連性スコアの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="39564-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="39564-155">[ **サイズの設定]** で、値を選択するか、既定値を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="39564-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="39564-156">復元アイコンは既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="39564-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="39564-157">[タグ **付けの開始] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39564-157">Click **Start tagging**.</span></span> <span data-ttu-id="39564-158">テスト サンプルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="39564-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="39564-159">[関連タグ] タブの各ファイルを確認してタグ付 **\> け** し、完了したら [計算] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="39564-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="39564-160">[テスト] タブで、[結果の表示 **]** をクリックしてテスト結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="39564-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="39564-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="39564-161">See also</span></span>

[<span data-ttu-id="39564-162">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="39564-162">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="39564-163">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="39564-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="39564-164">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="39564-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="39564-165">タグ付けと関連性のトレーニング</span><span class="sxs-lookup"><span data-stu-id="39564-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="39564-166">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="39564-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="39564-167">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="39564-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

