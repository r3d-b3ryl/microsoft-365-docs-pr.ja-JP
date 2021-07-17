---
title: シミュレートされた攻撃を通じて Microsoft Defender for Endpoint (MDE) を体験する
description: テスト ラボまたはMicrosoft 365 Defender環境をパイロットします。
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
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458144"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="79ef8-104">シミュレートされた攻撃を通じて Microsoft Defender for Endpoint (MDE) を体験する</span><span class="sxs-lookup"><span data-stu-id="79ef8-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="79ef8-105">Microsoft Defender for Endpoint の最新機能拡張: Defender for Endpoint の [新機能について説明します](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="79ef8-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="79ef8-106">Defender for Endpoint は、最近の MITRE 評価で業界をリードする光学機能と検出機能を実証しました。</span><span class="sxs-lookup"><span data-stu-id="79ef8-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="79ef8-107">読み取[インサイト MITRE ATT&CK ベースの評価を参照してください](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="79ef8-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="79ef8-108">サービスに複数のデバイスをオンボードする前に、Defender for Endpoint を体験する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="79ef8-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="79ef8-109">これを行うには、いくつかのテスト デバイスで制御攻撃シミュレーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="79ef8-110">シミュレートされた攻撃を実行した後、Defender for Endpoint が悪意のあるアクティビティを表面化する方法を確認し、効率的な対応を可能にする方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="79ef8-111">開始する前に</span><span class="sxs-lookup"><span data-stu-id="79ef8-111">Before you begin</span></span>

<span data-ttu-id="79ef8-112">提供されているシミュレーションのいずれかを実行するには、オンボードデバイスが少なくとも [1 つ必要です](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="79ef8-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="79ef8-113">各攻撃シナリオで提供されるチュートリアル ドキュメントを読み取る。</span><span class="sxs-lookup"><span data-stu-id="79ef8-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="79ef8-114">各ドキュメントには、OS とアプリケーションの要件、および攻撃シナリオに固有の詳細な手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79ef8-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="79ef8-115">シミュレーションの実行</span><span class="sxs-lookup"><span data-stu-id="79ef8-115">Run a simulation</span></span>

1. <span data-ttu-id="79ef8-116">[**ヘルプ**  >  **シミュレーション] &で**、シミュレートする利用可能な攻撃シナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="79ef8-117">**シナリオ 1: ドキュメントドロップバックドア** - ソーシャルエンジニアリングされたルアー ドキュメントの配信をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="79ef8-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="79ef8-118">このドキュメントは、攻撃者に制御を与える特別に細工されたバックドアを起動します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="79ef8-119">**シナリオ 2: ファイル** レス攻撃の PowerShell スクリプト - PowerShell に依存するファイルレス攻撃をシミュレートし、攻撃表面の縮小と悪意のあるメモリ アクティビティのデバイス学習検出を示します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="79ef8-120">**シナリオ 3: インシデント** 対応の自動化 - 自動調査がトリガーされ、侵害アーティファクトを自動的にハントして修復してインシデント対応の容量を拡張します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="79ef8-121">選択したシナリオで提供される対応するチュートリアル ドキュメントをダウンロードして読み取る。</span><span class="sxs-lookup"><span data-stu-id="79ef8-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="79ef8-122">シミュレーション ファイルをダウンロードするか、チュートリアルのヘルプ シミュレーションに移動してシミュレーション  >  **スクリプト&します**。</span><span class="sxs-lookup"><span data-stu-id="79ef8-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="79ef8-123">テスト デバイスでファイルまたはスクリプトをダウンロードすることもできますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="79ef8-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="79ef8-124">チュートリアル ドキュメントの指示に従って、テスト デバイスでシミュレーション ファイルまたはスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="79ef8-125">シミュレーション ファイルまたはスクリプトは攻撃アクティビティを模倣しますが、実際には良性であり、テスト デバイスに害を及ぼしたり、危険にさらしたりしません。</span><span class="sxs-lookup"><span data-stu-id="79ef8-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="79ef8-126">代替トピック テキスト</span><span class="sxs-lookup"><span data-stu-id="79ef8-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="79ef8-127">攻撃シナリオのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="79ef8-127">Simulate attack scenarios</span></span>

<span data-ttu-id="79ef8-128">テスト デバイスを使用して、テスト デバイスに接続して独自の攻撃シミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="79ef8-129">攻撃シナリオは、次の方法でシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="79ef8-130">["Do It Yourself" 攻撃のシナリオ](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="79ef8-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="79ef8-131">脅威シミュレーター</span><span class="sxs-lookup"><span data-stu-id="79ef8-131">Threat simulators</span></span>

<span data-ttu-id="79ef8-132">高度な検索を使用[してデータ](advanced-hunting-overview.md)をクエリし[](threat-analytics.md)、脅威分析を使用して、新たな脅威に関するレポートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="79ef8-133">Do-it-yourself 攻撃のシナリオ</span><span class="sxs-lookup"><span data-stu-id="79ef8-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="79ef8-134">事前に作成されたシミュレーションを探している場合は、"Do It [Yourself" 攻撃シナリオを使用できます](https://securitycenter.windows.com/tutorials)。</span><span class="sxs-lookup"><span data-stu-id="79ef8-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="79ef8-135">これらのスクリプトは安全で文書化され、使いやすいです。</span><span class="sxs-lookup"><span data-stu-id="79ef8-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="79ef8-136">これらのシナリオは、Defender for Endpoint の機能を反映し、調査のエクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="79ef8-137">テスト デバイスへの接続は RDP を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="79ef8-138">ファイアウォールの設定で RDP 接続が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ef8-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="79ef8-139">Connectを選択して、デバイスにアクセスし、攻撃シミュレーション **をConnect。**</span><span class="sxs-lookup"><span data-stu-id="79ef8-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![テスト デバイスの接続ボタンのイメージ](images/test-machine-table.png)

2. <span data-ttu-id="79ef8-141">RDP ファイルを保存し、[開く] を選択して **起動Connect。**</span><span class="sxs-lookup"><span data-stu-id="79ef8-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![リモート デスクトップ接続のイメージ](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="79ef8-143">初期セットアップ中に保存されたパスワードのコピーが存在しない場合は、メニューから [パスワードのリセット] を選択してパスワードをリセットできます。[パスワードのリセットの ![ イメージ]](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="79ef8-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="79ef8-144">デバイスは状態を "パスワードリセットの実行" に変更し、数分で新しいパスワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="79ef8-145">デバイスの作成手順中に表示されたパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-145">Enter the password that was displayed during the device creation step.</span></span>

   ![資格情報を入力するウィンドウのイメージ](images/enter-password.png)

4. <span data-ttu-id="79ef8-147">デバイスで Do-it-yourself 攻撃シミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="79ef8-148">脅威シミュレーターのシナリオ</span><span class="sxs-lookup"><span data-stu-id="79ef8-148">Threat simulator scenarios</span></span>

<span data-ttu-id="79ef8-149">ラボのセットアップ中にサポートされている脅威シミュレーターのインストールを選択した場合は、評価ラボ デバイスで組み込みのシミュレーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="79ef8-150">サード パーティプラットフォームを使用して脅威シミュレーションを実行すると、ラボ環境の範囲内で Microsoft Defender for Endpoint の機能を評価できます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="79ef8-151">シミュレーションを実行する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="79ef8-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="79ef8-152">評価ラボにデバイスを追加する必要があります</span><span class="sxs-lookup"><span data-stu-id="79ef8-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="79ef8-153">脅威シミュレーターは評価ラボにインストールする必要があります</span><span class="sxs-lookup"><span data-stu-id="79ef8-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="79ef8-154">ポータルで [シミュレーションの作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="79ef8-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="79ef8-155">脅威シミュレーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-155">Select a threat simulator.</span></span>

    ![脅威シミュレーターの選択のイメージ](images/select-simulator.png)

3. <span data-ttu-id="79ef8-157">シミュレーションを選択するか、シミュレーション ギャラリーを参照して使用可能なシミュレーションを参照します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="79ef8-158">シミュレーション ギャラリーは、次の場所から取得できます。</span><span class="sxs-lookup"><span data-stu-id="79ef8-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="79ef8-159">シミュレーションの概要タイルの主 **な** 評価ダッシュボードまたは</span><span class="sxs-lookup"><span data-stu-id="79ef8-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="79ef8-160">ナビゲーション ウィンドウの [評価] と **[チュートリアル]** から [シミュレーション] &をクリックし、[シミュレーション  >  カタログ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="79ef8-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="79ef8-161">シミュレーションを実行するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="79ef8-162">[シミュレーション **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="79ef8-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="79ef8-163">[シミュレーション] タブを選択して、シミュレーションの進行状況 **を表示** します。シミュレーションの状態、アクティブなアラート、その他の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="79ef8-164">![[シミュレーションのイメージ] タブ](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="79ef8-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="79ef8-165">シミュレーションを実行した後、ラボの進行状況バーを表示し **、Microsoft Defender for Endpoint** を調べ、自動調査と修復をトリガーしてください。</span><span class="sxs-lookup"><span data-stu-id="79ef8-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="79ef8-166">機能によって収集および分析された証拠を確認します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="79ef8-167">豊富なクエリ言語と生の利用統計情報を使用して高度な検索を通じて攻撃証拠を探し、Threat analytics に記載されている世界全体の脅威を確認します。</span><span class="sxs-lookup"><span data-stu-id="79ef8-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
