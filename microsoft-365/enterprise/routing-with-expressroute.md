---
title: Office 365 向け ExpressRoute でのルーティング
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: この記事では、Office 365で使用する Azure ExpressRoute のルーティング要件、回線、およびルーティング ドメインについて説明します。
ms.openlocfilehash: c63e3ae14c9b369265622f17c2e542818620aa3e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092913"
---
# <a name="routing-with-expressroute-for-office-365"></a>Office 365 向け ExpressRoute でのルーティング

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Azure ExpressRoute を使用してOffice 365へのルーティング トラフィックを適切に理解するには、[主要な ExpressRoute ルーティング要件](/azure/expressroute/expressroute-routing)と [ExpressRoute 回線とルーティング ドメイン](/azure/expressroute/expressroute-circuit-peerings)をしっかりと把握する必要があります。 これらは、お客様が信頼する ExpressRoute を使用するための基礎Office 365示しています。
  
上記の記事で理解する必要がある重要な項目の一部を次に示します。
  
- ExpressRoute 回線は特定の物理インフラストラクチャにマップされませんが、Microsoft とお客様の代わりにピアリング プロバイダーによって 1 つのピアリング場所で行われる論理接続です。

- ExpressRoute 回線と顧客のキーの間には 1 対 1 のマッピングがあります。

- 各回線では、2 つの独立したピアリング関係 (Azure プライベート ピアリングと Microsoft ピアリング) をサポートできます。Office 365には Microsoft ピアリングが必要です。

- 各回線には、すべてのピアリング関係で共有される固定帯域幅があります。

- ExpressRoute 回線に使用されるすべてのパブリック IPv4 アドレスとパブリック AS 番号は、お客様が所有しているか、アドレス範囲の所有者によって排他的に割り当てられているものとして検証する必要があります。

- 仮想 ExpressRoute 回線はグローバルに冗長であり、標準的な BGP ルーティングプラクティスに従います。 そのため、アクティブ/アクティブ構成でプロバイダーへのエグレスごとに 2 つの物理回線をお勧めします。

サポートされているサービス、コスト、構成の詳細については、 [FAQ ページ](/azure/expressroute/expressroute-faqs) を参照してください。 Microsoft ピアリングのサポートを提供する接続プロバイダーの一覧については、 [ExpressRoute の場所](/azure/expressroute/expressroute-locations) に関する記事を参照してください。 また、10 部構成の [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) シリーズをチャネル 9 に記録し、概念をより詳しく説明しました。
  
## <a name="ensuring-route-symmetry"></a>ルート対称性の確保

Office 365フロントエンド サーバーには、インターネットと ExpressRoute の両方でアクセスできます。 これらのサーバーは、両方が使用可能な場合は、ExpressRoute 回線経由でオンプレミスに戻す方が好まれます。 このため、ネットワークからのトラフィックがインターネット回線経由でルーティングすることを好む場合、ルート非対称の可能性があります。 ステートフル パケット検査を実行するデバイスは、後続の送信パケットとは異なるパスに従うリターン トラフィックをブロックできるため、非対称ルートが問題になります。
  
インターネット経由または ExpressRoute 経由でOffice 365への接続を開始するかどうかにかかわらず、ソースはパブリックにルーティング可能なアドレスである必要があります。 多くのお客様が Microsoft と直接ピアリングしている場合、顧客間で重複が可能なプライベート アドレスを持つことは不可能です。
  
Office 365からオンプレミス ネットワークへの通信が開始されるシナリオを次に示します。 ネットワーク設計を簡略化するために、インターネット パス経由で次のルートをルーティングすることをお勧めします。
  
- Exchange Online テナントからオンプレミス ホストへのメールや、SharePoint Online からオンプレミス ホストに送信されるSharePointオンライン メールなどの SMTP サービス。 SMTP プロトコルは、ExpressRoute 回線で共有されるルート プレフィックスよりも Microsoft のネットワーク内で広く使用され、ExpressRoute 経由でオンプレミスの SMTP サーバーをアドバタイズすると、これらの他のサービスでエラーが発生します。

