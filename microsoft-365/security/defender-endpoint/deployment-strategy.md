---
title: Microsoft Defender for Endpoint の展開を計画する
description: 環境に最適な Microsoft Defender for Endpoint 展開戦略を選択する
keywords: 展開、計画、展開戦略、クラウド ネイティブ、管理、prem、評価、オンボーディング、ローカル、グループ ポリシー、gp、エンドポイント マネージャー、mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163577"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="b0b81-104">Microsoft Defender for Endpoint の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="b0b81-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0b81-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b0b81-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0b81-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b0b81-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b0b81-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0b81-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b0b81-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b0b81-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b0b81-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b0b81-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="b0b81-110">Microsoft Defender for Endpoint の展開を計画して、スイート内のセキュリティ機能を最大限に活用し、企業をサイバー脅威からより良く保護できます。</span><span class="sxs-lookup"><span data-stu-id="b0b81-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="b0b81-111">このソリューションでは、環境アーキテクチャを特定する方法、ニーズに最も適した展開ツールの種類を選択する方法、および機能を構成する方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b0b81-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![展開フローのイメージ](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="b0b81-113">手順 1: アーキテクチャを識別する</span><span class="sxs-lookup"><span data-stu-id="b0b81-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="b0b81-114">すべてのエンタープライズ環境は一意なので、サービスの展開方法を柔軟に選択するためのオプションがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="b0b81-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="b0b81-115">環境に応じて、一部のツールは特定のアーキテクチャに適しています。</span><span class="sxs-lookup"><span data-stu-id="b0b81-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="b0b81-116">次の資料を使用して、組織に最適なエンドポイント向け Defender アーキテクチャを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0b81-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="b0b81-117">アイテム</span><span class="sxs-lookup"><span data-stu-id="b0b81-117">Item</span></span> | <span data-ttu-id="b0b81-118">説明</span><span class="sxs-lookup"><span data-stu-id="b0b81-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="b0b81-119">[![Defender for Endpoint 展開戦略のサム イメージ](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="b0b81-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="b0b81-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="b0b81-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="b0b81-121">アーキテクチャ教材は、次のアーキテクチャの展開を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b0b81-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="b0b81-122">クラウド-ネイティブ</span><span class="sxs-lookup"><span data-stu-id="b0b81-122">Cloud-native</span></span> </li><li> <span data-ttu-id="b0b81-123">共同管理</span><span class="sxs-lookup"><span data-stu-id="b0b81-123">Co-management</span></span> </li><li> <span data-ttu-id="b0b81-124">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="b0b81-124">On-premise</span></span></li><li><span data-ttu-id="b0b81-125">評価とローカル オンボード</span><span class="sxs-lookup"><span data-stu-id="b0b81-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="b0b81-126">手順 2: 展開方法の選択</span><span class="sxs-lookup"><span data-stu-id="b0b81-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="b0b81-127">Defender for Endpoint は、サービスにオンボードできるさまざまなエンドポイントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b0b81-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="b0b81-128">次の表に、サポートされているエンドポイントと、適切に展開を計画するために使用できる対応する展開ツールの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b0b81-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="b0b81-129">Endpoint</span><span class="sxs-lookup"><span data-stu-id="b0b81-129">Endpoint</span></span>     | <span data-ttu-id="b0b81-130">展開ツール</span><span class="sxs-lookup"><span data-stu-id="b0b81-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="b0b81-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b0b81-131">**Windows**</span></span>  |  [<span data-ttu-id="b0b81-132">ローカル スクリプト (最大 10 台のデバイス)</span><span class="sxs-lookup"><span data-stu-id="b0b81-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="b0b81-133">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="b0b81-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="b0b81-134">Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー</span><span class="sxs-lookup"><span data-stu-id="b0b81-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="b0b81-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b0b81-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="b0b81-136">VDI スクリプト</span><span class="sxs-lookup"><span data-stu-id="b0b81-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="b0b81-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="b0b81-137">**macOS**</span></span>    | [<span data-ttu-id="b0b81-138">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="b0b81-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="b0b81-139">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="b0b81-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="b0b81-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="b0b81-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="b0b81-141">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="b0b81-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="b0b81-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="b0b81-142">**Linux Server**</span></span> | [<span data-ttu-id="b0b81-143">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="b0b81-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="b0b81-144">Puppet</span><span class="sxs-lookup"><span data-stu-id="b0b81-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="b0b81-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="b0b81-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="b0b81-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="b0b81-146">**iOS**</span></span>      | [<span data-ttu-id="b0b81-147">アプリベース</span><span class="sxs-lookup"><span data-stu-id="b0b81-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="b0b81-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="b0b81-148">**Android**</span></span>  | [<span data-ttu-id="b0b81-149">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="b0b81-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="b0b81-150">手順 3: 機能を構成する</span><span class="sxs-lookup"><span data-stu-id="b0b81-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="b0b81-151">エンドポイントのオンボード後、Defender for Endpoint のセキュリティ機能を構成して、スイートで使用可能な堅牢なセキュリティ保護を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="b0b81-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="b0b81-152">機能には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b0b81-152">Capabilities include:</span></span>

- <span data-ttu-id="b0b81-153">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="b0b81-153">Endpoint detection and response</span></span>
- <span data-ttu-id="b0b81-154">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="b0b81-154">Next-generation protection</span></span>
- <span data-ttu-id="b0b81-155">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="b0b81-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="b0b81-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0b81-156">Related topics</span></span>
- [<span data-ttu-id="b0b81-157">展開フェーズ</span><span class="sxs-lookup"><span data-stu-id="b0b81-157">Deployment phases</span></span>](deployment-phases.md)
