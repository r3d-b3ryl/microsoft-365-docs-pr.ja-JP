---
title: 中国ユーザー向け Microsoft 365 グローバル テナントのパフォーマンスの最適化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: この記事では、グローバル Microsoft 365 テナントの中国ユーザー向けにネットワーク パフォーマンスを最適化するためのガイダンスを提供します。
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923196"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a><span data-ttu-id="3717e-103">中国ユーザー向け Microsoft 365 グローバル テナントのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="3717e-103">Microsoft 365 global tenant performance optimization for China users</span></span>

>[!IMPORTANT]
><span data-ttu-id="3717e-104">このガイダンスは、中国にある **エンタープライズ Microsoft 365** ユーザーがグローバル Microsoft 365 テナントに接続する使用シナリオ **に固有のガイダンスです**。</span><span class="sxs-lookup"><span data-stu-id="3717e-104">This guidance is specific to usage scenarios in which **enterprise Microsoft 365 users located in China** connect to a **global Microsoft 365 tenant**.</span></span> <span data-ttu-id="3717e-105">このガイダンス **は** 、21Vianet がOffice 365 のテナントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="3717e-105">This guidance does **not** apply to tenants in Office 365 operated by 21Vianet.</span></span>

<span data-ttu-id="3717e-106">グローバルな Microsoft 365 テナントと中国での企業プレゼンスを持つ企業では、中国に拠点を置くユーザー向け Microsoft 365 クライアントのパフォーマンスは、中国電話会社のインターネット アーキテクチャに固有の要因によって複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3717e-106">For enterprises with global Microsoft 365 tenants and a corporate presence in China, Microsoft 365 client performance for China-based users can be complicated by factors unique to China Telco's Internet architecture.</span></span>

<span data-ttu-id="3717e-107">中国 ISP は、国境を越えたネットワークの混雑が高レベルになりやすい境界デバイスを経由するグローバルパブリック インターネットへのオフショア接続を規制しています。</span><span class="sxs-lookup"><span data-stu-id="3717e-107">China ISPs have regulated offshore connections to the global public Internet that go through perimeter devices which are prone to high-levels of cross-border network congestion.</span></span> <span data-ttu-id="3717e-108">この輻輳により、中国に入り出るすべてのインターネット トラフィックに対してパケット損失と遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="3717e-108">This congestion creates packet loss and latency for all Internet traffic going into and out of China.</span></span>

![Microsoft 365 トラフィック - 最適化されていない](../media/O365-networking/China-O365-unoptimized.png)

<span data-ttu-id="3717e-110">パケット損失と待機時間は、ネットワーク サービスのパフォーマンス、特に大規模なデータ交換 (ファイル転送の大規模な転送など) を必要とするサービス、またはほぼリアルタイムのパフォーマンス (オーディオおよびビデオ アプリケーション) を必要とするサービスに影響します。</span><span class="sxs-lookup"><span data-stu-id="3717e-110">Packet loss and latency is detrimental to the performance of network services, especially services that require large data exchanges (such as large file transfers) or requiring near real-time performance (audio and video applications).</span></span>

<span data-ttu-id="3717e-111">このトピックの目的は、中国の国境を越えたネットワークの混雑が Microsoft 365 サービスに及ぼす影響を軽減するためのベスト プラクティスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3717e-111">The goal of this topic is to provide best practices for mitigating the impact of China cross-border network congestion on Microsoft 365 services.</span></span> <span data-ttu-id="3717e-112">このトピックでは、中国のキャリア内での複雑なルーティングによる高いパケット遅延の問題など、他の一般的なラストマイルのパフォーマンスの問題については説明します。</span><span class="sxs-lookup"><span data-stu-id="3717e-112">This topic does not address other common last-mile performance issues such as issues of high packet latency due to complex routing within China carriers.</span></span>

## <a name="corporate-network-best-practices"></a><span data-ttu-id="3717e-113">企業ネットワークのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3717e-113">Corporate network best practices</span></span>

<span data-ttu-id="3717e-114">グローバルな Microsoft 365 テナントと中国のユーザーを持つ多くの企業は、中国のオフィスの場所と世界中のオフショアの場所間の企業ネットワーク トラフィックを運ぶプライベート ネットワークを実装しています。</span><span class="sxs-lookup"><span data-stu-id="3717e-114">Many enterprises with global Microsoft 365 tenants and users in China have implemented private networks that carry corporate network traffic between China office locations and offshore locations around the world.</span></span> <span data-ttu-id="3717e-115">これらの企業は、このネットワーク インフラストラクチャを活用して、国境を越えたネットワークの混雑を回避し、中国での Microsoft 365 サービスのパフォーマンスを最適化できます。</span><span class="sxs-lookup"><span data-stu-id="3717e-115">These enterprises can leverage this network infrastructure to avoid cross-border network congestion and optimize their Microsoft 365 service performance in China.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3717e-116">すべてのプライベート WAN 実装と同様に、ネットワーク構成が準拠していることを確認するために、国や地域の規制要件を常に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3717e-116">As with all private WAN implementations, you should always consult regulatory requirements for your country and/or region to ensure that your network configuration is in compliance.</span></span>

