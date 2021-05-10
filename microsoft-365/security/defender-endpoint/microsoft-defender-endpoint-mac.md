---
title: Microsoft Defender for Endpoint on Mac
ms.reviewer: ''
description: Mac で Microsoft Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, catalina, mojave, mde for mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 365fed8b5f7c7fc617ea068e324da541f7f1b187
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301778"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="205f9-104">Microsoft Defender for Endpoint on Mac</span><span class="sxs-lookup"><span data-stu-id="205f9-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="205f9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="205f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="205f9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="205f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="205f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="205f9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="205f9-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="205f9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="205f9-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="205f9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="205f9-110">このトピックでは、Mac 上で Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="205f9-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="205f9-111">Microsoft Defender for Endpoint on Mac で他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しない副作用につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="205f9-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="205f9-112">Microsoft 以外のエンドポイント保護が環境の絶対的な要件である場合でも、パッシブ モードで実行するウイルス対策機能を構成した後も、Defender for Endpoint on Mac EDR[](mac-preferences.md#enable--disable-passive-mode)の機能を安全に利用できます。</span><span class="sxs-lookup"><span data-stu-id="205f9-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="205f9-113">最新リリースの新機能</span><span class="sxs-lookup"><span data-stu-id="205f9-113">What’s new in the latest release</span></span>

[<span data-ttu-id="205f9-114">Microsoft Defender for Endpoint の新機能</span><span class="sxs-lookup"><span data-stu-id="205f9-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="205f9-115">Microsoft Defender for Endpoint on Mac の新機能</span><span class="sxs-lookup"><span data-stu-id="205f9-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="205f9-116">共有するフィードバックがある場合は、デバイスで Microsoft Defender for Endpoint on Mac を開き、[フィードバックの送信に役立つ] に移動して送信  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="205f9-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="205f9-117">プレビュー機能 (Mac デバイスのエンドポイント検出や応答など) を含む最新の機能を取得するには、Microsoft Defender for Endpoint を実行している macOS デバイスを "Insider" デバイスに構成します。</span><span class="sxs-lookup"><span data-stu-id="205f9-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="205f9-118">Mac に Microsoft Defender for Endpoint をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="205f9-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="205f9-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="205f9-119">Prerequisites</span></span>

- <span data-ttu-id="205f9-120">Defender for Endpoint サブスクリプションとポータルへのアクセスMicrosoft Defender セキュリティ センターする</span><span class="sxs-lookup"><span data-stu-id="205f9-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="205f9-121">macOS と BASH スクリプトの初心者レベルのエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="205f9-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="205f9-122">デバイスの管理特権 (手動展開の場合)</span><span class="sxs-lookup"><span data-stu-id="205f9-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="205f9-123">インストール手順</span><span class="sxs-lookup"><span data-stu-id="205f9-123">Installation instructions</span></span>

<span data-ttu-id="205f9-124">Defender for Endpoint on Mac のインストールと構成に使用できる方法と展開ツールがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="205f9-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="205f9-125">サードパーティの管理ツール:</span><span class="sxs-lookup"><span data-stu-id="205f9-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="205f9-126">Microsoft Intune ベースの展開</span><span class="sxs-lookup"><span data-stu-id="205f9-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="205f9-127">JAMF ベースの展開</span><span class="sxs-lookup"><span data-stu-id="205f9-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="205f9-128">その他の MDM 製品</span><span class="sxs-lookup"><span data-stu-id="205f9-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="205f9-129">コマンド ライン ツール:</span><span class="sxs-lookup"><span data-stu-id="205f9-129">Command-line tool:</span></span>
    - [<span data-ttu-id="205f9-130">手動展開</span><span class="sxs-lookup"><span data-stu-id="205f9-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="205f9-131">システム要件</span><span class="sxs-lookup"><span data-stu-id="205f9-131">System requirements</span></span>

<span data-ttu-id="205f9-132">macOS の最新の 3 つのメジャー リリースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="205f9-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="205f9-133">macOS 11 (Big Sur) では、Microsoft Defender for Endpoint には追加の構成プロファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="205f9-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="205f9-134">以前のバージョンの macOS からアップグレードする既存のお客様の場合は [、macOS Catalina](mac-sysext-policies.md)および macOS の新しいバージョンの新しい構成プロファイルに記載されている追加の構成プロファイルを必ず展開してください。</span><span class="sxs-lookup"><span data-stu-id="205f9-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="205f9-135">macOS 10.13 (High Sierra) のサポートは、2021 年 2 月 15 日より中止されました。</span><span class="sxs-lookup"><span data-stu-id="205f9-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="205f9-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="205f9-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="205f9-137">ディスク領域: 1 GB</span><span class="sxs-lookup"><span data-stu-id="205f9-137">Disk space: 1GB</span></span>

<span data-ttu-id="205f9-138">macOS のベータ版はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="205f9-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="205f9-139">M1 プロセッサを搭載した macOS デバイスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="205f9-139">macOS devices with M1 processors are not supported.</span></span>

<span data-ttu-id="205f9-140">サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の送信接続を許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="205f9-140">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="205f9-141">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="205f9-141">Licensing requirements</span></span>

<span data-ttu-id="205f9-142">Microsoft Defender for Endpoint on Mac では、次のいずれかの Microsoft ボリューム ライセンス オファーが必要です。</span><span class="sxs-lookup"><span data-stu-id="205f9-142">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="205f9-143">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="205f9-143">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="205f9-144">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="205f9-144">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="205f9-145">Microsoft 365A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="205f9-145">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="205f9-146">Windows 10 EnterpriseE5</span><span class="sxs-lookup"><span data-stu-id="205f9-146">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="205f9-147">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="205f9-147">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="205f9-148">対象となるライセンスユーザーは、最大 5 つの同時デバイスで Microsoft Defender for Endpoint を使用できます。</span><span class="sxs-lookup"><span data-stu-id="205f9-148">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="205f9-149">Microsoft Defender for Endpoint は、ユーザー (CSP) から購入クラウド ソリューション プロバイダー利用できます。</span><span class="sxs-lookup"><span data-stu-id="205f9-149">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="205f9-150">CSP を介して購入した場合、Microsoft ボリューム ライセンスの提供は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="205f9-150">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="205f9-151">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="205f9-151">Network connections</span></span>

<span data-ttu-id="205f9-152">次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="205f9-152">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="205f9-153">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、許可ルールを作成する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="205f9-153">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="205f9-154">**ドメインリストのスプレッドシート**</span><span class="sxs-lookup"><span data-stu-id="205f9-154">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="205f9-155">**説明**</span><span class="sxs-lookup"><span data-stu-id="205f9-155">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)<br/>  | <span data-ttu-id="205f9-157">サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。</span><span class="sxs-lookup"><span data-stu-id="205f9-157">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="205f9-158">スプレッドシートをダウンロードするには、 [ 次の ](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)mdatp-urls.xlsxします。</span><span class="sxs-lookup"><span data-stu-id="205f9-158">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="205f9-159">Microsoft Defender for Endpoint では、次の検出方法を使用してプロキシ サーバーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="205f9-159">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="205f9-160">プロキシの自動構成 (PAC)</span><span class="sxs-lookup"><span data-stu-id="205f9-160">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="205f9-161">Web プロキシ自動検出プロトコル (WPAD)</span><span class="sxs-lookup"><span data-stu-id="205f9-161">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="205f9-162">静的プロキシの手動構成</span><span class="sxs-lookup"><span data-stu-id="205f9-162">Manual static proxy configuration</span></span>

<span data-ttu-id="205f9-163">プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="205f9-163">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="205f9-164">認証されたプロキシはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="205f9-164">Authenticated proxies are not supported.</span></span> <span data-ttu-id="205f9-165">PAC、WPAD、または静的プロキシだけが使用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="205f9-165">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="205f9-166">SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="205f9-166">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="205f9-167">SSL インスペクションとプロキシ サーバーの例外を構成して、macOS 上の Microsoft Defender for Endpoint のデータを、傍受なしで関連する URL に直接渡します。</span><span class="sxs-lookup"><span data-stu-id="205f9-167">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="205f9-168">インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。</span><span class="sxs-lookup"><span data-stu-id="205f9-168">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="205f9-169">接続がブロックされていないとテストするには、ブラウザー [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) で [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) 開きます。</span><span class="sxs-lookup"><span data-stu-id="205f9-169">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="205f9-170">コマンド ラインが必要な場合は、ターミナルで次のコマンドを実行して接続を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="205f9-170">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="205f9-171">このコマンドからの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="205f9-171">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="205f9-172">クライアント デバイスでシステム [整合性保護](https://support.apple.com/en-us/HT204899) (SIP) を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="205f9-172">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="205f9-173">SIP は、OS の低レベル改ざんを防止する組み込みの macOS セキュリティ機能であり、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="205f9-173">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="205f9-174">Microsoft Defender for Endpoint をインストールすると、ターミナルで次のコマンドを実行して接続を検証できます。</span><span class="sxs-lookup"><span data-stu-id="205f9-174">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="205f9-175">Microsoft Defender for Endpoint on Mac を更新する方法</span><span class="sxs-lookup"><span data-stu-id="205f9-175">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="205f9-176">Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。</span><span class="sxs-lookup"><span data-stu-id="205f9-176">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="205f9-177">Microsoft Defender for Endpoint on Mac を更新するには、Microsoft AutoUpdate (MAU) という名前のプログラムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="205f9-177">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="205f9-178">詳細については [、「Deploy updates for Microsoft Defender for Endpoint on Mac」を参照してください](mac-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="205f9-178">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="205f9-179">Mac で Microsoft Defender for Endpoint を構成する方法</span><span class="sxs-lookup"><span data-stu-id="205f9-179">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="205f9-180">エンタープライズ環境で製品を構成する方法については、「Mac での Microsoft Defender for Endpoint の設定 [」を参照してください](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="205f9-180">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="205f9-181">macOS カーネルとシステム拡張機能</span><span class="sxs-lookup"><span data-stu-id="205f9-181">macOS kernel and system extensions</span></span>

<span data-ttu-id="205f9-182">macOS の進化に合わせ、カーネル拡張機能の代わりにシステム拡張機能を活用する Microsoft Defender for Endpoint on Mac 更新プログラムを準備しています。</span><span class="sxs-lookup"><span data-stu-id="205f9-182">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="205f9-183">関連する詳細については [、「Microsoft Defender for Endpoint on Mac の新機能」を参照してください](mac-whatsnew.md)。</span><span class="sxs-lookup"><span data-stu-id="205f9-183">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="205f9-184">関連情報</span><span class="sxs-lookup"><span data-stu-id="205f9-184">Resources</span></span>

- <span data-ttu-id="205f9-185">ログ記録、アンインストール、その他のトピックの詳細については [、「Resources for Microsoft Defender for Endpoint on Mac」を参照してください](mac-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="205f9-185">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="205f9-186">[Microsoft Defender for Endpoint on Mac のプライバシー](mac-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="205f9-186">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
