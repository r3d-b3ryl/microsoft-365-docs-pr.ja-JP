---
title: エンドポイント DLP のデバイス プロキシとインターネット接続の構成
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: エンドポイント DLP のデバイス プロキシとインターネット接続の構成方法について説明します。
ms.openlocfilehash: 3b8ebdbb08a6a866cc84df2031e77378925eaa0e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907007"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="1120a-103">エンドポイント DLP のデバイス プロキシとインターネット接続の構成</span><span class="sxs-lookup"><span data-stu-id="1120a-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="1120a-104">Microsoft エンドポイント DLP は、Microsoft Windows HTTP (WinHTTP) を使用してデータを報告し、Microsoft エンドポイント クラウド サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="1120a-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="1120a-105">埋め込まれた エンドポイント DLP は、LocalSystem アカウントを使用してシステム コンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1120a-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="1120a-106">インターネットへのゲートウェイとして転送プロキシを使用する組織では、ネットワーク保護を使用してプロキシの背後を調査できます。</span><span class="sxs-lookup"><span data-stu-id="1120a-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="1120a-107">詳細については、「[転送プロキシの背後で発生する接続イベントの調査](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120a-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="1120a-108">WinHTTP の構成設定は、Windows Internet （WinINet） のインターネット閲覧用プロキシの設定とは独立しており、以下の自動検出手法でのみプロキシ サーバーを検出することができます。</span><span class="sxs-lookup"><span data-stu-id="1120a-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="1120a-109">透過プロキシ</span><span class="sxs-lookup"><span data-stu-id="1120a-109">Transparent proxy</span></span>
- <span data-ttu-id="1120a-110">Web プロキシ自動発見プロトコル (WPAD)</span><span class="sxs-lookup"><span data-stu-id="1120a-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="1120a-111">ネットワーク トポロジで透過プロキシまたは WPAD を使用している場合は、特別な構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1120a-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="1120a-112">プロキシでの Defender for Endpoint URL 除外の詳細については、「[プロキシ サーバーでエンドポイント DLP クラウド サービス URL へのアクセスを有効にする](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120a-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="1120a-113">手動の静的プロキシの構成:</span><span class="sxs-lookup"><span data-stu-id="1120a-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="1120a-114">レジストリ ベースの構成</span><span class="sxs-lookup"><span data-stu-id="1120a-114">Registry based configuration</span></span>
    - <span data-ttu-id="1120a-115">netsh コマンドを使用して構成された WinHTTP – 安定したトポロジのデスクトップ (同じプロキシの背後にある企業ネットワークのデスクトップなど) だけに適しています。</span><span class="sxs-lookup"><span data-stu-id="1120a-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="1120a-116">レジストリ ベースの静的プロキシを使用して、プロキシ サーバーを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="1120a-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="1120a-117">インターネットへの接続が許可されていないエンドポイント デバイスの場合は、レジストリ ベースの静的プロキシを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120a-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="1120a-118">これを構成し、Microsoft エンドポイント DLP のみが診断データを報告し、Microsoft エンドポイント クラウド サービスと通信できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120a-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="1120a-119">静的プロキシは、グループ ポリシー (GP) を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="1120a-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="1120a-120">グループ ポリシーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="1120a-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="1120a-121">**[管理用テンプレート]、[Windows コンポーネント]、[データの収集とプレビュー ビルド]、[接続ユーザー エクスペリエンスとテレメトリ サービスでの認証済みプロキシの使用を構成する]** の順に開きます</span><span class="sxs-lookup"><span data-stu-id="1120a-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="1120a-122">**[有効]** に設定し、**[認証済みプロキシの使用を無効にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1120a-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![グループ ポリシー設定の画像 1](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="1120a-124">**[管理用テンプレート]、[Windows コンポーネント]、[データの収集とプレビュー ビルド]、[接続ユーザーのエクスペリエンスと利用統計情報を構成する]** の順に開きます</span><span class="sxs-lookup"><span data-stu-id="1120a-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="1120a-125">プロキシを構成する</span><span class="sxs-lookup"><span data-stu-id="1120a-125">Configure the proxy</span></span>

![グループ ポリシー設定の画像 2](../media/atp-gpo-proxy2.png)

<span data-ttu-id="1120a-127">このポリシーは、レジストリ キー `HKLM\Software\Policies\Microsoft\Windows\DataCollection` の下に 2 つのレジストリ値 `TelemetryProxyServer` を REG_SZ として、`DisableEnterpriseAuthProxy` を REG_DWORD として設定します。</span><span class="sxs-lookup"><span data-stu-id="1120a-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="1120a-128">レジストリ値 TelemetryProxyServer の形式は \<server name or ip\>:\<port\> です。</span><span class="sxs-lookup"><span data-stu-id="1120a-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="1120a-129">例: **10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="1120a-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="1120a-130">レジストリ値 `DisableEnterpriseAuthProxy` を 1に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120a-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="1120a-131">「netsh」コマンドを使用してプロキシ サーバーを手動で構成する</span><span class="sxs-lookup"><span data-stu-id="1120a-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="1120a-132">netsh を使用して、システム全体の静的プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="1120a-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="1120a-133">これは、既定のプロキシで WinHTTP を使用する Windows サービスを含むすべてのアプリケーションに影響します。</span><span class="sxs-lookup"><span data-stu-id="1120a-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="1120a-134">- トポロジを変更するノート PC (例えば、オフィスから自宅へ) が netsh で正しく動作しない。</span><span class="sxs-lookup"><span data-stu-id="1120a-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="1120a-135">レジストリ ベースの静的プロキシの構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="1120a-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="1120a-136">管理者特権でのコマンド ラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="1120a-136">Open an elevated command-line:</span></span>
    1. <span data-ttu-id="1120a-137">**[スタート]** をクリックし、「**cmd**」と入力する</span><span class="sxs-lookup"><span data-stu-id="1120a-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="1120a-138">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1120a-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="1120a-139">次のコマンドを入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1120a-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="1120a-140">例: **netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="1120a-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="1120a-141">winhttp プロキシをリセットするには、次のコマンドを入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1120a-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="1120a-142">詳細については、「[Netsh コマンドの構文、コンテキスト、およびフォーマット](/windows-server/networking/technologies/netsh/netsh-contexts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120a-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="1120a-143">プロキシ サーバーのエンドポイント DLP クラウド サービス URL へのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1120a-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="1120a-144">プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインの通過だけを許可している場合は、ダウンロード可能シートに記載されているドメインを許可ドメインのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="1120a-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="1120a-145">この[ダウンロード可能なスプレッドシート](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/security/threat-protection/microsoft-defender-atp/downloads/mdatp-urls.xlsx)には、ネットワークが接続可能である必要があるサービスとそれに関連付けられた URL の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1120a-145">This [downloadable spreadsheet](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/security/threat-protection/microsoft-defender-atp/downloads/mdatp-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="1120a-146">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター処理ルールがないことを確認する必要があります。そうでない場合、URL 専用の許可ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120a-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="1120a-147">プロキシまたはファイアウォールで HTTPS スキャン (SSL 検査) が有効になっている場合は、上記の表に示されているドメインを HTTPS スキャンから除外します。</span><span class="sxs-lookup"><span data-stu-id="1120a-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="1120a-148">エンドポイント DLP がシステム コンテキストから接続しているため、プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、前述の URL で匿名トラフィックが許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1120a-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="1120a-149">Microsoft クラウド サービス URL へのクライアント接続を確認する</span><span class="sxs-lookup"><span data-stu-id="1120a-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="1120a-150">プロキシ構成が正常に完了したことを確認します。WinHTTP は環境内のプロキシ サーバーを介して検出および通信でき、プロキシ サーバーは Defender for Endpoint サービス URL へのトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="1120a-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="1120a-151">エンドポイント DLP が実行されている PC に、[MDATP クライアント アナライザー ツール](https://aka.ms/mdatpanalyzer)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="1120a-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="1120a-152">デバイス上に MDATPClientAnalyzer.zip のコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="1120a-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="1120a-153">管理者特権でのコマンド ラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="1120a-153">Open an elevated command-line:</span></span>
    1. <span data-ttu-id="1120a-154">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1120a-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="1120a-155">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1120a-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="1120a-156">次のコマンドを入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1120a-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="1120a-157">*HardDrivePath* を、たとえば MDATPClientAnalyzer ツールがダウンロードされたパスに置き換えます</span><span class="sxs-lookup"><span data-stu-id="1120a-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="1120a-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="1120a-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="1120a-159">ツールによって作成された **MDATPClientAnalyzerResult.zip** _ ファイルを _HardDrivePath\* で使用されているフォルダーに解凍します。</span><span class="sxs-lookup"><span data-stu-id="1120a-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="1120a-160">**MDATPClientAnalyzerResult.txt** を開き、プロキシ構成の手順を実行して、サーバーの検出とサービス URL へのアクセスを有効にしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1120a-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="1120a-161">このツールは、Defender for Endpoint クライアントが相互作用するように構成されている Defender for Endpoint サービス URL の接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="1120a-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="1120a-162">次に、Defender for Endpoint サービスとの通信に使用できる URL ごとに、結果を **MDATPClientAnalyzerResult.txt** ファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="1120a-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="1120a-163">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1120a-163">For example:</span></span>

    <span data-ttu-id="1120a-164">**テスト URL : https://xxx.microsoft.com/xxx </br> 1 - 既定のプロキシ: 成功 (200) </br> 2 - プロキシ自動検出 (WPAD): 成功 (200)</br> 3 - ププロキシが無効: 成功 (200)</br> 4 - 名前付きプロキシ: 存在しない</br> 5 - コマンド ライン プロキシ: 存在しない**</span><span class="sxs-lookup"><span data-stu-id="1120a-164">**Testing URL : https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="1120a-165">少なくとも 1 つの接続オプションが (200) ステータスを返した場合、Defender for Endpoint クライアントはこの接続方法を使用してテスト済み URL と正しく通信できます。</span><span class="sxs-lookup"><span data-stu-id="1120a-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="1120a-166">ただし、接続を確認した結果が失敗を示している場合は、HTTP エラーが表示されます (「HTTP ステータス コード」を参照)。</span><span class="sxs-lookup"><span data-stu-id="1120a-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="1120a-167">次に、「[プロキシ サーバーでエンドポイント DLP クラウド サービス URL へのアクセスを有効にする](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)」に示されている表の URL を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1120a-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="1120a-168">使用する URL は、オンボーディング手順で選択した地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1120a-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="1120a-169"> 接続アナライザー ツールは、ASR ルールと互換性がありません [PSExec および WMI コマンドから発生するプロセスの作成をブロックします](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="1120a-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="1120a-170">接続ツールを実行するには、この規則を一時的に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120a-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="1120a-171">TelemetryProxyServer がレジストリまたはグループ ポリシー経由で設定されている場合、定義されたプロキシにアクセスできないと、Defender for Endpoint はダイレクトにフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="1120a-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="1120a-172">関連トピック •   Windows 10 デバイスのオンボード •   Microsoft エンドポイント DLP のオンボード問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1120a-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="1120a-173">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="1120a-173">See also</span></span>

- [<span data-ttu-id="1120a-174">エンドポイント データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="1120a-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="1120a-175">エンドポイントのデータ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="1120a-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="1120a-176">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="1120a-176">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="1120a-177">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="1120a-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1120a-178">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="1120a-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="1120a-179">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1120a-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="1120a-180">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="1120a-180">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="1120a-181">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="1120a-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="1120a-182">Azure AD に参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="1120a-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="1120a-183">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="1120a-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)