---
title: Contoso Corporation のネットワーク
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のネットワークインフラストラクチャと、企業が Microsoft 365 for enterprise cloud services に最適なネットワークパフォーマンスを得るために、その SD テクノロジをどのように使用するかについて説明します。
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754016"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="755c5-103">Contoso Corporation のネットワーク</span><span class="sxs-lookup"><span data-stu-id="755c5-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="755c5-p101">クラウドを含むインフラストラクチャを採用するために、Contoso 社はクラウドサービスへのネットワークトラフィックの移動方法について基本的な説明を考案しています。ネットワーク接続と、office 階層の次のレベルのトラフィックを中心とする内部ハブアンドスポークモデルの代わりに、ユーザーの場所を、インターネット上の最も近い Microsoft 365 ネットワークの場所へのローカルインターネット出口およびローカル接続にマップしていました。</span><span class="sxs-lookup"><span data-stu-id="755c5-p101">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels. Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="755c5-106">ネットワークインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="755c5-106">Networking infrastructure</span></span>

<span data-ttu-id="755c5-107">以下は、世界中で Contoso 支社をリンクするネットワーク要素です。</span><span class="sxs-lookup"><span data-stu-id="755c5-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="755c5-108">Multiprotocol Label Switching (MPLS) WAN ネットワーク</span><span class="sxs-lookup"><span data-stu-id="755c5-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="755c5-p102">MPLS WAN ネットワークは、パリ本社を地域のオフィスや地域のオフィスに、スポークとハブの構成のサテライトオフィスに接続します。ネットワークによって、ユーザーは、パリ本社で基幹業務アプリケーションを構成するオンプレミスサーバーにアクセスできます。また、すべての一般的なインターネットトラフィックをパリのオフィスにルーティングします。これにより、ネットワークセキュリティデバイスが要求をスクラブできます。各オフィスで、ルーターは、プライベート IP アドレス空間を使用して、有線ホストまたはサブネット上のワイヤレスアクセスポイントにトラフィックを配信します。</span><span class="sxs-lookup"><span data-stu-id="755c5-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration. The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters. It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="755c5-113">Microsoft 365 トラフィック用のローカル直接インターネットアクセス</span><span class="sxs-lookup"><span data-stu-id="755c5-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="755c5-p103">各オフィスには、プロキシサーバー経由の独自のインターネット接続を備えた1つ以上のローカルインターネット ISP ネットワーク回線を備えた、ソフトウェア定義の WAN (SD) デバイスがあります。これは、通常、パブリック IP アドレスとローカル DNS サーバーも提供するローカル ISP への WAN リンクとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="755c5-p103">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="755c5-116">インターネット プレゼンス</span><span class="sxs-lookup"><span data-stu-id="755c5-116">Internet presence</span></span>

  <span data-ttu-id="755c5-p104">Contoso は contoso \. com パブリックドメイン名を所有しています。製品を注文するための Contoso 社のパブリック web サイトは、パリキャンパスのインターネット接続されたデータセンター内のサーバーのセットです。Contoso 社では、インターネット上のパブリック IP アドレスの範囲として24個を使用しています。</span><span class="sxs-lookup"><span data-stu-id="755c5-p104">Contoso owns the contoso\.com public domain name. The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="755c5-120">図1は、Contoso 社のネットワークインフラストラクチャと、そのインターネットに対する接続を示しています。</span><span class="sxs-lookup"><span data-stu-id="755c5-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Contoso ネットワーク](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="755c5-122">**図 1: Contoso ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="755c5-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="755c5-123">Microsoft への最適なネットワーク接続のための SD-WAN の使用</span><span class="sxs-lookup"><span data-stu-id="755c5-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="755c5-124">Contoso 社は次の [Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)に従いました。</span><span class="sxs-lookup"><span data-stu-id="755c5-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="755c5-125">Microsoft 365 ネットワーク トラフィックを識別して区別する</span><span class="sxs-lookup"><span data-stu-id="755c5-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="755c5-126">ネットワーク接続のローカルの出口を提供する</span><span class="sxs-lookup"><span data-stu-id="755c5-126">Egress network connections locally</span></span>
