---
title: Office 365 向け ExpressRoute でのルーティング
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: この記事では、Azure ExpressRoute ルーティング要件、回線、およびルーティング ドメインについて説明します。Office 365。
ms.openlocfilehash: e36730f457f17ca6e789bd0ba06998824a6c590a45c53f9050f497c762f5985b
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53904495"
---
# <a name="routing-with-expressroute-for-office-365"></a>Office 365 向け ExpressRoute でのルーティング

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

Azure ExpressRoute を使用して Office 365 へのルーティング トラフィックを適切に理解するには、ExpressRoute ルーティングのコア要件と[ExpressRoute](/azure/expressroute/expressroute-routing)回線とルーティング ドメインをしっかりと把握する[必要があります](/azure/expressroute/expressroute-circuit-peerings)。 これらは、お客様が信頼する ExpressRoute を使用Office 365を示しています。
  
上記の記事で理解する必要がある重要な項目には、次のようなものがあります。
  
- ExpressRoute 回線は特定の物理インフラストラクチャにマップされませんが、Microsoft とピアリング プロバイダーが代わって 1 つのピアリングの場所で行う論理的な接続です。

- ExpressRoute 回線と顧客の s キーの間には 1:1 マッピングがあります。

- 各回線は、2 つの独立したピアリング関係 (Azure Private ピアリングと Microsoft ピアリング) をサポートできます。Office 365 Microsoft ピアリングが必要です。

- 各回線には、すべてのピアリング関係で共有される固定帯域幅があります。

- ExpressRoute 回線に使用されるパブリック IPv4 アドレスとパブリック AS 番号は、自分が所有している、またはアドレス範囲の所有者によって排他的に割り当てられていると検証する必要があります。

- 仮想 ExpressRoute 回線はグローバルに冗長であり、標準的な BGP ルーティングプラクティスに従います。 これが、アクティブ/アクティブ構成でプロバイダーへの出力ごとに 2 つの物理回線を推奨する理由です。

サポートされる [サービス、コスト、](/azure/expressroute/expressroute-faqs) 構成の詳細については、「FAQ」ページを参照してください。 Microsoft ピア [リング サポートを提供](/azure/expressroute/expressroute-locations) する接続プロバイダーの一覧については、ExpressRoute の場所に関する記事を参照してください。 また、10 部構成の Azure [ExpressRoute](https://channel9.msdn.com/series/aer) for Office 365 トレーニング シリーズをチャンネル 9 に記録し、概念の詳細な説明を行いました。
  
## <a name="ensuring-route-symmetry"></a>ルートの対称性の確保

フロントエンド Office 365は、インターネットと ExpressRoute の両方でアクセスできます。 これらのサーバーは、両方が使用可能な場合は、ExpressRoute 回線を使用してオンプレミスに戻す必要があります。 そのため、ネットワークからのトラフィックがインターネット回線を通じてルーティングすることを好む場合、ルート asymmetry が発生する可能性があります。 ステートフル パケット インスペクションを実行するデバイスは、送信パケットが続くパスとは異なるパスに従うリターン トラフィックをブロックする可能性があるため、非対称ルートが問題になります。
  
インターネットまたは ExpressRoute を通Office 365接続を開始するかどうかに関係なく、ソースはパブリックルーティング可能なアドレスである必要があります。 多くのお客様が Microsoft と直接ピアリングを行う場合、顧客間で重複が可能なプライベート アドレスを持つことは不可能です。
  
次に示すのは、Office 365からオンプレミス ネットワークへの通信が開始されるシナリオです。 ネットワーク設計を簡略化するために、これらをインターネット パスを使用してルーティングすることをお勧めします。
  
- smtp サービス (Exchange Online テナントからオンプレミス ホストへのメール、SharePoint Online からオンプレミス ホストに送信される SharePoint Online メールなど)。 SMTP プロトコルは、ExpressRoute 回線上で共有されるルート プレフィックスや、ExpressRoute を使用したオンプレミスの SMTP サーバーの広告よりも、Microsoft のネットワーク内で広く使用され、これらの他のサービスでエラーが発生します。

- サインインのパスワード検証中の ADFS。

- [Exchange Serverハイブリッド展開](/exchange/exchange-hybrid).

- [SharePointハイブリッド検索を実行します](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)。

- [SharePointハイブリッド BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Skype for Businessおよび](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)/またはハイブリッド[フェデレーションSkype for Businessします](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。

- [Skype for Business クラウド コネクタ .](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)

Microsoft がこれらの双方向トラフィック フローのためにネットワークに戻す場合は、オンプレミス デバイスへの BGP ルートを Microsoft と共有する必要があります。 ExpressRoute を使用して Microsoft にルート プレフィックスをアドバタイズする場合は、次のベスト プラクティスに従う必要があります。

1) パブリック インターネットと ExpressRoute を使用して、同じパブリック IP アドレス ルート プレフィックスをアドバタイズしない。 ExpressRoute を超える Microsoft への IP BGP ルート プレフィックス アドバタイズメントは、インターネットにアドバタイズされない範囲から行う必要があります。 使用可能な IP アドレス空間が原因で実現できない場合は、インターネット回線よりも ExpressRoute で特定の範囲をアドバタイズする必要があります。

2) ExpressRoute 回線ごとに個別の NAT IP プールを使用し、インターネット回線とは別に使用します。

