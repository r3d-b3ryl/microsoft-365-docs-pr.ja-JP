---
title: 手順 2.  エンタープライズ テナントのMicrosoft 365に最適なネットワーク
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントへのネットワーク アクセスを最適化します。
ms.openlocfilehash: 2ee0f5cd784112909cbba465b94031ac2429963f
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524227"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>手順 2。 エンタープライズ テナントのMicrosoft 365に最適なネットワーク

企業向けのMicrosoft 365には、TeamsやExchange Online、Microsoft Intuneなどのクラウド生産性アプリと、Microsoft Azureの多くの ID およびセキュリティ サービスが含まれます。 これらのクラウドベースのサービスはすべて、オンプレミス ネットワークまたはインターネット上の任意の場所にあるクライアント デバイスからの接続のセキュリティ、パフォーマンス、信頼性に依存します。 

テナントのネットワーク アクセスを最適化するには、次の手順を実行する必要があります。

- オンプレミス ユーザーと Microsoft Global Network に最も近い場所との間のパスを最適化します。
- リモート アクセス VPN ソリューションを使用しているリモート ユーザーに対して、Microsoft Global Network へのアクセスを最適化します。
- ネットワーク インサイトを使用して、オフィスの場所のネットワーク境界を設計します。
- Office 365 CDNを使用して、SharePoint サイトでホストされている特定の資産へのアクセスを最適化します。
- エンドポイントの一覧を使用して信頼されたトラフィックMicrosoft 365処理をバイパスするようにプロキシ およびネットワーク エッジ デバイスを構成し、変更が加えられるとリストの更新を自動化します。

## <a name="enterprise-on-premises-workers"></a>オンプレミスのワーカーをEnterpriseする

エンタープライズ ネットワークの場合は、クライアントと最も近いMicrosoft 365 エンドポイント間で最もパフォーマンスの高いネットワーク アクセスを有効にすることで、エンド ユーザー エクスペリエンスを最適化する必要があります。 エンド ユーザー エクスペリエンスの品質は、ユーザーが使用しているアプリケーションのパフォーマンスと応答性に直接関係します。 たとえば、Microsoft Teamsは低待機時間に依存しているため、ユーザーの電話、会議、共有画面のコラボレーションは問題なく行われます。

ネットワーク設計の主な目標は、クライアント デバイスから Microsoft のパブリック ネットワーク バックボーンである Microsoft Global Network へのラウンドトリップ時間 (RTT) を短縮し、待機時間が短く、高可用性クラウド アプリケーションのエントリ ポイント (フロントドアと呼ばれる) が世界中に広がることで、待機時間を最小限に抑える必要があります。

従来のエンタープライズ ネットワークの例を次に示します。

![インターネットに一元的にアクセスできる従来のエンタープライズ ネットワーク。](../media/tenant-management-overview/tenant-management-networking-traditional.png)

この図では、ブランチ オフィスは、ワイド エリア ネットワーク (WAN) デバイスと WAN バックボーンを介して中央オフィスに接続します。 インターネット アクセスは、中央オフィスとインターネット サービス プロバイダー (ISP) のネットワーク エッジにあるセキュリティまたはプロキシ デバイスを介して行われます。 インターネット上では、Microsoft Global Network には、世界中のリージョンに一連のフロント ドアがあります。 組織は、トラフィックの追加のパケット処理とセキュリティのために中間の場所を使用することもできます。 組織のMicrosoft 365テナントは、Microsoft Global Network 内にあります。

Microsoft 365 クラウド サービスのこの構成に関する問題は次のとおりです。

- ブランチ オフィスのユーザーの場合、トラフィックはローカル以外のフロント ドアに送信され、待機時間が長くなります。
- トラフィックを中間の場所に送信すると、信頼されたトラフィックに対して重複するパケット処理を実行するネットワーク ヘアピンが作成され、待機時間が長くなります。
- ネットワーク エッジ デバイスは、信頼されたトラフィックに対して不要で重複するパケット処理を実行し、待機時間を長くします。

ネットワーク パフォーマンスMicrosoft 365最適化することは複雑である必要はありません。 いくつかの重要な原則に従って、可能な限り最高のパフォーマンスを得ることができます。

- ネットワーク トラフィックMicrosoft 365識別します。これは、Microsoft クラウド サービス宛ての信頼されたトラフィックです。
- ユーザーがMicrosoft 365に接続する各場所からインターネットへのMicrosoft 365ネットワーク トラフィックのローカル ブランチエグレスを許可します。
- ネットワーク ヘアピンは使用しないでください。
- Microsoft 365 トラフィックがプロキシとパケット検査デバイスをバイパスできるようにします。

これらの原則を実装すると、Microsoft 365用に最適化されたエンタープライズ ネットワークが得られます。

![Microsoft 365用に最適化されたエンタープライズ ネットワーク。](../media/tenant-management-overview/tenant-management-networking-optimized.png)

