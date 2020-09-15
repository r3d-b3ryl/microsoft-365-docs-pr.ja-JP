---
title: Microsoft 365 ネットワーク接続テスト (プレビュー)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/14/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 ネットワーク接続テスト (プレビュー)
ms.openlocfilehash: 92bd850c98261df1808219ee1f28c75da370d443
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650024"
---
# <a name="microsoft-365-network-connectivity-test-preview"></a><span data-ttu-id="8d091-103">Microsoft 365 ネットワーク接続テスト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8d091-103">Microsoft 365 network connectivity test (preview)</span></span>

<span data-ttu-id="8d091-104">Microsoft 365 ネットワーク接続テストツールは、にあり <https://connectivity.office.com> ます。</span><span class="sxs-lookup"><span data-stu-id="8d091-104">The Microsoft 365 network connectivity test tool is located at <https://connectivity.office.com>.</span></span> <span data-ttu-id="8d091-105">これは、Microsoft 365 管理センターで利用可能なネットワーク評価およびネットワーク insights 情報に対する adjunct ツールであり、正常性の下にあります。 **[接続** ] メニュー</span><span class="sxs-lookup"><span data-stu-id="8d091-105">It is an adjunct tool to the network assessment and network insights information available in the Microsoft 365 admin center under the **Health | Connectivity** menu.</span></span>

>[!NOTE]
><span data-ttu-id="8d091-106">ネットワーク接続テストツールは、世界各地の商用およびドイツのテナントをサポートしていますが、GCC のモデレート、GCC High、DoD、中国ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8d091-106">The network connectivity test tool supports tenants in WW Commercial and Germany but not GCC Moderate, GCC High, DoD or China.</span></span>

<span data-ttu-id="8d091-107">Microsoft 365 管理センターのネットワーク insights は、毎日集計される Microsoft 365 テナントの正規の製品の測定基準に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8d091-107">The network insights in the Microsoft 365 Admin Center are based on regular in-product measurements for your Microsoft 365 tenant which are aggregated each day.</span></span> <span data-ttu-id="8d091-108">これに対して、Microsoft 365 ネットワーク接続テストのネットワーク洞察は、ツールでローカルおよび1回実行されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-108">In comparison, the network insights from the Microsoft 365 network connectivity test are run locally and one time in the tool.</span></span> <span data-ttu-id="8d091-109">製品内で実行できるテストは制限されており、ユーザーに対してローカルにテストを実行することにより、より深い洞察を得られるように収集できます。</span><span class="sxs-lookup"><span data-stu-id="8d091-109">Testing that can be done in-product is limited and by running tests local to the user more data can be gathered resulting in deeper insights.</span></span> <span data-ttu-id="8d091-110">次に、Microsoft 365 管理センターの network insights は、特定のオフィスの場所で Microsoft 365 を使用するためのネットワークの問題があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8d091-110">Consider then that the network insights in the Microsoft 365 Admin Center will show that there is a networking problem for use of Microsoft 365 at a specific office location.</span></span> <span data-ttu-id="8d091-111">Microsoft 365 connectivity test は、この問題の根本的な原因を特定するのに役立ち、推奨されるネットワークパフォーマンスの向上アクションを導きます。</span><span class="sxs-lookup"><span data-stu-id="8d091-111">The Microsoft 365 connectivity test can help to identify the root cause of that problem leading to a recommended network performance improvement action.</span></span>

<span data-ttu-id="8d091-112">Microsoft 365 管理センターの各オフィスの場所についてネットワーク品質の状態を評価し、Microsoft 365 の接続テストに基づいてテストを展開した後は、より多くの情報を見つけられるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d091-112">We recommend that these be used together where networking quality status can be assessed for each office location in the Microsoft 365 Admin Center and more specifics can be found after deployment of testing based on the Microsoft 365 connectivity test.</span></span>

>[!IMPORTANT]
><span data-ttu-id="8d091-113">Network insights、Microsoft 365 Admin Center でのパフォーマンスに関する推奨事項と評価は現在プレビュー状態であり、機能プレビュープログラムに登録されている Microsoft 365 テナントに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d091-113">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="the-advanced-tests-client-application"></a><span data-ttu-id="8d091-114">高度なテストクライアントアプリケーション</span><span class="sxs-lookup"><span data-stu-id="8d091-114">The advanced tests client application</span></span>

<span data-ttu-id="8d091-115">Microsoft 365 ネットワーク接続テストには2つの部分があります。web サイト <https://connectivity.office.com> と、高度なネットワーク接続テストを実行するダウンロード可能な Windows クライアントアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="8d091-115">There are two parts to the Microsoft 365 network connectivity test; the web site <https://connectivity.office.com> and a downloadable Windows client application that runs advanced network connectivity tests.</span></span> <span data-ttu-id="8d091-116">ほとんどのテストでは、アプリケーションが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-116">Most of the tests require the application to be run.</span></span> <span data-ttu-id="8d091-117">実行時に、結果が web ページに返されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-117">It will populate results back into the web page as it runs.</span></span>

<span data-ttu-id="8d091-118">Web ブラウザーテストが完了した後、web サイトからアドバンストクライアントテストアプリケーションをダウンロードするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-118">You will be prompted to download the advanced client test application from the web site after the web browser tests have completed.</span></span> <span data-ttu-id="8d091-119">メッセージが表示されたら、ファイルを開いて実行します。</span><span class="sxs-lookup"><span data-stu-id="8d091-119">Open and run the file when prompted.</span></span>

