---
title: Contoso Corporation のネットワーク
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のネットワークインフラストラクチャと、その SD テクノロジを使用して、エンタープライズクラウドサービスの Microsoft 365 に対する最適なネットワークパフォーマンスを実現する方法について理解します。
ms.openlocfilehash: bc2ae68917258b94ed46ef0c1257f56e0736105c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685820"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="846b5-103">Contoso Corporation のネットワーク</span><span class="sxs-lookup"><span data-stu-id="846b5-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="846b5-p101">クラウドを組み込んだインフラストラクチャを導入するために、Contoso 社のネットワーク エンジニアは、ネットワーク トラフィックがクラウド サービスへ移動する際の根本的な変化を認識しました。Contoso オフィス階層の次のレベルのネットワーク接続とトラフィックに焦点を当てた内部ハブおよびスポーク モデルの代わりに、ユーザーの場所をローカルのインターネット出口と、インターネット上の最も近い Microsoft 365 ネットワークの場所へのローカル接続にマッピングしました。</span><span class="sxs-lookup"><span data-stu-id="846b5-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels. Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="846b5-106">Contoso 社のネットワーク インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="846b5-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="846b5-107">世界中のオフィスをつなぐ Contoso 社のネットワークの要素を次に示します。</span><span class="sxs-lookup"><span data-stu-id="846b5-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="846b5-108">Multiprotocol Label Switching (MPLS) WAN ネットワーク</span><span class="sxs-lookup"><span data-stu-id="846b5-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="846b5-p102">MPLS WAN ネットワークは、パリの本社と地方の支店や、地方の支店とサテライト オフィスを、スポークおよびハブによる構成で接続します。これは、ユーザーがパリのオフィスで基幹業務アプリケーションを構成するオンプレミス サーバーにアクセスするためのものです。また、一般的なインターネット トラフィックを、ネットワーク セキュリティ デバイスが要求をスクラブするパリのオフィスにルーティングします。各オフィス内でルーターは、プライベート IP アドレス空間を使用するサブネット上の有線ホストまたは無線アクセス ポイントにトラフィックを配信します。</span><span class="sxs-lookup"><span data-stu-id="846b5-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="846b5-113">Microsoft 365 トラフィックのローカル ダイレクト インターネット アクセス</span><span class="sxs-lookup"><span data-stu-id="846b5-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="846b5-p103">各オフィスには、1 つ以上のローカル インターネット ISP ネットワーク回線を持つソフトウェアによる WAN (SD-WAN) デバイスがあり、プロキシ サーバー経由でインターネットに接続します。これは通常、パブリック IP アドレスとローカル DNS サーバーの IPアドレスも提供するローカル ISP への WAN リンクとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="846b5-p103">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="846b5-116">インターネット プレゼンス</span><span class="sxs-lookup"><span data-stu-id="846b5-116">Internet presence</span></span>

  <span data-ttu-id="846b5-p104">Contoso 社は、contoso.com パブリック ドメイン名を所有しています。製品を発注するための Contoso 社のパブリック Web サイトは、パリ キャンパスのインターネット接続データセンター内のサーバー セットです。Contoso 社は、インターネット上の /24 のパブリック IP アドレス範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="846b5-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="846b5-120">図 1 は、Contoso 社のネットワーク インフラストラクチャと、そのインターネットに対する接続を示しています。</span><span class="sxs-lookup"><span data-stu-id="846b5-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Contoso 社のネットワーク](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="846b5-122">**図 1: Contoso 社のネットワーク**</span><span class="sxs-lookup"><span data-stu-id="846b5-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="846b5-123">Microsoft への最適なネットワーク接続のための SD-WAN の使用</span><span class="sxs-lookup"><span data-stu-id="846b5-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="846b5-124">Contoso 社は次の [Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)に従いました。</span><span class="sxs-lookup"><span data-stu-id="846b5-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

1. <span data-ttu-id="846b5-125">Microsoft 365 ネットワーク トラフィックを識別して区別する</span><span class="sxs-lookup"><span data-stu-id="846b5-125">Identify and differentiate Microsoft 365 network traffic</span></span>
2. <span data-ttu-id="846b5-126">ネットワーク接続のローカルの出口を提供する</span><span class="sxs-lookup"><span data-stu-id="846b5-126">Egress network connections locally</span></span>
3. <span data-ttu-id="846b5-127">ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="846b5-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="846b5-128">重複するネットワーク セキュリティ デバイスをバイパスする</span><span class="sxs-lookup"><span data-stu-id="846b5-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="846b5-129">Microsoft 365 のネットワーク トラフィックには、最適化、許可、既定の 3 つのカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="846b5-129">There are three categories of network traffic for Microsoft 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="846b5-130">トラフィックの最適化と許可は、エンドポイントで暗号化およびセキュリティ保護された信頼できるネットワーク トラフィックであり、Microsoft 365 ネットワーク宛てです。</span><span class="sxs-lookup"><span data-stu-id="846b5-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="846b5-131">Contoso は次のように決定しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-131">Contoso decided to:</span></span>

- <span data-ttu-id="846b5-132">最適化カテゴリと許可カテゴリのトラフィック用に直接のインターネット出口を使用し、すべての既定カテゴリのトラフィックをパリに本部を置く中央インターネット接続に転送することにしました。</span><span class="sxs-lookup"><span data-stu-id="846b5-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="846b5-133">これらの原則に従い、Microsoft 365 クラウドベースのサービスで最適なネットワーク パフォーマンスを実現する簡単な方法として、各オフィスに SD-WAN デバイスを導入することに決めました。</span><span class="sxs-lookup"><span data-stu-id="846b5-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="846b5-134">SD-WAN デバイスには、ローカル オフィス ネットワーク用の LAN ポートと複数の WAN ポートがあります。</span><span class="sxs-lookup"><span data-stu-id="846b5-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="846b5-135">1 つの WAN ポートは MPLS ネットワークに接続し、別の WAN ポートはローカル ISP 回線に接続します。</span><span class="sxs-lookup"><span data-stu-id="846b5-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="846b5-136">SD-WAN デバイスは、ISP リンクを介してカテゴリ ネットワーク トラフィックを最適化および許可します。</span><span class="sxs-lookup"><span data-stu-id="846b5-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="846b5-137">Contoso 社の基幹業務アプリケーションのインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="846b5-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="846b5-138">Contoso 社は、次のような基幹業務アプリケーションおよびサーバー イントラネット インフラストラクチャを設計しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="846b5-139">サテライト オフィスは、ローカル キャッシュ サーバーを使用して、アクセス頻度の高いドキュメントおよび内部 Web サイトを格納します。</span><span class="sxs-lookup"><span data-stu-id="846b5-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="846b5-p107">地域ハブは、地域オフィスおよびサテライト オフィスに地域アプリケーション サーバーを使用します。これらのサーバーは、パリ本社のサーバーと同期します。</span><span class="sxs-lookup"><span data-stu-id="846b5-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="846b5-142">パリ キャンパスには、組織全体にサービスを提供する集中管理されたアプリケーション サーバーを含むデータセンターが存在します。</span><span class="sxs-lookup"><span data-stu-id="846b5-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="846b5-143">図 2 は、Contoso 社のイントラネット サーバー アクセス時のネットワーク トラフィックの割合を示します。</span><span class="sxs-lookup"><span data-stu-id="846b5-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Contoso 社の内部アプリケーションのインフラストラクチャ](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="846b5-145">**図 2: Contoso 社の内部アプリケーションのインフラストラクチャ**</span><span class="sxs-lookup"><span data-stu-id="846b5-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="846b5-p108">サテライト オフィスまたは地域ハブ オフィスのユーザーについては、従業員が必要とするリソースの 60% をサテライト オフィスおよび地域ハブ オフィスのサーバーでまかなうことができます。リソース要求の残りの 40% は、WAN リンク経由でパリ キャンパスに引き継がれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="846b5-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-for-enterprise"></a><span data-ttu-id="846b5-148">Contoso 社のネットワーク分析と、Microsoft 365 for enterprise のネットワークの準備</span><span class="sxs-lookup"><span data-stu-id="846b5-148">Contoso's network analysis and preparation of their network for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="846b5-p109">Contoso 社のユーザーによるエンタープライズサービスへの Microsoft 365 の導入を成功させるには、インターネットへの可用性とパフォーマンスの高い接続、または Microsoft クラウドサービスへの直接アクセスがあります。Contoso 社は次の手順を実行して、エンタープライズクラウドサービス用に Microsoft 365 への接続の最適化を計画し、実装しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-p109">Successful adoption of Microsoft 365 for enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="846b5-151">計画の支援のために、会社の WAN ネットワーク ダイアグラムを作成</span><span class="sxs-lookup"><span data-stu-id="846b5-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="846b5-p110">Contoso 社は、ネットワーク上で管理されている場所、既存のネットワーク接続、既存のネットワーク周辺機器、サービス クラスを示す図を作成して、ネットワーク計画を開始しました。ネットワーク接続の計画と実装における後続の各ステップにおいて、この図が使用されました。</span><span class="sxs-lookup"><span data-stu-id="846b5-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="846b5-154">エンタープライズネットワーク接続用の Microsoft 365 の計画を作成しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-154">Created a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="846b5-155">Contoso 社は、[Microsoft 365 のネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)を使用し、参照ネットワーク アーキテクチャを提供して、Microsoft 365 接続の優先トポロジを SD-WAN にすることに決定しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-155">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and provided reference network architectures to determine SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="846b5-156">各オフィスのインターネット接続利用率と MPLS WAN 帯域幅を分析し、必要に応じて帯域幅を拡大</span><span class="sxs-lookup"><span data-stu-id="846b5-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="846b5-157">各オフィスで現在の使用状況が分析され、予測される Microsoft 365 のクラウドベースのトラフィックが未使用容量の平均 20% で動作するように回線が増加されました。</span><span class="sxs-lookup"><span data-stu-id="846b5-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="846b5-158">Microsoft ネットワーク サービスへのパフォーマンスを最適化</span><span class="sxs-lookup"><span data-stu-id="846b5-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="846b5-159">Contoso 社は、Office 365、Intune、Azure のエンドポイントのセットを決定し、最適なパフォーマンスを得るために、インターネット パス内のファイアウォール、セキュリティ デバイス、およびその他のシステムを構成しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="846b5-160">Office 365 のエンドポイントは、ISP 回線を介してルーティングするために、SD-WAN デバイスに最適化および許可カテゴリ トラフィックを構成しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="846b5-161">内部 DNS の構成</span><span class="sxs-lookup"><span data-stu-id="846b5-161">Configured internal DNS</span></span>

   <span data-ttu-id="846b5-162">DNS が機能し、Microsoft 365 トラフィックのためにローカルで検索対象になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="846b5-162">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="846b5-163">ネットワーク エンドポイントとポートの接続を検証</span><span class="sxs-lookup"><span data-stu-id="846b5-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="846b5-164">Contoso 社は、microsoft が提供するネットワーク接続テストツールを実行して、エンタープライズクラウドサービスのための Microsoft 365 の接続を検証しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="846b5-165">従業員のコンピューターのネットワーク接続を最適化</span><span class="sxs-lookup"><span data-stu-id="846b5-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="846b5-166">各自のコンピューターをチェックして、最新のオペレーティング システムの更新プログラムがインストールされ、すべてのクライアントでエンドポイント セキュリティ監視がアクティブであることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="846b5-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="846b5-167">次の手順</span><span class="sxs-lookup"><span data-stu-id="846b5-167">Next step</span></span>

<span data-ttu-id="846b5-168">Contoso 社が、どのようにクラウド内のオンプレミスの Active Directory ドメイン サービス (AD DS) を従業員向けに利用し、どのように顧客やビジネス パートナー向けのフェデレーション認証を活用しているかについて[説明](contoso-identity.md)します。</span><span class="sxs-lookup"><span data-stu-id="846b5-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="846b5-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="846b5-169">See also</span></span>

[<span data-ttu-id="846b5-170">Microsoft 365 のネットワークロードマップ</span><span class="sxs-lookup"><span data-stu-id="846b5-170">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="846b5-171">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="846b5-171">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="846b5-172">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="846b5-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