この図では、ブランチ オフィスは、ソフトウェア定義の WAN デバイス (SDWAN) デバイスを介して独自のインターネット接続を持ち、信頼されたMicrosoft 365トラフィックをリージョン内で最も近いフロント ドアに送信します。 中央オフィスでは、信頼されたMicrosoft 365トラフィックがセキュリティまたはプロキシ デバイスをバイパスし、中間デバイスは使用されなくなりました。

最適化された構成が従来のエンタープライズ ネットワークの待機時間の問題を解決する方法を次に示します。

- 信頼されたMicrosoft 365トラフィックは WAN バックボーンをスキップし、すべてのオフィスのローカル フロント ドアに送信され、待機時間が短縮されます。
- 重複するパケット処理を実行するネットワーク ヘアピンは、信頼されたトラフィックMicrosoft 365スキップされ、待機時間が短縮されます。
- 不要なパケット処理と重複するパケット処理を実行するネットワーク エッジ デバイスは、信頼されたトラフィックMicrosoft 365スキップされ、待機時間が短縮されます。

詳細については、「[Microsoft 365ネットワーク接続の概要](../enterprise/microsoft-365-networking-overview.md)」を参照してください。

## <a name="remote-workers"></a>リモート ワーカー

リモート ワーカーが従来の VPN クライアントを使用して組織ネットワークへのリモート アクセスを取得している場合は、VPN クライアントがスプリット トンネリング サポートを備えていることを確認してください。 スプリット トンネリングを使用しない場合、すべてのリモート作業トラフィックは VPN 接続を介して送信され、そこで組織のエッジ デバイスに転送されて処理され、インターネット上で送信される必要があります。 次に例を示します。