<span data-ttu-id="3717e-117">最初の手順として [、Microsoft 365](./network-planning-and-performance.md)のネットワーク計画とパフォーマンスチューニングのベンチマーク ネットワーク ガイダンスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3717e-117">As a first step, it is crucial that you follow our benchmark network guidance at [Network planning and performance tuning for Microsoft 365](./network-planning-and-performance.md).</span></span> <span data-ttu-id="3717e-118">主な目標は、可能であれば中国のインターネットからグローバル Microsoft 365 サービスにアクセスしないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="3717e-118">The primary goal should be to avoid accessing global Microsoft 365 services from the Internet in China if possible.</span></span>

- <span data-ttu-id="3717e-119">既存のプライベート ネットワークを活用して、中国のオフィス ネットワークと、中国外のパブリック インターネットに送信するオフショアの場所との間で Microsoft 365 ネットワーク トラフィックを伝送します。</span><span class="sxs-lookup"><span data-stu-id="3717e-119">Leverage your existing private network to carry Microsoft 365 network traffic between China office networks and offshore locations that egress on the public Internet outside China.</span></span> <span data-ttu-id="3717e-120">中国以外のほぼすべての場所が明確な利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="3717e-120">Almost any location outside China will provide a clear benefit.</span></span> <span data-ttu-id="3717e-121">ネットワーク管理者は、Microsoft グローバル ネットワークとの低遅延相互接続領域で出力することで、さらに [最適化できます](/azure/networking/microsoft-global-network)。</span><span class="sxs-lookup"><span data-stu-id="3717e-121">Network administrators can further optimize by egressing in areas with low-latency interconnect with the [Microsoft global network](/azure/networking/microsoft-global-network).</span></span> <span data-ttu-id="3717e-122">香港、日本、韓国が例です。</span><span class="sxs-lookup"><span data-stu-id="3717e-122">Hong Kong, Japan, and South Korea are examples.</span></span>
- <span data-ttu-id="3717e-123">VPN 接続を使用して企業ネットワークにアクセスするユーザー デバイスを構成して、Microsoft 365 トラフィックが企業ネットワークのプライベート オフショア リンクを通過できます。</span><span class="sxs-lookup"><span data-stu-id="3717e-123">Configure user devices to access the corporate network over a VPN connection to allow Microsoft 365 traffic to transit the corporate network's private offshore link.</span></span> <span data-ttu-id="3717e-124">VPN クライアントがスプリット トンネリングを使用するように構成されていないか、Microsoft 365 トラフィックの分割トンネリングを無視するようにユーザー デバイスが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3717e-124">Ensure that VPN clients are either not configured to use split tunneling, or that user devices are configured to ignore split tunneling for Microsoft 365 traffic.</span></span>
- <span data-ttu-id="3717e-125">すべての Microsoft 365 トラフィックをプライベートのオフショア リンクにルーティングするネットワークを構成します。</span><span class="sxs-lookup"><span data-stu-id="3717e-125">Configure your network to route all Microsoft 365 traffic across your private offshore link.</span></span> <span data-ttu-id="3717e-126">プライベート リンク上のトラフィックの量を最小限に抑える必要がある場合は、[最適化] カテゴリのエンドポイントのみをルーティングし、[許可]および[既定のエンドポイント] への要求でインターネットを中継できます。 </span><span class="sxs-lookup"><span data-stu-id="3717e-126">If you must minimize the volume of traffic on your private link, you can choose to only route endpoints in the **Optimize** category, and allow requests to **Allow** and **Default** endpoints to transit the Internet.</span></span> <span data-ttu-id="3717e-127">これにより、高遅延とパケット損失に最も敏感な重要なサービスに最適化されたトラフィックを制限することで、パフォーマンスを向上し、帯域幅の消費を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="3717e-127">This will improve performance and minimize bandwidth consumption by limiting optimized traffic to critical services that are most sensitive to high latency and packet loss.</span></span>
- <span data-ttu-id="3717e-128">可能であれば、Teams などのライブ メディア ストリーミング トラフィックに TCP の代わりに UDP を使用します。</span><span class="sxs-lookup"><span data-stu-id="3717e-128">If possible, use UDP instead of TCP for live media streaming traffic, such as for Teams.</span></span> <span data-ttu-id="3717e-129">UDP は、TCP よりも優れたライブ メディア ストリーミング パフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3717e-129">UDP offers better live media streaming performance than TCP.</span></span>

