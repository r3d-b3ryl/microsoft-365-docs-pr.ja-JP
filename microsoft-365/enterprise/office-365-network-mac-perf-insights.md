---
title: Microsoft 365 Network Insights (プレビュー)
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
description: Microsoft 365 Network Insights (プレビュー)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055475"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="cbc27-103">Microsoft 365 Network Insights (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cbc27-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="cbc27-104">**ネットワークインサイトは** 、Microsoft 365 テナントから収集されたパフォーマンスメトリックであり、テナント内の管理ユーザーだけが表示できます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="cbc27-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="cbc27-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="cbc27-106">インサイトは、オフィスの場所のネットワーク境界の設計に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="cbc27-107">各インサイトは、ユーザーがテナントにアクセスしている地理的な場所ごとに、特定の一般的な問題のパフォーマンス特性に関するライブの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="cbc27-108">オフィスごとに 6 つの特定のネットワークインサイトが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="cbc27-109">バックホールされたネットワークエグレス</span><span class="sxs-lookup"><span data-stu-id="cbc27-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="cbc27-110">ネットワーク中継デバイス</span><span class="sxs-lookup"><span data-stu-id="cbc27-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="cbc27-111">近くの顧客に対して検出されたパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="cbc27-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="cbc27-112">最適でない Exchange Online サービスフロント ドアの使用</span><span class="sxs-lookup"><span data-stu-id="cbc27-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="cbc27-113">最適でない SharePoint Online サービスのフロント ドアの使用</span><span class="sxs-lookup"><span data-stu-id="cbc27-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="cbc27-114">SharePoint フロント ドアからのダウンロード速度が低い</span><span class="sxs-lookup"><span data-stu-id="cbc27-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="cbc27-115">中国のユーザー最適なネットワークエグレス</span><span class="sxs-lookup"><span data-stu-id="cbc27-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="cbc27-116">テナントには、2 つのテナント レベルのネットワークインサイトが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="cbc27-117">これらは、生産的スコア ページにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="cbc27-118">接続の問題の影響を受け、Exchange のサンプル接続</span><span class="sxs-lookup"><span data-stu-id="cbc27-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="cbc27-119">接続の問題の影響を受け、SharePoint のサンプル接続</span><span class="sxs-lookup"><span data-stu-id="cbc27-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="cbc27-120">Microsoft 365 管理センターのネットワークの分析情報、パフォーマンスに関する推奨事項、評価は現在プレビュー状態であり、機能プレビュー プログラムに登録されている Microsoft 365 テナントでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="cbc27-121">バックホールされたネットワークエグレス</span><span class="sxs-lookup"><span data-stu-id="cbc27-121">Backhauled network egress</span></span>