3) Microsoft にアドバタイズされたルートは、ExpressRoute を使用してネットワークにアドバタイズされるルートだけでなく、Microsoft のネットワーク内の任意のサーバーからのネットワーク トラフィックを引き付ける点に注意してください。 ルーティング シナリオが定義され、チームによって十分に理解されているサーバーへのルートのみをアドバタイズします。 ネットワークから複数の ExpressRoute 回線ごとに個別の IP アドレス ルート プレフィックスをアドバタイズします。
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>ExpressRoute を使用してルーティングするアプリケーションと機能を決定する

Microsoft ピアリング ルーティング ドメインを使用してピアリング関係を構成し、適切なアクセスが承認されると、ExpressRoute で利用可能なすべての PaaS および SaaS サービスを確認できます。 ExpressRoute Office 365サービスは[、BGP](./bgp-communities-in-expressroute.md)コミュニティまたはルート フィルターを使用して[管理できます](/azure/expressroute/how-to-routefilter-portal)。
  
Microsoft ピアリングOffice 365使用できる各機能は、アプリケーションの種類と FQDN Office 365[](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)エンドポイントの記事に記載されています。 表で FQDN を使用する理由は、顧客が PAC ファイルまたは他のプロキシ構成を使用してトラフィックを管理できる理由です。PAC ファイルなどの[Office 365](./managing-office-365-endpoints.md)エンドポイントの管理に関するガイドを参照してください。
  
一部の状況では、1 つ以上のサブ FQDN が上位レベルのワイルドカード ドメインとは異なる方法でアドバタイズされるワイルドカード ドメインを使用しました。 これは通常、ワイルドカードが ExpressRoute とインターネットにアドバタイズされるサーバーの長い一覧を表し、宛先の小さなサブセットがインターネットにのみアドバタイズされる場合、または逆の場合に発生します。 相違点を理解するには、以下の表を参照してください。
  
次の表は、インターネットにのみアドバタイズされるサブ FQDN と共に、インターネットと Azure ExpressRoute の両方にアドバタイズされるワイルドカード FQDN を表示します。

|**ExpressRoute およびインターネット回線にアドバタイズされるワイルドカード ドメイン**|**インターネット回線にのみアドバタイズされるサブ FQDN**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

通常、PAC ファイルは、ExpressRoute アドバタイズされたエンドポイントにネットワーク要求を回線に直接送信し、他のすべてのネットワーク要求をプロキシに送信することを目的とします。 このような PAC ファイルを構成する場合は、次の順序で PAC ファイルを作成します。
  
