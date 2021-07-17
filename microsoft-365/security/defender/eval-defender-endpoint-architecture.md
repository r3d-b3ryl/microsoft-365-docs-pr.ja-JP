---
title: Microsoft Defender for Endpoint アーキテクチャの要件と主な概念を確認する
description: テスト ラボまたはパイロット環境を構築する前Microsoft 365 Defenderの Microsoft Defender for Endpoint の技術図は、Microsoft 365の ID を理解するのに役立ちます。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458127"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="0f619-103">Microsoft Defender for Endpoint アーキテクチャの要件と主な概念を確認する</span><span class="sxs-lookup"><span data-stu-id="0f619-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="0f619-104">**適用対象: Microsoft 365 Defender**</span><span class="sxs-lookup"><span data-stu-id="0f619-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="0f619-105">この記事では、Microsoft Defender for Endpoint 環境の評価をセットアップするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0f619-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="0f619-106">このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-endpoint-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0f619-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="0f619-107">Microsoft Defender for Endpoint を有効にする前に、アーキテクチャを理解し、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f619-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="0f619-108">アーキテクチャを理解する</span><span class="sxs-lookup"><span data-stu-id="0f619-108">Understand the architecture</span></span>

<span data-ttu-id="0f619-109">次の図は、Microsoft Defender for Endpoint アーキテクチャと統合を示しています。</span><span class="sxs-lookup"><span data-stu-id="0f619-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![Defender 評価環境に Microsoft Defender Office追加する手順](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="0f619-111">次の表に、図を示します。</span><span class="sxs-lookup"><span data-stu-id="0f619-111">The following table describes the illustration.</span></span>

<span data-ttu-id="0f619-112">コールアウト</span><span class="sxs-lookup"><span data-stu-id="0f619-112">Call-out</span></span> | <span data-ttu-id="0f619-113">説明</span><span class="sxs-lookup"><span data-stu-id="0f619-113">Description</span></span>
:---|:---|
<span data-ttu-id="0f619-114">1</span><span class="sxs-lookup"><span data-stu-id="0f619-114">1</span></span> | <span data-ttu-id="0f619-115">デバイスは、サポートされている管理ツールのいずれかを介してオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="0f619-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="0f619-116">2</span><span class="sxs-lookup"><span data-stu-id="0f619-116">2</span></span> | <span data-ttu-id="0f619-117">ボード上のデバイスは、Microsoft Defender for Endpoint シグナル データを提供して応答します。</span><span class="sxs-lookup"><span data-stu-id="0f619-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="0f619-118">3</span><span class="sxs-lookup"><span data-stu-id="0f619-118">3</span></span> | <span data-ttu-id="0f619-119">管理対象デバイスは、デバイスに参加または登録Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="0f619-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="0f619-120">4 </span><span class="sxs-lookup"><span data-stu-id="0f619-120">4</span></span> | <span data-ttu-id="0f619-121">ドメインに参加しているWindows 10デバイスは、Azure Active Directoryを使用Azure Active Directory Connect。</span><span class="sxs-lookup"><span data-stu-id="0f619-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="0f619-122">5 </span><span class="sxs-lookup"><span data-stu-id="0f619-122">5</span></span> | <span data-ttu-id="0f619-123">Microsoft Defender for Endpoint のアラート、調査、および応答は、Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="0f619-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="0f619-124">主要な概念を理解する</span><span class="sxs-lookup"><span data-stu-id="0f619-124">Understand key concepts</span></span>

