---
title: 脅威と脆弱性の管理における露出スコア
description: 脅威と脆弱性管理の暴露スコアは、組織がサイバーセキュリティの脅威に対してどのように脆弱かを反映しています。
keywords: 露出スコア、mdatp 露出スコア、mdatp tvm 露出スコア、組織の露出スコア、tvm 組織の露出スコア、脅威と脆弱性の管理、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cc7abd678d6f2d317d02c4ed2b8028e7e270b055
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068451"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="8b16f-104">露出スコア - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="8b16f-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8b16f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8b16f-105">**Applies to:**</span></span>

- [<span data-ttu-id="8b16f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8b16f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8b16f-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="8b16f-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8b16f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b16f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8b16f-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8b16f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8b16f-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="8b16f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="8b16f-111">露出スコアは、Microsoft Defender[](tvm-dashboard-insights.md)セキュリティ センターの脅威と脆弱性の管理ダッシュボードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b16f-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="8b16f-112">これは、組織がサイバーセキュリティの脅威に対してどのように脆弱かを反映しています。</span><span class="sxs-lookup"><span data-stu-id="8b16f-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="8b16f-113">露出スコアが低いということは、デバイスが悪用の影響を受けやすいという意味です。</span><span class="sxs-lookup"><span data-stu-id="8b16f-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="8b16f-114">組織のセキュリティの状態に関する高レベルのテイクアウトを迅速に理解し、特定します。</span><span class="sxs-lookup"><span data-stu-id="8b16f-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="8b16f-115">現在の状態を改善するために調査またはアクションが必要な領域を検出して対応します。</span><span class="sxs-lookup"><span data-stu-id="8b16f-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="8b16f-116">セキュリティの取り組みの影響について、ピアや経営陣とコミュニケーションを取る。</span><span class="sxs-lookup"><span data-stu-id="8b16f-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="8b16f-117">このカードは、時間の流れによる露出スコアの傾向を高レベルで表示します。</span><span class="sxs-lookup"><span data-stu-id="8b16f-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="8b16f-118">グラフ内のスパイクは、サイバーセキュリティの脅威に対する高い暴露を視覚的に示し、さらに調査することができます。</span><span class="sxs-lookup"><span data-stu-id="8b16f-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![露出スコア カード](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="8b16f-120">メカニズム</span><span class="sxs-lookup"><span data-stu-id="8b16f-120">How it works</span></span>

<span data-ttu-id="8b16f-121">露出スコアは、次のレベルに分割されます。</span><span class="sxs-lookup"><span data-stu-id="8b16f-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="8b16f-122">0 ~ 29: 低露出スコア</span><span class="sxs-lookup"><span data-stu-id="8b16f-122">0–29: low exposure score</span></span>
- <span data-ttu-id="8b16f-123">30 ~ 69: 中程度の露出スコア</span><span class="sxs-lookup"><span data-stu-id="8b16f-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="8b16f-124">70 ~ 100: 高い露出スコア</span><span class="sxs-lookup"><span data-stu-id="8b16f-124">70–100: high exposure score</span></span>

<span data-ttu-id="8b16f-125">優先度の高いセキュリティ推奨事項に基づいて問題を修復[](tvm-security-recommendation.md)し、露出スコアを下ろします。</span><span class="sxs-lookup"><span data-stu-id="8b16f-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="8b16f-126">各ソフトウェアには、推奨事項に変換され、組織のリスクに基づいて優先順位が付けられた弱点があります。</span><span class="sxs-lookup"><span data-stu-id="8b16f-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="8b16f-127">脅威と脆弱性の暴露を減らす</span><span class="sxs-lookup"><span data-stu-id="8b16f-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="8b16f-128">セキュリティに関する推奨事項を修正することで、脅威と脆弱性の暴露 [を削減します](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="8b16f-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="8b16f-129">脅威と脆弱性の管理ダッシュボードで確認できる、セキュリティに関する上位の推奨事項を修正することで、露出スコアに最も影響 [を与えます](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="8b16f-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8b16f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b16f-130">Related topics</span></span>

- [<span data-ttu-id="8b16f-131">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="8b16f-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8b16f-132">デバイスの Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="8b16f-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="8b16f-133">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="8b16f-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="8b16f-134">イベントタイムライン</span><span class="sxs-lookup"><span data-stu-id="8b16f-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
