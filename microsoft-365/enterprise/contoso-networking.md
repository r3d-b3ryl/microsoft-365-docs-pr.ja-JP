---
title: Contoso Corporation のネットワーク
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のネットワーク インフラストラクチャと、Microsoft 365 Enterprise のクラウドベースのサービスに対する最高性能のネットワーク接続性を得るために SD-WAN テクノロジをどのように使用しているかについて説明します。
ms.openlocfilehash: 0ef9c37755927444276c83a2c5952b5cb96f22ed
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868993"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="7b479-103">Contoso Corporation のネットワーク</span><span class="sxs-lookup"><span data-stu-id="7b479-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="7b479-104">**概要:** Contoso 社のネットワーク インフラストラクチャと、Microsoft 365 Enterprise のクラウドベースのサービスに対する最高性能のネットワーク接続性を得るために SD-WAN テクノロジをどのように使用しているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7b479-104">**Summary:** Understand the Contoso networking infrastructure and how it uses its SD WAN technology for optimal performance network connectivity to Microsoft 365 Enterprise cloud based services.</span></span>

<span data-ttu-id="7b479-p101">クラウドを組み込んだインフラストラクチャを導入するために、Contoso 社のネットワーク エンジニアは、ネットワーク トラフィックがクラウドベースのサービスへ移動する際の根本的な変化を認識しました。本社のネットワーク接続に注目したハブ アンド スポーク モデルの代わりに、ユーザーの場所をローカルのインターネット出口と、インターネット上の Microsoft ネットワークの場所へのローカル接続にマッピングしました。</span><span class="sxs-lookup"><span data-stu-id="7b479-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud-based services travels. Instead of a hub and spoke model that focusses network connectivity on the head office, they worked to map user locations to local Internet egress and local connections to Microsoft network locations on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="7b479-107">Contoso 社のネットワーク インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="7b479-107">Contoso's networking infrastructure</span></span>

<span data-ttu-id="7b479-108">世界中のオフィスをつなぐ Contoso 社のネットワークの要素を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7b479-108">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="7b479-109">MPLS WAN ネットワーク</span><span class="sxs-lookup"><span data-stu-id="7b479-109">MPLS WAN network</span></span>

  <span data-ttu-id="7b479-p102">MPLS WAN ネットワークは、パリの本社と地方の支店や、地方の支店とサテライト オフィスを、スポークとハブによる構成で接続します。これは、ユーザーがパリのオフィスで基幹業務アプリケーションを構成するオンプレミス サーバーにアクセスするためのものです。また、一般的なインターネット トラフィックを、ネットワーク セキュリティ デバイスが要求をスクラブするパリのオフィスにルーティングします。各オフィス内でルーターは、プライベート IP アドレス空間を使用するサブネット上のホストまたはワイヤレス アクセス ポイントにトラフィックを配信します。</span><span class="sxs-lookup"><span data-stu-id="7b479-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="7b479-114">Office 365 のトラフィック向けのローカル インターネット直接アクセス</span><span class="sxs-lookup"><span data-stu-id="7b479-114">Local direct Internet access for Office 365 traffic</span></span>

  <span data-ttu-id="7b479-p103">各オフィスには、1 つ以上のローカル インターネット ISP ネットワーク回線を持つ SD-WAN デバイスがあり、プロキシ サーバー経由でインターネットに接続します。これは通常、プロキシ サーバーのパブリック IP アドレスとローカル DNS サーバーの IPアドレスも提供するローカル ISP への WAN リンクとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="7b479-p103">Each office has an SD WAN device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and local DNS server IP addresses for the proxy server.</span></span>

- <span data-ttu-id="7b479-117">インターネット プレゼンス</span><span class="sxs-lookup"><span data-stu-id="7b479-117">Internet presence</span></span>

  <span data-ttu-id="7b479-p104">Contoso 社は、contoso.com パブリック ドメイン名を所有しています。製品を発注するための Contoso 社のパブリック Web サイトは、パリ キャンパスのインターネット接続データセンター内のサーバー セットです。Contoso 社は、インターネット上の /24 のパブリック IP アドレス範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b479-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="7b479-121">図 1 は、Contoso 社のネットワーク インフラストラクチャと、そのインターネットに対する接続を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b479-121">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![](./media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="7b479-122">**図 1: Contoso 社のネットワーク**</span><span class="sxs-lookup"><span data-stu-id="7b479-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="7b479-123">Microsoft への最適なネットワーク接続のための SD-WAN の使用</span><span class="sxs-lookup"><span data-stu-id="7b479-123">Use of SD WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="7b479-124">Contoso 社は [Office 365 ネットワーク接続の原則](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)に従いました。</span><span class="sxs-lookup"><span data-stu-id="7b479-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):</span></span>