1. 上記の表の列 2 のサブ FQDN を PAC ファイルの上部に含め、プロキシにトラフィックを送信します。 エンドポイントの管理に関する記事で使用するサンプル PAC[ファイルをOffice 365しました](./managing-office-365-endpoints.md)。

2. ExpressRoute 回線にトラフィックを直接送信する最初[](./urls-and-ip-address-ranges.md)のセクションの下のこの記事に、ExpressRoute にアドバタイズされたマークが付いているすべての FQDN を含めます。

3. これら 2 つのエントリの下に他のネットワーク エンドポイントまたはルールを含め、トラフィックをプロキシに送信します。

次の表は、Azure ExpressRoute およびインターネット回線にアドバタイズされるサブ FQDN と共にのみ、インターネット回線にアドバタイズされるワイルドカード ドメインを表示します。 上記の PAC ファイルの場合、下の表の 2 列目の FQDN は、参照されるリンクの ExpressRoute にアドバタイズされているとして一覧表示されます。つまり、ファイル内のエントリの 2 番目のグループに含まれます。

|**インターネット回線にのみアドバタイズされるワイルドカード ドメイン**|**ExpressRoute およびインターネット回線にアドバタイズされるサブ FQDN**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>インターネットOffice 365 ExpressRoute を使用したトラフィックのルーティング

選択したアプリケーションOffice 365にルーティングするには、多くの重要な要素を決定する必要があります。
  
1. アプリケーションに必要な帯域幅。 既存の使用状況のサンプリングは、組織内でこれを決定するための唯一の信頼できる方法です。

2. ネットワーク トラフィックがネットワークから離れる出力場所。 パフォーマンスに影響を及ぼすので、ネットワーク接続のネットワーク待機時間を最小限にOffice 365する必要があります。 ユーザーはSkype for Business音声とビデオを使用しますので、特にネットワーク遅延の影響を受けやすいです。

3. ネットワークの場所のすべてまたはサブセットに ExpressRoute を使用する場合。

4. 選択したネットワーク プロバイダーが ExpressRoute を提供する場所。