![トンネリングのない VPN クライアントからのネットワーク トラフィック。](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

この図では、Microsoft 365 トラフィックは組織を経由する間接ルートを取る必要があります。これは、VPN クライアントの物理的な場所から遠く離れた Microsoft Global Network のフロント ドアに転送される可能性があります。 この間接パスにより、ネットワーク トラフィックが遅延し、全体的なパフォーマンスを低下させます。 

スプリッ トトンネリングを使用すると、VPN クライアントを構成して、特定の種類のトラフィックが VPN 接続を介して、組織ネットワークに送信されることを除外できます。

Microsoft 365 クラウドリソースへのアクセスを最適化するには、VPN 接続を介して、**最適化** カテゴリの Microsoft 365 エンドポイントへのトラフィックを除外するようにスプリット トンネリング VPN クライアントを構成します。 詳細については、「[Office 365 エンドポイント カテゴリ](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)と、分割トンネリング用の最適化カテゴリ エンドポイントの[一覧](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)」を参照してください。

分割トンネリングの結果として得られるトラフィック フローを次に示します。このフローでは、クラウド アプリへのトラフィックの大部分Microsoft 365 VPN 接続がバイパスされます。

![トンネリングのある VPN クライアントからのネットワーク トラフィック。](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

この図では、VPN クライアントは、重要なMicrosoft 365クラウド サービス トラフィックをインターネット経由で直接受信し、Microsoft Global Network に最も近いフロント ドアに送受信します。

詳細とガイダンスについては、「[VPN スプリット トンネリングを使用してリモート ユーザーの Office 365 の接続を最適化する](../enterprise/microsoft-365-vpn-split-tunnel.md)」をご覧ください。

## <a name="using-network-insights-preview"></a>ネットワーク インサイトの使用 (プレビュー)

ネットワーク分析情報は、オフィスの場所のネットワーク境界を設計するのに役立つ、Microsoft 365 テナントから収集されたパフォーマンス メトリックです。 各分析情報は、オンプレミス ユーザーがテナントにアクセスしている地理的な場所ごとに、指定された問題のパフォーマンス特性に関するライブの詳細を提供します。

テナントには、次の 2 つのテナント レベルのネットワーク分析情報が表示されます。

- [接続の問題の影響を受けたサンプリングされた接続のExchange](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-affected-by-connectivity-issues)
- [接続の問題の影響を受けたサンプリングされた接続のSharePoint](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-affected-by-connectivity-issues)

オフィスの場所ごとに特定のネットワーク 分析情報を次に示します。

- [バックホールされたネットワークエグレス](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [近くの顧客に対して検出されるパフォーマンスの向上](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [最適でないExchange Onlineサービス フロント ドアの使用](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [最適でないSharePointオンライン サービス フロント ドアの使用](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [SharePointフロント ドアからのダウンロード速度が低い](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [中国ユーザーの最適なネットワークエグレス](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

> [!IMPORTANT]
> Microsoft 365 管理 センターのネットワーク分析情報、パフォーマンスに関する推奨事項、および評価は、現在プレビューの状態です。 機能プレビュー プログラムに登録されているMicrosoft 365 テナントでのみ使用できます。

詳細については、「[Microsoft 365 ネットワーク インサイト](../enterprise/office-365-network-mac-perf-insights.md)」を参照してください。

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>Office 365 CDNでパフォーマンスをSharePointする

クラウドベースのContent Delivery Network (CDN) を使用すると、読み込み時間を短縮し、帯域幅を節約し、応答性を向上させることができます。 CDNは、グラフィック ファイルやビデオ ファイルなどの静的アセットを要求するブラウザーに近い場所にキャッシュすることでパフォーマンスを向上させ、ダウンロードの高速化と待機時間の短縮に役立ちます。 Microsoft 365 E3と E5 のSharePointに付属する組み込みのOffice 365 Content Delivery Network (CDN) を使用して、静的アセットをホストして、SharePoint ページのパフォーマンスを向上させることができます。

Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。 Office 365 CDNでホストするコンテンツの種類に応じて、**パブリック** 配信元、**プライベート** 配信元、またはその両方を追加できます。

デプロイおよび構成すると、Office 365 CDNはパブリックおよびプライベートの配信元から資産をアップロードし、インターネット経由のユーザーにすばやくアクセスできるようにします。

![Office 365 CDNユーザー向けにデプロイされます。](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDNユーザー向けにデプロイ済み")

詳細については、「[SharePoint Online でOffice 365 CDNを使用する](../enterprise/use-microsoft-365-cdn-with-spo.md)」を参照してください。

## <a name="automated-endpoint-listing"></a>自動化されたエンドポイントの一覧

オンプレミスのクライアント、エッジ デバイス、クラウドベースのパケット分析サービスで信頼されたMicrosoft 365 トラフィックの処理をスキップするには、Microsoft 365 サービスに対応する一連のエンドポイント (IP アドレス範囲と DNS 名) を使用して構成する必要があります。 これらのエンドポイントは、ファイアウォールやその他のエッジ セキュリティ デバイス、プロキシをバイパスするクライアント コンピューター用の PAC ファイル、ブランチ オフィスの SD-WAN デバイスで手動で構成できます。 ただし、エンドポイントは時間の経過と共に変化するため、これらの場所のエンドポイント リストの継続的な手動メンテナンスが必要になります。

クライアント PAC ファイルとネットワーク デバイス内のMicrosoft 365 エンドポイントの一覧と変更管理を自動化するには、[Office 365 IP アドレスと URL REST ベースの Web サービスを](../enterprise/microsoft-365-ip-web-service.md)使用します。 このサービスを使用すると、ネットワーク トラフィックMicrosoft 365識別し、区別を深め、最新の変更を評価、構成、最新の状態に保つのが容易になります。

PowerShell、Python、またはその他の言語を使用して、時間の経過と共にエンドポイントに対する変更を決定し、PAC ファイルとエッジ ネットワーク デバイスを構成できます。

基本的なプロセスは次のとおりです。

1. Office 365 IP アドレスと URL Web サービス、および選択した構成メカニズムを使用して、現在の一連のMicrosoft 365 エンドポイントを使用して PAC ファイルとネットワーク デバイスを構成します。
2. 毎日定期的に実行して、エンドポイントの変更を確認するか、通知メソッドを使用します。
3. 変更が検出されたら、クライアント コンピューターの PAC ファイルを再生成して再配布し、ネットワーク デバイスに変更を加えます。

詳細については、「[Office 365 IP アドレスと URL Web サービス」を](../enterprise/microsoft-365-ip-web-service.md)参照してください。

## <a name="results-of-step-2"></a>手順 2 の結果

最適なネットワークを持つMicrosoft 365テナントについては、次のことを決定しました。

- すべてのブランチ オフィスにインターネット接続を追加し、ネットワーク ヘアピンを排除することで、オンプレミス ユーザーのネットワーク パフォーマンスを最適化する方法。
- 継続的な更新 (エンタープライズ ネットワークに最適) を含め、クライアント ベースの PAC ファイルとネットワーク デバイスとサービスに対して、自動化された信頼されたエンドポイントの一覧を実装する方法。
- オンプレミス リソースへのリモート ワーカーのアクセスをサポートする方法。
- ネットワーク インサイトを使用する方法
- Office 365 CDNをデプロイする方法。

最適なネットワークを備えたエンタープライズ組織とそのテナントの例を次に示します。

![最適なネットワークを持つテナントの例。](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

この図では、このエンタープライズ組織のテナントには次のものがあります。

- 信頼されたMicrosoft 365トラフィックをローカル のフロント ドアに転送する SDWAN デバイスを使用した各ブランチ オフィスのローカル インターネット アクセス。
- ネットワーク ヘアピンはありません。
- 信頼されたトラフィックをローカル のフロント ドアに転送Microsoft 365中央の Office セキュリティおよびプロキシ エッジ デバイス。

## <a name="ongoing-maintenance-for-optimal-networking"></a>最適なネットワークのための継続的なメンテナンス

継続的に、次の操作が必要になる場合があります。

- エンドポイントの変更のためにエッジ デバイスと展開された PAC ファイルを更新するか、自動化されたプロセスが正しく動作することを確認します。
- Office 365 CDNでアセットを管理します。
- エンドポイントの変更のために、VPN クライアントの分割トンネリング構成を更新します。

## <a name="next-step"></a>次の手順

[![手順 3.ID を同期し、セキュリティで保護されたサインインを適用します。](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

[ID](tenant-management-identity.md) を続行して、オンプレミスのアカウントとグループを同期し、セキュリティで保護されたユーザー サインインを適用します。
