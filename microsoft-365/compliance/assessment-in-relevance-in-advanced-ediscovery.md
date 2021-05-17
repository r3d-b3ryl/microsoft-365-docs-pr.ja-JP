---
title: 関連度の評価について(Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 評価ステージの概要と、関連度トレーニング中の問題の豊富さを判断する際の役割Microsoft 365 Advanced eDiscovery。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769278"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="95ee7-103">[関連度] モジュールの評価Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="95ee7-103">Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="95ee7-104">Advanced eDiscovery定義された問題やケースに対してインポートされたデータなど、早期評価を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-104">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="95ee7-105">Advanced eDiscovery、採用されたアプローチに関する意思決定を専門家が行い、これらの決定をドキュメント レビュー プロジェクトに適用できます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-105">Advanced eDiscovery lets the expert make decisions about an adopted approach and to apply these decisions to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="95ee7-106">評価について</span><span class="sxs-lookup"><span data-stu-id="95ee7-106">Understanding assessment</span></span>

<span data-ttu-id="95ee7-107">Assessment では、専門家が少なくとも 500 ファイルのランダム セットをレビューします。これは、問題の豊富さを判断し、トレーニング結果を反映する統計を生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-107">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="95ee7-108">Advanced eDiscovery Relevante が正確な統計を提供し、トレーニング プロセスの安定化ポイントを効果的に判断するのに役立つ統計レベルに達するのに十分な関連ファイルが見つかった場合、評価は成功します。</span><span class="sxs-lookup"><span data-stu-id="95ee7-108">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="95ee7-109">評価セット内の関連ファイルの数が多いほど、統計と安定性アルゴリズムの有効性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="95ee7-109">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="95ee7-110">評価ファイル内の関連ファイルの数は、問題の豊富さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="95ee7-110">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="95ee7-111">リッチとは、問題に関連するセット内の関連ファイルの推定割合です。</span><span class="sxs-lookup"><span data-stu-id="95ee7-111">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="95ee7-112">リッチ度が高い問題は、リッチ度が低い問題よりも、関連するファイルの数が多くなります。</span><span class="sxs-lookup"><span data-stu-id="95ee7-112">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="95ee7-113">非常にリッチ度が低い問題 (たとえば、2% 以下) では、関連するファイルの数が多い場合は、非常に大きな評価セットが必要になります。</span><span class="sxs-lookup"><span data-stu-id="95ee7-113">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="95ee7-114">トレーニング中とバッチ計算後の [トラック] タブと [決定] タブに表示される統計には、さまざまなレビュー セットのリコールの推定値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-114">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="95ee7-115">統計では、サンプル セット (この場合は評価ファイル) に基づく推定には、誤差の余白と、そのエラー マージンの信頼度が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-115">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="95ee7-116">たとえば、推定 80% のリコールの誤差幅はプラスまたはマイナス 5% で、信頼度は 95% です。</span><span class="sxs-lookup"><span data-stu-id="95ee7-116">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="95ee7-117">つまり、推定リコールは実際には 75%~85% で、この推定値の信頼度は 95% です。</span><span class="sxs-lookup"><span data-stu-id="95ee7-117">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="95ee7-118">評価セットが大きいほど、誤差の余白が小さくなり、統計の精度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="95ee7-118">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="95ee7-119">専門家が 500 ファイルの初期評価セットをレビューした後、関連度は、リコール値の現在の誤差幅を決定できます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-119">After the expert reviews an initial assessment set of 500 files, Relevance can determine the current margin of error of the recall values.</span></span> <span data-ttu-id="95ee7-120">関連性は、評価セットを最適化するために到達する既定の誤差幅も推奨します。</span><span class="sxs-lookup"><span data-stu-id="95ee7-120">Relevance will also recommend a default margin of error to reach to optimize the assessment set.</span></span> <span data-ttu-id="95ee7-121">次に、いくつかの例を示します:</span><span class="sxs-lookup"><span data-stu-id="95ee7-121">Here are some examples:</span></span>
  
- <span data-ttu-id="95ee7-122">評価セットが既にプラスまたはマイナス 10% の誤差幅を生み出した場合、関連性はトレーニングに移行することをお勧めします (追加の評価レビューは不要です)。</span><span class="sxs-lookup"><span data-stu-id="95ee7-122">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend moving on to training (no additional assessment review is needed).</span></span> 

- <span data-ttu-id="95ee7-123">評価セットで誤差の余白がプラスまたはマイナス 13% の場合、関連性は小さい余白に達するために別の評価ファイルセットのレビューを推奨する場合があります。</span><span class="sxs-lookup"><span data-stu-id="95ee7-123">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 

- <span data-ttu-id="95ee7-124">リッチ度が極端に低い場合、関連性は、誤差の余白が大きい (統計が非現実的になる) 場合でも、有用な誤差幅に達するために必要な評価セットが大きすぎるため、評価を停止することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="95ee7-124">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>

<span data-ttu-id="95ee7-125">各問題には、独自の豊富さ、現在の誤差幅、および結果として、追加の評価ファイルの推定数があります。</span><span class="sxs-lookup"><span data-stu-id="95ee7-125">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="95ee7-126">次の評価セットは、ファイルの最大数 (1 つのセットで最大 1,000) に従って作成されます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-126">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="95ee7-127">関連性の推奨事項を受け入れるか、ニーズに応じて現在の誤差幅を調整できます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-127">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="95ee7-128">既定の現在の誤差幅は、75% 以上のリコールに対して決定されます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-128">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="95ee7-129">問題の展開ビューの [関連性の追跡] タブで、問題ごとに [評価] チェック ボックスをオフにし、[すべての問題] を選択すると、評価ステージをバイパスできます。 **\>**</span><span class="sxs-lookup"><span data-stu-id="95ee7-129">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="95ee7-130">その結果、この問題に関する統計情報はありません。</span><span class="sxs-lookup"><span data-stu-id="95ee7-130">As a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="95ee7-131">[評価] **チェック** ボックスをオフにできるのは、評価が実行される前のみです。</span><span class="sxs-lookup"><span data-stu-id="95ee7-131">Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="95ee7-132">ケースに複数の問題が存在する場合、各問題のチェック ボックスがオフの場合にのみ評価がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="95ee7-132">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue.</span></span>
