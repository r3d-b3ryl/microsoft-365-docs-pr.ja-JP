---
title: 信頼性の分析情報
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f830e01d54aef9065727971533633f8e63bc1214
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257035"
---
# <a name="reliability-insights"></a><span data-ttu-id="bc01c-103">信頼性の分析情報</span><span class="sxs-lookup"><span data-stu-id="bc01c-103">Reliability insights</span></span>

<span data-ttu-id="bc01c-104">このビューでは、管理対象デバイスの正常性の概要が提供されます。</span><span class="sxs-lookup"><span data-stu-id="bc01c-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="bc01c-105">信頼性データを表示するには、[**信頼性**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="bc01c-105">To view reliability data, select the **Reliability** tab.</span></span>


![信頼性ウィンドウ](images/insights_reliability.png)

<span data-ttu-id="bc01c-107">「 **Devices**による信頼性」セクションでは、過去14日間にわたる展開の迅速な正常性の概要を提供します。これにより、"正常" と見なされているデバイスの割合と前回報告されたエラー以降に監視された平均時間を報告します。</span><span class="sxs-lookup"><span data-stu-id="bc01c-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="bc01c-108">右上の [時間] グラフの**信頼性**は、重大なエラーが発生したデバイスの数と、時間の経過とともに観測された重大なエラーの合計数を報告します。</span><span class="sxs-lookup"><span data-stu-id="bc01c-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="bc01c-109">「**上位の問題**」セクションでは、管理対象デバイスの少なくとも5% に影響する特定の問題を検出しました。</span><span class="sxs-lookup"><span data-stu-id="bc01c-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="bc01c-110">報告される詳細情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bc01c-110">Reported details include:</span></span>

- <span data-ttu-id="bc01c-111">問題の種類</span><span class="sxs-lookup"><span data-stu-id="bc01c-111">The type of issue</span></span>
    - <span data-ttu-id="bc01c-112">アプリケーションがクラッシュし、アプリが動作しなくなったか、アプリケーションが予期せず停止する</span><span class="sxs-lookup"><span data-stu-id="bc01c-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="bc01c-113">アプリケーションがハングし、アプリケーションが入力への応答を停止する</span><span class="sxs-lookup"><span data-stu-id="bc01c-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="bc01c-114">重大なエラー。 Windows が回復できない問題が発生したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="bc01c-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="bc01c-115">同じ問題によって影響を受けるデバイスの数</span><span class="sxs-lookup"><span data-stu-id="bc01c-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="bc01c-116">番号が表す管理対象デバイスの割合</span><span class="sxs-lookup"><span data-stu-id="bc01c-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="bc01c-117">特定の問題の出現回数の合計</span><span class="sxs-lookup"><span data-stu-id="bc01c-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="bc01c-118">問題のソースとして表示されるソフトウェアコンポーネント</span><span class="sxs-lookup"><span data-stu-id="bc01c-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="bc01c-119">Microsoft Managed Desktop 操作の現在の状態は、この問題の調査と remediates</span><span class="sxs-lookup"><span data-stu-id="bc01c-119">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

