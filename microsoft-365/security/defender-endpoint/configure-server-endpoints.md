---
title: Windows サーバーを Microsoft Defender for Endpoint サービスにオンボードする
description: センサー データを Microsoft Defender for Endpoint センサーに送信できるよう、Windows サーバーをオンボードします。
keywords: オンボード サーバー、サーバー、2012r2、2016、2019、サーバーオンボーディング、デバイス管理、Windows ATP サーバーの構成、Microsoft Defender for Endpoint サーバーのオンボード、Microsoft Defender for Endpoint サーバーのオンボード
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
ms.openlocfilehash: 1757160b37500e97586fbb6dfb16d81303bc54e4
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476483"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="5b40c-104">Windows サーバーを Microsoft Defender for Endpoint サービスにオンボードする</span><span class="sxs-lookup"><span data-stu-id="5b40c-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5b40c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5b40c-105">**Applies to:**</span></span>

- <span data-ttu-id="5b40c-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="5b40c-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="5b40c-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5b40c-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="5b40c-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5b40c-108">Windows Server 2016</span></span>
- <span data-ttu-id="5b40c-109">Windows Server (SAC) バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="5b40c-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="5b40c-110">Windows Server 2019 以降</span><span class="sxs-lookup"><span data-stu-id="5b40c-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="5b40c-111">Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="5b40c-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="5b40c-112">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="5b40c-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5b40c-113">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="5b40c-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


