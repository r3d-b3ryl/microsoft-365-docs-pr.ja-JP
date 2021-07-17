---
title: エンドポイントの Microsoft Defender のパイロット、パイロットのセットアップ、評価のテスト機能
description: パイロット グループの確認や機能の試用など、Microsoft Defender for Endpoint(MDE) のパイロットを実行する方法について説明します。
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
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458006"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a><span data-ttu-id="7483a-103">エンドポイント向け Microsoft Defender のパイロット</span><span class="sxs-lookup"><span data-stu-id="7483a-103">Pilot Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7483a-104">この記事では、Microsoft Defender for Endpoint のパイロットを実行するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7483a-104">This article will guide you in the process of running a pilot for Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="7483a-105">次の手順を使用して、Microsoft Defender for Endpoint のパイロットをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="7483a-105">Use the following steps to setup and configure the pilot for Microsoft Defender for Endpoint.</span></span> 

![Defender 評価環境に Microsoft Defender for Identity を追加する手順](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- <span data-ttu-id="7483a-107">手順 1.</span><span class="sxs-lookup"><span data-stu-id="7483a-107">Step 1.</span></span> <span data-ttu-id="7483a-108">パイロット グループの確認</span><span class="sxs-lookup"><span data-stu-id="7483a-108">Verify pilot group</span></span>
- <span data-ttu-id="7483a-109">手順 2.</span><span class="sxs-lookup"><span data-stu-id="7483a-109">Step 2.</span></span> <span data-ttu-id="7483a-110">機能を試す</span><span class="sxs-lookup"><span data-stu-id="7483a-110">Try out capabilities</span></span>

<span data-ttu-id="7483a-111">Microsoft Defender for Endpoint をパイロットする場合は、組織全体をオンボーディングする前に、いくつかのデバイスをサービスにオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="7483a-111">When you pilot Microsoft Defender for Endpoint, you may choose to onboard a few devices to the service before onboarding your entire organization.</span></span>  

<span data-ttu-id="7483a-112">その後、攻撃シミュレーションの実行、Defender for Endpoint による悪意のあるアクティビティの表面化、効率的な応答の実行など、利用可能な機能を試し直します。</span><span class="sxs-lookup"><span data-stu-id="7483a-112">You can then try out capabilities that are available such as running attack simulations and seeing how Defender for Endpoint surfaces malicious activities and enables you to conduct an efficient response.</span></span> 

## <a name="step-1-verify-pilot-group"></a><span data-ttu-id="7483a-113">手順 1.</span><span class="sxs-lookup"><span data-stu-id="7483a-113">Step 1.</span></span> <span data-ttu-id="7483a-114">パイロット グループの確認</span><span class="sxs-lookup"><span data-stu-id="7483a-114">Verify pilot group</span></span>
<span data-ttu-id="7483a-115">[評価を有効にする] セクションで説明されている[](eval-defender-endpoint-enable-eval.md)オンボーディング手順を完了すると、デバイスインベントリリストにデバイスが約 1 時間後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7483a-115">After completing the onboarding steps outlined in the [Enable evaluation](eval-defender-endpoint-enable-eval.md) section, you should see the devices in the Device inventory list approximately after an hour.</span></span> 

<span data-ttu-id="7483a-116">オンボードデバイスが表示された場合は、機能の試しに進みます。</span><span class="sxs-lookup"><span data-stu-id="7483a-116">When you see your onboarded devices you can then proceed with trying out capabilities.</span></span> 

## <a name="step-2-try-out-capabilities"></a><span data-ttu-id="7483a-117">手順 2.</span><span class="sxs-lookup"><span data-stu-id="7483a-117">Step 2.</span></span> <span data-ttu-id="7483a-118">機能を試す</span><span class="sxs-lookup"><span data-stu-id="7483a-118">Try out capabilities</span></span>
<span data-ttu-id="7483a-119">一部のデバイスのオンボーディングが完了し、サービスに報告されているのを確認したら、使用可能な強力な機能を試して、製品について理解してください。</span><span class="sxs-lookup"><span data-stu-id="7483a-119">Now that you've completed onboarding some devices and verified that they are reporting to the service, familiarize yourself with the product by trying out the powerful capabilities that are available right out of the box.</span></span>

<span data-ttu-id="7483a-120">パイロットの間は、複雑な構成手順を実行せずに、いくつかの機能を試して製品を実際に確認できます。</span><span class="sxs-lookup"><span data-stu-id="7483a-120">During the pilot, you can easily get started with trying out some of the features to see the product in action without going through complex configuration steps.</span></span>

<span data-ttu-id="7483a-121">まず、ダッシュボードをチェックアウトします。</span><span class="sxs-lookup"><span data-stu-id="7483a-121">Let's start by checking out the dashboards.</span></span>

### <a name="view-the-device-inventory"></a><span data-ttu-id="7483a-122">デバイス インベントリの表示</span><span class="sxs-lookup"><span data-stu-id="7483a-122">View the device inventory</span></span>
<span data-ttu-id="7483a-123">デバイス インベントリは、ネットワーク内のエンドポイント、ネットワーク デバイス、および IoT デバイスの一覧を表示する場所です。</span><span class="sxs-lookup"><span data-stu-id="7483a-123">The device inventory is where you'll see the list of endpoints, network devices, and IoT devices in your network.</span></span> <span data-ttu-id="7483a-124">ネットワーク内のデバイスのビューを提供するだけでなく、ドメイン、リスク レベル、OS プラットフォームなどの詳細な情報を提供し、最も危険にさらされているデバイスを簡単に識別できます。</span><span class="sxs-lookup"><span data-stu-id="7483a-124">Not only does it provide you with a view of the devices in your network, but it also gives your in-depth information about them such as  domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="7483a-125">脅威と脅威のダッシュボード脆弱性の管理する</span><span class="sxs-lookup"><span data-stu-id="7483a-125">View the Threat and vulnerability management dashboard</span></span> 
<span data-ttu-id="7483a-126">脅威と脆弱性の管理は、組織にとって最も緊急かつ最もリスクの高い弱点に集中するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7483a-126">Threat and vulnerability management helps you focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="7483a-127">ダッシュボードから、組織の露出スコア、Microsoft Secure Score for Devices、デバイスの露出分布、トップ セキュリティ推奨事項、脆弱なソフトウェアの上位、トップ修復アクティビティ、および公開されているトップ デバイス データの高レベルのビューを取得します。</span><span class="sxs-lookup"><span data-stu-id="7483a-127">From the dashboard, get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span> 

### <a name="run-a-simulation"></a><span data-ttu-id="7483a-128">シミュレーションの実行</span><span class="sxs-lookup"><span data-stu-id="7483a-128">Run a simulation</span></span>
<span data-ttu-id="7483a-129">Microsoft Defender for Endpoint には、パイロット デバイスで実行できる ["Do It Yourself"](https://securitycenter.windows.com/tutorials) 攻撃シナリオが付属しています。</span><span class="sxs-lookup"><span data-stu-id="7483a-129">Microsoft Defender for Endpoint comes with ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials) that you can run on your pilot devices.</span></span>  <span data-ttu-id="7483a-130">各ドキュメントには、OS とアプリケーションの要件、および攻撃シナリオに固有の詳細な手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7483a-130">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span> <span data-ttu-id="7483a-131">これらのスクリプトは安全で文書化され、使いやすいです。</span><span class="sxs-lookup"><span data-stu-id="7483a-131">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="7483a-132">これらのシナリオは、Defender for Endpoint の機能を反映し、調査のエクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7483a-132">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

<span data-ttu-id="7483a-133">提供されているシミュレーションのいずれかを実行するには、オンボードデバイスが少なくとも [1 つ必要です](../defender-endpoint/onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="7483a-133">To run any of the provided simulations, you need at least [one onboarded device](../defender-endpoint/onboard-configure.md).</span></span>

1. <span data-ttu-id="7483a-134">[**ヘルプ**  >  **シミュレーション] &で**、シミュレートする利用可能な攻撃シナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="7483a-134">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="7483a-135">**シナリオ 1: ドキュメントドロップバックドア** - ソーシャルエンジニアリングされたルアー ドキュメントの配信をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="7483a-135">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="7483a-136">このドキュメントは、攻撃者に制御を与える特別に細工されたバックドアを起動します。</span><span class="sxs-lookup"><span data-stu-id="7483a-136">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="7483a-137">**シナリオ 2: ファイル** レス攻撃の PowerShell スクリプト - PowerShell に依存するファイルレス攻撃をシミュレートし、攻撃表面の縮小と悪意のあるメモリ アクティビティのデバイス学習検出を示します。</span><span class="sxs-lookup"><span data-stu-id="7483a-137">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="7483a-138">**シナリオ 3: インシデント** 対応の自動化 - 自動調査がトリガーされ、侵害アーティファクトを自動的にハントして修復してインシデント対応の容量を拡張します。</span><span class="sxs-lookup"><span data-stu-id="7483a-138">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="7483a-139">選択したシナリオで提供される対応するチュートリアル ドキュメントをダウンロードして読み取る。</span><span class="sxs-lookup"><span data-stu-id="7483a-139">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="7483a-140">シミュレーション ファイルをダウンロードするか、チュートリアルのヘルプ シミュレーションに移動してシミュレーション  >  **スクリプト&します**。</span><span class="sxs-lookup"><span data-stu-id="7483a-140">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="7483a-141">テスト デバイスでファイルまたはスクリプトをダウンロードすることもできますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="7483a-141">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="7483a-142">チュートリアル ドキュメントの指示に従って、テスト デバイスでシミュレーション ファイルまたはスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="7483a-142">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="7483a-143">シミュレーション ファイルまたはスクリプトは攻撃アクティビティを模倣しますが、実際には良性であり、テスト デバイスに害を及ぼしたり、危険にさらしたりしません。</span><span class="sxs-lookup"><span data-stu-id="7483a-143">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7483a-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="7483a-144">Next steps</span></span>
[<span data-ttu-id="7483a-145">評価Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7483a-145">Evaluate Microsoft Cloud App Security</span></span>](eval-defender-mcas-overview.md)

<span data-ttu-id="7483a-146">エンドポイントの Microsoft [Defender の評価の概要に戻る](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7483a-146">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="7483a-147">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7483a-147">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>