---
title: 手順 2.  エンタープライズ テナント向け Microsoft 365 の最適なネットワーク
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントへのネットワーク アクセスを最適化します。
ms.openlocfilehash: 1e57911a6e8c51af3ae00ff0f9053bf9273e0e17
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908649"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="62830-104">手順 2.</span><span class="sxs-lookup"><span data-stu-id="62830-104">Step 2.</span></span> <span data-ttu-id="62830-105">エンタープライズ テナント向け Microsoft 365 の最適なネットワーク</span><span class="sxs-lookup"><span data-stu-id="62830-105">Optimal networking for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="62830-106">Microsoft 365 enterprise には、Teams、Exchange Online、Microsoft Intune などのクラウド生産性向上アプリと、Microsoft Azure の多くの ID およびセキュリティ サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62830-106">Microsoft 365 for enterprise includes cloud productivity apps such as Teams and Exchange Online, and Microsoft Intune, along with many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="62830-107">これらのクラウドベースのサービスはすべて、オンプレミス ネットワーク上またはインターネット上の任意の場所にあるクライアント デバイスからの接続のセキュリティ、パフォーマンス、および信頼性に依存します。</span><span class="sxs-lookup"><span data-stu-id="62830-107">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices on your on-premises network or any location on the Internet.</span></span> 

<span data-ttu-id="62830-108">テナントのネットワーク アクセスを最適化するには、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="62830-108">To optimize network access for your tenant, you need to:</span></span>

- <span data-ttu-id="62830-109">オンプレミス ユーザーと Microsoft グローバル ネットワークに最も近い場所との間のパスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="62830-109">Optimize the path between your on-premises users and the closest location to the Microsoft Global Network.</span></span>
- <span data-ttu-id="62830-110">リモート アクセス VPN ソリューションを使用しているリモート ユーザーの Microsoft グローバル ネットワークへのアクセスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="62830-110">Optimize access to the Microsoft Global Network for your remote users that are using a remote access VPN solution.</span></span>
- <span data-ttu-id="62830-111">Network Insights を使用して、オフィスの場所のネットワーク境界を設計します。</span><span class="sxs-lookup"><span data-stu-id="62830-111">Use Network Insights to design the network perimeter for your office locations.</span></span>
- <span data-ttu-id="62830-112">Office 365 CDN を使用して、SharePoint サイトでホストされている特定のアセットへのアクセスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="62830-112">Optimize access to specific assets hosted on SharePoint sites with the Office 365 CDN.</span></span>
- <span data-ttu-id="62830-113">エンドポイントの一覧を使用して Microsoft 365 の信頼されたトラフィックの処理をバイパスし、変更が行われた場合にリストの更新を自動化するプロキシおよびネットワーク エッジ デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="62830-113">Configure proxy and network edge devices to bypass processing for Microsoft 365 trusted traffic with the list of endpoints and automate the updating of the list as changes are made.</span></span>

## <a name="enterprise-on-premises-workers"></a><span data-ttu-id="62830-114">エンタープライズ オンプレミス ワーカー</span><span class="sxs-lookup"><span data-stu-id="62830-114">Enterprise on-premises workers</span></span>

<span data-ttu-id="62830-115">エンタープライズ ネットワークの場合は、クライアントと最も近い Microsoft 365 エンドポイント間で最高パフォーマンスのネットワーク アクセスを有効にすることで、エンド ユーザー エクスペリエンスを最適化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62830-115">For enterprise networks, you should optimize the end user experience by enabling the highest-performing network access between clients and the closest Microsoft 365 endpoints.</span></span> <span data-ttu-id="62830-116">エンド ユーザー エクスペリエンスの品質は、ユーザーが使用しているアプリケーションのパフォーマンスと応答性に直接関係します。</span><span class="sxs-lookup"><span data-stu-id="62830-116">The quality of end user experience is directly related to the performance and responsiveness of the application that the user is using.</span></span> <span data-ttu-id="62830-117">たとえば、Microsoft Teams は待機時間が短く、ユーザーの電話、会議、共有画面のコラボレーションが不具合の発生を抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="62830-117">For example, Microsoft Teams relies on low latency so that user phone calls, conferences and shared screen collaborations are glitch-free.</span></span>