1. <span data-ttu-id="7b479-125">Office 365 ネットワーク トラフィックを識別して区別する</span><span class="sxs-lookup"><span data-stu-id="7b479-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="7b479-126">ネットワーク接続のローカルの出口を提供する</span><span class="sxs-lookup"><span data-stu-id="7b479-126">Egress network connections locally</span></span>
3. <span data-ttu-id="7b479-127">ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="7b479-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="7b479-128">重複するネットワーク セキュリティ デバイスをバイパスする</span><span class="sxs-lookup"><span data-stu-id="7b479-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="7b479-p105">Office 365 のネットワーク トラフィックには、最適化、許可、既定の 3 つのカテゴリがあります。最適化トラフィックと許可トラフィックは、エンドポイントで暗号化され、セキュリティで保護された、Microsoft データセンター向けの信頼されたネットワーク トラフィックです。</span><span class="sxs-lookup"><span data-stu-id="7b479-p105">There are three categories of network traffic for Office 365: Optimize, Allow, and Default. Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for Microsoft datacenters.</span></span>

<span data-ttu-id="7b479-131">Contoso 社は、最適化カテゴリと許可カテゴリのトラフィック用に直接のインターネット出口を使用し、すべての既定カテゴリのトラフィックをパリに本部を置く中央インターネット接続に転送することにしました。</span><span class="sxs-lookup"><span data-stu-id="7b479-131">Contoso decided to use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

<span data-ttu-id="7b479-132">同社は、これらの原則に従い、Microsoft 365 クラウドベースのサービスで最適なネットワーク パフォーマンスを実現する簡単な方法として、各オフィスに SD-WAN デバイスを導入することに決めました。</span><span class="sxs-lookup"><span data-stu-id="7b479-132">They decided to deploy SD WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="7b479-p106">SD-WAN デバイスには、ローカル オフィス ネットワーク用の LAN ポートと複数の WAN ポートがあります。1 つの WAN ポートが MPLS ネットワークに接続し、他の WAN ポートがローカル ISP 回線に接続します。SD-WAN デバイスは、最適化および許可カテゴリのネットワーク トラフィックを ISP リンクにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7b479-p106">The SD WAN devices have a LAN port for the local office network and multiple WAN ports. One WAN port connects to their MPLS network and other WAN ports connect to local ISP circuits. The SD WAN device routes Optimize and Allow category network traffic to the ISP links.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="7b479-136">Contoso 社の基幹業務アプリケーションのインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="7b479-136">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="7b479-137">Contoso 社は、次のような基幹業務アプリケーションおよびサーバー インフラストラクチャを設計しました。</span><span class="sxs-lookup"><span data-stu-id="7b479-137">Contoso has architected its line of business application and server infrastructure for the following:</span></span>

