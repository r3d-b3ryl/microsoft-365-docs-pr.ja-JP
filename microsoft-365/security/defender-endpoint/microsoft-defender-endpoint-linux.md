---
title: Linux 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Microsoft Defender ATP for Linux をインストールして使用する方法について説明します。
keywords: microsoft、 defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: cc2f5be700395f6d88c05481d74501f4d9d92b76
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500670"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="65303-104">Linux 用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="65303-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65303-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="65303-105">**Applies to:**</span></span>
- [<span data-ttu-id="65303-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="65303-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65303-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65303-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="65303-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="65303-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="65303-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="65303-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="65303-110">このトピックでは、Microsoft Defender for Endpoint for Linux をインストール、構成、更新、および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65303-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="65303-111">Microsoft Defender for Endpoint for Linux と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しない副作用が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65303-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="65303-112">Microsoft 以外のエンドポイント保護が環境の絶対的な要件である場合でも、パッシブ モードで実行するウイルス対策機能を構成した後でも、Defender for Endpoint for Linux EDR 機能を安全に利用できます。 [](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="65303-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint for Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="65303-113">Microsoft Defender for Endpoint for Linux をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="65303-113">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="65303-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="65303-114">Prerequisites</span></span>

- <span data-ttu-id="65303-115">Microsoft Defender セキュリティ センター ポータルへのアクセス</span><span class="sxs-lookup"><span data-stu-id="65303-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="65303-116">systemd システム マネージャー [を使用した](https://systemd.io/) Linux 配布</span><span class="sxs-lookup"><span data-stu-id="65303-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="65303-117">Linux および BASH スクリプトでの初心者レベルのエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="65303-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="65303-118">デバイスの管理特権 (手動展開の場合)</span><span class="sxs-lookup"><span data-stu-id="65303-118">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="65303-119">インストール手順</span><span class="sxs-lookup"><span data-stu-id="65303-119">Installation instructions</span></span>

<span data-ttu-id="65303-120">Microsoft Defender for Endpoint for Linux のインストールと構成に使用できる方法と展開ツールがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="65303-120">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="65303-121">一般に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65303-121">In general you need to take the following steps:</span></span>

- <span data-ttu-id="65303-122">Microsoft Defender for Endpoint サブスクリプションを持ち、Microsoft Defender for Endpoint ポータルへのアクセス権を持 [っている必要があります](microsoft-defender-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="65303-122">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="65303-123">次のいずれかの展開方法を使用して、Microsoft Defender for Endpoint for Linux を展開します。</span><span class="sxs-lookup"><span data-stu-id="65303-123">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="65303-124">コマンド ライン ツール:</span><span class="sxs-lookup"><span data-stu-id="65303-124">The command-line tool:</span></span>
    - [<span data-ttu-id="65303-125">手動展開</span><span class="sxs-lookup"><span data-stu-id="65303-125">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="65303-126">サードパーティの管理ツール:</span><span class="sxs-lookup"><span data-stu-id="65303-126">Third-party management tools:</span></span>
    - [<span data-ttu-id="65303-127">Puppet 構成管理ツールを使用した展開</span><span class="sxs-lookup"><span data-stu-id="65303-127">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="65303-128">Ansible 構成管理ツールを使用した展開</span><span class="sxs-lookup"><span data-stu-id="65303-128">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="65303-129">インストールエラーが発生した場合は、「Microsoft Defender for Endpoint for Linux でのインストールエラーのトラブルシューティング [」を参照してください](linux-support-install.md)。</span><span class="sxs-lookup"><span data-stu-id="65303-129">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="65303-130">システム要件</span><span class="sxs-lookup"><span data-stu-id="65303-130">System requirements</span></span>

- <span data-ttu-id="65303-131">サポートされている Linux サーバーの配布とバージョン:</span><span class="sxs-lookup"><span data-stu-id="65303-131">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="65303-132">Red Hat Enterprise Linux 7.2 以上</span><span class="sxs-lookup"><span data-stu-id="65303-132">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="65303-133">CentOS 7.2 以上</span><span class="sxs-lookup"><span data-stu-id="65303-133">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="65303-134">Ubuntu 16.04 LTS 以上の LTS</span><span class="sxs-lookup"><span data-stu-id="65303-134">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="65303-135">Debian 9 以上</span><span class="sxs-lookup"><span data-stu-id="65303-135">Debian 9 or higher</span></span>
  - <span data-ttu-id="65303-136">SUSE Linux Enterprise Server 12 以上</span><span class="sxs-lookup"><span data-stu-id="65303-136">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="65303-137">Oracle Linux 7.2 以上</span><span class="sxs-lookup"><span data-stu-id="65303-137">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="65303-138">最小カーネル バージョン 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="65303-138">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="65303-139">カーネル `fanotify` オプションを有効にする必要があります</span><span class="sxs-lookup"><span data-stu-id="65303-139">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="65303-140">Defender for Endpoint for Linux を他のベースのセキュリティ ソリューションと並べて実行する `fanotify` 方法はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65303-140">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="65303-141">オペレーティング システムのハングを含む予期しない結果につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65303-141">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="65303-142">ディスク領域: 1 GB</span><span class="sxs-lookup"><span data-stu-id="65303-142">Disk space: 1GB</span></span>
- <span data-ttu-id="65303-143">/opt/microsoft/mdatp/sbin/wdavdaemon には実行可能なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="65303-143">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="65303-144">詳細については、「Microsoft Defender ATP for Linux のインストールに関する問題のトラブルシューティング」の「デーモンに実行可能なアクセス許可が付与されている」 [を参照してください](/microsoft-365/security/defender-endpoint/linux-support-install)。</span><span class="sxs-lookup"><span data-stu-id="65303-144">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="65303-145">メモリ: 1 GB</span><span class="sxs-lookup"><span data-stu-id="65303-145">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="65303-146">/var に空きディスク領域が含まれます。</span><span class="sxs-lookup"><span data-stu-id="65303-146">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="65303-147">ソリューションは現在、次のファイル システムの種類に対してリアルタイム保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="65303-147">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="65303-148">サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の送信接続を許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="65303-148">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="65303-149">監査フレームワーク ( `auditd` ) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65303-149">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="65303-150">追加されたルールによってキャプチャされたシステム イベントは (s) に追加され、ホストの監査とアップストリーム コレクション `/etc/audit/rules.d/` `audit.log` に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65303-150">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="65303-151">Microsoft Defender for Endpoint for Linux によって追加されたイベントには、キーがタグ付け `mdatp` されます。</span><span class="sxs-lookup"><span data-stu-id="65303-151">Events added by Microsoft Defender for Endpoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="65303-152">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="65303-152">Network connections</span></span>

<span data-ttu-id="65303-153">次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="65303-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="65303-154">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しなかっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65303-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="65303-155">ある場合は、許可ルール *の作成が* 必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="65303-155">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="65303-156">**ドメインリストのスプレッドシート**</span><span class="sxs-lookup"><span data-stu-id="65303-156">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="65303-157">**Description**</span><span class="sxs-lookup"><span data-stu-id="65303-157">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)<br/>  | <span data-ttu-id="65303-159">サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。</span><span class="sxs-lookup"><span data-stu-id="65303-159">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="65303-160">ここにスプレッドシートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="65303-160">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="65303-161">より具体的な URL リストについては [、「Configure proxy and internet connectivity settings」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="65303-161">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="65303-162">Defender for Endpoint では、次の検出方法を使用してプロキシ サーバーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="65303-162">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="65303-163">透過プロキシ</span><span class="sxs-lookup"><span data-stu-id="65303-163">Transparent proxy</span></span>
- <span data-ttu-id="65303-164">静的プロキシの手動構成</span><span class="sxs-lookup"><span data-stu-id="65303-164">Manual static proxy configuration</span></span>

<span data-ttu-id="65303-165">プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65303-165">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="65303-166">透過プロキシの場合、Defender for Endpoint の追加構成は不要です。</span><span class="sxs-lookup"><span data-stu-id="65303-166">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="65303-167">静的プロキシの場合は、「手動静的プロキシ構成 [」の手順に従います](linux-static-proxy-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="65303-167">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="65303-168">PAC、WPAD、および認証されたプロキシはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65303-168">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="65303-169">静的プロキシまたは透過プロキシのみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="65303-169">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="65303-170">SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65303-170">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="65303-171">SSL インスペクションとプロキシ サーバーが、Defender for Endpoint for Linux からインターセプトなしで関連する URL にデータを直接渡す例外を構成します。</span><span class="sxs-lookup"><span data-stu-id="65303-171">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="65303-172">インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。</span><span class="sxs-lookup"><span data-stu-id="65303-172">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="65303-173">トラブルシューティング手順については、「Microsoft Defender for Endpoint for Linux のクラウド接続の問題のトラブルシューティング [」を参照してください](linux-support-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="65303-173">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="65303-174">Microsoft Defender for Endpoint for Linux を更新する方法</span><span class="sxs-lookup"><span data-stu-id="65303-174">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="65303-175">Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。</span><span class="sxs-lookup"><span data-stu-id="65303-175">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="65303-176">Microsoft Defender for Endpoint for Linux を更新するには [、「Deploy updates for Microsoft Defender for Endpoint for Linux」を参照してください](linux-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="65303-176">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="65303-177">Microsoft Defender for Endpoint for Linux を構成する方法</span><span class="sxs-lookup"><span data-stu-id="65303-177">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="65303-178">エンタープライズ環境で製品を構成する方法のガイダンスについては、「Linux 用 Microsoft Defender for Endpoint の基本設定の [設定」を参照してください](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="65303-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="65303-179">関連情報</span><span class="sxs-lookup"><span data-stu-id="65303-179">Resources</span></span>

- <span data-ttu-id="65303-180">ログ記録、アンインストール、その他のトピックの詳細については [、「Resources」を参照してください](linux-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="65303-180">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
