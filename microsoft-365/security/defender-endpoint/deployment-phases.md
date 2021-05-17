---
title: 展開フェーズ
description: エンドポイントを準備、セットアップ、オンボーディングして、そのサービスに Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: 展開、準備、セットアップ、オンボード、フェーズ、展開、展開、導入、構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165167"
---
# <a name="deployment-phases"></a><span data-ttu-id="4ac4c-104">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="4ac4c-104">Deployment phases</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ac4c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4ac4c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4ac4c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4ac4c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4ac4c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ac4c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4ac4c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="4ac4c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4ac4c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="4ac4c-110">Microsoft Defender for Endpoint を展開して、企業が予防保護、侵害後の検出、自動調査、および対応を活用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-110">Learn how to deploy Microsoft Defender for Endpoint so that your enterprise can take advantage of preventative protection, post-breach detection, automated investigation, and response.</span></span> 


<span data-ttu-id="4ac4c-111">このガイドは、関係者間で作業して環境を準備し、評価から有意義なパイロット、完全な展開に移行する方法でデバイスをオンボードするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-111">This guide helps you work across stakeholders to prepare your environment and then onboard devices in a methodical way, moving from evaluation, to a meaningful pilot, to full deployment.</span></span>

<span data-ttu-id="4ac4c-112">各セクションは、このソリューションの個別の記事に対応します。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-112">Each section corresponds to a separate article in this solution.</span></span>

![表の詳細を含む展開フェーズのイメージ](images/deployment-guide-phases.png)


![展開フェーズの概要: 準備、セットアップ、オンボード](images/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="4ac4c-115">段階</span><span class="sxs-lookup"><span data-stu-id="4ac4c-115">Phase</span></span> | <span data-ttu-id="4ac4c-116">説明</span><span class="sxs-lookup"><span data-stu-id="4ac4c-116">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="4ac4c-117">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="4ac4c-117">Phase 1: Prepare</span></span>](prepare-deployment.md)| <span data-ttu-id="4ac4c-118">利害関係者の承認、環境に関する考慮事項、アクセス許可、機能の導入順序など、Defender for Endpoint を展開する際に考慮する必要がある事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-118">Learn about what you need to consider when deploying Defender for Endpoint such as stakeholder approvals, environment considerations, access permissions, and adoption order of capabilities.</span></span> 
| [<span data-ttu-id="4ac4c-119">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="4ac4c-119">Phase 2: Setup</span></span>](production-deployment.md)|  <span data-ttu-id="4ac4c-120">ライセンスの検証、セットアップ ウィザードの完了、ネットワーク構成など、ポータルにアクセスするために必要な最初の手順に関するガイダンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-120">Get guidance on the initial steps you need to take so that you can access the portal such as validating licensing, completing the setup wizard, and network configuration.</span></span> 
| [<span data-ttu-id="4ac4c-121">フェーズ 3: オンボード</span><span class="sxs-lookup"><span data-stu-id="4ac4c-121">Phase 3: Onboard</span></span>](onboarding.md) | <span data-ttu-id="4ac4c-122">展開リングを使用する方法、エンドポイントの種類に基づいてサポートされるオンボーディング ツール、および使用可能な機能の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-122">Learn how to make use of deployment rings, supported onboarding tools based on the type of endpoint, and configuring available capabilities.</span></span> 


<span data-ttu-id="4ac4c-123">このガイドを完了すると、適切なアクセス許可を使用してセットアップされ、エンドポイントがオンボードされ、センサー データがサービスに報告され、次世代の保護や攻撃表面の縮小などの機能が実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-123">After you've completed this guide, you'll be setup with the right access permissions, your endpoints will be onboarded and reporting sensor data to the service, and capabilities such as next-generation protection and attack surface reduction will be in place.</span></span>



<span data-ttu-id="4ac4c-124">「展開の計画」のガイダンスで説明されている環境アーキテクチャと展開方法に[](deployment-strategy.md)関係なく、このガイドでは、オンボーディング エンドポイントのサポートを行います。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-124">Regardless of the environment architecture and method of deployment you choose outlined in the [Plan deployment](deployment-strategy.md) guidance, this guide is going to support you in onboarding endpoints.</span></span> 








## <a name="key-capabilities"></a><span data-ttu-id="4ac4c-125">主な機能</span><span class="sxs-lookup"><span data-stu-id="4ac4c-125">Key capabilities</span></span>

<span data-ttu-id="4ac4c-126">Microsoft Defender for Endpoint には多くの機能が備え付けられますが、この展開ガイドの主な目的は、デバイスのオンボーディングを開始する方法です。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-126">While Microsoft Defender for Endpoint provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="4ac4c-127">オンボーディングに加えて、このガイダンスでは、次の機能を使用して開始できます。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-127">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>



