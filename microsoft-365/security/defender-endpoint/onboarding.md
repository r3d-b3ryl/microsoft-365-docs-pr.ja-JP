---
title: Microsoft Defender ATP サービスにオンボードする
description: エンドポイントを Microsoft Defender ATP サービスにオンボードする方法について説明します。
keywords: ''
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
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186931"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="a9a98-103">Microsoft Defender for Endpoint サービスにオンボードする</span><span class="sxs-lookup"><span data-stu-id="a9a98-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9a98-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a9a98-104">**Applies to:**</span></span>
- [<span data-ttu-id="a9a98-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a9a98-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9a98-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9a98-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a9a98-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a9a98-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a9a98-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="a9a98-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a9a98-109">Microsoft Defender for Endpoint の展開のさまざまなフェーズと、ソリューション内の機能を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9a98-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="a9a98-110">Defender for Endpoint の展開は、次の 3 フェーズプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a9a98-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="a9a98-111">[![展開フェーズ - 準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="a9a98-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="a9a98-112">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="a9a98-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="a9a98-113">[![展開フェーズ - セットアップ](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="a9a98-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="a9a98-114">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="a9a98-114">Phase 2: Setup</span></span>](production-deployment.md) | ![展開フェーズ - オンボード](images/phase-diagrams/onboard.png)<br><span data-ttu-id="a9a98-116">フェーズ 3: オンボード</span><span class="sxs-lookup"><span data-stu-id="a9a98-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="a9a98-117">*お前はここにいる!*</span><span class="sxs-lookup"><span data-stu-id="a9a98-117">*You are here!*</span></span>|

<span data-ttu-id="a9a98-118">現在、オンボーディング フェーズに入っている。</span><span class="sxs-lookup"><span data-stu-id="a9a98-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="a9a98-119">Defender for Endpoint を展開するために必要な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9a98-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="a9a98-120">手順 1: サービスにエンドポイントをオンボードする</span><span class="sxs-lookup"><span data-stu-id="a9a98-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="a9a98-121">手順 2: 機能を構成する</span><span class="sxs-lookup"><span data-stu-id="a9a98-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="a9a98-122">手順 1: サポートされている管理ツールを使用してエンドポイントをオンボードする</span><span class="sxs-lookup"><span data-stu-id="a9a98-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="a9a98-123">「 [展開の計画」](deployment-strategy.md) トピックでは、Defender for Endpoint の展開に必要な一般的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9a98-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="a9a98-124">オンボーディング プロセスの概要と、使用可能なツールと方法について詳しくは、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9a98-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="a9a98-125">アーキテクチャを特定した後、使用する展開方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9a98-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="a9a98-126">選択した展開ツールは、エンドポイントをサービスにオンボードする方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="a9a98-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="a9a98-127">オンボーディング ツールのオプション</span><span class="sxs-lookup"><span data-stu-id="a9a98-127">Onboarding tool options</span></span>

<span data-ttu-id="a9a98-128">次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。</span><span class="sxs-lookup"><span data-stu-id="a9a98-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="a9a98-129">Endpoint</span><span class="sxs-lookup"><span data-stu-id="a9a98-129">Endpoint</span></span>     | <span data-ttu-id="a9a98-130">ツール オプション</span><span class="sxs-lookup"><span data-stu-id="a9a98-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="a9a98-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="a9a98-131">**Windows**</span></span>  |  [<span data-ttu-id="a9a98-132">ローカル スクリプト (最大 10 台のデバイス)</span><span class="sxs-lookup"><span data-stu-id="a9a98-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="a9a98-133">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="a9a98-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="a9a98-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="a9a98-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="a9a98-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a9a98-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="a9a98-136">VDI スクリプト</span><span class="sxs-lookup"><span data-stu-id="a9a98-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="a9a98-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="a9a98-137">**macOS**</span></span>    | [<span data-ttu-id="a9a98-138">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="a9a98-138">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="a9a98-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a9a98-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="a9a98-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="a9a98-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="a9a98-141">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="a9a98-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="a9a98-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="a9a98-142">**Linux Server**</span></span> | [<span data-ttu-id="a9a98-143">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="a9a98-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="a9a98-144">Puppet</span><span class="sxs-lookup"><span data-stu-id="a9a98-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="a9a98-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="a9a98-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="a9a98-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="a9a98-146">**iOS**</span></span>      | [<span data-ttu-id="a9a98-147">アプリベース</span><span class="sxs-lookup"><span data-stu-id="a9a98-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="a9a98-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="a9a98-148">**Android**</span></span>  | [<span data-ttu-id="a9a98-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a9a98-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="a9a98-150">手順 2: 機能を構成する</span><span class="sxs-lookup"><span data-stu-id="a9a98-150">Step 2: Configure capabilities</span></span>
<span data-ttu-id="a9a98-151">エンドポイントのオンボード後、エンドポイントの検出と応答、次世代保護、攻撃表面の縮小など、さまざまな機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="a9a98-151">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="a9a98-152">展開の例</span><span class="sxs-lookup"><span data-stu-id="a9a98-152">Example deployments</span></span>
<span data-ttu-id="a9a98-153">この展開ガイドでは、2 つの展開ツールを使用してエンドポイントをオンボードし、機能を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9a98-153">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="a9a98-154">展開例のツールは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9a98-154">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="a9a98-155">Microsoft Endpoint Configuration Manager を使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="a9a98-155">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="a9a98-156">Microsoft Endpoint Manager を使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="a9a98-156">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="a9a98-157">上記の展開ツールを使用して、次の Defender for Endpoint 機能の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9a98-157">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="a9a98-158">エンドポイントの検出と応答の構成</span><span class="sxs-lookup"><span data-stu-id="a9a98-158">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="a9a98-159">次世代の保護構成</span><span class="sxs-lookup"><span data-stu-id="a9a98-159">Next-generation protection configuration</span></span>
- <span data-ttu-id="a9a98-160">攻撃表面の縮小構成</span><span class="sxs-lookup"><span data-stu-id="a9a98-160">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9a98-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9a98-161">Related topics</span></span>
- [<span data-ttu-id="a9a98-162">Microsoft Endpoint Configuration Manager を使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="a9a98-162">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="a9a98-163">Microsoft Endpoint Manager を使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="a9a98-163">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)