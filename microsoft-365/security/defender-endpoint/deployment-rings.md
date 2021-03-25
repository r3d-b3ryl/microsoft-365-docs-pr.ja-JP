---
title: Microsoft Defender for Endpoint をリングに展開する
description: リングに Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: 展開、リング、評価、パイロット、インサイダーファースト、インサイダースロー、セットアップ、オンボード、フェーズ、展開、展開、導入、構成
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
ms.openlocfilehash: 2d34b984436b3ed0537af2eebcd8475ec270cd8e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165791"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="66055-104">Microsoft Defender for Endpoint をリングに展開する</span><span class="sxs-lookup"><span data-stu-id="66055-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="66055-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="66055-105">**Applies to:**</span></span>
- [<span data-ttu-id="66055-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="66055-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="66055-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66055-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="66055-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="66055-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="66055-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="66055-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="66055-110">Microsoft Defender for Endpoint の展開は、リング ベースの展開方法を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="66055-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="66055-111">展開リングは、次のシナリオで適用できます。</span><span class="sxs-lookup"><span data-stu-id="66055-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="66055-112">新しい展開</span><span class="sxs-lookup"><span data-stu-id="66055-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="66055-113">既存の展開</span><span class="sxs-lookup"><span data-stu-id="66055-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="66055-114">新しい展開</span><span class="sxs-lookup"><span data-stu-id="66055-114">New deployments</span></span>

![展開リングのイメージ](images/deployment-rings.png)


<span data-ttu-id="66055-116">リング ベースのアプローチは、オンボードする一連のエンドポイントを識別し、より大きなデバイス セットにサービスを展開する前に特定の条件が満たされるのを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="66055-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="66055-117">各リングの終了条件を定義し、次のリングに進む前に満たされた条件を満たします。</span><span class="sxs-lookup"><span data-stu-id="66055-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="66055-118">リング ベースの展開を採用すると、サービスの展開中に発生する可能性のある潜在的な問題を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="66055-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="66055-119">最初に特定の数のデバイスをパイロットすることで、潜在的な問題を特定し、発生する可能性のあるリスクを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="66055-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="66055-120">表 1 に、使用できる展開リングの例を示します。</span><span class="sxs-lookup"><span data-stu-id="66055-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="66055-121">**表 1**</span><span class="sxs-lookup"><span data-stu-id="66055-121">**Table 1**</span></span>

|<span data-ttu-id="66055-122">**展開リング**</span><span class="sxs-lookup"><span data-stu-id="66055-122">**Deployment ring**</span></span>|<span data-ttu-id="66055-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="66055-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="66055-124">Evaluate</span><span class="sxs-lookup"><span data-stu-id="66055-124">Evaluate</span></span> | <span data-ttu-id="66055-125">リング 1: パイロット テスト用の 50 のシステムを特定する</span><span class="sxs-lookup"><span data-stu-id="66055-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="66055-126">パイロット</span><span class="sxs-lookup"><span data-stu-id="66055-126">Pilot</span></span> | <span data-ttu-id="66055-127">リング 2: 実稼働環境の次の 50 ~ 100 エンドポイントを特定する</span><span class="sxs-lookup"><span data-stu-id="66055-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="66055-128">完全展開</span><span class="sxs-lookup"><span data-stu-id="66055-128">Full deployment</span></span> | <span data-ttu-id="66055-129">リング 3: より大きな増分でサービスを残りの環境にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="66055-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="66055-130">終了条件</span><span class="sxs-lookup"><span data-stu-id="66055-130">Exit criteria</span></span>
<span data-ttu-id="66055-131">これらのリングの終了条件のセットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="66055-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="66055-132">デバイスがデバイス インベントリ リストに表示される</span><span class="sxs-lookup"><span data-stu-id="66055-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="66055-133">ダッシュボードにアラートが表示される</span><span class="sxs-lookup"><span data-stu-id="66055-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="66055-134">検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="66055-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="66055-135">デバイスに対してシミュレートされた攻撃を実行する</span><span class="sxs-lookup"><span data-stu-id="66055-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="66055-136">Evaluate</span><span class="sxs-lookup"><span data-stu-id="66055-136">Evaluate</span></span>
<span data-ttu-id="66055-137">サービスにオンボードする環境内のテスト マシンの数が少ない場合を特定します。</span><span class="sxs-lookup"><span data-stu-id="66055-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="66055-138">理想的には、これらのコンピューターは 50 未満のエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="66055-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="66055-139">パイロット</span><span class="sxs-lookup"><span data-stu-id="66055-139">Pilot</span></span>
<span data-ttu-id="66055-140">Microsoft Defender ATP は、サービスにオンボードできるさまざまなエンドポイントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="66055-140">Microsoft Defender ATP supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="66055-141">このリングで、オンボードする複数のデバイスを特定し、定義した終了条件に基づいて、次の展開リングに進みます。</span><span class="sxs-lookup"><span data-stu-id="66055-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="66055-142">次の表に、サポートされているエンドポイントと、サービスにデバイスをオンボードするために使用できる対応するツールを示します。</span><span class="sxs-lookup"><span data-stu-id="66055-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="66055-143">Endpoint</span><span class="sxs-lookup"><span data-stu-id="66055-143">Endpoint</span></span>     | <span data-ttu-id="66055-144">展開ツール</span><span class="sxs-lookup"><span data-stu-id="66055-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="66055-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="66055-145">**Windows**</span></span>  |  [<span data-ttu-id="66055-146">ローカル スクリプト (最大 10 台のデバイス)</span><span class="sxs-lookup"><span data-stu-id="66055-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="66055-147">注: 10 台を超えるデバイスを実稼働環境に展開する場合は、代わりに Group Policy メソッドを使用するか、以下に示す他のサポートされているツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="66055-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="66055-148">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="66055-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="66055-149">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="66055-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="66055-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="66055-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="66055-151">VDI スクリプト</span><span class="sxs-lookup"><span data-stu-id="66055-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="66055-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="66055-152">**macOS**</span></span>    | [<span data-ttu-id="66055-153">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="66055-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="66055-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="66055-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="66055-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="66055-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="66055-156">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="66055-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="66055-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="66055-157">**Linux Server**</span></span> | [<span data-ttu-id="66055-158">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="66055-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="66055-159">Puppet</span><span class="sxs-lookup"><span data-stu-id="66055-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="66055-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="66055-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="66055-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="66055-161">**iOS**</span></span>      | [<span data-ttu-id="66055-162">アプリベース</span><span class="sxs-lookup"><span data-stu-id="66055-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="66055-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="66055-163">**Android**</span></span>  | [<span data-ttu-id="66055-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="66055-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="66055-165">完全展開</span><span class="sxs-lookup"><span data-stu-id="66055-165">Full deployment</span></span>
<span data-ttu-id="66055-166">この段階では、展開 [の計画に](deployment-strategy.md) 役立つ展開の計画資料を使用できます。</span><span class="sxs-lookup"><span data-stu-id="66055-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="66055-167">次の資料を使用して、組織に最適な Microsoft Defender ATP アーキテクチャを選択します。</span><span class="sxs-lookup"><span data-stu-id="66055-167">Use the following material to select the appropriate Microsoft Defender ATP architecture that best suites your organization.</span></span>

|<span data-ttu-id="66055-168">**項目**</span><span class="sxs-lookup"><span data-stu-id="66055-168">**Item**</span></span>|<span data-ttu-id="66055-169">**説明**</span><span class="sxs-lookup"><span data-stu-id="66055-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66055-170">[![Microsoft Defender ATP 展開戦略のサムネイルイメージ](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="66055-170">[![Thumb image for Microsoft Defender ATP deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="66055-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="66055-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="66055-172">アーキテクチャ教材は、次のアーキテクチャの展開を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="66055-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="66055-173">クラウド-ネイティブ</span><span class="sxs-lookup"><span data-stu-id="66055-173">Cloud-native</span></span> </li><li> <span data-ttu-id="66055-174">共同管理</span><span class="sxs-lookup"><span data-stu-id="66055-174">Co-management</span></span> </li><li> <span data-ttu-id="66055-175">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="66055-175">On-premise</span></span></li><li><span data-ttu-id="66055-176">評価とローカル オンボード</span><span class="sxs-lookup"><span data-stu-id="66055-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="66055-177">既存の展開</span><span class="sxs-lookup"><span data-stu-id="66055-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="66055-178">Windows エンドポイント</span><span class="sxs-lookup"><span data-stu-id="66055-178">Windows endpoints</span></span>
<span data-ttu-id="66055-179">Windows サーバーまたは Windows サーバーの場合は、セキュリティ更新プログラム検証プログラム **(SUVP)** を使用して、(パッチが火曜日に更新される前に) テストする複数のコンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="66055-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="66055-180">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66055-180">For more information, see:</span></span>
- [<span data-ttu-id="66055-181">セキュリティ更新プログラムの検証プログラムとは</span><span class="sxs-lookup"><span data-stu-id="66055-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="66055-182">ソフトウェア更新プログラムの検証プログラムとマイクロソフト マルウェア プロテクション センター設定 - TwC 対話型タイムライン パート 4</span><span class="sxs-lookup"><span data-stu-id="66055-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="66055-183">Windows 以外のエンドポイント</span><span class="sxs-lookup"><span data-stu-id="66055-183">Non-Windows endpoints</span></span>
<span data-ttu-id="66055-184">macOS と Linux を使用すると、いくつかのシステムを使用して "InsidersFast" チャネルで実行できます。</span><span class="sxs-lookup"><span data-stu-id="66055-184">With macOS and Linux, you could take a couple of systems and run in the "InsidersFast" channel.</span></span>

>[!NOTE]
><span data-ttu-id="66055-185">ビルドが "実稼働" チャネルに入る前に互換性、パフォーマンス、および信頼性の問題を見つけ出せそうとして、少なくとも 1 人のセキュリティ管理者と 1 人の開発者が理想的です。</span><span class="sxs-lookup"><span data-stu-id="66055-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the "Production" channel.</span></span>

<span data-ttu-id="66055-186">チャネルの選択によって、デバイスに提供される更新プログラムの種類と頻度が決されます。</span><span class="sxs-lookup"><span data-stu-id="66055-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="66055-187">insiders-fast のデバイスは、更新プログラムと新機能を受け取る最初のデバイスで、後で insiders-slow と最後に prod が続きます。</span><span class="sxs-lookup"><span data-stu-id="66055-187">Devices in insiders-fast are the first ones to receive updates and new features, followed later by insiders-slow and lastly by prod.</span></span>

![インサイダー リングのイメージ](images/insider-rings.png)

<span data-ttu-id="66055-189">新機能をプレビューし、早期のフィードバックを提供するために、インサイダーが高速またはインサイダーが遅い場合に使用するデバイスを企業内で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66055-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either insiders-fast or insiders-slow.</span></span>

>[!WARNING]
><span data-ttu-id="66055-190">最初のインストール後にチャネルを切り替える場合は、製品を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66055-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="66055-191">製品チャネルを切り替える: 既存のパッケージをアンインストールし、新しいチャネルを使用するデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="66055-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