<span data-ttu-id="62830-118">ネットワーク設計の主な目標は、クライアント デバイスから Microsoft グローバル ネットワークへの往復時間 (RTT) を短縮することで待機時間を最小限に抑える必要があります。これは、Microsoft のパブリック ネットワーク バックボーンで、Microsoft のすべてのデータセンターを低待機時間で相互接続するパブリック ネットワーク バックボーンで、フロント ドアと呼ばれる高可用性クラウド アプリケーション エントリ ポイントが世界中に広がっています。</span><span class="sxs-lookup"><span data-stu-id="62830-118">The primary goal in the network design should be to minimize latency by reducing the round-trip time (RTT) from client devices to the Microsoft Global Network, Microsoft's public network backbone that interconnects all of Microsoft's datacenters with low latency, high availability cloud application entry points, known as front doors, spread around the world.</span></span>

<span data-ttu-id="62830-119">従来のエンタープライズ ネットワークの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62830-119">Here is an example of a traditional enterprise network.</span></span>

![インターネットへの集中アクセスを備え、従来のエンタープライズ ネットワーク](../media/tenant-management-overview/tenant-management-networking-traditional.png)

<span data-ttu-id="62830-121">この図では、ブランチ オフィスはワイド エリア ネットワーク (WAN) デバイスと WAN バックボーンを介して中央オフィスに接続します。</span><span class="sxs-lookup"><span data-stu-id="62830-121">In this illustration, branch offices connect to a central office through wide area network (WAN) devices and a WAN backbone.</span></span> <span data-ttu-id="62830-122">インターネット アクセスは、中央オフィスとインターネット サービス プロバイダー (ISP) のネットワーク エッジにあるセキュリティ デバイスまたはプロキシ デバイスを介して行います。</span><span class="sxs-lookup"><span data-stu-id="62830-122">Internet access is through a security or proxy device at the network edge of the central office and an Internet service provider (ISP).</span></span> <span data-ttu-id="62830-123">インターネット上で、Microsoft グローバル ネットワークには、世界中の地域に一連のフロント ドアがあります。</span><span class="sxs-lookup"><span data-stu-id="62830-123">On the Internet, the Microsoft Global Network has a series of front doors in regions around the world.</span></span> <span data-ttu-id="62830-124">組織は、トラフィックの追加パケット処理とセキュリティのために中間の場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="62830-124">Organizations can also use intermediate locations for additional packet processing and security for traffic.</span></span> <span data-ttu-id="62830-125">組織の Microsoft 365 テナントは、Microsoft グローバル ネットワーク内に位置します。</span><span class="sxs-lookup"><span data-stu-id="62830-125">An organization's Microsoft 365 tenant is located within the Microsoft Global Network.</span></span>

<span data-ttu-id="62830-126">Microsoft 365 クラウド サービスのこの構成の問題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="62830-126">The problems with this configuration for Microsoft 365 cloud services are:</span></span>

- <span data-ttu-id="62830-127">ブランチ オフィスのユーザーの場合、トラフィックはローカル以外のフロント ドアに送信され、待機時間が増加します。</span><span class="sxs-lookup"><span data-stu-id="62830-127">For users in branch offices, traffic gets sent to non-local front doors, increasing latency.</span></span>
- <span data-ttu-id="62830-128">中間の場所にトラフィックを送信すると、信頼されたトラフィックで重複するパケット処理を実行するネットワーク ヘアピンが作成され、待機時間が増加します。</span><span class="sxs-lookup"><span data-stu-id="62830-128">Sending traffic to intermediate locations create network hairpins that perform duplicate packet processing on trusted traffic, increasing latency.</span></span>
- <span data-ttu-id="62830-129">ネットワーク エッジ デバイスは、信頼されたトラフィックで不要で重複するパケット処理を実行し、待機時間を増加します。</span><span class="sxs-lookup"><span data-stu-id="62830-129">Network edge devices perform unneeded and duplicate packet processing on trusted traffic, increasing latency.</span></span>

<span data-ttu-id="62830-130">Microsoft 365 のネットワーク パフォーマンスの最適化は複雑である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="62830-130">Optimizing Microsoft 365 network performance doesn't need to be complicated.</span></span> <span data-ttu-id="62830-131">いくつかの主要な原則に従って、最高のパフォーマンスを得る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62830-131">You can get the best possible performance by following a few key principles:</span></span>

