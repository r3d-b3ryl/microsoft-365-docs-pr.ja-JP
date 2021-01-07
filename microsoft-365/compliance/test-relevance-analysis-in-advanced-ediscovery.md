---
title: Advanced eDiscovery での関連性分析のテスト
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Advanced eDiscovery のバッチ計算後に [テスト] タブを使用して、処理の全体的な品質をテスト、比較、検証する方法について説明します。
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769172"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="2d967-103">Advanced eDiscovery での関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="2d967-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="2d967-104">Advanced eDiscovery の [テスト] タブでは、処理の全体的な品質をテスト、比較、検証できます。</span><span class="sxs-lookup"><span data-stu-id="2d967-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="2d967-105">これらのテストは、バッチ計算後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="2d967-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="2d967-106">専門家は、コレクション内のファイルにタグを付け、タグ付けされた各ファイルがケースに関連するかどうかについて最終的な判断を下します。</span><span class="sxs-lookup"><span data-stu-id="2d967-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="2d967-107">単一および複数の問題のシナリオでは、テストは通常、問題ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="2d967-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="2d967-108">各テストの後に結果を表示し、指定したサンプル テスト ファイルを使用してテスト結果を再作業できます。</span><span class="sxs-lookup"><span data-stu-id="2d967-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="2d967-109">残りのテスト</span><span class="sxs-lookup"><span data-stu-id="2d967-109">Testing the rest</span></span>

