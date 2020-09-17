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
# <a name="reliability-insights"></a><span data-ttu-id="467ca-103">信頼性の分析情報</span><span class="sxs-lookup"><span data-stu-id="467ca-103">Reliability insights</span></span>

<span data-ttu-id="467ca-104">このビューでは、管理対象デバイスの正常性の概要が提供されます。</span><span class="sxs-lookup"><span data-stu-id="467ca-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="467ca-105">信頼性データを表示するには、[ **信頼性** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="467ca-105">To view reliability data, select the **Reliability** tab.</span></span>


![[信頼性] ウィンドウ: デバイス間の信頼性を左上に、時間の経過による信頼性を右上に、トップの問題の表を下にします。](../../media/insights_reliability.png)

<span data-ttu-id="467ca-108">「 **Devices** による信頼性」セクションでは、過去14日間にわたる展開の迅速な正常性の概要を提供します。これにより、"正常" と見なされているデバイスの割合と前回報告されたエラー以降に監視された平均時間を報告します。</span><span class="sxs-lookup"><span data-stu-id="467ca-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="467ca-109">右上の [時間] グラフの **信頼性** は、重大なエラーが発生したデバイスの数と、時間の経過とともに観測された重大なエラーの合計数を報告します。</span><span class="sxs-lookup"><span data-stu-id="467ca-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="467ca-110">「 **上位の問題** 」セクションでは、管理対象デバイスの少なくとも5% に影響する特定の問題を検出しました。</span><span class="sxs-lookup"><span data-stu-id="467ca-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="467ca-111">報告される詳細情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="467ca-111">Reported details include:</span></span>

- <span data-ttu-id="467ca-112">問題の種類</span><span class="sxs-lookup"><span data-stu-id="467ca-112">The type of issue</span></span>
    - <span data-ttu-id="467ca-113">アプリケーションがクラッシュし、アプリが動作しなくなったか、アプリケーションが予期せず停止する</span><span class="sxs-lookup"><span data-stu-id="467ca-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="467ca-114">アプリケーションがハングし、アプリケーションが入力への応答を停止する</span><span class="sxs-lookup"><span data-stu-id="467ca-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="467ca-115">重大なエラー。 Windows が回復できない問題が発生したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="467ca-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="467ca-116">同じ問題によって影響を受けるデバイスの数</span><span class="sxs-lookup"><span data-stu-id="467ca-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="467ca-117">番号が表す管理対象デバイスの割合</span><span class="sxs-lookup"><span data-stu-id="467ca-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="467ca-118">特定の問題の発生回数の合計</span><span class="sxs-lookup"><span data-stu-id="467ca-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="467ca-119">問題のソースとして表示されるソフトウェアコンポーネント</span><span class="sxs-lookup"><span data-stu-id="467ca-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="467ca-120">検出された問題のカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="467ca-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="467ca-121">ブラウザー (エッジ、クロム、IE)</span><span class="sxs-lookup"><span data-stu-id="467ca-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="467ca-122">Unknown (Microsoft 以外のコンポーネント)</span><span class="sxs-lookup"><span data-stu-id="467ca-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="467ca-123">ドライバー (オーディオ、グラフィックス、またはその他のドライバー)</span><span class="sxs-lookup"><span data-stu-id="467ca-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="467ca-124">生産性 (余裕期間、G スイート、Microsoft Office およびそのアドオンまたは拡張機能、Teams)</span><span class="sxs-lookup"><span data-stu-id="467ca-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="467ca-125">メディア (画像、音楽、ビデオアプリ)</span><span class="sxs-lookup"><span data-stu-id="467ca-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="467ca-126">セキュリティ (Windows セキュリティコンポーネント)</span><span class="sxs-lookup"><span data-stu-id="467ca-126">Security (Windows security components)</span></span>
- <span data-ttu-id="467ca-127">Microsoft Managed Desktop 操作の現在の状態は、この問題の調査と remediates</span><span class="sxs-lookup"><span data-stu-id="467ca-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