- サインイン用のパスワード検証中の ADFS。

- [ハイブリッド展開をExchange Serverします](/exchange/exchange-hybrid)。

- [フェデレーション ハイブリッド検索をSharePoint](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)します。

- [ハイブリッド BCS をSharePoint](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)します。

- [ハイブリッド](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)フェデレーションまたは[Skype for BusinessフェデレーションをSkype for Business](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)します。

- [クラウド コネクタSkype for Business](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)。

Microsoft がこれらの双方向トラフィック フローのためにネットワークに戻るには、オンプレミス デバイスへの BGP ルートを Microsoft と共有する必要があります。 ExpressRoute 経由でルート プレフィックスを Microsoft にアドバタイズする場合は、次のベスト プラクティスに従う必要があります。

1) パブリック インターネットと ExpressRoute 経由で、同じパブリック IP アドレス ルート プレフィックスをアドバタイズしないでください。 ExpressRoute 経由で Microsoft に対する IP BGP ルート プレフィックスアドバタイズは、インターネットにまったくアドバタイズされていない範囲から行うことをお勧めします。 使用可能な IP アドレス空間のためにこれを実現できない場合は、ExpressRoute 経由でインターネット回線よりも具体的な範囲をアドバタイズすることが不可欠です。

2) ExpressRoute 回線ごとに個別の NAT IP プールを使用し、インターネット回線の NAT IP プールとは別に使用します。

3) Microsoft にアドバタイズされたルートは、ExpressRoute 経由でネットワークにアドバタイズされるルートだけでなく、Microsoft のネットワーク内の任意のサーバーからネットワーク トラフィックを引き付けます。 ルーティング シナリオが定義され、チームによってよく理解されているサーバーにのみルートをアドバタイズします。 ネットワークから複数の ExpressRoute 回線のそれぞれに個別の IP アドレス ルート プレフィックスをアドバタイズします。
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>ExpressRoute 経由でルーティングするアプリケーションと機能を決定する

Microsoft ピアリング ルーティング ドメインを使用してピアリング関係を構成し、適切なアクセスが承認されると、ExpressRoute で使用可能なすべての PaaS および SaaS サービスを確認できます。 ExpressRoute 用に設計されたOffice 365 サービスは、[BGP コミュニティ](./bgp-communities-in-expressroute.md)または[ルート フィルター](/azure/expressroute/how-to-routefilter-portal)を使用して管理できます。
  
Microsoft ピアリングを使用して使用できる各Office 365機能は、アプリケーションの種類と FQDN 別の[Office 365 エンドポイントに関する記事](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)に記載されています。 テーブルで FQDN を使用する理由は、お客様が PAC ファイルやその他のプロキシ構成を使用してトラフィックを管理できるようにすることです。PAC ファイルなどの[エンドポイントOffice 365管理](./managing-office-365-endpoints.md)するガイドを参照してください。
  
場合によっては、1 つ以上のサブ FQDN が上位レベルのワイルドカード ドメインとは異なる方法でアドバタイズされるワイルドカード ドメインを使用しました。 通常、ワイルドカードが ExpressRoute とインターネットにアドバタイズされるサーバーの長いリストを表し、宛先の小さなサブセットがインターネットにのみアドバタイズされるか、逆の場合に発生します。 違いを理解するには、次の表を参照してください。
  
次の表に、インターネットと Azure ExpressRoute の両方にアドバタイズされるワイルドカード FQDN と、インターネットにのみアドバタイズされるサブ FQDN を表示します。

|**ExpressRoute とインターネット回線にアドバタイズされるワイルドカード ドメイン**|**インターネット回線のみにアドバタイズされたサブ FQDN**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

通常、PAC ファイルは、ExpressRoute によってアドバタイズされたエンドポイントにネットワーク要求を直接回線に送信し、他のすべてのネットワーク要求をプロキシに送信することを目的としています。 このような PAC ファイルを構成する場合は、次の順序で PAC ファイルを作成します。
  
