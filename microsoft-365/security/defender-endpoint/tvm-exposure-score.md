---
title: ユーザーの露出スコア脅威と脆弱性の管理
description: この脅威と脆弱性の管理は、組織がサイバーセキュリティの脅威に対してどのように脆弱かを反映しています。
keywords: 露出スコア、Microsoft Defender for Endpoint 露出スコア、Microsoft Defender for Endpoint tvm 露出スコア、組織の露出スコア、tvm 組織の露出スコア、脅威と脆弱性の管理、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcea240fe1dc0ce97a2800391320b04c39c84336
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934107"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="e4786-104">露出スコア - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="e4786-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e4786-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e4786-105">**Applies to:**</span></span>

- [<span data-ttu-id="e4786-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e4786-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e4786-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="e4786-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e4786-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4786-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e4786-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="e4786-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e4786-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e4786-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="e4786-111">露出スコアは、ユーザーの脅威と脆弱性の管理[ダッシュボード](tvm-dashboard-insights.md)に表示Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="e4786-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="e4786-112">これは、組織がサイバーセキュリティの脅威に対してどのように脆弱かを反映しています。</span><span class="sxs-lookup"><span data-stu-id="e4786-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="e4786-113">露出スコアが低いということは、デバイスが悪用の影響を受けやすいという意味です。</span><span class="sxs-lookup"><span data-stu-id="e4786-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="e4786-114">組織のセキュリティの状態に関する高レベルのテイクアウトを迅速に理解し、特定します。</span><span class="sxs-lookup"><span data-stu-id="e4786-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="e4786-115">現在の状態を改善するために調査またはアクションが必要な領域を検出して対応します。</span><span class="sxs-lookup"><span data-stu-id="e4786-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="e4786-116">セキュリティの取り組みの影響について、ピアや経営陣とコミュニケーションを取る。</span><span class="sxs-lookup"><span data-stu-id="e4786-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="e4786-117">このカードは、時間の流れによる露出スコアの傾向を高レベルで表示します。</span><span class="sxs-lookup"><span data-stu-id="e4786-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="e4786-118">グラフ内のスパイクは、サイバーセキュリティの脅威に対する高い暴露を視覚的に示し、さらに調査することができます。</span><span class="sxs-lookup"><span data-stu-id="e4786-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![露出スコア カード](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="e4786-120">メカニズム</span><span class="sxs-lookup"><span data-stu-id="e4786-120">How it works</span></span>

<span data-ttu-id="e4786-121">露出スコアは、次のレベルに分割されます。</span><span class="sxs-lookup"><span data-stu-id="e4786-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="e4786-122">0 ~ 29: 低露出スコア</span><span class="sxs-lookup"><span data-stu-id="e4786-122">0–29: low exposure score</span></span>
- <span data-ttu-id="e4786-123">30 ~ 69: 中程度の露出スコア</span><span class="sxs-lookup"><span data-stu-id="e4786-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="e4786-124">70 ~ 100: 高い露出スコア</span><span class="sxs-lookup"><span data-stu-id="e4786-124">70–100: high exposure score</span></span>

<span data-ttu-id="e4786-125">優先度の高いセキュリティ推奨事項に基づいて問題を修復[](tvm-security-recommendation.md)し、露出スコアを下ろします。</span><span class="sxs-lookup"><span data-stu-id="e4786-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="e4786-126">各ソフトウェアには、推奨事項に変換され、組織のリスクに基づいて優先順位が付けられた弱点があります。</span><span class="sxs-lookup"><span data-stu-id="e4786-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="e4786-127">脅威と脆弱性の暴露を減らす</span><span class="sxs-lookup"><span data-stu-id="e4786-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="e4786-128">セキュリティに関する推奨事項を修正することで、脅威と脆弱性の暴露 [を削減します](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="e4786-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="e4786-129">最も重要なセキュリティ推奨事項を修復して、露出スコアに最も大きな影響を与えます。これは、脅威と脆弱性の管理[ダッシュボードで確認できます](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="e4786-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4786-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4786-130">Related topics</span></span>

- [<span data-ttu-id="e4786-131">脅威と脆弱性の管理概要</span><span class="sxs-lookup"><span data-stu-id="e4786-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e4786-132">デバイス向けの Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="e4786-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="e4786-133">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="e4786-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="e4786-134">イベントのタイムライン</span><span class="sxs-lookup"><span data-stu-id="e4786-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
