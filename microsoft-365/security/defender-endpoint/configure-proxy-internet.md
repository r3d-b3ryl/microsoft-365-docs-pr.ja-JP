---
title: デバイス プロキシとインターネット接続の設定を構成する
description: Microsoft Defender for Endpoint プロキシとインターネット設定を構成して、クラウド サービスとの通信を有効にします。
keywords: configure, proxy, internet, internet connectivity, settings, proxy settings, netsh, winhttp, proxy server
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ebfff7721bc61012811a66146079ac9758889594
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893603"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="45b28-104">デバイス プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="45b28-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="45b28-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="45b28-105">**Applies to:**</span></span>
- [<span data-ttu-id="45b28-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="45b28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="45b28-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45b28-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="45b28-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="45b28-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45b28-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="45b28-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="45b28-110">Defender for Endpoint センサーでは、センサー データを報告し、Defender for Endpoint サービスと通信するために Microsoft Windows HTTP (WinHTTP) が必要です。</span><span class="sxs-lookup"><span data-stu-id="45b28-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="45b28-111">埋め込み Defender for Endpoint センサーは、LocalSystem アカウントを使用してシステム コンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="45b28-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="45b28-112">センサーは、Microsoft Windows HTTP Services (WinHTTP) を使用して、Defender for Endpoint クラウド サービスとの通信を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="45b28-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="45b28-113">インターネットへのゲートウェイとして転送プロキシを使用する組織では、ネットワーク保護を使用してプロキシの背後を調査できます。</span><span class="sxs-lookup"><span data-stu-id="45b28-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="45b28-114">詳細については、「[転送プロキシの背後で発生する接続イベントの調査](investigate-behind-proxy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b28-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="45b28-115">WinHTTP 構成設定は、Windows Internet (WinINet) インターネット ブラウズ プロキシ設定とは独立し、次の検出方法を使用してのみプロキシ サーバーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="45b28-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="45b28-116">自動検出の方法:</span><span class="sxs-lookup"><span data-stu-id="45b28-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="45b28-117">透過プロキシ</span><span class="sxs-lookup"><span data-stu-id="45b28-117">Transparent proxy</span></span>
  - <span data-ttu-id="45b28-118">Web プロキシ自動発見プロトコル (WPAD)</span><span class="sxs-lookup"><span data-stu-id="45b28-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="45b28-119">ネットワーク トポロジで透過プロキシまたは WPAD を使用している場合は、特別な構成設定は必要ない。</span><span class="sxs-lookup"><span data-stu-id="45b28-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="45b28-120">プロキシの Defender for Endpoint URL 除外の詳細については、「プロキシ サーバーで Defender for Endpoint Service URL へのアクセスを有効にする」 [を参照してください](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="45b28-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="45b28-121">手動の静的プロキシの構成:</span><span class="sxs-lookup"><span data-stu-id="45b28-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="45b28-122">レジストリ ベースの構成</span><span class="sxs-lookup"><span data-stu-id="45b28-122">Registry based configuration</span></span>
  - <span data-ttu-id="45b28-123">netsh コマンドを使用して構成された WinHTTP – 安定したトポロジのデスクトップ (同じプロキシの背後にある企業ネットワークのデスクトップなど) だけに適しています。</span><span class="sxs-lookup"><span data-stu-id="45b28-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="45b28-124">レジストリ ベースの静的プロキシを使用して、プロキシ サーバーを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="45b28-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="45b28-125">コンピューターがインターネットへの接続を許可されていない場合、Defender for Endpoint センサーだけが診断データを報告し、Defender for Endpoint サービスと通信できるレジストリ ベースの静的プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="45b28-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

> [!NOTE]
> - <span data-ttu-id="45b28-126">Windows 10 または Windows Server 2019 でこのオプションを使用する場合は、次の (以降の) ビルドと累積的な更新プログラムのロールアップを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b28-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span></br>
> <span data-ttu-id="45b28-127">Windows 10 バージョン 1909 - https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="45b28-127">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span></br>
> <span data-ttu-id="45b28-128">Windows 10 バージョン 2004 - https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="45b28-128">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="45b28-129">Windows 10 バージョン 20H2 - https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="45b28-129">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="45b28-130">これらの更新プログラムは、CnC (Command and Control) チャネルの接続性と信頼性を向上します。</span><span class="sxs-lookup"><span data-stu-id="45b28-130">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span></br>

<span data-ttu-id="45b28-131">静的プロキシは、グループ ポリシー (GP) を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="45b28-131">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="45b28-132">グループ ポリシーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="45b28-132">The group policy can be found under:</span></span>

- <span data-ttu-id="45b28-133">管理用> Windows コンポーネント>データ収集とプレビュー ビルド> 接続されたユーザー エクスペリエンスとテレメトリ サービスの認証プロキシの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="45b28-133">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="45b28-134">[有効] **に設定し** 、[ **認証されたプロキシの使用を** 無効にする: ![ グループ ポリシーのイメージ設定 1] を選択します。](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="45b28-134">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="45b28-135">**管理用テンプレート > Windows コンポーネント**>データ収集とプレビュー ビルド>接続されたユーザー エクスペリエンスと利用統計情報を構成する:</span><span class="sxs-lookup"><span data-stu-id="45b28-135">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="45b28-136">プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="45b28-136">Configure the proxy:</span></span><br>
    <span data-ttu-id="45b28-137">![グループ ポリシー設定 2 のイメージ](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="45b28-137">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="45b28-138">このポリシーは、レジストリ キー `HKLM\Software\Policies\Microsoft\Windows\DataCollection` の下に 2 つのレジストリ値 `TelemetryProxyServer` を REG_SZ として、`DisableEnterpriseAuthProxy` を REG_DWORD として設定します。</span><span class="sxs-lookup"><span data-stu-id="45b28-138">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="45b28-139">レジストリ値は、 `TelemetryProxyServer` 次の文字列形式を取ります。</span><span class="sxs-lookup"><span data-stu-id="45b28-139">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="45b28-140">例: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="45b28-140">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="45b28-141">レジストリ値 `DisableEnterpriseAuthProxy` を 1に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b28-141">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="45b28-142">netsh コマンドを使用してプロキシ サーバーを手動で構成する</span><span class="sxs-lookup"><span data-stu-id="45b28-142">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="45b28-143">netsh を使用して、システム全体の静的プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="45b28-143">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="45b28-144">これは、既定のプロキシで WinHTTP を使用する Windows サービスを含むすべてのアプリケーションに影響します。</span><span class="sxs-lookup"><span data-stu-id="45b28-144">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="45b28-145">トポロジを変更しているラップトップ (たとえば、オフィスから自宅) は netsh に誤動作します。</span><span class="sxs-lookup"><span data-stu-id="45b28-145">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="45b28-146">レジストリ ベースの静的プロキシの構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="45b28-146">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="45b28-147">管理者特権でのコマンド ラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="45b28-147">Open an elevated command-line:</span></span>

    <span data-ttu-id="45b28-148">a.</span><span class="sxs-lookup"><span data-stu-id="45b28-148">a.</span></span> <span data-ttu-id="45b28-149">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="45b28-149">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="45b28-150">b.</span><span class="sxs-lookup"><span data-stu-id="45b28-150">b.</span></span> <span data-ttu-id="45b28-151">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="45b28-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="45b28-152">次のコマンドを入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="45b28-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="45b28-153">例: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="45b28-153">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="45b28-154">winhttp プロキシをリセットするには、次のコマンドを入力して Enter キーを押 **します。**</span><span class="sxs-lookup"><span data-stu-id="45b28-154">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="45b28-155">詳細については、「[Netsh コマンドの構文、コンテキスト、およびフォーマット](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b28-155">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="45b28-156">プロキシ サーバーで Microsoft Defender for Endpoint サービス URL へのアクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="45b28-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="45b28-157">プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインの通過だけを許可している場合は、ダウンロード可能シートに記載されているドメインを許可ドメインのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="45b28-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="45b28-158">次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="45b28-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="45b28-159">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、許可ルールを作成する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="45b28-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="45b28-160">**ドメインリストのスプレッドシート**</span><span class="sxs-lookup"><span data-stu-id="45b28-160">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="45b28-161">**説明**</span><span class="sxs-lookup"><span data-stu-id="45b28-161">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)<br/>  | <span data-ttu-id="45b28-163">サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。</span><span class="sxs-lookup"><span data-stu-id="45b28-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="45b28-164">ここにスプレッドシートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="45b28-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="45b28-165">プロキシまたはファイアウォールで HTTPS スキャン (SSL 検査) が有効になっている場合は、上記の表に示されているドメインを HTTPS スキャンから除外します。</span><span class="sxs-lookup"><span data-stu-id="45b28-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="45b28-166">settings-win.data.microsoft.com は、バージョン 1803 以前を実行している Windows 10 デバイスがある場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="45b28-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="45b28-167">v20 を含む URL は、バージョン 1803 以降を実行している Windows 10 デバイスがある場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="45b28-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="45b28-168">たとえば、バージョン 1803 以降を実行し、米国のデータ ストレージ領域にオンボードされている ```us-v20.events.data.microsoft.com``` Windows 10 デバイスに必要です。</span><span class="sxs-lookup"><span data-stu-id="45b28-168">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="45b28-169">環境で Microsoft Defender ウイルス対策を使用している場合は、「Microsoft Defender ウイルス対策クラウド サービスへのネットワーク接続を構成する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="45b28-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="45b28-170">Defender for Endpoint センサーがシステム コンテキストから接続している場合、プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b28-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="45b28-171">Microsoft Monitoring Agent (MMA) - 以前のバージョンの Windows クライアントまたは Windows Server のプロキシとファイアウォールの要件</span><span class="sxs-lookup"><span data-stu-id="45b28-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="45b28-172">以下の情報は、Windows 7 SP1、Windows 8.1、Windows Server 2008 R2、Windows Server 2012 R2、Windows Server 2016 などの以前のバージョンの Windows の Log Analytics エージェント (Microsoft Monitoring Agent と呼ばれます) との通信に必要なプロキシおよびファイアウォール構成情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="45b28-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="45b28-173">エージェント リソース</span><span class="sxs-lookup"><span data-stu-id="45b28-173">Agent Resource</span></span>|<span data-ttu-id="45b28-174">ポート</span><span class="sxs-lookup"><span data-stu-id="45b28-174">Ports</span></span> |<span data-ttu-id="45b28-175">Direction</span><span class="sxs-lookup"><span data-stu-id="45b28-175">Direction</span></span> |<span data-ttu-id="45b28-176">HTTPS 検査のバイパス</span><span class="sxs-lookup"><span data-stu-id="45b28-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="45b28-177">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="45b28-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="45b28-178">ポート 443</span><span class="sxs-lookup"><span data-stu-id="45b28-178">Port 443</span></span> |<span data-ttu-id="45b28-179">送信</span><span class="sxs-lookup"><span data-stu-id="45b28-179">Outbound</span></span>|<span data-ttu-id="45b28-180">はい</span><span class="sxs-lookup"><span data-stu-id="45b28-180">Yes</span></span> |  
|<span data-ttu-id="45b28-181">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="45b28-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="45b28-182">ポート 443</span><span class="sxs-lookup"><span data-stu-id="45b28-182">Port 443</span></span> |<span data-ttu-id="45b28-183">送信</span><span class="sxs-lookup"><span data-stu-id="45b28-183">Outbound</span></span>|<span data-ttu-id="45b28-184">はい</span><span class="sxs-lookup"><span data-stu-id="45b28-184">Yes</span></span> |  
|<span data-ttu-id="45b28-185">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="45b28-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="45b28-186">ポート 443</span><span class="sxs-lookup"><span data-stu-id="45b28-186">Port 443</span></span> |<span data-ttu-id="45b28-187">送信</span><span class="sxs-lookup"><span data-stu-id="45b28-187">Outbound</span></span>|<span data-ttu-id="45b28-188">はい</span><span class="sxs-lookup"><span data-stu-id="45b28-188">Yes</span></span> |
|<span data-ttu-id="45b28-189">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="45b28-189">\*.azure-automation.net</span></span> |<span data-ttu-id="45b28-190">ポート 443</span><span class="sxs-lookup"><span data-stu-id="45b28-190">Port 443</span></span> |<span data-ttu-id="45b28-191">送信</span><span class="sxs-lookup"><span data-stu-id="45b28-191">Outbound</span></span>|<span data-ttu-id="45b28-192">はい</span><span class="sxs-lookup"><span data-stu-id="45b28-192">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="45b28-193">クラウドベースのソリューションとして、IP 範囲が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45b28-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="45b28-194">DNS 解決設定に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b28-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="45b28-195">Microsoft 監視エージェント (MMA) サービス URL の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="45b28-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="45b28-196">以前のバージョンの Windows で Microsoft Monitoring Agent (MMA) を使用する場合、特定の環境のワイルドカード (\*) 要件を排除するには、次のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b28-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="45b28-197">Microsoft Monitoring Agent (MMA) を使用して以前のオペレーティング システムを Defender for Endpoint にオンボードします (詳細については、「Defender [on Defender](https://go.microsoft.com/fwlink/p/?linkid=2010326) およびオンボード Windows サーバーの以前のバージョンの Windows のオンボード」を [参照してください](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="45b28-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="45b28-198">コンピューターが Microsoft Defender セキュリティ センター ポータルに正常に報告されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="45b28-198">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="45b28-199">"C:\Program Files\Microsoft Monitoring Agent\Agent" の TestCloudConnection.exe ツールを実行して、接続を検証し、特定のワークスペースに必要な URL を確認します。</span><span class="sxs-lookup"><span data-stu-id="45b28-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="45b28-200">Microsoft Defender for Endpoint URL リストで、地域の要件の完全な一覧を確認します (「サービス URL スプレッドシート」を参照 [してください](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx))。</span><span class="sxs-lookup"><span data-stu-id="45b28-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![管理者のWindows PowerShell](images/admin-powershell.png)

<span data-ttu-id="45b28-202">*.ods.opinsights.azure.com、*.oms.opinsights.azure.com、および *.agentsvc.azure-automation.net URL エンドポイントで使用されるワイルドカード (*) は、特定の Workspace ID に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="45b28-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="45b28-203">ワークスペース ID は環境とワークスペースに固有の ID で、Microsoft Defender セキュリティ センター ポータル内のテナントの [オンボーディング] セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="45b28-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="45b28-204">\*.blob.core.windows.net URL エンドポイントは、テスト結果の 「ファイアウォール ルール: \*.blob.core.windows.net」セクションに示されている URL に置き換え可能です。</span><span class="sxs-lookup"><span data-stu-id="45b28-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="45b28-205">Azure Security Center (ASC) 経由でオンボーディングを行う場合、複数のワークスペースが使用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45b28-205">In the case of onboarding via Azure Security Center (ASC), multiple workspaces maybe used.</span></span> <span data-ttu-id="45b28-206">上記の TestCloudConnection.exe 手順を、各ワークスペースのオンボード コンピューターで実行する必要があります (ワークスペース間で \*.blob.core.windows.net URL に変更が加わるかどうかを判断するには)。</span><span class="sxs-lookup"><span data-stu-id="45b28-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="45b28-207">エンドポイント サービス URL 用 Microsoft Defender へのクライアント接続を確認する</span><span class="sxs-lookup"><span data-stu-id="45b28-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="45b28-208">プロキシ構成が正常に完了したことを確認します。WinHTTP は環境内のプロキシ サーバーを介して検出および通信でき、プロキシ サーバーは Defender for Endpoint サービス URL へのトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="45b28-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="45b28-209">エンドポイント センサーの Defender が実行されている PC に [MDATP](https://aka.ms/mdatpanalyzer) クライアント アナライザー ツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="45b28-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="45b28-210">デバイス上に MDATPClientAnalyzer.zip のコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="45b28-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="45b28-211">管理者特権でのコマンド ラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="45b28-211">Open an elevated command-line:</span></span>

    <span data-ttu-id="45b28-212">a.</span><span class="sxs-lookup"><span data-stu-id="45b28-212">a.</span></span> <span data-ttu-id="45b28-213">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="45b28-213">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="45b28-214">b.</span><span class="sxs-lookup"><span data-stu-id="45b28-214">b.</span></span>  <span data-ttu-id="45b28-215">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="45b28-215">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="45b28-216">次のコマンドを入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="45b28-216">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="45b28-217">*HardDrivePath* を、たとえば MDATPClientAnalyzer ツールがダウンロードされたパスに置き換えます</span><span class="sxs-lookup"><span data-stu-id="45b28-217">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="45b28-218">*HardDrivePath\*\*でMDATPClientAnalyzerResult.zip* フォルダーにツールによって作成されたファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="45b28-218">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="45b28-219">*MDATPClientAnalyzerResult.txt* を開き、プロキシ構成の手順を実行して、サーバーの検出とサービス URL へのアクセスを有効にしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="45b28-219">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="45b28-220">このツールは、Defender for Endpoint クライアントが相互作用するように構成されている Defender for Endpoint サービス URL の接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="45b28-220">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="45b28-221">次に、Defender for Endpoint サービスとの通信に使用できる URL ごとに、結果を *MDATPClientAnalyzerResult.txt* ファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="45b28-221">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="45b28-222">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="45b28-222">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="45b28-223">少なくとも 1 つの接続オプションが (200) ステータスを返した場合、Defender for Endpoint クライアントはこの接続方法を使用してテスト済み URL と正しく通信できます。</span><span class="sxs-lookup"><span data-stu-id="45b28-223">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="45b28-224">ただし、接続を確認した結果が失敗を示している場合は、HTTP エラーが表示されます (「HTTP ステータス コード」を参照)。</span><span class="sxs-lookup"><span data-stu-id="45b28-224">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="45b28-225">次に、「プロキシ サーバーの Defender for Endpoint サービス URL へのアクセスを有効にする」に示されている表の [URL を使用できます](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="45b28-225">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="45b28-226">使用する URL は、オンボーディング手順で選択された地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="45b28-226">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="45b28-227"> 接続アナライザー ツールは、ASR ルールと互換性がありません [PSExec および WMI コマンドから発生するプロセスの作成をブロックします](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="45b28-227">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="45b28-228">接続ツールを実行するには、この規則を一時的に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b28-228">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="45b28-229">TelemetryProxyServer がレジストリまたはグループ ポリシーを介して設定されている場合、Defender for Endpoint は、定義されたプロキシにアクセスできない場合、直接に戻されます。</span><span class="sxs-lookup"><span data-stu-id="45b28-229">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="45b28-230">関連項目</span><span class="sxs-lookup"><span data-stu-id="45b28-230">Related topics</span></span>

- [<span data-ttu-id="45b28-231">Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="45b28-231">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="45b28-232">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="45b28-232">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
