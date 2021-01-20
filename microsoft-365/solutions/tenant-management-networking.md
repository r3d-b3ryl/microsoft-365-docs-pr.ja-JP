---
title: 手順 2.  エンタープライズ テナント向け Microsoft 365 の最適なネットワーク
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントへのネットワーク アクセスを最適化します。
ms.openlocfilehash: 1e57911a6e8c51af3ae00ff0f9053bf9273e0e17
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908649"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>手順 2. エンタープライズ テナント向け Microsoft 365 の最適なネットワーク

Microsoft 365 enterprise には、Teams、Exchange Online、Microsoft Intune などのクラウド生産性向上アプリと、Microsoft Azure の多くの ID およびセキュリティ サービスが含まれています。 これらのクラウドベースのサービスはすべて、オンプレミス ネットワーク上またはインターネット上の任意の場所にあるクライアント デバイスからの接続のセキュリティ、パフォーマンス、および信頼性に依存します。 

テナントのネットワーク アクセスを最適化するには、次の作業を行う必要があります。

- オンプレミス ユーザーと Microsoft グローバル ネットワークに最も近い場所との間のパスを最適化します。
- リモート アクセス VPN ソリューションを使用しているリモート ユーザーの Microsoft グローバル ネットワークへのアクセスを最適化します。
- Network Insights を使用して、オフィスの場所のネットワーク境界を設計します。
- Office 365 CDN を使用して、SharePoint サイトでホストされている特定のアセットへのアクセスを最適化します。
- エンドポイントの一覧を使用して Microsoft 365 の信頼されたトラフィックの処理をバイパスし、変更が行われた場合にリストの更新を自動化するプロキシおよびネットワーク エッジ デバイスを構成します。

## <a name="enterprise-on-premises-workers"></a>エンタープライズ オンプレミス ワーカー

エンタープライズ ネットワークの場合は、クライアントと最も近い Microsoft 365 エンドポイント間で最高パフォーマンスのネットワーク アクセスを有効にすることで、エンド ユーザー エクスペリエンスを最適化する必要があります。 エンド ユーザー エクスペリエンスの品質は、ユーザーが使用しているアプリケーションのパフォーマンスと応答性に直接関係します。 たとえば、Microsoft Teams は待機時間が短く、ユーザーの電話、会議、共有画面のコラボレーションが不具合の発生を抑える必要があります。

ネットワーク設計の主な目標は、クライアント デバイスから Microsoft グローバル ネットワークへの往復時間 (RTT) を短縮することで待機時間を最小限に抑える必要があります。これは、Microsoft のパブリック ネットワーク バックボーンで、Microsoft のすべてのデータセンターを低待機時間で相互接続するパブリック ネットワーク バックボーンで、フロント ドアと呼ばれる高可用性クラウド アプリケーション エントリ ポイントが世界中に広がっています。

従来のエンタープライズ ネットワークの例を次に示します。

![インターネットへの集中アクセスを備え、従来のエンタープライズ ネットワーク](../media/tenant-management-overview/tenant-management-networking-traditional.png)

この図では、ブランチ オフィスはワイド エリア ネットワーク (WAN) デバイスと WAN バックボーンを介して中央オフィスに接続します。 インターネット アクセスは、中央オフィスとインターネット サービス プロバイダー (ISP) のネットワーク エッジにあるセキュリティ デバイスまたはプロキシ デバイスを介して行います。 インターネット上で、Microsoft グローバル ネットワークには、世界中の地域に一連のフロント ドアがあります。 組織は、トラフィックの追加パケット処理とセキュリティのために中間の場所を使用できます。 組織の Microsoft 365 テナントは、Microsoft グローバル ネットワーク内に位置します。

Microsoft 365 クラウド サービスのこの構成の問題は次のとおりです。

- ブランチ オフィスのユーザーの場合、トラフィックはローカル以外のフロント ドアに送信され、待機時間が増加します。
- 中間の場所にトラフィックを送信すると、信頼されたトラフィックで重複するパケット処理を実行するネットワーク ヘアピンが作成され、待機時間が増加します。
- ネットワーク エッジ デバイスは、信頼されたトラフィックで不要で重複するパケット処理を実行し、待機時間を増加します。

Microsoft 365 のネットワーク パフォーマンスの最適化は複雑である必要はありません。 いくつかの主要な原則に従って、最高のパフォーマンスを得る可能性があります。

- Microsoft 365 ネットワーク トラフィックを特定します。これは、Microsoft クラウド サービス宛ての信頼されたトラフィックです。
- ユーザーが Microsoft 365 に接続する各場所からインターネットへの Microsoft 365 ネットワーク トラフィックのローカルブランチエグレスを許可します。
- ネットワーク ヘアピンを使用しないようにします。
- Microsoft 365 トラフィックがプロキシとパケット検査デバイスをバイパスできます。

これらの原則を実装すると、Microsoft 365 向けに最適化されたエンタープライズ ネットワークを利用できます。

![Microsoft 365 向けに最適化されたエンタープライズ ネットワーク](../media/tenant-management-overview/tenant-management-networking-optimized.png)