- <span data-ttu-id="7b479-138">サテライト オフィスは、ローカル キャッシュ サーバーを使用して、アクセス頻度の高いドキュメントおよび内部 Web サイトを格納します。</span><span class="sxs-lookup"><span data-stu-id="7b479-138">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="7b479-p107">地域ハブは、地域オフィスおよびサテライト オフィスに地域アプリケーション サーバーを使用します。これらのサーバーは、パリ本社のサーバーと同期します。</span><span class="sxs-lookup"><span data-stu-id="7b479-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="7b479-141">パリ キャンパスには、組織全体にサービスを提供する集中管理されたアプリケーション サーバーを含むデータセンターが存在します。</span><span class="sxs-lookup"><span data-stu-id="7b479-141">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="7b479-142">図 2 は、Contoso 社のイントラネット サーバー アクセス時のネットワーク トラフィックの割合を示します。</span><span class="sxs-lookup"><span data-stu-id="7b479-142">Figure 1 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![](./media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="7b479-143">**図 2: Contoso 社の内部アプリケーションのインフラストラクチャ**</span><span class="sxs-lookup"><span data-stu-id="7b479-143">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="7b479-p108">サテライト オフィスまたは地域ハブ オフィスのユーザーについては、従業員が必要とするリソースの 60% をサテライト オフィスおよび地域ハブ オフィスのサーバーでまかなうことができます。リソース要求の残りの 40% は、WAN リンク経由でパリ キャンパスに引き継がれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b479-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="7b479-146">Contoso 社のネットワーク分析と Microsoft 365 Enterprise のネットワークの準備</span><span class="sxs-lookup"><span data-stu-id="7b479-146">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7b479-p109">Contoso 社のユーザーによる Microsoft 365 Enterprise サービスの導入が成功するかどうかは、インターネットへの高可用性と高性能の接続、または Microsoft クラウド サービスへの直接接続によります。Contoso 社は、Microsoft 365 Enterprise のクラウド サービスへの最適な接続を計画および実装するために、次の手順を実行しました。</span><span class="sxs-lookup"><span data-stu-id="7b479-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="7b479-149">計画の支援のために、会社の WAN ネットワーク ダイアグラムを作成</span><span class="sxs-lookup"><span data-stu-id="7b479-149">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="7b479-p110">Contoso 社は、ネットワーク上で管理されている場所、既存のネットワーク接続、既存のネットワーク周辺機器、サービス クラスを示す図を作成して、ネットワーク計画を開始しました。ネットワーク接続の計画と実装における後続の各ステップにおいて、この図が使用されました。</span><span class="sxs-lookup"><span data-stu-id="7b479-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="7b479-152">Microsoft 365 Enterprise のネットワーク接続の計画を作成</span><span class="sxs-lookup"><span data-stu-id="7b479-152">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="7b479-153">Contoso 社は、[Office 365 のネットワーク接続の原則](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)を使用し、参照ネットワーク アーキテクチャを提供して、Office 365 接続の優先トポロジを SD-WAN にすることに決定しました。</span><span class="sxs-lookup"><span data-stu-id="7b479-153">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="7b479-154">各オフィスのインターネット接続利用率と MPLS WAN 帯域幅を分析し、必要に応じて帯域幅を拡大</span><span class="sxs-lookup"><span data-stu-id="7b479-154">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="7b479-155">各オフィスで現在の使用状況が分析され、予測される Microsoft 365 のクラウドベースのトラフィックが未使用容量の平均 20% で動作するように回線が増加されました。</span><span class="sxs-lookup"><span data-stu-id="7b479-155">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="7b479-156">Microsoft ネットワーク サービスへのパフォーマンスを最適化</span><span class="sxs-lookup"><span data-stu-id="7b479-156">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="7b479-p111">Contoso 社は、最適なパフォーマンスを得るために、Office 365、Intune、Azure エンドポイントのセットを決定し、インターネット パス上にファイアウォール、セキュリティ デバイス、その他のシステムを構成しました。Office 365 の最適化および許可カテゴリのトラフィックのエンドポイントは、インターネットへの直接アクセスを可能にする SD-WAN デバイスに構成されました。</span><span class="sxs-lookup"><span data-stu-id="7b479-p111">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance. Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD WAN devices that provided direct Internet access.</span></span>

5. <span data-ttu-id="7b479-159">内部 DNS の構成</span><span class="sxs-lookup"><span data-stu-id="7b479-159">Configured internal DNS</span></span>

   <span data-ttu-id="7b479-160">DNS が機能し、Office 365 トラフィックのためにローカルで検索対象になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b479-160">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="7b479-161">ネットワーク エンドポイントとポートの接続を検証</span><span class="sxs-lookup"><span data-stu-id="7b479-161">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="7b479-162">Contoso 社は、Microsoft が提供するネットワーク接続テスト ツールを実行して、Microsoft 365 Enterprise のクラウド サービスの接続を検証しました。</span><span class="sxs-lookup"><span data-stu-id="7b479-162">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="7b479-163">従業員のコンピューターのネットワーク接続を最適化</span><span class="sxs-lookup"><span data-stu-id="7b479-163">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="7b479-164">各自のコンピューターをチェックして、最新のオペレーティング システムの更新プログラムがインストールされ、すべてのクライアントでエンドポイント セキュリティ監視がアクティブであることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="7b479-164">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="7b479-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="7b479-165">Next step</span></span>

<span data-ttu-id="7b479-166">Contoso 社が、どのようにクラウド内のオンプレミスの ID プロバイダーを従業員向けに利用し、どのように顧客やビジネス パートナー向けのフェデレーション認証を活用しているかについて[説明](contoso-identity.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b479-166">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises identity provider in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b479-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b479-167">See also</span></span>

[<span data-ttu-id="7b479-168">Microsoft 365 Enterprise のネットワーク</span><span class="sxs-lookup"><span data-stu-id="7b479-168">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="7b479-169">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="7b479-169">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7b479-170">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="7b479-170">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
