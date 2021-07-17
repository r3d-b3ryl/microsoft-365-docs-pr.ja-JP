---
title: エンドポイント評価用のパイロット Defender
description: 試用版ラボMicrosoft 365 Defenderパイロット環境を有効にする。
keywords: Microsoft 365 Defender試し、Microsoft 365 Defender を試し、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度なハンティングを評価する
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458187"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="464de-104">パイロット MDE 評価</span><span class="sxs-lookup"><span data-stu-id="464de-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="464de-105">一般的な展開を案内する目的で、このシナリオでは、このシナリオでは、ユーザーの使用のみをMicrosoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="464de-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="464de-106">Defender for Endpoint は、他のオンボーディング ツールの使用をサポートしていますが、展開ガイドではこれらのシナリオについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="464de-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="464de-107">詳細については、「デバイスを [Microsoft Defender for Endpoint にオンボードする」を参照してください](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="464de-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="464de-108">手順 1.</span><span class="sxs-lookup"><span data-stu-id="464de-108">Step 1.</span></span> <span data-ttu-id="464de-109">ライセンスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="464de-109">Check license state</span></span>

<span data-ttu-id="464de-110">ライセンスの状態を確認し、適切にプロビジョニングされたかどうかを確認するには、管理センターまたはポータルMicrosoft Azure **できます**。</span><span class="sxs-lookup"><span data-stu-id="464de-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="464de-111">ライセンスを表示するには、Microsoft Azureポータルに **移動** し、[Microsoft Azure][セクションに移動します](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="464de-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![[Azure ライセンス] ページのイメージ](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="464de-113">または、管理センターで [課金サブスクリプション]   >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="464de-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="464de-114">画面に、すべてのプロビジョニング済みライセンスと現在の状態が表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="464de-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![課金ライセンスのイメージ](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="464de-116">手順 2.</span><span class="sxs-lookup"><span data-stu-id="464de-116">Step 2.</span></span> <span data-ttu-id="464de-117">サポートされている管理ツールを使用したオンボード エンドポイント</span><span class="sxs-lookup"><span data-stu-id="464de-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="464de-118">「 [展開の計画」](deployment-strategy.md) トピックでは、Defender for Endpoint の展開に必要な一般的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="464de-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="464de-119">オンボーディング プロセスの概要と、使用可能なツールと方法について詳しくは、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="464de-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="464de-120">アーキテクチャを特定した後、使用する展開方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="464de-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="464de-121">選択した展開ツールは、エンドポイントをサービスにオンボードする方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="464de-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="464de-122">オンボーディング ツールのオプション</span><span class="sxs-lookup"><span data-stu-id="464de-122">Onboarding tool options</span></span>

<span data-ttu-id="464de-123">次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。</span><span class="sxs-lookup"><span data-stu-id="464de-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="464de-124">Endpoint</span><span class="sxs-lookup"><span data-stu-id="464de-124">Endpoint</span></span>     | <span data-ttu-id="464de-125">ツール オプション</span><span class="sxs-lookup"><span data-stu-id="464de-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="464de-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="464de-126">**Windows**</span></span>  |  [<span data-ttu-id="464de-127">ローカル スクリプト (最大 10 台のデバイス)</span><span class="sxs-lookup"><span data-stu-id="464de-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="464de-128">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="464de-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="464de-129">Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー</span><span class="sxs-lookup"><span data-stu-id="464de-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="464de-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="464de-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="464de-131">VDI スクリプト</span><span class="sxs-lookup"><span data-stu-id="464de-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="464de-132">Azure Defender との統合</span><span class="sxs-lookup"><span data-stu-id="464de-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="464de-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="464de-133">**macOS**</span></span>    | [<span data-ttu-id="464de-134">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="464de-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="464de-135">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="464de-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="464de-136">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="464de-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="464de-137">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="464de-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="464de-138">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="464de-138">**Linux Server**</span></span> | [<span data-ttu-id="464de-139">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="464de-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="464de-140">Puppet</span><span class="sxs-lookup"><span data-stu-id="464de-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="464de-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="464de-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="464de-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="464de-142">**iOS**</span></span>      | [<span data-ttu-id="464de-143">アプリベース</span><span class="sxs-lookup"><span data-stu-id="464de-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="464de-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="464de-144">**Android**</span></span>  | [<span data-ttu-id="464de-145">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="464de-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