<span data-ttu-id="4ac4c-128">機能</span><span class="sxs-lookup"><span data-stu-id="4ac4c-128">Capability</span></span> | <span data-ttu-id="4ac4c-129">説明</span><span class="sxs-lookup"><span data-stu-id="4ac4c-129">Description</span></span> 
:---|:---
<span data-ttu-id="4ac4c-130">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="4ac4c-130">Endpoint detection and response</span></span> | <span data-ttu-id="4ac4c-131">エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応するために配置されます。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-131">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span>
<span data-ttu-id="4ac4c-132">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="4ac4c-132">Next-generation protection</span></span> | <span data-ttu-id="4ac4c-133">Microsoft Defender for Endpoint は、ネットワークのセキュリティ境界をさらに強化するために、すべての種類の新しい脅威をキャッチするように設計された次世代の保護を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-133">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>
<span data-ttu-id="4ac4c-134">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="4ac4c-134">Attack surface reduction</span></span> |  <span data-ttu-id="4ac4c-135">スタック内の防御の最初の行を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-135">Provide the first line of defense in the stack.</span></span> <span data-ttu-id="4ac4c-136">構成設定が適切に設定され、悪用の軽減手法が適用されていることを確認することで、これらの一連の機能は攻撃と悪用に抵抗します。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-136">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

<span data-ttu-id="4ac4c-137">これらすべての機能は、Microsoft Defender for Endpoint ライセンスホルダーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-137">All these capabilities are available for Microsoft Defender for Endpoint license holders.</span></span> <span data-ttu-id="4ac4c-138">詳細については、「ライセンス要件 [」を参照してください](minimum-requirements.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-138">For more information, see [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

## <a name="scope"></a><span data-ttu-id="4ac4c-139">範囲</span><span class="sxs-lookup"><span data-stu-id="4ac4c-139">Scope</span></span>

### <a name="in-scope"></a><span data-ttu-id="4ac4c-140">スコープ内</span><span class="sxs-lookup"><span data-stu-id="4ac4c-140">In scope</span></span>

-   <span data-ttu-id="4ac4c-141">サービスへのMicrosoft エンドポイント マネージャーとMicrosoft エンドポイント マネージャーの使用と機能の構成</span><span class="sxs-lookup"><span data-stu-id="4ac4c-141">Use of Microsoft Endpoint Manager and Microsoft Endpoint Manager to onboard endpoints into the service and configure capabilities</span></span>

-   <span data-ttu-id="4ac4c-142">Defender for Endpoint エンドポイントの検出と応答 (EDR) 機能の有効化</span><span class="sxs-lookup"><span data-stu-id="4ac4c-142">Enabling Defender for Endpoint endpoint detection and response (EDR)  capabilities</span></span>

-   <span data-ttu-id="4ac4c-143">Defender for Endpoint Endpoint Protection platform (EPP) 機能の有効化</span><span class="sxs-lookup"><span data-stu-id="4ac4c-143">Enabling Defender for Endpoint endpoint protection platform (EPP) capabilities</span></span>

    -   <span data-ttu-id="4ac4c-144">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="4ac4c-144">Next-generation protection</span></span>

    -   <span data-ttu-id="4ac4c-145">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="4ac4c-145">Attack surface reduction</span></span>


### <a name="out-of-scope"></a><span data-ttu-id="4ac4c-146">対象外</span><span class="sxs-lookup"><span data-stu-id="4ac4c-146">Out of scope</span></span>

<span data-ttu-id="4ac4c-147">以下は、この展開ガイドの範囲を外しています。</span><span class="sxs-lookup"><span data-stu-id="4ac4c-147">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="4ac4c-148">Defender for Endpoint と統合される可能性のあるサード パーティ製ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="4ac4c-148">Configuration of third-party solutions that might integrate with Defender for Endpoint</span></span>

-   <span data-ttu-id="4ac4c-149">実稼働環境での侵入テスト</span><span class="sxs-lookup"><span data-stu-id="4ac4c-149">Penetration testing in production environment</span></span>




## <a name="see-also"></a><span data-ttu-id="4ac4c-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ac4c-150">See also</span></span>
- [<span data-ttu-id="4ac4c-151">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="4ac4c-151">Phase 1: Prepare</span></span>](prepare-deployment.md)
- [<span data-ttu-id="4ac4c-152">フェーズ 2: 設定</span><span class="sxs-lookup"><span data-stu-id="4ac4c-152">Phase 2: Set up</span></span>](production-deployment.md)
- [<span data-ttu-id="4ac4c-153">フェーズ 3: オンボード</span><span class="sxs-lookup"><span data-stu-id="4ac4c-153">Phase 3: Onboard</span></span>](onboarding.md)
- [<span data-ttu-id="4ac4c-154">展開を計画する</span><span class="sxs-lookup"><span data-stu-id="4ac4c-154">Plan deployment</span></span>](deployment-strategy.md)