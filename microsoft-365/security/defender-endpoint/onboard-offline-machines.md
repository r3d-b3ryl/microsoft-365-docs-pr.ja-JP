---
title: Microsoft Defender for Endpoint へのインターネット アクセスのないオンボード デバイス
ms.reviewer: ''
description: センサー データを Microsoft Defender for Endpoint センサーに送信できるよう、インターネット にアクセスしないオンボード デバイス
keywords: オンボード、サーバー、VM、オンプレミス、oms ゲートウェイ、ログ分析、Azure ログ分析、mma
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
ms.openlocfilehash: ee06f927579445825a2b2813e483c24357d2ed78
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934923"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="bf6d8-104">Microsoft Defender for Endpoint へのインターネット アクセスのないオンボード デバイス</span><span class="sxs-lookup"><span data-stu-id="bf6d8-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bf6d8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bf6d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf6d8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf6d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf6d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf6d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bf6d8-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="bf6d8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bf6d8-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="bf6d8-110">インターネット にアクセスせずにデバイスをオンボードするには、次の一般的な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="bf6d8-111">以下の手順は、以前のバージョンのデバイス (Windows以前または以前のバージョンWindows Server 2016デバイスWindows 8.1適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="bf6d8-112">「TelemetryProxyServer」レジストリまたは GPO を使用して構成されている場合、接続されていない Windows 10 または Windows Server 2019 デバイスのプロキシとして OMS ゲートウェイ サーバーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="bf6d8-113">サーバー 2019 Windows 10またはWindowsサーバー 2019 では、TelemetryProxyServer を使用する場合は、標準のプロキシ デバイスまたはアプライアンスを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="bf6d8-114">さらに、接続Windows 10環境Windowsサーバー 2019 の証明書信頼リストを、内部ファイルまたは Web サーバーを介してオフラインで更新できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="bf6d8-115">オフラインでの CTL の更新の詳細については、「CTL ファイルをダウンロードするファイルまたは Web サーバーを構成する [」を参照してください](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="bf6d8-116">オンボーディング方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="bf6d8-117">以前のバージョンの Windows をオンボードする</span><span class="sxs-lookup"><span data-stu-id="bf6d8-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="bf6d8-118">Microsoft Defender for Endpoint サービスへのオンボード サーバー</span><span class="sxs-lookup"><span data-stu-id="bf6d8-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="bf6d8-119">デバイス プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="bf6d8-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="bf6d8-120">オンプレミス デバイス</span><span class="sxs-lookup"><span data-stu-id="bf6d8-120">On-premise devices</span></span>

- <span data-ttu-id="bf6d8-121">プロキシまたはハブとして機能するように Azure Log Analytics (以前は OMS Gateway と呼ばれる) をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="bf6d8-122">Azure Log Analytics エージェント</span><span class="sxs-lookup"><span data-stu-id="bf6d8-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="bf6d8-123">エンドポイント ワークスペースキー id Microsoft Monitoring Agent Defender をポイントするコンピューター [(MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)ポイントをインストール&する</span><span class="sxs-lookup"><span data-stu-id="bf6d8-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="bf6d8-124">Azure Log Analytics の同じネットワーク内のオフライン デバイス</span><span class="sxs-lookup"><span data-stu-id="bf6d8-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="bf6d8-125">次の点を示す MMA を構成します。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="bf6d8-126">プロキシとしての Azure Log Analytics IP</span><span class="sxs-lookup"><span data-stu-id="bf6d8-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="bf6d8-127">Defender for Endpoint workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="bf6d8-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="bf6d8-128">Azure 仮想マシン</span><span class="sxs-lookup"><span data-stu-id="bf6d8-128">Azure virtual machines</span></span>
- <span data-ttu-id="bf6d8-129">[Azure Log Analytics ワークスペースの構成と有効化](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="bf6d8-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="bf6d8-130">プロキシまたはハブとして機能するように Azure Log Analytics Gateway (以前は OMS ゲートウェイと呼ばれる) をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="bf6d8-131">Azure Log Analytics Gateway</span><span class="sxs-lookup"><span data-stu-id="bf6d8-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="bf6d8-132">エンドポイント ワークスペースキー id Microsoft Monitoring Agent Defender をポイントするコンピューター [(MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)ポイントをインストール&する</span><span class="sxs-lookup"><span data-stu-id="bf6d8-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="bf6d8-133">OMS ゲートウェイの同じネットワーク内のオフライン Azure VM</span><span class="sxs-lookup"><span data-stu-id="bf6d8-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="bf6d8-134">Azure Log Analytics IP をプロキシとして構成する</span><span class="sxs-lookup"><span data-stu-id="bf6d8-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="bf6d8-135">Azure Log Analytics Workspace Key & ID</span><span class="sxs-lookup"><span data-stu-id="bf6d8-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="bf6d8-136">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="bf6d8-136">Azure Defender</span></span>
      - [<span data-ttu-id="bf6d8-137">セキュリティ ポリシー \> ログ分析ワークスペース</span><span class="sxs-lookup"><span data-stu-id="bf6d8-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="bf6d8-138">脅威検出 \> エンドポイントの Defender が自分のデータにアクセスできる</span><span class="sxs-lookup"><span data-stu-id="bf6d8-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="bf6d8-139">詳細については、「セキュリティ ポリシーの [操作」を参照してください](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)。</span><span class="sxs-lookup"><span data-stu-id="bf6d8-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>