1. 上の表の 2 列目のサブ FQDN を PAC ファイルの上部に含め、トラフィックをプロキシに送信します。 [Office 365エンドポイントの管理](./managing-office-365-endpoints.md)に関する記事で使用するサンプル PAC ファイルを作成しました。

2. 最初のセクションの下の [この記事](./urls-and-ip-address-ranges.md) では、ExpressRoute にアドバタイズされたマークが付いたすべての FQDN を含め、トラフィックを ExpressRoute 回線に直接送信します。

3. これら 2 つのエントリの下に他のネットワーク エンドポイントまたはルールを含め、トラフィックをプロキシに送信します。

次の表に、インターネット回線にアドバタイズされるワイルドカード ドメインを、Azure ExpressRoute およびインターネット回線にアドバタイズするサブ FQDN と共に表示します。 上記の PAC ファイルの場合、次の表の列 2 の FQDN は、参照されているリンクの ExpressRoute にアドバタイズされているものとして一覧表示されます。つまり、これらはファイル内のエントリの 2 番目のグループに含まれることを意味します。

|**インターネット回線のみにアドバタイズされるワイルドカード ドメイン**|**ExpressRoute とインターネット回線にアドバタイズされるサブ FQDN**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> www.office.com  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover-\<tenant\>.outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>インターネットと ExpressRoute 経由でトラフィックOffice 365ルーティングする

選択したOffice 365 アプリケーションにルーティングするには、いくつかの重要な要因を決定する必要があります。
  
1. アプリケーションに必要な帯域幅の量。 既存の使用状況をサンプリングすることは、組織内でこれを決定するための唯一の信頼性の高い方法です。

2. ネットワーク トラフィックからネットワークを離れるエグレスの場所。 これはパフォーマンスに影響するため、Office 365への接続のネットワーク待機時間を最小限に抑える必要があります。 Skype for Businessはリアルタイムの音声とビデオを使用するため、ネットワーク待機時間が短くなる可能性があります。

3. ネットワークの場所のすべてまたはサブセットで ExpressRoute を使用する場合。

4. 選択したネットワーク プロバイダーが ExpressRoute を提供する場所。

