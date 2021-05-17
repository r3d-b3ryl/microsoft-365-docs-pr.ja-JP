---
title: 手順 2.  エンタープライズ テナント向けMicrosoft 365最適なネットワーク
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: テナントへのネットワーク アクセスを最適化Microsoft 365します。
ms.openlocfilehash: 5eac0793d2afc924a919671ffa105362ea1866d9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407194"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="08e1c-104">手順 2.</span><span class="sxs-lookup"><span data-stu-id="08e1c-104">Step 2.</span></span> <span data-ttu-id="08e1c-105">エンタープライズ テナント向けMicrosoft 365最適なネットワーク</span><span class="sxs-lookup"><span data-stu-id="08e1c-105">Optimal networking for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="08e1c-106">Microsoft 365には、Teams や Exchange Online、Microsoft Intune などのクラウド生産性アプリと、Microsoft Azure の多くの ID およびセキュリティ サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-106">Microsoft 365 for enterprise includes cloud productivity apps such as Teams and Exchange Online, and Microsoft Intune, along with many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="08e1c-107">これらのクラウドベースのサービスはすべて、オンプレミス ネットワークまたはインターネット上の任意の場所にあるクライアント デバイスからの接続のセキュリティ、パフォーマンス、および信頼性に依存します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-107">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices on your on-premises network or any location on the Internet.</span></span> 

<span data-ttu-id="08e1c-108">テナントのネットワーク アクセスを最適化するには、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-108">To optimize network access for your tenant, you need to:</span></span>

- <span data-ttu-id="08e1c-109">オンプレミスユーザーと Microsoft グローバル ネットワークに最も近い場所との間のパスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-109">Optimize the path between your on-premises users and the closest location to the Microsoft Global Network.</span></span>
- <span data-ttu-id="08e1c-110">リモート アクセス VPN ソリューションを使用しているリモート ユーザーの Microsoft Global Network へのアクセスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-110">Optimize access to the Microsoft Global Network for your remote users that are using a remote access VPN solution.</span></span>
- <span data-ttu-id="08e1c-111">ネットワーク インサイトを使用して、オフィスの場所のネットワーク境界を設計します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-111">Use Network Insights to design the network perimeter for your office locations.</span></span>
- <span data-ttu-id="08e1c-112">サイトでホストされている特定のアセットへのアクセスSharePoint、Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="08e1c-112">Optimize access to specific assets hosted on SharePoint sites with the Office 365 CDN.</span></span>
- <span data-ttu-id="08e1c-113">エンドポイントの一覧を使用して信頼Microsoft 365の処理をバイパスし、変更が加わるとリストの更新を自動化するプロキシおよびネットワーク エッジ デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-113">Configure proxy and network edge devices to bypass processing for Microsoft 365 trusted traffic with the list of endpoints and automate the updating of the list as changes are made.</span></span>

## <a name="enterprise-on-premises-workers"></a><span data-ttu-id="08e1c-114">Enterprise作業員</span><span class="sxs-lookup"><span data-stu-id="08e1c-114">Enterprise on-premises workers</span></span>

<span data-ttu-id="08e1c-115">エンタープライズ ネットワークの場合は、クライアントと最も近いエンドポイント間で最もパフォーマンスの高いネットワーク アクセスを有効にすることで、エンド ユーザー エクスペリエンスMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-115">For enterprise networks, you should optimize the end user experience by enabling the highest-performing network access between clients and the closest Microsoft 365 endpoints.</span></span> <span data-ttu-id="08e1c-116">エンド ユーザー エクスペリエンスの品質は、ユーザーが使用しているアプリケーションのパフォーマンスと応答性に直接関係します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-116">The quality of end user experience is directly related to the performance and responsiveness of the application that the user is using.</span></span> <span data-ttu-id="08e1c-117">たとえば、Microsoft Teams通話、会議、共有画面のコラボレーションがグリッチフリーになじむ低遅延に依存している場合です。</span><span class="sxs-lookup"><span data-stu-id="08e1c-117">For example, Microsoft Teams relies on low latency so that user phone calls, conferences and shared screen collaborations are glitch-free.</span></span>

