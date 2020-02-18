---
title: '手順 3: ネットワーク ヘアピンを回避する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ネットワーク ヘアピンについて理解して削除することにより、パフォーマンスの向上を図ります。
ms.openlocfilehash: f9499fdb8e8c3f7b77e3349d6cc99f6dbf465870
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066716"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="3d750-103">手順 3: ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="3d750-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="3d750-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="3d750-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 1 - ネットワーキング](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="3d750-106">[ネットワーク ヘアピン](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)は、宛先に向けられたトラフィックが最初にオンプレミス セキュリティ スタック、クラウド アクセス ブローカー、クラウドベースの Web ゲートウェイなどの別の中間場所に向けられたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3d750-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="3d750-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3d750-107">Here is an example.</span></span>

![ネットワーク ヘアピンの例](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="3d750-109">ネットワーク ヘアピンは、ネットワーク サービス プロバイダーが原因でインターネット上のルーティングが不十分な場合にも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d750-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="3d750-110">ヘアピンは待機時間を追加し、潜在的にトラフィックを地理的に離れた場所にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="3d750-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="3d750-p102">Microsoft 365 のクラウドベース サービスに対するトラフィックのパフォーマンスを最適化するには、ローカルのインターネット接続を提供する ISP と、その場所と近接した Microsoft のグローバル ネットワークの間に直接のピアリング関係があるかを確認します。そのような接続では、ヘアピンは生じません。</span><span class="sxs-lookup"><span data-stu-id="3d750-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="3d750-p103">Microsoft 365 のトラフィックにクラウドベースのネットワークやセキュリティ サービスを使用している場合は、ヘアピンの影響を評価し、パフォーマンスに与える影響を理解する必要があります。次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="3d750-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="3d750-115">支店や Microsoft グローバル ネットワークのピアリング ポイントとの関係においてトラフィックの転送経路となるサービス プロバイダーの数および場所。</span><span class="sxs-lookup"><span data-stu-id="3d750-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="3d750-116">サービス プロバイダーと ISP や Microsoft とのネットワーク ピアリング関係の品質。</span><span class="sxs-lookup"><span data-stu-id="3d750-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="3d750-117">サービス プロバイダーのインフラストラクチャ内で生じるバックホーリングがパフォーマンスに与える影響。</span><span class="sxs-lookup"><span data-stu-id="3d750-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="3d750-118">可能であれば、インターネット トラフィックを処理するサード パーティのクラウドやクラウドベース ネットワーク セキュリティ ベンダーを介したプロキシ処理やトンネリング処理を行うのではなく、信頼済みの Microsoft 365 トラフィックを直接送信するようにエッジ ルーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="3d750-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![ネットワーク ヘアピンをバイパスする例](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="3d750-120">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step3)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3d750-120">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="3d750-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="3d750-121">Next step</span></span>

|||
|:-------|:-----|
|![手順 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="3d750-123">トラフィック バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="3d750-123">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
