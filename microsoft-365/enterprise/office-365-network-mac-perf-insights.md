---
title: Microsoft 365ネットワーク インサイト (プレビュー)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365ネットワーク インサイト (プレビュー)
ms.openlocfilehash: ca665f4e492b071e5a387ffde0efae8336bd96bc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245782"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="2186a-103">Microsoft 365ネットワーク インサイト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2186a-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="2186a-104">**ネットワーク分析情報は**、Microsoft 365 テナントから収集されたパフォーマンス 指標であり、テナントの管理ユーザーだけが表示できます。</span><span class="sxs-lookup"><span data-stu-id="2186a-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="2186a-105">インサイトは、管理センターの Microsoft 365に表示されます <https://portal.microsoft.com/adminportal/home#/networkperformance> 。</span><span class="sxs-lookup"><span data-stu-id="2186a-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="2186a-106">インサイトは、オフィスの場所のネットワーク境界を設計する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2186a-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="2186a-107">各分析情報は、ユーザーがテナントにアクセスしている地理的な場所ごとに、特定の一般的な問題のパフォーマンス特性に関するライブの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="2186a-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="2186a-108">各オフィスの場所に表示される可能性がある 6 つの特定のネットワーク分析情報があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="2186a-109">バックホールされたネットワーク出力</span><span class="sxs-lookup"><span data-stu-id="2186a-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="2186a-110">ネットワーク仲介デバイス</span><span class="sxs-lookup"><span data-stu-id="2186a-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="2186a-111">近くの顧客に対して検出されるパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="2186a-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="2186a-112">サービス フロント ドアの最適Exchange Online使用</span><span class="sxs-lookup"><span data-stu-id="2186a-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="2186a-113">オンライン サービス フロント ドアSharePoint最適でないサービスの使用</span><span class="sxs-lookup"><span data-stu-id="2186a-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="2186a-114">フロント ドアからのダウンロードSharePoint速度が低い</span><span class="sxs-lookup"><span data-stu-id="2186a-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="2186a-115">中国ユーザーの最適なネットワーク出力</span><span class="sxs-lookup"><span data-stu-id="2186a-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="2186a-116">テナントには、2 つのテナント レベルのネットワーク分析情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="2186a-117">これらは生産性スコア ページにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="2186a-118">Exchangeの問題の影響を受け、サンプリングされた接続を確認する</span><span class="sxs-lookup"><span data-stu-id="2186a-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="2186a-119">SharePointの問題の影響を受け、サンプルされた接続を確認する</span><span class="sxs-lookup"><span data-stu-id="2186a-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="2186a-120">Microsoft 365 管理センターのネットワーク分析情報、パフォーマンスの推奨事項、評価は現在プレビュー状態であり、機能プレビュー プログラムに登録されている Microsoft 365 テナントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2186a-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="2186a-121">バックホールされたネットワーク出力</span><span class="sxs-lookup"><span data-stu-id="2186a-121">Backhauled network egress</span></span>

<span data-ttu-id="2186a-122">この分析情報は、ネットワーク インサイト サービスが、特定のユーザーの場所からネットワーク出力までの距離が 500 マイル (800 キロメートル) を超えると検出した場合に表示され、Microsoft 365 トラフィックが一般的なインターネット エッジ デバイスまたはプロキシにバックホールされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="2186a-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="2186a-123">この分析情報は、一部の概要ビュー Egress"」と省略されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2186a-124">![バックホールされたネットワーク出力](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="2186a-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-125">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-125">What does this mean?</span></span>

<span data-ttu-id="2186a-126">これは、オフィスの場所とネットワーク出力の間の距離が 500 マイル (800 キロメートル) を超える場合を識別します。</span><span class="sxs-lookup"><span data-stu-id="2186a-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="2186a-127">Office の場所は難読化されたクライアント コンピューターの場所によって識別され、ネットワーク出力の場所は、場所データベースへの逆 IP アドレスを使用して識別されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="2186a-128">コンピューターで Location Services が無効になっている場合Windowsオフィスの場所が不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="2186a-129">逆 IP アドレス データベース情報が不正確な場合、ネットワーク出力場所が不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="2186a-130">この分析情報の詳細には、オフィスの場所、現在のネットワーク出力場所、出力場所の関連性、場所と現在の出力ポイント間の距離、条件が最初に検出された日付、および条件が解決された日付の合計テナント ユーザーの推定割合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2186a-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-131">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-131">What should I do?</span></span>

