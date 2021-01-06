---
title: Advanced eDiscovery の関連性の評価を理解する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Assessment ステージの概要と、Microsoft 365 Advanced eDiscovery の関連度トレーニング中の問題の豊富さを判断する役割について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9ce400af87af36dfc9e0d51caba90b952edec9c
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759923"
---
# <a name="understand-assessment-in-relevance-in-advanced-ediscovery-classic"></a><span data-ttu-id="6f66c-103">Advanced eDiscovery (クラシック) の関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="6f66c-103">Understand Assessment in Relevance in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="6f66c-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="6f66c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6f66c-106">Advanced eDiscovery では、定義済みの問題やケースにインポートされたデータなど、早期評価が可能です。</span><span class="sxs-lookup"><span data-stu-id="6f66c-106">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="6f66c-107">Advanced eDiscovery を使用すると、専門家は採用されたアプローチについて決定を行い、これらの決定をドキュメント レビュー プロジェクトに適用できます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-107">Advanced eDiscovery lets the expert make decisions about an adopted approach and to apply these decisions to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="6f66c-108">評価について</span><span class="sxs-lookup"><span data-stu-id="6f66c-108">Understanding assessment</span></span>

<span data-ttu-id="6f66c-109">Assessment では、専門家は少なくとも 500 ファイルのランダム セットをレビューします。このファイルは、問題の豊富さを判断し、トレーニング結果を反映した統計を生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-109">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="6f66c-110">適切な関連ファイルが統計レベルに達し、Advanced eDiscovery の関連性が正確な統計情報を提供し、トレーニング プロセスの手ブレ補正ポイントを効果的に決定するのに役立つ場合、評価は成功します。</span><span class="sxs-lookup"><span data-stu-id="6f66c-110">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="6f66c-111">評価セット内の関連ファイルの数が多いほど、安定性アルゴリズムの統計情報と有効性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="6f66c-111">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="6f66c-112">評価ファイル内の関連ファイルの数は、問題の豊富さによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6f66c-112">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="6f66c-113">リッチとは、セット内の問題に関連する関連ファイルの推定割合です。</span><span class="sxs-lookup"><span data-stu-id="6f66c-113">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="6f66c-114">リッチ度が高い問題は、リッチ度の低い問題よりも、関連性の高いファイルの数が多くなります。</span><span class="sxs-lookup"><span data-stu-id="6f66c-114">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="6f66c-115">リッチ度が非常に低い問題 (たとえば、2% 以下) では、多数の関連ファイルに到達するには、非常に大きな評価セットが必要になります。</span><span class="sxs-lookup"><span data-stu-id="6f66c-115">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="6f66c-116">トレーニング中とバッチ計算後に [追跡] タブと [決定] タブに表示される統計情報には、さまざまなレビュー セットの取り消しの予測が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-116">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="6f66c-117">統計では、サンプル セット (この場合は評価ファイル) に基づく推定には、エラーの余白と、そのエラー余白の信頼度が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-117">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="6f66c-118">たとえば、推定される 80% の取り消しでは、誤差はプラスマイナス 5% で、信頼度は 95% です。</span><span class="sxs-lookup"><span data-stu-id="6f66c-118">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="6f66c-119">つまり、推定リコールは実際には 75% ~ 85% であり、この推定値の信頼度は 95% です。</span><span class="sxs-lookup"><span data-stu-id="6f66c-119">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="6f66c-120">評価セットが大きいほど、エラーの余白が小さくなり、統計情報の精度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="6f66c-120">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="6f66c-121">専門家が 500 ファイルの初期評価セットをレビューした後、関連度は、取り消し値の現在のエラーの余白を判断できます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-121">After the expert reviews an initial assessment set of 500 files, Relevance can determine the current margin of error of the recall values.</span></span> <span data-ttu-id="6f66c-122">関連性では、評価セットを最適化するために到達するエラーの既定の余白も推奨されます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-122">Relevance will also recommend a default margin of error to reach to optimize the assessment set.</span></span> <span data-ttu-id="6f66c-123">次に、いくつかの例を示します:</span><span class="sxs-lookup"><span data-stu-id="6f66c-123">Here are some examples:</span></span>
  
- <span data-ttu-id="6f66c-124">評価セットで既に正負 10% の誤差幅が得られた場合、関連性はトレーニングに移行することをお勧めします (追加の評価レビューは必要ない)。</span><span class="sxs-lookup"><span data-stu-id="6f66c-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend moving on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="6f66c-125">評価セットの誤差がプラスマイナス 13% の余白を生み出した場合、関連性は、小さな余白に達するために別の評価ファイルセットのレビューを推奨する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6f66c-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="6f66c-126">リッチ度が非常に低い場合、関連性は、エラーの余白が大きい (統計を非現実的に) しても評価を停止することをお勧めします。これは、有用なエラーの余白に達するために必要な評価セットが大きすぎるためです。</span><span class="sxs-lookup"><span data-stu-id="6f66c-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="6f66c-127">各問題には、独自の豊富さ、現在のエラーの余白、および結果として、追加の評価ファイルの推定数があります。</span><span class="sxs-lookup"><span data-stu-id="6f66c-127">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="6f66c-128">次の評価セットは、ファイルの最大数 (単一セットでは最大 1,000) に従って作成されます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-128">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="6f66c-129">関連性の推奨事項を受け入れるか、必要に応じて現在のエラーの余白を調整できます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-129">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="6f66c-130">エラーの既定の現在の余白は、取り消し率が 75% 以上と判断されます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-130">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f66c-131">Assessment ステージは、問題の展開ビューの [関連性トラック] タブで、問題ごとに [Assessment]チェック ボックスをオフにし、[すべての問題] に対してオフにすることでバイパスできます。 **\>**</span><span class="sxs-lookup"><span data-stu-id="6f66c-131">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="6f66c-132">ただし、その結果、この問題に関する統計情報はありません。</span><span class="sxs-lookup"><span data-stu-id="6f66c-132">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="6f66c-133">>チェック **ボックスを** オフにできるのは、評価が実行される前のみです。</span><span class="sxs-lookup"><span data-stu-id="6f66c-133">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="6f66c-134">1 つのケースに複数の問題が存在する場合、評価は、問題ごとにチェック ボックスがオフの場合にのみバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="6f66c-134">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue.</span></span>