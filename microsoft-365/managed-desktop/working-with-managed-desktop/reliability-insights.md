---
title: 信頼性の分析情報
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950344"
---
# <a name="reliability-insights"></a><span data-ttu-id="c751e-103">信頼性の分析情報</span><span class="sxs-lookup"><span data-stu-id="c751e-103">Reliability insights</span></span>

<span data-ttu-id="c751e-104">このビューには、管理対象デバイスの正常性の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c751e-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="c751e-105">信頼性データを表示するには、[信頼性] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c751e-105">To view reliability data, select the **Reliability** tab.</span></span>


![[信頼性] ウィンドウ: 左上のデバイス間の信頼性、右上の時間のグラフの信頼性、下部の上の問題の表。](../../media/insights_reliability.png)

<span data-ttu-id="c751e-108">[ **デバイス** 間の信頼性] セクションでは、"正常" と見なされるデバイスの割合と、前回報告されたエラー以降に観察された平均時間を報告することで、過去 14 日間の展開の正常性の概要を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="c751e-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="c751e-109">右側 **の [時間の間の** 信頼性] グラフは、重大なエラーが発生したデバイスの数と、時間の間に観測された重大なエラーの総数を報告します。</span><span class="sxs-lookup"><span data-stu-id="c751e-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="c751e-110">[ **上位の問題]** セクションでは、管理対象デバイスの少なくとも 5% に影響する特定の検出された問題について詳しくは説明します。</span><span class="sxs-lookup"><span data-stu-id="c751e-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="c751e-111">報告された詳細には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c751e-111">Reported details include:</span></span>

- <span data-ttu-id="c751e-112">問題の種類</span><span class="sxs-lookup"><span data-stu-id="c751e-112">The type of issue</span></span>
    - <span data-ttu-id="c751e-113">アプリケーションがクラッシュし、アプリが機能を停止するか、予期せず停止する</span><span class="sxs-lookup"><span data-stu-id="c751e-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="c751e-114">アプリケーションがハングし、アプリケーションが入力への応答を停止する</span><span class="sxs-lookup"><span data-stu-id="c751e-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="c751e-115">重大なエラー(Windows で回復できない問題が発生した場合に発生する)</span><span class="sxs-lookup"><span data-stu-id="c751e-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="c751e-116">同じ問題の影響を受けるデバイスの数</span><span class="sxs-lookup"><span data-stu-id="c751e-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="c751e-117">数が表す管理対象デバイスの割合</span><span class="sxs-lookup"><span data-stu-id="c751e-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="c751e-118">特定の問題の発生回数の合計</span><span class="sxs-lookup"><span data-stu-id="c751e-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="c751e-119">問題の発生源と思えるソフトウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c751e-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="c751e-120">検出された問題のカテゴリ:</span><span class="sxs-lookup"><span data-stu-id="c751e-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="c751e-121">ブラウザー (エッジ、クロム、IE)</span><span class="sxs-lookup"><span data-stu-id="c751e-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="c751e-122">不明 (Microsoft 以外のコンポーネント)</span><span class="sxs-lookup"><span data-stu-id="c751e-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="c751e-123">ドライバー (オーディオ、グラフィックス、その他のドライバー)</span><span class="sxs-lookup"><span data-stu-id="c751e-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="c751e-124">生産性 (Slack、G-Suites、Microsoft Officeアドオンまたは拡張機能 Teams)</span><span class="sxs-lookup"><span data-stu-id="c751e-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="c751e-125">メディア (画像、音楽、またはビデオ アプリ)</span><span class="sxs-lookup"><span data-stu-id="c751e-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="c751e-126">セキュリティ (Windows セキュリティ コンポーネント)</span><span class="sxs-lookup"><span data-stu-id="c751e-126">Security (Windows security components)</span></span>
- <span data-ttu-id="c751e-127">Microsoft Managed Desktop Operations が問題を調査および修復する現在の状態</span><span class="sxs-lookup"><span data-stu-id="c751e-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