<span data-ttu-id="2186a-132">この分析情報を得る場合は、ネットワーク出力をオフィスの場所に近づけて、接続を Microsoft のグローバル ネットワークと最も近いサービス フロント ドアに最適にルーティングMicrosoft 365勧めします。</span><span class="sxs-lookup"><span data-stu-id="2186a-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="2186a-133">また、ユーザーのオフィスの場所に近いネットワーク出力を使用すると、Microsoft が将来、プレゼンスのネットワーク ポイントと Microsoft 365 サービス フロント ドアの両方を拡張する中で、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="2186a-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="2186a-134">この問題を解決する方法の詳細については、「ネットワーク[](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)接続Egress」を参照Office 365[してください](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="2186a-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="2186a-135">ネットワーク仲介デバイス</span><span class="sxs-lookup"><span data-stu-id="2186a-135">Network intermediary device</span></span>

<span data-ttu-id="2186a-136">この分析情報は、ユーザーと Microsoft のネットワークの間でデバイスが検出され、ユーザー エクスペリエンスの向上に影響を与Office 365表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="2186a-137">Microsoft データセンター宛ての特定のネットワーク トラフィックMicrosoft 365バイパスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="2186a-138">この推奨事項については、「ネットワーク接続[の原則Microsoft 365」で説明します](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="2186a-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="2186a-139">Exchange、SharePoint、Teams の重要な Office 365 ネットワーク エンドポイントがネットワーク仲介デバイスによって傍受および復号化された場合の SSL ブレークとインスペクションが示されているネットワーク仲介の分析情報の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="2186a-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-140">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-140">What does this mean?</span></span>

<span data-ttu-id="2186a-141">プロキシ サーバー、VPN、データ損失防止デバイスなどのネットワーク仲介デバイスは、トラフィックが中間的な Microsoft 365 クライアントのパフォーマンスと安定性に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-142">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-142">What should I do?</span></span>

<span data-ttu-id="2186a-143">ネットワーク トラフィックの処理をバイパスするために検出されたネットワーク仲介Microsoft 365構成します。</span><span class="sxs-lookup"><span data-stu-id="2186a-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="2186a-144">近くの顧客に対して検出されるパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="2186a-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="2186a-145">この分析情報は、ネットワーク インサイト サービスが、このオフィスの場所にある組織内のユーザーよりも、メトロエリアのかなりの数の顧客のパフォーマンスが優れたと検出した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="2186a-146">この分析情報は、一部の概要ビューで "Peers" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2186a-147">![相対ネットワークパフォーマンス](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="2186a-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-148">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-148">What does this mean?</span></span>

<span data-ttu-id="2186a-149">この分析情報は、このオフィスの場所と同Microsoft 365顧客の集計パフォーマンスを調べる。</span><span class="sxs-lookup"><span data-stu-id="2186a-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="2186a-150">この分析情報は、ユーザーの平均待機時間が隣接テナントの平均待機時間より 10% 大きい場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-151">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-151">What should I do?</span></span>

<span data-ttu-id="2186a-152">この状態には、企業ネットワークまたは ISP の待機時間、ボトルネック、アーキテクチャ設計の問題など、多くの理由が考え得る。</span><span class="sxs-lookup"><span data-stu-id="2186a-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="2186a-153">Office ネットワークと現在のネットワーク間のルート内の各ホップ間の待機時間をMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="2186a-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="2186a-154">詳細については、「ネットワーク接続[Microsoft 365」を参照してください](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="2186a-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="2186a-155">サービス フロント ドアの最適Exchange Online使用</span><span class="sxs-lookup"><span data-stu-id="2186a-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="2186a-156">この分析情報は、ネットワーク インサイト サービスが、特定の場所のユーザーが最適なサービス フロント ドアに接続Exchange Online場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="2186a-157">この分析情報は、一部の概要ビューでは "ルーティング" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2186a-158">![最適ではない EXO フロント ドア](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="2186a-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-159">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-159">What does this mean?</span></span>

<span data-ttu-id="2186a-160">優れたパフォーマンスExchange Onlineオフィスの場所から使用に適したサービス フロント ドアの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2186a-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="2186a-161">現在のテストで、このリストに含Exchange Onlineサービス フロント ドアの使用が示されている場合は、この推奨事項を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2186a-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-162">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-162">What should I do?</span></span>

<span data-ttu-id="2186a-163">サービス フロント ドアに最適でない Exchange Onlineを使用すると、企業のネットワーク出力の前にネットワーク バックホールが発生する可能性があります。その場合は、ローカルおよび直接のネットワーク出力をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2186a-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="2186a-164">また、リモート DNS 再帰的リゾルバー サーバーを使用した場合、DNS 再帰的リゾルバー サーバーをネットワーク出力に合わせて配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2186a-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="2186a-165">オンライン サービス フロント ドアSharePoint最適でないサービスの使用</span><span class="sxs-lookup"><span data-stu-id="2186a-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="2186a-166">この分析情報は、ネットワーク インサイト サービスが、特定の場所のユーザーが Online サービスのフロント ドアに最も近いユーザーに接続SharePoint場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="2186a-167">この分析情報は、一部の概要ビューで "Afd" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2186a-168">![最適でない SPO フロント ドア](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="2186a-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-169">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-169">What does this mean?</span></span>

<span data-ttu-id="2186a-170">テスト クライアントがSharePointしているオンライン サービスのフロント ドアを特定します。</span><span class="sxs-lookup"><span data-stu-id="2186a-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="2186a-171">次に、オフィスの場所の都市について、その都市のSharePointオンライン サービスのフロント ドアと比較します。</span><span class="sxs-lookup"><span data-stu-id="2186a-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="2186a-172">一致しない場合は、この推奨事項を作成します。</span><span class="sxs-lookup"><span data-stu-id="2186a-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-173">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-173">What should I do?</span></span>

<span data-ttu-id="2186a-174">最適ではないネットワーク SharePoint サービス フロント ドアの使用は、企業のネットワーク出力の前にネットワーク バックホールが発生する可能性があります。その場合は、ローカルおよび直接のネットワーク出力をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2186a-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="2186a-175">また、リモート DNS 再帰的リゾルバー サーバーを使用した場合、DNS 再帰的リゾルバー サーバーをネットワーク出力に合わせて配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2186a-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="2186a-176">フロント ドアからのダウンロードSharePoint速度が低い</span><span class="sxs-lookup"><span data-stu-id="2186a-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="2186a-177">この分析情報は、ネットワーク インサイト サービスが、特定のオフィスの場所とオンライン間の帯域幅が 1 MBps 未満SharePoint検出した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="2186a-178">この分析情報は、一部の概要ビューで "スループット" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-179">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-179">What does this mean?</span></span>

<span data-ttu-id="2186a-180">ユーザーがオンラインおよび SharePoint および OneDrive for Business から取得できるダウンロード速度は、1 秒あたりのメガバイト (MBps) 単位で測定されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="2186a-181">この値が 1 MBps 未満の場合は、この分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2186a-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-182">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-182">What should I do?</span></span>

<span data-ttu-id="2186a-183">ダウンロード速度を向上させるために、帯域幅を増やす必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="2186a-184">または、オフィスの場所でユーザー コンピューターとオンライン サービスのフロント ドアSharePointネットワークの混雑が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="2186a-185">これは、混雑損失と呼ばれる場合があります。十分な帯域幅が利用可能な場合でも、ユーザーが利用できるダウンロード速度が制限されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="2186a-186">中国ユーザーの最適なネットワーク出力</span><span class="sxs-lookup"><span data-stu-id="2186a-186">China user optimal network egress</span></span>

<span data-ttu-id="2186a-187">この分析情報は、中国のユーザーが他の地理的な場所Microsoft 365に接続している場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-188">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-188">What does this mean?</span></span>

<span data-ttu-id="2186a-189">組織にプライベート WAN 接続がある場合は、次の場所でインターネットへのネットワーク出力を持つ中国のオフィスの場所からネットワーク WAN 回線を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2186a-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="2186a-190">香港特別行政区</span><span class="sxs-lookup"><span data-stu-id="2186a-190">Hong Kong</span></span>
- <span data-ttu-id="2186a-191">日本</span><span class="sxs-lookup"><span data-stu-id="2186a-191">Japan</span></span>
- <span data-ttu-id="2186a-192">台湾</span><span class="sxs-lookup"><span data-stu-id="2186a-192">Taiwan</span></span>
- <span data-ttu-id="2186a-193">韓国</span><span class="sxs-lookup"><span data-stu-id="2186a-193">South Korea</span></span>
- <span data-ttu-id="2186a-194">シンガポール</span><span class="sxs-lookup"><span data-stu-id="2186a-194">Singapore</span></span>
- <span data-ttu-id="2186a-195">マレーシア</span><span class="sxs-lookup"><span data-stu-id="2186a-195">Malaysia</span></span>

<span data-ttu-id="2186a-196">これらの場所よりもユーザーから遠く離れたインターネット出力はパフォーマンスを低下させるので、中国の出力は国境を越えた混雑のために高い遅延と接続の問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-197">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-197">What should I do?</span></span>

<span data-ttu-id="2186a-198">この分析情報に関連するパフォーマンスの問題を軽減する方法の詳細については、「中国のユーザー Microsoft 365のパフォーマンスの最適化」を[参照してください](microsoft-365-networking-china.md)。</span><span class="sxs-lookup"><span data-stu-id="2186a-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="2186a-199">Exchangeの問題の影響を受け、サンプリングされた接続を確認する</span><span class="sxs-lookup"><span data-stu-id="2186a-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="2186a-200">この分析情報は、サンプリングされた接続の 50% 以上が影響を受け取る場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="2186a-201">影響は、サンプルごとに 60% 未満Exchange評価によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-202">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-202">What does this mean?</span></span>

<span data-ttu-id="2186a-203">これは、ユーザーの大半が、ユーザーに接続するユーザーエクスペリエンスの問題が発生している可能性が高Outlook示Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2186a-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="2186a-204">サンプルの割合は、60 ポイントを下回るユーザーの割合を表している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-205">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-205">What should I do?</span></span>

<span data-ttu-id="2186a-206">オフィスの場所ネットワーク接続の可視性を有効にする (まだ有効にしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="2186a-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="2186a-207">Exchange に影響を与えるネットワーク接続の不十分な影響を受け、ユーザーを Microsoft のネットワークに接続する各オフィスでネットワーク境界を改善する方法を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="2186a-208">SharePointの問題の影響を受け、サンプルされた接続を確認する</span><span class="sxs-lookup"><span data-stu-id="2186a-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="2186a-209">この分析情報は、サンプリングされた接続の 50% 以上が影響を受け取る場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="2186a-210">影響は、各サンプルSharePoint 40% 未満の評価によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2186a-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="2186a-211">シナリオ</span><span class="sxs-lookup"><span data-stu-id="2186a-211">What does this mean?</span></span>

<span data-ttu-id="2186a-212">これは、ユーザーの大半が、ユーザーエクスペリエンスの問題が発生している可能性が高SharePoint示OneDrive。</span><span class="sxs-lookup"><span data-stu-id="2186a-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="2186a-213">サンプルの割合は、40 ポイントを下回るユーザーの割合を表している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="2186a-214">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2186a-214">What should I do?</span></span>

<span data-ttu-id="2186a-215">オフィスの場所ネットワーク接続の可視性を有効にする (まだ有効にしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="2186a-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="2186a-216">SharePoint に影響を与えるネットワーク接続の不十分な影響を受け、ユーザーを Microsoft のネットワークに接続する各オフィスでネットワーク境界を改善する方法を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2186a-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2186a-217">関連項目</span><span class="sxs-lookup"><span data-stu-id="2186a-217">Related topics</span></span>

[<span data-ttu-id="2186a-218">管理センターでのネットワークMicrosoft 365 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2186a-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="2186a-219">Microsoft 365評価 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2186a-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="2186a-220">Microsoft 365接続テスト ツール (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2186a-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="2186a-221">Microsoft 365ネットワーク接続位置情報サービス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2186a-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
