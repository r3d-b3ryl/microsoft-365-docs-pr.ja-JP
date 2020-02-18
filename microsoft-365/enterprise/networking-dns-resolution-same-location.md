---
title: '手順 2: オフィスごとにローカルのインターネット接続を構成する'
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
description: DNS 解決について理解し、パフォーマンスの良い DNS 解決を構成します。
ms.openlocfilehash: 8b4302c06e75c59a1b99eb60399c9df897ad17ea
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066666"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="f3dce-103">手順 2: オフィスごとにローカルのインターネット接続を構成する</span><span class="sxs-lookup"><span data-stu-id="f3dce-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="f3dce-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="f3dce-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 1 - ネットワーキング](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="f3dce-p101">手順 2 では、オフィスごとにローカルのインターネット接続を構成し、ローカルの DNS サーバーを使用していることを確認します。どちらも、接続待機時間を削減し、オンプレミスのクライアント コンピューターが Microsoft 365 クラウドベース サービスの最寄りのエントリ ポイントに確実に接続するために必要な要素です。</span><span class="sxs-lookup"><span data-stu-id="f3dce-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="f3dce-108">大規模な組織の従来のネットワークの場合、インターネット トラフィックは、ネットワーク バックボーンを横断して中央インターネット接続に到達します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="f3dce-109">グローバルに分散した、Office 365 や Microsoft 365 の Intune 製品を含む、サービスとしてのソフトウェア (SaaS) インフラストラクチャの場合、この方法ではパフォーマンスの最適化がうまくいきません。</span><span class="sxs-lookup"><span data-stu-id="f3dce-109">This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Intune products in Microsoft 365.</span></span>

<span data-ttu-id="f3dce-110">Microsoft のグローバル ネットワークには、地理的に分散された場所を用いた高可用性でスケーラブルなネットワーク エッジとなる *分散サービス フロント ドア* インフラストラクチャが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3dce-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="f3dce-111">それは、フロント ドア サーバーでエンド ユーザー接続を終了させ、Microsoft のグローバル ネットワーク内でエンド ユーザー トラフィックを効率的にルーティングさせます。</span><span class="sxs-lookup"><span data-stu-id="f3dce-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![Microsoft のグローバル ネットワーク](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="f3dce-113">最高のパフォーマンスを目指す場合、オンプレミスのクライアントは、ネットワーク バックボーン全体や組織の中央インターネット接続に最も近いフロント ドアにトラフィックを送信するのではなく、地理的に最も近い場所のフロント ドアにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3dce-113">For the best performance, on-premises clients should access a front door location that is geographically closest to them, rather than sending the traffic over a network backbone and to the front door that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="f3dce-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-114">Here’s an example.</span></span>

![Microsoft のグローバル ネットワークの使用例](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="f3dce-116">パリ支社のユーザーが SharePoint Online サイトにアクセスする場合:</span><span class="sxs-lookup"><span data-stu-id="f3dce-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="f3dce-117">Contoso.sharepoint.com など、名前解決のために DNS クエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="f3dce-118">ISP によって提供される DNS サーバーでは、そのクエリを Microsoft DNS サーバーに転送します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="f3dce-119">Microsoft の DNS サーバーでは、転送された DNS クエリのソース IP アドレスからそのアドレスが割り当てられている世界の地域を特定します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="f3dce-120">Microsoft DNS サーバーでは、ヨーロッパで最も近い Microsoft ネットワーク フロント ドアの IP アドレスに応答します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="f3dce-121">ISP の DNS サーバーでは、その IP アドレスをユーザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="f3dce-122">ユーザーは、ヨーロッパのフロント ドアを通過して SharePoint サーバーへの接続を開始します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="f3dce-123">地理的に最も近いフロント ドアへとクライアント要求を方向づけるために、Microsoft の DNS サーバーでは、クライアントの最初の接続要求に対応した DNS クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-123">To direct a client request to the geographically nearest front door, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request.</span></span> <span data-ttu-id="f3dce-124">そのため、次のようにしてネットワーク遅延を最小化します。</span><span class="sxs-lookup"><span data-stu-id="f3dce-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="f3dce-125">組織のすべてのオフィスに、[最適化](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)カテゴリのネットワーク トラフィック用のローカル インターネット接続が用意されている。</span><span class="sxs-lookup"><span data-stu-id="f3dce-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="f3dce-126">各ローカル インターネット接続で、その地点からの送信インターネット トラフィックに、地理的にローカルな DNS サーバーを使用している。</span><span class="sxs-lookup"><span data-stu-id="f3dce-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="f3dce-127">詳細については、「[ネットワーク接続のローカルの出口を提供する](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3dce-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="f3dce-128">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step2)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3dce-128">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f3dce-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="f3dce-129">Next step</span></span>

|||
|:-------|:-----|
|![手順 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="f3dce-131">ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="f3dce-131">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
