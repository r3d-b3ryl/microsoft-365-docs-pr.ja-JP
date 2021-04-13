---
title: デバイスの検出に関するよく寄せられる質問
description: デバイスの検出に関するよく寄せられる質問 (FAQ) に対する回答を検索する
keywords: デバイスの検出、検出、パッシブ、プロアクティブ、ネットワーク、可視性、サーバー、ワークステーション、オンボード、管理されていないデバイス
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7165d943fd39e298894531f1dabdec408144898d
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698469"
---
# <a name="device-discovery-frequently-asked-questions"></a><span data-ttu-id="3c181-104">デバイスの検出に関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3c181-104">Device discovery frequently asked questions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c181-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3c181-105">**Applies to:**</span></span>
- [<span data-ttu-id="3c181-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3c181-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3c181-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c181-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3c181-108">デバイスの検出に関するよく寄せられる質問 (FAQ) に対する回答を検索します。</span><span class="sxs-lookup"><span data-stu-id="3c181-108">Find answers to frequently asked questions (FAQs) about device discovery.</span></span>

## <a name="what-is-basic-discovery-mode"></a><span data-ttu-id="3c181-109">基本検出モードとは</span><span class="sxs-lookup"><span data-stu-id="3c181-109">What is Basic discovery mode?</span></span>
<span data-ttu-id="3c181-110">このモードでは、すべての Microsoft Defender for Endpoint オンボード デバイスがネットワーク データを収集し、隣接するデバイスを検出できます。</span><span class="sxs-lookup"><span data-stu-id="3c181-110">This mode allows every Microsoft Defender for Endpoint onboarded device to collect network data and discover neighboring devices.</span></span> <span data-ttu-id="3c181-111">オンボードエンドポイントは、ネットワーク内のイベントをパッシブに収集し、そこからデバイス情報を抽出します。</span><span class="sxs-lookup"><span data-stu-id="3c181-111">Onboarded endpoints passively collect events in the network and extract device information from them.</span></span> <span data-ttu-id="3c181-112">ネットワーク トラフィックは開始されません。</span><span class="sxs-lookup"><span data-stu-id="3c181-112">No network traffic will be initiated.</span></span> <span data-ttu-id="3c181-113">オンボードエンドポイントは、オンボードされたデバイスで見られるすべてのネットワーク トラフィックからデータを抽出するだけで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3c181-113">Onboarded endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> <span data-ttu-id="3c181-114">ネットワーク内の管理されていないデバイスを一覧表示するために使用されるこのデータ。</span><span class="sxs-lookup"><span data-stu-id="3c181-114">This data used to list unmanaged devices in your network.</span></span>

## <a name="can-i-disable-basic-discovery"></a><span data-ttu-id="3c181-115">基本検出を無効にできますか?</span><span class="sxs-lookup"><span data-stu-id="3c181-115">Can I disable Basic discovery?</span></span>
<span data-ttu-id="3c181-116">[高度な機能] ページでデバイスの検出を [無効にするオプション](advanced-features.md) があります。</span><span class="sxs-lookup"><span data-stu-id="3c181-116">You have the option to turn off device discovery through the [Advanced features](advanced-features.md) page.</span></span> <span data-ttu-id="3c181-117">ただし、ネットワーク内の管理されていないデバイスの表示が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c181-117">However, you will lose visibility on unmanaged devices in your network.</span></span> 

## <a name="what-is-standard-discovery-mode"></a><span data-ttu-id="3c181-118">標準検出モードとは</span><span class="sxs-lookup"><span data-stu-id="3c181-118">What is Standard discovery mode?</span></span>
 <span data-ttu-id="3c181-119">このモードでは、Microsoft Defender for Endpoint にオンボードされたエンドポイントは、ネットワーク内の監視されたデバイスをアクティブにプローブして、収集されたデータを強化できます (ネットワーク トラフィックの量はごくわずかです)。</span><span class="sxs-lookup"><span data-stu-id="3c181-119">In this mode endpoints onboarded to Microsoft Defender for Endpoint can actively probe observed devices in the network to enrich collected data (with negligible amount of network traffic).</span></span> <span data-ttu-id="3c181-120">このモードは、信頼性の高い一貫性のあるデバイス インベントリを構築する場合に強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c181-120">This mode is highly recommended for building a reliable and coherent device inventory.</span></span> <span data-ttu-id="3c181-121">このモードを無効にし、[基本検出モード] を選択すると、ネットワーク内の管理されていないエンドポイントの表示が制限される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c181-121">If you choose to disable this mode, and select Basic discovery mode, you will likely only gain limited visibility of unmanaged endpoints in your network.</span></span>

## <a name="can-i-control-which-devices-perform-standard-discovery"></a><span data-ttu-id="3c181-122">標準検出を実行するデバイスを制御できますか?</span><span class="sxs-lookup"><span data-stu-id="3c181-122">Can I control which devices perform Standard discovery?</span></span>
 <span data-ttu-id="3c181-123">Standard Discovery の実行に使用されるデバイスの一覧をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3c181-123">You can customize the list of devices that are used to perform Standard discovery.</span></span> <span data-ttu-id="3c181-124">この機能をサポートしているすべてのオンボード デバイス (現在は Windows 10 デバイスのみ) で Standard Discovery を有効にするか、デバイス タグを指定してデバイスのサブセットまたはサブセットを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3c181-124">You can either enable Standard discovery on all the onboarded devices that also support this capability (currently Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> <span data-ttu-id="3c181-125">この場合、他のすべてのデバイスは基本検出のみを実行するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="3c181-125">In this case, all other devices will be configured to run Basic discovery only.</span></span> <span data-ttu-id="3c181-126">構成は、[デバイスの検出設定] ページで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c181-126">The configuration is available in the device discovery settings page.</span></span>

## <a name="which-onboarded-devices-can-perform-discovery"></a><span data-ttu-id="3c181-127">検出を実行できるオンボード デバイス</span><span class="sxs-lookup"><span data-stu-id="3c181-127">Which onboarded devices can perform discovery?</span></span>
 <span data-ttu-id="3c181-128">Windows 10 バージョン 1809 以降で実行されているオンボード デバイスは、検出を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3c181-128">Onboarded devices running on Windows 10 version 1809 or later can perform discovery.</span></span>

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a><span data-ttu-id="3c181-129">オンボード デバイスがホーム ネットワークまたはパブリック アクセス ポイントに接続されている場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="3c181-129">What happens if my onboarded devices is connected to my home network, or to public access point?</span></span>
 <span data-ttu-id="3c181-130">検出エンジンは、企業ネットワークで受信されるネットワーク イベントと企業ネットワーク外のネットワーク イベントを区別します。</span><span class="sxs-lookup"><span data-stu-id="3c181-130">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="3c181-131">すべてのテナントのクライアント間でネットワーク識別子を関連付け、プライベート ネットワークから受信したイベントと企業ネットワークの間でイベントが区別されます。</span><span class="sxs-lookup"><span data-stu-id="3c181-131">By correlating network identifiers across all tenant's clients, events are differentiated between ones that were received from private networks and corporate networks.</span></span> <span data-ttu-id="3c181-132">プライベート ネットワーク デバイスはインベントリに表示され、アクティブにプローブされません。</span><span class="sxs-lookup"><span data-stu-id="3c181-132">Private network devices will not be listed in the inventory and will not be actively probed.</span></span>

## <a name="what-protocols-are-you-capturing-and-analyzing"></a><span data-ttu-id="3c181-133">キャプチャと分析を行うプロトコルは何ですか?</span><span class="sxs-lookup"><span data-stu-id="3c181-133">What protocols are you capturing and analyzing?</span></span>
 <span data-ttu-id="3c181-134">既定では、Windows 10 バージョン 1809 以降で実行されているオンボード デバイスはすべて、ARP、CDP、DHCP、DHCPv6、IP (ヘッダー)、LLDP、LLMNR、mDNS、MNDP、NBNS、SSDP、TCP (ヘッダー)、UDP (ヘッダー)、WSD のプロトコルをキャプチャおよび分析しています。</span><span class="sxs-lookup"><span data-stu-id="3c181-134">By default, all onboarded devices running on Windows 10 version 1809 or later are capturing and analyzing the following protocols: ARP, CDP, DHCP, DHCPv6, IP (headers), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (headers), UDP (headers), WSD</span></span>

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a><span data-ttu-id="3c181-135">Standard Discovery でアクティブなプロビリングに使用するプロトコルは何ですか?</span><span class="sxs-lookup"><span data-stu-id="3c181-135">Which protocols do you use for active probing in Standard discovery?</span></span>
 <span data-ttu-id="3c181-136">デバイスが標準検出を実行するように構成されている場合、公開されたサービスは、ARP、FTP、HTTP、ICMP、LLMNR、NBNS、RDP、SIP、SMTP、SNMP、SSH、Telnet、UPNP、WSD、SMB、NBSS、IPP、PJL を使用してプローブされます。</span><span class="sxs-lookup"><span data-stu-id="3c181-136">When a device is configured to run Standard discovery, exposed services are being probed by using the following protocols: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL</span></span>

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a><span data-ttu-id="3c181-137">標準検出でターゲットをプローブから除外する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="3c181-137">How can I exclude targets from being probed with Standard discovery?</span></span>
 <span data-ttu-id="3c181-138">ネットワーク上にアクティブにプローブしないデバイスがある場合は、除外リストを定義してスキャンを防止することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c181-138">If there are devices on your network which should not be actively probed, you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="3c181-139">構成は、[デバイスの検出設定] ページで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c181-139">The configuration is available in the device discovery settings page.</span></span>

## <a name="can-i-exclude-devices-from-being-discovered"></a><span data-ttu-id="3c181-140">デバイスを検出から除外できますか?</span><span class="sxs-lookup"><span data-stu-id="3c181-140">Can I exclude devices from being discovered?</span></span>
 <span data-ttu-id="3c181-141">デバイス検出ではパッシブ メソッドを使用してネットワーク内のデバイスを検出します。企業ネットワーク内のオンボード デバイスと通信するデバイスは、インベントリ内で検出および一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c181-141">As device discovery uses passive methods to discover devices in the network, any device that communicates with your onboarded devices in the corporate network can be discovered and listed in the inventory.</span></span> <span data-ttu-id="3c181-142">アクティブなプロビリングからのみデバイスを除外できます。</span><span class="sxs-lookup"><span data-stu-id="3c181-142">You can exclude devices from active probing only.</span></span>

## <a name="how-frequent-is-the-active-probing"></a><span data-ttu-id="3c181-143">アクティブなプロブの頻度はどのくらいですか?</span><span class="sxs-lookup"><span data-stu-id="3c181-143">How frequent is the active probing?</span></span>
 <span data-ttu-id="3c181-144">デバイスの特性の変化が観察された場合、および既存の情報が最新の状態を確認するために週に 1 回、デバイスがアクティブにプローブされます。</span><span class="sxs-lookup"><span data-stu-id="3c181-144">Devices will actively be probed when changes in device characteristics are observed, and once a week to make sure the existing information is up-to-date.</span></span>

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a><span data-ttu-id="3c181-145">セキュリティ ツールによって開始されたUnicastScanner.ps1スキャン アクティビティに関するアラートが発生しました。何を行う必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="3c181-145">My security tool raised alert on UnicastScanner.ps1 or port scanning activity initiated by it, what should I do?</span></span>
 <span data-ttu-id="3c181-146">アクティブなプロブ スクリプトは Microsoft によって署名され、安全です。</span><span class="sxs-lookup"><span data-stu-id="3c181-146">The active probing scripts are signed by Microsoft and are safe.</span></span> <span data-ttu-id="3c181-147">除外リストに次のパスを追加できます。 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span><span class="sxs-lookup"><span data-stu-id="3c181-147">You can add the following path to your exclusion list: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span></span>


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a><span data-ttu-id="3c181-148">Standard Discovery アクティブ プローブによって生成されるトラフィックの量は何ですか?</span><span class="sxs-lookup"><span data-stu-id="3c181-148">What is the amount of traffic being generated by the Standard discovery active probe?</span></span>
 <span data-ttu-id="3c181-149">アクティブプローブは、オンボードデバイスとプローブされたデバイスの間で最大 5K のトラフィックを生成できます。すべてのプローブ試行</span><span class="sxs-lookup"><span data-stu-id="3c181-149">Active probing can generate up to 5K of traffic between the onboarded device and the probed device, every probing attempt</span></span>

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a><span data-ttu-id="3c181-150">デバイス インベントリ内の "オンボード可能" デバイスと、ダッシュボード タイル内の "オンボードするデバイス" の数との間に不一致がある理由</span><span class="sxs-lookup"><span data-stu-id="3c181-150">Why is there a discrepancy between "can be onboarded" devices in the device inventory, and the number of "devices to onboard" in the dashboard tile?</span></span>
<span data-ttu-id="3c181-151">デバイス インベントリの [オンボード可能] の下にリストされているデバイスの数、"Microsoft Defender for Endpoint にオンボード" セキュリティ推奨事項、および "オンボードするデバイス" ダッシュボード ウィジェットの数の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="3c181-151">You may notice differences between the number of listed devices under "can be onboarded" in the device inventory, "onboard to Microsoft Defender for Endpoint" security recommendation, and "devices to onboard" dashboard widget.</span></span>

 <span data-ttu-id="3c181-152">セキュリティの推奨事項とダッシュボード ウィジェットは、ネットワーク内で安定しているデバイス用です。一時的なデバイス、ゲスト デバイス、その他を除く。</span><span class="sxs-lookup"><span data-stu-id="3c181-152">The security recommendation and the dashboard widget are for devices that are stable in the network; excluding ephemeral devices, guest devices and others.</span></span> <span data-ttu-id="3c181-153">このアイデアは、組織の全体的なセキュリティ スコアを示す永続的なデバイスで推奨する方法です。</span><span class="sxs-lookup"><span data-stu-id="3c181-153">The idea is to recommend on persistent devices, that also imply on the overall security score of the organization.</span></span>

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a><span data-ttu-id="3c181-154">検出された管理されていないデバイスをオンボードできますか?</span><span class="sxs-lookup"><span data-stu-id="3c181-154">Can I onboard unmanaged devices that were found?</span></span>
 <span data-ttu-id="3c181-155">はい。</span><span class="sxs-lookup"><span data-stu-id="3c181-155">Yes.</span></span> <span data-ttu-id="3c181-156">ネットワーク内の管理されていないエンドポイントは、ネットワークに脆弱性とリスクを導入します。</span><span class="sxs-lookup"><span data-stu-id="3c181-156">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="3c181-157">サービスにオンボーディングすると、セキュリティの可視性が向上します。</span><span class="sxs-lookup"><span data-stu-id="3c181-157">Onboarding them to the service can increase the security visibility on them.</span></span> 


