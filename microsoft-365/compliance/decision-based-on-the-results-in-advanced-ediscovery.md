---
title: データの結果に基づくAdvanced eDiscovery
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
description: ケース ファイルのレビュー セットのAdvanced eDiscoveryを決定するのに役立つデータを提供する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769152"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="7d408-103">関連性に基づく決定は、データのAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7d408-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="7d408-104">[関連] モジュールの Advanced eDiscovery で、[決定] タブには、ケース ファイルのレビュー セットのサイズを決定するための意思決定サポート統計の表示と使用に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d408-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="7d408-105">[決定] タブの使用</span><span class="sxs-lookup"><span data-stu-id="7d408-105">Using the Decide tab</span></span>

![関連性の決定](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="7d408-107">このタブには、次のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d408-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="7d408-108">**問題**: ここから、リストから関心のある問題を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7d408-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="7d408-109">**レビューリコール率**: 関連性スコアにAdvanced eDiscoveryレビューの比較。</span><span class="sxs-lookup"><span data-stu-id="7d408-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="7d408-110">グラフのカットオフ ポイントは、関連性スコアにマップされた、レビューするファイルの割合を表します。</span><span class="sxs-lookup"><span data-stu-id="7d408-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="7d408-111">これは、関連性テスト フェーズで、およびカリングのエクスポートしきい値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d408-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="7d408-112">レビューするファイル数の既定のカットオフ ポイントは、呼び出しと精度のバランスが最適な時点です。</span><span class="sxs-lookup"><span data-stu-id="7d408-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="7d408-113">実際のカットオフ ポイントは、目標とコストトレードオフ (%review) とリスク (%リコール) に応じてユーザーが決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d408-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="7d408-114">スライダーを使用すると、カットオフ ポイントを調整し、グラフとパラメーターへの影響、取得する関連ファイルの割合を調整する場合、および決定を検証する前に確認できます。</span><span class="sxs-lookup"><span data-stu-id="7d408-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="7d408-115">**パラメーター**: レビュー、呼び出し、次に関連するコスト パラメーター、および合計コスト パラメーターは、ケース全体のコレクションに関連するレビュー セットに関連する累積計算統計です。</span><span class="sxs-lookup"><span data-stu-id="7d408-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="7d408-116">これらのパラメーターの定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d408-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="7d408-117">**レビュー**: このカットオフに基づいて確認するファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="7d408-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="7d408-118">**呼び** 出し : レビュー セット内の関連するファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="7d408-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="7d408-119">**次に関連**: 現在レビュー セットに含されていない別の関連ファイルを確認して識別するためのコスト。</span><span class="sxs-lookup"><span data-stu-id="7d408-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="7d408-120">**合計コスト**: ケース ファイルのこの割合を確認するコスト。</span><span class="sxs-lookup"><span data-stu-id="7d408-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="7d408-121">コスト パラメーターの設定は、ケース マネージャーによって設定できます。</span><span class="sxs-lookup"><span data-stu-id="7d408-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="7d408-122">**関連性スコアによる配布**: 左の濃い灰色の表示のファイルは、カットオフ スコアの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d408-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="7d408-123">ツール ヒントには、関連性スコアと、ファイルの合計に関連するレビュー ファイル セット内のファイルの関連割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d408-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="7d408-124">展開された [詳細 **] ウィンドウ** には、詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d408-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="7d408-125">コレクション図形内のファイルには、空のファイルやネビュラス なファイルは含めされません。</span><span class="sxs-lookup"><span data-stu-id="7d408-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="7d408-126">ファミリ ファイルの図は、関連性に読み込まれ、ファミリの一部としてカウントされていないファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="7d408-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
