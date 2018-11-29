---
title: '手順 2: オフィスごとにローカルのインターネット接続を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: DNS 解決について理解し、パフォーマンスの良い DNS 解決を構成します。
ms.openlocfilehash: 9ccd5c477b4aeda8e7dcf482cc09c8a357f19f40
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869016"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="7ff14-103">手順 2: オフィスごとにローカルのインターネット接続を構成する</span><span class="sxs-lookup"><span data-stu-id="7ff14-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="7ff14-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7ff14-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="7ff14-p101">手順 2 では、オフィスごとにローカルのインターネット接続を構成し、ローカルの DNS サーバーを使用していることを確認します。どちらも、接続待機時間を削減し、オンプレミスのクライアント コンピューターが Microsoft 365 クラウドベース サービスの最寄りのエントリ ポイントに確実に接続するために必要な要素です。</span><span class="sxs-lookup"><span data-stu-id="7ff14-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="7ff14-p102">大規模な組織向けの従来型ネットワークの場合、インターネット トラフィックはネットワーク バックボーンを通過してから中央インターネット接続に到達します。グローバルに分散した、Office 365 や Microsoft 365 の Enterprise Mobility + Security (EMS) 製品を含むサービスとしてのソフトウェア (SaaS) インフラストラクチャの場合、この方法ではパフォーマンスを最適化できません。</span><span class="sxs-lookup"><span data-stu-id="7ff14-p102">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="7ff14-p103">Microsoft のグローバル ネットワークには、Microsoft 365 の一連のクラウド サービスで使用するフロント エンド サーバーが世界中に配置されています。最適なパフォーマンスを実現するため、オンプレミスのクライアントは、ネットワーク バックボーンを介して組織の中央インターネット接続に最も近いフロントエンド サーバーにトラフィックを送信するのではなく、地理的に最も近いフロントエンド サーバーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ff14-p103">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="7ff14-p104">地理的に最も近いフロントエンド サーバーにクライアントの要求を送信するため、Microsoft の DNS サーバーは、クライアントの最初の接続要求に対応する DNS クエリを使用します。したがって、ネットワーク待ち時間を最短にするには、次のことが必要です。</span><span class="sxs-lookup"><span data-stu-id="7ff14-p104">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="7ff14-113">組織のすべてのオフィスに、[最適化](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)カテゴリのネットワーク トラフィック用のローカル インターネット接続が用意されている。</span><span class="sxs-lookup"><span data-stu-id="7ff14-113">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="7ff14-114">各ローカル インターネット接続で、その地点からの送信インターネット トラフィックに、地理的にローカルな DNS サーバーを使用している。</span><span class="sxs-lookup"><span data-stu-id="7ff14-114">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="7ff14-115">詳細については、「[ネットワーク接続のローカルの出口を提供する](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ff14-115">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="7ff14-116">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step2)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7ff14-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="7ff14-117">次の手順</span><span class="sxs-lookup"><span data-stu-id="7ff14-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="7ff14-118">ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="7ff14-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
