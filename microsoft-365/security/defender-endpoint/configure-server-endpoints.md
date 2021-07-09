---
title: Microsoft Defender Windowsエンドポイント サービスへのオンボード サーバー
description: センサー Windowsを Microsoft Defender for Endpoint センサーに送信できるよう、オンボード サーバーを使用します。
keywords: オンボード サーバー、サーバー、2012r2、2016、2019、サーバーオンボーディング、デバイス管理、エンドポイント サーバー用 Microsoft Defender の構成、Microsoft Defender for Endpoint サーバーのオンボード、Microsoft Defender for Endpoint サーバーのオンボード
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 08fe4314c1461710d83ea7aeba1fdf9a60dd33a8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339240"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="29d65-104">Microsoft Defender Windowsエンドポイント サービスへのオンボード サーバー</span><span class="sxs-lookup"><span data-stu-id="29d65-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="29d65-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="29d65-105">**Applies to:**</span></span>

- <span data-ttu-id="29d65-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="29d65-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="29d65-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="29d65-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="29d65-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="29d65-108">Windows Server 2016</span></span>
- <span data-ttu-id="29d65-109">Windows Server (SAC) バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="29d65-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="29d65-110">Windows Server 2019 以降</span><span class="sxs-lookup"><span data-stu-id="29d65-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="29d65-111">Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="29d65-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="29d65-112">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="29d65-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="29d65-113">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="29d65-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="29d65-114">Defender for Endpoint では、サポートを拡張して、サーバー オペレーティング Windowsも含まれます。</span><span class="sxs-lookup"><span data-stu-id="29d65-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="29d65-115">このサポートは、高度な攻撃の検出と調査機能を、Microsoft 365 Defender提供します。</span><span class="sxs-lookup"><span data-stu-id="29d65-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft 365 Defender console.</span></span>

