---
title: Microsoft 365 Network Insights (プレビュー)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
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
ms.openlocfilehash: a9d4dbde112c9b6c74e340824c63ce2b9749e80e
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948518"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="24f20-103">Microsoft 365 Network Insights (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="24f20-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="24f20-104">**Network insights** は、Microsoft 365 テナントから収集されたパフォーマンス指標で、テナントの管理ユーザーのみが参照できます。</span><span class="sxs-lookup"><span data-stu-id="24f20-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="24f20-105">Insights は、Microsoft 365 管理センターのに表示され <https://portal.microsoft.com/adminportal/home#/networkperformance> ます。</span><span class="sxs-lookup"><span data-stu-id="24f20-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="24f20-106">Insights は、オフィスの場所のネットワーク境界を設計するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="24f20-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="24f20-107">各洞察では、ユーザーがテナントにアクセスする地理的な場所ごとに、特定の一般的な問題のパフォーマンス特性に関するライブ詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="24f20-108">各オフィスの場所には、次の6つの特定のネットワーク洞察が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="24f20-109">Backhauled ネットワークの出口</span><span class="sxs-lookup"><span data-stu-id="24f20-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="24f20-110">近距離のお客様のためのパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="24f20-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="24f20-111">Exchange Online サービスのフロントドアの非最適な使用</span><span class="sxs-lookup"><span data-stu-id="24f20-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="24f20-112">最適ではない SharePoint Online サービスのフロントドアの使用</span><span class="sxs-lookup"><span data-stu-id="24f20-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="24f20-113">SharePoint フロントドアからのダウンロード速度が低い</span><span class="sxs-lookup"><span data-stu-id="24f20-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="24f20-114">中国ユーザーにとって最適なネットワークの出口</span><span class="sxs-lookup"><span data-stu-id="24f20-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="24f20-115">テナントには、2つのテナントレベルのネットワーク洞察が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="24f20-116">これらは、次のように、本番 viて y スコアページにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="24f20-117">接続の問題によって影響を受ける Exchange のサンプリングされる接続</span><span class="sxs-lookup"><span data-stu-id="24f20-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="24f20-118">接続の問題によって影響を受ける SharePoint のサンプリングされる接続</span><span class="sxs-lookup"><span data-stu-id="24f20-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="24f20-119">Network insights、Microsoft 365 Admin Center でのパフォーマンスに関する推奨事項と評価は現在プレビュー状態であり、機能プレビュープログラムに登録されている Microsoft 365 テナントに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="24f20-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="24f20-120">Backhauled ネットワークの出口</span><span class="sxs-lookup"><span data-stu-id="24f20-120">Backhauled network egress</span></span>

