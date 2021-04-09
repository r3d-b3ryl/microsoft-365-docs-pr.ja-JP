---
title: ネットワーク デバイスの検出と脆弱性の管理
description: スイッチ、ルーター、WLAN コントローラー、ファイアウォールのオペレーティング システムでは、セキュリティに関する推奨事項と脆弱性の検出を利用できます。
keywords: ネットワーク デバイス、ネットワーク デバイスの脆弱性検出、スイッチ、ルーター、WLAN コントローラー、ファイアウォールのオペレーティング システム
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d0ae82c2e284235d96531c04dc2240063d4e4183
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51657043"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="6dfac-104">ネットワーク デバイスの検出と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="6dfac-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6dfac-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6dfac-105">**Applies to:**</span></span>

- [<span data-ttu-id="6dfac-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6dfac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6dfac-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="6dfac-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6dfac-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6dfac-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="6dfac-109">**ネットワーク デバイスのスキャンと管理が現在パブリック プレビュー中**</span><span class="sxs-lookup"><span data-stu-id="6dfac-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="6dfac-110">このプレビュー バージョンはサービス レベル契約なしで提供され、実稼働ワークロードには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="6dfac-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="6dfac-111">一部の機能はサポートされていないか、制限された機能を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="6dfac-112">詳細については [、「Microsoft Defender for Endpoint プレビュー機能」を参照してください](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="6dfac-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="6dfac-113">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="6dfac-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6dfac-114">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="6dfac-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="6dfac-115">ネットワーク検出機能は、Microsoft 365 セキュリティ センターと Microsoft Defender セキュリティ センター コンソールの [デバイス インベントリ] セクションで使用できます。 </span><span class="sxs-lookup"><span data-stu-id="6dfac-115">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="6dfac-116">指定された Microsoft Defender for Endpoint デバイスは、構成済みのネットワーク デバイスの定期的な認証スキャンを実行するために、各ネットワーク セグメントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-116">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="6dfac-117">検出された Defender for Endpoint の脅威および脆弱性管理機能は、検出されたスイッチ、ルーター、WLAN コントローラー、ファイアウォール、VPN ゲートウェイを保護するための統合ワークフローを提供します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-117">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="6dfac-118">ネットワーク デバイスが検出され、分類された後、セキュリティ管理者は最新のセキュリティ推奨事項を受け取り、組織全体に展開されたネットワーク デバイスで最近検出された脆弱性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-118">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="6dfac-119">方法</span><span class="sxs-lookup"><span data-stu-id="6dfac-119">Approach</span></span>

<span data-ttu-id="6dfac-120">Defender for Endpoint にはネットワーク デバイス自体にセンサーが組み込かされていないので、ネットワーク デバイスは標準エンドポイントとして管理されません。</span><span class="sxs-lookup"><span data-stu-id="6dfac-120">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="6dfac-121">これらの種類のデバイスでは、リモート スキャンがデバイスから必要な情報を取得するエージェントレスアプローチが必要です。</span><span class="sxs-lookup"><span data-stu-id="6dfac-121">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="6dfac-122">ネットワーク トポロジと特性に応じて、Microsoft Defender for Endpoint にオンボードされている 1 台のデバイスまたは数台のデバイスで、SNMP (読み取り専用) を使用してネットワーク デバイスの認証スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-122">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="6dfac-123">次の 2 種類のデバイスを念頭に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-123">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="6dfac-124">**評価デバイス**: ネットワーク デバイスのスキャンに使用するオンボード済みのデバイス。</span><span class="sxs-lookup"><span data-stu-id="6dfac-124">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="6dfac-125">**ネットワーク デバイス**: スキャンとオンボードを計画しているネットワーク デバイス。</span><span class="sxs-lookup"><span data-stu-id="6dfac-125">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="6dfac-126">ネットワーク デバイスの脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="6dfac-126">Vulnerability management for network devices</span></span> 

<span data-ttu-id="6dfac-127">ネットワーク デバイスが検出され、分類された後、セキュリティ管理者は最新のセキュリティ推奨事項を受け取り、組織全体に展開されたネットワーク デバイスで最近検出された脆弱性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-127">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="6dfac-128">サポートされているオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="6dfac-128">Operating systems that are supported</span></span>

<span data-ttu-id="6dfac-129">現在サポートされているオペレーティング システムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6dfac-129">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="6dfac-130">Cisco IOS、IOS-XE、NX-OS</span><span class="sxs-lookup"><span data-stu-id="6dfac-130">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="6dfac-131">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="6dfac-131">Juniper JUNOS</span></span>
- <span data-ttu-id="6dfac-132">HPE ArubaOS,Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="6dfac-132">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="6dfac-133">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="6dfac-133">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="6dfac-134">顧客の使用状況から収集されたデータに基づいて、時間の間に追加されるネットワーク ベンダーと OS の数が多くなされます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-134">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="6dfac-135">したがって、この一覧で指定されていない場合でも、すべてのネットワーク デバイスを構成してください。</span><span class="sxs-lookup"><span data-stu-id="6dfac-135">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="6dfac-136">始める方法</span><span class="sxs-lookup"><span data-stu-id="6dfac-136">How to get started</span></span>

<span data-ttu-id="6dfac-137">最初の手順は、認証されたネットワーク スキャンを実行するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-137">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="6dfac-138">スキャンを計画しているネットワーク デバイスの管理ポートにネットワーク接続を持つ Defender for Endpoint オンボード デバイス (クライアントまたはサーバー) を決定します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-138">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="6dfac-139">Defender for Endpoint 評価デバイスと対象ネットワーク デバイス間の SNMP トラフィックを許可する必要があります (ファイアウォールなど)。</span><span class="sxs-lookup"><span data-stu-id="6dfac-139">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="6dfac-140">脆弱性に対して評価されるネットワーク デバイスを決定します (たとえば、Cisco スイッチや Palo Alto Networks ファイアウォール)。</span><span class="sxs-lookup"><span data-stu-id="6dfac-140">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="6dfac-141">構成済みのすべてのネットワーク デバイスで SNMP 読み取り専用が有効になっているので、Defender for Endpoint 評価デバイスが構成済みのネットワーク デバイスに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-141">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="6dfac-142">この機能の適切な機能には「SNMP 書き込み」は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="6dfac-142">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="6dfac-143">スキャンするネットワーク デバイス (またはこれらのデバイスが展開されているサブネット) の IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-143">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="6dfac-144">ネットワーク デバイスの SNMP 資格情報を取得します (たとえば、コミュニティ文字列、noAuthNoPriv、authNoPriv、authPriv)。</span><span class="sxs-lookup"><span data-stu-id="6dfac-144">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="6dfac-145">新しい評価ジョブを構成するときに資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-145">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="6dfac-146">プロキシ クライアントの構成: Defender for Endpoint デバイス プロキシの要件以外に、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6dfac-146">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="6dfac-147">ネットワーク スキャナーを認証して適切に動作するには、次のドメイン/URL を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-147">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="6dfac-148">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="6dfac-148">login.windows.net</span></span>  
    - <span data-ttu-id="6dfac-149">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="6dfac-149">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="6dfac-150">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6dfac-150">login.microsoftonline.com</span></span>
    - <span data-ttu-id="6dfac-151">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="6dfac-151">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    <span data-ttu-id="6dfac-152">注: すべての URL が、許可されたデータ収集の Defender for Endpoint ドキュメントリストで指定されていない場合。</span><span class="sxs-lookup"><span data-stu-id="6dfac-152">Note: Not all URLs are not specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="6dfac-153">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6dfac-153">Permissions</span></span>

<span data-ttu-id="6dfac-154">評価ジョブを構成するには、次のユーザーアクセス許可オプションが必要です。セキュリティ センター **でセキュリティ設定を管理します**。</span><span class="sxs-lookup"><span data-stu-id="6dfac-154">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="6dfac-155">アクセス許可は、[設定の役割] に **移動して**  >  **確認できます**。</span><span class="sxs-lookup"><span data-stu-id="6dfac-155">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="6dfac-156">詳細については、「役割ベースの [アクセス制御の役割の作成と管理」を参照してください。](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6dfac-156">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="6dfac-157">ネットワーク スキャナーのインストール</span><span class="sxs-lookup"><span data-stu-id="6dfac-157">Install the network scanner</span></span>

1. <span data-ttu-id="6dfac-158">Microsoft **365 セキュリティ** 設定  >    >  **エンドポイント**  >  **評価** ジョブ ([ネットワーク評価] の下) に移動します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-158">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under 'Network assessments').</span></span>
    1. <span data-ttu-id="6dfac-159">Microsoft Defender セキュリティ センターで、[評価ジョブの設定>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-159">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="6dfac-160">ネットワーク スキャナーをダウンロードし、指定された Defender for Endpoint 評価デバイスにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6dfac-160">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

![[スキャナーのダウンロード] ボタン](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="6dfac-162">ネットワーク スキャナーのインストール&登録</span><span class="sxs-lookup"><span data-stu-id="6dfac-162">Network scanner installation & registration</span></span>

<span data-ttu-id="6dfac-163">サインイン プロセスは、指定された評価デバイス自体または他のデバイス (個人用クライアント デバイスなど) で完了できます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-163">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="6dfac-164">ネットワーク スキャナーの登録プロセスを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-164">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="6dfac-165">コマンド ラインに表示される URL をコピーしてフォローし、提供されたインストール コードを使用して登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-165">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>
    - <span data-ttu-id="6dfac-166">注: URL をコピーするには、コマンド プロンプトの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-166">Note: You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="6dfac-167">コードを入力し、「セキュリティ センターでセキュリティ設定を管理する」と呼ばれる Defender for Endpoint アクセス許可を持つ Microsoft アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="6dfac-167">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="6dfac-168">完了すると、サインインしたというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-168">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="6dfac-169">新しい評価ジョブを構成する</span><span class="sxs-lookup"><span data-stu-id="6dfac-169">Configure a new assessment job</span></span>  

<span data-ttu-id="6dfac-170">[設定] の [評価ジョブ] **ページで、[** ネットワーク **評価ジョブの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6dfac-170">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="6dfac-171">セットアップ プロセスに従って、定期的にスキャンしてデバイス インベントリに追加するネットワーク デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-171">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="6dfac-172">ネットワーク デバイス インベントリでデバイスの重複を防止するには、各 IP アドレスが複数の評価デバイスで 1 回だけ構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-172">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

![[ネットワーク評価ジョブの追加] ボタン](images/assessment-jobs-add.png)

<span data-ttu-id="6dfac-174">ネットワーク評価ジョブステップの追加:</span><span class="sxs-lookup"><span data-stu-id="6dfac-174">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="6dfac-175">ネットワーク スキャナーがインストールされた 'Assessment job' 名と 'Assessment device' を選択します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-175">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="6dfac-176">このデバイスは、定期的に認証されたスキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-176">This device will perform the periodic authenticated scans.</span></span> 
2. <span data-ttu-id="6dfac-177">スキャンするターゲット ネットワーク デバイス (またはこれらのデバイスが展開されているサブネット) の IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-177">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 
3. <span data-ttu-id="6dfac-178">ターゲット ネットワーク デバイスの必要な SNMP 資格情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-178">Add required SNMP credentials of the target network devices.</span></span> 
4. <span data-ttu-id="6dfac-179">新しく構成されたネットワーク評価ジョブを保存して、定期的なネットワーク スキャンを開始します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-179">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="6dfac-180">ネットワーク デバイスのスキャンと追加</span><span class="sxs-lookup"><span data-stu-id="6dfac-180">Scan and add network devices</span></span>

<span data-ttu-id="6dfac-181">セットアップ プロセス中に、1 回のテスト スキャンを実行して、次の処理を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-181">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="6dfac-182">Defender for Endpoint 評価デバイスと構成済みのターゲット ネットワーク デバイスの間に接続があります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-182">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="6dfac-183">構成済みの SNMP 資格情報が正しい。</span><span class="sxs-lookup"><span data-stu-id="6dfac-183">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="6dfac-184">各評価デバイスは、最大 1,500 の成功した IP アドレス スキャンをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-184">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="6dfac-185">たとえば、10 の異なるサブネットをスキャンすると、100 の IP アドレスだけが成功した結果を返す場合、同じ評価デバイス上の他のサブネットから 1,400 の IP 追加アドレスをスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-185">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="6dfac-186">スキャンする IP アドレス範囲/サブネットが複数ある場合、テスト スキャンの結果が表示されるのに数分かかります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-186">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="6dfac-187">テスト スキャンは、最大 1,024 アドレスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-187">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="6dfac-188">結果が表示された後、定期的なスキャンに含めるデバイスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-188">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="6dfac-189">スキャン結果の表示をスキップすると、構成済みのすべての IP アドレスがネットワーク評価ジョブに追加されます (デバイスの応答に関係なく)。</span><span class="sxs-lookup"><span data-stu-id="6dfac-189">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="6dfac-190">スキャン結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-190">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="6dfac-191">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="6dfac-191">Device inventory</span></span>

<span data-ttu-id="6dfac-192">新しく検出されたデバイスは、[デバイス インベントリ] ページの [新しい **ネットワーク** デバイス] タブ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-192">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="6dfac-193">デバイスが更新されるまで、評価ジョブを追加するまでに最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-193">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

![[デバイス インベントリ] の [ネットワーク デバイス] セクション](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a><span data-ttu-id="6dfac-195">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6dfac-195">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="6dfac-196">ネットワーク スキャナーのインストールに失敗しました</span><span class="sxs-lookup"><span data-stu-id="6dfac-196">Network scanner installation has failed</span></span>

<span data-ttu-id="6dfac-197">ファイアウォール設定で、許可されているドメインに必要な URL が追加されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-197">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="6dfac-198">また、「デバイス プロキシとインターネット接続の設定を構成する」の説明に従ってプロキシ [設定が構成されていることを確認します。](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="6dfac-198">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="6dfac-199">Web Microsoft.com/devicelogin が表示されない</span><span class="sxs-lookup"><span data-stu-id="6dfac-199">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="6dfac-200">必要な URL がファイアウォールで許可されているドメインに追加されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-200">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="6dfac-201">また、「デバイス プロキシとインターネット接続の設定を構成する」の説明に従ってプロキシ [設定が構成されていることを確認します](configure-proxy-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="6dfac-201">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="6dfac-202">数時間後にネットワーク デバイスがデバイス インベントリに表示されない</span><span class="sxs-lookup"><span data-stu-id="6dfac-202">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="6dfac-203">スキャン結果は、評価ジョブの構成が完了した後に行った最初のスキャンの数時間後に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dfac-203">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="6dfac-204">デバイスがまだ表示されない場合は、ネットワーク スキャナーをインストールした評価デバイスでサービス 'MdatpNetworkScanService' が実行されていることを確認し、関連する評価ジョブ構成で "スキャンの実行" を実行します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-204">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="6dfac-205">5 分後に結果が得られた場合は、サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-205">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="6dfac-206">デバイスの最終表示時間が 24 時間を超える</span><span class="sxs-lookup"><span data-stu-id="6dfac-206">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="6dfac-207">スキャナーが正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-207">Validate that the scanner is running properly.</span></span> <span data-ttu-id="6dfac-208">次に、スキャン定義に移動し、[テストの実行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-208">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="6dfac-209">関連する IP アドレスから返されるエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-209">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="6dfac-210">必須の脅威と脆弱性管理ユーザーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6dfac-210">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="6dfac-211">登録が完了し、エラーが発生しました。"新しいエージェントを追加するための十分なアクセス許可がないように見えます。</span><span class="sxs-lookup"><span data-stu-id="6dfac-211">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="6dfac-212">必要なアクセス許可は、「セキュリティ センターでセキュリティ設定を管理する」です。</span><span class="sxs-lookup"><span data-stu-id="6dfac-212">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="6dfac-213">任意のキーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-213">Press any key to exit.</span></span>

<span data-ttu-id="6dfac-214">必要なアクセス許可を割り当てるには、システム管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6dfac-214">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="6dfac-215">または、別の関連メンバーにサインイン コードとリンクを提供してサインイン プロセスを支援します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-215">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="6dfac-216">登録プロセスでコマンド ラインの指定されたリンクを使用して登録プロセスが失敗する</span><span class="sxs-lookup"><span data-stu-id="6dfac-216">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="6dfac-217">別のブラウザーを試したり、サインイン リンクとコードを別のデバイスにコピーしたりします。</span><span class="sxs-lookup"><span data-stu-id="6dfac-217">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="6dfac-218">テキストが小さすぎるか、コマンド ラインからテキストをコピーできない</span><span class="sxs-lookup"><span data-stu-id="6dfac-218">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="6dfac-219">デバイスのコマンド ライン設定を変更して、テキスト サイズのコピーと変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="6dfac-219">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6dfac-220">関連記事</span><span class="sxs-lookup"><span data-stu-id="6dfac-220">Related articles</span></span>

- [<span data-ttu-id="6dfac-221">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="6dfac-221">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="6dfac-222">高度な機能を構成する</span><span class="sxs-lookup"><span data-stu-id="6dfac-222">Configure advanced features</span></span>](advanced-features.md)