<span data-ttu-id="08e1c-118">ネットワーク設計の主な目標は、クライアント デバイスから Microsoft Global Network への往復時間 (RTT) を短縮し、Microsoft のすべてのデータセンターを低遅延で相互接続する Microsoft のパブリック ネットワーク バックボーンである、フロント ドアと呼ばれる高可用性クラウド アプリケーション エントリ ポイントを世界中に広げ、待機時間を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-118">The primary goal in the network design should be to minimize latency by reducing the round-trip time (RTT) from client devices to the Microsoft Global Network, Microsoft's public network backbone that interconnects all of Microsoft's datacenters with low latency, high availability cloud application entry points, known as front doors, spread around the world.</span></span>

<span data-ttu-id="08e1c-119">従来のエンタープライズ ネットワークの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-119">Here is an example of a traditional enterprise network.</span></span>

![インターネットへの集中アクセスを備え、従来のエンタープライズ ネットワーク](../media/tenant-management-overview/tenant-management-networking-traditional.png)

<span data-ttu-id="08e1c-121">この図では、ブランチ オフィスは、ワイド エリア ネットワーク (WAN) デバイスと WAN バックボーンを介して中央オフィスに接続します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-121">In this illustration, branch offices connect to a central office through wide area network (WAN) devices and a WAN backbone.</span></span> <span data-ttu-id="08e1c-122">インターネット アクセスは、中央オフィスのネットワーク エッジとインターネット サービス プロバイダー (ISP) のセキュリティまたはプロキシ デバイスを介して行います。</span><span class="sxs-lookup"><span data-stu-id="08e1c-122">Internet access is through a security or proxy device at the network edge of the central office and an Internet service provider (ISP).</span></span> <span data-ttu-id="08e1c-123">インターネット上では、Microsoft Global Network は世界中の地域で一連のフロント ドアを持っています。</span><span class="sxs-lookup"><span data-stu-id="08e1c-123">On the Internet, the Microsoft Global Network has a series of front doors in regions around the world.</span></span> <span data-ttu-id="08e1c-124">組織は、トラフィックの追加のパケット処理とセキュリティのために中間の場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-124">Organizations can also use intermediate locations for additional packet processing and security for traffic.</span></span> <span data-ttu-id="08e1c-125">組織の組織のMicrosoft 365は、Microsoft グローバル ネットワーク内に位置します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-125">An organization's Microsoft 365 tenant is located within the Microsoft Global Network.</span></span>

<span data-ttu-id="08e1c-126">クラウド サービスのこの構成のMicrosoft 365は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="08e1c-126">The problems with this configuration for Microsoft 365 cloud services are:</span></span>

- <span data-ttu-id="08e1c-127">ブランチ オフィスのユーザーの場合、トラフィックはローカル以外のフロント ドアに送信され、待機時間が増加します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-127">For users in branch offices, traffic gets sent to non-local front doors, increasing latency.</span></span>
- <span data-ttu-id="08e1c-128">中間の場所にトラフィックを送信すると、信頼できるトラフィックで重複するパケット処理を実行するネットワーク ヘアピンが作成され、待機時間が長くなる。</span><span class="sxs-lookup"><span data-stu-id="08e1c-128">Sending traffic to intermediate locations create network hairpins that perform duplicate packet processing on trusted traffic, increasing latency.</span></span>
- <span data-ttu-id="08e1c-129">ネットワーク エッジ デバイスは、信頼できるトラフィックで不要で重複したパケット処理を実行し、待機時間を長くします。</span><span class="sxs-lookup"><span data-stu-id="08e1c-129">Network edge devices perform unneeded and duplicate packet processing on trusted traffic, increasing latency.</span></span>

<span data-ttu-id="08e1c-130">ネットワークのMicrosoft 365最適化は複雑である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="08e1c-130">Optimizing Microsoft 365 network performance doesn't need to be complicated.</span></span> <span data-ttu-id="08e1c-131">次の主要な原則に従って、可能な限り最高のパフォーマンスを得る方法があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-131">You can get the best possible performance by following a few key principles:</span></span>

