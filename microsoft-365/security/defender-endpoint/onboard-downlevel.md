---
title: Microsoft Defender for Endpoint の以前Windowsバージョンのオンボード
description: センサー データを Microsoft Defender for Endpoint センサーに送信Windows以前のバージョンのデバイスをオンボードでサポート
keywords: オンボード、Windows、7、81、oms、sp1、enterprise、pro、down level
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 945645e0f20f316c094f746adb6ba193f6806f86
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861361"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="e56f5-104">以前のバージョンの Windows をオンボードする</span><span class="sxs-lookup"><span data-stu-id="e56f5-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e56f5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e56f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="e56f5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e56f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e56f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e56f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="e56f5-108">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="e56f5-108">**Platforms**</span></span>
- <span data-ttu-id="e56f5-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e56f5-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="e56f5-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="e56f5-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="e56f5-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="e56f5-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="e56f5-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e56f5-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="e56f5-113">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e56f5-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="e56f5-114">[無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="e56f5-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="e56f5-115">Defender for Endpoint は、ダウンレベルのオペレーティング システムを含むサポートを拡張し、サポートされているバージョンの高度な攻撃検出と調査Windowsします。</span><span class="sxs-lookup"><span data-stu-id="e56f5-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="e56f5-116">クライアント エンドポイントのダウンレベル Windows Defender for Endpoint にオンボードするには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="e56f5-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="e56f5-117">クライアントの構成と更新System Center Endpoint Protectionします。</span><span class="sxs-lookup"><span data-stu-id="e56f5-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="e56f5-118">以下に示すMicrosoft Monitoring Agent、センサー データを Defender for Endpoint に報告するように、センサー データ (MMA) をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="e56f5-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="e56f5-119">デバイスのオンボード後、検出テストを実行して、サービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e56f5-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="e56f5-120">詳細については、「新しくオンボードされた Defender for Endpoint エンドポイントで検出テストを実行 [する」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="e56f5-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="e56f5-121">クライアントの構成と更新System Center Endpoint Protectionする</span><span class="sxs-lookup"><span data-stu-id="e56f5-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="e56f5-122">この手順は、組織が SCEP (SCEP) System Center Endpoint Protection必要です。</span><span class="sxs-lookup"><span data-stu-id="e56f5-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="e56f5-123">Defender for Endpoint は System Center Endpoint Protection と統合し、マルウェアの検出を可視化し、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内の攻撃の伝達を停止します。</span><span class="sxs-lookup"><span data-stu-id="e56f5-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="e56f5-124">この統合を有効にするには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="e56f5-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="e56f5-125">[2017 年 1](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)月のマルウェア対策プラットフォーム更新プログラムをクライアントEndpoint Protectionする</span><span class="sxs-lookup"><span data-stu-id="e56f5-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="e56f5-126">SCEP クライアント Cloud Protection Service メンバーシップを詳細設定に **構成** する</span><span class="sxs-lookup"><span data-stu-id="e56f5-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="e56f5-127">クラウドへの接続を許可するネットワークMicrosoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="e56f5-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="e56f5-128">詳細については、「Allow [connections to the Microsoft Defender ウイルス対策 クラウド」を参照してください。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="e56f5-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e56f5-129">センサー データを Microsoft Defender for Endpoint にMicrosoft Monitoring Agentレポートするデバイス (MMA) をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="e56f5-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="e56f5-130">はじめに</span><span class="sxs-lookup"><span data-stu-id="e56f5-130">Before you begin</span></span>
<span data-ttu-id="e56f5-131">最小システム要件を確認するには、次の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="e56f5-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="e56f5-132">[2018 年 2 月の更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="e56f5-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="e56f5-133">7 SP1 および 7 SP1 Windows 7 SP1 EnterpriseおよびWindowsにのみPro。</span><span class="sxs-lookup"><span data-stu-id="e56f5-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="e56f5-134">カスタマー エクスペリエンス [と診断テレメトリの更新プログラムをインストールする](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="e56f5-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="e56f5-135">[.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする</span><span class="sxs-lookup"><span data-stu-id="e56f5-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="e56f5-136">7 SP1 および 7 SP1 Windows 7 SP1 EnterpriseおよびWindowsにのみPro。</span><span class="sxs-lookup"><span data-stu-id="e56f5-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="e56f5-137">上記のインストールを.NET Framework 4.0.x にはインストールしない。</span><span class="sxs-lookup"><span data-stu-id="e56f5-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="e56f5-138">Azure Log Analytics エージェントの最小システム要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="e56f5-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="e56f5-139">詳細については、「Log Analytics を使用して環境内のコンピューターからデータ [を収集する」を参照してください。](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="e56f5-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="e56f5-140">エージェント セットアップ ファイルをダウンロードします[Windows 64 ビット](https://go.microsoft.com/fwlink/?LinkId=828603)エージェントまたは[32 ビット Windowsエージェントをダウンロードします](https://go.microsoft.com/fwlink/?LinkId=828604)。</span><span class="sxs-lookup"><span data-stu-id="e56f5-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="e56f5-141">ワークスペース ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="e56f5-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="e56f5-142">[Defender for Endpoint] ナビゲーション ウィンドウで、[デバイス設定 >**オンボーディング>選択します。**</span><span class="sxs-lookup"><span data-stu-id="e56f5-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="e56f5-143">オペレーティング **Windows 7 SP1 と 8.1** を選択する</span><span class="sxs-lookup"><span data-stu-id="e56f5-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="e56f5-144">ワークスペース ID とワークスペース キーをコピーする</span><span class="sxs-lookup"><span data-stu-id="e56f5-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="e56f5-145">Workspace ID と Workspace キーを使用して、次のインストール方法を選択してエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e56f5-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="e56f5-146">[セットアップを使用してエージェントを手動でインストールします](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。</span><span class="sxs-lookup"><span data-stu-id="e56f5-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="e56f5-147">[エージェント **のセットアップ オプション]** ページで、[エージェント **Connect Azure Log Analytics (OMS) に移動する] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="e56f5-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="e56f5-148">[コマンド ラインを使用してエージェントをインストールします](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。</span><span class="sxs-lookup"><span data-stu-id="e56f5-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="e56f5-149">[スクリプトを使用してエージェントを構成します](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。</span><span class="sxs-lookup"><span data-stu-id="e56f5-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e56f5-150">米国政府機関のお客様[](gov.md)の場合は、[Azure Cloud] の下で、セットアップ ウィザードを使用する場合は "Azure US Government" を選択するか、コマンド ラインまたはスクリプトを使用する場合は、"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e56f5-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="e56f5-151">プロキシを使用してインターネットに接続する場合は、「プロキシ設定の構成」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e56f5-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="e56f5-152">完了すると、1 時間以内にポータルにオンボード エンドポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e56f5-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="e56f5-153">プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="e56f5-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="e56f5-154">各Windows HTTPS を使用してインターネットに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e56f5-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="e56f5-155">この接続は、直接、プロキシを使用するか [、OMS ゲートウェイを介して行います](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)。</span><span class="sxs-lookup"><span data-stu-id="e56f5-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="e56f5-156">プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックしており、特定のドメインのみを許可している場合や HTTPS スキャン (SSL 検査) が有効になっている場合は [、Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)Service URL へのアクセスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="e56f5-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="e56f5-157">オフボード クライアント エンドポイント</span><span class="sxs-lookup"><span data-stu-id="e56f5-157">Offboard client endpoints</span></span>
<span data-ttu-id="e56f5-158">オフボードには、エンドポイントから MMA エージェントをアンインストールするか、レポートから Defender for Endpoint ワークスペースに切り離します。</span><span class="sxs-lookup"><span data-stu-id="e56f5-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="e56f5-159">エージェントのオフボード後、エンドポイントはセンサー データを Defender for Endpoint に送信しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e56f5-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="e56f5-160">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e56f5-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="e56f5-161">[無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)。</span><span class="sxs-lookup"><span data-stu-id="e56f5-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

