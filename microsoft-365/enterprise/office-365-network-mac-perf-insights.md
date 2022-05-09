---
title: Microsoft 365 ネットワーク インサイト
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/06/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 ネットワーク インサイト
ms.openlocfilehash: 429b066a7132cb29f2a35d43857534695391d33c
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806950"
---
# <a name="microsoft-365-network-insights"></a>Microsoft 365 ネットワーク インサイト

**ネットワーク分析情報** は、Microsoft 365 テナントから収集されたパフォーマンス メトリックであり、テナント内の管理者ユーザーのみが表示できます。 インサイトは、Microsoft 365 管理 センターに<https://portal.microsoft.com/adminportal/home#/networkperformance>表示されます。

分析情報は、オフィスの場所のネットワーク境界の設計を支援することを目的としています。 各分析情報は、ユーザーがテナントにアクセスしている地理的な場所ごとに、特定の一般的な問題のパフォーマンス特性に関するライブの詳細を提供します。

各オフィスの場所に対して表示される可能性がある 6 つの特定のネットワーク分析情報があります。

- [バックホールされたネットワークエグレス](#backhauled-network-egress)
- [ネットワーク中継デバイス](#network-intermediary-device)
- [近くの顧客に対して検出されるパフォーマンスの向上](#better-performance-detected-for-customers-near-you)
- [最適でないExchange Onlineサービス フロント ドアの使用](#use-of-a-non-optimal-exchange-online-service-front-door)
- [最適でないSharePointオンライン サービス フロント ドアの使用](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [SharePointフロント ドアからのダウンロード速度が低い](#low-download-speed-from-sharepoint-front-door)
- [中国ユーザーの最適なネットワークエグレス](#china-user-optimal-network-egress)

テナントに対して表示できるテナント レベルのネットワーク 分析情報は 2 つあります。

- [接続の問題の影響を受けるサンプリングされた接続をExchangeする](#exchange-sampled-connections-affected-by-connectivity-issues)
- [接続の問題の影響を受けるサンプリングされた接続をSharePointする](#sharepoint-sampled-connections-affected-by-connectivity-issues)

これらの分析情報は、生産性スコア ページにも表示されます。

>[!IMPORTANT]
>Microsoft 365 管理 センターのネットワーク分析情報、パフォーマンスに関する推奨事項、および評価は現在プレビュー状態にあり、機能プレビュー プログラムに登録されているMicrosoft 365テナントでのみ使用できます。

## <a name="backhauled-network-egress"></a>バックホールされたネットワークエグレス

この分析情報は、特定のユーザーの場所からネットワークエグレスまでの距離が 500 マイル (800 キロメートル) を超えるとネットワーク 分析情報サービスが検出した場合に表示されます。 これは、Microsoft 365 トラフィックが共通のインターネット エッジ デバイスまたはプロキシにバックホールされていることを示している可能性があります。

この分析情報は、一部の概要ビューでは "Egress" と省略されています。

> [!div class="mx-imgBorder"]
> ![バックホールされたネットワークエグレス。](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

これにより、オフィスの場所とネットワークエグレスの間の距離が 500 マイル (800 キロメートル) を超えていることがわかります。 Office の場所は難読化されたクライアント コンピューターの場所によって識別され、ネットワークエグレスの場所は逆 IP アドレスから場所データベースに対して識別されます。 コンピューターで位置情報サービスWindows無効になっていると、オフィスの場所が不正確になる可能性があります。 逆 IP アドレス データベース情報が不正確な場合は、ネットワークエグレスの場所が不正確になる可能性があります。

この分析情報の詳細は次のとおりです。

- 勤務先の住所
- 場所でのテナント ユーザーの合計の推定割合
- 現在のネットワーク エグレスの場所
- エグレスの場所の関連性
- 場所と現在のエグレス ポイント間の距離
- 条件が最初に検出された日付
- 条件が解決された日付

### <a name="what-should-i-do"></a>どうすればよいですか?

オフィスの場所にできるだけ近いネットワーク エグレスをお勧めします。  Microsoft 365トラフィックは、Microsoft のグローバル ネットワークと最も近いMicrosoft 365サービス フロント ドアに最適にルーティングする必要があります。 ユーザーのオフィスの場所に近いネットワークエグレスを使用すると、Microsoft が将来、ネットワークのプレゼンス ポイントとMicrosoft 365サービス フロント ドアの両方を拡張するため、パフォーマンスを向上させることもできます。

この問題を解決する方法の詳細については、「[Microsoft 365 ネットワーク接続の原則」でネットワーク接続をローカルに](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)Egressする方法に関[するページを参照](microsoft-365-network-connectivity-principles.md)してください。

## <a name="network-intermediary-device"></a>ネットワーク中継デバイス

この分析情報は、ユーザーと Microsoft のネットワーク間でデバイスが検出された場合に表示されます。 待機時間に依存するMicrosoft 365ネットワーク トラフィックは、このようなデバイスをバイパスすることをお勧めします。 この推奨事項については、「[Microsoft 365 ネットワーク接続の原則」](microsoft-365-network-connectivity-principles.md)でさらに説明します。

私たちが示すネットワーク中間分析情報の 1 つは、Exchange、SharePoint、およびTeamsの重要なMicrosoft 365ネットワーク エンドポイントがネットワーク中間デバイスによってインターセプトおよび復号化された場合の SSL ブレークと検査です。

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

プロキシ サーバー、VPN、データ損失防止デバイスなどのネットワーク中継デバイスは、トラフィックが中間処理されるMicrosoft 365 クライアントのパフォーマンスと安定性に影響を与える可能性があります。

### <a name="what-should-i-do"></a>どうすればよいですか?

Microsoft 365ネットワーク トラフィックの処理をバイパスするために検出されたネットワーク中継デバイスを構成します。

## <a name="better-performance-detected-for-customers-near-you"></a>近くの顧客に対して検出されるパフォーマンスの向上

この分析情報は、ネットワーク分析情報サービスが、このオフィスの場所のユーザーよりも、メトロエリア内のかなりの数の顧客のパフォーマンスが向上していることを検出した場合に表示されます。

この分析情報は、一部の概要ビューでは "Peers" と略されます。

> [!div class="mx-imgBorder"]
> ![相対ネットワーク パフォーマンス。](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

この分析情報は、このオフィスの場所と同じ都市のMicrosoft 365顧客の集計パフォーマンスを調べます。 この分析情報は、ユーザーの平均待機時間が近隣テナントの平均待機時間よりも 10% 大きい場合に表示されます。

### <a name="what-should-i-do"></a>どうすればよいですか?

この状態には、企業ネットワークや ISP の待機時間、ボトルネック、アーキテクチャ設計の問題など、さまざまな理由が考えられます。 オフィス ネットワークと現在のMicrosoft 365フロント ドアの間のルート内の各ホップ間の待機時間を調べます。 詳細については、「[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)」を参照してください。

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>最適でないExchange Onlineサービス フロント ドアの使用

この分析情報は、特定の場所のユーザーが最適なExchange Onlineサービス フロント ドアに接続されていないことがネットワーク 分析情報サービスによって検出された場合に表示されます。

この分析情報は、一部の概要ビューでは "ルーティング" と略されます。

> [!div class="mx-imgBorder"]
> ![最適でない EXO フロント ドア。](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

オフィスの場所の都市からの使用に適したExchange Onlineサービス フロント ドアを一覧表示します。 現在のテストで、この一覧にないExchange Onlineサービス フロント ドアの使用が示されている場合は、この推奨事項を呼び出します。

### <a name="what-should-i-do"></a>どうすればよいですか?

最適でないExchange Onlineサービス フロント ドアの使用は、ネットワーク バックホールによって発生する可能性があります。その場合は、ローカルおよびダイレクト ネットワークエグレスをお勧めします。 リモート DNS 再帰リゾルバー サーバーを実装している場合は、サーバー構成をネットワーク エグレスに合わせることをお勧めします。

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>最適でないSharePointオンライン サービス フロント ドアの使用

この分析情報は、特定の場所のユーザーが最も近い SharePoint Online サービス フロント ドアに接続していないと network insights サービスが検出した場合に表示されます。

この分析情報は、一部の概要ビューでは "Afd" と省略されています。

> [!div class="mx-imgBorder"]
> ![最適でない SPO フロント ドア。](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

テスト クライアントが接続しているSharePoint Online サービス フロント ドアを特定します。 次に、オフィスの所在地の都市では、それをその都市の想定SharePointオンライン サービス フロント ドアと比較します。 一致しない場合は、この推奨事項を行います。

### <a name="what-should-i-do"></a>どうすればよいですか?

最適でないSharePoint Online サービス フロント ドアの使用は、企業ネットワークエグレスの前のネットワーク バックホールによって発生する可能性があります。その場合は、ローカルおよびダイレクト ネットワークエグレスをお勧めします。 また、リモート DNS 再帰リゾルバー サーバーを使用している場合、DNS 再帰リゾルバー サーバーをネットワーク エグレスに配置することをお勧めします。

## <a name="low-download-speed-from-sharepoint-front-door"></a>SharePointフロント ドアからのダウンロード速度が低い

この分析情報は、特定のオフィスの場所とオンラインSharePoint間の帯域幅が 1 MBps 未満であることがネットワーク 分析情報サービスによって検出された場合に表示されます。

この分析情報は、一部の概要ビューでは "スループット" と略されます。

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

ユーザーが SharePoint Online およびOneDrive for Businessサービス フロント ドアから取得できるダウンロード速度は、1 秒あたりメガバイト (MBps) で測定されます。 この値が 1 MBps 未満の場合は、この分析情報を提供します。

### <a name="what-should-i-do"></a>どうすればよいですか?

ダウンロード速度を向上させるには、帯域幅を増やす必要がある場合があります。 または、オフィスの場所にあるコンピューターと SharePoint Online サービス フロント ドアの間でネットワークが混雑している可能性があります。 この条件により、十分な帯域幅が利用できる場合でも、ユーザーが使用できるダウンロード速度が制限されます。

## <a name="china-user-optimal-network-egress"></a>中国ユーザーの最適なネットワークエグレス

この分析情報は、組織に中国のユーザーが他の地理的な場所にあるMicrosoft 365 テナントに接続している場合に表示されます。

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

組織にプライベート WAN 接続がある場合は、次のいずれかの場所でインターネットへのネットワークエグレスを持つ中国のオフィスの場所からネットワーク WAN 回線を構成することをお勧めします。

- 香港特別行政区
- 日本
- 台湾
- 韓国
- シンガポール
- マレーシア

これらの場所よりもユーザーから離れたインターネットエグレスはパフォーマンスを低下させ、中国のエグレスは、クロスボーダー混雑のために待機時間と接続の問題を引き起こす可能性があります。

### <a name="what-should-i-do"></a>どうすればよいですか?

この分析情報に関連するパフォーマンスの問題を軽減する方法の詳細については、「[中国ユーザーのグローバル テナント パフォーマンスの最適化Microsoft 365](microsoft-365-networking-china.md)」を参照してください。

## <a name="exchange-sampled-connections-affected-by-connectivity-issues"></a>接続の問題の影響を受けるサンプリングされた接続をExchangeする

この分析情報は、サンプリングされた接続の 50% 以上が影響を受けた場合に表示されます。 影響は、サンプルごとに 60% を下回るExchange評価によって定義されます。

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

これは、ほとんどのユーザーがExchange Onlineへの接続に関する問題Outlook発生している可能性が高いことを示しています。 サンプルの割合は、60 ポイント未満を示すユーザーの割合を表します。  

### <a name="what-should-i-do"></a>どうすればよいですか?

まだ行っていない場合は、Office の場所ネットワーク接続の可視性を有効にします。 ネットワーク接続の問題の影響を受けるオフィスを特定し、ユーザーを Microsoft のネットワークに接続する各ネットワーク境界を改善する方法を見つけます。

## <a name="sharepoint-sampled-connections-affected-by-connectivity-issues"></a>接続の問題の影響を受けるサンプリングされた接続をSharePointする

この分析情報は、サンプリングされた接続の 50% 以上が影響を受けた場合に表示されます。 影響は、サンプルごとに 40% を下回るSharePoint評価によって定義されます。

### <a name="what-does-this-mean"></a>これはどういう意味ですか?

これは、ほとんどのユーザーが、SharePointとOneDriveに関する問題が発生している可能性があることを示しています。 サンプルの割合は、40 ポイント未満を示すユーザーの割合を表します。  

### <a name="what-should-i-do"></a>どうすればよいですか?

まだ行っていない場合は、Office の場所ネットワーク接続の可視性を有効にします。 ネットワーク接続の問題の影響を受けるオフィスを特定し、ユーザーを Microsoft のネットワークに接続する各ネットワーク境界を改善する方法を見つけます。

## <a name="related-topics"></a>関連項目

[Microsoft 365 管理 センターでのネットワーク接続](office-365-network-mac-perf-overview.md)

[Microsoft 365 ネットワーク評価](office-365-network-mac-perf-score.md)

[Microsoft 365ネットワーク接続テスト ツール](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 ネットワーク接続場所サービス](office-365-network-mac-location-services.md)