この図では、ブランチ オフィスはソフトウェア定義 WAN デバイス (SDWAN) デバイスを介して独自のインターネット接続を確立し、信頼できる Microsoft 365 トラフィックを地域で最も近いフロント ドアに送信します。 中央オフィスでは、信頼できる Microsoft 365 トラフィックはセキュリティ デバイスまたはプロキシ デバイスをバイパスし、中間デバイスは使用されなくなりました。

最適化された構成が従来のエンタープライズ ネットワークの待機時間の問題を解決する方法を次に示します。

- 信頼された Microsoft 365 トラフィックは WAN バックボーンをスキップし、すべてのオフィスのローカル フロント ドアに送信され、待機時間が短縮されます。
- 重複するパケット処理を実行するネットワーク ヘアピンは、Microsoft 365 の信頼されたトラフィックではスキップされ、待機時間が減少します。
- 不要で重複するパケット処理を実行するネットワーク エッジ デバイスは、Microsoft 365 の信頼されたトラフィックではスキップされ、待機時間が短縮されます。

詳細については [、Microsoft 365 ネットワーク接続の概要を参照してください](../enterprise/microsoft-365-networking-overview.md)。

## <a name="remote-workers"></a>リモート ワーカー

リモート ワーカーが従来の VPN クライアントを使用して組織ネットワークへのリモート アクセスを取得している場合は、VPN クライアントがスプリット トンネリング サポートを備えていることを確認してください。 スプリット トンネリングを使用しない場合、すべてのリモート作業トラフィックは VPN 接続を介して送信され、そこで組織のエッジ デバイスに転送されて処理され、インターネット上で送信される必要があります。 次に例を示します。

