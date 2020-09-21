---
title: Microsoft 365 ネットワーク接続テスト (プレビュー)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
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
ms.openlocfilehash: 2197f3361efee51dfa2bd170b0c8d8e94709d3e8
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962400"
---
# <a name="microsoft-365-network-connectivity-test-preview"></a>Microsoft 365 ネットワーク接続テスト (プレビュー)

Microsoft 365 ネットワーク接続テストツールは、にあり <https://connectivity.office.com> ます。 これは、Microsoft 365 管理センターで利用可能なネットワーク評価およびネットワーク insights 情報に対する adjunct ツールであり、正常性の下にあります。 **[接続** ] メニュー

![接続テストツール](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>ネットワーク接続テストツールは、世界各地の商用およびドイツのテナントをサポートしていますが、GCC のモデレート、GCC High、DoD、中国ではサポートされていません。

Microsoft 365 管理センターのネットワーク insights は、毎日集計される Microsoft 365 テナントの正規の製品の測定基準に基づいています。 これに対して、Microsoft 365 ネットワーク接続テストのネットワーク洞察は、ツールでローカルおよび1回実行されます。 製品内で実行できるテストは制限されており、ユーザーに対してローカルにテストを実行することにより、より深い洞察を得られるように収集できます。 次に、Microsoft 365 管理センターの network insights は、特定のオフィスの場所で Microsoft 365 を使用するためのネットワークの問題があることを示しています。 Microsoft 365 connectivity test は、この問題の根本的な原因を特定するのに役立ち、推奨されるネットワークパフォーマンスの向上アクションを導きます。

Microsoft 365 管理センターの各オフィスの場所についてネットワーク品質の状態を評価し、Microsoft 365 の接続テストに基づいてテストを展開した後は、より多くの情報を見つけられるようにすることをお勧めします。

>[!IMPORTANT]
>Network insights、Microsoft 365 Admin Center でのパフォーマンスに関する推奨事項と評価は現在プレビュー状態であり、機能プレビュープログラムに登録されている Microsoft 365 テナントに対してのみ使用できます。

## <a name="the-advanced-tests-client-application"></a>高度なテストクライアントアプリケーション

Microsoft 365 ネットワーク接続テストには2つの部分があります。web サイト <https://connectivity.office.com> と、高度なネットワーク接続テストを実行するダウンロード可能な Windows クライアントアプリケーション。 ほとんどのテストでは、アプリケーションが実行されている必要があります。 実行時に、結果が web ページに返されます。

Web ブラウザーテストが完了した後、web サイトからアドバンストクライアントテストアプリケーションをダウンロードするように求めるメッセージが表示されます。 メッセージが表示されたら、ファイルを開いて実行します。

![高度なテストクライアントアプリケーション](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

## <a name="sharing-your-test-report"></a>テストレポートを共有する

テストレポートには、Office 365 アカウントにサインインする必要があります。 テストレポートを共有する方法は、管理者が選択します。

### <a name="sharing-your-report-with-your-administrator"></a>管理者とレポートを共有する

サインインしているすべてのテストレポートは、管理者と共有されます。

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Microsoft アカウントチーム、サポート、またはその他の担当者との共有

個人 id を除くテストレポートは、Microsoft の従業員と共有されます。 これは既定で有効になっており、管理者が正常性で無効にすることができます。 **Health | Network Connectivity**Microsoft 365 管理センターの [ネットワーク接続] ページ

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>同じ Office 365 テナントにサインインしている他のユーザーとの共有

レポートを共有するユーザーを選択できます。これは既定で有効になっています。 また、管理者が無効にすることもできます。

![テスト結果へのリンクをユーザーと共有する](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>ReportID リンクを使用したすべてのユーザーとの共有

報告 Tid リンクへのアクセスを提供することにより、テストレポートを任意のユーザーと共有することができます。 これにより、ユーザーに送信できる URL が生成され、サインインせずにテストレポートを表示できるようになります。 これは既定で無効になっており、管理者が有効にする必要があります。

![テスト結果へのリンクの共有](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>ネットワーク接続テストの結果

結果は [ **概要** ] タブと [ **詳細** ] タブに表示されます。 [概要] タブには、検出されたネットワーク境界のマップと、近くにある他の Office 365 お客様とのネットワーク評価の比較が表示されます。 テストレポートを共有することもできます。 概要結果ビューは次のようになります。

![ネットワーク接続テストツールの概要結果](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

このツールで表示される [詳細] タブの出力の例を次に示します。 [詳細] タブでは、結果が favorably をしきい値と比較した場合は、緑色の円チェックマークが表示されます。 結果がネットワークの洞察を示すしきい値を超えた場合は、赤い三角形の感嘆符が表示されます。 次のセクションでは、[詳細] タブの各結果行について説明し、ネットワークインサイトで使用されるしきい値について説明します。

![テスト結果の例のネットワーク接続テストツール](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>場所情報

ここでは、自分の場所に関連するテスト結果を示します。

#### <a name="your-location"></a>自分の場所

ユーザーの場所は、ユーザーの web ブラウザーから検出されるか、ユーザーの選択で入力できます。 これは、企業ネットワーク境界の特定の部分に対するネットワークの距離を特定するために使用されます。 この場所を検出した市区町村のみがレポートに保存されます。

ユーザーのオフィスの場所がマップビューに表示されます。

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>ネットワークの出口の場所 (ネットワークが ISP に接続する場所)

サーバー側のネットワーク出口 IP アドレスを特定します。 場所データベースは、ネットワーク出口のおおよその場所を検索するために使用されます。 これらのデータベースでは、通常、IP アドレスの約90% の精度があります。 ネットワークの出口 IP アドレスから検索された場所が正確でない場合は、このテストの結果が false になります。 特定の IP アドレスに対してこのエラーが発生しているかどうかを検証するには、パブリックにアクセス可能なネットワークの IP アドレスの場所 web サイトを使用して、実際の場所と比較することができます。

#### <a name="your-distance-from-the-network-egress-location"></a>ネットワークの出口位置からの距離

その場所からオフィスの場所までの距離を決定します。 これは、距離が **500 マイル** (800 km) を超える場合に、TCP の待機時間が25ミリ秒を超える可能性があり、ユーザーの利便性に影響する可能性があるため、ネットワークの洞察として示されています。

ネットワークの出口の場所がマップビューに表示され、エンタープライズ WAN 内部のネットワークバックを示す、ユーザーのオフィスの場所に接続されます。

Microsoft 365 のネットワーク接続には、ユーザーのオフィスの場所からインターネットへのローカルおよび直接ネットワーク出口を実装することをお勧めします。 このネットワークの洞察に対処するための最善の方法は、ローカルおよび直接出口に対する機能強化です。

#### <a name="proxy-server-information"></a>プロキシサーバー情報

ローカルコンピューターで構成されているプロキシサーバーを識別します。 最適化カテゴリの Microsoft 365 ネットワークトラフィックで、これらのいずれかが構成されているかどうかを確認します。 ユーザーのオフィスの場所からプロキシサーバーへの距離を特定します。 この距離は、最初に ICMP ping によってテストされ、失敗した場合は TCP ping を使用してテストを実行して失敗した場合は、IP アドレスの場所データベースでプロキシサーバーの IP アドレスを検索します。 プロキシサーバーが、ユーザーのオフィスの場所から **500 マイル** (800 km) を超える場合は、ネットワークの洞察を示しています。

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>組織に接続するために使用する仮想プライベートネットワーク (VPN)

これは、VPN を使用して Office 365 に接続しているかどうかを検出します。 VPN を使用していない場合、または Office 365 に対して推奨される分割トンネル構成を備えた VPN がある場合は、合格の結果が表示されます。

#### <a name="vpn-split-tunnel"></a>VPN 分割トンネル

Exchange Online、SharePoint Online、Microsoft Teams の各最適化カテゴリルートは、VPN で tunnelled されているかどうかをテストします。 ワークロードの分割は、VPN 全体を回避します。 Tunnelled ワークロードは、すべて VPN 経由で送信されます。 選択的 tunnelled ワークロードには、VPN 経由で送信されるいくつかのルートと一部が切り離されています。すべてのワークロードがスプリットアウトまたは選択的 tunnelled であるかどうかを示す結果が返されます。

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>優れたパフォーマンスを備えた大都市圏のお客様

Exchange Online サービスのフロントドアに対するユーザーのオフィスの場所のネットワーク TCP 遅延が、同じメトロエリアにある他の Microsoft 365 ユーザーと比較されます。 同じメトロエリア内の10% 以上のお客様がパフォーマンスが優れている場合は、ネットワークの洞察が表示されます。 これは、Microsoft 365 ユーザーインターフェイスでユーザーのパフォーマンスが向上することを意味します。

このネットワークの洞察は、1つの都市内のすべてのユーザーが同じ通信インフラストラクチャにアクセスできることと、インターネット回線および Microsoft のネットワークとの距離に応じて生成されます。

#### <a name="time-to-make-a-dns-request-on-your-network"></a>ネットワークで DNS 要求を行う時間

これは、テストを実行したクライアントコンピューター上に構成された DNS サーバーを示しています。 DNS 再帰リゾルバーサーバーの場合もありますが、これは一般的ではありません。 Dns フォワーダーサーバーは、DNS の結果をキャッシュし、キャッシュされていない DNS 要求を別の DNS サーバーに転送する可能性が高くなります。

これは情報のみを対象として提供されており、ネットワークに関する洞察には影響しません。

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>DNS の再帰的なリゾルバーに接続する、または時刻からの距離

使用中の DNS 再帰リゾルバーは、特定の DNS 要求を作成し、同じ要求を受信した IP アドレスに対して DNS ネームサーバーに要求することで識別されます。 この IP アドレスは、DNS の再帰的なリゾルバーです。これは、IP アドレスの場所のデータベースで検索され、場所を見つけます。 その後、ユーザーのオフィスの場所から DNS の再帰的なリゾルバーサーバーの場所までの距離が計算されます。 これは、距離が **500 マイル** (800 km) を超える場合にネットワークの洞察として表示されます。

ネットワーク出力 IP アドレスから検索された場所が正確でない可能性があるため、このテストからの結果が false になることがあります。 特定の IP アドレスに対してこのエラーが発生しているかどうかを検証するには、パブリックにアクセス可能なネットワーク IP アドレスの場所 web サイトを使用できます。

このネットワークの洞察は、Exchange Online サービスのフロントドアの選択に特に影響を与えます。 この洞察に対応するために、ローカルおよび直接ネットワークからの出口を指定する必要があります。その後、DNS 再帰リゾルバーは、そのネットワーク出口の近くに配置する必要があります。

### <a name="exchange-online"></a>Exchange Online

このセクションでは、Exchange Online に関連するテスト結果を示します。

#### <a name="exchange-service-front-door-location"></a>Exchange サービスのフロントドアの場所

使用中の Exchange サービスのフロントドアは、Outlook と同じ方法で識別され、ユーザーの場所からのネットワーク TCP 遅延を測定します。 TCP の遅延が表示され、使用中の Exchange サービスのフロントドアが、現在の場所のサービスのトップドアのリストと比較されます。 最適な Exchange サービスのフロントドアのいずれかが使用されていない場合は、ネットワークの洞察として表示されます。

最適な Exchange サービスフロントドアのいずれかを使用しない場合は、企業ネットワークの出口の前にネットワークバックアウトが発生することがあります。これは、ローカルおよび直接ネットワークを出口にすることをお勧めします。 また、リモート DNS の再帰リゾルバーサーバーを使用して、DNS の再帰リゾルバーサーバーをネットワークの出口に配置することが推奨される場合もあります。

Exchange サービスのフロントドアに対する TCP の遅延 (ms) の向上の可能性を計算します。 これを行うには、テストされたユーザーのオフィスの場所のネットワーク待ち時間を調べて、現在の場所から closets Exchange サービスのフロントドアまで、ネットワークの待機時間を減算します。 違いは、改善につながる可能性がある機会を表します。

#### <a name="best-exchange-service-front-doors-for-your-location"></a>自分の場所に最適な Exchange サービスのフロントドア

これにより、場所に応じた、Exchange サービスのフロントドアの最適な位置が一覧表示されます。

#### <a name="service-front-door-recorded-in-the-client-dns"></a>クライアント DNS に記録されたサービスのフロントドア

これには、移動先の Exchange サービスのフロントドアサーバーの DNS 名と IP アドレスが表示されます。 これは情報のみを対象として提供されており、関連するネットワークの洞察がありません。

### <a name="sharepoint-online"></a>SharePoint Online

このセクションでは、SharePoint Online と OneDrive に関連するテスト結果を示します。

#### <a name="the-service-front-door-location"></a>サービスのフロントドアの場所

使用中の SharePoint サービスのフロントドアは、OneDrive クライアントと同じ方法で識別され、ユーザーのオフィスの場所からのネットワーク TCP 遅延を測定します。

#### <a name="download-speed"></a>ダウンロード速度

SharePoint サービスのフロントドアから、15Mb ファイルのダウンロード速度を測定します。 結果はメガバイト/秒で表示され、 **1 秒**間に SharePoint または OneDrive からダウンロードできるサイズファイルのサイズを示します。 この数は、少なくとも1秒あたりの回線帯域幅の最小値に似ている必要があります。 たとえば、100mbps のインターネット接続を使用している場合は、10 mb/秒 (10MBps) と予想されることがあります。

#### <a name="buffer-bloat"></a>バッファーの膨張

15Mb のダウンロード中に、SharePoint サービスのフロントドアに対する TCP 遅延を測定します。 これは負荷の下の待機時間で、負荷がかかっていない場合の待機時間と比較されます。 負荷の下での待機時間の増加は、多くの場合、コンシューマーネットワークデバイスのバッファーがロードされている (または膨張している) ことに起因します。 ネットワークの洞察は、1000以上の膨張に対して表示されます。

#### <a name="service-front-door-recorded-in-the-client-dns"></a>クライアント DNS に記録されたサービスのフロントドア

これにより、移動先の SharePoint サービスのフロントドアサーバーの DNS 名と IP アドレスが表示されます。 これは情報のみを対象として提供されており、関連するネットワークの洞察がありません。

### <a name="microsoft-teams"></a>Microsoft Teams

このセクションでは、Microsoft Teams に関連するテスト結果を示します。

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>メディア接続 (オーディオ、ビデオ、アプリケーション共有)

これにより、Microsoft Teams サービスのフロントドアへの UDP 接続がテストされます。 これがブロックされている場合、Microsoft Teams は TCP を使用しても動作しますが、音声とビデオは損なわれます。 これらの UDP ネットワークの測定の詳細については、「 [Skype For Business Online でのメディア品質とネットワーク接続のパフォーマンス」の](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)「Microsoft Teams」にも適用されます。

#### <a name="packet-loss"></a>パケット損失

クライアントから Microsoft Teams サービスのフロントドアへの、10秒テストの音声呼び出しで測定された UDP パケット損失を示します。 この値は、パスの **1.00%** 未満である必要があります。

### <a name="latency"></a>遅延

測定された UDP 待機時間を示します。これは **100 ミリ秒**より小さくなければなりません。

#### <a name="jitter"></a>ずれ

測定された UDP ジッターを示します。これは **30 ミリ秒**未満である必要があります。

#### <a name="connectivity"></a>接続

ユーザーのオフィスの場所から、必要なすべての Microsoft 365 ネットワークエンドポイントへの HTTP 接続をテストします。 これらは、で公開され [https://aka.ms/o365ip](https://aka.ms/o365ip) ます。 に接続できない必要なネットワークエンドポイントに対して、ネットワークの洞察が表示されます。

接続 ay は、プロキシサーバー、ファイアウォール、またはエンタープライズネットワーク境界またはクラウドプロキシとして使用されている別のネットワークセキュリティデバイスによってブロックされます。

「」で定義されている、「optimize or allow category」に記載されている必要な各 Microsoft 365 ネットワークエンドポイントで、SSL 証明書をテストし [https://aka.ms/o365ip](https://aka.ms/o365ip) ます。 いずれかのテストで Microsoft SSL 証明書が見つからない場合は、暗号化されたネットワークが仲介ネットワークデバイスによって傍受されている必要があります。 ネットワークの洞察は、傍受されたネットワークエンドポイントに表示されます。

Microsoft によって提供されていない SSL 証明書が見つかった場合は、テストの FQDN と使用中の SSL 証明書の所有者が表示されます。 この SSL 証明書の所有者は、プロキシサーバーのベンダーである場合もあれば、エンタープライズ自己署名証明書の場合もあります。

#### <a name="network-path"></a>ネットワークパス

このセクションでは、Exchange Online サービスのフロントドア、SharePoint Online サービスのフロントドア、Microsoft Teams サービスのフロントドアに対する ICMP traceroute の結果を示します。 これは情報のみを対象として提供されており、関連するネットワークの洞察がありません。 3つの traceroutes が提供されています。 Traceroute から_outlook.office365.com_、顧客の SharePoint フロントエンドに対する traceroute、または_microsoft.sharepoint.com_が提供されていない場合はに、traceroute_に world.tr.teams.microsoft.com するもの。_

## <a name="what-happens-at-each-test-step"></a>各テストステップで行われる処理

### <a name="office-location-identification"></a>オフィスの場所の識別情報

[テストの実行] ボタンをクリックすると、実行中のテストページが表示され、オフィスの場所が特定されます。 所在地は、市区町村、都道府県、および国で入力できます。また、web ブラウザーから検出することもできます。 この値を検出した場合は、web ブラウザーから緯度と経度を要求し、使用する前に300m で300m に対して正確な精度を設定します。 これは、ネットワークパフォーマンスの構築よりも正確に場所を特定する必要がないためです。 

### <a name="javascript-tests"></a>JavaScript テスト

Office の場所を識別した後、JavaScript で TCP レイテンシテストを実行し、使用中の Office 365 サービスのフロントドアサーバーについてサービスのデータを要求します。 完了したら、マップと [詳細] タブで、次の手順の前に表示することができます。

### <a name="download-the-advanced-tests-client-application"></a>高度なテストクライアントアプリケーションをダウンロードする

次に、高度なテストクライアントアプリケーションのダウンロードを開始します。 クライアントアプリケーションを起動するには、ユーザーを使用します。また、.NET Core がインストールされている必要もあります。

### <a name="start-the-advanced-tests-client-application"></a>高度なテストクライアントアプリケーションを開始する

クライアントアプリケーションが開始すると、web ページが更新されて表示され、テストデータが web ページに受信され始めます。 新しいデータが受信されるたびに更新され、受信したデータを確認できます。

### <a name="advanced-tests-completed-and-test-report-upload"></a>高度なテストの完了とテストレポートのアップロード

テストが完了すると、web ページと高度なテストクライアントはどちらもこれを示し、テストレポートにサインインしているユーザーがいる場合は、顧客テナントにアップロードされます。

## <a name="connectivity-reports"></a>接続レポート

サインインすると、以前に実行したレポートを確認できます。 また、それらを共有したり、リストから削除したりすることもできます。

![レポート](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>ネットワーク正常性の状態

これは、microsoft 365 のお客様に影響を与える可能性のある Microsoft のグローバルネットワークの重大な正常性の問題を示しています。

![ネットワーク正常性の状態](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>よくあるご質問 (FAQ)

ここでは、よく寄せられる質問の一部に対する回答を示します。

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>このツールは、Microsoft によってリリースされ、サポートされていますか?

現時点ではプレビューになっており、Microsoft のサポートによって ga リリース状態に達するまで定期的に更新プログラムを提供する予定です。 品質向上のためにフィードバックを提供してください。 このツールの一部として、より詳細な Office 365 ネットワークオンボードガイドを発行することを計画しています。このツールは、テスト結果によって組織用にカスタマイズされています。

### <a name="what-is-required-to-run-the-advanced-test-client"></a>高度なテストクライアントを実行するために必要なこと

高度なテストクライアントには、.NET コア3.1 デスクトップランタイムが必要です。 高度なテストクライアントをインストールせずに実行すると、 [.Net Core 3.1 インストーラページ](https://dotnet.microsoft.com/download/dotnet-core/3.1)に転送されます。 SDK ではなく、ASP.NET Core ランタイムをインストールするようにしてください。これは、ページ上でより上位にある必要があります。 コンピューターに対する管理者のアクセス許可は、.NET コアをインストールするための reuqired です。 

### <a name="what-is-microsoft-365-service-front-door"></a>Microsoft 365 サービスのフロントドアとは

Microsoft 365 service のフロントドアは、Office クライアントとサービスがネットワーク接続を終了する Microsoft のグローバルネットワークにおけるエントリポイントです。 Microsoft 365 への最適なネットワーク接続のために、ネットワーク接続を都市またはメトロの最も近い Microsoft 365 フロントドアに終端することをお勧めします。

注: Microsoft 365 service のフロントドアには、Azure marketplace で利用可能な **Azure Front ドアサービス** 製品との直接の関係はありません。

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>Microsoft 365 サービスのフロントドアの最適なものは何ですか。

最も優れた Microsoft 365 サービスのフロントドア (以前は最適なサービスのフロントドア) は、ネットワーク出口 (一般には、都市またはメトロエリア) に最も近いものです。 Microsoft 365 ネットワークパフォーマンスツールを使用して、使用中の Microsoft 365 サービスのフロントドアと最適なサービスフロントドアの場所を特定します。 使用中のフロントドアが最適なものの1つであることがツールによって決まる場合は、Microsoft のグローバルネットワークへの接続性を期待する必要があります。

### <a name="what-is-an-internet-egress-location"></a>インターネット出口の場所とは

インターネット出口の場所は、ネットワークトラフィックがエンタープライズネットワークから出てインターネットに接続する場所です。 これは、ネットワークアドレス変換 (NAT) デバイスがあり、通常はインターネットサービスプロバイダー (ISP) を使用して接続する場所としても識別されます。 場所とインターネット出口の場所の間に長距離の距離がある場合は、WAN のバックアウトが非常に重要であることがわかります。

## <a name="related-topics"></a>関連トピック

[Microsoft 365 管理センター (プレビュー) でのネットワークパフォーマンスに関する推奨事項](office-365-network-mac-perf-overview.md)

[Microsoft 365 network performance insights (プレビュー)](office-365-network-mac-perf-insights.md)

[Microsoft 365 ネットワーク評価 (プレビュー)](office-365-network-mac-perf-score.md)

[Microsoft 365 ネットワーク接続ロケーションサービス (プレビュー)](office-365-network-mac-location-services.md)
