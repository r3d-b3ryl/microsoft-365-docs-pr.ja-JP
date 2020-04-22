---
title: '手順 3: ネットワーク ヘアピンを回避する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ネットワーク ヘアピンについて理解して削除することにより、パフォーマンスの向上を図ります。
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583427"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="e94f6-103">手順 3: ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="e94f6-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="e94f6-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="e94f6-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 1 - ネットワーキング](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="e94f6-106">[ネットワーク ヘアピン](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)は、宛先に向けられたトラフィックが最初にオンプレミス セキュリティ スタック、クラウド アクセス ブローカー、クラウドベースの Web ゲートウェイなどの別の中間場所に向けられたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e94f6-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="e94f6-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e94f6-107">Here is an example.</span></span>

![ネットワーク ヘアピンの例](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="e94f6-109">ネットワーク ヘアピンは、ネットワーク サービス プロバイダーが原因でインターネット上のルーティングが不十分な場合にも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e94f6-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="e94f6-110">ヘアピンは待機時間を追加し、潜在的にトラフィックを地理的に離れた場所にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="e94f6-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="e94f6-p102">Microsoft 365 のクラウドベース サービスに対するトラフィックのパフォーマンスを最適化するには、ローカルのインターネット接続を提供する ISP と、その場所と近接した Microsoft のグローバル ネットワークの間に直接のピアリング関係があるかを確認します。そのような接続では、ヘアピンは生じません。</span><span class="sxs-lookup"><span data-stu-id="e94f6-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="e94f6-p103">Microsoft 365 のトラフィックにクラウドベースのネットワークやセキュリティ サービスを使用している場合は、ヘアピンの影響を評価し、パフォーマンスに与える影響を理解する必要があります。次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="e94f6-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="e94f6-115">支店や Microsoft グローバル ネットワークのピアリング ポイントとの関係においてトラフィックの転送経路となるサービス プロバイダーの数および場所。</span><span class="sxs-lookup"><span data-stu-id="e94f6-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="e94f6-116">サービス プロバイダーと ISP や Microsoft とのネットワーク ピアリング関係の品質。</span><span class="sxs-lookup"><span data-stu-id="e94f6-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="e94f6-117">サービス プロバイダーのインフラストラクチャ内で生じるバックホーリングがパフォーマンスに与える影響。</span><span class="sxs-lookup"><span data-stu-id="e94f6-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="e94f6-118">可能であれば、インターネット トラフィックを処理するサード パーティのクラウドやクラウドベース ネットワーク セキュリティ ベンダーを介したプロキシ処理やトンネリング処理を行うのではなく、信頼済みの Microsoft 365 トラフィックを直接送信するようにエッジ ルーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="e94f6-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![ネットワーク ヘアピンをバイパスする例](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="e94f6-120">Microsoft のグローバルネットワークのエントリポイントまでの距離と、組織のネットワークが ISP に接続するポイントまでの距離をテストするには、[Office 365 ネットワーク オンボードツール](https://connectivity.office.com/)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e94f6-120">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="e94f6-121">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step3)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e94f6-121">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e94f6-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="e94f6-122">Next step</span></span>

|||
|:-------|:-----|
|![手順 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="e94f6-124">トラフィック バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="e94f6-124">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