![高度なテストクライアントアプリケーション](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

## <a name="sharing-your-test-report"></a><span data-ttu-id="8d091-121">テストレポートを共有する</span><span class="sxs-lookup"><span data-stu-id="8d091-121">Sharing your test report</span></span>

<span data-ttu-id="8d091-122">テストレポートには、Office 365 アカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-122">The test report requires sign-in to your Office 365 account.</span></span> <span data-ttu-id="8d091-123">テストレポートを共有する方法は、管理者が選択します。</span><span class="sxs-lookup"><span data-stu-id="8d091-123">Your administrator selects how you can share your test report.</span></span>

### <a name="sharing-your-report-with-your-administrator"></a><span data-ttu-id="8d091-124">管理者とレポートを共有する</span><span class="sxs-lookup"><span data-stu-id="8d091-124">Sharing your report with your administrator</span></span>

<span data-ttu-id="8d091-125">サインインしているすべてのテストレポートは、管理者と共有されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-125">All test reports while you are signed in are shared with your administrator.</span></span>

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a><span data-ttu-id="8d091-126">Microsoft アカウントチーム、サポート、またはその他の担当者との共有</span><span class="sxs-lookup"><span data-stu-id="8d091-126">Sharing with your Microsoft account team, support or other personnel</span></span>

<span data-ttu-id="8d091-127">個人 id を除くテストレポートは、Microsoft の従業員と共有されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-127">Test reports excluding any personal identification are shared with Microsoft employees.</span></span> <span data-ttu-id="8d091-128">これは既定で有効になっており、管理者が正常性で無効にすることができます。 **Health | Network Connectivity**Microsoft 365 管理センターの [ネットワーク接続] ページ</span><span class="sxs-lookup"><span data-stu-id="8d091-128">This is enabled by default and can be disabled by your administrator in the **Health | Network Connectivity** page in the Microsoft 365 Admin Center.</span></span>

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a><span data-ttu-id="8d091-129">同じ Office 365 テナントにサインインしている他のユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="8d091-129">Sharing with other users who sign in to the same Office 365 tenant</span></span>

<span data-ttu-id="8d091-130">レポートを共有するユーザーを選択できます。これは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8d091-130">You can choose users to share your report with and this is enabled by default.</span></span> <span data-ttu-id="8d091-131">また、管理者が無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8d091-131">It can also be disabled by your administrator.</span></span>

![テスト結果へのリンクをユーザーと共有する](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a><span data-ttu-id="8d091-133">ReportID リンクを使用したすべてのユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="8d091-133">Sharing with anyone using a ReportID link</span></span>

<span data-ttu-id="8d091-134">報告 Tid リンクへのアクセスを提供することにより、テストレポートを任意のユーザーと共有することができます。</span><span class="sxs-lookup"><span data-stu-id="8d091-134">You can share your test report with anyone by providing access to a ReportID link.</span></span> <span data-ttu-id="8d091-135">これにより、ユーザーに送信できる URL が生成され、サインインせずにテストレポートを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8d091-135">This generates a URL that you can send to someone so that they can bring up the test report without signing in.</span></span> <span data-ttu-id="8d091-136">これは既定で無効になっており、管理者が有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-136">This is disabled by default and must be enabled by your administrator.</span></span>

![テスト結果へのリンクの共有](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a><span data-ttu-id="8d091-138">ネットワーク接続テストの結果</span><span class="sxs-lookup"><span data-stu-id="8d091-138">Network Connectivity Test Results</span></span>

<span data-ttu-id="8d091-139">結果は [ **概要** ] タブと [ **詳細** ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-139">The results are shown in the **Summary** and **Details** tabs.</span></span> <span data-ttu-id="8d091-140">[概要] タブには、検出されたネットワーク境界のマップと、近くにある他の Office 365 お客様とのネットワーク評価の比較が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-140">The summary tab shows a map of the detected network perimeter and a comparison of the network assessment to other Office 365 customers nearby.</span></span> <span data-ttu-id="8d091-141">テストレポートを共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d091-141">It also allows for sharing of the test report.</span></span> <span data-ttu-id="8d091-142">概要結果ビューは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8d091-142">Here's what the summary results view looks like.</span></span>

![ネットワーク接続テストツールの概要結果](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

<span data-ttu-id="8d091-144">このツールで表示される [詳細] タブの出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-144">Here is an example of the details tab output that the tool shows.</span></span> <span data-ttu-id="8d091-145">[詳細] タブでは、結果が favorably をしきい値と比較した場合は、緑色の円チェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-145">On the details tab we show a green circle check mark if the result was compared favorably to a threshold.</span></span> <span data-ttu-id="8d091-146">結果がネットワークの洞察を示すしきい値を超えた場合は、赤い三角形の感嘆符が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-146">We show a red triangle exclamation point if the result exceeded a threshold indicating a network insight.</span></span> <span data-ttu-id="8d091-147">次のセクションでは、[詳細] タブの各結果行について説明し、ネットワークインサイトで使用されるしきい値について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d091-147">The following sections describe each of the details tab results rows and explains the thresholds used for network insights.</span></span>

![テスト結果の例のネットワーク接続テストツール](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a><span data-ttu-id="8d091-149">場所情報</span><span class="sxs-lookup"><span data-stu-id="8d091-149">Your location information</span></span>

<span data-ttu-id="8d091-150">ここでは、自分の場所に関連するテスト結果を示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-150">This section shows test results related to your location.</span></span>

#### <a name="your-location"></a><span data-ttu-id="8d091-151">自分の場所</span><span class="sxs-lookup"><span data-stu-id="8d091-151">Your location</span></span>

<span data-ttu-id="8d091-152">ユーザーの場所は、ユーザーの web ブラウザーから検出されるか、ユーザーの選択で入力できます。</span><span class="sxs-lookup"><span data-stu-id="8d091-152">The user location is detected from the users web browser, or it can be typed in at the users choice.</span></span> <span data-ttu-id="8d091-153">これは、企業ネットワーク境界の特定の部分に対するネットワークの距離を特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-153">It is used to identify network distances to specific parts of the enterprise network perimeter.</span></span> <span data-ttu-id="8d091-154">この場所を検出した市区町村のみがレポートに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-154">Only the city from this location detection and the distance to other network points are saved in the report.</span></span>

<span data-ttu-id="8d091-155">ユーザーのオフィスの場所がマップビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-155">The user office location is shown on the map view.</span></span>

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a><span data-ttu-id="8d091-156">ネットワークの出口の場所 (ネットワークが ISP に接続する場所)</span><span class="sxs-lookup"><span data-stu-id="8d091-156">Network egress location (the location where your network connects to your ISP)</span></span>

<span data-ttu-id="8d091-157">サーバー側のネットワーク出口 IP アドレスを特定します。</span><span class="sxs-lookup"><span data-stu-id="8d091-157">We identify the network egress IP address on the server side.</span></span> <span data-ttu-id="8d091-158">場所データベースは、ネットワーク出口のおおよその場所を検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-158">Location databases are used to look up the approximate location for the network egress.</span></span> <span data-ttu-id="8d091-159">これらのデータベースでは、通常、IP アドレスの約90% の精度があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-159">These databases typically have an accuracy of about 90% of IP addresses.</span></span> <span data-ttu-id="8d091-160">ネットワークの出口 IP アドレスから検索された場所が正確でない場合は、このテストの結果が false になります。</span><span class="sxs-lookup"><span data-stu-id="8d091-160">If the location looked up from the network egress IP address is not accurate then this would lead to a false result from this test.</span></span> <span data-ttu-id="8d091-161">特定の IP アドレスに対してこのエラーが発生しているかどうかを検証するには、パブリックにアクセス可能なネットワークの IP アドレスの場所 web サイトを使用して、実際の場所と比較することができます。</span><span class="sxs-lookup"><span data-stu-id="8d091-161">To validate if this error is occurring for a specific IP address you can use publicly accessible network IP address location web sites to compare to your actual location.</span></span>

#### <a name="your-distance-from-the-network-egress-location"></a><span data-ttu-id="8d091-162">ネットワークの出口位置からの距離</span><span class="sxs-lookup"><span data-stu-id="8d091-162">Your distance from the network egress location</span></span>

<span data-ttu-id="8d091-163">その場所からオフィスの場所までの距離を決定します。</span><span class="sxs-lookup"><span data-stu-id="8d091-163">We determine the distance from that location to the office location.</span></span> <span data-ttu-id="8d091-164">これは、距離が **500 マイル** (800 km) を超える場合に、TCP の待機時間が25ミリ秒を超える可能性があり、ユーザーの利便性に影響する可能性があるため、ネットワークの洞察として示されています。</span><span class="sxs-lookup"><span data-stu-id="8d091-164">This is shown as a network insight if the distance is greater than **500 miles** (800 kilometers) since that is likely to increase the TCP latency by more than 25ms and may affect user experience.</span></span>

<span data-ttu-id="8d091-165">ネットワークの出口の場所がマップビューに表示され、エンタープライズ WAN 内部のネットワークバックを示す、ユーザーのオフィスの場所に接続されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-165">The network egress location is shown on the map view and connected to the user office location indicating the network backhaul inside of the enterprise WAN.</span></span>

<span data-ttu-id="8d091-166">Microsoft 365 のネットワーク接続には、ユーザーのオフィスの場所からインターネットへのローカルおよび直接ネットワーク出口を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d091-166">Implementing local and direct network egress from user office locations to the Internet is recommended for Microsoft 365 network connectivity.</span></span> <span data-ttu-id="8d091-167">このネットワークの洞察に対処するための最善の方法は、ローカルおよび直接出口に対する機能強化です。</span><span class="sxs-lookup"><span data-stu-id="8d091-167">Improvements to local and direct egress are the best way to address this network insight.</span></span>

#### <a name="proxy-server-information"></a><span data-ttu-id="8d091-168">プロキシサーバー情報</span><span class="sxs-lookup"><span data-stu-id="8d091-168">Proxy server information</span></span>

<span data-ttu-id="8d091-169">ローカルコンピューターで構成されているプロキシサーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="8d091-169">We identify proxy server(s) configured on the local machine.</span></span> <span data-ttu-id="8d091-170">最適化カテゴリの Microsoft 365 ネットワークトラフィックで、これらのいずれかが構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d091-170">We identify if any of these are configured in the network path for optimize category Microsoft 365 network traffic.</span></span> <span data-ttu-id="8d091-171">ユーザーのオフィスの場所からプロキシサーバーへの距離を特定します。</span><span class="sxs-lookup"><span data-stu-id="8d091-171">We identify the distance from the user office location to the proxy servers.</span></span> <span data-ttu-id="8d091-172">この距離は、最初に ICMP ping によってテストされ、失敗した場合は TCP ping を使用してテストを実行して失敗した場合は、IP アドレスの場所データベースでプロキシサーバーの IP アドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="8d091-172">The distance is tested first by ICMP ping and if that fails we test with TCP ping and finally if that fails we look up the proxy server IP Address in an IP Address location database.</span></span> <span data-ttu-id="8d091-173">プロキシサーバーが、ユーザーのオフィスの場所から **500 マイル** (800 km) を超える場合は、ネットワークの洞察を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d091-173">We show a network insight if the proxy server is further than **500 miles** (800 kilometers) away from the user office location.</span></span>

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a><span data-ttu-id="8d091-174">組織に接続するために使用する仮想プライベートネットワーク (VPN)</span><span class="sxs-lookup"><span data-stu-id="8d091-174">Virtual private network (VPN) you use to connect to your organization</span></span>

<span data-ttu-id="8d091-175">これは、VPN を使用して Office 365 に接続しているかどうかを検出します。</span><span class="sxs-lookup"><span data-stu-id="8d091-175">This detects if you are using a VPN to connect to Office 365.</span></span> <span data-ttu-id="8d091-176">VPN を使用していない場合、または Office 365 に対して推奨される分割トンネル構成を備えた VPN がある場合は、合格の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-176">A passing result will show if you have no VPN, or if you have a VPN with recommended split tunnel configuration for Office 365.</span></span>

#### <a name="vpn-split-tunnel"></a><span data-ttu-id="8d091-177">VPN 分割トンネル</span><span class="sxs-lookup"><span data-stu-id="8d091-177">VPN Split Tunnel</span></span>

<span data-ttu-id="8d091-178">Exchange Online、SharePoint Online、Microsoft Teams の各最適化カテゴリルートは、VPN で tunnelled されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="8d091-178">Each optimize category route for Exchange Online, SharePoint Online, and Microsoft Teams is tested to see if it is tunnelled on the VPN or not.</span></span> <span data-ttu-id="8d091-179">ワークロードの分割は、VPN 全体を回避します。</span><span class="sxs-lookup"><span data-stu-id="8d091-179">A split out workload avoids the VPN entirely.</span></span> <span data-ttu-id="8d091-180">Tunnelled ワークロードは、すべて VPN 経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-180">A tunnelled workload is all sent over the VPN.</span></span> <span data-ttu-id="8d091-181">選択的 tunnelled ワークロードには、VPN 経由で送信されるいくつかのルートと一部が切り離されています。すべてのワークロードがスプリットアウトまたは選択的 tunnelled であるかどうかを示す結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-181">A selective tunnelled workload has some routes sent over the VPN and some split out. A passing result will show if all workloads are split out or selective tunnelled.</span></span>

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a><span data-ttu-id="8d091-182">優れたパフォーマンスを備えた大都市圏のお客様</span><span class="sxs-lookup"><span data-stu-id="8d091-182">Customers in your metropolitan area with better performance</span></span>

<span data-ttu-id="8d091-183">Exchange Online サービスのフロントドアに対するユーザーのオフィスの場所のネットワーク TCP 遅延が、同じメトロエリアにある他の Microsoft 365 ユーザーと比較されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-183">The network TCP latency of the user office location to the Exchange Online service front door is compared to other Microsoft 365 customers in the same metro area.</span></span> <span data-ttu-id="8d091-184">同じメトロエリア内の10% 以上のお客様がパフォーマンスが優れている場合は、ネットワークの洞察が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-184">A network insight is shown if 10% or more of customers in the same metro area have better performance.</span></span> <span data-ttu-id="8d091-185">これは、Microsoft 365 ユーザーインターフェイスでユーザーのパフォーマンスが向上することを意味します。</span><span class="sxs-lookup"><span data-stu-id="8d091-185">This means their users will have better performance in the Microsoft 365 user interface.</span></span>

<span data-ttu-id="8d091-186">このネットワークの洞察は、1つの都市内のすべてのユーザーが同じ通信インフラストラクチャにアクセスできることと、インターネット回線および Microsoft のネットワークとの距離に応じて生成されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-186">This network insight is generated on the basis that all users in a city have access to the same telecommunications infrastructure and the same proximity to Internet circuits and Microsoft's network.</span></span>

#### <a name="time-to-make-a-dns-request-on-your-network"></a><span data-ttu-id="8d091-187">ネットワークで DNS 要求を行う時間</span><span class="sxs-lookup"><span data-stu-id="8d091-187">Time to make a DNS request on your network</span></span>

<span data-ttu-id="8d091-188">これは、テストを実行したクライアントコンピューター上に構成された DNS サーバーを示しています。</span><span class="sxs-lookup"><span data-stu-id="8d091-188">This shows the DNS server configured on the client machine that ran the tests.</span></span> <span data-ttu-id="8d091-189">DNS 再帰リゾルバーサーバーの場合もありますが、これは一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="8d091-189">It might be a DNS Recursive Resolver server however this is uncommon.</span></span> <span data-ttu-id="8d091-190">Dns フォワーダーサーバーは、DNS の結果をキャッシュし、キャッシュされていない DNS 要求を別の DNS サーバーに転送する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="8d091-190">It is more likely to be a DNS forwarder server which caches DNS results and forwards any uncached DNS requests to another DNS server.</span></span>

<span data-ttu-id="8d091-191">これは情報のみを対象として提供されており、ネットワークに関する洞察には影響しません。</span><span class="sxs-lookup"><span data-stu-id="8d091-191">This is provided for information only and does not contribute to any network insight.</span></span>

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a><span data-ttu-id="8d091-192">DNS の再帰的なリゾルバーに接続する、または時刻からの距離</span><span class="sxs-lookup"><span data-stu-id="8d091-192">Your distance from and/or time to connect to a DNS recursive resolver</span></span>

<span data-ttu-id="8d091-193">使用中の DNS 再帰リゾルバーは、特定の DNS 要求を作成し、同じ要求を受信した IP アドレスに対して DNS ネームサーバーに要求することで識別されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-193">The in-use DNS Recursive Resolver is identified by making a specific DNS request and then asking the DNS Name Server for the IP Address that it received the same request from.</span></span> <span data-ttu-id="8d091-194">この IP アドレスは、DNS の再帰的なリゾルバーです。これは、IP アドレスの場所のデータベースで検索され、場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="8d091-194">This IP Address is the DNS Recursive Resolver and it will be looked up in IP Address location databases to find the location.</span></span> <span data-ttu-id="8d091-195">その後、ユーザーのオフィスの場所から DNS の再帰的なリゾルバーサーバーの場所までの距離が計算されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-195">The distance from the user office location to the DNS Recursive Resolver server location is then calculated.</span></span> <span data-ttu-id="8d091-196">これは、距離が **500 マイル** (800 km) を超える場合にネットワークの洞察として表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-196">This is shown as a network insight if the distance is greater than **500 miles** (800 kilometers).</span></span>

<span data-ttu-id="8d091-197">ネットワーク出力 IP アドレスから検索された場所が正確でない可能性があるため、このテストからの結果が false になることがあります。</span><span class="sxs-lookup"><span data-stu-id="8d091-197">The location looked up from the network egress IP Address may not be accurate and this would lead to a false result from this test.</span></span> <span data-ttu-id="8d091-198">特定の IP アドレスに対してこのエラーが発生しているかどうかを検証するには、パブリックにアクセス可能なネットワーク IP アドレスの場所 web サイトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d091-198">To validate if this error is occurring for a specific IP Address you can use publicly accessible network IP Address location web sites.</span></span>

<span data-ttu-id="8d091-199">このネットワークの洞察は、Exchange Online サービスのフロントドアの選択に特に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="8d091-199">This network insight will specifically impact the selection of the Exchange Online service front door.</span></span> <span data-ttu-id="8d091-200">この洞察に対応するために、ローカルおよび直接ネットワークからの出口を指定する必要があります。その後、DNS 再帰リゾルバーは、そのネットワーク出口の近くに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-200">To address this insight local and direct network egress should be a pre-requisite and then DNS Recursive Resolver should be located close to that network egress.</span></span>

### <a name="exchange-online"></a><span data-ttu-id="8d091-201">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8d091-201">Exchange Online</span></span>

<span data-ttu-id="8d091-202">このセクションでは、Exchange Online に関連するテスト結果を示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-202">This section shows test results related to Exchange Online.</span></span>

#### <a name="exchange-service-front-door-location"></a><span data-ttu-id="8d091-203">Exchange サービスのフロントドアの場所</span><span class="sxs-lookup"><span data-stu-id="8d091-203">Exchange service front door location</span></span>

<span data-ttu-id="8d091-204">使用中の Exchange サービスのフロントドアは、Outlook と同じ方法で識別され、ユーザーの場所からのネットワーク TCP 遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="8d091-204">The in-use Exchange service front door is identified in the same way that Outlook does this and we measure the network TCP latency from the user location to it.</span></span> <span data-ttu-id="8d091-205">TCP の遅延が表示され、使用中の Exchange サービスのフロントドアが、現在の場所のサービスのトップドアのリストと比較されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-205">The TCP latency is shown and the in-use Exchange service front door is compared to the list of best service front doors for the current location.</span></span> <span data-ttu-id="8d091-206">最適な Exchange サービスのフロントドアのいずれかが使用されていない場合は、ネットワークの洞察として表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-206">This is shown as a network insight if one of the best Exchange service front door(s) is not in use.</span></span>

<span data-ttu-id="8d091-207">最適な Exchange サービスフロントドアのいずれかを使用しない場合は、企業ネットワークの出口の前にネットワークバックアウトが発生することがあります。これは、ローカルおよび直接ネットワークを出口にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d091-207">Not using one of the best Exchange service front door(s) could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="8d091-208">また、リモート DNS の再帰リゾルバーサーバーを使用して、DNS の再帰リゾルバーサーバーをネットワークの出口に配置することが推奨される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8d091-208">It could also be caused by use of a remote DNS recursive resolver server in which case we recommend aligning the DNS recursive resolver server with the network egress.</span></span>

<span data-ttu-id="8d091-209">Exchange サービスのフロントドアに対する TCP の遅延 (ms) の向上の可能性を計算します。</span><span class="sxs-lookup"><span data-stu-id="8d091-209">We calculate a potential improvement in TCP latency (ms) to the Exchange service front door.</span></span> <span data-ttu-id="8d091-210">これを行うには、テストされたユーザーのオフィスの場所のネットワーク待ち時間を調べて、現在の場所から closets Exchange サービスのフロントドアまで、ネットワークの待機時間を減算します。</span><span class="sxs-lookup"><span data-stu-id="8d091-210">This is done by looking at the tested user office location network latency and subtracting the network latency from the current location to the closets Exchange service front door.</span></span> <span data-ttu-id="8d091-211">違いは、改善につながる可能性がある機会を表します。</span><span class="sxs-lookup"><span data-stu-id="8d091-211">The difference represents the potential opportunity for improvement.</span></span>

#### <a name="best-exchange-service-front-doors-for-your-location"></a><span data-ttu-id="8d091-212">自分の場所に最適な Exchange サービスのフロントドア</span><span class="sxs-lookup"><span data-stu-id="8d091-212">Best Exchange service front door(s) for your location</span></span>

<span data-ttu-id="8d091-213">これにより、場所に応じた、Exchange サービスのフロントドアの最適な位置が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-213">This lists the best Exchange service front door locations by city for your location.</span></span>

#### <a name="service-front-door-recorded-in-the-client-dns"></a><span data-ttu-id="8d091-214">クライアント DNS に記録されたサービスのフロントドア</span><span class="sxs-lookup"><span data-stu-id="8d091-214">Service front door recorded in the client DNS</span></span>

<span data-ttu-id="8d091-215">これには、移動先の Exchange サービスのフロントドアサーバーの DNS 名と IP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-215">This shows the DNS name and IP Address of the Exchange service front door server that you were directed to.</span></span> <span data-ttu-id="8d091-216">これは情報のみを対象として提供されており、関連するネットワークの洞察がありません。</span><span class="sxs-lookup"><span data-stu-id="8d091-216">It is provided for information only and there is no associated network insight.</span></span>

### <a name="sharepoint-online"></a><span data-ttu-id="8d091-217">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8d091-217">SharePoint Online</span></span>

<span data-ttu-id="8d091-218">このセクションでは、SharePoint Online と OneDrive に関連するテスト結果を示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-218">This section shows test results related to SharePoint Online and OneDrive.</span></span>

#### <a name="the-service-front-door-location"></a><span data-ttu-id="8d091-219">サービスのフロントドアの場所</span><span class="sxs-lookup"><span data-stu-id="8d091-219">The service front door location</span></span>

<span data-ttu-id="8d091-220">使用中の SharePoint サービスのフロントドアは、OneDrive クライアントと同じ方法で識別され、ユーザーのオフィスの場所からのネットワーク TCP 遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="8d091-220">The in-use SharePoint service front door is identified in the same way that the OneDrive client does and we measure the network TCP latency from the user office location to it.</span></span>

#### <a name="download-speed"></a><span data-ttu-id="8d091-221">ダウンロード速度</span><span class="sxs-lookup"><span data-stu-id="8d091-221">Download speed</span></span>

<span data-ttu-id="8d091-222">SharePoint サービスのフロントドアから、15Mb ファイルのダウンロード速度を測定します。</span><span class="sxs-lookup"><span data-stu-id="8d091-222">We measure the download speed for a 15Mb file from the SharePoint service front door.</span></span> <span data-ttu-id="8d091-223">結果はメガバイト/秒で表示され、 **1 秒**間に SharePoint または OneDrive からダウンロードできるサイズファイルのサイズを示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-223">The result is shown in megabytes per second to indicate what size file in megabytes can be downloaded from SharePoint or OneDrive in **one second**.</span></span> <span data-ttu-id="8d091-224">この数は、少なくとも1秒あたりの回線帯域幅の最小値に似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-224">The number should be similar to one tenth of the minimum circuit bandwidth in megabits per second.</span></span> <span data-ttu-id="8d091-225">たとえば、100mbps のインターネット接続を使用している場合は、10 mb/秒 (10MBps) と予想されることがあります。</span><span class="sxs-lookup"><span data-stu-id="8d091-225">For example if you have a 100mbps internet connection, you may expect 10 megabytes per second (10MBps).</span></span>

#### <a name="buffer-bloat"></a><span data-ttu-id="8d091-226">バッファーの膨張</span><span class="sxs-lookup"><span data-stu-id="8d091-226">Buffer bloat</span></span>

<span data-ttu-id="8d091-227">15Mb のダウンロード中に、SharePoint サービスのフロントドアに対する TCP 遅延を測定します。</span><span class="sxs-lookup"><span data-stu-id="8d091-227">During the 15Mb download we measure the TCP latency to the SharePoint service front door.</span></span> <span data-ttu-id="8d091-228">これは負荷の下の待機時間で、負荷がかかっていない場合の待機時間と比較されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-228">This is the latency under load and it is compared to the latency when not under load.</span></span> <span data-ttu-id="8d091-229">負荷の下での待機時間の増加は、多くの場合、コンシューマーネットワークデバイスのバッファーがロードされている (または膨張している) ことに起因します。</span><span class="sxs-lookup"><span data-stu-id="8d091-229">The increase in latency when under load is often attributable to consumer network device buffers being loaded (or bloated).</span></span> <span data-ttu-id="8d091-230">ネットワークの洞察は、1000以上の膨張に対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-230">A network insight is shown for any bloat of 1,000 or more.</span></span>

#### <a name="service-front-door-recorded-in-the-client-dns"></a><span data-ttu-id="8d091-231">クライアント DNS に記録されたサービスのフロントドア</span><span class="sxs-lookup"><span data-stu-id="8d091-231">Service front door recorded in the client DNS</span></span>

<span data-ttu-id="8d091-232">これにより、移動先の SharePoint サービスのフロントドアサーバーの DNS 名と IP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-232">This shows the DNS name and IP Address of the SharePoint service front door server that you were directed to.</span></span> <span data-ttu-id="8d091-233">これは情報のみを対象として提供されており、関連するネットワークの洞察がありません。</span><span class="sxs-lookup"><span data-stu-id="8d091-233">It is provided for information only and there is no associated network insight.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="8d091-234">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d091-234">Microsoft Teams</span></span>

<span data-ttu-id="8d091-235">このセクションでは、Microsoft Teams に関連するテスト結果を示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-235">This section shows test results related to Microsoft Teams.</span></span>

#### <a name="media-connectivity-audio-video-and-application-sharing"></a><span data-ttu-id="8d091-236">メディア接続 (オーディオ、ビデオ、アプリケーション共有)</span><span class="sxs-lookup"><span data-stu-id="8d091-236">Media connectivity (audio, video, and application sharing)</span></span>

<span data-ttu-id="8d091-237">これにより、Microsoft Teams サービスのフロントドアへの UDP 接続がテストされます。</span><span class="sxs-lookup"><span data-stu-id="8d091-237">This tests for UDP connectivity to the Microsoft Teams service front door.</span></span> <span data-ttu-id="8d091-238">これがブロックされている場合、Microsoft Teams は TCP を使用しても動作しますが、音声とビデオは損なわれます。</span><span class="sxs-lookup"><span data-stu-id="8d091-238">If this is blocked then Microsoft Teams may still work using TCP, but audio and video will be impaired.</span></span> <span data-ttu-id="8d091-239">これらの UDP ネットワークの測定の詳細については、「 [Skype For Business Online でのメディア品質とネットワーク接続のパフォーマンス」の](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)「Microsoft Teams」にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-239">Read more about these UDP network measurements which also apply to Microsoft Teams at [Media Quality and Network Connectivity Performance in Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)</span></span>

#### <a name="packet-loss"></a><span data-ttu-id="8d091-240">パケット損失</span><span class="sxs-lookup"><span data-stu-id="8d091-240">Packet loss</span></span>

<span data-ttu-id="8d091-241">クライアントから Microsoft Teams サービスのフロントドアへの、10秒テストの音声呼び出しで測定された UDP パケット損失を示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-241">Shows the UDP packet loss measured in a 10 second test audio call from the client to the Microsoft Teams service front door.</span></span> <span data-ttu-id="8d091-242">この値は、パスの **1.00%** 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-242">This should be lower than **1.00%** for a pass.</span></span>

### <a name="latency"></a><span data-ttu-id="8d091-243">遅延</span><span class="sxs-lookup"><span data-stu-id="8d091-243">Latency</span></span>

<span data-ttu-id="8d091-244">測定された UDP 待機時間を示します。これは **100 ミリ秒**より小さくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8d091-244">Shows the measured UDP latency, which should be lower than **100ms**.</span></span>

#### <a name="jitter"></a><span data-ttu-id="8d091-245">ずれ</span><span class="sxs-lookup"><span data-stu-id="8d091-245">Jitter</span></span>

<span data-ttu-id="8d091-246">測定された UDP ジッターを示します。これは **30 ミリ秒**未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-246">Shows the measured UDP jitter, which should be lower than **30ms**.</span></span>

#### <a name="connectivity"></a><span data-ttu-id="8d091-247">接続</span><span class="sxs-lookup"><span data-stu-id="8d091-247">Connectivity</span></span>

<span data-ttu-id="8d091-248">ユーザーのオフィスの場所から、必要なすべての Microsoft 365 ネットワークエンドポイントへの HTTP 接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="8d091-248">We test for HTTP connectivity from the user office location to all of the required Microsoft 365 network endpoints.</span></span> <span data-ttu-id="8d091-249">これらは、で公開され [https://aka.ms/o365ip](https://aka.ms/o365ip) ます。</span><span class="sxs-lookup"><span data-stu-id="8d091-249">These are published at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="8d091-250">に接続できない必要なネットワークエンドポイントに対して、ネットワークの洞察が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-250">A network insight is shown for any required network endpoints which cannot be connected to.</span></span>

<span data-ttu-id="8d091-251">接続 ay は、プロキシサーバー、ファイアウォール、またはエンタープライズネットワーク境界またはクラウドプロキシとして使用されている別のネットワークセキュリティデバイスによってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8d091-251">Connectivity ay be blocked by a proxy server, a firewall, or another network security device on the enterprise network perimeter or in use as a cloud proxy.</span></span>

<span data-ttu-id="8d091-252">「」で定義されている、「optimize or allow category」に記載されている必要な各 Microsoft 365 ネットワークエンドポイントで、SSL 証明書をテストし [https://aka.ms/o365ip](https://aka.ms/o365ip) ます。</span><span class="sxs-lookup"><span data-stu-id="8d091-252">We test the SSL certificate at each required Microsoft 365 network endpoint that is in the optimize or allow category as defined at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="8d091-253">いずれかのテストで Microsoft SSL 証明書が見つからない場合は、暗号化されたネットワークが仲介ネットワークデバイスによって傍受されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-253">If any tests do not find a Microsoft SSL certificate, then the encrypted network connected must have been intercepted by an intermediary network device.</span></span> <span data-ttu-id="8d091-254">ネットワークの洞察は、傍受されたネットワークエンドポイントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-254">A network insight is shown on any intercepted encrypted network endpoints.</span></span>

<span data-ttu-id="8d091-255">Microsoft によって提供されていない SSL 証明書が見つかった場合は、テストの FQDN と使用中の SSL 証明書の所有者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-255">Where an SSL certificate is found that isn't provided by Microsoft, we show the FQDN for the test and the in-use SSL certificate owner.</span></span> <span data-ttu-id="8d091-256">この SSL 証明書の所有者は、プロキシサーバーのベンダーである場合もあれば、エンタープライズ自己署名証明書の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8d091-256">This SSL certificate owner may be a proxy server vendor, or it may be an enterprise self-signed certificate.</span></span>

#### <a name="network-path"></a><span data-ttu-id="8d091-257">ネットワークパス</span><span class="sxs-lookup"><span data-stu-id="8d091-257">Network path</span></span>

<span data-ttu-id="8d091-258">このセクションでは、Exchange Online サービスのフロントドア、SharePoint Online サービスのフロントドア、Microsoft Teams サービスのフロントドアに対する ICMP traceroute の結果を示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-258">This section shows the results of an ICMP traceroute to the Exchange Online service front door, the SharePoint Online service front door, and the Microsoft Teams service front door.</span></span> <span data-ttu-id="8d091-259">これは情報のみを対象として提供されており、関連するネットワークの洞察がありません。</span><span class="sxs-lookup"><span data-stu-id="8d091-259">It is provided for information only and there is no associated network insight.</span></span> <span data-ttu-id="8d091-260">3つの traceroutes が提供されています。</span><span class="sxs-lookup"><span data-stu-id="8d091-260">There are three traceroutes provided.</span></span> <span data-ttu-id="8d091-261">Traceroute から_outlook.office365.com_、顧客の SharePoint フロントエンドに対する traceroute、または_microsoft.sharepoint.com_が提供されていない場合はに、traceroute_に world.tr.teams.microsoft.com するもの。_</span><span class="sxs-lookup"><span data-stu-id="8d091-261">A traceroute to _outlook.office365.com_, a traceroute to the customers SharePoint front end or to _microsoft.sharepoint.com_ if one was not provided, and a traceroute to _world.tr.teams.microsoft.com_.</span></span>

## <a name="connectivity-reports"></a><span data-ttu-id="8d091-262">接続レポート</span><span class="sxs-lookup"><span data-stu-id="8d091-262">Connectivity reports</span></span>

<span data-ttu-id="8d091-263">サインインすると、以前に実行したレポートを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d091-263">When you are signed in you can review previous reports that you have run.</span></span> <span data-ttu-id="8d091-264">また、それらを共有したり、リストから削除したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8d091-264">You can also share them or delete them from the list.</span></span>

![レポート](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a><span data-ttu-id="8d091-266">ネットワーク正常性の状態</span><span class="sxs-lookup"><span data-stu-id="8d091-266">Network health status</span></span>

<span data-ttu-id="8d091-267">これは、microsoft 365 のお客様に影響を与える可能性のある Microsoft のグローバルネットワークの重大な正常性の問題を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d091-267">This shows any significant health issues with Microsoft's global network which might impact Microsoft 365 customers.</span></span>

![ネットワーク正常性の状態](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a><span data-ttu-id="8d091-269">よくあるご質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="8d091-269">FAQ</span></span>

<span data-ttu-id="8d091-270">ここでは、よく寄せられる質問の一部に対する回答を示します。</span><span class="sxs-lookup"><span data-stu-id="8d091-270">Here are answers to some of our frequently asked questions.</span></span>

### <a name="is-this-tool-released-and-supported-by-microsoft"></a><span data-ttu-id="8d091-271">このツールは、Microsoft によってリリースされ、サポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="8d091-271">Is this tool released and supported by Microsoft?</span></span>

<span data-ttu-id="8d091-272">現時点ではプレビューになっており、Microsoft のサポートによって ga リリース状態に達するまで定期的に更新プログラムを提供する予定です。</span><span class="sxs-lookup"><span data-stu-id="8d091-272">It is currently a preview and we plan to provide updates regularly until we reach general availability release status with support from Microsoft.</span></span> <span data-ttu-id="8d091-273">品質向上のためにフィードバックを提供してください。</span><span class="sxs-lookup"><span data-stu-id="8d091-273">Please provide feedback to help us improve.</span></span> <span data-ttu-id="8d091-274">このツールの一部として、より詳細な Office 365 ネットワークオンボードガイドを発行することを計画しています。このツールは、テスト結果によって組織用にカスタマイズされています。</span><span class="sxs-lookup"><span data-stu-id="8d091-274">We are planning to publish a more detailed Office 365 Network Onboarding guide as part of this tool which is customized for the organization by its test results.</span></span>

### <a name="what-is-microsoft-365-service-front-door"></a><span data-ttu-id="8d091-275">Microsoft 365 サービスのフロントドアとは</span><span class="sxs-lookup"><span data-stu-id="8d091-275">What is Microsoft 365 service front door?</span></span>

<span data-ttu-id="8d091-276">Microsoft 365 service のフロントドアは、Office クライアントとサービスがネットワーク接続を終了する Microsoft のグローバルネットワークにおけるエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="8d091-276">The Microsoft 365 service front door is an entry point on Microsoft's global network where Office clients and services terminate their network connection.</span></span> <span data-ttu-id="8d091-277">Microsoft 365 への最適なネットワーク接続のために、ネットワーク接続を都市またはメトロの最も近い Microsoft 365 フロントドアに終端することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d091-277">For an optimal network connection to Microsoft 365, it is recommended that your network connection is terminated into the closest Microsoft 365 front door in your city or metro.</span></span>

<span data-ttu-id="8d091-278">注: Microsoft 365 service のフロントドアには、Azure marketplace で利用可能な **Azure Front ドアサービス** 製品との直接の関係はありません。</span><span class="sxs-lookup"><span data-stu-id="8d091-278">Note: Microsoft 365 service front door has no direct relationship to the **Azure Front Door Service** product available in the Azure marketplace.</span></span>

### <a name="what-is-the-best-microsoft-365-service-front-door"></a><span data-ttu-id="8d091-279">Microsoft 365 サービスのフロントドアの最適なものは何ですか。</span><span class="sxs-lookup"><span data-stu-id="8d091-279">What is the best Microsoft 365 service front door?</span></span>

<span data-ttu-id="8d091-280">最も優れた Microsoft 365 サービスのフロントドア (以前は最適なサービスのフロントドア) は、ネットワーク出口 (一般には、都市またはメトロエリア) に最も近いものです。</span><span class="sxs-lookup"><span data-stu-id="8d091-280">A best Microsoft 365 service front door (formerly known as an optimal service front door) is one that is closest to your network egress, generally in your city or metro area.</span></span> <span data-ttu-id="8d091-281">Microsoft 365 ネットワークパフォーマンスツールを使用して、使用中の Microsoft 365 サービスのフロントドアと最適なサービスフロントドアの場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="8d091-281">Use the Microsoft 365 network performance tool to determine location of your in-use Microsoft 365 service front door and the best service front door(s).</span></span> <span data-ttu-id="8d091-282">使用中のフロントドアが最適なものの1つであることがツールによって決まる場合は、Microsoft のグローバルネットワークへの接続性を期待する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d091-282">If the tool determines your in-use front door is one of the best ones, then you should expect great connectivity into Microsoft's global network.</span></span>

### <a name="what-is-an-internet-egress-location"></a><span data-ttu-id="8d091-283">インターネット出口の場所とは</span><span class="sxs-lookup"><span data-stu-id="8d091-283">What is an internet egress location?</span></span>

<span data-ttu-id="8d091-284">インターネット出口の場所は、ネットワークトラフィックがエンタープライズネットワークから出てインターネットに接続する場所です。</span><span class="sxs-lookup"><span data-stu-id="8d091-284">The internet egress Location is the location where your network traffic exits your enterprise network and connects to the Internet.</span></span> <span data-ttu-id="8d091-285">これは、ネットワークアドレス変換 (NAT) デバイスがあり、通常はインターネットサービスプロバイダー (ISP) を使用して接続する場所としても識別されます。</span><span class="sxs-lookup"><span data-stu-id="8d091-285">This is also identified as the location where you have a Network Address Translation (NAT) device and usually where you connect with an Internet Service Provider (ISP).</span></span> <span data-ttu-id="8d091-286">場所とインターネット出口の場所の間に長距離の距離がある場合は、WAN のバックアウトが非常に重要であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="8d091-286">If you see a long distance between your location and your internet egress location, then this may identify a significant WAN backhaul.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d091-287">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d091-287">Related topics</span></span>

[<span data-ttu-id="8d091-288">Microsoft 365 管理センター (プレビュー) でのネットワークパフォーマンスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="8d091-288">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="8d091-289">Microsoft 365 network performance insights (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8d091-289">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="8d091-290">Microsoft 365 ネットワーク評価 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8d091-290">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="8d091-291">Microsoft 365 ネットワーク接続ロケーションサービス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8d091-291">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
