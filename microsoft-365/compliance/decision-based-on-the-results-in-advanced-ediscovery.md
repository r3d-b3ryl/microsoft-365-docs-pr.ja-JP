---
title: Advanced eDiscovery の結果に基づく決定
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Advanced eDiscovery の [決定] タブで、ケース ファイルのレビュー セットの正しいサイズを判断するのに役立つデータを提供する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0423a21520375f1d9de8e2eaeca142b979ff1883
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759869"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="112f5-103">Advanced eDiscovery (クラシック) の結果に基づく決定</span><span class="sxs-lookup"><span data-stu-id="112f5-103">Decision based on the results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="112f5-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="112f5-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="112f5-106">Advanced eDiscovery では、[決定] タブには、ケース ファイルのレビュー セットのサイズを決定するための意思決定サポート統計を表示および使用するための追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="112f5-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="112f5-107">[決定] タブの使用</span><span class="sxs-lookup"><span data-stu-id="112f5-107">Using the Decide tab</span></span>

![関連性の決定](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="112f5-109">このタブには、次のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="112f5-109">This tab includes the following components:</span></span>
  
- <span data-ttu-id="112f5-110">**問題**: ここから、リストから関心のある問題を選択できます。</span><span class="sxs-lookup"><span data-stu-id="112f5-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="112f5-111">**レビューリコール率**: 関連性スコアに従った Advanced eDiscovery レビューの比較。</span><span class="sxs-lookup"><span data-stu-id="112f5-111">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="112f5-112">グラフの切り離し点は、関連性スコアにマップされた、レビューするファイルの割合を表します。</span><span class="sxs-lookup"><span data-stu-id="112f5-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="112f5-113">これは、関連性テスト フェーズで使用され、カリングのエクスポートしきい値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="112f5-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="112f5-114">レビューするファイル数の既定の切り離し点は、取り消しと精度のバランスが最適な時点です。</span><span class="sxs-lookup"><span data-stu-id="112f5-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="112f5-115">実際の切り離しポイントは、目標とコストのトレードオフ (%review) とリスク (%recall) に応じてユーザーが決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112f5-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="112f5-116">スライダーを使って、カットオフ ポイントを調整し、グラフとパラメーターへの影響、取得する関連ファイルの割合を調整する場合、および決定を検証する前に確認できます。</span><span class="sxs-lookup"><span data-stu-id="112f5-116">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="112f5-117">**パラメーター**: レビュー、取り消し、次の関連する総コストパラメーターは、ケース全体のコレクションに関連するレビュー セットに関連する累積計算された統計です。</span><span class="sxs-lookup"><span data-stu-id="112f5-117">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="112f5-118">これらのパラメーターの定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="112f5-118">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="112f5-119">**Review**: このカットオフに基づいて確認するファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="112f5-119">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="112f5-120">**取** り消し : レビュー セット内の関連ファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="112f5-120">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="112f5-121">**次に関連**: 現在レビュー セットに含されていない追加の関連ファイルを確認して識別するためのコスト。</span><span class="sxs-lookup"><span data-stu-id="112f5-121">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="112f5-122">**総コスト**: ケース ファイルのこの割合を確認するコスト。</span><span class="sxs-lookup"><span data-stu-id="112f5-122">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="112f5-123">コスト パラメーターの設定は、ケース マネージャーが設定できます。</span><span class="sxs-lookup"><span data-stu-id="112f5-123">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="112f5-124">**関連性スコアによる配布**: 左に濃い灰色の表示のファイルは、カットオフ スコアの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="112f5-124">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="112f5-125">ツール ヒントには、ファイルの合計に関連する、レビュー ファイル セット内のファイルの関連性スコアと関連する割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="112f5-125">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="112f5-126">展開された [詳細] ウィンドウには、追加の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="112f5-126">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="112f5-127">コレクションの図に含まれるファイルには、空のファイルや大きいなファイルは含めされません。</span><span class="sxs-lookup"><span data-stu-id="112f5-127">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="112f5-128">ファミリ ファイルの図は、関連性に読み込まれなのにファミリの一部としてカウントされているファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="112f5-128">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