<span data-ttu-id="2d967-110">「残りのテスト」テストは、カリングの決定を検証するために使用されます。たとえば、最終的な Advanced eDiscovery の結果に基づいて、特定の関連性カットオフ スコアの上にあるファイルのみを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d967-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="2d967-111">エキスパートは、選択したカットオフ スコアの下にあるファイルのサンプルをレビューして、そのセット内の関連ファイルの数を評価します。</span><span class="sxs-lookup"><span data-stu-id="2d967-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="2d967-112">このテストでは、レビュー セットと残りの母集団の統計と比較を行います。</span><span class="sxs-lookup"><span data-stu-id="2d967-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="2d967-113">レビュー セットの結果は、トレーニング中に関連性によって計算されます。</span><span class="sxs-lookup"><span data-stu-id="2d967-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="2d967-114">結果には、次のような設定と入力パラメーターに基づく計算が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d967-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="2d967-115">サンプル内のファイル数と、関連するファイルを特定したサンプル統計情報をテストします。</span><span class="sxs-lookup"><span data-stu-id="2d967-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="2d967-116">レビュー セットの母集団パラメーターと残りの部分を表形式で比較します。たとえば、ファイル数、関連するファイルの推定数、予想されるリッチさ、および別の関連ファイルを検索する平均コストなどです。</span><span class="sxs-lookup"><span data-stu-id="2d967-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="2d967-117">コスト パラメーターの設定は、管理者が設定できます。</span><span class="sxs-lookup"><span data-stu-id="2d967-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="2d967-118">"残りのテスト" テストを実行するには、</span><span class="sxs-lookup"><span data-stu-id="2d967-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="2d967-119">[関連性テスト **] タブ \> を開** きます。</span><span class="sxs-lookup"><span data-stu-id="2d967-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="2d967-120">[テスト **] タブで** 、[新しいテスト] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2d967-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="2d967-121">次 **の例に** 示すように、[テストの作成] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d967-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![関連性テストの残りの結果](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="2d967-123">[ **テスト名]** と [ **説明] に**、名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="2d967-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="2d967-124">[テストの **種類] ボックスの一覧** で、[ **残りのテスト] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="2d967-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="2d967-125">[問題 **] / [カテゴリ] の** 一覧で、問題名を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d967-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="2d967-126">[読み **込み] ボックス** の一覧で、負荷を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d967-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="2d967-127">[ **読み取り率**] で、既定値を受け入れるか、カットオフ関連性スコアの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d967-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="2d967-128">[ **サイズの設定]** または既定値を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="2d967-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="2d967-129">復元アイコンは既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="2d967-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="2d967-130">[タグ **付けの開始] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2d967-130">Click **Start tagging**.</span></span> <span data-ttu-id="2d967-131">テスト サンプルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2d967-131">A test sample is generated.</span></span>

10. <span data-ttu-id="2d967-132">[関連タグ] タブの各ファイルを確認してタグ付 **\> け** し、完了したら 、[計算] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="2d967-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="2d967-133">[テスト] タブで、[結果の表示 **]** をクリックしてテスト結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2d967-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="2d967-134">次のスクリーンショットに例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d967-134">An example is shown in the following screenshot.</span></span>

    ![残りの結果をテストする](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="2d967-136">前のスクリーンショットの表のサンプル パラメーター セクションには、エキスパートによってタグ付けされたサンプル内のファイル数と、そのサンプルで見つかった関連ファイルの数に関する詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d967-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="2d967-137">表の **[母** 集団のパラメーター] セクションには、選択した切り離しの下のスコアを持つファイルのレビュー セットの母集団と、選択したカットオフの上にスコアを持つファイルの "残りの" 母集団が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d967-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="2d967-138">母集団ごとに、次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d967-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="2d967-139">読み取り率 - 示された切り離しのファイルが含まれます</span><span class="sxs-lookup"><span data-stu-id="2d967-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="2d967-140">ファイルの総数</span><span class="sxs-lookup"><span data-stu-id="2d967-140">The total number of files</span></span>

- <span data-ttu-id="2d967-141">関連ファイルの推定数</span><span class="sxs-lookup"><span data-stu-id="2d967-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="2d967-142">予想されるリッチさ</span><span class="sxs-lookup"><span data-stu-id="2d967-142">The estimated richness</span></span>

- <span data-ttu-id="2d967-143">別の関連ファイルを検索する平均レビュー コスト</span><span class="sxs-lookup"><span data-stu-id="2d967-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="2d967-144">スライスのテスト</span><span class="sxs-lookup"><span data-stu-id="2d967-144">Testing the slice</span></span>

<span data-ttu-id="2d967-145">"スライスのテスト" テストは、"残りのテスト" テストと同様のテストを実行しますが、関連度の読み取り % で指定されたファイル セットのセグメントに対して実行します。</span><span class="sxs-lookup"><span data-stu-id="2d967-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="2d967-146">"スライスのテスト" テストを実行するには、</span><span class="sxs-lookup"><span data-stu-id="2d967-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="2d967-147">[関連性テスト **] タブ \> を開** きます。</span><span class="sxs-lookup"><span data-stu-id="2d967-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="2d967-148">[テスト **] タブで** 、[新しいテスト] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2d967-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="2d967-149">[ **テストの作成]** ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d967-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="2d967-150">[ **テスト名] と** [ **説明] に** 情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2d967-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="2d967-151">[テストの **種類] ボックスの一覧** で、[ **スライスのテスト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2d967-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="2d967-152">[問題 **] ボックス** の一覧で、問題名を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d967-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="2d967-153">[読み **込み] ボックス** の一覧で、負荷を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d967-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="2d967-154">[ **次の値の間** の読み取り率] で、既定の低および高範囲の値を受け入れるか、カットオフ関連性スコアの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d967-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="2d967-155">[ **サイズの設定]** で、値を選択するか、既定値を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d967-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="2d967-156">復元アイコンは既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="2d967-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="2d967-157">[タグ **付けの開始] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2d967-157">Click **Start tagging**.</span></span> <span data-ttu-id="2d967-158">テスト サンプルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2d967-158">A test sample is generated.</span></span>

10. <span data-ttu-id="2d967-159">[関連タグ] タブの各ファイルを確認してタグ付 **\> け** し、完了したら 、[計算] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="2d967-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="2d967-160">[テスト] タブで、[結果の表示 **]** をクリックしてテスト結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2d967-160">In the Test tab, you can click **View results** to see the test results.</span></span>