<span data-ttu-id="29d65-116">ライセンスとインフラストラクチャに必要な機能に関する実践的なガイダンスについては、「Defender for Endpoint Windowsサーバーの保護」[を参照してください](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)。</span><span class="sxs-lookup"><span data-stu-id="29d65-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="29d65-117">サーバーのベースラインをダウンロードして使用する方法Windows セキュリティについては、「Windowsベースライン[Windows セキュリティ」を参照してください](/windows/device-security/windows-security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="29d65-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="29d65-118">WindowsServer 2008 R2 SP1、Windows Server 2012 R2、およびWindows Server 2016</span><span class="sxs-lookup"><span data-stu-id="29d65-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="29d65-119">次のオプションWindowsを使用して、Defender for Endpoint Windows Server 2008 R2 SP1、Windows Server 2012 R2、Windows Server 2016 を Defender にオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="29d65-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="29d65-120">**オプション 1**:[インストールおよび構成によるオンボード Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="29d65-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="29d65-121">**オプション 2**: [Azure セキュリティ センター経由でオンボードする](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="29d65-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="29d65-122">**オプション 3**:[バージョン 2002 以降Microsoft エンドポイント マネージャーオンボード](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="29d65-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="29d65-123">提供されているオプションを使用してオンボーディング手順を完了した後、クライアントの構成と更新[System Center Endpoint Protection必要があります](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="29d65-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="29d65-124">Windows サーバーを Microsoft Monitoring Agent (オプション 1) または Microsoft エンドポイント マネージャー (オプション 3) を介してオンボードするには、ノードごとにエンドポイントのスタンドアロン サーバー ライセンスの Defender が必要です。</span><span class="sxs-lookup"><span data-stu-id="29d65-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="29d65-125">または、Azure セキュリティ センター (オプション 2) を介して Windows サーバーをオンボードするには、ノードごとに Azure Defender for Servers ライセンスが必要です[。「Azure Defender](/azure/security-center/security-center-services)で利用可能なサポートされる機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d65-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="29d65-126">オプション 1: インストールと構成を行 Microsoft Monitoring Agentってオンボードする (MMA)</span><span class="sxs-lookup"><span data-stu-id="29d65-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="29d65-127">センサー データを Defender for Endpoint に報告するには、Windowsサーバー用に MMA をインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d65-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="29d65-128">詳細については [、「Azure Log Analytics エージェントを使用してログ データを収集する」を参照してください](/azure/azure-monitor/platform/log-analytics-agent)。</span><span class="sxs-lookup"><span data-stu-id="29d65-128">For more information, see [Collect log data with Azure Log Analytics agent](/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="29d65-129">System Center Operations Manager (SCOM) または Azure Monitor (旧称:Operations Management Suite (OMS)) を既に使用している場合は、Microsoft Monitoring Agent (MMA) を添付して、マルチホミング サポートを通じて Defender for Endpoint ワークスペースに報告します。</span><span class="sxs-lookup"><span data-stu-id="29d65-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="29d65-130">一般に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d65-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="29d65-131">「始める前に」で説明されているオンボーディング要件 **を満た** します。</span><span class="sxs-lookup"><span data-stu-id="29d65-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="29d65-132">ポータルからサーバーの監視Microsoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="29d65-132">Turn on server monitoring from Microsoft 365 Defender portal.</span></span>
3. <span data-ttu-id="29d65-133">センサー データを Defender for Endpoint に報告するサーバーの MMA をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="29d65-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="29d65-134">クライアントの構成と更新System Center Endpoint Protectionします。</span><span class="sxs-lookup"><span data-stu-id="29d65-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="29d65-135">デバイスのオンボード後、検出テストを実行して、サービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="29d65-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="29d65-136">詳細については、「新しくオンボードされた Defender for Endpoint エンドポイントで検出テストを実行 [する」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="29d65-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="29d65-137">開始する前に</span><span class="sxs-lookup"><span data-stu-id="29d65-137">Before you begin</span></span>

<span data-ttu-id="29d65-138">オンボーディング要件を満たすために、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="29d65-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="29d65-139">Windows Server 2008 R2 SP1 または R2 のWindows Server 2012、次の修正プログラムをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="29d65-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="29d65-140">カスタマー エクスペリエンスと診断テレメトリの更新</span><span class="sxs-lookup"><span data-stu-id="29d65-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="29d65-141">Server 2008 R2 SP1 Windows、次の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29d65-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="29d65-142">2 [月の月次更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="29d65-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="29d65-143">[.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする</span><span class="sxs-lookup"><span data-stu-id="29d65-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="29d65-144">SCCM を使用して Windows Server 2008 R2 SP1 を管理している場合、SCCM クライアント エージェントは .Net Framework 4.5.2 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="29d65-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="29d65-145">そのため、.NET framework 4.5 (以降) をインストールする必要はないので、</span><span class="sxs-lookup"><span data-stu-id="29d65-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="29d65-146">サーバー Windows 2008 R2 SP1 および Windows Server 2012 R2 の場合: クライアントSystem Center Endpoint Protection[構成および更新します](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="29d65-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="29d65-147">この手順は、組織で System Center Endpoint Protection (SCEP) を使用し、Windows Server 2008 R2 SP1 および R2 をオンボーディングする場合Windows Server 2012です。</span><span class="sxs-lookup"><span data-stu-id="29d65-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="29d65-148">センサー データを Microsoft Defender for Endpoint にMicrosoft Monitoring Agentレポートするデバイス (MMA) をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="29d65-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="29d65-149">エージェント セットアップ ファイルをダウンロードします[。Windows 64 ビット エージェントをダウンロードします](https://go.microsoft.com/fwlink/?LinkId=828603)。</span><span class="sxs-lookup"><span data-stu-id="29d65-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="29d65-150">前の手順で取得した Workspace ID と Workspace キーを使用して、次のインストール方法を選択して、エージェントをサーバーにインストールWindowsします。</span><span class="sxs-lookup"><span data-stu-id="29d65-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="29d65-151">[セットアップを使用してエージェントを手動でインストールします](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。</span><span class="sxs-lookup"><span data-stu-id="29d65-151">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="29d65-152">[エージェント **のセットアップ オプション]** ページで、[エージェント **Connect Azure Log Analytics (OMS) に移動する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="29d65-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="29d65-153">[コマンド ラインを使用してエージェントをインストールします](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。</span><span class="sxs-lookup"><span data-stu-id="29d65-153">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="29d65-154">[スクリプトを使用してエージェントを構成します](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。</span><span class="sxs-lookup"><span data-stu-id="29d65-154">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="29d65-155">米国政府機関のお客様[](gov.md)の場合は、[Azure Cloud] の下で、セットアップ ウィザードを使用する場合は "Azure US Government" を選択するか、コマンド ラインまたはスクリプトを使用する場合は、"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d65-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="29d65-156">必要にWindowsサーバー プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="29d65-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="29d65-157">サーバーが Defender for Endpoint と通信するためにプロキシを使用する必要がある場合は、次のいずれかの方法を使用して、プロキシ サーバーを使用する MMA を構成します。</span><span class="sxs-lookup"><span data-stu-id="29d65-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="29d65-158">プロキシ サーバーを使用する MMA を構成する</span><span class="sxs-lookup"><span data-stu-id="29d65-158">Configure the MMA to use a proxy server</span></span>](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="29d65-159">すべてのWindowsプロキシ サーバーを使用するサーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="29d65-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="29d65-160">プロキシまたはファイアウォールが使用されている場合は、サーバーが SSL インターセプトなしで直接 Microsoft Defender for Endpoint サービス URL にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="29d65-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="29d65-161">詳細については、「Defender for Endpoint Service URL へのアクセス [を有効にする」を参照してください](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="29d65-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="29d65-162">SSL インターセプトを使用すると、システムは Defender for Endpoint サービスと通信できません。</span><span class="sxs-lookup"><span data-stu-id="29d65-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="29d65-163">完了すると、1 時間以内にポータルにオンボード Windowsサーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="29d65-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="29d65-164">オプション 2: Azure セキュリティ センター Windowsサーバーをオンボードする</span><span class="sxs-lookup"><span data-stu-id="29d65-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="29d65-165">[デバイスのMicrosoft 365 Defender] ウィンドウで、[エンドポイント **デバイス** 設定  >    >  **オンボーディング]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="29d65-165">In the Microsoft 365 Defender navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="29d65-166">オペレーティング **Windowsサーバー 2008 R2 SP1、2012 R2、2016** を選択します。</span><span class="sxs-lookup"><span data-stu-id="29d65-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="29d65-167">**[Azure セキュリティ センターのオンボード サーバー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="29d65-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="29d65-168">[「Microsoft Defender for Endpoint with Azure Defender」](/azure/security-center/security-center-wdatp)のオンボーディング手順に従い、Azure ARC を使用している場合は[、「Microsoft Defender for](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)Endpoint 統合を有効にする」のオンボーディング手順に従います。</span><span class="sxs-lookup"><span data-stu-id="29d65-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="29d65-169">オンボーディングの手順を完了した後、クライアントの構成と[更新System Center Endpoint Protection必要があります](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="29d65-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="29d65-170">Azure Defender for Servers によるオンボーディングが期待通り動作するには、サーバーに適切なワークスペースとキーが構成されている必要があります。Microsoft Monitoring Agent (MMA) の設定で構成します。</span><span class="sxs-lookup"><span data-stu-id="29d65-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="29d65-171">構成が完了すると、適切なクラウド管理パックがコンピューターに展開され、センサー プロセス (MsSenseS.exe) が展開され、開始されます。</span><span class="sxs-lookup"><span data-stu-id="29d65-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="29d65-172">これは、サーバーが OMS ゲートウェイ サーバーをプロキシとして使用するように構成されている場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="29d65-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="29d65-173">オプション 3: Windows 2002 以降Microsoft エンドポイント マネージャーサーバーにオンボードする</span><span class="sxs-lookup"><span data-stu-id="29d65-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="29d65-174">R2 と Windows Server 2012バージョン 2002 以降Windows Server 2016使用Microsoft エンドポイント マネージャーオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="29d65-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="29d65-175">詳細については[、「Microsoft Defender for Endpoint in Microsoft エンドポイント マネージャー」を参照してください](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="29d65-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="29d65-176">オンボーディングの手順を完了した後、クライアントの構成と[更新System Center Endpoint Protection必要があります](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="29d65-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="29d65-177">Windowsサーバー (SAC) バージョン 1803、Windows Server 2019、Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="29d65-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="29d65-178">次の展開方法を使用して、Windows Server (SAC) バージョン 1803、Windows Server 2019、または Windows Server 2019 Core Edition をオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="29d65-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="29d65-179">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="29d65-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="29d65-180">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="29d65-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="29d65-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="29d65-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="29d65-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="29d65-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="29d65-183">永続的でないデバイスの VDI オンボーディング スクリプト</span><span class="sxs-lookup"><span data-stu-id="29d65-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="29d65-184">現在、スクリプトがWindowsサーバー 2019 Microsoft エンドポイント マネージャーオンボーディング パッケージ。</span><span class="sxs-lookup"><span data-stu-id="29d65-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="29d65-185">Configuration Manager でスクリプトを展開する方法の詳細については、「Configuration Manager の [パッケージとプログラム」を参照してください](/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="29d65-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="29d65-186">ローカル スクリプトは概念実証に適していますが、実稼働展開には使用できません。</span><span class="sxs-lookup"><span data-stu-id="29d65-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="29d65-187">実稼働展開の場合は、グループ ポリシーまたはグループ ポリシーを使用Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="29d65-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="29d65-188">サーバーのWindowsは、サーバーアクティビティ、カーネル攻撃とメモリ攻撃検出の範囲に関するより深い洞察を提供し、応答アクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="29d65-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="29d65-189">デバイスの同じツールとメソッドを使用して、Windows サーバー上の Defender for Endpoint オンボーディング設定をWindows 10します。</span><span class="sxs-lookup"><span data-stu-id="29d65-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="29d65-190">詳細については、「Onboard [Windows 10 デバイス」を参照してください](configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="29d65-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="29d65-191">サードパーティのマルウェア対策ソリューションを実行している場合は、次の Microsoft Defender AV パッシブ モード設定を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d65-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="29d65-192">正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29d65-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="29d65-193">次のレジストリ エントリを設定します。</span><span class="sxs-lookup"><span data-stu-id="29d65-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="29d65-194">パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="29d65-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="29d65-195">名前: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="29d65-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="29d65-196">種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="29d65-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="29d65-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="29d65-197">Value: 1</span></span>

    1. <span data-ttu-id="29d65-198">次の PowerShell コマンドを実行して、パッシブ モードが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29d65-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="29d65-199">パッシブ モード イベントを含む最近のイベントが見つかったこと確認します。</span><span class="sxs-lookup"><span data-stu-id="29d65-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![パッシブ モード検証結果のイメージ](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="29d65-201">次のコマンドを実行して、Microsoft Defender AV がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29d65-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="29d65-202">結果が '指定されたサービスがインストールされたサービスとして存在しない' の場合は、Microsoft Defender AV をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d65-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="29d65-203">詳細については[、「Microsoft Defender ウイルス対策」をWindows 10。](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="29d65-203">For more information, see [Microsoft Defender Antivirus in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="29d65-204">グループ ポリシーを使用 Microsoft Defender ウイルス対策して Windows サーバーでグループ ポリシーを構成および管理する方法については、「グループ ポリシー設定を使用してグループ ポリシーを構成および管理する」を参照[Microsoft Defender ウイルス対策。](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="29d65-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="29d65-205">Azure Defender との統合</span><span class="sxs-lookup"><span data-stu-id="29d65-205">Integration with Azure Defender</span></span>

<span data-ttu-id="29d65-206">Defender for Endpoint は、Azure Defender と統合して、包括的なサーバー保護Windows提供できます。</span><span class="sxs-lookup"><span data-stu-id="29d65-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="29d65-207">この統合により、Azure Defender は Defender for Endpoint の機能を使用して、サーバーの脅威検出を強化Windowsできます。</span><span class="sxs-lookup"><span data-stu-id="29d65-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="29d65-208">この統合には、次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29d65-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="29d65-209">自動オンボーディング - Defender for Endpoint センサーは、Azure Defender にオンボードWindowsサーバーで自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="29d65-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="29d65-210">Azure Defender オンボーディングの詳細については、「統合 Microsoft Defender for Endpoint ライセンスを使用する [」を参照してください](/azure/security-center/security-center-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="29d65-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="29d65-211">Azure Defender for Servers と Microsoft Defender for Endpoint の統合は[、Windows Server 2019 と Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)をサポートするように拡張されました。</span><span class="sxs-lookup"><span data-stu-id="29d65-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="29d65-212">Windows監視されるサーバーは、Defender for Endpoint でも利用できます 。 Azure Defender は Defender for Endpoint テナントにシームレスに接続し、クライアントとサーバー間で 1 つのビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="29d65-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="29d65-213">さらに、Defender for Endpoint アラートは Azure Defender コンソールで利用できます。</span><span class="sxs-lookup"><span data-stu-id="29d65-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="29d65-214">サーバー調査 - Azure Defender のお客様は、Microsoft 365 Defenderポータルにアクセスして詳細な調査を実行し、潜在的な侵害の範囲を明らかにできます。</span><span class="sxs-lookup"><span data-stu-id="29d65-214">Server investigation -  Azure Defender customers can access Microsoft 365 Defender portal to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="29d65-215">Azure Defender を使用してサーバーを監視すると、Defender for Endpoint テナントが自動的に作成されます (米国のユーザーは米国、EU ではヨーロッパおよび英国のユーザー)。</span><span class="sxs-lookup"><span data-stu-id="29d65-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="29d65-216">Defender for Endpoint によって収集されたデータは、プロビジョニング中に特定されたテナントの地理的位置に格納されます。</span><span class="sxs-lookup"><span data-stu-id="29d65-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="29d65-217">Azure Defender を使用する前に Defender for Endpoint を使用する場合、後で Azure Defender と統合した場合でも、テナントの作成時に指定した場所にデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="29d65-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="29d65-218">構成が完了すると、データの保存場所を変更できません。</span><span class="sxs-lookup"><span data-stu-id="29d65-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="29d65-219">データを別の場所に移動する必要がある場合は、Microsoft サポートに問い合わせ、テナントをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d65-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="29d65-220">この統合を利用したサーバー エンドポイントの監視は、ユーザーのOffice 365 GCCされています。</span><span class="sxs-lookup"><span data-stu-id="29d65-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="29d65-221">クライアントの構成と更新System Center Endpoint Protectionする</span><span class="sxs-lookup"><span data-stu-id="29d65-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="29d65-222">Defender for Endpoint は、エンドポイントとSystem Center Endpoint Protection。</span><span class="sxs-lookup"><span data-stu-id="29d65-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="29d65-223">この統合により、マルウェアの検出を可視化し、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内の攻撃の伝達を停止できます。</span><span class="sxs-lookup"><span data-stu-id="29d65-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="29d65-224">この統合を有効にするには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="29d65-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="29d65-225">[2017 年 1](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)月のマルウェア対策プラットフォーム更新プログラムをクライアントEndpoint Protectionします。</span><span class="sxs-lookup"><span data-stu-id="29d65-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="29d65-226">[SCEP クライアント Cloud Protection Service メンバーシップを Advanced](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 設定に **構成** します。</span><span class="sxs-lookup"><span data-stu-id="29d65-226">[Configure the SCEP client Cloud Protection Service membership](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="29d65-227">オフボード Windows サーバー</span><span class="sxs-lookup"><span data-stu-id="29d65-227">Offboard Windows servers</span></span>

<span data-ttu-id="29d65-228">Windows クライアント デバイスで使用できるのと同じ方法で、Windows サーバー (SAC)、Windows Server 2019、および Windows Server 2019 Core edition をオフボードWindows 10できます。</span><span class="sxs-lookup"><span data-stu-id="29d65-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="29d65-229">他のサーバー Windowsの場合は、サービスからサーバーをオフボードWindows 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="29d65-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="29d65-230">MMA エージェントのアンインストール</span><span class="sxs-lookup"><span data-stu-id="29d65-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="29d65-231">Defender for Endpoint ワークスペース構成を削除する</span><span class="sxs-lookup"><span data-stu-id="29d65-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="29d65-232">オフボードにより、Windows サーバーはセンサー データのポータルへの送信を停止しますが、Windows サーバーからのデータ (通知への参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="29d65-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="29d65-233">MMA Windowsをアンインストールして、サーバーをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="29d65-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="29d65-234">サーバーをオフWindowsするには、MMA エージェントを Windows サーバーからアンインストールするか、レポートから Defender for Endpoint ワークスペースに切り離します。</span><span class="sxs-lookup"><span data-stu-id="29d65-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="29d65-235">エージェントのオフボード後、Windowsサーバーは Defender for Endpoint にセンサー データを送信しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="29d65-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="29d65-236">詳細については、「エージェントを無効 [にするには」を参照してください](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。</span><span class="sxs-lookup"><span data-stu-id="29d65-236">For more information, see [To disable an agent](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="29d65-237">Defender for Endpoint ワークスペース構成を削除する</span><span class="sxs-lookup"><span data-stu-id="29d65-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="29d65-238">サーバーをオフボードWindows、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="29d65-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="29d65-239">DEFENDER for Endpoint ワークスペース構成を MMA エージェントから削除する</span><span class="sxs-lookup"><span data-stu-id="29d65-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="29d65-240">PowerShell コマンドを実行して構成を削除する</span><span class="sxs-lookup"><span data-stu-id="29d65-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="29d65-241">DEFENDER for Endpoint ワークスペース構成を MMA エージェントから削除する</span><span class="sxs-lookup"><span data-stu-id="29d65-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="29d65-242">[プロパティ **Microsoft Monitoring Agent] で\*\*\*\*、[Azure Log Analytics (OMS) タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="29d65-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="29d65-243">[Defender for Endpoint] ワークスペースを選択し、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="29d65-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![プロパティのMicrosoft Monitoring Agent画像](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="29d65-245">PowerShell コマンドを実行して構成を削除する</span><span class="sxs-lookup"><span data-stu-id="29d65-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="29d65-246">ワークスペース ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="29d65-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="29d65-247">[デバイスのMicrosoft 365 Defender] ウィンドウで、[エンドポイント **デバイス** 設定  >    >  **オンボーディング]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="29d65-247">In the Microsoft 365 Defender navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

   1. <span data-ttu-id="29d65-248">オペレーティング **システムWindows Server 2008 R2 SP1、2012 R2、2016** を選択し、ワークスペース ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="29d65-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![サーバーオンボーディングWindowsイメージ](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="29d65-250&quot;>管理者特権の PowerShell を開き、次のコマンドを実行します。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;29d65-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;29d65-251&quot;>取得して置き換えたワークスペース ID を使用します `WorkspaceID` 。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;29d65-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="29d65-252">管理ソリューションを使用してサーバーをオンボーディングする</span><span class="sxs-lookup"><span data-stu-id="29d65-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="29d65-253">グループ ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="29d65-253">Using Group Policy</span></span>

<span data-ttu-id="29d65-254">**手順-1: サーバーにコピーするために必要なファイルを作成します。**</span><span class="sxs-lookup"><span data-stu-id="29d65-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="29d65-255">c:\windows\sysvol\domain\scripts に移動します (ドメイン コントローラーの 1 つで変更コントロールが必要になる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="29d65-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="29d65-256">MMA という名前のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29d65-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="29d65-257">以下をダウンロードし、MMA フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="29d65-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="29d65-258">**カスタマー エクスペリエンスと診断テレメトリの更新 (Windows Server 2008 R2 および Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="29d65-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="29d65-259">2008 Windows R2 x64 の場合</span><span class="sxs-lookup"><span data-stu-id="29d65-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="29d65-260">2012 Windows R2 x64 の場合</span><span class="sxs-lookup"><span data-stu-id="29d65-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="29d65-261">この記事では、x64 ベースのサーバー (MMA エージェント .exe X64 新 [しい SHA-2 準拠バージョン) を使用している必要があります](https://go.microsoft.com/fwlink/?LinkId=828603)。</span><span class="sxs-lookup"><span data-stu-id="29d65-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="29d65-262">**手順-2: ファイル名 DeployMMA.cmd を作成する (メモ帳を使用)** cmd ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="29d65-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="29d65-263">ワークスペース ID と KEY が必要です。</span><span class="sxs-lookup"><span data-stu-id="29d65-263">Note that you'll need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="29d65-264">グループ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="29d65-264">Group Policy Configuration</span></span>

<span data-ttu-id="29d65-265">「Microsoft Defender for Endpoint Onboarding」などのオンボード デバイス専用の新しいグループ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29d65-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="29d65-266">"c:\windows\MMA" という名前のグループ ポリシー フォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="29d65-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="フォルダー":::

    <span data-ttu-id="29d65-268">**これにより、GPO が適用され、MMA と呼ばれるすべてのサーバーに新しいフォルダーが追加され、c:\windows に格納されます。これには、MMA、前提条件、およびインストール スクリプトのインストール ファイルが含まれる。**</span><span class="sxs-lookup"><span data-stu-id="29d65-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="29d65-269">Net ログオンに格納されている各ファイルのグループ ポリシー ファイルの基本設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="29d65-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="グループ ポリシーイメージ1":::

<span data-ttu-id="29d65-271">DOMAIN\NETLOGON\MMA\filename から C:\windows\MMA\filename にファイルをコピーします。そのため、インストール ファイルはサーバー **にローカルです**。</span><span class="sxs-lookup"><span data-stu-id="29d65-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="mma cmd を展開する":::

<span data-ttu-id="29d65-273">2 つの KB (1 つは Windows Server 2008R2/Windows 7、もう 1 つは Windows Server 2012 R2) の場合は、このプロセスを繰り返しますが、[COMMON] タブでアイテム レベルのターゲット設定を作成します。そのため、ファイルはスコープ内の適切なプラットフォーム/オペレーティング システム バージョンにのみコピーされます。</span><span class="sxs-lookup"><span data-stu-id="29d65-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="ターゲット エディター":::

- <span data-ttu-id="29d65-275">サーバー 2008 R2 Windows Windows6.1-BJ3080149-x64.msu が必要です (コピーダウンのみ)</span><span class="sxs-lookup"><span data-stu-id="29d65-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="29d65-276">たとえばWindows Server 2012 R2 Windows8.1-BJ3080149-x64.msu が必要です (コピーダウンのみ)。</span><span class="sxs-lookup"><span data-stu-id="29d65-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="29d65-277">これが完了したら、起動スクリプト ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d65-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="プロパティの起動":::

<span data-ttu-id="29d65-279">ここで実行するファイルの名前は c:\windows\MMA\DeployMMA.cmd です。</span><span class="sxs-lookup"><span data-stu-id="29d65-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="29d65-280">サーバーが起動プロセスの一部として再起動すると、カスタマー エクスペリエンスと診断テレメトリ KB の更新プログラムがインストールされ、MMA エージェントがインストールされ、ワークスペース ID とキーが設定され、サーバーがオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="29d65-280">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="29d65-281">すべてのサーバーを再起動 **しない** 場合は、即時タスクを使用して deployMMA.cmd を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="29d65-281">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="29d65-282">これは、2 つのフェーズで実行できます。</span><span class="sxs-lookup"><span data-stu-id="29d65-282">This could be done in two phases.</span></span> <span data-ttu-id="29d65-283">まず **、GPO でファイルと** フォルダーを作成します。GPO が適用され、すべてのサーバーにインストール ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="29d65-283">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="29d65-284">次に、イミディエイト タスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="29d65-284">Then, add the immediate task.</span></span> <span data-ttu-id="29d65-285">これにより、再起動を必要とせずに同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="29d65-285">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="29d65-286">スクリプトは exit メソッドを持ち、MMA がインストールされている場合は再び実行されませんので、毎日スケジュールされたタスクを使用して同じ結果を得る場合も可能です。</span><span class="sxs-lookup"><span data-stu-id="29d65-286">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="29d65-287">Configuration Manager コンプライアンス ポリシーと同様に、MMA が存在しているのを確認するために毎日チェックされます。</span><span class="sxs-lookup"><span data-stu-id="29d65-287">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="スケジュール タスク":::

:::image type="content" source="images/newtaskprops.png" alt-text="新しいタスクのプロパティ":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="mma ダウンロード の小道具を展開する":::

:::image type="content" source="images/tasksch.png" alt-text="タスク スケジューラ":::

<span data-ttu-id="29d65-292">Server 2008 R2 のオンボーディングに関するドキュメントで特に説明したように、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d65-292">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="29d65-293">サーバー Windows 2008 R2 PS1 の場合は、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="29d65-293">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="29d65-294">[2018 年 2 月の更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="29d65-294">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="29d65-295">[.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする</span><span class="sxs-lookup"><span data-stu-id="29d65-295">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="29d65-296">Windows Server 2008 R2 をオンボーディングする前に、KB が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d65-296">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="29d65-297">関連項目</span><span class="sxs-lookup"><span data-stu-id="29d65-297">Related topics</span></span>

- [<span data-ttu-id="29d65-298">Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="29d65-298">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="29d65-299">Windows 以外のデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="29d65-299">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="29d65-300">プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="29d65-300">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="29d65-301">新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="29d65-301">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="29d65-302">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="29d65-302">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