<span data-ttu-id="24f20-121">Network insights service が、特定のユーザーの場所からネットワークの出口までの距離が500マイル (800 km) よりも大きいことを検出した場合に、この洞察が表示されます。これは、Microsoft 365 トラフィックが共通のインターネットエッジデバイスまたはプロキシに backhauled されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="24f20-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="24f20-122">この洞察は、一部の要約ビューで "出口" として短縮されています。</span><span class="sxs-lookup"><span data-stu-id="24f20-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Backhauled ネットワークの出口](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="24f20-124">シナリオ</span><span class="sxs-lookup"><span data-stu-id="24f20-124">What does this mean?</span></span>

<span data-ttu-id="24f20-125">これは、オフィスの場所とネットワーク出口との間の距離が500マイル (800 km) を超えていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="24f20-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="24f20-126">Office の場所は難読化されたクライアントコンピューターの場所で識別され、ネットワークの出口の場所は、逆引き IP アドレスを使用して場所データベースに識別されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="24f20-127">Windows ロケーションサービスがコンピューターで無効になっている場合は、office の場所が不正確になることがあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="24f20-128">逆引き IP アドレスデータベースの情報が正確でない場合は、ネットワークの出口の場所が不正確になることがあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="24f20-129">この洞察の詳細には、オフィスの場所、現在のネットワーク出口の位置、出口位置の関連性、位置と現在の出口ポイント間の距離、条件が最初に検出された日付、および条件が解決された日付が含まれます。</span><span class="sxs-lookup"><span data-stu-id="24f20-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="24f20-130">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="24f20-130">What should I do?</span></span>

<span data-ttu-id="24f20-131">この情報については、office の場所へのネットワーク出口をお勧めします。これにより、接続が Microsoft のグローバルネットワークおよび最寄りの Microsoft 365 service フロントドアに最適にルーティングされるようになります。</span><span class="sxs-lookup"><span data-stu-id="24f20-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="24f20-132">また、ユーザーのオフィスの場所に対してネットワークを閉じることにより、将来的に、Microsoft がネットワークポイントプレゼンスと Microsoft 365 サービスのフロントドアの両方を展開した場合にもパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="24f20-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="24f20-133">この問題を解決する方法の詳細については、「 [Office 365 のネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)」の「[ネットワーク接続をローカル](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)に出力する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f20-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="24f20-134">近距離のお客様のためのパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="24f20-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="24f20-135">この洞察は、このオフィスの場所にある組織のユーザーに比べて、メトロエリア内の多数の顧客の方がパフォーマンスが優れていることを network insights service が検出した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="24f20-136">この洞察は、一部の概要ビューでは "ピア" として短縮されています。</span><span class="sxs-lookup"><span data-stu-id="24f20-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![ネットワークの相対パフォーマンス](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="24f20-138">シナリオ</span><span class="sxs-lookup"><span data-stu-id="24f20-138">What does this mean?</span></span>

<span data-ttu-id="24f20-139">この洞察は、このオフィスの場所と同じ都市にある Microsoft 365 の顧客の総合的なパフォーマンスを調査します。</span><span class="sxs-lookup"><span data-stu-id="24f20-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="24f20-140">この洞察は、ユーザーの平均待機時間が近隣テナントの平均待機時間を10% 上回る場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="24f20-141">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="24f20-141">What should I do?</span></span>

<span data-ttu-id="24f20-142">この条件には、企業ネットワークまたは ISP の待機時間、ボトルネック、アーキテクチャ設計上の問題など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="24f20-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="24f20-143">Office ネットワークと現在の Microsoft 365 フロントドア間のルートで、各ホップ間の待機時間を調べます。</span><span class="sxs-lookup"><span data-stu-id="24f20-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="24f20-144">詳細については、「 [Office 365 のネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f20-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="24f20-145">Exchange Online サービスのフロントドアの非最適な使用</span><span class="sxs-lookup"><span data-stu-id="24f20-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="24f20-146">ネットワークインサイト内のユーザーが、最適な Exchange Online サービスのフロントドアに接続されていないことを検出した場合、この洞察が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="24f20-147">この洞察は、一部の概要ビューに "ルーティング" として短縮されています。</span><span class="sxs-lookup"><span data-stu-id="24f20-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![非最適なフロントドア](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="24f20-149">シナリオ</span><span class="sxs-lookup"><span data-stu-id="24f20-149">What does this mean?</span></span>

<span data-ttu-id="24f20-150">適切なパフォーマンスを備えた、office の場所の都市からの使用に適した Exchange Online サービスのフロントドアをリストしています。</span><span class="sxs-lookup"><span data-stu-id="24f20-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="24f20-151">現在のテストで、この一覧にない Exchange Online サービスのフロントドアの使用が示されている場合は、この推奨事項を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="24f20-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="24f20-152">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="24f20-152">What should I do?</span></span>

<span data-ttu-id="24f20-153">Exchange Online サービスのフロントドアを使用していない場合は、企業ネットワークの出口の前にネットワークのバックアウトが原因で、ローカルと直接のネットワーク出口が推奨されることがあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="24f20-154">また、リモート DNS の再帰リゾルバーサーバーを使用して、DNS の再帰リゾルバーサーバーをネットワークの出口に配置することが推奨される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="24f20-155">最適ではない SharePoint Online サービスのフロントドアの使用</span><span class="sxs-lookup"><span data-stu-id="24f20-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="24f20-156">ネットワーク insights サービスが、特定の場所にいるユーザーが最も近い SharePoint Online サービスのフロントドアに接続していないことを検出した場合、この洞察が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="24f20-157">この洞察は、一部の要約ビューでは "Afd" と略記されています。</span><span class="sxs-lookup"><span data-stu-id="24f20-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![非最適なフロントドア](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="24f20-159">シナリオ</span><span class="sxs-lookup"><span data-stu-id="24f20-159">What does this mean?</span></span>

<span data-ttu-id="24f20-160">テストクライアントが接続している SharePoint Online サービスのフロントドアを特定します。</span><span class="sxs-lookup"><span data-stu-id="24f20-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="24f20-161">次に、オフィスの所在地の市区町村に対して、その都市に対して予想される SharePoint Online サービスのフロントドアと比較します。</span><span class="sxs-lookup"><span data-stu-id="24f20-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="24f20-162">一致しない場合は、この推奨事項を行います。</span><span class="sxs-lookup"><span data-stu-id="24f20-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="24f20-163">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="24f20-163">What should I do?</span></span>

<span data-ttu-id="24f20-164">最適でない SharePoint Online サービスのフロントドアの使用は、企業ネットワークの出口の前にネットワークバックが発生した場合に発生することがあります。これは、ローカルおよび直接ネットワークを出口にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24f20-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="24f20-165">また、リモート DNS の再帰リゾルバーサーバーを使用して、DNS の再帰リゾルバーサーバーをネットワークの出口に配置することが推奨される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="24f20-166">SharePoint フロントドアからのダウンロード速度が低い</span><span class="sxs-lookup"><span data-stu-id="24f20-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="24f20-167">Network insights service が、特定のオフィスの場所と SharePoint Online の間の帯域幅が 1 MBps 未満であることを検出すると、この洞察が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="24f20-168">この洞察は、一部の要約ビューで "スループット" と短縮されています。</span><span class="sxs-lookup"><span data-stu-id="24f20-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="24f20-169">シナリオ</span><span class="sxs-lookup"><span data-stu-id="24f20-169">What does this mean?</span></span>

<span data-ttu-id="24f20-170">ユーザーが SharePoint Online と OneDrive for business サービスのフロントドアから取得できるダウンロード速度は、1秒あたりのメガバイト数 (MBps) で測定されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="24f20-171">この値が 1 Mb 未満の場合は、この洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="24f20-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="24f20-172">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="24f20-172">What should I do?</span></span>

<span data-ttu-id="24f20-173">ダウンロード速度を向上させるには、帯域幅を増やす必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="24f20-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="24f20-174">または、オフィスの場所と SharePoint Online サービスのフロントドアで、ユーザーのコンピューター間にネットワークの輻輳が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="24f20-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="24f20-175">これは、congestive 損失とも呼ばれ、十分な帯域幅が利用可能な場合でも、ユーザーが使用できるダウンロード速度を制限します。</span><span class="sxs-lookup"><span data-stu-id="24f20-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="24f20-176">中国ユーザーにとって最適なネットワークの出口</span><span class="sxs-lookup"><span data-stu-id="24f20-176">China user optimal network egress</span></span>

<span data-ttu-id="24f20-177">この洞察は、中国のユーザーが他の地理的な場所にある Microsoft 365 テナントに接続している場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="24f20-178">シナリオ</span><span class="sxs-lookup"><span data-stu-id="24f20-178">What does this mean?</span></span>

<span data-ttu-id="24f20-179">組織のプライベート WAN 接続がある場合は、次のいずれかの場所でインターネットへのネットワーク出口を備えた中国のオフィスの場所からネットワーク WAN 回線を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24f20-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="24f20-180">香港特別行政区</span><span class="sxs-lookup"><span data-stu-id="24f20-180">Hong Kong</span></span>
- <span data-ttu-id="24f20-181">日本</span><span class="sxs-lookup"><span data-stu-id="24f20-181">Japan</span></span>
- <span data-ttu-id="24f20-182">台湾</span><span class="sxs-lookup"><span data-stu-id="24f20-182">Taiwan</span></span>
- <span data-ttu-id="24f20-183">韓国</span><span class="sxs-lookup"><span data-stu-id="24f20-183">South Korea</span></span>
- <span data-ttu-id="24f20-184">シンガポール</span><span class="sxs-lookup"><span data-stu-id="24f20-184">Singapore</span></span>
- <span data-ttu-id="24f20-185">マレーシア</span><span class="sxs-lookup"><span data-stu-id="24f20-185">Malaysia</span></span>

<span data-ttu-id="24f20-186">このような場所を超えるユーザーからのインターネット出口はパフォーマンスを低下させ、中国での出口によって、クロスボーダー輻輳が発生して遅延と接続の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="24f20-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="24f20-187">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="24f20-187">What should I do?</span></span>

<span data-ttu-id="24f20-188">この洞察に関連するパフォーマンスの問題を軽減する方法の詳細については、「 [Office 365 グローバルテナントパフォーマンスの最適化 (中国ユーザー向け](microsoft-365-networking-china.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f20-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="24f20-189">接続の問題によって影響を受ける Exchange のサンプリングされる接続</span><span class="sxs-lookup"><span data-stu-id="24f20-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="24f20-190">この洞察は、サンプリングされた接続の50% 以上が影響を受けたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="24f20-191">この影響は、各サンプルの Exchange 評価が60% 以下になることによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="24f20-192">シナリオ</span><span class="sxs-lookup"><span data-stu-id="24f20-192">What does this mean?</span></span>

<span data-ttu-id="24f20-193">ユーザーの大部分が Outlook を Exchange Online に接続しているときに、ユーザーの問題が発生している可能性があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="24f20-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="24f20-194">サンプルのパーセンテージは、60ポイントを下回っているユーザーの割合を表すことがあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="24f20-195">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="24f20-195">What should I do?</span></span>

<span data-ttu-id="24f20-196">まだ実行していない場合は、office の場所のネットワーク接続の表示を有効にします。</span><span class="sxs-lookup"><span data-stu-id="24f20-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="24f20-197">Exchange に影響を与えるネットワーク接続の問題が impactred ているオフィスを特定し、ユーザーを Microsoft のネットワークに接続するそれぞれのネットワーク境界を改善する方法を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f20-197">You want to identify which offices are impactred by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="24f20-198">接続の問題によって影響を受ける SharePoint のサンプリングされる接続</span><span class="sxs-lookup"><span data-stu-id="24f20-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="24f20-199">この洞察は、サンプリングされた接続の50% 以上が影響を受けたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f20-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="24f20-200">各サンプルでは、SharePoint の評価が40% 未満であるという影響が定義されています。</span><span class="sxs-lookup"><span data-stu-id="24f20-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="24f20-201">シナリオ</span><span class="sxs-lookup"><span data-stu-id="24f20-201">What does this mean?</span></span>

<span data-ttu-id="24f20-202">多くのユーザーが SharePoint および OneDrive でユーザー環境に問題が発生している可能性があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="24f20-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="24f20-203">サンプルのパーセンテージは、40ポイントを下回っているユーザーの割合を表すことがあります。</span><span class="sxs-lookup"><span data-stu-id="24f20-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="24f20-204">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="24f20-204">What should I do?</span></span>

<span data-ttu-id="24f20-205">まだ実行していない場合は、office の場所のネットワーク接続の表示を有効にします。</span><span class="sxs-lookup"><span data-stu-id="24f20-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="24f20-206">SharePoint に影響を与えるネットワーク接続の不足によって impactred されているオフィスを特定し、ユーザーを Microsoft のネットワークに接続するそれぞれのネットワーク境界を改善する方法を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f20-206">You want to identify which offices are impactred by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="24f20-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="24f20-207">Related topics</span></span>

[<span data-ttu-id="24f20-208">Microsoft 365 管理センター (プレビュー) でのネットワークパフォーマンスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="24f20-208">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="24f20-209">Microsoft 365 ネットワーク評価 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="24f20-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="24f20-210">M365 管理センターでの Microsoft 365 の接続テスト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="24f20-210">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="24f20-211">Microsoft 365 ネットワーク接続ロケーションサービス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="24f20-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