- <span data-ttu-id="62830-132">Microsoft 365 ネットワーク トラフィックを特定します。これは、Microsoft クラウド サービス宛ての信頼されたトラフィックです。</span><span class="sxs-lookup"><span data-stu-id="62830-132">Identify Microsoft 365 network traffic, which is trusted traffic destined to Microsoft cloud services.</span></span>
- <span data-ttu-id="62830-133">ユーザーが Microsoft 365 に接続する各場所からインターネットへの Microsoft 365 ネットワーク トラフィックのローカルブランチエグレスを許可します。</span><span class="sxs-lookup"><span data-stu-id="62830-133">Allow local branch egress of Microsoft 365 network traffic to the internet from each location where users connect to Microsoft 365.</span></span>
- <span data-ttu-id="62830-134">ネットワーク ヘアピンを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="62830-134">Avoid network hairpins.</span></span>
- <span data-ttu-id="62830-135">Microsoft 365 トラフィックがプロキシとパケット検査デバイスをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="62830-135">Allow Microsoft 365 traffic to bypass proxies and packet inspection devices.</span></span>

<span data-ttu-id="62830-136">これらの原則を実装すると、Microsoft 365 向けに最適化されたエンタープライズ ネットワークを利用できます。</span><span class="sxs-lookup"><span data-stu-id="62830-136">If you implement these principles, you get an enterprise network optimized for Microsoft 365.</span></span>

![Microsoft 365 向けに最適化されたエンタープライズ ネットワーク](../media/tenant-management-overview/tenant-management-networking-optimized.png)

<span data-ttu-id="62830-138">この図では、ブランチ オフィスはソフトウェア定義 WAN デバイス (SDWAN) デバイスを介して独自のインターネット接続を確立し、信頼できる Microsoft 365 トラフィックを地域で最も近いフロント ドアに送信します。</span><span class="sxs-lookup"><span data-stu-id="62830-138">In this illustration, branch offices have their own Internet connection through a software-defined WAN device (SDWAN) device, which sends trusted Microsoft 365 traffic to the regionally closest front door.</span></span> <span data-ttu-id="62830-139">中央オフィスでは、信頼できる Microsoft 365 トラフィックはセキュリティ デバイスまたはプロキシ デバイスをバイパスし、中間デバイスは使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="62830-139">At the central office, trusted Microsoft 365 traffic bypasses the security or proxy device and intermediate devices are no longer used.</span></span>

<span data-ttu-id="62830-140">最適化された構成が従来のエンタープライズ ネットワークの待機時間の問題を解決する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62830-140">Here's are how the optimized configuration solves the latency issues of a traditional enterprise network:</span></span>

- <span data-ttu-id="62830-141">信頼された Microsoft 365 トラフィックは WAN バックボーンをスキップし、すべてのオフィスのローカル フロント ドアに送信され、待機時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="62830-141">Trusted Microsoft 365 traffic skips the WAN backbone and is sent to local front doors for all offices, decreasing latency.</span></span>
- <span data-ttu-id="62830-142">重複するパケット処理を実行するネットワーク ヘアピンは、Microsoft 365 の信頼されたトラフィックではスキップされ、待機時間が減少します。</span><span class="sxs-lookup"><span data-stu-id="62830-142">Network hairpins that perform duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>
- <span data-ttu-id="62830-143">不要で重複するパケット処理を実行するネットワーク エッジ デバイスは、Microsoft 365 の信頼されたトラフィックではスキップされ、待機時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="62830-143">Network edge devices that perform unneeded and duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>

