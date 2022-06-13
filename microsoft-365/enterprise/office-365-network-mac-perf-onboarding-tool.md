---
title: Microsoft 365ネットワーク接続テスト ツール
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 1/18/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365ネットワーク接続テスト ツール
ms.openlocfilehash: ac2ec12ac0da2309e1d5ac0c35bbd0462cc68a62
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66043711"
---
# <a name="microsoft-365-network-connectivity-test-tool"></a>Microsoft 365ネットワーク接続テスト ツール

Microsoft 365ネットワーク接続テスト ツールは 、 <https://connectivity.office.com>. これは、正常性|の下のMicrosoft 365 管理センターで利用可能なネットワーク評価とネットワーク分析情報の補助ツール **です。[接続**] メニュー。

> [!IMPORTANT]
> すべてのテスト レポートが管理者と共有され、サインイン中にテナントにアップロードされるため、Microsoft 365 テナントにサインインすることが重要です。

> [!div class="mx-imgBorder"]
> ![接続テスト ツール。](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>ネットワーク接続テスト ツールは、WW コマーシャルのテナントをサポートしますが、中、GCC高、DoD、中国GCCサポートしていません。

Microsoft 365 管理 センターのネットワーク分析情報は、毎日集計される、Microsoft 365 テナントの定期的な製品内測定値に基づいています。 これに対し、Microsoft 365ネットワーク接続テストのネットワーク 分析情報は、ツールでローカルで実行されます。

製品内テストは限られており、ユーザーに対してローカルでテストを実行すると、より多くのデータが収集され、より深い分析情報が得られます。 Microsoft 365 管理 センターのネットワーク分析情報は、特定のオフィスの場所にネットワークの問題があることを示します。 Microsoft 365接続テストは、その問題の根本原因を特定し、ターゲットを絞ったパフォーマンス向上アクションを提供するのに役立ちます。

これらの分析情報は、Microsoft 365 管理 センター内の各オフィスの場所に対してネットワーク品質の状態を評価でき、Microsoft 365接続テストに基づいてテストを展開した後でより詳細な情報を見つけることができる場合に、一緒に使用することをお勧めします。

## <a name="what-happens-at-each-test-step"></a>各テスト ステップで何が起こるか

### <a name="office-location-identification"></a>Office場所の識別

[ *テストの実行* ] ボタンをクリックすると、実行中のテスト ページが表示され、オフィスの場所が特定されます。 都市、州、国別に場所を入力するか、検出するように選択できます。 オフィスの場所を検出した場合、ツールは Web ブラウザーから緯度と経度を要求し、使用前に精度を 300 メートル 300 メートルに制限します。 ネットワーク パフォーマンスを測定するために、建物よりも正確に場所を特定する必要はありません。

### <a name="javascript-tests"></a>JavaScript テスト

オフィスの場所を識別した後、JavaScript で TCP 待機時間テストを実行し、サービスフロント ドア サーバーの使用中と推奨されるMicrosoft 365に関するデータをサービスに要求します。 これらのテストが完了すると、マップと詳細タブに表示され、次の手順の前に表示できます。

### <a name="download-the-advanced-tests-client-application"></a>高度なテスト クライアント アプリケーションをダウンロードする

次に、高度なテスト クライアント アプリケーションのダウンロードを開始します。 クライアント アプリケーションを起動するにはユーザーに依存しており、.NET 6.0 ランタイムもインストールされている必要があります。

Microsoft 365ネットワーク接続テストには、Web サイト<https://connectivity.office.com>と、高度なネットワーク接続テストを実行するダウンロード可能なWindowsクライアント アプリケーションの 2 つの部分があります。 ほとんどのテストでは、アプリケーションを実行する必要があります。 実行すると、Web ページに結果が設定されます。

Web ブラウザーのテストが完了したら、Web サイトから高度なクライアント テスト アプリケーションをダウンロードするように求められます。 プロンプトが表示されたら、ファイルを開いて実行します。

> [!div class="mx-imgBorder"]
> ![高度なテストのクライアント アプリケーション。](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>高度なテスト クライアント アプリケーションを開始する

クライアント アプリケーションが起動すると、web ページが更新され、この結果が表示されます。 テスト データは、web ページへの受信を開始します。 新しいデータが受信されるたびにページが更新され、到着したデータを確認できます。

### <a name="advanced-tests-completed-and-test-report-upload"></a>高度なテストが完了し、レポートのアップロードをテストする

テストが完了すると、Web ページと高度なテスト クライアントの両方に表示されます。 ユーザーがサインインしている場合、テスト レポートは顧客のテナントにアップロードされます。

## <a name="sharing-your-test-report"></a>テスト レポートを共有する

テスト レポートでは、Microsoft 365 アカウントに対する認証が必要です。 管理者は、テスト レポートを共有する方法を選択します。 既定の設定では、組織内の他のユーザーとレポートを共有できます。ReportID リンクは使用できません。 レポートは既定で 90 日後に期限切れになります。

### <a name="sharing-your-report-with-your-administrator"></a>管理者とレポートを共有する

テスト レポートが発生したときにサインインしている場合、レポートは管理者と共有されます。

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Microsoft アカウント チーム、サポート、その他の担当者と共有する

テスト レポート (個人識別を除く) は、Microsoft の従業員と共有されます。 この共有は既定で有効になっており、正常性|で管理者が無効にすることができます。**Microsoft 365 管理 センターの [ネットワーク接続**] ページ。

### <a name="sharing-with-other-users-who-sign-in-to-the-same-microsoft-365-tenant"></a>同じMicrosoft 365 テナントにサインインする他のユーザーと共有する

レポートを共有するユーザーを選択できます。 選択できる機能は既定で有効になっていますが、管理者が無効にすることもできます。

> [!div class="mx-imgBorder"]
> ![テスト結果へのリンクをユーザーと共有する。](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>ReportID リンクを使用して他のユーザーと共有する

ReportID リンクへのアクセス権を提供することで、テスト レポートをだれとでも共有できます。 このリンクは、サインインせずにテスト レポートを表示できるように、他のユーザーに送信できる URL を生成します。 この共有は既定で無効になっており、管理者が有効にする必要があります。

> [!div class="mx-imgBorder"]
> ![テスト結果へのリンクを共有する。](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>ネットワーク接続テストの結果

結果は、[**概要**] タブと [**詳細**] タブに表示されます。 [概要] タブには、検出されたネットワーク境界のマップと、近くの他のMicrosoft 365顧客とのネットワーク評価の比較が表示されます。 また、テスト レポートを共有することもできます。 結果概要ビューは次のようになります。

> [!div class="mx-imgBorder"]
> ![ネットワーク接続テスト ツールの概要結果。](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

詳細タブ出力の例を次に示します。 [詳細] タブには、結果が良好に比較された場合に緑色の円のチェック マークが表示されます。 結果がネットワーク分析情報を示すしきい値を超えた場合、赤い三角形の感嘆符が表示されます。 次のセクションでは、詳細タブの結果行のそれぞれについて説明し、ネットワーク分析情報に使用されるしきい値について説明します。

> [!div class="mx-imgBorder"]
> ![ネットワーク接続テスト ツールのテスト結果の例。](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>位置情報

このセクションでは、自分の場所に関連するテスト結果を示します。

#### <a name="your-location"></a>自分の場所

ユーザーの場所は、ユーザー Web ブラウザーから検出されます。 ユーザーの選択で入力することもできます。 これは、エンタープライズ ネットワーク境界の特定の部分へのネットワーク距離を識別するために使用されます。 この場所検出からの都市と他のネットワーク ポイントまでの距離のみがレポートに保存されます。

ユーザー オフィスの場所がマップ ビューに表示されます。

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>ネットワークエグレスの場所 (ネットワークが ISP に接続する場所)

サーバー側でネットワーク エグレス IP アドレスを識別します。 場所データベースは、ネットワーク エグレスのおおよその場所を検索するために使用されます。 通常、これらのデータベースの IP アドレスの精度は約 90% です。 ネットワーク エグレス IP アドレスから検索された場所が正確でない場合は、誤った結果が発生します。 特定の IP アドレスに対してこのエラーが発生しているかどうかを検証するには、パブリックにアクセスできるネットワーク IP アドレスの場所 Web サイトを使用して、実際の場所と比較できます。

#### <a name="your-distance-from-the-network-egress-location"></a>ネットワークの出口からの距離

その場所からオフィスの場所までの距離を決定します。 これは、距離が **500 マイル (800** キロメートル) を超える場合、TCP 待機時間が 25 ミリ秒を超える可能性があり、ユーザー エクスペリエンスに影響を与える可能性があるため、ネットワーク 分析情報として表示されます。

マップには、エンタープライズ WAN 内のネットワーク バックホールを示すユーザー オフィスの場所に関連するネットワークエグレスの場所が表示されます。

最適なMicrosoft 365ネットワーク接続を実現するために、ユーザー オフィスの場所からインターネットへのローカルおよびダイレクト ネットワークエグレスを実装します。 このネットワーク 分析情報に対処するには、ローカルおよびダイレクト エグレスの改善が最適な方法です。

#### <a name="proxy-server-information"></a>プロキシ サーバー情報

**最適化** カテゴリでネットワーク トラフィックMicrosoft 365渡すように、プロキシ サーバーがローカル コンピューターで構成されているかどうかを確認します。 ユーザー オフィスの場所からプロキシ サーバーまでの距離を特定します。

距離は、最初に ICMP ping によってテストされます。 失敗した場合は、TCP ping を使用してテストし、最後に IP アドレスの場所データベースでプロキシ サーバーの IP アドレスを検索します。 プロキシ サーバーがユーザー オフィスの場所から **500 マイル (800** キロメートル) を超える場合は、ネットワーク分析情報を表示します。

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>組織への接続に使用する仮想プライベート ネットワーク (VPN)

このテストでは、VPN を使用してMicrosoft 365に接続しているかどうかを検出します。 成功の結果は、VPN がない場合、または推奨される分割トンネル構成の VPN がある場合Microsoft 365表示されます。

#### <a name="vpn-split-tunnel"></a>VPN 分割Tunnel

Exchange Online、SharePoint Online、Microsoft Teamsの各 **最適化** カテゴリ ルートは、VPN でトンネリングされているかどうかを確認するためにテストされます。 分割されたワークロードでは、VPN が完全に回避されます。 トンネリングされたワークロードは、VPN 経由で送信されます。 選択的トンネリングされたワークロードには、VPN 経由で送信されるルートと分割されたルートがあります。合格結果は、すべてのワークロードが分割されるか、選択的にトンネリングされるかを示します。

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>パフォーマンスが向上した大都市圏のお客様

ユーザーオフィスの場所とExchange Onlineサービスの間のネットワーク待機時間は、同じメトロエリア内の他のMicrosoft 365顧客と比較されます。 ネットワーク分析情報は、同じ地下鉄エリア内の 10% 以上の顧客のパフォーマンスが向上している場合に表示されます。 つまり、ユーザーはMicrosoft 365ユーザー インターフェイスのパフォーマンスが向上します。

このネットワーク 分析情報は、市内のすべてのユーザーが同じ通信インフラストラクチャにアクセスし、インターネット回線と Microsoft のネットワークに同じ近接性を持っていることに基づいて生成されます。

#### <a name="time-to-make-a-dns-request-on-your-network"></a>ネットワークで DNS 要求を行う時間

これは、テストを実行したクライアント マシンで構成された DNS サーバーを示しています。 DNS 再帰リゾルバー サーバーである可能性があります。ただし、これは一般的ではありません。 DNS フォワーダー サーバーである可能性が高くなります。このサーバーは、DNS 結果をキャッシュし、キャッシュされていない DNS 要求を別の DNS サーバーに転送します。

これは情報提供のみを目的として提供され、ネットワーク分析情報には影響しません。

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>DNS 再帰リゾルバーへの接続までの距離(または時間)

使用中の DNS 再帰リゾルバーは、特定の DNS 要求を行い、同じ要求を受信した IP アドレスを DNS ネーム サーバーに要求することによって識別されます。 この IP アドレスは DNS 再帰リゾルバーであり、IP アドレスの場所データベースで検索されて場所が見つかります。 次に、ユーザー オフィスの場所から DNS 再帰リゾルバー サーバーの場所までの距離が計算されます。 距離が **500 マイル (800** キロメートル) を超える場合、これはネットワーク 分析情報として表示されます。

ネットワーク エグレス IP アドレスから検索された場所が正確でない可能性があり、このテストの結果として誤った結果が生じる可能性があります。 特定の IP アドレスに対してこのエラーが発生しているかどうかを検証するには、パブリックにアクセスできるネットワーク IP アドレスの場所 Web サイトを使用します。

このネットワーク 分析情報は、Exchange Onlineサービス フロント ドアの選択に特に影響します。 この分析情報に対処するには、ローカルおよびダイレクト ネットワークエグレスを前提条件とし、DNS 再帰リゾルバーをそのネットワークエグレスの近くに配置する必要があります。

### <a name="exchange-online"></a>Exchange Online

このセクションでは、Exchange Onlineに関連するテスト結果を示します。

#### <a name="exchange-service-front-door-location"></a>Exchange サービス フロント ドアの場所

使用中のExchangeサービス フロント ドアは、Outlookがこれを行うのと同じ方法で識別され、ユーザーの場所からそれに至るネットワーク TCP 待機時間を測定します。 TCP 待機時間が表示され、使用中のExchangeサービス フロント ドアが、現在の場所に最適なサービス フロント ドアの一覧と比較されます。 これは、最高のExchangeサービス フロント ドアの 1 つが使用されていない場合、ネットワーク分析情報として表示されます。

最適なExchangeサービス フロント ドアの 1 つを使用していない場合は、企業ネットワークエグレスの前にネットワーク バックホールが発生する可能性があります。その場合は、ローカルおよびダイレクト ネットワークエグレスをお勧めします。 また、リモート DNS 再帰リゾルバー サーバーの使用によって発生する可能性もあります。その場合は、DNS 再帰リゾルバー サーバーをネットワーク エグレスに合わせることをお勧めします。

Exchangeサービス フロント ドアに対する TCP 待機時間 (ミリ秒) の潜在的な改善を計算します。 これは、テスト済みのユーザー オフィスの場所のネットワーク待機時間を調べて、ネットワーク待機時間を現在の場所から、サービス フロント ドアExchange押し入れに減算することによって行われます。 この違いは、改善の潜在的な機会を表します。

#### <a name="best-exchange-service-front-doors-for-your-location"></a>お客様の場所に最適なExchangeサービス フロント ドア

これにより、お客様の場所に最適なExchangeサービス フロント ドアの場所が都市別に一覧表示されます。

#### <a name="service-front-door-recorded-in-the-client-dns"></a>クライアント DNS に記録されたサービス フロント ドア

これは、送信されたExchange サービス フロント ドア サーバーの DNS 名と IP アドレスを示します。 これは情報提供のみを目的として提供され、関連するネットワーク 分析情報はありません。

### <a name="sharepoint-online"></a>SharePoint Online

このセクションでは、SharePoint Online とOneDriveに関連するテスト結果を示します。

#### <a name="the-service-front-door-location"></a>サービス フロント ドアの場所

使用中のSharePointサービス フロント ドアは、OneDrive クライアントと同じ方法で識別され、ユーザー オフィスの場所からそれに至るネットワーク TCP 待機時間を測定します。

#### <a name="download-speed"></a>ダウンロード速度

SharePoint サービス フロント ドアから 15 Mb のファイルのダウンロード速度を測定します。 結果は、SharePointまたはOneDriveから 1 秒でダウンロードできるサイズ ファイルをメガバイト単位で示すために、**1 秒** あたりメガバイト単位で表示されます。 この数は、1 秒あたりのメガビット数の最小回線帯域幅の 10 分の 1 に似ている必要があります。 たとえば、100 mbps のインターネット接続がある場合は、1 秒あたり 10 メガバイト (10 MBps) が必要になることがあります。

#### <a name="buffer-bloat"></a>バッファーの肥大化

15 Mb のダウンロード中に、SharePoint サービス フロント ドアへの TCP 待機時間を測定します。 これは読み込み中の待機時間であり、読み込まれていない場合の待機時間と比較されます。 負荷が低い場合の待機時間の増加は、多くの場合、読み込まれる (または肥大化している) コンシューマー ネットワーク デバイス バッファーに起因します。 1,000 以上の肥大化に対するネットワーク分析情報が表示されます。

#### <a name="service-front-door-recorded-in-the-client-dns"></a>クライアント DNS に記録されたサービス フロント ドア

これは、送信されたSharePoint サービス フロント ドア サーバーの DNS 名と IP アドレスを示します。 これは情報提供のみを目的として提供され、関連するネットワーク 分析情報はありません。

### <a name="microsoft-teams"></a>Microsoft Teams

このセクションでは、Microsoft Teamsに関連するテスト結果を示します。

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>メディア接続 (オーディオ、ビデオ、アプリケーション共有)

これにより、Microsoft Teams サービス フロント ドアへの UDP 接続がテストされます。 これがブロックされている場合、Microsoft Teams は 引き続き TCP を使用して動作する可能性がありますが、オーディオとビデオが損なわれます。 これらの UDP ネットワーク測定値の詳細については、Skype for Business [Online のメディア品質とネットワーク接続のパフォーマンスのMicrosoft Teams](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)にも適用されます。

#### <a name="packet-loss"></a>パケット損失

クライアントからMicrosoft Teams サービス フロント ドアへの 10 秒間のテスト オーディオ呼び出しで測定された UDP パケット損失を示します。 パスの場合、これは **1.00%** 未満にする必要があります。

#### <a name="latency"></a>遅延

測定された UDP 待機時間を示します。 **これは 100 ミリ秒** 未満である必要があります。

#### <a name="jitter"></a>ジッタ

測定された UDP ジッターを示します。 **これは 30 ミリ秒** 未満である必要があります。

#### <a name="connectivity"></a>接続

ユーザー オフィスの場所から、必要なすべてのMicrosoft 365ネットワーク エンドポイントへの HTTP 接続をテストします。 これらは 、次の時点で [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md)公開されています。 ネットワーク 分析情報は、接続できない必要なネットワーク エンドポイントに対して表示されます。

接続は、プロキシ サーバー、ファイアウォール、またはエンタープライズ ネットワーク境界上の別のネットワーク セキュリティ デバイスによってブロックされる可能性があります。 TCP ポート 80 への接続は HTTP 要求でテストされ、TCP ポート 443 への接続は HTTPS 要求でテストされます。 応答がない場合、FQDN はエラーとしてマークされます。 HTTP 応答コード 407 がある場合、FQDN はエラーとしてマークされます。 HTTP 応答コード 403 がある場合は、応答のサーバー属性を確認し、プロキシ サーバーと見なされる場合は、これをエラーとしてマークします。 Windowsコマンド ライン ツール curl.exeを使用して実行するテストをシミュレートできます。

次に定義[https://aka.ms/o365ip](./urls-and-ip-address-ranges.md)されている最適化カテゴリまたは許可カテゴリに含まれる、必要な各Microsoft 365ネットワーク エンドポイントで SSL 証明書をテストします。 Microsoft SSL 証明書が見つからないテストがある場合は、接続されている暗号化されたネットワークが中間ネットワーク デバイスによって傍受されている必要があります。 ネットワーク分析情報は、傍受された暗号化されたネットワーク エンドポイントに表示されます。

Microsoft によって提供されていない SSL 証明書が見つかった場合は、テストの FQDN と使用中の SSL 証明書の所有者が表示されます。 この SSL 証明書の所有者は、プロキシ サーバー ベンダーであるか、エンタープライズ自己署名証明書である可能性があります。

#### <a name="network-path"></a>ネットワーク パス

このセクションでは、Exchange Online サービス フロント ドア、SharePoint Online サービス フロント ドア、Microsoft Teams サービス フロント ドアへの ICMP トレースルートの結果を示します。 これは情報提供のみを目的として提供され、関連するネットワーク 分析情報はありません。 指定されたトレースルートは 3 つあります。 _outlook.office365.com_ へのトレースルート、顧客SharePointフロントエンドへのトレースルート、または提供されていない場合は _microsoft.sharepoint.com_ するトレースルート、_および world.tr.teams.microsoft.com_ へのトレースルート。

## <a name="connectivity-reports"></a>接続レポート

サインインしたら、実行した以前のレポートを確認できます。 それらを共有したり、リストから削除したりすることもできます。

> [!div class="mx-imgBorder"]
> ![レポート。](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>ネットワークの正常性状態

これは、Microsoft のグローバル ネットワークに関する重大な正常性の問題を示しています。これは、お客様Microsoft 365影響を与える可能性があります。

> [!div class="mx-imgBorder"]
> ![ネットワークの正常性状態。](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="testing-from-the-command-line"></a>コマンド ラインからのテスト

リモート展開ツールと実行ツールで使用できるコマンド ライン実行可能ファイルを提供し、Microsoft 365ネットワーク接続テスト ツールの Web サイトで使用できるのと同じテストを実行します。

コマンド ライン テスト ツールは、次の[コマンド ライン ツール](https://connectivity.office.com/api/AnonymousConnectivityTest/DownloadStandAloneRichClient)からダウンロードできます。

これを実行するには、Windows エクスプローラーで実行可能ファイルをダブルクリックするか、コマンド プロンプトから起動するか、タスク スケジューラを使用してスケジュールを設定します。

初めて実行可能ファイルを起動するときに、テストが実行される前にエンド ユーザー ライセンス契約 (EULA) に同意するように求められます。 EULA を既に読んで承諾している場合は、実行可能プロセスの起動時に、現在の作業ディレクトリに Microsoft-365-Network-Connectivity-Test-EULA-accepted.txt という空のファイルを作成できます。 EULA に同意するには、「y」と入力し、プロンプトが表示されたらコマンド ライン ウィンドウで Enter キーを押します。

実行可能ファイルは、次のコマンド ライン パラメーターを受け入れます。
- -h : このヘルプ ドキュメントへのリンクを表示する
- -testlist test&gt;: 実行するテストを指定します&lt;。 既定では、基本的なテストのみが実行されます。 有効なテスト名には、すべて、dnsConnectivityPerf、dnsResolverIdentification、bufferBloat、traceroute、プロキシ、VPN、skype、接続、networkInterface が含まれます。
- -filepath &lt;filedir&gt; Directory パスのテスト結果ファイル。 許可される値は、アクセス可能なディレクトリの絶対パスまたは相対パスです
- -city &lt;city&gt; 都市、州、および国のフィールドに対して、指定した値が指定された場合に使用されます。 指定されていない場合は、Windows Location Services (WLS) に対してクエリが実行されます。 WLS が失敗した場合、コンピューターのネットワーク エグレスから場所が検出されます 
- -state state &lt;&gt;
- -country &lt;country&gt; 
- インターネットにアクセスするためにプロキシが必要な場合は、-proxy &lt;アカウント&gt;&lt;のパスワード&gt; プロキシ アカウント名とパスワードを指定できます

### <a name="results"></a>結果
結果の出力は、既に存在しない限り、プロセスの現在の作業ディレクトリに作成される TestResults という名前のフォルダー内の JSON ファイルに書き込まれます。 出力のファイル名の形式は、connectivity_test_result_YYYY-MM-DD-HH-MM-SS.json です。 結果は、Microsoft 365ネットワーク接続テスト ツール Web サイトの Web ページに表示される出力と一致する JSON ノードになります。 実行するたびに新しい結果ファイルが作成され、スタンドアロン実行可能ファイルは Admin Center Network Connectivity ページで表示するための結果を Microsoft テナントにアップロードしません。 フロント ドア のコード、経度、緯度は結果ファイルに含まれません。

### <a name="launching-from-windows-file-explorer"></a>Windows エクスプローラーからの起動
実行可能ファイルをダブルクリックしてテストを開始するだけで、コマンド プロンプト ウィンドウが表示されます。

### <a name="launching-from-the-command-prompt"></a>コマンド プロンプトからの起動
CMD.EXEコマンド プロンプト ウィンドウで、実行する実行可能ファイルのパスと名前を入力できます。 ファイル名がMicrosoft.Connectivity.Test.exe

### <a name="launching-from-windows-task-scheduler"></a>タスク スケジューラから起動Windows
Windowsタスク スケジューラでは、スタンドアロン のテスト実行可能ファイルを起動するタスクを追加できます。 実行可能ファイルは EULA が受け入れられるまでブロックされるため、タスクの現在の作業ディレクトリを EULA 承認済みファイルを作成した場所に指定する必要があります。 コンソールなしでプロセスがバックグラウンドで開始されている場合、EULA を対話的に受け入れることはできません。

### <a name="more-details-on-the-standalone-executable"></a>スタンドアロン実行可能ファイルの詳細
コマンド ライン ツールでは、Windows Location Services を使用して、一部の距離を決定するためのユーザーの市区町村の国情報を検索します。 コントロール パネルで Windows Location Services が無効になっている場合、ユーザーの場所ベースの評価は空白になります。 Windows 設定では、"Location Services" がオンになっている必要があり、"デスクトップ アプリが自分の場所にアクセスできるようにする" こともオンになっている必要があります。

コマンド ライン ツールは、まだインストールされていない場合、.NET Frameworkのインストールを試みます。 また、Microsoft 365 ネットワーク接続テスト ツールからメインのテスト実行可能ファイルをダウンロードし、それを起動します。

## <a name="faq"></a>FAQ

よく寄せられる質問の一部に対する回答を次に示します。

### <a name="what-is-required-to-run-the-advanced-test-client"></a>高度なテスト クライアントを実行するために必要なものは何ですか?

高度なテスト クライアントには、.NET 6.0 ランタイムが必要です。 インストールされていない高度なテスト クライアントを実行すると、 [.NET 6.0 インストーラー ページ](https://dotnet.microsoft.com/en-us/download/dotnet/6.0/runtime?utm_source=getdotnetcore)に移動します。 Windowsの [デスクトップ アプリの実行] 列から必ずインストールしてください。 .NET 6.0 ランタイムをインストールするには、コンピューターに対する管理者権限が必要です。

高度なテスト クライアントでは、SignalR を使用して Web ページに通信します。 このためには、 **connectivity.service.signalr.net** への TCP ポート 443 接続が開かれていることを確認する必要があります。 この URL は、Microsoft 365 クライアント アプリケーション ユーザーには接続が必要ないため、この URL は公開<https://aka.ms/o365ip>されません。

### <a name="what-is-microsoft-365-service-front-door"></a>サービス フロント ドアMicrosoft 365とは何ですか?

Microsoft 365サービス フロント ドアは、Office クライアントとサービスがネットワーク接続を終了する Microsoft のグローバル ネットワーク上のエントリ ポイントです。 Microsoft 365への最適なネットワーク接続を実現するには、ネットワーク接続を、都市または地下鉄の最も近いMicrosoft 365フロント ドアに終端することをお勧めします。

> [!NOTE]
> サービス フロント ドアMicrosoft 365、Azure マーケットプレースで使用できる **Azure Front Door Service** 製品との直接的な関係はありません。

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>サービス フロント ドアMicrosoft 365最適なものは何ですか?

最適なMicrosoft 365サービス フロント ドア (以前は最適なサービス フロント ドアと呼ばられていました) は、ネットワーク エグレスに最も近いもので、通常は都市または地下鉄のエリアにあります。 Microsoft 365ネットワーク パフォーマンス ツールを使用して、使用中のMicrosoft 365サービス フロント ドアと最適なサービス フロント ドアの場所を決定します。 使用中のフロント ドアが最適なものの 1 つであるとツールが判断した場合は、Microsoft のグローバル ネットワークへの優れた接続が期待されます。

### <a name="what-is-an-internet-egress-location"></a>インターネットエグレスの場所は何ですか?

インターネットエグレスの場所は、ネットワーク トラフィックがエンタープライズ ネットワークから出てインターネットに接続する場所です。 これは、ネットワーク アドレス変換 (NAT) デバイスがあり、通常はインターネット サービス プロバイダー (ISP) と接続する場所としても識別されます。 場所とインターネットエグレスの場所の間に長い距離が表示される場合、これは重要な WAN バックホールを識別する可能性があります。

## <a name="related-topics"></a>関連項目

[Microsoft 365 管理 センターでのネットワーク接続](office-365-network-mac-perf-overview.md)

[ネットワーク パフォーマンスの分析情報をMicrosoft 365する](office-365-network-mac-perf-insights.md)

[Microsoft 365 ネットワーク評価](office-365-network-mac-perf-score.md)

[Microsoft 365 ネットワーク接続場所サービス](office-365-network-mac-location-services.md)