これらの質問に対する回答を決定したら、帯域幅と場所のニーズを満たす ExpressRoute 回線をプロビジョニングできます。 ネットワーク計画の詳細については、[Office 365ネットワーク チューニング ガイド](./network-planning-and-performance.md)と[、Microsoft がネットワーク パフォーマンス計画を処理する方法に関するケース スタディを](https://aka.ms/tunemsit)参照してください。
  
### <a name="example-1-single-geographic-location"></a>例 1: 単一の地理的位置
  
この例は、1 つの地理的な場所を持つ Trey Research という架空の会社のシナリオです。
  
Trey Research の従業員は、セキュリティ部門が企業ネットワークと ISP の間にある送信プロキシのペアで明示的に許可しているインターネット上のサービスと Web サイトへの接続のみを許可されます。
  
Trey Research では、Office 365に Azure ExpressRoute を使用する予定であり、コンテンツ配信ネットワーク宛てのトラフィックなどの一部のトラフィックは、Office 365接続のために ExpressRoute 経由でルーティングできないことを認識しています。 すべてのトラフィックは既定でプロキシ デバイスに既にルーティングされているため、これらの要求は引き続き以前と同様に機能します。 Trey Research は、Azure ExpressRoute ルーティング要件を満たすことができると判断した後、回線の作成、ルーティングの構成、新しい ExpressRoute 回線の仮想ネットワークへのリンクに進みます。 基本的な Azure ExpressRoute 構成が整ったら、Trey Research は公開する [#2 PAC ファイル](./managing-office-365-endpoints.md)を使用して、お客様固有のデータを含むトラフィックを直接 ExpressRoute 経由でルーティングし、Office 365接続します。
  
次の図に示すように、Trey Research は、ルーティングと送信プロキシ構成の変更の組み合わせを使用して、インターネット経由でOffice 365トラフィックと ExpressRoute 経由のトラフィックのサブセットをルーティングする要件を満たすことができます。
  
1. [#2 PAC ファイル](./managing-office-365-endpoints.md)を使用して、Azure ExpressRoute for Office 365の別のインターネット エグレス ポイントを介してトラフィックをルーティングするために公開します。

2. クライアントは、Trey Research のプロキシへの既定のルートで構成されます。

この例のシナリオでは、Trey Research は送信プロキシ デバイスを使用しています。 同様に、Office 365用に Azure ExpressRoute を使用していないお客様は、この手法を使用して、既知の大量エンドポイント宛てのトラフィックを検査するコストに基づいてトラフィックをルーティングしたい場合があります。
  
Exchange Online、SharePoint Online、Skype for Business Online の最大ボリューム FQDN は次のとおりです。
  
![ExpressRoute カスタマー エッジ ネットワーク。](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com、outlook.office.com

- \<tenant-name\>.sharepoint.com、 \<tenant-name\>-my.sharepoint.com、 \<tenant-name\>-\<app\>.sharepoint.com

- \*.Lync.com と TCP 以外のトラフィックの IP 範囲

- \*broadcast.officeapps.live.com、\*excel.officeapps.live.com、\*onenote.officeapps.live.com、\*powerpoint.officeapps.live.com、view.officeapps.live.com、\*\*visio.officeapps.live.com、\*word-edit.officeapps.live.com、\*word-view.officeapps.live.com、office.live.com

[Windows 8でのプロキシ設定の展開と管理](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy)について説明し、[プロキシによってOffice 365が調整されないように](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)する方法について説明します。
  
単一の ExpressRoute 回線では、Trey Research の高可用性はありません。 ExpressRoute 接続にサービスを提供している Trey の冗長なエッジ デバイスのペアが失敗した場合、フェールオーバーする余分な ExpressRoute 回線はありません。 これにより、Trey Research はインターネットにフェールオーバーするには手動で再構成する必要があり、場合によっては新しい IP アドレスが必要になるという苦境に置かされます。 Trey が高可用性を追加する場合、最も簡単な解決策は、場所ごとに ExpressRoute 回線を追加し、アクティブ/アクティブな方法で回線を構成することです。
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>複数の場所を持つOffice 365の ExpressRoute をルーティングする

最後のシナリオでは、ExpressRoute 経由でトラフィックOffice 365ルーティングすることが、さらに複雑なルーティング アーキテクチャの基礎となります。 場所の数に関係なく、それらの場所が存在する大陸の数、ExpressRoute 回線の数など、一部のトラフィックをインターネットにルーティングでき、ExpressRoute 経由で一部のトラフィックをルーティングできる必要があります。
  
複数の地域に複数の場所を持つお客様に対して回答する必要がある追加の質問は次のとおりです。
  
1. すべての場所に ExpressRoute 回線が必要ですか? Skype for Business Online を使用している場合、またはSharePoint Online またはExchange Onlineの待機時間の機密性に関心がある場合は、各場所でアクティブ/アクティブな ExpressRoute 回線の冗長ペアをお勧めします。 詳細については、Skype for Business メディアの品質とネットワーク接続に関するガイドを参照してください。

2. ExpressRoute 回線が特定のリージョンで使用できない場合は、宛先トラフィックをどのようにルーティングOffice 365必要がありますか?

3. 小さな場所が多いネットワークの場合、トラフィックを統合するための推奨される方法は何ですか?

これらはそれぞれ、独自のネットワークと Microsoft から利用可能なオプションを評価する必要がある固有の課題です。

|**考慮事項**|**評価するネットワーク コンポーネント**|
|:-----|:-----|
|複数の場所にある回線  <br/> |アクティブ/アクティブな方法で構成された少なくとも 2 つの回線をお勧めします。  <br/> コスト、待機時間、帯域幅のニーズを比較する必要があります。  <br/> BGP ルート コスト、PAC ファイル、NAT を使用して、複数の回線を使用してルーティングを管理します。  <br/> |
|ExpressRoute 回線を使用しない場所からのルーティング  <br/> |Office 365の要求を開始するユーザーに近いエグレスと DNS 解決をお勧めします。  <br/> DNS 転送を使用すると、リモート オフィスで適切なエンドポイントを検出できます。  <br/> リモート オフィスのクライアントには、ExpressRoute 回線へのアクセスを提供するルートが必要です。  <br/> |
|小規模オフィス統合  <br/> |使用可能な帯域幅とデータ使用量は慎重に比較する必要があります。  <br/> |

> [!NOTE]
> 物理的な場所に関係なくルートが利用可能な場合、Microsoft はインターネット経由で ExpressRoute を優先します。
  
これらの各考慮事項は、一意のネットワークごとに考慮する必要があります。 次に例を示します。
  
### <a name="example-2-multi-geographic-locations"></a>例 2: 複数の地理的な場所
  
この例は、複数の地理的な場所を持つ "Humongous Insurance" という架空の会社のシナリオです。
  
Humongous Insurance は、世界中のオフィスと地理的に分散されています。 直接ネットワーク接続でほとんどのOffice 365 トラフィックを維持するために、Office 365用の Azure ExpressRoute を実装したいと考えています。 Humongous Insurance には、さらに 2 つの大陸にオフィスがあります。 ExpressRoute を使用できないリモート オフィスの従業員は、ExpressRoute 接続を使用するために、プライマリ設備の 1 つまたは両方に戻る必要があります。
  
原則は、Office 365宛先トラフィックをできるだけ早く Microsoft データセンターに送信することです。 この例では、Humongous Insurance は、リモート オフィスをインターネット経由でルーティングして、可能な限り迅速に任意の接続経由で Microsoft データセンターにアクセスするか、またはリモート オフィスが内部ネットワーク経由でルーティングして ExpressRoute 接続を介して Microsoft データセンターにできるだけ早くアクセスする必要があるかどうかを決定する必要があります。
  
Microsoft のデータセンター、ネットワーク、およびアプリケーション アーキテクチャは、グローバルに異なる通信を取り、可能な限り最も効率的な方法でサービスを提供するように設計されています。 これは、世界で最大のネットワークの 1 つです。 必要以上に長く顧客ネットワークに残るOffice 365宛ての要求では、このアーキテクチャを利用できません。
  
Humongous Insurance の状況では、ExpressRoute 経由で使用するアプリケーションに応じて処理を進める必要があります。 たとえば、Skype for Business Online のお客様である場合や、外部のSkype for Business Online 会議に接続するときに ExpressRoute 接続を使用する予定がある場合は、Skype for Businessで推奨される設計 オンライン メディアの品質とネットワーク接続ガイドは、3 番目の場所に追加の ExpressRoute 回線をプロビジョニングすることです。 ネットワークの観点から見ると、これはコストが高くなる可能性があります。ただし、Microsoft データセンターに配信する前に、ある大陸から別の大陸に要求をルーティングすると、Skype for Business Online の会議や通信中に不十分または使用できないエクスペリエンスが発生する可能性があります。
  
Humongous Insurance が使用していない場合や、Skype for Business Online を何らかの方法で使用する予定がない場合は、ExpressRoute 接続Office 365宛先ネットワーク トラフィックを大陸にルーティングすることは可能ですが、不要な待機時間や TCP 混雑の原因になる可能性があります。 どちらの場合も、ローカル サイトでインターネット宛てのトラフィックをインターネットにルーティングして、Office 365が依存しているコンテンツ配信ネットワークを利用することをお勧めします。
  
![ExpressRoute の複数地域。](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Humongous Insurance が複数地域戦略を計画している場合、回線のサイズ、回線の数、フェールオーバーなどについて考慮すべき点が多く存在します。
  
複数のリージョンが回線を使用しようとしている単一の場所にある ExpressRoute では、Humongous Insurance は、リモート オフィスからOffice 365への接続が、最寄りのOffice 365 データセンターに送信され、本社の場所から受信されるようにしたいと考えています。 これを行うために、Humongous Insurance は DNS 転送を実装して、本社のインターネットエグレス ポイントに最も近いOffice 365環境との適切な接続を確立するために必要なラウンド トリップと DNS 参照の数を減らします。 これにより、クライアントはローカル フロントエンド サーバーを解決できず、ユーザーが接続するFront-End サーバーが、Humongous Insurance が Microsoft とピアリングしている本社の近くに配置されます。 [また、ドメイン名に条件付きフォワーダーを割り当てること](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))も学習できます。
  
このシナリオでは、リモート オフィスからのトラフィックは、北米のOffice 365フロントエンド インフラストラクチャを解決し、Office 365を使用してOffice 365 アプリケーションのアーキテクチャに従ってバックエンド サーバーに接続します。 たとえば、Exchange Onlineは北米の接続を終了し、それらのフロントエンド サーバーはテナントが存在する場所であればどこでもバックエンド メールボックス サーバーに接続します。 すべてのサービスには、ユニキャストと anycast の宛先で構成される、広く分散されたフロント ドア サービスがあります。
  
複数の大陸に大きなオフィスがある場合は、Skype for Business Online などの機密性の高いアプリケーションの待機時間を短縮するために、リージョンごとに少なくとも 2 つのアクティブ/アクティブ回線が推奨されます。 すべてのオフィスが単一の大陸にある場合、またはリアルタイムコラボレーションを使用していない場合、統合または分散されたエグレス ポイントを持つことは、顧客固有の決定です。 複数の回線を使用できる場合、BGP ルーティングにより、単一の回線が使用できなくなった場合にフェールオーバーが確実に行われます。
  
[サンプル ルーティングの構成](/azure/expressroute/expressroute-config-samples-routing)と[https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat)詳細については、こちらを参照してください。
  
## <a name="selective-routing-with-expressroute"></a>ExpressRoute を使用した選択的ルーティング

ExpressRoute を使用した選択的ルーティングは、テスト、ExpressRoute のユーザーのサブセットへのロールアウトなど、さまざまな理由で必要になる場合があります。 お客様が ExpressRoute 経由でネットワーク トラフィックOffice 365選択的にルーティングするために使用できるさまざまなツールがあります。
  
1. **ルート のフィルター処理/分離** - BGP ルートが ExpressRoute 経由でサブネットまたはルーターのサブセットにOffice 365できるようにします。 これにより、顧客のネットワーク セグメントまたは物理的なオフィスの場所によって選択的にルーティングされます。 これは、Office 365用の ExpressRoute の千鳥的なロールアウトで一般的であり、BGP デバイスで構成されます。

2. **PAC ファイル/URL** - 特定の FQDN の宛先ネットワーク トラフィックOffice 365特定のパスにルーティングするように指示します。 これにより、 [PAC ファイルの展開](./managing-office-365-endpoints.md)によって識別されるクライアント コンピューターによって選択的にルーティングされます。

3. **ルート フィルター** - 処理 [ルート フィルター](/azure/expressroute/how-to-routefilter-portal)は、Microsoft ピアリングを通じてサポートされているサービスのサブセットを使用する方法です。

4. **BGP コミュニティ** - [BGP コミュニティ タグ](./bgp-communities-in-expressroute.md)に基づくフィルター処理を使用すると、お客様は、ExpressRoute を通過するOffice 365アプリケーションとインターネットを通過するアプリケーションを決定できます。

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/erorouting]()
  
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
  
[Office 365シナリオでの ExpressRoute での BGP コミュニティの使用](bgp-communities-in-expressroute.md)
  
[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)
  
[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)
  
[Office 365 の URL および IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 のネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)