<span data-ttu-id="62830-144">詳細については [、Microsoft 365 ネットワーク接続の概要を参照してください](../enterprise/microsoft-365-networking-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="62830-144">For more information, see [Microsoft 365 network connectivity overview](../enterprise/microsoft-365-networking-overview.md).</span></span>

## <a name="remote-workers"></a><span data-ttu-id="62830-145">リモート ワーカー</span><span class="sxs-lookup"><span data-stu-id="62830-145">Remote workers</span></span>

<span data-ttu-id="62830-146">リモート ワーカーが従来の VPN クライアントを使用して組織ネットワークへのリモート アクセスを取得している場合は、VPN クライアントがスプリット トンネリング サポートを備えていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="62830-146">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span> <span data-ttu-id="62830-147">スプリット トンネリングを使用しない場合、すべてのリモート作業トラフィックは VPN 接続を介して送信され、そこで組織のエッジ デバイスに転送されて処理され、インターネット上で送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="62830-147">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span> <span data-ttu-id="62830-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="62830-148">Here is an example.</span></span>

![トンネリングのない VPN クライアントからのネットワーク トラフィック](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="62830-150">この図では、Microsoft 365 トラフィックは組織を通る間接的なルートを通る必要があります。このルートは、VPN クライアントの物理的な場所から遠く離れた Microsoft グローバル ネットワークのフロント ドアに転送される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62830-150">In this illustration, Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft Global Network front door far away from the VPN client’s physical location.</span></span> <span data-ttu-id="62830-151">この間接パスにより、ネットワーク トラフィックが遅延し、全体的なパフォーマンスを低下させます。</span><span class="sxs-lookup"><span data-stu-id="62830-151">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="62830-152">スプリッ トトンネリングを使用すると、VPN クライアントを構成して、特定の種類のトラフィックが VPN 接続を介して、組織ネットワークに送信されることを除外できます。</span><span class="sxs-lookup"><span data-stu-id="62830-152">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="62830-153">Microsoft 365 クラウドリソースへのアクセスを最適化するには、VPN 接続を介して、**最適化** カテゴリの Microsoft 365 エンドポイントへのトラフィックを除外するようにスプリット トンネリング VPN クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="62830-153">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="62830-154">詳細については[](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)[、365 Officeカテゴリと分割トン](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)ネリング用の最適化カテゴリ エンドポイントの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62830-154">For more information, see [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) and [the lists](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) of Optimize category endpoints for split tunneling.</span></span>

<span data-ttu-id="62830-155">スプリット トンネリングの結果として生じるトラフィック フローを次に示します。このトラフィックは、Microsoft 365 クラウド アプリへのトラフィックのほとんどが VPN 接続をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="62830-155">Here is the resulting traffic flow for split tunneling, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![トンネリングのある VPN クライアントからのネットワーク トラフィック](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="62830-157">この図では、VPN クライアントは、インターネットを通して直接、および Microsoft グローバル ネットワークに最も近いフロント ドアに Microsoft 365 クラウド サービスの重要なトラフィックを送信および受信します。</span><span class="sxs-lookup"><span data-stu-id="62830-157">In this illustration, the VPN client sends and receives crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest front door into the Microsoft Global Network.</span></span>

<span data-ttu-id="62830-158">詳細とガイダンスについては、「[VPN スプリット トンネリングを使用してリモート ユーザーの Office 365 の接続を最適化する](../enterprise/microsoft-365-vpn-split-tunnel.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="62830-158">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

## <a name="using-network-insights-preview"></a><span data-ttu-id="62830-159">ネットワーク インサイトの使用 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="62830-159">Using Network Insights (preview)</span></span>

<span data-ttu-id="62830-160">ネットワークインサイトは、Microsoft 365 テナントから収集されたパフォーマンス メトリックで、オフィスの場所のネットワーク境界を設計するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="62830-160">Network insights are performance metrics collected from your Microsoft 365 tenant that help you design network perimeters for your office locations.</span></span> <span data-ttu-id="62830-161">各インサイトは、オンプレミスのユーザーがテナントにアクセスしている地理的な場所ごとに、指定された問題のパフォーマンス特性に関するライブの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="62830-161">Each insight provides live details about the performance characteristics for a specified issue for each geographic location where on-premises users are accessing your tenant.</span></span>

<span data-ttu-id="62830-162">テナントには、次の 2 つのテナント レベルのネットワークインサイトが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="62830-162">There are two tenant level network insights that may be shown for the tenant:</span></span>

- [<span data-ttu-id="62830-163">接続の問題の影響を受け、Exchange のサンプル接続</span><span class="sxs-lookup"><span data-stu-id="62830-163">Exchange sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="62830-164">接続の問題の影響を受け、SharePoint のサンプル接続</span><span class="sxs-lookup"><span data-stu-id="62830-164">SharePoint sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

<span data-ttu-id="62830-165">各オフィスの場所に関する特定のネットワークインサイトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="62830-165">These are the specific network insights for each office location:</span></span>

- [<span data-ttu-id="62830-166">バックホールされたネットワークエグレス</span><span class="sxs-lookup"><span data-stu-id="62830-166">Backhauled network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [<span data-ttu-id="62830-167">近くの顧客に対して検出されたパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="62830-167">Better performance detected for customers near you</span></span>](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="62830-168">最適でない Exchange Online サービスフロント ドアの使用</span><span class="sxs-lookup"><span data-stu-id="62830-168">Use of a non-optimal Exchange Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="62830-169">最適でない SharePoint Online サービスフロント ドアの使用</span><span class="sxs-lookup"><span data-stu-id="62830-169">Use of a non-optimal SharePoint Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="62830-170">SharePoint フロント ドアからのダウンロード速度が低い</span><span class="sxs-lookup"><span data-stu-id="62830-170">Low download speed from SharePoint front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="62830-171">中国のユーザー最適なネットワークエグレス</span><span class="sxs-lookup"><span data-stu-id="62830-171">China user optimal network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
><span data-ttu-id="62830-172">Microsoft 365 管理センターのネットワークの分析情報、パフォーマンスに関する推奨事項、評価は、現在プレビュー状態です。</span><span class="sxs-lookup"><span data-stu-id="62830-172">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status.</span></span> <span data-ttu-id="62830-173">機能プレビュー プログラムに登録されている Microsoft 365 テナントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="62830-173">It is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

<span data-ttu-id="62830-174">詳細については [、「Microsoft 365 Network Insights」を参照してください](../enterprise/office-365-network-mac-perf-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="62830-174">For more information, see [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).</span></span>

## <a name="sharepoint-performance-with-the-office-365-cdn"></a><span data-ttu-id="62830-175">Office 365 CDN を使用した SharePoint のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="62830-175">SharePoint performance with the Office 365 CDN</span></span>

<span data-ttu-id="62830-176">クラウドベースのコンテンツ配信ネットワーク (CDN) を使用すると、読み込み時間を短縮し、帯域幅を節約し、応答速度を速くすることができます。</span><span class="sxs-lookup"><span data-stu-id="62830-176">A cloud-based Content Delivery Network (CDN) allows you to reduce load times, save bandwidth, and speed responsiveness.</span></span> <span data-ttu-id="62830-177">CDN は、グラフィック ファイルやビデオ ファイルなどの静的アセットを要求するブラウザーの近くにキャッシュすることでパフォーマンスを向上させます。これにより、ダウンロードの速度を上げ、待機時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="62830-177">A CDN improves performance by caching static assets such as graphic or video files closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="62830-178">Microsoft 365 E3 および E5 の SharePoint に付属する組み込みの Office 365 コンテンツ配信ネットワーク (CDN) を使用して静的アセットをホストし、SharePoint ページのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="62830-178">You can use the built-in Office 365 Content Delivery Network (CDN), included with SharePoint in Microsoft 365 E3 and E5, to host static assets to provide better performance for your SharePoint pages.</span></span>

<span data-ttu-id="62830-179">Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。</span><span class="sxs-lookup"><span data-stu-id="62830-179">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="62830-180">Office 365 CDN でホストするコンテンツの種類に応じて、パブリックの配信元、プライベートの配信元、または両方を追加できます。</span><span class="sxs-lookup"><span data-stu-id="62830-180">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins, or both.</span></span>

<span data-ttu-id="62830-181">展開および構成すると、Office 365 CDN はパブリックおよびプライベートの配信元からアセットをアップロードし、インターネット上に配置されたユーザーに高速にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62830-181">When deployed and configured, the Office 365 CDN uploads assets from public and private origins and makes them available for fast access to users located across the Internet.</span></span>

<span data-ttu-id="62830-182">![Office 365 CDN の展開](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN の展開")</span><span class="sxs-lookup"><span data-stu-id="62830-182">![Office 365 CDN deployed for users](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN deployed for users")</span></span>

<span data-ttu-id="62830-183">詳細については [、「SharePoint Online で Office 365 CDN](../enterprise/use-microsoft-365-cdn-with-spo.md)を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62830-183">For more information, see [Use the Office 365 CDN with SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md).</span></span>

## <a name="automated-endpoint-listing"></a><span data-ttu-id="62830-184">エンドポイントの自動一覧</span><span class="sxs-lookup"><span data-stu-id="62830-184">Automated endpoint listing</span></span>

<span data-ttu-id="62830-185">オンプレミスのクライアント、エッジ デバイス、およびクラウドベースのパケット分析サービスが信頼できる Microsoft 365 トラフィックの処理をスキップするには、Microsoft 365 サービスに対応するエンドポイントのセット (IP アドレス範囲と DNS 名) を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62830-185">To have your on-premises clients, edge devices, and cloud-based packet analysis services skip processing of trusted Microsoft 365 traffic, you must configure them with the set of endpoints (IP address ranges and DNS names) corresponding to Microsoft 365 services.</span></span> <span data-ttu-id="62830-186">これらのエンドポイントは、ファイアウォールや他のエッジ セキュリティ デバイス、クライアント コンピューターがプロキシをバイパスする PAC ファイル、ブランチ オフィスの SD-WAN デバイスで手動で構成できます。</span><span class="sxs-lookup"><span data-stu-id="62830-186">These endpoints can be manually configured in firewalls and other edge security devices, PAC files for client computers to bypass proxies, or SD-WAN devices at branch offices.</span></span> <span data-ttu-id="62830-187">ただし、エンドポイントは時間の間に変化し、これらの場所でエンドポイント リストを継続的に手動で保守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62830-187">However, the endpoints change over time, requiring ongoing manual maintenance of the endpoint lists in these locations.</span></span>

<span data-ttu-id="62830-188">クライアント PAC ファイルとネットワーク デバイスで Microsoft 365 エンドポイントの一覧と変更管理を自動化するには [、Office 365 IP アドレス](../enterprise/microsoft-365-ip-web-service.md)と URL REST ベースの Web サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="62830-188">To automate the listing and change management for Microsoft 365 endpoints in your client PAC files and network devices, use the [Office 365 IP Address and URL REST-based web service](../enterprise/microsoft-365-ip-web-service.md).</span></span> <span data-ttu-id="62830-189">このサービスは、Microsoft 365 のネットワーク トラフィックをより適切に識別して区別するのに役立ちます。これにより、最新の変更を評価、構成、および最新の状態に簡単に更新できます。</span><span class="sxs-lookup"><span data-stu-id="62830-189">This service helps you better identify and differentiate Microsoft 365 network traffic, making it easier for you to evaluate, configure, and stay current with the latest changes.</span></span>

<span data-ttu-id="62830-190">PowerShell、Python、または他の言語を使用して、時間のたつ間にエンドポイントに対する変更を判断し、PAC ファイルとエッジ ネットワーク デバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="62830-190">You can use PowerShell, Python, or other languages to determine the changes to endpoints over time and configure your PAC files and edge network devices.</span></span>

<span data-ttu-id="62830-191">基本的なプロセスは次の処理です。</span><span class="sxs-lookup"><span data-stu-id="62830-191">The basic process is:</span></span>

1. <span data-ttu-id="62830-192">Office 365 IP アドレスと URL Web サービス、および選択した構成メカニズムを使用して、PAC ファイルとネットワーク デバイスを Microsoft 365 エンドポイントの現在のセットで構成します。</span><span class="sxs-lookup"><span data-stu-id="62830-192">Use the Office 365 IP Address and URL web service and the configuration mechanism of your choice to configure your PAC files and network devices with the current set of Microsoft 365 endpoints.</span></span>
2. <span data-ttu-id="62830-193">毎日定期的に実行してエンドポイントの変更を確認するか、通知方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="62830-193">Run a daily recurring to check for changes in the endpoints or use a notification method.</span></span>
3. <span data-ttu-id="62830-194">変更が検出された場合は、クライアント コンピューターの PAC ファイルを再生成して再配布し、ネットワーク デバイスに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="62830-194">When changes are detected, regenerate and redistribute the PAC file for client computers and make the changes to your network devices.</span></span>

<span data-ttu-id="62830-195">詳細については、「Office [365 IP アドレスと URL Web サービス」を参照してください](../enterprise/microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="62830-195">For more information, see [Office 365 IP Address and URL web service](../enterprise/microsoft-365-ip-web-service.md).</span></span>

## <a name="results-of-step-2"></a><span data-ttu-id="62830-196">手順 2 の結果</span><span class="sxs-lookup"><span data-stu-id="62830-196">Results of Step 2</span></span>

<span data-ttu-id="62830-197">最適なネットワークを使用する Microsoft 365 テナントについては、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="62830-197">For your Microsoft 365 tenant with optimal networking, you have determined:</span></span>

- <span data-ttu-id="62830-198">すべてのブランチ オフィスにインターネット接続を追加し、ネットワーク ヘアピンを排除して、オンプレミス ユーザーのネットワーク パフォーマンスを最適化する方法。</span><span class="sxs-lookup"><span data-stu-id="62830-198">How to optimize network performance for on-premises users by adding Internet connections to all branch offices and eliminating network hairpins.</span></span>
- <span data-ttu-id="62830-199">継続的な更新プログラム (エンタープライズ ネットワークに最適) を含む、クライアント ベースの PAC ファイルとネットワーク デバイスとサービスに対して、信頼されたエンドポイントの自動登録情報を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62830-199">How to implement automated trusted endpoint listing for your client-based PAC files and your network devices and services, including ongoing updates (most suitable for enterprise networks).</span></span>
- <span data-ttu-id="62830-200">オンプレミス リソースへのリモート ワーカーのアクセスをサポートする方法。</span><span class="sxs-lookup"><span data-stu-id="62830-200">How to support the access of remote workers to on-premises resources.</span></span>
- <span data-ttu-id="62830-201">Network Insights の使い方</span><span class="sxs-lookup"><span data-stu-id="62830-201">How to use Network Insights</span></span>
- <span data-ttu-id="62830-202">Office 365 CDN を展開する方法。</span><span class="sxs-lookup"><span data-stu-id="62830-202">How to deploy the Office 365 CDN.</span></span>

<span data-ttu-id="62830-203">最適なネットワークを備え、エンタープライズ組織とそのテナントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62830-203">Here is an example of an enterprise organization and its tenant with optimal networking.</span></span>

![最適なネットワークを持つテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[<span data-ttu-id="62830-205">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="62830-205">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

<span data-ttu-id="62830-206">この図では、このエンタープライズ組織のテナントには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="62830-206">In this illustration, the tenant for this enterprise organization has:</span></span>

- <span data-ttu-id="62830-207">信頼できる Microsoft 365 トラフィックをローカルのフロント ドアに転送する SDWAN デバイスを使用した各ブランチ オフィスのローカル インターネット アクセス。</span><span class="sxs-lookup"><span data-stu-id="62830-207">Local internet access for each branch office with an SDWAN device that forwards trusted Microsoft 365 traffic to a local front door.</span></span>
- <span data-ttu-id="62830-208">ネットワーク ヘアピンなし。</span><span class="sxs-lookup"><span data-stu-id="62830-208">No network hairpins.</span></span>
- <span data-ttu-id="62830-209">Microsoft 365 の信頼されたトラフィックをローカルのフロント ドアに転送する、中央オフィスのセキュリティ およびプロキシ エッジ デバイス。</span><span class="sxs-lookup"><span data-stu-id="62830-209">Central office security and proxy edge devices that forward Microsoft 365 trusted traffic to a local front door.</span></span>

## <a name="ongoing-maintenance-for-optimal-networking"></a><span data-ttu-id="62830-210">最適なネットワークのための継続的なメンテナンス</span><span class="sxs-lookup"><span data-stu-id="62830-210">Ongoing maintenance for optimal networking</span></span>

<span data-ttu-id="62830-211">継続的に、次の必要が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="62830-211">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="62830-212">エンドポイントの変更について、エッジ デバイスと展開された PAC ファイルを更新するか、自動化されたプロセスが正しく動作するか確認します。</span><span class="sxs-lookup"><span data-stu-id="62830-212">Update your edge devices and deployed PAC files for changes in endpoints or verify that your automated process works properly.</span></span>
- <span data-ttu-id="62830-213">Office 365 CDN でアセットを管理します。</span><span class="sxs-lookup"><span data-stu-id="62830-213">Manage your assets in the Office 365 CDN.</span></span>
- <span data-ttu-id="62830-214">エンドポイントの変更について、VPN クライアントの分割トンネリング構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="62830-214">Update the split tunneling configuration in your VPN clients for changes in endpoints.</span></span>

## <a name="next-step"></a><span data-ttu-id="62830-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="62830-215">Next step</span></span>

<span data-ttu-id="62830-216">[![手順 3.ID を同期し、セキュリティで保護されたサインインを適用する](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span><span class="sxs-lookup"><span data-stu-id="62830-216">[![Step 3. Synchronize your identities and enforce secure sign-ins](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span></span>

<span data-ttu-id="62830-217">ID を [続行して](tenant-management-identity.md) 、オンプレミスのアカウントとグループを同期し、セキュリティで保護されたユーザー サインインを適用します。</span><span class="sxs-lookup"><span data-stu-id="62830-217">Continue with [identity](tenant-management-identity.md) to synchronize your on-premises accounts and groups and enforce secure user sign-ins.</span></span>