これらの質問に対する回答を確認したら、帯域幅と場所のニーズを満たす ExpressRoute 回線をプロビジョニングできます。 ネットワーク計画の詳細については、「ネットワーク チューニング[](./network-planning-and-performance.md)ガイドOffice 365 Microsoft がネットワーク パフォーマンス計画を処理する方法に関するケース スタディ[」を参照してください](https://aka.ms/tunemsit)。
  
### <a name="example-1-single-geographic-location"></a>例 1: 単一の地理的位置
  
この例は、地理的な場所が 1 つの Trey Research という架空の会社のシナリオです。
  
Trey Research の従業員は、企業ネットワークと ISP の間に存在する 2 つの送信プロキシでセキュリティ部門が明示的に許可するインターネット上のサービスと Web サイトにのみ接続できます。
  
Trey Research は、Office 365 用に Azure ExpressRoute を使用することを計画し、コンテンツ配信ネットワーク宛てのトラフィックなどの一部のトラフィックが Office 365 接続用の ExpressRoute をルーティングできないと認識しています。 既定では、すべてのトラフィックが既にプロキシ デバイスにルーティングされています。 Trey Research が Azure ExpressRoute ルーティング要件を満たできると判断した後、回線の作成、ルーティングの構成、および新しい ExpressRoute 回線の仮想ネットワークへのリンクに進みます。 基本的な Azure ExpressRoute 構成が行われ次第[、Trey](./managing-office-365-endpoints.md) Research は発行する #2 PAC ファイルを使用して、Office 365 接続用の直接 ExpressRoute を通して顧客固有のデータを使用してトラフィックをルーティングします。
  
次の図に示すように、Trey Research は、ルーティングと送信プロキシ構成の変更を組み合わせて使用して、Office 365 トラフィックをインターネット上にルーティングし、ExpressRoute を通じてトラフィックのサブセットをルーティングする要件を満たします。
  
1. この PAC[ファイル#2使用して](./managing-office-365-endpoints.md)、Azure ExpressRoute 用の別のインターネット出力ポイントを経由してトラフィックをルーティングOffice 365。

2. クライアントは、Trey Research のプロキシに対する既定のルートで構成されます。

この例のシナリオでは、Trey Research は送信プロキシ デバイスを使用しています。 同様に、Office 365 に Azure ExpressRoute を使用していないお客様は、この手法を使用して、既知の高ボリューム エンドポイント宛てのトラフィックを検査するコストに基づいてトラフィックをルーティングできます。
  
オンライン、オンライン、Exchange Online、SharePointの最もSkype for Businessの FQDN は次のとおりです。
  
![ExpressRoute カスタマー エッジ ネットワーク](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com,outlook.office.com

- \<tenant-name\>\<tenant-name\>.sharepoint.com、-my.sharepoint.com、.sharepoint.com \<tenant-name\> - \<app\>

- \*.Lync.com TCP 以外のトラフィックの IP 範囲と共に設定する

- \*\*broadcast.officeapps.live.com、excel.officeapps.live.com、onenote.officeapps.live.com、powerpoint.officeapps.live.com、view.officeapps.live.com、visio.officeapps.live.com、word-edit.officeapps.live.com、word-view.officeapps.live.com、office.live.com \* \* \* \* \* \*

プロキシ設定の[展開](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy)と管理について、Windows 8プロキシOffice 365調整されていないことを[確認する方法について説明します](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)。
  
単一の ExpressRoute 回線では、Trey Research の高可用性はありません。 ExpressRoute 接続にサービスを提供している Trey の冗長なエッジ デバイスのペアが失敗した場合、フェールオーバー先の ExpressRoute 回線は追加されません。 これにより、Trey Research は、インターネットへのフェールオーバーが手動で再構成され、場合によっては新しい IP アドレスが必要になります。 Trey が高可用性を追加する場合、最も簡単な解決策は、場所ごとに ExpressRoute 回線を追加し、アクティブ/アクティブな方法で回線を構成します。
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>複数の場所を持つOffice 365 ExpressRoute のルーティング

最後のシナリオでは、ExpressRoute Office 365トラフィックをルーティングする方法が、さらに複雑なルーティング アーキテクチャの基盤です。 場所の数に関係なく、それらの場所が存在する大陸の数、ExpressRoute 回線の数など、一部のトラフィックをインターネットにルーティングし、一部のトラフィックを ExpressRoute 上にルーティングできる必要があります。
  
複数の地域に複数の場所を持つ顧客に対して回答する必要があるその他の質問には、次のようなものがあります。
  
1. すべての場所で ExpressRoute 回線が必要ですか? Skype for Business Online を使用している場合、または SharePoint Online または Exchange Online の待機時間の感度が懸念される場合は、各場所でアクティブ/アクティブ ExpressRoute 回線の冗長ペアをお勧めします。 詳細についてはSkype for Businessメディア品質とネットワーク接続ガイドを参照してください。

2. ExpressRoute 回線が特定の地域で使用できない場合は、Office 365をルーティングする必要がありますか?

3. 小さな場所が多いネットワークの場合、トラフィックを統合する場合に推奨される方法は何ですか?

これらのそれぞれは、独自のネットワークと Microsoft から利用可能なオプションを評価する必要がある独自の課題を提示します。

|**考慮事項**|**評価するネットワーク コンポーネント**|
|:-----|:-----|
|複数の場所の回線  <br/> |アクティブ/アクティブな方法で構成される回線は、少なくとも 2 つお勧めします。  <br/> コスト、待機時間、帯域幅のニーズを比較する必要があります。  <br/> 複数の回線でルーティングを管理するには、BGP ルート コスト、PAC ファイル、NAT を使用します。  <br/> |
|ExpressRoute 回線のない場所からのルーティング  <br/> |送信および DNS 解決は、要求を開始するユーザーに近いOffice 365。  <br/> DNS 転送を使用すると、リモート オフィスが適切なエンドポイントを検出できます。  <br/> リモート オフィスのクライアントには、ExpressRoute 回線にアクセスできるルートが必要です。  <br/> |
|小規模なオフィス統合  <br/> |使用可能な帯域幅とデータ使用量を慎重に比較する必要があります。  <br/> |

> [!NOTE]
> 物理的な場所に関係なくルートが利用可能な場合、Microsoft はインターネットよりも ExpressRoute を優先します。
  
これらの各考慮事項は、一意のネットワークごとに考慮する必要があります。 以下に例を示します。
  
### <a name="example-2-multi-geographic-locations"></a>例 2: 複数地域の場所
  
この例は、複数の地理的な場所を持つ架空の企業である Humongous Insurance のシナリオです。
  
Humongous Insuranceは地理的に世界中のオフィスに分散しています。 直接ネットワーク接続上のトラフィックのOffice 365を維持Office 365 Azure ExpressRoute を実装する必要があります。 Humongous Insurance には、2 つの追加の大陸にオフィスがあります。 ExpressRoute が実現不可能なリモート オフィスの従業員は、ExpressRoute 接続を使用するためにプライマリ施設の一方または両方に戻す必要があります。
  
基本的な原則は、Office 365な限り迅速に Microsoft データセンターへのトラフィックを取得することです。 この例では、Humongous Insurance は、リモート オフィスが可能な限り迅速に接続を通して Microsoft データセンターに接続するためにインターネットを通してルーティングする必要がある場合、またはリモート オフィスが ExpressRoute 接続を使用して Microsoft データセンターに可能な限り迅速にアクセスするために内部ネットワークを通してルーティングする必要がある場合に決定する必要があります。
  
Microsoft のデータセンター、ネットワーク、およびアプリケーション アーキテクチャは、可能な限り最も効率的な方法で、グローバルに分散した通信を行い、サービスを提供するように設計されています。 これは、世界最大のネットワークの 1 つです。 顧客ネットワークにOffice 365に必要以上に長く残るユーザー宛ての要求は、このアーキテクチャを利用できないでしょう。
  
Humongous Insurance の状況では、ExpressRoute で使用するアプリケーションに応じて処理を進める必要があります。 たとえば、Skype for Business Online のお客様である場合や、外部の Skype for Business Online 会議に接続するときに ExpressRoute 接続を使用する予定の場合、Skype for Business Online メディア品質とネットワーク接続ガイドで推奨される設計は、3 番目の場所に ExpressRoute 回線を追加で準備する方法です。 これは、ネットワークの観点から見るとコストが高い場合があります。ただし、Microsoft データセンターに配信する前に、1 つの大陸から別の大陸に要求をルーティングすると、オンラインの会議や通信中に、Skype for Businessエクスペリエンスが低下する可能性があります。
  
Humongous Insurance を使用しない場合や、Skype for Business Online を使用する予定がない場合は、Office 365 宛てのネットワーク トラフィックを ExpressRoute 接続で大陸にルーティングし戻す可能性があります。しかし、不必要な遅延や TCP 輻輳を引き起こす可能性があります。 どちらの場合も、インターネット宛てのトラフィックをローカル サイトでインターネットにルーティングして、ユーザーが依存するコンテンツ配信ネットワークOffice 365勧めします。
  
![ExpressRoute の複数地域](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Humongous Insurance が複数地域戦略を計画している場合、回線のサイズ、回線数、フェールオーバーなどについて考慮すべき点が多数存在します。
  
複数の地域が回線を使用しようとする単一の場所に ExpressRoute を使用する場合、Humongous Insurance は、リモート オフィスからの Office 365 への接続が Office 365 データセンターの最寄りの本社に送信され、本社の場所によって受信されるのを確認します。 これを行うには、Humongous Insurance は DNS フォワーディングを実装して、本社のインターネット出力ポイントに最も近い Office 365 環境との適切な接続を確立するために必要なラウンド トリップと DNS 参照の数を減らします。 これにより、クライアントはローカルのフロントエンド サーバーを解決し、ユーザーが接続する Front-End サーバーが、Humongous Insurance が Microsoft とピアリングしている本社の近くに置かされます。 また、「ドメイン名に条件付 [き転送者を割り当てる」も学習できます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))。
  
このシナリオでは、リモート オフィスからのトラフィックは、北米の Office 365 フロントエンド インフラストラクチャを解決し、Office 365 を使用して Office 365 アプリケーションのアーキテクチャに従ってバックエンド サーバーに接続します。 たとえば、Exchange Onlineは北米で接続を終了し、これらのフロントエンド サーバーはテナントが存在するバックエンド メールボックス サーバーに接続します。 すべてのサービスには、ユニキャストと anycast の宛先で構成される、広く分散されたフロント ドア サービスがあります。
  
Humongous に複数の大陸に主要なオフィスがある場合は、Skype for Business Online などの機密性の高いアプリケーションの待機時間を短縮するために、地域ごとに少なくとも 2 つのアクティブ/アクティブ回線をお勧めします。 すべてのオフィスが単一の大陸にある場合、またはリアルタイムのコラボレーションを使用していない場合は、統合または分散された出力ポイントを持つことは、お客様固有の決定です。 複数の回線を使用できる場合、BGP ルーティングによって、単一の回線が使用できなくなった場合にフェールオーバーが保証されます。
  
ルーティング構成のサンプル [とについて詳しくは、以下をご](/azure/expressroute/expressroute-config-samples-routing) 覧ください [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat) 。
  
## <a name="selective-routing-with-expressroute"></a>ExpressRoute による選択的ルーティング

ExpressRoute を使用した選択的ルーティングは、テスト、ユーザーのサブセットへの ExpressRoute の展開など、さまざまな理由で必要になる場合があります。 お客様が ExpressRoute を使用してネットワーク トラフィックを選択的にルーティングOffice 365さまざまなツールがあります。
  
1. **ルーティング フィルタリング/分離**- BGP ルートが ExpressRoute をOffice 365サブネットまたはルーターのサブセットにルーティングすることを許可します。 これは、お客様のネットワーク セグメントまたは物理的なオフィスの場所によって選択的にルーティングされます。 これは、お使いの BGP デバイスで構成されている、Office 365 ExpressRoute の驚異的なロールアウトに共通です。

2. **PAC ファイル/URL** - 特定Office 365パスでルーティングする特定の FQDN のネットワーク トラフィックを送信します。 これは、PAC ファイルの展開によって識別されるクライアント コンピューターによって選択的 [にルーティングされます](./managing-office-365-endpoints.md)。

3. **ルート フィルター**  - [ルート フィルターは](/azure/expressroute/how-to-routefilter-portal)、Microsoft ピアリングを通じてサポートされているサービスのサブセットを使用する方法です。

4. **BGP コミュニティ**- [BGP](./bgp-communities-in-expressroute.md)コミュニティ タグに基づくフィルター処理を使用すると、お客様は、ExpressRoute をOffice 365するアプリケーションと、インターネットを通過するアプリケーションを特定できます。

ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/erorouting]()
  
## <a name="related-topics"></a>関連項目

[Office 365 ネットワーク接続の評価](assessing-network-connectivity.md)
  
[Office 365 向け Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 向け ExpressRoute の管理](managing-expressroute-for-connectivity.md)
  
[Office 365 向け ExpressRoute でのネットワーク計画](network-planning-with-expressroute.md)
  
[Office 365 向け ExpressRoute の実装](implementing-expressroute.md)
  
[Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Skype for Business Online 向けのネットワークの最適化](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[Skype for Business Online での ExpressRoute および QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute を使用したコール フロー](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[ExpressRoute での BGP コミュニティの使用によるOffice 365シナリオ](bgp-communities-in-expressroute.md)
  
[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)
  
[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)
  
[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 のネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)
