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
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (プレビュー)

**ネットワークインサイトは** 、Microsoft 365 テナントから収集されたパフォーマンスメトリックであり、テナント内の管理ユーザーだけが表示できます。 Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance> .

インサイトは、オフィスの場所のネットワーク境界の設計に役立ちます。 各インサイトは、ユーザーがテナントにアクセスしている地理的な場所ごとに、特定の一般的な問題のパフォーマンス特性に関するライブの詳細を提供します。

オフィスごとに 6 つの特定のネットワークインサイトが表示される場合があります。

- [バックホールされたネットワークエグレス](#backhauled-network-egress)
- [ネットワーク中継デバイス](#network-intermediary-device)
- [近くの顧客に対して検出されたパフォーマンスの向上](#better-performance-detected-for-customers-near-you)
- [最適でない Exchange Online サービスフロント ドアの使用](#use-of-a-non-optimal-exchange-online-service-front-door)
- [最適でない SharePoint Online サービスのフロント ドアの使用](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [SharePoint フロント ドアからのダウンロード速度が低い](#low-download-speed-from-sharepoint-front-door)
- [中国のユーザー最適なネットワークエグレス](#china-user-optimal-network-egress)

テナントには、2 つのテナント レベルのネットワークインサイトが表示される場合があります。 これらは、生産的スコア ページにも表示されます。

- [接続の問題の影響を受け、Exchange のサンプル接続](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [接続の問題の影響を受け、SharePoint のサンプル接続](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Microsoft 365 管理センターのネットワークの分析情報、パフォーマンスに関する推奨事項、評価は現在プレビュー状態であり、機能プレビュー プログラムに登録されている Microsoft 365 テナントでのみ利用できます。

## <a name="backhauled-network-egress"></a>バックホールされたネットワークエグレス

この分析情報は、ネットワークインサイト サービスが、特定のユーザーの場所からネットワーク出口までの距離が 500 マイル (800 km) を超えると検出した場合に表示されます。これは、Microsoft 365 トラフィックが共通のインターネット エッジ デバイスまたはプロキシにバックホール中であることを示します。

このインサイトは、一部の概要ビューでは "エグレス" と省略されます。

![バックホールされたネットワークエグレス](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>シナリオ

これは、オフィスの場所とネットワーク出口の間の距離が 500 マイル (800 キロメートル) を超える距離を表します。 オフィスの場所は難読化されたクライアント コンピューターの場所によって識別され、ネットワーク出口の場所は、場所データベースへの逆 IP アドレスを使用して識別されます。 コンピューターで Windows 位置情報サービスが無効になっていると、オフィスの場所が不正確になる可能性があります。 逆 IP アドレス データベース情報が不正確な場合は、ネットワーク出口の場所が不正確になる可能性があります。

このインサイトの詳細には、オフィスの場所、その場所のテナント ユーザーの推定割合、現在のネットワーク出口の場所、出口の場所の関連性、場所と現在の出口ポイントの間の距離、条件が最初に検出された日付、条件が解決された日付が含まれます。

### <a name="what-should-i-do"></a>どうすればよいですか?

この洞察のために、接続が Microsoft のグローバル ネットワークと最も近い Microsoft 365 サービスのフロント ドアに最適にルーティングできるよう、オフィスの場所に近いネットワーク出口をお勧めします。 ユーザーのオフィスの場所に近いネットワーク出口を用意することで、Microsoft が今後、プレゼンスのネットワーク ポイントと Microsoft 365 サービス フロント ドアの両方を拡張する中で、今後のパフォーマンスが向上します。

この問題を解決する方法の詳細については、「Office [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) [365 Network Connectivity Principles」](microsoft-365-network-connectivity-principles.md)の「ネットワーク接続をローカルに送信する」を参照してください。

## <a name="network-intermediary-device"></a>ネットワーク中継デバイス

この分析情報は、ユーザーと Microsoft のネットワークの間でデバイスが検出され、Office 365 のユーザー エクスペリエンスに影響を与える可能性がある場合に表示されます。 これらは、Microsoft データセンター宛ての特定の Microsoft 365 ネットワーク トラフィックに対してバイパスをお勧めします。 この推奨事項については [、Microsoft 365 ネットワーク接続の原則でさらに説明されています。](microsoft-365-network-connectivity-principles.md)

### <a name="what-does-this-mean"></a>シナリオ

プロキシ サーバー、VPN、データ損失防止デバイスなどのネットワーク中継デバイスは、トラフィックが中間的に使用される Microsoft 365 クライアントのパフォーマンスと安定性に影響を与える可能性があります。

### <a name="what-should-i-do"></a>どうすればよいですか?

Microsoft 365 ネットワーク トラフィックの処理をバイパスするために検出されたネットワーク中継デバイスを構成します。

## <a name="better-performance-detected-for-customers-near-you"></a>近くの顧客に対して検出されたパフォーマンスの向上

この分析情報は、ネットワークインサイト サービスが、このオフィスの場所にある組織内のユーザーよりも、多数の顧客が施設エリア内のユーザーのパフォーマンスが優れたと検出した場合に表示されます。

この分析情報は、一部の概要ビューでは "ピア" と省略されます。

![相対的なネットワーク パフォーマンス](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>シナリオ

この分析情報は、このオフィスの場所と同じ市にある Microsoft 365 ユーザーの集計パフォーマンスを調べています。 この分析情報は、ユーザーの平均待機時間が、隣接するテナントの平均待機時間よりも 10% 長い場合に表示されます。

### <a name="what-should-i-do"></a>どうすればよいですか?

この状態には、企業ネットワークまたは ISP の待機時間、ボトルネック、アーキテクチャ設計の問題など、さまざまな理由が考えらたはずです。 オフィス ネットワークと現在の Microsoft 365 フロント ドア間のルートの各ホップ間の遅延を調べる。 詳細については [、「Microsoft 365 Network Connectivity Principles」を参照してください](microsoft-365-network-connectivity-principles.md)。

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>最適でない Exchange Online サービスフロント ドアの使用

この分析情報は、ネットワークインサイト サービスが、特定の場所のユーザーが最適な Exchange Online サービスのフロント ドアに接続していないと検出した場合に表示されます。

この分析情報は、一部の概要ビューでは "ルーティング" と省略されます。

![最適でない EXO フロント ドア](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>シナリオ

優れたパフォーマンスを備え、オフィス所在地の都市からの使用に適した Exchange Online サービスフロント ドアの一覧を示します。 現在のテストで、このリストに記載されていない Exchange Online サービスのフロント ドアの使用が示されている場合は、この推奨事項を呼び出します。

### <a name="what-should-i-do"></a>どうすればよいですか?

最適でない Exchange Online サービスのフロント ドアの使用は、企業のネットワーク出口の前のネットワーク バックホールが原因で発生する可能性があります。その場合は、ローカルおよび直接のネットワークエグレスをお勧めします。 また、リモート DNS 再帰リゾルバー サーバーの使用が原因で発生する可能性もあります。この場合、DNS 再帰リゾルバー サーバーをネットワーク出口に合わせて配置することをお勧めします。

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>最適でない SharePoint Online サービスのフロント ドアの使用

この分析情報は、ネットワークインサイト サービスが、特定の場所のユーザーが最も近い SharePoint Online サービスのフロント ドアに接続していないと検出した場合に表示されます。

この分析情報は、一部の概要ビューでは "Afd" と省略されます。

![最適でない SPO フロント ドア](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>シナリオ

テスト クライアントが接続している SharePoint Online サービスのフロント ドアを特定します。 次に、オフィスの場所の都市について、その都市の予想される SharePoint Online サービスのフロント ドアと比較します。 一致しない場合は、この推奨事項を作成します。

### <a name="what-should-i-do"></a>どうすればよいですか?

最適でない SharePoint Online サービスのフロント ドアの使用は、企業ネットワーク出口の前のネットワーク バックホールが原因で発生する可能性があります。その場合は、ローカルおよび直接のネットワークエグレスをお勧めします。 また、リモート DNS 再帰リゾルバー サーバーの使用が原因で発生する可能性もあります。この場合、DNS 再帰リゾルバー サーバーをネットワーク出口に合わせて配置することをお勧めします。

## <a name="low-download-speed-from-sharepoint-front-door"></a>SharePoint フロント ドアからのダウンロード速度が低い

この分析情報は、ネットワークインサイト サービスが、特定のオフィスの場所と SharePoint Online 間の帯域幅が 1 MBps 未満を検出した場合に表示されます。

この分析情報は、一部の概要ビューでは "スループット" と省略されます。

### <a name="what-does-this-mean"></a>シナリオ

ユーザーが SharePoint Online および OneDrive for Business サービスフロント ドアから取得できるダウンロード速度は、メガバイト/秒 (MBps) 単位で測定されます。 この値が 1 MBps 未満の場合は、この分析情報が提供されます。

### <a name="what-should-i-do"></a>どうすればよいですか?

ダウンロード速度を向上させるために、帯域幅を増やす必要がある場合があります。 または、オフィスの場所にあるユーザー コンピューターと SharePoint Online サービスのフロント ドアの間でネットワークの混雑が発生する可能性があります。 これは、混雑した損失と呼ばれる場合があります。また、十分な帯域幅が利用可能な場合でも、ユーザーが利用できるダウンロード速度が制限されます。

## <a name="china-user-optimal-network-egress"></a>中国のユーザー最適なネットワークエグレス

この分析情報は、中国のユーザーが他の地理的な場所にある Microsoft 365 テナントに接続している場合に表示されます。 

### <a name="what-does-this-mean"></a>シナリオ

組織にプライベート WAN 接続がある場合は、次の場所のインターネットへのネットワークエグレスがある中国のオフィスの場所からネットワーク WAN 回線を構成することをお勧めします。

- 香港特別行政区
- 日本
- 台湾
- 韓国
- シンガポール
- マレーシア

これらの場所よりもユーザーから離れた場所にインターネットエグレスを使用すると、パフォーマンスが低下し、中国の出口では、境界を越えた輻輳のために待ち時間が長く接続の問題が発生する可能性があります。

### <a name="what-should-i-do"></a>どうすればよいですか?

このインサイトに関連するパフォーマンスの問題を軽減する方法の詳細については、中国ユーザー向け [Microsoft 365 グローバル](microsoft-365-networking-china.md)テナントのパフォーマンスの最適化を参照してください。

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>接続の問題の影響を受け、Exchange のサンプル接続

この分析情報は、サンプリングされた接続の 50% 以上が影響を受け取る場合に表示されます。 影響は、Exchange 評価がサンプルごとに 60% 未満であることによって定義されます。

### <a name="what-does-this-mean"></a>シナリオ

これは、ユーザーの大部分が Exchange Online に接続する Outlook でユーザー エクスペリエンスの問題が発生している可能性が高いことを示しています。 サンプルの割合は、60 ポイントを下回るユーザーの割合を表している可能性があります。  

### <a name="what-should-i-do"></a>どうすればよいですか?

まだ有効にしていない場合は、オフィスの場所のネットワーク接続の可視性を有効にする。 Exchange に影響を与えるネットワーク接続の不十分な影響を受け、ユーザーを Microsoft のネットワークに接続する各オフィスでネットワーク境界を改善する方法を見つける必要があります。

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>接続の問題の影響を受け、SharePoint のサンプル接続

この分析情報は、サンプリングされた接続の 50% 以上が影響を受け取る場合に表示されます。 影響は、SharePoint 評価がサンプルごとに 40% 未満であることによって定義されます。

### <a name="what-does-this-mean"></a>シナリオ

これは、ユーザーの大部分が SharePoint と OneDrive でユーザー エクスペリエンスの問題を経験している可能性が高いことを示しています。 サンプルの割合は、40 ポイントを下回るユーザーの割合を表している可能性があります。  

### <a name="what-should-i-do"></a>どうすればよいですか?

まだ有効にしていない場合は、オフィスの場所のネットワーク接続の可視性を有効にする。 SharePoint に影響を与える低品質ネットワーク接続の影響を受け、ユーザーを Microsoft のネットワークに接続する各オフィスでネットワーク境界を改善する方法を見つける必要があります。

## <a name="related-topics"></a>関連項目

[Microsoft 365 管理センターでのネットワーク接続 (プレビュー)](office-365-network-mac-perf-overview.md)

[Microsoft 365 ネットワーク評価 (プレビュー)](office-365-network-mac-perf-score.md)

[Microsoft 365 ネットワーク接続テスト ツール (プレビュー)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (プレビュー)](office-365-network-mac-location-services.md)
