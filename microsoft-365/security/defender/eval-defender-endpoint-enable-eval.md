---
title: Microsoft Defender for Endpoint 評価を有効にし、MDE の評価をアクティブ化する
description: ライセンス状態のMicrosoft 365 Defender、enpoints のオンボーディングなど、テストラボまたはパイロット環境を有効にする
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458099"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="1283e-103">エンドポイント評価環境で Microsoft Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="1283e-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="1283e-104">この記事では、実稼働デバイスを使用して Microsoft Defender for Endpoint の評価環境をセットアップする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1283e-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="1283e-105">Microsoft Defender for Endpoint には、事前に構成されたデバイスを追加し、シミュレーションを実行してプラットフォームの機能を評価できる製品内評価ラボも付属しています。</span><span class="sxs-lookup"><span data-stu-id="1283e-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="1283e-106">このラボには、高度な狩猟や脅威分析などの多くの機能に関するガイダンスを含む、Microsoft Defender for Enpdoint の価値をすばやく実証するのに役立つ、簡略化されたセットアップ エクスペリエンスが付属しています。</span><span class="sxs-lookup"><span data-stu-id="1283e-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="1283e-107">詳細については、「評価機能 [」を参照してください](/defender-endpoint/evaluation-lab.md)。</span><span class="sxs-lookup"><span data-stu-id="1283e-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="1283e-108">この記事で提供されるガイダンスと評価ラボの主な違いは、評価環境が実稼働デバイスを使用するのに対し、評価ラボでは非実稼働デバイスを使用する点です。</span><span class="sxs-lookup"><span data-stu-id="1283e-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="1283e-109">Microsoft Defender for Endpoint の評価を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1283e-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![Microsoft Defender 評価環境で Microsoft Defender for Endpoint を有効にする手順](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="1283e-111">手順 1.ライセンスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="1283e-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="1283e-112">手順 2.オンボード エンドポイント</span><span class="sxs-lookup"><span data-stu-id="1283e-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="1283e-113">手順 1.</span><span class="sxs-lookup"><span data-stu-id="1283e-113">Step 1.</span></span> <span data-ttu-id="1283e-114">ライセンスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="1283e-114">Check license state</span></span>

<span data-ttu-id="1283e-115">まず、ライセンス状態を確認して、ライセンスが適切にプロビジョニングされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1283e-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="1283e-116">これを行うには、管理センターまたはポータルから **Microsoft Azureします**。</span><span class="sxs-lookup"><span data-stu-id="1283e-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="1283e-117">ライセンスを表示するには、Microsoft Azureポータルに **移動** し、[Microsoft Azure][セクションに移動します](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="1283e-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![[Azure ライセンス] ページのイメージ](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="1283e-119">または、管理センターで [課金サブスクリプション]   >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1283e-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="1283e-120">画面に、すべてのプロビジョニング済みライセンスと現在の状態が表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="1283e-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![課金ライセンスのイメージ](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="1283e-122">手順 2.</span><span class="sxs-lookup"><span data-stu-id="1283e-122">Step 2.</span></span> <span data-ttu-id="1283e-123">サポートされている管理ツールを使用したオンボード エンドポイント</span><span class="sxs-lookup"><span data-stu-id="1283e-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="1283e-124">ライセンス状態が適切にプロビジョニングされていることを確認した後、サービスへのデバイスのオンボーディングを開始できます。</span><span class="sxs-lookup"><span data-stu-id="1283e-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="1283e-125">Microsoft Defender for Endpoint の評価を行う目的で、評価を行う 2 Windows 10デバイスを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1283e-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="1283e-126">「 [展開の計画」](../defender-endpoint/deployment-strategy.md) トピックでは、Defender for Endpoint の展開に必要な一般的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1283e-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="1283e-127">オンボーディング プロセスの概要と、使用可能なツールと方法について詳しくは、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1283e-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="1283e-128">オンボーディング ツールのオプション</span><span class="sxs-lookup"><span data-stu-id="1283e-128">Onboarding tool options</span></span>

<span data-ttu-id="1283e-129">次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。</span><span class="sxs-lookup"><span data-stu-id="1283e-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="1283e-130">Endpoint</span><span class="sxs-lookup"><span data-stu-id="1283e-130">Endpoint</span></span> | <span data-ttu-id="1283e-131">ツール オプション</span><span class="sxs-lookup"><span data-stu-id="1283e-131">Tool options</span></span>
:---|:---
<span data-ttu-id="1283e-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="1283e-132">**Windows**</span></span> | <span data-ttu-id="1283e-133">[ローカル スクリプト (最大 10](../defender-endpoint/configure-endpoints-script.md)台のデバイス) [、](../defender-endpoint/configure-endpoints-gp.md)グループ ポリシー 、 [Microsoft エンドポイント マネージャー/](../defender-endpoint/configure-endpoints-mdm.md)Mobile Device Manager [、](../defender-endpoint/configure-endpoints-sccm.md)Microsoft Endpoint Configuration Manager 、 [VDI スクリプト](../defender-endpoint/configure-endpoints-vdi.md)、 Azure Defender との[統合](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span><span class="sxs-lookup"><span data-stu-id="1283e-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="1283e-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="1283e-134">**macOS**</span></span> | <span data-ttu-id="1283e-135">[ローカル スクリプト](../defender-endpoint/mac-install-manually.md)、 [Microsoft エンドポイント マネージャー](../defender-endpoint/mac-install-with-intune.md)、 [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md)、[モバイル デバイス管理](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="1283e-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="1283e-136">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="1283e-136">**Linux Server**</span></span> | <span data-ttu-id="1283e-137">[ローカル スクリプト](../defender-endpoint/linux-install-manually.md)、  [Puppet](../defender-endpoint/linux-install-with-puppet.md)、  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="1283e-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="1283e-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="1283e-138">**iOS**</span></span> | [<span data-ttu-id="1283e-139">アプリベース</span><span class="sxs-lookup"><span data-stu-id="1283e-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="1283e-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="1283e-140">**Android**</span></span> | [<span data-ttu-id="1283e-141">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="1283e-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="1283e-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="1283e-142">Next step</span></span>
[<span data-ttu-id="1283e-143">Microsoft Defender for Endpoint のパイロットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="1283e-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="1283e-144">エンドポイントの Microsoft [Defender の評価の概要に戻る](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1283e-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="1283e-145">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1283e-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>