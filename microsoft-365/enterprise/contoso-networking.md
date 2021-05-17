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
description: Contoso のネットワーク インフラストラクチャと、企業が SD-WAN テクノロジを使用して、エンタープライズ クラウド サービスに最適なネットワーク パフォーマンスをMicrosoft 365について説明します。
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754016"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="7eb8a-103">Contoso Corporation のネットワーク</span><span class="sxs-lookup"><span data-stu-id="7eb8a-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="7eb8a-104">クラウドを含むインフラストラクチャを採用するために、Contoso 社はクラウド サービスへのネットワーク トラフィックの移動方法の根本的な変化を考案しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="7eb8a-105">次のレベルのオフィス階層のネットワーク接続とトラフィックに焦点を当てた内部ハブ アンド スポーク モデルの代わりに、ユーザーの場所をローカルインターネット出力にマップし、インターネット上で最も近い Microsoft 365 ネットワークの場所にローカル接続をマップしました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="7eb8a-106">ネットワーク インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="7eb8a-106">Networking infrastructure</span></span>

<span data-ttu-id="7eb8a-107">世界中の Contoso のオフィスをリンクするネットワーク要素を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="7eb8a-108">Multiprotocol Label Switching (MPLS) WAN ネットワーク</span><span class="sxs-lookup"><span data-stu-id="7eb8a-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="7eb8a-109">MPLS WAN ネットワークは、パリ本社を地域のオフィスや地域のオフィスとサテライト オフィスに接続し、スポークアンドハブ構成で接続します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="7eb8a-110">このネットワークを使用すると、ユーザーはパリ本社のビジネス アプリケーションを構成するオンプレミス サーバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="7eb8a-111">また、一般的なインターネット トラフィックをパリのオフィスにルーティングし、ネットワーク セキュリティ デバイスが要求をスクラブします。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="7eb8a-112">各オフィス内で、ルーターはプライベート IP アドレス空間を使用するサブネット上の有線ホストまたはワイヤレス アクセス ポイントにトラフィックを配信します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="7eb8a-113">トラフィックのローカル直接Microsoft 365アクセス</span><span class="sxs-lookup"><span data-stu-id="7eb8a-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="7eb8a-114">各オフィスには、1 つ以上のローカル インターネット ISP ネットワーク回線を備え、プロキシ サーバーを介した独自のインターネット接続を備えるソフトウェア定義の WAN (SD-WAN) デバイスがあります。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="7eb8a-115">これは通常、パブリック IP アドレスとローカル DNS サーバーも提供するローカル ISP への WAN リンクとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="7eb8a-116">インターネット プレゼンス</span><span class="sxs-lookup"><span data-stu-id="7eb8a-116">Internet presence</span></span>

  <span data-ttu-id="7eb8a-117">Contoso は contoso com パブリック \. ドメイン名を所有しています。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="7eb8a-118">製品を注文する Contoso パブリック Web サイトは、パリキャンパス内のインターネットに接続されたデータセンター内のサーバーのセットです。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="7eb8a-119">Contoso は、インターネット上で /24 パブリック IP アドレス範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="7eb8a-120">図 1 は、Contoso のネットワーク インフラストラクチャとインターネットへの接続を示しています。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Contoso ネットワーク](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="7eb8a-122">**図 1: Contoso ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="7eb8a-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="7eb8a-123">Microsoft への最適なネットワーク接続のための SD-WAN の使用</span><span class="sxs-lookup"><span data-stu-id="7eb8a-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="7eb8a-124">Contoso 社は次の [Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)に従いました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="7eb8a-125">Microsoft 365 ネットワーク トラフィックを識別して区別する</span><span class="sxs-lookup"><span data-stu-id="7eb8a-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="7eb8a-126">ネットワーク接続のローカルの出口を提供する</span><span class="sxs-lookup"><span data-stu-id="7eb8a-126">Egress network connections locally</span></span>
- <span data-ttu-id="7eb8a-127">ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="7eb8a-127">Avoid network hairpins</span></span>
- <span data-ttu-id="7eb8a-128">重複するネットワーク セキュリティ デバイスをバイパスする</span><span class="sxs-lookup"><span data-stu-id="7eb8a-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="7eb8a-129">ネットワーク トラフィックには、最適化、許可、および *Microsoft 365の* 3 *つの* カテゴリ *があります*。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="7eb8a-130">最適化と許可トラフィックは、エンドポイントで暗号化されセキュリティで保護され、ネットワーク上のネットワークにMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="7eb8a-131">Contoso は次のように決定しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-131">Contoso decided to:</span></span>

- <span data-ttu-id="7eb8a-132">オプティマイズと許可カテゴリ トラフィックに直接インターネット出力を使用し、すべての既定のカテゴリ トラフィックをパリベースの中央インターネット接続に転送します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="7eb8a-133">これらの原則に従い、クラウド ベースのサービスに最適なネットワーク パフォーマンスを実現する簡単な方法として、各Microsoft 365に SD-WAN デバイスを展開します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="7eb8a-134">SD-WAN デバイスには、ローカル オフィス ネットワーク用の LAN ポートと複数の WAN ポートがあります。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="7eb8a-135">1 つの WAN ポートが MPLS ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="7eb8a-136">別の ISP 回線はローカル ISP 回線に接続します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="7eb8a-137">SD-WAN デバイスは、ISP リンクを介してカテゴリ ネットワーク トラフィックを最適化および許可します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="7eb8a-138">Contoso line-of-business アプリ インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="7eb8a-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="7eb8a-139">Contoso 社は、次の業務用アプリケーションとサーバー イントラネット インフラストラクチャを設計しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="7eb8a-140">サテライト オフィスは、ローカル キャッシュ サーバーを使用して、アクセス頻度の高いドキュメントおよび内部 Web サイトを格納します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="7eb8a-p107">地域ハブは、地域オフィスおよびサテライト オフィスに地域アプリケーション サーバーを使用します。これらのサーバーは、パリ本社のサーバーと同期します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="7eb8a-143">パリのキャンパス データセンターには、組織全体にサービスを提供する集中アプリケーション サーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="7eb8a-144">図 2 は、Contoso イントラネット全体のサーバーにアクセスするときに使用されるネットワーク トラフィック容量の割合を示しています。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![内部アプリケーションの Contoso インフラストラクチャ](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="7eb8a-146">**図 2: 内部アプリケーションの Contoso インフラストラクチャ**</span><span class="sxs-lookup"><span data-stu-id="7eb8a-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="7eb8a-147">サテライトまたは地域のハブ オフィスでは、従業員が必要とするリソースの 60% をサテライトおよび地域のハブ オフィス サーバーで提供できます。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="7eb8a-148">リソース要求の追加 40% は、パリキャンパスへの WAN リンクを越える必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="7eb8a-149">エンタープライズ向けネットワーク分析Microsoft 365準備</span><span class="sxs-lookup"><span data-stu-id="7eb8a-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="7eb8a-150">Contoso ユーザーによるエンタープライズ Microsoft 365の導入の成功は、高可用性とパフォーマンスの高いインターネット接続、または Microsoft クラウド サービスへの直接接続に依存します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="7eb8a-151">Contoso は、エンタープライズ クラウド サービス向けに最適化された接続を計画および実装するためにMicrosoft 365手順を実行しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="7eb8a-152">計画を支援する会社の WAN ネットワーク図を作成する</span><span class="sxs-lookup"><span data-stu-id="7eb8a-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="7eb8a-153">Contoso 社は、ネットワーク計画を開始するために、自分のオフィスの場所、既存のネットワーク接続、既存のネットワーク境界デバイス、およびネットワーク上で管理されるサービス クラスを示す図を作成しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="7eb8a-154">この図は、ネットワーク接続の計画と実装の後続の各手順で使用しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="7eb8a-155">エンタープライズ ネットワーク接続用のMicrosoft 365計画を作成する</span><span class="sxs-lookup"><span data-stu-id="7eb8a-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="7eb8a-156">Contoso 社は[、Microsoft 365接続](microsoft-365-network-connectivity-principles.md)の原則とサンプル リファレンス ネットワーク アーキテクチャを使用して、SD-WAN をネットワーク接続の優先トポロジMicrosoft 365しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="7eb8a-157">各オフィスでのインターネット接続使用率と MPLS-WAN 帯域幅を分析し、必要に応じて帯域幅を増やします</span><span class="sxs-lookup"><span data-stu-id="7eb8a-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="7eb8a-158">各オフィスの現在の使用状況が分析され、回線が増加し、Microsoft 365 クラウドベースのトラフィックが平均 20% の未使用容量で動作すると予測されました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="7eb8a-159">Microsoft ネットワーク サービスへのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="7eb8a-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="7eb8a-160">Contoso 社は、最適なパフォーマンスOffice 365、インターネット パス内の一連のファイアウォール、Intune、Azure エンドポイント、および構成済みのファイアウォール、セキュリティ デバイス、その他のシステムを決定しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="7eb8a-161">[最適化Office 365許可] カテゴリ トラフィックのエンドポイントは、ISP 回線を通してルーティングするために SD-WAN デバイスに構成されています。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="7eb8a-162">内部 DNS の構成</span><span class="sxs-lookup"><span data-stu-id="7eb8a-162">Configure internal DNS</span></span>

   <span data-ttu-id="7eb8a-163">DNS が機能し、Microsoft 365 トラフィックのためにローカルで検索対象になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="7eb8a-164">ネットワーク エンドポイントとポート接続の検証</span><span class="sxs-lookup"><span data-stu-id="7eb8a-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="7eb8a-165">Contoso 社は、Microsoft ネットワーク接続テスト ツールを実行して、エンタープライズ クラウド Microsoft 365の接続を検証しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="7eb8a-166">ネットワーク接続用に従業員のコンピューターを最適化する</span><span class="sxs-lookup"><span data-stu-id="7eb8a-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="7eb8a-167">個々のコンピューターがチェックされ、最新のオペレーティング システム更新プログラムがインストールされ、すべてのクライアントでエンドポイント セキュリティ監視がアクティブにされていることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="7eb8a-168">次の手順</span><span class="sxs-lookup"><span data-stu-id="7eb8a-168">Next step</span></span>

<span data-ttu-id="7eb8a-169">Contoso 社が従業員 [向け](contoso-identity.md) クラウドでオンプレミスの Active Directory ドメイン サービスを活用し、顧客とビジネス パートナーのフェデレーション認証を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7eb8a-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="7eb8a-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eb8a-170">See also</span></span>

[<span data-ttu-id="7eb8a-171">ネットワークのロードマップ (Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7eb8a-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="7eb8a-172">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="7eb8a-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7eb8a-173">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="7eb8a-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