<span data-ttu-id="0f619-125">次の表に、Microsoft Defender for Endpoint の評価、構成、展開を行う際に重要な重要な概念を示します。</span><span class="sxs-lookup"><span data-stu-id="0f619-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="0f619-126">概念</span><span class="sxs-lookup"><span data-stu-id="0f619-126">Concept</span></span> | <span data-ttu-id="0f619-127">説明</span><span class="sxs-lookup"><span data-stu-id="0f619-127">Description</span></span> | <span data-ttu-id="0f619-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0f619-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="0f619-129">管理ポータル</span><span class="sxs-lookup"><span data-stu-id="0f619-129">Administration Portal</span></span> | <span data-ttu-id="0f619-130">Microsoft 365 Defender、高度な永続的な脅威アクティビティやデータ侵害の可能性に関するアラートの監視と対応を支援するポータルを提供します。</span><span class="sxs-lookup"><span data-stu-id="0f619-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="0f619-131">Microsoft Defender for Endpoint ポータルの概要</span><span class="sxs-lookup"><span data-stu-id="0f619-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="0f619-132">攻撃表面の縮小</span><span class="sxs-lookup"><span data-stu-id="0f619-132">Attack Surface Reduction</span></span> | <span data-ttu-id="0f619-133">組織がサイバー脅威や攻撃に対して脆弱な場所を最小限に抑えることによって、攻撃の表面を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f619-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="0f619-134">攻撃面の減少の概要</span><span class="sxs-lookup"><span data-stu-id="0f619-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="0f619-135">エンドポイントの検出と応答</span><span class="sxs-lookup"><span data-stu-id="0f619-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="0f619-136">エンドポイントの検出および応答機能は、ほぼリアルタイムでアクション可能な高度な攻撃検出を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f619-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="0f619-137">エンドポイントの検出および応答機能の概要</span><span class="sxs-lookup"><span data-stu-id="0f619-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="0f619-138">動作のブロックと格納</span><span class="sxs-lookup"><span data-stu-id="0f619-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="0f619-139">動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作とプロセス ツリーに基づいて、脅威を特定して停止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f619-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="0f619-140">動作ブロックと封じ込め</span><span class="sxs-lookup"><span data-stu-id="0f619-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="0f619-141">自動調査と対応</span><span class="sxs-lookup"><span data-stu-id="0f619-141">Automated Investigation and Response</span></span> | <span data-ttu-id="0f619-142">自動調査では、セキュリティ アナリストが使用するプロセスに基づいてさまざまな検査アルゴリズムを使用し、アラートを調べ、侵害を解決するために直ちに対応するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="0f619-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="0f619-143">自動調査を使用して脅威を調査および修復する</span><span class="sxs-lookup"><span data-stu-id="0f619-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="0f619-144">高度な追求</span><span class="sxs-lookup"><span data-stu-id="0f619-144">Advanced Hunting</span></span> | <span data-ttu-id="0f619-145">高度な検索はクエリベースの脅威ハンティング ツールで、最大 30 日間の生データを調査して、ネットワーク内のイベントを積極的に検査して脅威インジケーターとエンティティを特定できます。</span><span class="sxs-lookup"><span data-stu-id="0f619-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="0f619-146">高度な検索の概要</span><span class="sxs-lookup"><span data-stu-id="0f619-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="0f619-147">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="0f619-147">Threat Analytics</span></span> | <span data-ttu-id="0f619-148">脅威分析は、最も関連性の高い脅威をカバーする Microsoft の専門家のセキュリティ研究者からの一連のレポートです。</span><span class="sxs-lookup"><span data-stu-id="0f619-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="0f619-149">新しい脅威を追跡して対応する</span><span class="sxs-lookup"><span data-stu-id="0f619-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="0f619-150">Microsoft Defender for Endpoint に含まれる機能の詳細については、「What [is Microsoft Defender for Endpoint」を参照してください](/defender-endpoint/microsoft-defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="0f619-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="0f619-151">SIEM 統合</span><span class="sxs-lookup"><span data-stu-id="0f619-151">SIEM integration</span></span>

<span data-ttu-id="0f619-152">Microsoft Defender for Endpoint と Azure Sentinel を統合して、組織全体のセキュリティ イベントをより包括的に分析し、効果的かつ迅速な対応を行うプレイブックを構築できます。</span><span class="sxs-lookup"><span data-stu-id="0f619-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="0f619-153">Microsoft Defender for Endpoint は、他のセキュリティ情報およびイベント管理 (SIEM) ソリューションにも統合できます。</span><span class="sxs-lookup"><span data-stu-id="0f619-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="0f619-154">詳細については [、「Enable SIEM integration in Microsoft Defender for Endpoint」を参照してください](/defender-endpoint/enable-siem-integration)。</span><span class="sxs-lookup"><span data-stu-id="0f619-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="0f619-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="0f619-155">Next steps</span></span>
[<span data-ttu-id="0f619-156">評価を有効にする</span><span class="sxs-lookup"><span data-stu-id="0f619-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="0f619-157">エンドポイントの Microsoft [Defender の評価の概要に戻る](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0f619-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="0f619-158">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0f619-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>