- <span data-ttu-id="755c5-127">ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="755c5-127">Avoid network hairpins</span></span>
- <span data-ttu-id="755c5-128">重複するネットワーク セキュリティ デバイスをバイパスする</span><span class="sxs-lookup"><span data-stu-id="755c5-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="755c5-129">Microsoft 365 のネットワークトラフィックには、 *Optimize*、 *Allow*、および *Default*の3つのカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="755c5-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="755c5-130">トラフィックの最適化と許可は、エンドポイントで暗号化およびセキュリティ保護され、Microsoft 365 ネットワークに向けられている信頼されたネットワークトラフィックです。</span><span class="sxs-lookup"><span data-stu-id="755c5-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="755c5-131">Contoso は次のように決定しました。</span><span class="sxs-lookup"><span data-stu-id="755c5-131">Contoso decided to:</span></span>

- <span data-ttu-id="755c5-132">直接インターネット出口を使用してカテゴリトラフィックを最適化および許可し、すべての既定のカテゴリトラフィックをパリベースの中央インターネット接続に転送します。</span><span class="sxs-lookup"><span data-stu-id="755c5-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="755c5-133">これらの原則に従って、Microsoft 365 のクラウドベースのサービスで最適なネットワークパフォーマンスを実現するための簡単な方法として、各オフィスの SD を展開します。</span><span class="sxs-lookup"><span data-stu-id="755c5-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="755c5-134">SD-WAN デバイスには、ローカル オフィス ネットワーク用の LAN ポートと複数の WAN ポートがあります。</span><span class="sxs-lookup"><span data-stu-id="755c5-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="755c5-135">1つの WAN ポートが MPLS ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="755c5-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="755c5-136">別の方法として、ローカルの ISP サーキットに接続します。</span><span class="sxs-lookup"><span data-stu-id="755c5-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="755c5-137">SD-WAN デバイスは、ISP リンクを介してカテゴリ ネットワーク トラフィックを最適化および許可します。</span><span class="sxs-lookup"><span data-stu-id="755c5-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="755c5-138">Contoso の基幹業務アプリインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="755c5-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="755c5-139">Contoso 社は、次のような基幹業務アプリケーションとサーバーのイントラネットインフラストラクチャを構築しています。</span><span class="sxs-lookup"><span data-stu-id="755c5-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="755c5-140">サテライト オフィスは、ローカル キャッシュ サーバーを使用して、アクセス頻度の高いドキュメントおよび内部 Web サイトを格納します。</span><span class="sxs-lookup"><span data-stu-id="755c5-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="755c5-p107">地域ハブは、地域オフィスおよびサテライト オフィスに地域アプリケーション サーバーを使用します。これらのサーバーは、パリ本社のサーバーと同期します。</span><span class="sxs-lookup"><span data-stu-id="755c5-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="755c5-143">パリキャンパスデータセンターには、組織全体にサービスを提供する集中管理アプリケーションサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="755c5-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="755c5-144">図2は、Contoso イントラネット経由でサーバーにアクセスする際に使用されるネットワークトラフィック容量の割合を示しています。</span><span class="sxs-lookup"><span data-stu-id="755c5-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![内部アプリケーションの Contoso インフラストラクチャ](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="755c5-146">**図 2: 内部アプリケーションの Contoso インフラストラクチャ**</span><span class="sxs-lookup"><span data-stu-id="755c5-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="755c5-147">サテライトまたは地域ハブのオフィスの場合、従業員が必要とするリソースの60% は、サテライトおよび地域のハブオフィスサーバーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="755c5-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="755c5-148">リソース要求の40% は、パリキャンパスへの WAN リンクを介して追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="755c5-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="755c5-149">Microsoft 365 for enterprise のネットワーク分析と準備</span><span class="sxs-lookup"><span data-stu-id="755c5-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="755c5-150">Contoso ユーザーによるエンタープライズサービスへの Microsoft 365 の導入を成功させるには、インターネットまたは Microsoft クラウドサービスに直接接続できる高可用性とパフォーマンスを備えています。</span><span class="sxs-lookup"><span data-stu-id="755c5-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="755c5-151">Contoso 社は次の手順を実行して、エンタープライズクラウドサービス用に Microsoft 365 への接続を最適化して計画および実装しました。</span><span class="sxs-lookup"><span data-stu-id="755c5-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="755c5-152">計画に役立てるために会社の WAN ネットワーク図を作成する</span><span class="sxs-lookup"><span data-stu-id="755c5-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="755c5-153">ネットワーク計画を開始するために、Contoso 社は、オフィスの場所、既存のネットワーク接続、既存のネットワーク境界デバイス、およびネットワーク上で管理されているサービスのクラスを示す図を作成しました。</span><span class="sxs-lookup"><span data-stu-id="755c5-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="755c5-154">この図は、「ネットワーク接続の計画と実装」に記載されている以降の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="755c5-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="755c5-155">エンタープライズネットワーク接続用の Microsoft 365 の計画を作成する</span><span class="sxs-lookup"><span data-stu-id="755c5-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="755c5-156">Contoso 社は、microsoft [365 のネットワーク接続の原則](microsoft-365-network-connectivity-principles.md) とサンプルの参照ネットワークアーキテクチャを使用して、microsoft 365 接続の優先トポロジとして SD WAN を識別していました。</span><span class="sxs-lookup"><span data-stu-id="755c5-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="755c5-157">各オフィスでインターネット接続の使用率と MPLS-WAN の帯域幅を分析し、必要に応じて帯域幅を増やす</span><span class="sxs-lookup"><span data-stu-id="755c5-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="755c5-158">各 office の現在の使用状況が分析され、回路が増加したため、Microsoft 365 のクラウドベースのトラフィックは、平均で20% の未使用容量を使用して動作するようになりました。</span><span class="sxs-lookup"><span data-stu-id="755c5-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="755c5-159">Microsoft ネットワークサービスに対するパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="755c5-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="755c5-160">Contoso 社は、最適なパフォーマンスを得るために、Office 365、Intune、および Azure エンドポイントのセット、および構成されているファイアウォール、セキュリティデバイス、およびその他のシステムをインターネットパスに決定しました。</span><span class="sxs-lookup"><span data-stu-id="755c5-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="755c5-161">Office 365 のエンドポイント [最適化] および [許可] カテゴリトラフィックは、ISP 回線経由でルーティングするために SD デバイスに構成されました。</span><span class="sxs-lookup"><span data-stu-id="755c5-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="755c5-162">内部 DNS を構成する</span><span class="sxs-lookup"><span data-stu-id="755c5-162">Configure internal DNS</span></span>

   <span data-ttu-id="755c5-163">DNS が機能し、Microsoft 365 トラフィックのためにローカルで検索対象になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="755c5-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="755c5-164">ネットワークエンドポイントとポート接続を検証する</span><span class="sxs-lookup"><span data-stu-id="755c5-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="755c5-165">Contoso 社は Microsoft ネットワーク接続テストツールを実行して、エンタープライズクラウドサービスの Microsoft 365 への接続を検証しました。</span><span class="sxs-lookup"><span data-stu-id="755c5-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="755c5-166">ネットワーク接続のために従業員のコンピューターを最適化する</span><span class="sxs-lookup"><span data-stu-id="755c5-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="755c5-167">各コンピューターは、最新のオペレーティングシステムの更新プログラムがインストールされていて、エンドポイントのセキュリティ監視がすべてのクライアントでアクティブであったことを確認するためにチェックされました。</span><span class="sxs-lookup"><span data-stu-id="755c5-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="755c5-168">次のステップ</span><span class="sxs-lookup"><span data-stu-id="755c5-168">Next step</span></span>

<span data-ttu-id="755c5-169">Contoso 社が、従業員向けの [クラウドで社内 Active Directory ドメインサービスを利用](contoso-identity.md) する方法と、顧客やビジネスパートナーに対するフェデレーション認証について説明します。</span><span class="sxs-lookup"><span data-stu-id="755c5-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="755c5-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="755c5-170">See also</span></span>

[<span data-ttu-id="755c5-171">Microsoft 365 のネットワークロードマップ</span><span class="sxs-lookup"><span data-stu-id="755c5-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="755c5-172">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="755c5-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="755c5-173">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="755c5-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