![トンネリングのない VPN クライアントからのネットワーク トラフィック](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

この図では、Microsoft 365 トラフィックは組織を通る間接的なルートを通る必要があります。このルートは、VPN クライアントの物理的な場所から遠く離れた Microsoft グローバル ネットワークのフロント ドアに転送される可能性があります。 この間接パスにより、ネットワーク トラフィックが遅延し、全体的なパフォーマンスを低下させます。 

スプリッ トトンネリングを使用すると、VPN クライアントを構成して、特定の種類のトラフィックが VPN 接続を介して、組織ネットワークに送信されることを除外できます。

Microsoft 365 クラウドリソースへのアクセスを最適化するには、VPN 接続を介して、**最適化** カテゴリの Microsoft 365 エンドポイントへのトラフィックを除外するようにスプリット トンネリング VPN クライアントを構成します。 詳細については[](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)[、365 Officeカテゴリと分割トン](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)ネリング用の最適化カテゴリ エンドポイントの一覧を参照してください。

スプリット トンネリングの結果として生じるトラフィック フローを次に示します。このトラフィックは、Microsoft 365 クラウド アプリへのトラフィックのほとんどが VPN 接続をバイパスします。

![トンネリングのある VPN クライアントからのネットワーク トラフィック](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

この図では、VPN クライアントは、インターネットを通して直接、および Microsoft グローバル ネットワークに最も近いフロント ドアに Microsoft 365 クラウド サービスの重要なトラフィックを送信および受信します。

詳細とガイダンスについては、「[VPN スプリット トンネリングを使用してリモート ユーザーの Office 365 の接続を最適化する](../enterprise/microsoft-365-vpn-split-tunnel.md)」をご覧ください。

## <a name="using-network-insights-preview"></a>ネットワーク インサイトの使用 (プレビュー)

ネットワークインサイトは、Microsoft 365 テナントから収集されたパフォーマンス メトリックで、オフィスの場所のネットワーク境界を設計するのに役立ちます。 各インサイトは、オンプレミスのユーザーがテナントにアクセスしている地理的な場所ごとに、指定された問題のパフォーマンス特性に関するライブの詳細を提供します。

テナントには、次の 2 つのテナント レベルのネットワークインサイトが表示される場合があります。

- [接続の問題の影響を受け、Exchange のサンプル接続](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [接続の問題の影響を受け、SharePoint のサンプル接続](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

各オフィスの場所に関する特定のネットワークインサイトを次に示します。

- [バックホールされたネットワークエグレス](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [近くの顧客に対して検出されたパフォーマンスの向上](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [最適でない Exchange Online サービスフロント ドアの使用](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [最適でない SharePoint Online サービスフロント ドアの使用](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [SharePoint フロント ドアからのダウンロード速度が低い](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [中国のユーザー最適なネットワークエグレス](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Microsoft 365 管理センターのネットワークの分析情報、パフォーマンスに関する推奨事項、評価は、現在プレビュー状態です。 機能プレビュー プログラムに登録されている Microsoft 365 テナントでのみ使用できます。

詳細については [、「Microsoft 365 Network Insights」を参照してください](../enterprise/office-365-network-mac-perf-insights.md)。

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>Office 365 CDN を使用した SharePoint のパフォーマンス

クラウドベースのコンテンツ配信ネットワーク (CDN) を使用すると、読み込み時間を短縮し、帯域幅を節約し、応答速度を速くすることができます。 CDN は、グラフィック ファイルやビデオ ファイルなどの静的アセットを要求するブラウザーの近くにキャッシュすることでパフォーマンスを向上させます。これにより、ダウンロードの速度を上げ、待機時間を短縮できます。 Microsoft 365 E3 および E5 の SharePoint に付属する組み込みの Office 365 コンテンツ配信ネットワーク (CDN) を使用して静的アセットをホストし、SharePoint ページのパフォーマンスを向上させることができます。

Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。 Office 365 CDN でホストするコンテンツの種類に応じて、パブリックの配信元、プライベートの配信元、または両方を追加できます。

展開および構成すると、Office 365 CDN はパブリックおよびプライベートの配信元からアセットをアップロードし、インターネット上に配置されたユーザーに高速にアクセスできます。

![Office 365 CDN の展開](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN の展開")

詳細については [、「SharePoint Online で Office 365 CDN](../enterprise/use-microsoft-365-cdn-with-spo.md)を使用する」を参照してください。

## <a name="automated-endpoint-listing"></a>エンドポイントの自動一覧

オンプレミスのクライアント、エッジ デバイス、およびクラウドベースのパケット分析サービスが信頼できる Microsoft 365 トラフィックの処理をスキップするには、Microsoft 365 サービスに対応するエンドポイントのセット (IP アドレス範囲と DNS 名) を使用して構成する必要があります。 これらのエンドポイントは、ファイアウォールや他のエッジ セキュリティ デバイス、クライアント コンピューターがプロキシをバイパスする PAC ファイル、ブランチ オフィスの SD-WAN デバイスで手動で構成できます。 ただし、エンドポイントは時間の間に変化し、これらの場所でエンドポイント リストを継続的に手動で保守する必要があります。

クライアント PAC ファイルとネットワーク デバイスで Microsoft 365 エンドポイントの一覧と変更管理を自動化するには [、Office 365 IP アドレス](../enterprise/microsoft-365-ip-web-service.md)と URL REST ベースの Web サービスを使用します。 このサービスは、Microsoft 365 のネットワーク トラフィックをより適切に識別して区別するのに役立ちます。これにより、最新の変更を評価、構成、および最新の状態に簡単に更新できます。

PowerShell、Python、または他の言語を使用して、時間のたつ間にエンドポイントに対する変更を判断し、PAC ファイルとエッジ ネットワーク デバイスを構成できます。

基本的なプロセスは次の処理です。

1. Office 365 IP アドレスと URL Web サービス、および選択した構成メカニズムを使用して、PAC ファイルとネットワーク デバイスを Microsoft 365 エンドポイントの現在のセットで構成します。
2. 毎日定期的に実行してエンドポイントの変更を確認するか、通知方法を使用します。
3. 変更が検出された場合は、クライアント コンピューターの PAC ファイルを再生成して再配布し、ネットワーク デバイスに変更を加えます。

詳細については、「Office [365 IP アドレスと URL Web サービス」を参照してください](../enterprise/microsoft-365-ip-web-service.md)。

## <a name="results-of-step-2"></a>手順 2 の結果

最適なネットワークを使用する Microsoft 365 テナントについては、次の点を決定しました。

- すべてのブランチ オフィスにインターネット接続を追加し、ネットワーク ヘアピンを排除して、オンプレミス ユーザーのネットワーク パフォーマンスを最適化する方法。
- 継続的な更新プログラム (エンタープライズ ネットワークに最適) を含む、クライアント ベースの PAC ファイルとネットワーク デバイスとサービスに対して、信頼されたエンドポイントの自動登録情報を実装する方法について説明します。
- オンプレミス リソースへのリモート ワーカーのアクセスをサポートする方法。
- Network Insights の使い方
- Office 365 CDN を展開する方法。

最適なネットワークを備え、エンタープライズ組織とそのテナントの例を次に示します。

![最適なネットワークを持つテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

この図では、このエンタープライズ組織のテナントには次の機能があります。

- 信頼できる Microsoft 365 トラフィックをローカルのフロント ドアに転送する SDWAN デバイスを使用した各ブランチ オフィスのローカル インターネット アクセス。
- ネットワーク ヘアピンなし。
- Microsoft 365 の信頼されたトラフィックをローカルのフロント ドアに転送する、中央オフィスのセキュリティ およびプロキシ エッジ デバイス。

## <a name="ongoing-maintenance-for-optimal-networking"></a>最適なネットワークのための継続的なメンテナンス

継続的に、次の必要が生じ得る場合があります。

- エンドポイントの変更について、エッジ デバイスと展開された PAC ファイルを更新するか、自動化されたプロセスが正しく動作するか確認します。
- Office 365 CDN でアセットを管理します。
- エンドポイントの変更について、VPN クライアントの分割トンネリング構成を更新します。

## <a name="next-step"></a>次の手順

[![手順 3.ID を同期し、セキュリティで保護されたサインインを適用する](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

ID を [続行して](tenant-management-identity.md) 、オンプレミスのアカウントとグループを同期し、セキュリティで保護されたユーザー サインインを適用します。