<span data-ttu-id="5b40c-114">Defender for Endpoint は、Windows Server オペレーティング システムも含むサポートを拡張します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="5b40c-115">このサポートは、Microsoft Defender セキュリティ センター コンソールを通じて、高度な攻撃検出および調査機能をシームレスに提供します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="5b40c-116">ライセンスとインフラストラクチャに必要な機能に関する実践的なガイダンスについては、「Defender for Endpoint を使用して Windows サーバーを保護する [」を参照してください](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="5b40c-117">Windows サーバーの Windows セキュリティ ベースラインをダウンロードして使用する方法のガイダンスについては [、「Windows セキュリティ ベースライン」を参照してください](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="5b40c-118">Windows Server 2008 R2 SP1、Windows Server 2012 R2、および Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5b40c-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="5b40c-119">次のオプションWindows Server 2008 R2使用して、SP1、Windows Server 2012 R2、Windows Server 2016 を Defender for Endpoint にオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="5b40c-120">**オプション 1**: [Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)のインストールと構成によるオンボード</span><span class="sxs-lookup"><span data-stu-id="5b40c-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="5b40c-121">**オプション 2**: [Azure セキュリティ センター経由でオンボードする](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="5b40c-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="5b40c-122">**オプション 3**: [Microsoft Endpoint Manager バージョン 2002](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)以降のオンボード</span><span class="sxs-lookup"><span data-stu-id="5b40c-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>


<span data-ttu-id="5b40c-123">指定されたオプションを使用してオンボーディング手順を完了した後、System Center Endpoint Protection クライアントを構成および [更新する必要があります](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>


> [!NOTE]
> <span data-ttu-id="5b40c-124">Microsoft Monitoring Agent (オプション 1) または Microsoft Endpoint Manager (オプション 3) を介して Windows サーバーをオンボードするには、ノードごとに Defender for Endpoint スタンドアロン サーバー ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="5b40c-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="5b40c-125">または、Azure セキュリティ センター (オプション 2) を介して Windows サーバーをオンボードするには、ノードごとに Azure Defender for Servers ライセンスが必要です [。「Azure](https://docs.microsoft.com/azure/security-center/security-center-services)Security Center で利用可能なサポートされる機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b40c-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="5b40c-126">オプション 1: Microsoft 監視エージェント (MMA) のインストールと構成によるオンボード</span><span class="sxs-lookup"><span data-stu-id="5b40c-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>
<span data-ttu-id="5b40c-127">センサー データを Defender for Endpoint に報告するには、Windows サーバー用の MMA をインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="5b40c-128">詳細については [、「Azure Log Analytics エージェントを使用してログ データを収集する」を参照してください](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="5b40c-129">System Center Operations Manager (SCOM) または Azure Monitor (以前は Operations Management Suite (OMS) と呼ばれる) を既に使用している場合は、Microsoft Monitoring Agent (MMA) を接続して、マルチホミング サポートを通じて Defender for Endpoint ワークスペースに報告します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="5b40c-130">一般に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-130">In general, you'll need to take the following steps:</span></span>
1. <span data-ttu-id="5b40c-131">「始める前に」で説明されているオンボーディング要件 **を満た** します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="5b40c-132">Microsoft Defender セキュリティ センターからサーバーの監視を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5b40c-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="5b40c-133">センサー データを Defender for Endpoint に報告するサーバーの MMA をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="5b40c-134">System Center Endpoint Protection クライアントを構成および更新します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-134">Configure and update System Center Endpoint Protection clients.</span></span>


> [!TIP]
> <span data-ttu-id="5b40c-135">デバイスのオンボード後、検出テストを実行して、サービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="5b40c-136">詳細については、「新しくオンボードされた Defender for Endpoint エンドポイントで検出テストを実行 [する」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>


#### <a name="before-you-begin"></a><span data-ttu-id="5b40c-137">はじめに</span><span class="sxs-lookup"><span data-stu-id="5b40c-137">Before you begin</span></span> 
<span data-ttu-id="5b40c-138">オンボーディング要件を満たすために、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

 - <span data-ttu-id="5b40c-139">SP1 Windows Server 2008 R2 R2 Windows Server 2012、次の修正プログラムをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="5b40c-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>
    - [<span data-ttu-id="5b40c-140">カスタマー エクスペリエンスと診断テレメトリの更新</span><span class="sxs-lookup"><span data-stu-id="5b40c-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - <span data-ttu-id="5b40c-141">さらに、SP1 のWindows Server 2008 R2、次の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-141">In addition, for Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>
    - <span data-ttu-id="5b40c-142">2 [月の月次更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="5b40c-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
    - <span data-ttu-id="5b40c-143">[.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする</span><span class="sxs-lookup"><span data-stu-id="5b40c-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>
   
   > [!NOTE]
    > <span data-ttu-id="5b40c-144">SCCM を使用して SP1 Windows Server 2008 R2管理している場合、SCCM クライアント エージェントは .Net Framework 4.5.2 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5b40c-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="5b40c-145">そのため、.NET framework 4.5 (以降) をインストールする必要はないので、</span><span class="sxs-lookup"><span data-stu-id="5b40c-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>
   
 - <span data-ttu-id="5b40c-146">SP1 Windows Server 2008 R2 R2 のWindows Server 2012: System Center Endpoint Protection クライアント [を構成および更新します](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b40c-147">この手順は、組織で System Center Endpoint Protection (SCEP) を使用し、SP1 および R2 のオンボーディングWindows Server 2008 R2必要Windows Server 2012です。</span><span class="sxs-lookup"><span data-stu-id="5b40c-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="5b40c-148">センサー データを Microsoft Defender for Endpoint に報告する Microsoft Monitoring Agent (MMA) をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="5b40c-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="5b40c-149">エージェント セットアップ ファイル [(Windows 64 ビット](https://go.microsoft.com/fwlink/?LinkId=828603)エージェント) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5b40c-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="5b40c-150">前の手順で取得した Workspace ID と Workspace キーを使用して、Windows サーバーにエージェントをインストールするには、次のインストール方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="5b40c-151">[セットアップを使用してエージェントを手動でインストールします](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
    <span data-ttu-id="5b40c-152">[エージェントの **セットアップ オプション] ページ** で、[ **エージェントを Azure Log Analytics (OMS)** に接続する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="5b40c-153">[コマンド ラインを使用してエージェントをインストールします](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="5b40c-154">[スクリプトを使用してエージェントを構成します](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="5b40c-155">米国政府機関のお客様[](gov.md)の場合は、[Azure Cloud] の下で、セットアップ ウィザードを使用する場合は "Azure US Government" を選択するか、コマンド ラインまたはスクリプトを使用する場合は、"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="5b40c-156">必要に応じて Windows サーバー プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5b40c-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>
<span data-ttu-id="5b40c-157">サーバーが Defender for Endpoint と通信するためにプロキシを使用する必要がある場合は、次のいずれかの方法を使用して、プロキシ サーバーを使用する MMA を構成します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>


- [<span data-ttu-id="5b40c-158">プロキシ サーバーを使用する MMA を構成する</span><span class="sxs-lookup"><span data-stu-id="5b40c-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="5b40c-159">すべての接続にプロキシ サーバーを使用する Windows を構成する</span><span class="sxs-lookup"><span data-stu-id="5b40c-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="5b40c-160">プロキシまたはファイアウォールが使用されている場合は、サーバーが SSL インターセプトなしで直接 Microsoft Defender for Endpoint サービス URL にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="5b40c-161">詳細については、「Defender for Endpoint Service URL へのアクセス [を有効にする」を参照してください](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="5b40c-162">SSL インターセプトを使用すると、システムは Defender for Endpoint サービスと通信できません。</span><span class="sxs-lookup"><span data-stu-id="5b40c-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span> 

<span data-ttu-id="5b40c-163">完了すると、1 時間以内にポータルにオンボード Windows サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="5b40c-164">オプション 2: Azure セキュリティ センターを介して Windows サーバーをオンボードする</span><span class="sxs-lookup"><span data-stu-id="5b40c-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>
1. <span data-ttu-id="5b40c-165">Microsoft Defender Security Center ナビゲーションウィンドウで、[設定] [  >  **デバイス管理オン** ボーディング]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5b40c-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="5b40c-166">オペレーティング **Windows Server 2008 R2 SP1、2012 R2、2016 を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="5b40c-167">**[Azure セキュリティ センターのオンボード サーバー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b40c-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="5b40c-168">Microsoft Defender for Endpoint with [Azure Security Center のオンボーディング手順に従います](https://docs.microsoft.com/azure/security-center/security-center-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

<span data-ttu-id="5b40c-169">オンボーディングの手順を完了した後、System Center [Endpoint Protection クライアントを構成および更新する必要があります](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> - <span data-ttu-id="5b40c-170">Azure Defender for Servers (以前の Azure Security Center Standard Edition) によるオンボーディングが期待通り動作するには、サーバーが Microsoft Monitoring Agent (MMA) 設定内で適切なワークスペースとキーを構成している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-170">For onboarding via Azure Defender for Servers (previously Azure Security Center Standard Edition) to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="5b40c-171">構成が完了すると、適切なクラウド管理パックがコンピューターに展開され、センサー プロセス (MsSenseS.exe) が展開され、開始されます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span> 
> - <span data-ttu-id="5b40c-172">これは、サーバーが OMS ゲートウェイ サーバーをプロキシとして使用するように構成されている場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="5b40c-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="5b40c-173">オプション 3: Microsoft Endpoint Manager バージョン 2002 以降の Windows サーバーをオンボードする</span><span class="sxs-lookup"><span data-stu-id="5b40c-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>
<span data-ttu-id="5b40c-174">Microsoft Endpoint Manager Windows Server 2012 2002 以降を使用して、R2 および Windows Server 2016 をオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="5b40c-175">詳細については [、「Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch」を参照してください](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="5b40c-176">オンボーディングの手順を完了した後、System Center [Endpoint Protection クライアントを構成および更新する必要があります](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="5b40c-177">Windows Server (SAC) バージョン 1803、Windows Server 2019、および Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="5b40c-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>
<span data-ttu-id="5b40c-178">次の展開方法を使用して、Windows Server (SAC) バージョン 1803、Windows Server 2019、または Windows Server 2019 Core Edition をオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="5b40c-179">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="5b40c-179">Local script</span></span>](configure-endpoints-script.md) 
- [<span data-ttu-id="5b40c-180">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="5b40c-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="5b40c-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5b40c-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="5b40c-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="5b40c-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="5b40c-183">永続的でないデバイスの VDI オンボーディング スクリプト</span><span class="sxs-lookup"><span data-stu-id="5b40c-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
> - <span data-ttu-id="5b40c-184">Microsoft Endpoint Manager を介した Windows Server 2019 のオンボーディング パッケージには、現在スクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b40c-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="5b40c-185">Configuration Manager でスクリプトを展開する方法の詳細については、「Configuration Manager の [パッケージとプログラム」を参照してください](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="5b40c-186">ローカル スクリプトは概念実証に適していますが、実稼働展開には使用できません。</span><span class="sxs-lookup"><span data-stu-id="5b40c-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="5b40c-187">実稼働展開の場合は、グループ ポリシーまたは Microsoft Endpoint Configuration Manager を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b40c-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="5b40c-188">Windows Server のサポートは、サーバーアクティビティ、カーネル攻撃とメモリ攻撃検出の範囲に関するより深い洞察を提供し、応答アクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5b40c-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="5b40c-189">Windows 10 デバイス用の同じツールとメソッドを使用して、Windows サーバーの Defender for Endpoint オンボーディング設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="5b40c-190">詳細については、「オンボード [Windows 10 デバイス」を参照してください](configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="5b40c-191">サードパーティのマルウェア対策ソリューションを実行している場合は、次の Microsoft Defender AV パッシブ モード設定を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-191">If you're running a third-party antimalware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="5b40c-192">正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="5b40c-193">次のレジストリ エントリを設定します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="5b40c-194">パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="5b40c-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="5b40c-195">名前: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="5b40c-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="5b40c-196">種類: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="5b40c-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="5b40c-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="5b40c-197">Value: 1</span></span>

    1. <span data-ttu-id="5b40c-198">次の PowerShell コマンドを実行して、パッシブ モードが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="5b40c-199">パッシブ モード イベントを含む最近のイベントが見つかったこと確認します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![パッシブ モード検証結果のイメージ](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="5b40c-201">次のコマンドを実行して、Microsoft Defender AV がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="5b40c-202">結果が '指定されたサービスがインストールされたサービスとして存在しない' の場合は、Microsoft Defender AV をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="5b40c-203">詳細については [、「Microsoft Defender Antivirus in Windows 10」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>
    
    <span data-ttu-id="5b40c-204">Windows サーバーでグループ ポリシーを使用して Microsoft Defender ウイルス対策を構成および管理する方法については、「グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を構成および管理する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

<br>

## <a name="integration-with-azure-security-center"></a><span data-ttu-id="5b40c-205">Azure セキュリティ センターとの統合</span><span class="sxs-lookup"><span data-stu-id="5b40c-205">Integration with Azure Security Center</span></span>
<span data-ttu-id="5b40c-206">Defender for Endpoint は、Azure Security Center と統合して、包括的な Windows サーバー保護ソリューションを提供できます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-206">Defender for Endpoint can integrate with Azure Security Center to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="5b40c-207">この統合により、Azure Security Center は Defender for Endpoint の機能を使用して、Windows サーバーの脅威検出を強化できます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-207">With this integration, Azure Security Center can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="5b40c-208">この統合には、次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b40c-208">The following capabilities are included in this integration:</span></span>
- <span data-ttu-id="5b40c-209">自動オンボーディング - Defender for Endpoint センサーは、Azure セキュリティ センターにオンボードされている Windows サーバーで自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Security Center.</span></span> <span data-ttu-id="5b40c-210">Azure Security Center オンボーディングの詳細については、「強化されたセキュリティのための Azure Security Center Standard へのオンボーディング」 [を参照してください](https://docs.microsoft.com/azure/security-center/security-center-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-210">For more information on Azure Security Center onboarding, see [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b40c-211">Azure Defender for Servers と Microsoft Defender for Endpoint の統合は [、Windows Server 2019 と Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)をサポートするように拡張されました。</span><span class="sxs-lookup"><span data-stu-id="5b40c-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="5b40c-212">Azure Security Center によって監視される Windows サーバーは、Defender for Endpoint - Azure Security Center で Defender for Endpoint テナントにシームレスに接続し、クライアントとサーバー全体で 1 つのビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-212">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="5b40c-213">さらに、Defender for Endpoint アラートは Azure Security Center コンソールで利用できます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-213">In addition, Defender for Endpoint alerts will be available in the Azure Security Center console.</span></span>
- <span data-ttu-id="5b40c-214">サーバー調査 - Azure Security Center のお客様は、Microsoft Defender Security Center にアクセスして詳細な調査を実行して、潜在的な侵害の範囲を明らかにできます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-214">Server investigation -  Azure Security Center customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="5b40c-215">Azure Security Center を使用してサーバーを監視すると、Defender for Endpoint テナントが自動的に作成されます (米国のユーザーは米国、EU ではヨーロッパおよび英国のユーザー)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-215">When you use Azure Security Center to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="5b40c-216">Defender for Endpoint によって収集されたデータは、プロビジョニング中に特定されたテナントの地理的位置に格納されます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="5b40c-217">Azure Security Center を使用する前に Defender for Endpoint を使用する場合、後で Azure Security Center と統合した場合でも、テナントの作成時に指定した場所にデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-217">If you use Defender for Endpoint before using Azure Security Center, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Security Center at a later time.</span></span>
> - <span data-ttu-id="5b40c-218">構成が完了すると、データの保存場所を変更できません。</span><span class="sxs-lookup"><span data-stu-id="5b40c-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="5b40c-219">データを別の場所に移動する必要がある場合は、Microsoft サポートに問い合わせ、テナントをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="5b40c-220">この統合を利用したサーバー エンドポイントの監視は、365 GCC のお客様Office無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5b40c-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="5b40c-221">System Center Endpoint Protection クライアントの構成と更新</span><span class="sxs-lookup"><span data-stu-id="5b40c-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="5b40c-222">Defender for Endpoint は、System Center Endpoint Protection と統合されます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="5b40c-223">この統合により、マルウェアの検出を可視化し、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内の攻撃の伝達を停止できます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="5b40c-224">この統合を有効にするには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="5b40c-224">The following steps are required to enable this integration:</span></span>
- <span data-ttu-id="5b40c-225">Endpoint [Protection クライアント用の 2017 年 1 月のマルウェア対策プラットフォーム更新プログラムをインストールします](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="5b40c-226">[SCEP クライアント Cloud Protection Service メンバーシップを Advanced](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 設定に **構成** します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

<br>

## <a name="offboard-windows-servers"></a><span data-ttu-id="5b40c-227">オフボード Windows サーバー</span><span class="sxs-lookup"><span data-stu-id="5b40c-227">Offboard Windows servers</span></span>
<span data-ttu-id="5b40c-228">Windows Server (SAC)、Windows Server 2019、および Windows Server 2019 Core Edition は、Windows 10 クライアント デバイスで使用できるのと同じ方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="5b40c-229">その他の Windows サーバー バージョンでは、サービスから Windows サーバーをオフボードする 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5b40c-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>
- <span data-ttu-id="5b40c-230">MMA エージェントのアンインストール</span><span class="sxs-lookup"><span data-stu-id="5b40c-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="5b40c-231">Defender for Endpoint ワークスペース構成を削除する</span><span class="sxs-lookup"><span data-stu-id="5b40c-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="5b40c-232">オフボードにより、Windows サーバーはポータルへのセンサー データの送信を停止しますが、Windows サーバーからのデータ (それが持っていたアラートへの参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="5b40c-233">MMA エージェントをアンインストールして Windows サーバーをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="5b40c-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>
<span data-ttu-id="5b40c-234">Windows サーバーをオフボードするには、WINDOWS サーバーから MMA エージェントをアンインストールするか、レポートから Defender for Endpoint ワークスペースに切り離します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="5b40c-235">エージェントのオフボード後、Windows サーバーは Defender for Endpoint にセンサー データを送信しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5b40c-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="5b40c-236">詳細については、「エージェントを無効 [にするには」を参照してください](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。</span><span class="sxs-lookup"><span data-stu-id="5b40c-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="5b40c-237">Defender for Endpoint ワークスペース構成を削除する</span><span class="sxs-lookup"><span data-stu-id="5b40c-237">Remove the Defender for Endpoint workspace configuration</span></span>
<span data-ttu-id="5b40c-238">Windows サーバーをオフボードするには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b40c-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="5b40c-239">DEFENDER for Endpoint ワークスペース構成を MMA エージェントから削除する</span><span class="sxs-lookup"><span data-stu-id="5b40c-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="5b40c-240">PowerShell コマンドを実行して構成を削除する</span><span class="sxs-lookup"><span data-stu-id="5b40c-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="5b40c-241">DEFENDER for Endpoint ワークスペース構成を MMA エージェントから削除する</span><span class="sxs-lookup"><span data-stu-id="5b40c-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="5b40c-242">**[Microsoft 監視エージェントのプロパティ] で\*\*\*\*、[Azure Log Analytics (OMS) ] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="5b40c-243">[Defender for Endpoint] ワークスペースを選択し、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b40c-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Microsoft Monitoring Agent のプロパティのイメージ](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="5b40c-245">PowerShell コマンドを実行して構成を削除する</span><span class="sxs-lookup"><span data-stu-id="5b40c-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="5b40c-246">ワークスペース ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="5b40c-247">ナビゲーション ウィンドウで、[設定オンボーディング]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5b40c-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="5b40c-248">オペレーティング **Windows Server 2008 R2 SP1、2012 R2、2016** を選択し、ワークスペース ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Windows サーバーオンボーディングのイメージ](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="5b40c-250">管理者特権の PowerShell を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b40c-250">Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id="5b40c-251">取得して置き換えたワークスペース ID を使用します `WorkspaceID` 。</span><span class="sxs-lookup"><span data-stu-id="5b40c-251">Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a><span data-ttu-id="5b40c-252">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b40c-252">Related topics</span></span>
- [<span data-ttu-id="5b40c-253">Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="5b40c-253">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="5b40c-254">Windows 以外のデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="5b40c-254">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="5b40c-255">プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5b40c-255">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="5b40c-256">新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="5b40c-256">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="5b40c-257">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5b40c-257">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
