---
title: シミュレートされた攻撃を通じて Microsoft Defender for Endpoint を体験する
description: 提供された攻撃シナリオシミュレーションを実行して、Microsoft Defender for Endpoint が侵害を検出、調査、および対応する方法を体験します。
keywords: test, scenario, attack, Simulation, simulationed, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 9a56167f0025ec42f4fd441886f83026c1bf23d6
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339540"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="7f631-104">シミュレートされた攻撃を通じて Microsoft Defender for Endpoint を体験する</span><span class="sxs-lookup"><span data-stu-id="7f631-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7f631-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7f631-105">**Applies to:**</span></span>
- [<span data-ttu-id="7f631-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7f631-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7f631-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f631-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="7f631-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7f631-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7f631-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7f631-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="7f631-110">Microsoft Defender for Endpoint の最新機能拡張: Defender for Endpoint の [新機能について説明します](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="7f631-110">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="7f631-111">Defender for Endpoint は、最近の MITRE 評価で業界をリードする光学機能と検出機能を実証しました。</span><span class="sxs-lookup"><span data-stu-id="7f631-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="7f631-112">読み取[インサイト MITRE ATT&CK ベースの評価を参照してください](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="7f631-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="7f631-113">サービスに複数のデバイスをオンボードする前に、Defender for Endpoint を体験する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f631-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="7f631-114">これを行うには、いくつかのテスト デバイスで制御攻撃シミュレーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7f631-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="7f631-115">シミュレートされた攻撃を実行した後、Defender for Endpoint が悪意のあるアクティビティを表面化する方法を確認し、効率的な対応を可能にする方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7f631-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7f631-116">開始する前に</span><span class="sxs-lookup"><span data-stu-id="7f631-116">Before you begin</span></span>

<span data-ttu-id="7f631-117">提供されているシミュレーションのいずれかを実行するには、オンボードデバイスが少なくとも [1 つ必要です](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="7f631-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="7f631-118">各攻撃シナリオで提供されるチュートリアル ドキュメントを読み取る。</span><span class="sxs-lookup"><span data-stu-id="7f631-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="7f631-119">各ドキュメントには、OS とアプリケーションの要件、および攻撃シナリオに固有の詳細な手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7f631-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="7f631-120">シミュレーションの実行</span><span class="sxs-lookup"><span data-stu-id="7f631-120">Run a simulation</span></span>

1. <span data-ttu-id="7f631-121">**[Endpoints** Evaluation & チュートリアル &シミュレーション] で、シミュレートする利用可能な攻撃シナリオを  >    >  選択します。</span><span class="sxs-lookup"><span data-stu-id="7f631-121">In **Endpoints** > **Evaluation & tutorials** > **Tutorials & simulations**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="7f631-122">**シナリオ 1: ドキュメントドロップバックドア** - ソーシャルエンジニアリングされたルアー ドキュメントの配信をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="7f631-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="7f631-123">このドキュメントは、攻撃者に制御を与える特別に細工されたバックドアを起動します。</span><span class="sxs-lookup"><span data-stu-id="7f631-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="7f631-124">**シナリオ 2: ファイル** レス攻撃の PowerShell スクリプト - PowerShell に依存するファイルレス攻撃をシミュレートし、攻撃表面の縮小と悪意のあるメモリ アクティビティのデバイス学習検出を示します。</span><span class="sxs-lookup"><span data-stu-id="7f631-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="7f631-125">**シナリオ 3: インシデント** 対応の自動化 - 自動調査がトリガーされ、侵害アーティファクトを自動的にハントして修復してインシデント対応の容量を拡張します。</span><span class="sxs-lookup"><span data-stu-id="7f631-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="7f631-126">選択したシナリオで提供される対応するチュートリアル ドキュメントをダウンロードして読み取る。</span><span class="sxs-lookup"><span data-stu-id="7f631-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="7f631-127">シミュレーション ファイルをダウンロードするか、チュートリアルのヘルプ シミュレーションに移動してシミュレーション  >  **スクリプト&します**。</span><span class="sxs-lookup"><span data-stu-id="7f631-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="7f631-128">テスト デバイスでファイルまたはスクリプトをダウンロードすることもできますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="7f631-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="7f631-129">チュートリアル ドキュメントの指示に従って、テスト デバイスでシミュレーション ファイルまたはスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f631-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="7f631-130">シミュレーション ファイルまたはスクリプトは攻撃アクティビティを模倣しますが、実際には良性であり、テスト デバイスに害を及ぼしたり、危険にさらしたりしません。</span><span class="sxs-lookup"><span data-stu-id="7f631-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="7f631-131">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7f631-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7f631-132">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7f631-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="7f631-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f631-133">Related topics</span></span>

- [<span data-ttu-id="7f631-134">デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="7f631-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="7f631-135">Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="7f631-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