<span data-ttu-id="3717e-130">Microsoft 365 トラフィックを選択的にルーティングする方法については [、「365](managing-office-365-endpoints.md)エンドポイントの管理Officeを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3717e-130">For information about how to selectively route Microsoft 365 traffic, see [Managing Office 365 endpoints](managing-office-365-endpoints.md).</span></span> <span data-ttu-id="3717e-131">365 の URL と IP アドレスOfficeの一覧については [、「365](urls-and-ip-address-ranges.md)URL Office IP アドレス範囲」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3717e-131">For a list of all worldwide Office 365 URLs and IP addresses, see [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>

![Microsoft 365 トラフィック - 最適化](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a><span data-ttu-id="3717e-133">ユーザーのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3717e-133">User best practices</span></span>

<span data-ttu-id="3717e-134">企業ネットワークに接続できない家庭、喫茶店、ホテル、ブランチ オフィスなどのリモートの場所からグローバルな Microsoft 365 テナントに接続する中国のユーザーは、デバイスと Microsoft 365 間のトラフィックが中国の混雑したクロスボーダー ネットワーク回線を通過する必要があるため、ネットワークパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3717e-134">Users in China who connect to global Microsoft 365 tenants from remote locations such as homes, coffee shops, hotels and branch offices with no connection to enterprise networks can experience poor network performance because traffic between their devices and Microsoft 365 must transit China's congested cross-border network circuits.</span></span>

<span data-ttu-id="3717e-135">国境を越えたプライベート ネットワークや企業ネットワークへの VPN アクセスがオプションではない場合でも、中国に拠点を置くユーザーがこれらのベスト プラクティスに従うトレーニングを行って、ユーザーごとのパフォーマンスの問題を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="3717e-135">If cross-border private networks and/or VPN access into the corporate network are not an option, per-user performance issues can still be mitigated by training your China-based users to follow these best practices.</span></span>

- <span data-ttu-id="3717e-136">キャッシュをOfficeするリッチ クライアント (Outlook、Teams、OneDrive など) を利用し、Web ベースのクライアントを回避します。</span><span class="sxs-lookup"><span data-stu-id="3717e-136">Utilize rich Office clients that support caching (e.g. Outlook, Teams, OneDrive, etc.), and avoid web-based clients.</span></span> <span data-ttu-id="3717e-137">Officeキャッシュ機能とオフライン アクセス機能を使用すると、ネットワークの輻輳と待機時間の影響を大幅に軽減できます。</span><span class="sxs-lookup"><span data-stu-id="3717e-137">Office client caching and offline access features can dramatically reduce the impact of network congestion and latency.</span></span>
- <span data-ttu-id="3717e-138">Microsoft 365 テナントが電話会議機能で構成されている場合、Teams ユーザーは公衆交換電話網 (PSTN) を介して会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="3717e-138">If your Microsoft 365 tenant has been configured with the _Audio Conferencing_ feature, Teams users can join meetings via the public switched telephone network (PSTN).</span></span> <span data-ttu-id="3717e-139">詳細については、「電話会議 in [Office 365」を参照してください](/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="3717e-139">For more information, see [Audio Conferencing in Office 365](/microsoftteams/audio-conferencing-in-office-365).</span></span>
- <span data-ttu-id="3717e-140">ネットワーク パフォーマンスの問題が発生した場合は、トラブルシューティングのために IT 部門に報告し、Microsoft 365 サービスの問題が疑われる場合は Microsoft サポートにエスカレートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3717e-140">If users experience network performance issues, they should report to their IT department for troubleshooting, and escalate to Microsoft support if trouble with Microsoft 365 services is suspected.</span></span> <span data-ttu-id="3717e-141">一部の問題は、国境を越えたネットワークのパフォーマンスによって引き起こされるという問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="3717e-141">Not all issues are caused by cross-border network performance.</span></span>

<span data-ttu-id="3717e-142">Microsoft は、Microsoft 365 のユーザー エクスペリエンスと、可能な限り幅広いネットワーク アーキテクチャと特性に対するクライアントのパフォーマンスの向上に継続的に取り組み続け中です。</span><span class="sxs-lookup"><span data-stu-id="3717e-142">Microsoft is continually working to improve the Microsoft 365 user experience and the performance of clients over the widest possible range of network architectures and characteristics.</span></span> <span data-ttu-id="3717e-143">Office [365 Tech Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) にアクセスして、会話を開始または参加し、リソースを検索し、機能の要求と提案を送信します。</span><span class="sxs-lookup"><span data-stu-id="3717e-143">Visit the [Office 365 Tech Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) to start or join a conversation, find resources, and submit feature requests and suggestions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3717e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="3717e-144">Related topics</span></span>

[<span data-ttu-id="3717e-145">Microsoft 365 のネットワーク計画とパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="3717e-145">Network planning and performance tuning for Microsoft 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="3717e-146">Microsoft 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="3717e-146">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="3717e-147">Office 365 エンドポイントの管理</span><span class="sxs-lookup"><span data-stu-id="3717e-147">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="3717e-148">Office 365 の URL および IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="3717e-148">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="3717e-149">Microsoft グローバル ネットワーク</span><span class="sxs-lookup"><span data-stu-id="3717e-149">Microsoft global network</span></span>](/azure/networking/microsoft-global-network)