<span data-ttu-id="cbc27-122">この分析情報は、ネットワークインサイト サービスが、特定のユーザーの場所からネットワーク出口までの距離が 500 マイル (800 km) を超えると検出した場合に表示されます。これは、Microsoft 365 トラフィックが共通のインターネット エッジ デバイスまたはプロキシにバックホール中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="cbc27-123">このインサイトは、一部の概要ビューでは "エグレス" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![バックホールされたネットワークエグレス](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-125">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-125">What does this mean?</span></span>

<span data-ttu-id="cbc27-126">これは、オフィスの場所とネットワーク出口の間の距離が 500 マイル (800 キロメートル) を超える距離を表します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="cbc27-127">オフィスの場所は難読化されたクライアント コンピューターの場所によって識別され、ネットワーク出口の場所は、場所データベースへの逆 IP アドレスを使用して識別されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="cbc27-128">コンピューターで Windows 位置情報サービスが無効になっていると、オフィスの場所が不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="cbc27-129">逆 IP アドレス データベース情報が不正確な場合は、ネットワーク出口の場所が不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="cbc27-130">このインサイトの詳細には、オフィスの場所、その場所のテナント ユーザーの推定割合、現在のネットワーク出口の場所、出口の場所の関連性、場所と現在の出口ポイントの間の距離、条件が最初に検出された日付、条件が解決された日付が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-131">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-131">What should I do?</span></span>

<span data-ttu-id="cbc27-132">この洞察のために、接続が Microsoft のグローバル ネットワークと最も近い Microsoft 365 サービスのフロント ドアに最適にルーティングできるよう、オフィスの場所に近いネットワーク出口をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbc27-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="cbc27-133">ユーザーのオフィスの場所に近いネットワーク出口を用意することで、Microsoft が今後、プレゼンスのネットワーク ポイントと Microsoft 365 サービス フロント ドアの両方を拡張する中で、今後のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="cbc27-134">この問題を解決する方法の詳細については、「Office [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) [365 Network Connectivity Principles」](microsoft-365-network-connectivity-principles.md)の「ネットワーク接続をローカルに送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbc27-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="cbc27-135">ネットワーク中継デバイス</span><span class="sxs-lookup"><span data-stu-id="cbc27-135">Network intermediary device</span></span>

<span data-ttu-id="cbc27-136">この分析情報は、ユーザーと Microsoft のネットワークの間でデバイスが検出され、Office 365 のユーザー エクスペリエンスに影響を与える可能性がある場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="cbc27-137">これらは、Microsoft データセンター宛ての特定の Microsoft 365 ネットワーク トラフィックに対してバイパスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbc27-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="cbc27-138">この推奨事項については [、Microsoft 365 ネットワーク接続の原則でさらに説明されています。](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="cbc27-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-139">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-139">What does this mean?</span></span>

<span data-ttu-id="cbc27-140">プロキシ サーバー、VPN、データ損失防止デバイスなどのネットワーク中継デバイスは、トラフィックが中間的に使用される Microsoft 365 クライアントのパフォーマンスと安定性に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-141">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-141">What should I do?</span></span>

<span data-ttu-id="cbc27-142">Microsoft 365 ネットワーク トラフィックの処理をバイパスするために検出されたネットワーク中継デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="cbc27-143">近くの顧客に対して検出されたパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="cbc27-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="cbc27-144">この分析情報は、ネットワークインサイト サービスが、このオフィスの場所にある組織内のユーザーよりも、多数の顧客が施設エリア内のユーザーのパフォーマンスが優れたと検出した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="cbc27-145">この分析情報は、一部の概要ビューでは "ピア" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![相対的なネットワーク パフォーマンス](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-147">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-147">What does this mean?</span></span>

<span data-ttu-id="cbc27-148">この分析情報は、このオフィスの場所と同じ市にある Microsoft 365 ユーザーの集計パフォーマンスを調べています。</span><span class="sxs-lookup"><span data-stu-id="cbc27-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="cbc27-149">この分析情報は、ユーザーの平均待機時間が、隣接するテナントの平均待機時間よりも 10% 長い場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-150">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-150">What should I do?</span></span>

<span data-ttu-id="cbc27-151">この状態には、企業ネットワークまたは ISP の待機時間、ボトルネック、アーキテクチャ設計の問題など、さまざまな理由が考えらたはずです。</span><span class="sxs-lookup"><span data-stu-id="cbc27-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="cbc27-152">オフィス ネットワークと現在の Microsoft 365 フロント ドア間のルートの各ホップ間の遅延を調べる。</span><span class="sxs-lookup"><span data-stu-id="cbc27-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="cbc27-153">詳細については [、「Microsoft 365 Network Connectivity Principles」を参照してください](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc27-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="cbc27-154">最適でない Exchange Online サービスフロント ドアの使用</span><span class="sxs-lookup"><span data-stu-id="cbc27-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="cbc27-155">この分析情報は、ネットワークインサイト サービスが、特定の場所のユーザーが最適な Exchange Online サービスのフロント ドアに接続していないと検出した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="cbc27-156">この分析情報は、一部の概要ビューでは "ルーティング" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![最適でない EXO フロント ドア](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-158">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-158">What does this mean?</span></span>

<span data-ttu-id="cbc27-159">優れたパフォーマンスを備え、オフィス所在地の都市からの使用に適した Exchange Online サービスフロント ドアの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="cbc27-160">現在のテストで、このリストに記載されていない Exchange Online サービスのフロント ドアの使用が示されている場合は、この推奨事項を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-161">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-161">What should I do?</span></span>

<span data-ttu-id="cbc27-162">最適でない Exchange Online サービスのフロント ドアの使用は、企業のネットワーク出口の前のネットワーク バックホールが原因で発生する可能性があります。その場合は、ローカルおよび直接のネットワークエグレスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbc27-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="cbc27-163">また、リモート DNS 再帰リゾルバー サーバーの使用が原因で発生する可能性もあります。この場合、DNS 再帰リゾルバー サーバーをネットワーク出口に合わせて配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbc27-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="cbc27-164">最適でない SharePoint Online サービスのフロント ドアの使用</span><span class="sxs-lookup"><span data-stu-id="cbc27-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="cbc27-165">この分析情報は、ネットワークインサイト サービスが、特定の場所のユーザーが最も近い SharePoint Online サービスのフロント ドアに接続していないと検出した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="cbc27-166">この分析情報は、一部の概要ビューでは "Afd" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![最適でない SPO フロント ドア](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-168">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-168">What does this mean?</span></span>

<span data-ttu-id="cbc27-169">テスト クライアントが接続している SharePoint Online サービスのフロント ドアを特定します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="cbc27-170">次に、オフィスの場所の都市について、その都市の予想される SharePoint Online サービスのフロント ドアと比較します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="cbc27-171">一致しない場合は、この推奨事項を作成します。</span><span class="sxs-lookup"><span data-stu-id="cbc27-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-172">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-172">What should I do?</span></span>

<span data-ttu-id="cbc27-173">最適でない SharePoint Online サービスのフロント ドアの使用は、企業ネットワーク出口の前のネットワーク バックホールが原因で発生する可能性があります。その場合は、ローカルおよび直接のネットワークエグレスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbc27-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="cbc27-174">また、リモート DNS 再帰リゾルバー サーバーの使用が原因で発生する可能性もあります。この場合、DNS 再帰リゾルバー サーバーをネットワーク出口に合わせて配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbc27-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="cbc27-175">SharePoint フロント ドアからのダウンロード速度が低い</span><span class="sxs-lookup"><span data-stu-id="cbc27-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="cbc27-176">この分析情報は、ネットワークインサイト サービスが、特定のオフィスの場所と SharePoint Online 間の帯域幅が 1 MBps 未満を検出した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="cbc27-177">この分析情報は、一部の概要ビューでは "スループット" と省略されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-178">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-178">What does this mean?</span></span>

<span data-ttu-id="cbc27-179">ユーザーが SharePoint Online および OneDrive for Business サービスフロント ドアから取得できるダウンロード速度は、メガバイト/秒 (MBps) 単位で測定されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="cbc27-180">この値が 1 MBps 未満の場合は、この分析情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-181">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-181">What should I do?</span></span>

<span data-ttu-id="cbc27-182">ダウンロード速度を向上させるために、帯域幅を増やす必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="cbc27-183">または、オフィスの場所にあるユーザー コンピューターと SharePoint Online サービスのフロント ドアの間でネットワークの混雑が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="cbc27-184">これは、混雑した損失と呼ばれる場合があります。また、十分な帯域幅が利用可能な場合でも、ユーザーが利用できるダウンロード速度が制限されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="cbc27-185">中国のユーザー最適なネットワークエグレス</span><span class="sxs-lookup"><span data-stu-id="cbc27-185">China user optimal network egress</span></span>

<span data-ttu-id="cbc27-186">この分析情報は、中国のユーザーが他の地理的な場所にある Microsoft 365 テナントに接続している場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-187">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-187">What does this mean?</span></span>

<span data-ttu-id="cbc27-188">組織にプライベート WAN 接続がある場合は、次の場所のインターネットへのネットワークエグレスがある中国のオフィスの場所からネットワーク WAN 回線を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbc27-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="cbc27-189">香港特別行政区</span><span class="sxs-lookup"><span data-stu-id="cbc27-189">Hong Kong</span></span>
- <span data-ttu-id="cbc27-190">日本</span><span class="sxs-lookup"><span data-stu-id="cbc27-190">Japan</span></span>
- <span data-ttu-id="cbc27-191">台湾</span><span class="sxs-lookup"><span data-stu-id="cbc27-191">Taiwan</span></span>
- <span data-ttu-id="cbc27-192">韓国</span><span class="sxs-lookup"><span data-stu-id="cbc27-192">South Korea</span></span>
- <span data-ttu-id="cbc27-193">シンガポール</span><span class="sxs-lookup"><span data-stu-id="cbc27-193">Singapore</span></span>
- <span data-ttu-id="cbc27-194">マレーシア</span><span class="sxs-lookup"><span data-stu-id="cbc27-194">Malaysia</span></span>

<span data-ttu-id="cbc27-195">これらの場所よりもユーザーから離れた場所にインターネットエグレスを使用すると、パフォーマンスが低下し、中国の出口では、境界を越えた輻輳のために待ち時間が長く接続の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-196">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-196">What should I do?</span></span>

<span data-ttu-id="cbc27-197">このインサイトに関連するパフォーマンスの問題を軽減する方法の詳細については、中国ユーザー向け [Microsoft 365 グローバル](microsoft-365-networking-china.md)テナントのパフォーマンスの最適化を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbc27-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="cbc27-198">接続の問題の影響を受け、Exchange のサンプル接続</span><span class="sxs-lookup"><span data-stu-id="cbc27-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="cbc27-199">この分析情報は、サンプリングされた接続の 50% 以上が影響を受け取る場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="cbc27-200">影響は、Exchange 評価がサンプルごとに 60% 未満であることによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-201">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-201">What does this mean?</span></span>

<span data-ttu-id="cbc27-202">これは、ユーザーの大部分が Exchange Online に接続する Outlook でユーザー エクスペリエンスの問題が発生している可能性が高いことを示しています。</span><span class="sxs-lookup"><span data-stu-id="cbc27-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="cbc27-203">サンプルの割合は、60 ポイントを下回るユーザーの割合を表している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-204">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-204">What should I do?</span></span>

<span data-ttu-id="cbc27-205">まだ有効にしていない場合は、オフィスの場所のネットワーク接続の可視性を有効にする。</span><span class="sxs-lookup"><span data-stu-id="cbc27-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="cbc27-206">Exchange に影響を与えるネットワーク接続の不十分な影響を受け、ユーザーを Microsoft のネットワークに接続する各オフィスでネットワーク境界を改善する方法を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="cbc27-207">接続の問題の影響を受け、SharePoint のサンプル接続</span><span class="sxs-lookup"><span data-stu-id="cbc27-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="cbc27-208">この分析情報は、サンプリングされた接続の 50% 以上が影響を受け取る場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="cbc27-209">影響は、SharePoint 評価がサンプルごとに 40% 未満であることによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="cbc27-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="cbc27-210">シナリオ</span><span class="sxs-lookup"><span data-stu-id="cbc27-210">What does this mean?</span></span>

<span data-ttu-id="cbc27-211">これは、ユーザーの大部分が SharePoint と OneDrive でユーザー エクスペリエンスの問題を経験している可能性が高いことを示しています。</span><span class="sxs-lookup"><span data-stu-id="cbc27-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="cbc27-212">サンプルの割合は、40 ポイントを下回るユーザーの割合を表している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="cbc27-213">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="cbc27-213">What should I do?</span></span>

<span data-ttu-id="cbc27-214">まだ有効にしていない場合は、オフィスの場所のネットワーク接続の可視性を有効にする。</span><span class="sxs-lookup"><span data-stu-id="cbc27-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="cbc27-215">SharePoint に影響を与える低品質ネットワーク接続の影響を受け、ユーザーを Microsoft のネットワークに接続する各オフィスでネットワーク境界を改善する方法を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbc27-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cbc27-216">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbc27-216">Related topics</span></span>

[<span data-ttu-id="cbc27-217">Microsoft 365 管理センターでのネットワーク接続 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cbc27-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="cbc27-218">Microsoft 365 ネットワーク評価 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cbc27-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="cbc27-219">Microsoft 365 ネットワーク接続テスト ツール (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cbc27-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="cbc27-220">Microsoft 365 Network Connectivity Location Services (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cbc27-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
