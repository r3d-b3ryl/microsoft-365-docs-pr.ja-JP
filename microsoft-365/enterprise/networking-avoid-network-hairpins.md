---
title: '手順 3: ネットワーク ヘアピンを回避する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ネットワーク ヘアピンについて理解して削除することにより、パフォーマンスの向上を図ります。
ms.openlocfilehash: eef8770dff6c54da51650b0fb70077fdd125f981
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291521"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="8a5c4-103">手順 3: ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="8a5c4-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="8a5c4-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="8a5c4-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="8a5c4-p101">[ネットワーク ヘアピン](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)は、ある宛先に送信されたトラフィックが、オンプレミスのセキュリティ スタックや、クラウド アクセス ブローカー、クラウドベースの Web ゲートウェイなど、宛先以外の中間の場所に最初に差し向けられると発生します。ネットワーク ヘアピンは、ネットワーク サービス プロバイダーが原因のインターネット上の不適切なルーティングによっても発生する可能性があります。ヘアピンが発生すると、待機時間が増え、地理的に離れた場所にトラフィックがリダイレクトされる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8a5c4-p101">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway. A network hairpin could also be caused by poor routing on the Internet due to network service providers. A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="8a5c4-p102">Microsoft 365 のクラウドベース サービスに対するトラフィックのパフォーマンスを最適化するには、ローカルのインターネット接続を提供する ISP と、その場所と近接した Microsoft のグローバル ネットワークの間に直接のピアリング関係があるかを確認します。そのような接続では、ヘアピンは生じません。</span><span class="sxs-lookup"><span data-stu-id="8a5c4-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="8a5c4-p103">Microsoft 365 のトラフィックにクラウドベースのネットワークやセキュリティ サービスを使用している場合は、ヘアピンの影響を評価し、パフォーマンスに与える影響を理解する必要があります。次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="8a5c4-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="8a5c4-112">支店や Microsoft グローバル ネットワークのピアリング ポイントとの関係においてトラフィックの転送経路となるサービス プロバイダーの数および場所。</span><span class="sxs-lookup"><span data-stu-id="8a5c4-112">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="8a5c4-113">サービス プロバイダーと ISP や Microsoft とのネットワーク ピアリング関係の品質。</span><span class="sxs-lookup"><span data-stu-id="8a5c4-113">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="8a5c4-114">サービス プロバイダーのインフラストラクチャ内で生じるバックホーリングがパフォーマンスに与える影響。</span><span class="sxs-lookup"><span data-stu-id="8a5c4-114">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="8a5c4-115">可能であれば、インターネット トラフィックを処理するサード パーティのクラウドやクラウドベース ネットワーク セキュリティ ベンダーを介したプロキシ処理やトンネリング処理を行うのではなく、信頼済みの Microsoft 365 トラフィックを直接送信するようにエッジ ルーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="8a5c4-115">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

<span data-ttu-id="8a5c4-116">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step3)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a5c4-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8a5c4-117">次の手順</span><span class="sxs-lookup"><span data-stu-id="8a5c4-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="8a5c4-118">トラフィック バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="8a5c4-118">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