- <span data-ttu-id="08e1c-132">Microsoft クラウド Microsoft 365宛ての信頼できるトラフィックであるネットワーク トラフィックを特定します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-132">Identify Microsoft 365 network traffic, which is trusted traffic destined to Microsoft cloud services.</span></span>
- <span data-ttu-id="08e1c-133">ユーザーがネットワークに接続するMicrosoft 365場所からインターネットへのネットワーク トラフィックのローカル ブランチ出力を許可Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="08e1c-133">Allow local branch egress of Microsoft 365 network traffic to the internet from each location where users connect to Microsoft 365.</span></span>
- <span data-ttu-id="08e1c-134">ネットワーク ヘアピンを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="08e1c-134">Avoid network hairpins.</span></span>
- <span data-ttu-id="08e1c-135">プロキシMicrosoft 365パケット検査デバイスをバイパスするトラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-135">Allow Microsoft 365 traffic to bypass proxies and packet inspection devices.</span></span>

<span data-ttu-id="08e1c-136">これらの原則を実装する場合は、エンタープライズ ネットワークの最適化を行い、Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="08e1c-136">If you implement these principles, you get an enterprise network optimized for Microsoft 365.</span></span>

![ユーザー向けに最適化されたエンタープライズ ネットワークMicrosoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

<span data-ttu-id="08e1c-138">この図では、ブランチ オフィスはソフトウェア定義の WAN デバイス (SDWAN) デバイスを介して独自のインターネット接続を持ち、信頼できる Microsoft 365 トラフィックを地域で最も近いフロント ドアに送信します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-138">In this illustration, branch offices have their own Internet connection through a software-defined WAN device (SDWAN) device, which sends trusted Microsoft 365 traffic to the regionally closest front door.</span></span> <span data-ttu-id="08e1c-139">中央オフィスでは、信頼できるMicrosoft 365はセキュリティまたはプロキシ デバイスをバイパスし、中間デバイスは使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="08e1c-139">At the central office, trusted Microsoft 365 traffic bypasses the security or proxy device and intermediate devices are no longer used.</span></span>

<span data-ttu-id="08e1c-140">最適化された構成が従来のエンタープライズ ネットワークの待機時間の問題を解決する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-140">Here's are how the optimized configuration solves the latency issues of a traditional enterprise network:</span></span>

- <span data-ttu-id="08e1c-141">信頼Microsoft 365トラフィックは WAN バックボーンをスキップし、すべてのオフィスのローカル フロント ドアに送信され、待機時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-141">Trusted Microsoft 365 traffic skips the WAN backbone and is sent to local front doors for all offices, decreasing latency.</span></span>
- <span data-ttu-id="08e1c-142">重複するパケット処理を実行するネットワーク ヘアピンは、信頼できるトラフィックMicrosoft 365に対してスキップされ、待機時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-142">Network hairpins that perform duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>
- <span data-ttu-id="08e1c-143">不要で重複するパケット処理を実行するネットワーク エッジ デバイスは、信頼できるトラフィックMicrosoft 365にスキップされ、待機時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-143">Network edge devices that perform unneeded and duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>

<span data-ttu-id="08e1c-144">詳細については、「ネットワーク接続の[概要Microsoft 365を参照してください](../enterprise/microsoft-365-networking-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="08e1c-144">For more information, see [Microsoft 365 network connectivity overview](../enterprise/microsoft-365-networking-overview.md).</span></span>

## <a name="remote-workers"></a><span data-ttu-id="08e1c-145">リモート ワーカー</span><span class="sxs-lookup"><span data-stu-id="08e1c-145">Remote workers</span></span>

<span data-ttu-id="08e1c-146">リモート ワーカーが従来の VPN クライアントを使用して組織ネットワークへのリモート アクセスを取得している場合は、VPN クライアントがスプリット トンネリング サポートを備えていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="08e1c-146">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span> <span data-ttu-id="08e1c-147">スプリット トンネリングを使用しない場合、すべてのリモート作業トラフィックは VPN 接続を介して送信され、そこで組織のエッジ デバイスに転送されて処理され、インターネット上で送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-147">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span> <span data-ttu-id="08e1c-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-148">Here is an example.</span></span>

![トンネリングのない VPN クライアントからのネットワーク トラフィック](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="08e1c-150">この図では、Microsoft 365トラフィックは組織を通じて間接的なルートを取る必要があります。これは、VPN クライアントの物理的な場所から遠く離れた Microsoft Global Network フロント ドアに転送される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-150">In this illustration, Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft Global Network front door far away from the VPN client’s physical location.</span></span> <span data-ttu-id="08e1c-151">この間接パスにより、ネットワーク トラフィックが遅延し、全体的なパフォーマンスを低下させます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-151">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="08e1c-152">スプリッ トトンネリングを使用すると、VPN クライアントを構成して、特定の種類のトラフィックが VPN 接続を介して、組織ネットワークに送信されることを除外できます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-152">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="08e1c-153">Microsoft 365 クラウドリソースへのアクセスを最適化するには、VPN 接続を介して、**最適化** カテゴリの Microsoft 365 エンドポイントへのトラフィックを除外するようにスプリット トンネリング VPN クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-153">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="08e1c-154">詳細については、「ネットワーク エンドポイント カテゴリ[Office 365、](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)スプリット[](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)トンネリング用のオプティマイズ カテゴリ エンドポイントの一覧」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e1c-154">For more information, see [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) and [the lists](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) of Optimize category endpoints for split tunneling.</span></span>

<span data-ttu-id="08e1c-155">クラウド アプリへのトラフィックの大部分が VPN 接続をバイパスするスプリット トンネリングMicrosoft 365トラフィック フローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-155">Here is the resulting traffic flow for split tunneling, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![トンネリングのある VPN クライアントからのネットワーク トラフィック](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="08e1c-157">この図では、VPN クライアントは、インターネットを通Microsoft 365、Microsoft グローバル ネットワークに最も近いフロント ドアに対して、重要なクラウド サービス トラフィックを送信および受信します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-157">In this illustration, the VPN client sends and receives crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest front door into the Microsoft Global Network.</span></span>

<span data-ttu-id="08e1c-158">詳細とガイダンスについては、「[VPN スプリット トンネリングを使用してリモート ユーザーの Office 365 の接続を最適化する](../enterprise/microsoft-365-vpn-split-tunnel.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="08e1c-158">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

## <a name="using-network-insights-preview"></a><span data-ttu-id="08e1c-159">ネットワーク インサイトの使用 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="08e1c-159">Using Network Insights (preview)</span></span>

<span data-ttu-id="08e1c-160">ネットワークインサイトは、オフィスの場所のネットワーク境界を設計するのに役立つ、Microsoft 365テナントから収集されるパフォーマンス指標です。</span><span class="sxs-lookup"><span data-stu-id="08e1c-160">Network insights are performance metrics collected from your Microsoft 365 tenant that help you design network perimeters for your office locations.</span></span> <span data-ttu-id="08e1c-161">各分析情報は、オンプレミスユーザーがテナントにアクセスしている地理的な場所ごとに、指定された問題のパフォーマンス特性に関するライブの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-161">Each insight provides live details about the performance characteristics for a specified issue for each geographic location where on-premises users are accessing your tenant.</span></span>

<span data-ttu-id="08e1c-162">テナントには、次の 2 つのテナント レベルのネットワーク分析情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-162">There are two tenant level network insights that may be shown for the tenant:</span></span>

- [<span data-ttu-id="08e1c-163">Exchangeの問題の影響を受け、サンプリングされた接続を確認する</span><span class="sxs-lookup"><span data-stu-id="08e1c-163">Exchange sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="08e1c-164">SharePointの問題の影響を受け、サンプルされた接続を確認する</span><span class="sxs-lookup"><span data-stu-id="08e1c-164">SharePoint sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

<span data-ttu-id="08e1c-165">次に、各オフィスの場所に関する特定のネットワーク インサイトを示します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-165">These are the specific network insights for each office location:</span></span>

- [<span data-ttu-id="08e1c-166">バックホールされたネットワーク出力</span><span class="sxs-lookup"><span data-stu-id="08e1c-166">Backhauled network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [<span data-ttu-id="08e1c-167">近くの顧客に対して検出されるパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="08e1c-167">Better performance detected for customers near you</span></span>](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="08e1c-168">サービス フロント ドアの最適Exchange Online使用</span><span class="sxs-lookup"><span data-stu-id="08e1c-168">Use of a non-optimal Exchange Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="08e1c-169">オンライン サービス フロント ドアSharePoint最適でないサービスの使用</span><span class="sxs-lookup"><span data-stu-id="08e1c-169">Use of a non-optimal SharePoint Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="08e1c-170">フロント ドアからのダウンロードSharePoint速度が低い</span><span class="sxs-lookup"><span data-stu-id="08e1c-170">Low download speed from SharePoint front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="08e1c-171">中国ユーザーの最適なネットワーク出力</span><span class="sxs-lookup"><span data-stu-id="08e1c-171">China user optimal network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
><span data-ttu-id="08e1c-172">管理センターのネットワークインサイト、パフォーマンスの推奨事項、評価Microsoft 365現在プレビュー状態です。</span><span class="sxs-lookup"><span data-stu-id="08e1c-172">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status.</span></span> <span data-ttu-id="08e1c-173">この機能は、Microsoft 365プログラムに登録されているテナントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-173">It is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

<span data-ttu-id="08e1c-174">詳細については、「ネットワーク インサイト[のMicrosoft 365を参照してください](../enterprise/office-365-network-mac-perf-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="08e1c-174">For more information, see [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).</span></span>

## <a name="sharepoint-performance-with-the-office-365-cdn"></a><span data-ttu-id="08e1c-175">SharePointを使用してパフォーマンスをOffice 365 CDN</span><span class="sxs-lookup"><span data-stu-id="08e1c-175">SharePoint performance with the Office 365 CDN</span></span>

<span data-ttu-id="08e1c-176">クラウドベースのContent Delivery Network (CDN) を使用すると、読み込み時間を短縮し、帯域幅を節約し、応答性を向上できます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-176">A cloud-based Content Delivery Network (CDN) allows you to reduce load times, save bandwidth, and speed responsiveness.</span></span> <span data-ttu-id="08e1c-177">このCDNを要求するブラウザーに近いグラフィック ファイルやビデオ ファイルなどの静的アセットをキャッシュすることでパフォーマンスが向上し、ダウンロードの高速化と待機時間の短縮に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-177">A CDN improves performance by caching static assets such as graphic or video files closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="08e1c-178">Microsoft 365 E3 および E5 の SharePoint に含まれる組み込みの Office 365 Content Delivery Network (CDN) を使用して、静的アセットをホストして、SharePoint ページのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-178">You can use the built-in Office 365 Content Delivery Network (CDN), included with SharePoint in Microsoft 365 E3 and E5, to host static assets to provide better performance for your SharePoint pages.</span></span>

<span data-ttu-id="08e1c-179">Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-179">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="08e1c-180">ホストするコンテンツの種類に応じて、Office 365 CDN、プライベートオリジン、または両方を追加できます。  </span><span class="sxs-lookup"><span data-stu-id="08e1c-180">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins, or both.</span></span>

<span data-ttu-id="08e1c-181">展開および構成すると、Office 365 CDNはパブリックおよびプライベートのオリジンからアセットをアップロードし、インターネット上にあるユーザーに高速にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-181">When deployed and configured, the Office 365 CDN uploads assets from public and private origins and makes them available for fast access to users located across the Internet.</span></span>

<span data-ttu-id="08e1c-182">![Office 365 CDN用に展開されている場合](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN用に展開されている場合")</span><span class="sxs-lookup"><span data-stu-id="08e1c-182">![Office 365 CDN deployed for users](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN deployed for users")</span></span>

<span data-ttu-id="08e1c-183">詳細については、「オンラインと一[緒にOffice 365 CDNをSharePointする」を参照してください](../enterprise/use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="08e1c-183">For more information, see [Use the Office 365 CDN with SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md).</span></span>

## <a name="automated-endpoint-listing"></a><span data-ttu-id="08e1c-184">エンドポイントの自動一覧</span><span class="sxs-lookup"><span data-stu-id="08e1c-184">Automated endpoint listing</span></span>

<span data-ttu-id="08e1c-185">オンプレミスのクライアント、エッジ デバイス、およびクラウドベースのパケット分析サービスに信頼済み Microsoft 365 トラフィックの処理をスキップするには、Microsoft 365 サービスに対応する一連のエンドポイント (IP アドレス範囲と DNS 名) を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-185">To have your on-premises clients, edge devices, and cloud-based packet analysis services skip processing of trusted Microsoft 365 traffic, you must configure them with the set of endpoints (IP address ranges and DNS names) corresponding to Microsoft 365 services.</span></span> <span data-ttu-id="08e1c-186">これらのエンドポイントは、ファイアウォールや他のエッジ セキュリティ デバイス、クライアント コンピューターがプロキシをバイパスする PAC ファイル、ブランチ オフィスの SD-WAN デバイスで手動で構成できます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-186">These endpoints can be manually configured in firewalls and other edge security devices, PAC files for client computers to bypass proxies, or SD-WAN devices at branch offices.</span></span> <span data-ttu-id="08e1c-187">ただし、エンドポイントは時間の間に変化し、これらの場所でエンドポイント リストを継続的に手動でメンテナンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-187">However, the endpoints change over time, requiring ongoing manual maintenance of the endpoint lists in these locations.</span></span>

<span data-ttu-id="08e1c-188">クライアント PAC ファイルおよびネットワーク デバイス内の Microsoft 365 エンドポイントの一覧と変更管理を自動化するには、Office 365 IP アドレスと[URL REST ベースの Web](../enterprise/microsoft-365-ip-web-service.md)サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-188">To automate the listing and change management for Microsoft 365 endpoints in your client PAC files and network devices, use the [Office 365 IP Address and URL REST-based web service](../enterprise/microsoft-365-ip-web-service.md).</span></span> <span data-ttu-id="08e1c-189">このサービスを使用すると、ネットワーク トラフィックのMicrosoft 365識別と区別が容易になり、最新の変更を評価、構成、および最新の状態に変えやすくなります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-189">This service helps you better identify and differentiate Microsoft 365 network traffic, making it easier for you to evaluate, configure, and stay current with the latest changes.</span></span>

<span data-ttu-id="08e1c-190">PowerShell、Python、または他の言語を使用して、時間の間にエンドポイントに対する変更を決定し、PAC ファイルとエッジ ネットワーク デバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-190">You can use PowerShell, Python, or other languages to determine the changes to endpoints over time and configure your PAC files and edge network devices.</span></span>

<span data-ttu-id="08e1c-191">基本的なプロセスは次の手順です。</span><span class="sxs-lookup"><span data-stu-id="08e1c-191">The basic process is:</span></span>

1. <span data-ttu-id="08e1c-192">IP アドレスOffice 365 URL Web サービスと構成メカニズムを使用して、PAC ファイルとネットワーク デバイスを現在の一連のエンドポイントで構成Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-192">Use the Office 365 IP Address and URL web service and the configuration mechanism of your choice to configure your PAC files and network devices with the current set of Microsoft 365 endpoints.</span></span>
2. <span data-ttu-id="08e1c-193">毎日定期的に実行して、エンドポイントの変更を確認するか、通知方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-193">Run a daily recurring to check for changes in the endpoints or use a notification method.</span></span>
3. <span data-ttu-id="08e1c-194">変更が検出された場合は、クライアント コンピューターの PAC ファイルを再生成して再配布し、ネットワーク デバイスに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="08e1c-194">When changes are detected, regenerate and redistribute the PAC file for client computers and make the changes to your network devices.</span></span>

<span data-ttu-id="08e1c-195">詳細については、「IP[アドレスOffice 365 URL Web サービス」を参照してください](../enterprise/microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="08e1c-195">For more information, see [Office 365 IP Address and URL web service](../enterprise/microsoft-365-ip-web-service.md).</span></span>

## <a name="results-of-step-2"></a><span data-ttu-id="08e1c-196">手順 2 の結果</span><span class="sxs-lookup"><span data-stu-id="08e1c-196">Results of Step 2</span></span>

<span data-ttu-id="08e1c-197">最適なネットワークMicrosoft 365テナントの場合、次の条件を決定しました。</span><span class="sxs-lookup"><span data-stu-id="08e1c-197">For your Microsoft 365 tenant with optimal networking, you have determined:</span></span>

- <span data-ttu-id="08e1c-198">すべてのブランチ オフィスにインターネット接続を追加し、ネットワーク ヘアピンを排除して、オンプレミス ユーザーのネットワーク パフォーマンスを最適化する方法。</span><span class="sxs-lookup"><span data-stu-id="08e1c-198">How to optimize network performance for on-premises users by adding Internet connections to all branch offices and eliminating network hairpins.</span></span>
- <span data-ttu-id="08e1c-199">継続的な更新プログラム (エンタープライズ ネットワークに最適) を含む、クライアント ベースの PAC ファイルとネットワーク デバイスとサービスに対して、信頼できるエンドポイントの自動登録を実装する方法。</span><span class="sxs-lookup"><span data-stu-id="08e1c-199">How to implement automated trusted endpoint listing for your client-based PAC files and your network devices and services, including ongoing updates (most suitable for enterprise networks).</span></span>
- <span data-ttu-id="08e1c-200">リモート ワーカーからオンプレミス リソースへのアクセスをサポートする方法。</span><span class="sxs-lookup"><span data-stu-id="08e1c-200">How to support the access of remote workers to on-premises resources.</span></span>
- <span data-ttu-id="08e1c-201">ネットワーク インサイトの使い方</span><span class="sxs-lookup"><span data-stu-id="08e1c-201">How to use Network Insights</span></span>
- <span data-ttu-id="08e1c-202">アプリケーションを展開するOffice 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="08e1c-202">How to deploy the Office 365 CDN.</span></span>

<span data-ttu-id="08e1c-203">最適なネットワークを持つエンタープライズ組織とそのテナントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-203">Here is an example of an enterprise organization and its tenant with optimal networking.</span></span>

![最適なネットワークを持つテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[<span data-ttu-id="08e1c-205">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="08e1c-205">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

<span data-ttu-id="08e1c-206">この図では、このエンタープライズ組織のテナントには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-206">In this illustration, the tenant for this enterprise organization has:</span></span>

- <span data-ttu-id="08e1c-207">信頼できるネットワーク トラフィックをローカル フロント ドアに転送する SDWAN デバイスをMicrosoft 365ブランチ オフィスのローカル インターネット アクセス。</span><span class="sxs-lookup"><span data-stu-id="08e1c-207">Local internet access for each branch office with an SDWAN device that forwards trusted Microsoft 365 traffic to a local front door.</span></span>
- <span data-ttu-id="08e1c-208">ネットワーク ヘアピンはありません。</span><span class="sxs-lookup"><span data-stu-id="08e1c-208">No network hairpins.</span></span>
- <span data-ttu-id="08e1c-209">信頼できるトラフィックをローカルのフロント ドアに転送するMicrosoft 365プロキシ エッジ デバイス。</span><span class="sxs-lookup"><span data-stu-id="08e1c-209">Central office security and proxy edge devices that forward Microsoft 365 trusted traffic to a local front door.</span></span>

## <a name="ongoing-maintenance-for-optimal-networking"></a><span data-ttu-id="08e1c-210">最適なネットワークのための継続的なメンテナンス</span><span class="sxs-lookup"><span data-stu-id="08e1c-210">Ongoing maintenance for optimal networking</span></span>

<span data-ttu-id="08e1c-211">継続的に、次の必要が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="08e1c-211">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="08e1c-212">エンドポイントの変更のためにエッジ デバイスと展開された PAC ファイルを更新するか、自動化されたプロセスが正しく動作するか確認します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-212">Update your edge devices and deployed PAC files for changes in endpoints or verify that your automated process works properly.</span></span>
- <span data-ttu-id="08e1c-213">アセットを管理するには、Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="08e1c-213">Manage your assets in the Office 365 CDN.</span></span>
- <span data-ttu-id="08e1c-214">エンドポイントの変更については、VPN クライアントの分割トンネリング構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-214">Update the split tunneling configuration in your VPN clients for changes in endpoints.</span></span>

## <a name="next-step"></a><span data-ttu-id="08e1c-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="08e1c-215">Next step</span></span>

<span data-ttu-id="08e1c-216">[![手順 3.ID を同期し、セキュリティで保護されたサインインを適用する](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span><span class="sxs-lookup"><span data-stu-id="08e1c-216">[![Step 3. Synchronize your identities and enforce secure sign-ins](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span></span>

<span data-ttu-id="08e1c-217">ID を [続行して](tenant-management-identity.md) 、オンプレミスのアカウントとグループを同期し、セキュリティで保護されたユーザー サインインを適用します。</span><span class="sxs-lookup"><span data-stu-id="08e1c-217">Continue with [identity](tenant-management-identity.md) to synchronize your on-premises accounts and groups and enforce secure user sign-ins.</span></span>
