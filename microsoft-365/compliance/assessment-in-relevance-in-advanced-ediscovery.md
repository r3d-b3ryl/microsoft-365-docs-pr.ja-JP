---
title: 高度な電子情報開示の関連性の評価を理解する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Microsoft 365 Advanced eDiscovery の関連トレーニングにおいて、さまざまな問題を特定するための評価ステージとその役割についての概要を説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: afd4f1f549d52652ac02cfa410efc507ece58910
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818416"
---
# <a name="understand-assessment-in-relevance-in-advanced-ediscovery-classic"></a><span data-ttu-id="b8ec2-103">高度な電子情報開示で関連性のある評価を理解する (クラシック)</span><span class="sxs-lookup"><span data-stu-id="b8ec2-103">Understand Assessment in Relevance in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="b8ec2-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="b8ec2-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="b8ec2-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="b8ec2-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b8ec2-106">上級電子情報開示では、たとえば定義済みの問題とケースに対してインポートされたデータについて、早期に評価することができます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-106">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="b8ec2-107">上級電子情報開示を使用すると、エキスパートは採用されたアプローチを決定し、ドキュメントレビュープロジェクトにこれらの決定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-107">Advanced eDiscovery lets the expert make decisions about an adopted approach and to apply these decisions to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="b8ec2-108">評価について</span><span class="sxs-lookup"><span data-stu-id="b8ec2-108">Understanding assessment</span></span>

<span data-ttu-id="b8ec2-109">評価では、専門家は少なくとも500のファイルのランダムセットをレビューします。これは、問題の豊富さを特定し、トレーニング結果を反映するために統計情報を生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-109">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="b8ec2-110">詳細な電子情報開示の関連性を向上させるために詳細な電子情報開示の関連性を向上させる統計レベルに達すると、評価は成功します。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-110">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="b8ec2-111">評価セット内の関連ファイルの数が多いほど、安定性アルゴリズムの統計と効果が正確になります。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-111">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="b8ec2-112">評価ファイル内の関連ファイルの数は、その問題の豊富さに依存します。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-112">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="b8ec2-113">多様性は、懸案事項に関連する設定の関連ファイルの予想パーセンテージです。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-113">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="b8ec2-114">低コストの問題よりも、より高いレベルの関連ファイルをより多く使用すると、低低の問題よりも高速になります。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-114">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="b8ec2-115">非常に低い (たとえば2% 以下の) 豊富な問題については、膨大な数の関連ファイルを獲得するために非常に大きな評価を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-115">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="b8ec2-116">この統計情報は、トレーニング中に [追跡] タブと [決定] タブに表示されます。また、バッチ計算後には、さまざまなレビューセットに対する呼び戻しの見積もりを含みます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-116">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="b8ec2-117">Statistics では、サンプルセット (この例では評価ファイル) に基づく見積もりには、エラーの余白と、その誤差範囲の信頼度レベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-117">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="b8ec2-118">たとえば、80% の予想リコールは、信頼レベルが95% で、プラスまたはマイナス5% の誤差がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-118">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="b8ec2-119">これは、推定される呼び戻しは実際には 75%-85% で、この推定は95% の信頼度があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-119">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="b8ec2-120">評価セットが大きいほど、エラーの余白が小さくなり、統計値がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-120">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="b8ec2-121">専門家が500ファイルの初期評価セットをレビューした後、関連性によって、呼び戻し値の現在のエラーのマージンを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-121">After the expert reviews an initial assessment set of 500 files, Relevance can determine the current margin of error of the recall values.</span></span> <span data-ttu-id="b8ec2-122">また、評価セットを最適化するために、既定のエラーの許容範囲を設定することも推奨されます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-122">Relevance will also recommend a default margin of error to reach to optimize the assessment set.</span></span> <span data-ttu-id="b8ec2-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-123">Here are some examples:</span></span>
  
- <span data-ttu-id="b8ec2-124">評価セットで既にプラスまたはマイナス10% の誤差が得られている場合は、トレーニングへの移行をお勧めします (追加の評価レビューは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend moving on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="b8ec2-125">評価セットでプラスまたはマイナス13% の誤差が得られた場合は、別の評価ファイルのセットをレビューして、より小さな余白に到達することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="b8ec2-126">豊富な機能が非常に低い場合は、エラーの許容範囲を超えている場合でも、評価を停止することをお勧めします (統計値が実用的でない場合)。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="b8ec2-127">各問題には、さまざまな豊富なエラーがあり、その結果として予測される追加評価ファイルの推定数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-127">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="b8ec2-128">次の評価セットは、最大ファイル数 (1 つのセット内の最大 1000) に従って作成されます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-128">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="b8ec2-129">必要に応じて、関連性に関する推奨事項を受け入れるか、または現在の誤差の余白を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-129">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="b8ec2-130">既定のエラーの現在のマージンは、「呼び戻し」では、75% 以上であることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-130">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8ec2-131">問題が発生した場合は、展開されたビューの [**関連性の \> 追跡**] タブで、問題ごとに [**評価**] チェックボックスをオフにし、次に [すべての問題] を選択して、評価ステージをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-131">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="b8ec2-132">そのため、この問題に関する統計情報はありません。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-132">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="b8ec2-133">[**評価**] チェックボックスをオフにする > は、評価が実行される前にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-133">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="b8ec2-134">複数の問題が存在する場合は、各問題のチェックボックスがオフになっている場合にのみ評価が省略されます。</span><span class="sxs-lookup"><span data-stu-id="b8ec2-134">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="b8ec2-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8ec2-135">Related topics</span></span>

[<span data-ttu-id="b8ec2-136">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="b8ec2-136">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b8ec2-137">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="b8ec2-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b8ec2-138">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="b8ec2-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b8ec2-139">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="b8ec2-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b8ec2-140">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="b8ec2-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b8ec2-141">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="b8ec2-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

