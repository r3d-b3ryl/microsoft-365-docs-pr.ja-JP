---
title: VPN スプリット トンネリングを実装するMicrosoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 1/28/2022
audience: Admin
ms.article: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: VPN スプリット トンネリングを実装するMicrosoft 365
ms.openlocfilehash: 59414e32f187dc4e8354dc0c20228a4222fa2754
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281184"
---
# <a name="implementing-vpn-split-tunneling-for-microsoft-365"></a>VPN スプリット トンネリングを実装するMicrosoft 365

>[!NOTE]
>この記事は、リモート ユーザーの最適化に関するMicrosoft 365の一部です。

>- VPN スプリット トンネリングを使用してリモート ユーザー Microsoft 365接続を最適化する方法の概要については、「[Overview: VPN split tunneling for remoteing for remote」を参照](microsoft-365-vpn-split-tunnel.md)Microsoft 365。
>- 中国のユーザーに対するMicrosoft 365のパフォーマンスの最適化の詳細については、「中国のユーザー Microsoft 365[パフォーマンスの最適化」を参照してください](microsoft-365-networking-china.md)。

企業は何年もの間、VPN を使用してユーザーのリモート エクスペリエンスをサポートしてきました。 コア ワークロードはオンプレミスのままですが、リモート クライアントからの VPN は企業ネットワーク上のデータセンターを経由してルーティングされ、リモート ユーザーが企業リソースにアクセスする主な方法でした。 接続を保護するため、企業は VPN パスに沿ってネットワーク セキュリティ ソリューションのレイヤを構築します。 このセキュリティは、内部インフラストラクチャを保護し、VPN にトラフィックをルーティングし、オンプレミスのインターネット境界を経由して外部 Web サイトのモバイル ブラウズを保護するために構築されました。 VPN、ネットワーク境界、および関連するセキュリティ インフラストラクチャは、通常、企業ネットワーク内から開始されるほとんどの接続で、そのほとんどが内部ネットワーク境界内にとどまる、定義されたトラフィック量に対して専用に構築され、スケーリングされました。

長い間、リモート ユーザー デバイスからのすべての接続がオンプレミス ネットワークにルーティングされる VPN モデル (いわゆる _強制トンネリング_) は、リモート ユーザーの同時接続規模を控えめにし、VPN を横断するトラフィック量を少なく済ませる限りは、ほぼ持続可能でした。  一部の顧客は、アプリケーションが企業境界内からパブリック SaaS クラウドに移行した後も、VPN フォース トンネリングを現状として使用し続けました。

分散およびパフォーマンスに敏感なクラウド アプリケーションへの接続に強制トンネリングされた VPN の使用は最適とは言え、一部の企業ではセキュリティの現状を維持するために悪影響が受け入れらされています。 このシナリオの例となる図を次に示します。

![VPN Tunnel分割。](../media/vpn-split-tunneling/enterprise-network-traditional.png)

この問題は何年も前から増加し続け、多くのお客様がネットワーク トラフィック パターンの大幅な変化を報告しています。 オンプレミスに滞在するために使用されたトラフィックは、外部クラウド エンドポイントに接続されます。 多くの Microsoft のお客様は、ネットワーク トラフィックの約 80% が内部ソース (上の図の点線で表される) に送信されたと報告しています。 2020 年には、主要なワークロードをクラウドに移行した数が約 20% 以下になってきたので、これらの傾向は他の企業でも珍しくありません。 時間が経過するにつれて、クラウドジャーニーが進むにつれて、上記のモデルはますます面倒で持続不可能になり、クラウドファーストの世界に移行するにつれて組織が機敏になるのを防ぐ。

世界的な COVID-19 禍により、この問題に対する即時の対応が必要とされています。 IT 企業には、社員の安全を確保するため、大規模な在宅勤務の生産性を援助しなければいけないというこれまでにない要求が生じています。 Microsoft 365は、お客様が需要を満たすのに役立つ十分な位置にありますが、自宅で作業するユーザーの同時実行性が高い場合、大量の Microsoft 365 トラフィックが発生します。これは、強制トンネル VPN とオンプレミス ネットワーク境界を経由してルーティングされた場合、急速な飽和を引き起こし、VPN インフラストラクチャが容量を使い果たします。 この新しい現実では、VPN を使用して Microsoft 365 にアクセスするのはパフォーマンスの障害ではなく、Microsoft 365 に影響を与えるだけでなく、運用するために VPN に依存する必要がある重要なビジネス操作に影響を与えるハードウォールです。

Microsoft は、お客様や幅広い業界と長年にわたって緊密に連携し、これらの問題に対して、当社のサービス内から効果的かつ最新のソリューションを提供し、より最適な業務の実現をサポートしています。 [](./microsoft-365-network-connectivity-principles.md) Microsoft 365 サービスの接続の原則は、リモート ユーザーが効率的に動作するように設計されている一方で、組織がセキュリティを維持し、接続を制御できるように設計されています。 これらのソリューションは、限られた作業でも迅速に実装することができますが、上記の問題に大きなプラスの影響を及ぼす可能性があります。

リモート ワーカーの接続を最適化するための Microsoft の推奨戦略は、問題を迅速に軽減し、いくつかの簡単な手順で高いパフォーマンスを提供する点に重点を置いて行っています。 次の手順では、ボトルネックが発生した VPN サーバーをバイパスするいくつかの定義済みエンドポイントの従来の VPN アプローチを調整します。 同等、あるいはより優れたセキュリティ モデルを異なるレイヤに適用することで、企業ネットワークの出口ですべてのトラフィックを保護する必要がなくなります。 ほとんどの場合、これは数時間で効果的に達成され、要件の需要と時間が可能な限り他のワークロードに対して拡張可能です。

## <a name="common-vpn-scenarios"></a>一般的な VPN のシナリオ

以下の一覧では、エンタープライズ環境で最も一般的な VPN シナリオが表示されます。 ほとんどの企業は、従来モデル 1 (VPN 強制トンネリング) を運用しています。 このセクションでは、比較的少ない労力で達成できるモデル **2** への迅速かつ安全な移行に役立ち、ネットワークパフォーマンスとユーザー エクスペリエンスに大きなメリットがあります。

| モデル | 説明 |
| --- | --- |
| [1. VPN 強制トンネリング](#1-vpn-forced-tunnel) | トラフィックの 100% は、オンプレミス、インターネット、およびすべての O365/M365 を含む VPN トンネルに入ります |
| [2. いくつかの例外を含む VPN 強制トンネリング](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN トンネルが既定で使用され (既定のルート ポイントが VPNに繋がっている)、直接のアクセスが許可される最も重要な除外シナリオはほとんど使用されない。 |
| [3. 広範囲な例外を含む VPN 強制トンネリング](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN トンネルは既定で使用されます (既定のルート ポイントは VPN をポイントします)。直接移動できる広範な例外 (すべての Microsoft 365、All Salesforce、All Zoom など) |
| [4. VPN 選択的トンネリング](#4-vpn-selective-tunnel) | VPN トンネルは、corpnet ベースのサービスにのみ使用されます。 既定のルート (インターネットとすべてのインターネット ベースのサービス) は直接行きます。 |
| [5. VPN なし](#5-no-vpn) | #2 のバリエーション。 従来の VPN の代わりに、すべての corpnet サービスは最新のセキュリティ アプローチ (Zscaler ZPA、Azure Active Directory (Azure AD) プロキシ/MCAS など) を通じて公開されます。 |

### <a name="1-vpn-forced-tunnel"></a>1. VPN 強制トンネリング

ほとんどのエンタープライズ顧客の最も一般的な開始シナリオ。 強制 VPN が使用されます。つまり、エンドポイントが企業ネットワーク内にあるかどうかに関なく、トラフィックの 100% が企業ネットワークに送信されます。 外部 (インターネット) にバインドされたトラフィック (Microsoft 365インターネットブラウズなど) は、プロキシなどのオンプレミスのセキュリティ機器からヘア ピン留めされます。 したがって、リモートで作業しているユーザーの 100% 近い現在の環境では、このモデルは VPN インフラストラクチャに大きな負荷を与え、すべての企業トラフィックのパフォーマンスを大幅に低下させる可能性が高く、企業が危機の時に効率的に運用する可能性があります。

![VPN 強制Tunnelモデル 1。](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. 少数の認可された例外を含む VPN 強制トンネル

企業の運用効率が大幅に向上しました。 このモデルを使用すると、高負荷と待機時間に敏感ないくつかの制御および定義されたエンドポイントが VPN トンネルをバイパスし、Microsoft 365 サービスに直接Microsoft 365できます。 これにより、オフロードされたサービスのパフォーマンスが大幅に向上し、VPN インフラストラクチャへの負荷も軽減され、リソースに対するより低いコンテンツで動作する必要がある要素も可能になります。 この記事では、単純で定義されたアクションを多数の肯定的な結果で迅速に実行できるので、移行の支援に集中しています。

![VPN Tunnel 2 を分割します。](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. 広範囲な例外を含む VPN 強制トンネリング

モデル 2 の範囲を広げる。 定義されたエンドポイントの小さなグループを直接送信するのではなく、すべてのトラフィックを信頼できるサービス (Microsoft 365や SalesForce など) に直接送信します。 これにより、企業の VPN インフラストラクチャの負荷がさらに軽減され、決められたサービスのパフォーマンスが向上します。 このモデルの実現可能性を評価して実装するには、より多くの時間がかかる可能性が高いから、モデル 2 が正常に実施されると、後日繰り返し実行できる手順になる可能性があります。

![スプリット Tunnel VPN モデル 3.](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. VPN 選択的トンネリング

企業の IP アドレスを持つこととして識別されたトラフィックだけが VPN トンネルに送信され、インターネット パスが他のすべての既定のルートであるという点で、3 番目のモデルを反転します。 このモデルでは、組織が[ゼロ トラスト](https://www.microsoft.com/security/zero-trust?rtc=1)への道を歩み、安全な実装ができる必要があります。 このモデルまたはその一部のバリエーションは、企業ネットワークからクラウドに移動するサービスが多くなると、必要な既定になる可能性があります。

Microsoft では、このモデルを内部的に使用します。 Microsoft の VPN スプリット トンネリングの実装に関する詳細については、「 [RUNNING on VPN: Microsoft](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) がリモート ワークフォースを接続し続ける方法」を参照してください。

![VPN Tunnel 4 を分割します。](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. VPN なし

モデル番号 2 のより高度なバージョンで、内部サービスは、Azure AD Proxy、Defender for Cloud Apps、Zscaler ZPA などの最新のセキュリティ アプローチまたは SDWAN ソリューションを通じて公開されます。

![VPN Tunnel 5 を分割します。](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>スプリット トンネル VPN の実装

このセクションでは、VPN クライアント アーキテクチャを _VPN_ 強制トンネルから VPN 強制トンネルに移行するために必要な簡単な手順について説明します。一般的な [VPN](#common-vpn-scenarios) シナリオでは、いくつかの信頼できる例外を除き、VPN スプリット トンネル モデル [#2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) を使用します。

次の図は、推奨している VPN スプリット トンネリング ソリューションのしくみを示しています。

![スプリット トンネル VPN ソリューションの詳細。](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. 最適化するエンドポイントを決める

「URL [Microsoft 365 IP](urls-and-ip-address-ranges.md) アドレス範囲」の記事では、最適化に必要な主要なエンドポイントを明確に特定し、それらをオプティマイズとして分類 **します**。 現在、最適化する必要がある URL は 4 つ、IP サブネットは 20 個です。 この小規模なエンドポイント グループは、Microsoft 365 サービスへのトラフィック量の約 70% から 80% を占め、Teams メディア向けエンドポイントなどの遅延に敏感なエンドポイントを含む。 基本的に、これは特別な管理が必要なトラフィックであり、従来のネットワーク パスや VPN インフラストラクチャに大なるプレッシャーをかかえるトラフィックです。

このカテゴリの URL には、次のような特性があります。

- Microsoft インフラストラクチャにホストされている Microsoft が所有および管理するエンドポイントである
- IP が提供されている
- 変化率が低く、数も少ないと予想される (現在 20 の IP サブネット)
- 帯域幅や遅延の影響を受けやすい
- 必要なセキュリティ要素をネットワーク上で、インラインではなくサービスで提供することができる
- サービスへのトラフィック量の約 70 ~ 80% をMicrosoft 365します。

エンドポイントの分類と管理Microsoft 365詳細については、「管理エンドポイントの管理」[を参照Microsoft 365してください](managing-office-365-endpoints.md)。

#### <a name="optimize-urls"></a>URL を最適化する

現在の最適化 URL は次の表に記載されています。 ほとんどの状況では、エンドポイントがプロキシにではなく直接送信されるように設定されている[ブラウザ PAC ファイル](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)の URL エンドポイントのみを使用する必要があります。

| URL を最適化する | ポート/プロトコル | 用途 |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | これは、Outlook が Exchange Online サーバーへの接続に使用する主要なURL の 1 つであり、帯域幅の使用数と接続数が大量になります。 クイック検索、その他のメールボックス 予定表、空き時間の検索、ルールと通知の管理、Exchange オンラインのアーカイブ、送信トレイからのメール送信などといったオンライン上の機能では、ネットワークの遅延を少なくしておく必要があります。 |
| <https://outlook.office.com> | TCP 443 | このURLは Outlook Online Web Access が Exchange Online のサーバーに接続するために使用され、ネットワーク遅延の影響を受けやすくなっています。 SharePoint Online での大きなファイルのアップロードとダウンロードには、特に接続性が必要です。 |
| \<tenant\>https://.sharepoint.com | TCP 443 | これは、オンラインでの使用SharePointのプライマリ URL です。 |
| \<tenant\>https://-my.sharepoint.com | TCP 443 | これは OneDrive for Business の標準 URL で、帯域幅の使用率が高く、OneDrive for Business Sync ツールからの接続数が多くなることがあります。 |
| Teams のメディア IP (URL なし) | UDP 3478、3479、3480、および3481 | Relay Discovery の割り当てとリアルタイム トラフィック (3478)、オーディオ (3479)、ビデオ (3480)、ビデオスクリーン共有 (3481)。 これらは、メディア トラフィック (通話、会議などSkype for Business Microsoft Teamsのエンドポイントです。 ほとんどのエンドポイントは、Microsoft Teams クライアントが発信を確立するときに提供されます(サービスのリストにある必要な IP 内に含まれています)。 メディアの品質を最適化するには、UDP プロトコルを使用する必要があります。   |

上記の例では、**テナント** をテナント名Microsoft 365する必要があります。 たとえば **、contoso.onmicrosoft.com と** _contoso.sharepoint.com を_ _contoso-my.sharepoint.com。_

#### <a name="optimize-ip-address-ranges"></a>IP アドレスの範囲を最適化する

これらのエンドポイントが対応する IP アドレス範囲を記述する時点では、次のようになります。 この例、[Microsoft 365 IP および URL Web](microsoft-365-ip-web-service.md) サービス、[URL/IP](urls-and-ip-address-ranges.md) ページなどのスクリプトを使用して、構成を適用する際に更新プログラムを確認し、ポリシーを定期的に適用してください。[](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category)

```
104.146.128.0/17
13.107.128.0/22
13.107.136.0/22
13.107.18.10/31
13.107.6.152/31
13.107.64.0/18
131.253.33.215/32
132.245.0.0/16
150.171.32.0/22
150.171.40.0/22
204.79.197.215/32
23.103.160.0/20
40.104.0.0/15
40.108.128.0/17
40.96.0.0/13
52.104.0.0/14
52.112.0.0/14
52.96.0.0/14
52.120.0.0/14
```

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. VPN を介して、これらのエンドポイントへのアクセスを最適化する

こういった重要なエンドポイントを特定したら、それを VPN トンネルから逸らし、ユーザーのローカル インターネット接続を使用してサービスに直接接続できるようにする必要があります。  これを実現する方法は、使用する VPN 製品とマシンのプラットフォームによって異なりますが、ほとんどの VPN ソリューションでは、この手法を適用するポリシーを簡単に構成することができます。 VPN プラットフォーム固有のスプリット  トンネリングを行う方法については、「[一般 VPN プラットフォームの HOWTO ガイド](#howto-guides-for-common-vpn-platforms)」をご覧ください。

ソリューションを手動でテストしたい場合は、次の PowerShell の例を実行して、ルート テーブルからソリューションをエミュレートできます。 この例では、それぞれの Teams メディア IP サブネットのルートをルート テーブルに追加します。 Teams のメディアの前後でのパフォーマンスをテストをし、指定されたエンドポイントのルートの違いを観察できます。

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>例: Teams メディア IP サブネットをルート テーブルに追加する

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

上記のスクリプトで、 _$intIndex_ は、インターネットに接続されたインターフェースの索引 (PowerShellで **get-netadapter** を実行して検索し、_ifIndex_ の値を探します) であり、 _$gateway_ はそのインターフェースの既定のゲートウェイです (コマンド プロンプトの **ipconfig** か、 **(Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop** を PowerShellで実行し検索します)。

ルートを追加したら、コマンド プロンプトまたは PowerShell で「**印刷のルーティング**」を実行して、ルート テーブルが正しいことを確認できます。  出力には、追加したルートが含まれ、インターフェースのインデックス (この例では _22_) とそのインターフェースのゲートウェイ (この例では _192.168.1.1_) が表示されます。

![印刷出力をルーティングします。](../media/vpn-split-tunneling/vpn-route-print.png)

[最適化] カテゴリ内のすべての現在の IP アドレス範囲のルートを追加するには、次のスクリプトバリエーションを使用して、[Microsoft 365 IP と URL Web](microsoft-365-ip-web-service.md) サービスに対して現在の一連のオプティマイズ IP サブネットを照会し、ルート テーブルに追加できます。

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>例: すべての最適化サブネットをルート テーブルに追加する 

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
# Query the web service for IPs in the Optimize category
$ep = Invoke-RestMethod ("https://endpoints.office.com/endpoints/worldwide?clientrequestid=" + ([GUID]::NewGuid()).Guid)
# Output only IPv4 Optimize IPs to $optimizeIps
$destPrefix = $ep | where {$_.category -eq "Optimize"} | Select-Object -ExpandProperty ips | Where-Object { $_ -like '*.*' }
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

うっかり誤ったパラメーターでルートを追加してしまった場合、あるいは単に変更を元に戻したい場合は、次のコマンドを使用して、追加したルートを削除できます。

```powershell
foreach ($prefix in $destPrefix) {Remove-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

<!--- remmed until we add more reliable interface selection logic
#### Example script to add Teams Media subnets to the route table

```powershell
$adapter = get-netadapter | ? {$_.Status -eq "Up"}
$adapterIndex = $adapter.ifIndex
$gateway = (Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop

$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18"
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```
-->

VPN クライアントの設定を行い、**最適化** IP へのトラフィックがこの方法でルーティングされるようにしてください。 これにより、トラフィックは、Microsoft 365 サービスと接続エンドポイントを可能な限りユーザーに近い環境で提供する [Azure Front Door](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) などの Microsoft 365 Service Front Door などのローカル Microsoft リソースを利用できます。 これにより、世界中のユーザーに高いパフォーマンス レベルを提供し、 [Microsoft](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) の世界クラスのグローバル ネットワークをフルに活用できます。これは、ユーザーの直接出力から数ミリ秒以内である可能性があります。

## <a name="configuring-and-securing-teams-media-traffic"></a>Teams メディア トラフィックの構成と保護

一部の管理者は、スプリット トンネリング モデルを使用した Teams での発信フローの動作方法と接続のセキュリティを保護する方法に関して詳細な情報が必要かもしれません。

### <a name="configuration"></a>構成

通話と会議の両方で、Teams メディアに対して必要なオプティマイズ IP サブネットが正しく配置されている限り、Teams が [GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) 関数を呼び出して、特定の宛先に使用するルートに対応するローカル インターフェイスを特定すると、上記の Microsoft IP ブロック内の Microsoft 宛先に対してローカル インターフェイスが返されます。

一部の VPN クライアント ソフトウェアでは、URL に基づいてルーティング操作が可能です。 ただし、Teams のメディア トラフィックには URL が関連付けられていないため、このトラフィックのルーティングの制御は IP サブネットを使用して行う必要があります。

特定の状況では、Teams クライアントの設定とは関係なく、メディア トラフィックは正しいルートが設定されていても VPN トンネルを通過します。 このシナリオが発生した場合は、ファイアウォール ルールを使用して、VPN を使用Teams IP サブネットまたはポートの使用をブロックすれば十分です。

>[!IMPORTANT]
>すべての VPN シナリオTeams方法を使用してメディア トラフィックを確実にルーティングするには、ユーザーが Microsoft Teams クライアント バージョン **1.3.00.13565** 以上を実行している必要があります。 このバージョンには、クライアントが使用可能なネットワーク パスを検出する方法の改善が含まれています。

シグナリング トラフィックは HTTPS 経由で実行され、メディア トラフィックほど遅延に敏感ではなく、URL/IP データで許可としてマークされ、必要に応じて VPN クライアントを介して安全にルーティングできます。

>[!NOTE]
>Microsoft Edge **96 以上では**、ピアツーピア トラフィックの VPN スプリット トンネリングもサポートしています。 つまり、たとえば、エッジ上の Web クライアントTeams VPN スプリット トンネリングのメリットを得られるのです。 Edge で実行されている Web サイト用に設定する場合は、 [Edge WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) ポリシーを有効にする追加の手順を実行します。

### <a name="security"></a>セキュリティ

スプリット トンネルを回避するための一般的な引数の 1 つは、セキュリティが低い、つまり VPN トンネルを通過しないトラフィックは、VPN トンネルに適用される暗号化方式の恩恵を受け、セキュリティが低い。

これに対する主な反論は、機密性、認証、および RTP トラフィックに対する再生攻撃の保護を提供するリアルタイム転送プロトコル (RTP) のプロファイルである「_Secure Real-Time Transport Protocol (SRTP)_」によってメディアのトラフィックがすでに暗号化されていることです。  SRTP 自体は、ランダムに生成されたセッションキーに依存します。これは、TLS で保護された出力チャネルを介して交換されます。 これについては、[セキュリティガイド](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)で詳しく説明していますが、重要な部分はメディアの暗号化です。

メディア トラフィックは SRTP を使用して暗号化されます。SRTP は、セキュリティ保護された乱数ジェネレータによって生成され、シグナル出力 TLS チャネルで交換されるセッションキーを使用します。 さらに、仲介サーバーとその内部の次ホップの間で双方向に流れるメディアも、SRTP を使用して暗号化されます。

Skype for Business Online は、_Traversal Using Relay around NAT (TURN)_ を介したメディア リレーへの安全なアクセスのためのユーザー名/パスワードを生成します。 メディア リレーは、TLS で保護された SIP チャネル上でユーザー名/パスワードを交換します。 VPN トンネルを使用してクライアントを企業ネットワークに接続する場合でも、サービスに到達するために企業ネットワークを離れる場合、トラフィックは引き続き SRTP 形式でフローする必要があります。

Teams が音声やセッション トラバーサル ユーティリティ for _NAT (STUN)_ 増幅攻撃などの一般的なセキュリティ上の懸念を軽減する方法については、「[5.1 Security Considerations for Implementers](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)」を参照してください。

リモートワーク環境での最新のセキュリティ管理については、「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」を参照してください。

### <a name="testing"></a>テスト

ポリシーが適用された後、期待通り動作しているのを確認する必要があります。 ローカル インターネット接続を使用するようにパスが正しく設定されているかどうかテストするには、いくつかの方法があります。

- トレース ルートMicrosoft 365[含](https://aka.ms/netonboard)めて、接続テストを実行する接続テストを実行します。 また、このツールに VPN テストを追加し、さらに分析情報を提供する必要があります。

- 分割トンネル **のスコープ内** のエンドポイントへの単純な tracert には、次に示すパスが表示されます。

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  その後、ローカル ISP を経由してこのエンドポイントへのパスが表示され、スプリット トンネリング用に構成した Teams範囲の IP に解決する必要があります。

- Wireshark などのツールを使用してネットワーク キャプチャを取得します。  発信中に UDP でフィルタリングすると、 Teams の「**最適化**」範囲の IP アドレスに流れるトラフィックが表示されます。 このトラフィックに VPN トンネルが使用されている場合、メディア トラフィックはトレースに表示されません。

### <a name="additional-support-logs"></a>追加のサポート ログ

トラブル シューティングのためにさらにデータが必要な場合、または Microsoft のサポートが必要な場合は、次の情報を集めておくと、解決策を迅速に見つけることができます。 Microsoft サポートの **TSS Windows CMD ベースのユニバーサル TroubleShooting スクリプト** ツールセットを使用すると、関連するログを簡単に収集できます。 使用に関するツールと手順については、次のページをご覧ください <https://aka.ms/TssTools>。

## <a name="how-to-optimize-stream--live-events"></a>ライブ イベントのストリーム&する方法

Microsoft 365 ライブ イベント トラフィック (これには、Teams が生成されたライブ イベントへの出席者、および Teams、ストリーム、または Yammer 経由で外部エンコーダーで生成されたイベントが含まれます)、オンデマンド ストリーム トラフィックは現在、サービスの [URL/IP](urls-and-ip-address-ranges.md) リストの Default とオプティマイズに分類されています。 これらのエンドポイントは、他のサービスでも使用される可能性がある CDN 上でホストされているので、Default に分類されます。 お客様は一般に、この種類のトラフィックをプロキシし、このようなエンドポイントで通常行われるセキュリティ要素を適用することを好む。

多くのお客様は、VPN インフラストラクチャを介して大ボリュームおよび待機時間に敏感なトラフィックをルーティングするのではなく、ローカル インターネット接続から直接ユーザーを Stream/Live イベントに接続するために必要な URL/IP データを要求しています。 通常、これは、専用の名前空間とエンドポイントの正確な IP 情報の両方なしでは使用できません。これは、既定として分類された Microsoft 365 エンドポイントには提供 **されません**。

強制トンネル VPN を使用するクライアントからの Stream/Live イベント サービスの直接接続を有効にするには、次の手順を使用します。 このソリューションは、在宅作業のシナリオのためにネットワーク トラフィックが多い一方で、VPN を使用して Live Events トラフィックをルーティングしないようにするオプションを顧客に提供することを目的とします。 可能であれば、検査プロキシを介してサービスにアクセスする必要があります。

>[!NOTE]
>このソリューションを使用すると、提供された IP アドレスに解決されないサービス要素が VPN を通過する場合がありますが、ストリーミング データのような大量トラフィックの大部分は必要です。 このオフロードによってキャッチされる Live Events/Stream のスコープ外には他の要素が含まれる場合がありますが、直接行く前に _FQDN と_ IP 一致の両方を満たす必要がある場合は、これらを制限する必要があります。

>[!IMPORTANT]
>お客様は、ライブ イベントのパフォーマンス向上を超え、VPN をバイパスするトラフィックを多く送信するリスクを量り取る必要があります。

ライブ イベントとストリームの強制トンネルTeams実装するには、次の手順を適用する必要があります。

### <a name="1-configure-external-dns-resolution"></a>1. 外部 DNS 解決を構成する

クライアントは、次のホスト名を IP アドレスに解決するために、外部の再帰的な DNS 解決を利用できる必要があります。

- \*.azureedge.net
- \*.media.azure.net
- \*.bmc.cdn.office.net

**\*.azureedge.net** は Stream イベントに使用されます (Microsoft Stream でのライブ ストリーミング用にエンコーダーを構成 [する - Microsoft Stream |Microsoft Docs](/stream/live-encoder-setup))。

**\*.media.azure.net** **\*と .bmc.cdn.office.net** は、Teams が生成するライブ イベント (クイック スタート イベント、RTMP-In サポートされているイベント [ロードマップ ID 84960]) に使用されます。Teams クライアントからスケジュールされます。

 これらのエンドポイントの一部は、Stream/Live イベント以外の他の要素と共有されています。VPN ソリューションで技術的に可能な場合でも、これらの FQDN を使用して VPN オフロードを構成する必要があります (たとえば、IP ではなく FQDN で動作する場合)。

FQDN は VPN 構成では必要ありません。これらは純粋に関連するトラフィックを直接送信するために、AP と組み合わせて PAC ファイルで使用するために使用されます。

### <a name="2-implement-pac-file-changes-where-required"></a>2. PAC ファイルの変更を実装する (必要な場合)

VPN の実行中に PAC ファイルを使用してプロキシ経由でトラフィックをルーティングする組織の場合、これは通常、FQDN を使用して実現されます。 ただし、Stream/Live イベント **\*** では、提供されるホスト名には .azureedge.net などのワイルドカードが含まれています。また、完全な IP リストを提供できない他の要素も含まれます。 したがって、DNS ワイルドカードの一致に基づいて要求が直接送信される場合、手順 3 で直接パスを経由するルートが無い場合、これらのエンドポイントへのトラフィックは [ブロック](#3-configure-routing-on-the-vpn-to-enable-direct-egress)されます。

これを解決するために、次の IP を提供し、PAC ファイルの例の手順 [1](#1-configure-external-dns-resolution) のホスト名と組み合わせて使用します。 PAC ファイルは、URL が Stream/Live イベントで使用される URL と一致する場合、その URL が一致する場合は、DNS 参照から返された IP がサービスに提供された IP と一致する場合も確認します。 両方 _が一_ 致する場合、トラフィックは直接ルーティングされます。 いずれかの要素 (FQDN/IP) が一致しない場合、トラフィックはプロキシに送信されます。 その結果、IP 名前空間と定義済み名前空間の両方のスコープ外の IP に解決される何でも、通常通り VPN 経由でプロキシを通過できます。

#### <a name="gathering-the-current-lists-of-cdn-endpoints"></a>エンドポイントの現在のリストCDNする

ライブ イベントでは、複数のCDNプロバイダーを使用して顧客にストリーミングし、最適なカバレッジ、品質、復元性を提供します。 現在、Microsoft と verizon Azure CDNの両方が使用されています。 時間がたつ間に、地域の可用性などの状況により変更される可能性があります。 この記事は、IP 範囲を最新の状態に保つソースです。

Microsoft Azure CDNの場合は、公式 Microsoft ダウンロード センターから [Azure IP](https://www.microsoft.com/download/details.aspx?id=56519) 範囲とサービス タグをダウンロード - パブリック クラウドからリストをダウンロードできます。JSON の *サービス タグ AzureFrontdoor.Frontend* を特に探す必要があります。*addressPrefixes は* IPv4/IPv6 サブネットを表示します。 時間がたつ間に、AP は変更できますが、サービス タグリストは常に更新され、使用されます。

Verizon (Edgecast) [https://docs.microsoft.com/rest/api/cdn/edge-nodes/list](/rest/api/cdn/edge-nodes/list) のAzure CDNには、([試す] を **クリック)** **\_** を使用して網羅的なリストを見つける必要があります。プレミアムVerizon セクションを具体的に検索する必要があります。 この API には、すべての Edgecast IPs (origin と Anycast) が表示されます。 現在、API がオリジンと Anycast を区別するメカニズムは提供されていない。

これを PAC ファイルに実装するには、次の例を使用して、FQDN を介して Microsoft 365 Optimize トラフィック ダイレクト (推奨されるベスト プラクティス) と、FQDN と返される IP アドレスの組み合わせを介して重要な Stream/Live Events トラフィックを直接送信します。 Contoso の _プレースホルダー名_ は、contoso がユーザーの名前である特定のテナントの名前に編集する contoso.onmicrosoft.com

##### <a name="example-pac-file"></a>PAC ファイルの例

PAC ファイルを生成する方法の例を次に示します。

1. 以下のスクリプトをローカル ハード ディスクに保存 _します(Get-TLEPacFile.ps1_)。
1. [Verizon URL に移動し](/rest/api/cdn/edge-nodes/list#code-try-0)、結果の JSON をダウンロードします (cdnedgenodes.json のようなファイルにコピー貼り付け)
1. スクリプトと同じフォルダーにファイルを置きます。
1. PowerShell ウィンドウで、次のコマンドを実行します。 SPO URL が必要な場合は、別のテナント名を変更します。 これはタイプ 2 なので、 **オプティマイズ** と **許可** (Type 1 はオプティマイズのみ) です。

   ```powershell
   .\Get-TLEPacFile.ps1 -Instance Worldwide -Type 2 -TenantName <contoso> -CdnEdgeNodesFilePath .\cdnedgenodes.json -FilePath TLE.pac
   ```

5. TLE.pac ファイルには、すべての名前空間と IPs (IPv4/IPv6) が含まれる。

###### <a name="get-tlepacfileps1"></a>Get-TLEPacFile.ps1

```powershell
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License.

<#PSScriptInfo

.VERSION 1.0.4

.AUTHOR Microsoft Corporation

.GUID 7f692977-e76c-4582-97d5-9989850a2529

.COMPANYNAME Microsoft

.COPYRIGHT
Copyright (c) Microsoft Corporation. All rights reserved.
Licensed under the MIT License.

.TAGS PAC Microsoft Microsoft365 365

.LICENSEURI

.PROJECTURI http://aka.ms/ipurlws

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

#>

<#

.SYNOPSIS

Create a PAC file for Microsoft 365 prioritized connectivity

.DESCRIPTION

This script will access updated information to create a PAC file to prioritize Microsoft 365 Urls for
better access to the service. This script will allow you to create different types of files depending
on how traffic needs to be prioritized.

.PARAMETER Instance

The service instance inside Microsoft 365.

.PARAMETER ClientRequestId

The client request id to connect to the web service to query up to date Urls.

.PARAMETER DirectProxySettings

The direct proxy settings for priority traffic.

.PARAMETER DefaultProxySettings

The default proxy settings for non priority traffic.

.PARAMETER Type

The type of prioritization to give. Valid values are 1 and 2, which are 2 different modes of operation.
Type 1 will send Optimize traffic to the direct route. Type 2 will send Optimize and Allow traffic to
the direct route.

.PARAMETER Lowercase

Flag this to include lowercase transformation into the PAC file for the host name matching.

.PARAMETER TenantName

The tenant name to replace wildcard Urls in the webservice.

.PARAMETER ServiceAreas

The service areas to filter endpoints by in the webservice.

.PARAMETER FilePath

The file to print the content to.

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type1.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance China -Type 2 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type2.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance WorldWide -Lowercase -TenantName tenantName -ServiceAreas Sharepoint

#>

#Requires -Version 2

[CmdletBinding(SupportsShouldProcess=$True)]
Param (
    [Parameter(Mandatory = $false)]
    [ValidateSet('Worldwide', 'Germany', 'China', 'USGovDoD', 'USGovGCCHigh')]
    [String] $Instance = "Worldwide",

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [guid] $ClientRequestId = [Guid]::NewGuid().Guid,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DirectProxySettings = 'DIRECT',

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DefaultProxySettings = 'PROXY 10.10.10.10:8080',

    [Parameter(Mandatory = $false)]
    [ValidateRange(1, 2)]
    [int] $Type = 1,

    [Parameter(Mandatory = $false)]
    [switch] $Lowercase = $false,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $TenantName,

    [Parameter(Mandatory = $false)]
    [ValidateSet('Exchange', 'SharePoint', 'Common', 'Skype')]
    [string[]] $ServiceAreas,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $FilePath,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $CdnEdgeNodesFilePath
)

##################################################################################################################
### Global constants
##################################################################################################################

$baseServiceUrl = "https://endpoints.office.com/endpoints/$Instance/?ClientRequestId={$ClientRequestId}"
$directProxyVarName = "direct"
$defaultProxyVarName = "proxyServer"
$bl = "`r`n"

##################################################################################################################
### Functions to create PAC files
##################################################################################################################

function Get-PacClauses
{
    param(
        [Parameter(Mandatory = $false)]
        [string[]] $Urls,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $ReturnVarName
    )

    if (!$Urls)
    {
        return ""
    }

    $clauses =  (($Urls | ForEach-Object { "shExpMatch(host, `"$_`")" }) -Join "$bl        || ")

@"
    if($clauses)
    {
        return $ReturnVarName;
    }
"@
}

function Get-PacString
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [array[]] $MapVarUrls
    )

@"
// This PAC file will provide proxy config to Microsoft 365 services
//  using data from the public web service for all endpoints
function FindProxyForURL(url, host)
{
    var $directProxyVarName = "$DirectProxySettings";
    var $defaultProxyVarName = "$DefaultProxySettings";

$( if ($Lowercase) { "    host = host.toLowerCase();" })

$( ($MapVarUrls | ForEach-Object { Get-PACClauses -ReturnVarName $_.Item1 -Urls $_.Item2 }) -Join "$bl$bl" )

$( if (!$ServiceAreas -or $ServiceAreas.Contains('Skype')) { Get-TLEPacConfiguration })

    return $defaultProxyVarName;
}
"@ -replace "($bl){3,}","$bl$bl" # Collapse more than one blank line in the PAC file so it looks better.
}

##################################################################################################################
### Functions to get and filter endpoints
##################################################################################################################

function Get-TLEPacConfiguration {
    param ()
    $PreBlock = @"
    // Don't Proxy Teams Live Events traffic

    if(shExpMatch(host, "*.azureedge.net")
    || shExpMatch(host, "*.bmc.cdn.office.net")
    || shExpMatch(host, "*.media.azure.net"))
    {
        var resolved_ip = dnsResolveEx(host);

"@
    $TLESb = New-Object 'System.Text.StringBuilder'
    $TLESb.Append($PreBlock) | Out-Null

    if (![string]::IsNullOrEmpty($CdnEdgeNodesFilePath) -and (Test-Path -Path $CdnEdgeNodesFilePath)) {
        $CdnData = Get-Content -Path $CdnEdgeNodesFilePath -Raw -ErrorAction SilentlyContinue | ConvertFrom-Json | Select-Object -ExpandProperty value | 
            Where-Object { $_.name -eq 'Premium_Verizon'} | Select-Object -First 1 -ExpandProperty properties | 
            Select-Object -ExpandProperty ipAddressGroups
        $CdnData | Select-Object -ExpandProperty ipv4Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
        $CdnData | Select-Object -ExpandProperty ipv6Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
    }
    $AzureIPsUrl = Invoke-WebRequest -Uri "https://www.microsoft.com/en-us/download/confirmation.aspx?id=56519" -UseBasicParsing -ErrorAction SilentlyContinue  | 
            Select-Object -ExpandProperty Links | Select-Object -ExpandProperty href | 
            Where-Object { $_.EndsWith('.json') -and $_ -match 'ServiceTags' } | Select-Object -First 1
    if ($AzureIPsUrl) {
        Invoke-RestMethod -Uri $AzureIPsUrl -ErrorAction SilentlyContinue | Select-Object -ExpandProperty values | 
            Where-Object { $_.name -eq 'AzureFrontDoor.Frontend' } | Select-Object -First 1 -ExpandProperty properties |
            Select-Object -ExpandProperty addressPrefixes | ForEach-Object {
                if ($TLESb.Length -eq $PreBlock.Length) {
                    $TLESb.Append("        if(") | Out-Null
                }
                else {
                    $TLESb.AppendLine() | Out-Null
                    $TLESb.Append("        || ") | Out-Null
                }
                $TLESb.Append("isInNetEx(resolved_ip, `"$_`")") | Out-Null
            }
    }
    if ($TLESb.Length -gt $PreBlock.Length) {
        $TLESb.AppendLine(")") | Out-Null
        $TLESb.AppendLine("        {") | Out-Null
        $TLESb.AppendLine("            return $directProxyVarName;") | Out-Null
        $TLESb.AppendLine("        }") | Out-Null
    }
    else {
        $TLESb.AppendLine("        // no addresses found for service via script") | Out-Null
    }
    $TLESb.AppendLine("    }") | Out-Null
    return $TLESb.ToString()
}

function Get-Regex
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $Fqdn
    )

    return "^" + $Fqdn.Replace(".", "\.").Replace("*", ".*").Replace("?", ".?") + "$"
}

function Match-RegexList
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $ToMatch,

        [Parameter(Mandatory = $false)]
        [string[]] $MatchList
    )

    if (!$MatchList)
    {
        return $false
    }
    foreach ($regex in $MatchList)
    {
        if ($regex -ne $ToMatch -and $ToMatch -match (Get-Regex $regex))
        {
            return $true
        }
    }
    return $false
}

function Get-Endpoints
{
    $url = $baseServiceUrl
    if ($TenantName)
    {
        $url += "&TenantName=$TenantName"
    }
    if ($ServiceAreas)
    {
        $url += "&ServiceAreas=" + ($ServiceAreas -Join ",")
    }
    return Invoke-RestMethod -Uri $url
}

function Get-Urls
{
    param(
        [Parameter(Mandatory = $false)]
        [psobject[]] $Endpoints
    )

    if ($Endpoints)
    {
        return $Endpoints | Where-Object { $_.urls } | ForEach-Object { $_.urls } | Sort-Object -Unique
    }
    return @()
}

function Get-UrlVarTuple
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $VarName,

        [Parameter(Mandatory = $false)]
        [string[]] $Urls
    )
    return New-Object 'Tuple[string,string[]]'($VarName, $Urls)
}

function Get-MapVarUrls
{
    Write-Verbose "Retrieving all endpoints for instance $Instance from web service."
    $Endpoints = Get-Endpoints

    if ($Type -eq 1)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -eq "Optimize" })
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -ne "Optimize" }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
    elseif ($Type -eq 2)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -in @("Optimize", "Allow")})
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -notin @("Optimize", "Allow") }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
}

##################################################################################################################
### Main script
##################################################################################################################

$content = Get-PacString (Get-MapVarUrls)

if ($FilePath)
{
    $content | Out-File -FilePath $FilePath -Encoding ascii
}
else
{
    $content
}
```

スクリプトは **AzureFrontDoor.Frontend** のダウンロード [URL](https://www.microsoft.com/download/details.aspx?id=56519) とキーオフに基づいて Azure リストを自動的に解析します。そのため、手動で取得する必要はありません。

繰り返しますが、FQDN を使用して VPN オフロードを実行する必要はありません。関数内 **の** FQDN と IP アドレスの両方を利用すると、このオフロードの使用を、Live イベント/ストリームを含む制限されたエンドポイントセットに範囲を設定するのに役立ちます。 関数の構造化方法により、クライアントによって直接一覧表示される FQDN に対して DNS 参照が実行されます。つまり、残りの名前空間の DNS 解決は変更されません。

Live Events および Stream **\*** に関連しないエンドポイントをオフロードするリスクを制限する場合は、すべての Azure CDN ユーザーに使用される共有ドメインであり、このリスクの大部分が存在する構成から .azureedge.net ドメインを削除できます。 この欠点は、外部エンコーダーを使用するイベントは最適化されませんが、外部エンコーダー内で生成またはTeamsです。

### <a name="3-configure-routing-on-the-vpn-to-enable-direct-egress"></a>3. 直接出力を有効にするために VPN のルーティングを構成する

最後の手順では、「**CDN Endpoints** の現在のリストを VPN 構成に収集する」で説明されている Live イベントの直接ルートを追加し、トラフィックが強制トンネルを介して VPN に送信されなかることを確認します。 Microsoft 365 Optimize エンドポイントに対してこれを行う方法の詳細については、「[VPN](#implement-vpn-split-tunneling) スプリット トンネリングの実装」セクションを参照してください。このドキュメントに記載されている Stream/Live イベントの AP のプロセスはまったく同じです。

VPN 構成には、エンドポイントの現在のリストを収集する [](#gathering-the-current-lists-of-cdn-endpoints) (FQDN ではなく) CDNに注意してください。

### <a name="stream--live-events-optimization-faq"></a>ストリーム &ライブ イベントの最適化に関する FAQ

#### <a name="will-this-send-all-my-traffic-to-the-service-direct"></a>これにより、すべてのトラフィックがサービスに直接送信されますか?

いいえ、これにより Live イベントまたはストリーム ビデオダイレクトの遅延に敏感なストリーミング トラフィックが送信されます。公開された AP に解決されない場合、他のトラフィックは引き続き VPN トンネルを使用します。

#### <a name="do-i-need-to-use-the-ipv6-addresses"></a>IPv6 アドレスを使用する必要がありますか?

いいえ、接続は必要な場合にのみ IPv4 にできます。

#### <a name="why-are-these-ips-not-published-in-the-microsoft-365-urlip-service"></a>これらの IP が URL/IP サービスのMicrosoft 365されない理由

Microsoft では、サービス内の情報の形式と種類に関する厳密な管理を行い、お客様が情報を確実に使用して、エンドポイント カテゴリに基づいて安全で最適なルーティングを実装できます。

[ **既定の** エンドポイント] カテゴリには、さまざまな理由で IP 情報が提供されません (既定のエンドポイントは Microsoft の制御の外部にある場合や、頻繁に変更される可能性がある、または他の要素と共有されるブロックに含まれます)。 このため、既定のエンドポイントは、通常の Web トラフィックのように、FQDN を介して検査プロキシに送信するように設計されています。

この場合、上記のエンドポイントは、Live イベントまたは Stream 以外の Microsoft 以外の制御要素によって使用される可能性のある CDN であり、トラフィックダイレクトを送信すると、これらの ID に解決されるその他の意味もクライアントから直接送信されます。 現在のグローバル危機の固有の性質と、お客様の短期的なニーズを満たすために、Microsoft は、お客様が適した状態で使用するために上記の情報を提供しました。

Microsoft は、今後の Allow/Optimize エンドポイント カテゴリに含まれるライブ イベント エンドポイントを再構成する作業を行っています。

#### <a name="do-i-only-need-to-allow-access-to-these-ips"></a>これらの AP へのアクセスのみを許可する必要がありますか?

いいえ、サービスを運用するには、[URL/IP](urls-and-ip-address-ranges.md) サービス内のすべての必須マーク付きエンドポイントへのアクセスが不可欠です。 さらに、Stream (ID 41-45) のマークが付いている任意のオプション エンドポイントが必要です。

#### <a name="what-scenarios-will-this-advice-cover"></a>このアドバイスでカバーされるシナリオは何ですか?

1. アプリ内で生成されるライブ イベントTeamsアプリ
2. ストリームホスト型コンテンツの表示
3. 外部デバイス (エンコーダー) によって生成されるイベント

#### <a name="does-this-advice-cover-presenter-traffic"></a>このアドバイスは発表者のトラフィックをカバーしていますか?

そうではありません。上記のアドバイスは、サービスを利用する人のためのものです。 Teams 内から提示すると、発表者のトラフィックが URL/IP サービス行 11 に記載されているオプティマイズ マークされた UDP エンドポイントに流れ、VPN スプリット トンネリングの実装セクションで説明されている詳細な [VPN](#implement-vpn-split-tunneling) オフロードアドバイスが表示されます。

#### <a name="does-this-configuration-risk-traffic-other-than-live-events-amp-stream-being-sent-direct"></a>この構成では、ライブ イベント ストリーム以外のトラフィック &amp; が直接送信されるリスクがありますか?

はい、サービスの一部の要素で使用される共有 FQDN のため、これは避けできません。 通常、このトラフィックは、検査を適用できる企業プロキシ経由で送信されます。 VPN 分割トンネルのシナリオでは、FQDN と IPs の両方を使用すると、このリスクを最小限に抑えますが、それでも存在します。 お客様は、オフロード構成から .azureedge.net ドメインを削除し、このリスクを最小限に抑えますが、これにより、ストリームでサポートされるライブ イベント (Teams スケジュールされた外部エンコーダー イベント、Teams で生成される Yammer イベント、Yammer スケジュールされた外部エンコーダー イベント、Stream スケジュールされたイベントまたはストリームからのオンデマンド表示) のオフロードが削除されます。**\*** イベントは、スケジュールされ、Teams影響を受けません。

## <a name="howto-guides-for-common-vpn-platforms"></a>一般 VPN プラットフォームのHOWTO ガイド

このセクションでは、この領域で最も一般的なパートナーからのトラフィックに対してMicrosoft 365トンネリングを実装するための詳細なガイドへのリンクを提供します。 ガイドは利用可能になり次第、追加する予定です。

- **Windows 10 VPN クライアント**: ネイティブ Microsoft 365 VPN クライアントを使用したリモート ワーカーのトラフィックWindows 10 [最適化](/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco Anyconnect**：[ Anyconnect スプリット トンネリングを Office365 向けに最適化する](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect**: [VPN スプリット 経由Microsoft 365トラフィックの最適化Tunnelアクセス ルートを除外する](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 Networks BIG-IP APM**: [BIG-IP APM](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365) を使用Microsoft 365 VPN を介したリモート アクセスでのトラフィックの最適化
- **Citrix Gateway**: [Office365 向けのCitrix Gateway VPN スプリット トンネルの最適化](https://docs.citrix.com/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse Secure**: [VPN トンネリング: スプリット](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417) トンネリングを構成して、アプリケーションからMicrosoft 365する方法
- **Check Point VPN**: [Split Tunnelおよび他Microsoft 365 SaaS アプリケーションを構成する方法](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="vpn-split-tunneling-faq"></a>VPN スプリット トンネリングに関する FAQ

Microsoft Security Team は、セキュリティ専門家と [IT](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) 担当者が、今日の独自のリモート作業シナリオ (ブログ投稿) で最新のセキュリティ制御を実現するための代替手段を公開しました。この記事では、セキュリティ専門家の主要な方法の概要と、IT が今日の独自のリモート作業シナリオで最新のセキュリティ制御を実現できます。 さらに、この件に関してお客様からよく寄せられる質問と回答を以下に示します。

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>データを引き出される可能性がある、信頼していない他のテナントにユーザーがアクセスすることを防ぐにはどうすればいいですか？

[「テナントの制限」と呼ばれる機能](/azure/active-directory/manage-apps/tenant-restrictions)が回答になります。 認証トラフィックは、ボリュームが大きく、特に待機時間に敏感ではないので、VPN ソリューションを介して、機能が適用されるオンプレミス プロキシに送信できます。 信頼できるテナントの許可リストはここで管理され、クライアントが信頼されていないテナントにトークンを取得しようとすると、プロキシは要求を拒否します。 信頼されているテナントの場合、ユーザーが適切な資格情報とアクセス権限を持っていると、トークンを取得できます。

したがって、ユーザーは上記の Optimize マークされたエンドポイントに TCP/UDP 接続を行えますが、問題のテナントにアクセスするための有効なトークンがなくても、単にログインしてデータにアクセス/移動することはできません。

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>このモデルでは、個人の OneDrive アカウントなど、コンシューマー サービスへのアクセスはできますか？

いいえ、Microsoft 365 エンドポイントはコンシューマー サービス (例として Onedrive.live.com) と同じではないので、スプリット トンネルではユーザーがコンシューマー サービスに直接アクセスすることはできません。 コンシューマー エンドポイントへのトラフィックは引き続き VPN トンネルを使用し、既存のポリシーが引き続き適用されます。

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>トラフィックがオンプレミスのソリューションを通過しなくなったときに、DLP を適用して機密データを保護するにはどうすればよいですか？

機密情報が偶発的に漏えいしないように、Microsoft 365組み込みのツールが豊富に[含まれています](../compliance/information-protection.md)。 Teams と SharePoint の組み込みの [ DLP 機能](../compliance/dlp-learn-about-dlp.md)を使用して、不適切に保存または共有された機密情報を検出できます。 リモート作業戦略の一部に独自デバイス (BYOD) ポリシーが含まれる場合は、アプリベースの条件付きアクセス[](/azure/active-directory/conditional-access/app-based-conditional-access)を使用して、機密データがユーザーの個人デバイスにダウンロードされるのを防ぐ

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>ユーザーが直接接続を行っている時に、ユーザーの認証制御を評価、維持するにはどうすればよいですか？

Q1 に記載されているテナント制限機能に加えて、「[条件付きアクセス ポリシー](/azure/active-directory/conditional-access/overview)」を適用して、認証リクエストのリスクを動的に評価し、適切な対応を行うことができます。 Microsoft では、[ゼロトラスト](https://www.microsoft.com/security/zero-trust?rtc=1) モデルを時間の間に実装し、条件付きアクセス ポリシー Azure ADを使用して、モバイルおよびクラウドファーストの世界での制御を維持できます。 条件付きアクセス ポリシーを使用すると、次のようなさまざまな要因に基づいて、認証要求が成功したかどうかをリアルタイムで判断できます。

- デバイス、デバイスは既知/信頼済み/ドメインに参加しているか？
- IP アドレス – 認証要求は既知の企業 IP アドレスからのものか？ または信頼していない場所からのものか？
- アプリケーション – ユーザーはこのアプリケーションの使用を許可されているか？

次に、承認、MFA のトリガー、またはこれらのポリシーに基づく認証のブロックなどのポリシーをトリガーできます。

### <a name="how-do-i-protect-against-viruses-and-malware"></a>ウイルスやマルウェアからの保護はどうすればいいですか？

繰り返Microsoft 365、このドキュメントで概説されている、サービス自体のさまざまなレイヤーのオプティマイズマークエンドポイントに対する保護[を提供します](/office365/Enterprise/office-365-malware-and-ransomware-protection)。 上記のように、プロトコル/トラフィックを完全に理解していない可能性のあるデバイスに沿って実行するのではなく、サービス自体にこれらのセキュリティ要素を提供する方が非常に効率的です。 既定では、オンラインSharePointファイル[のアップロードで既知のマルウェアが](../security/office-365-security/virus-detection-in-spo.md)自動的にスキャンされます

上記のExchangeエンドポイントでは、Exchange Online Protection および [microsoft Defender for Microsoft 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) は、サービスへのトラフィックのセキュリティを提供する優れた仕事をします。 [](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>「最適化」トラフィック以外にも直接送信は行えますか？

「**最適化**」マークの付いたエンドポイントが優先されます。これらのエンドポイントは、下位レベルでの作業に最大の利益をもたらすからです。 ただし、必要に応じて、サービスが機能し、必要に応じて使用できる IP アドレスがエンドポイントに提供される場合は、[マークされたエンドポイントを許可する] が必要です。

また、セキュリティ保護された Web ゲートウェイと呼ばれるクラウドベースのプロキシ/セキュリティ ソリューションを提供するさまざまなベンダーがいて、一般的な Web 閲覧用の中央セキュリティ、制御、および企業ポリシー アプリケーションを提供します。 これらのソリューションは、ユーザーに近いクラウドベースの場所から安全なインターネット アクセスを提供することで、高可用性、パフォーマンス、プロビジョニングがユーザーに近い場合、クラウドファーストの世界でうまく機能します。 これにより、一般的な閲覧トラフィック用の VPN/企業ネットワークを介したヘアピンの必要性が取り除かれ、一方で一般的なセキュリティ制御が可能です。

ただし、これらのソリューションを使用する場合でも、オプティマイズのマーク付きトラフィックをサービスに直接Microsoft 365強く推奨しています。

Azure Virtual Network への直接アクセスを許可する方法については、「 [Azure VPN Gateway Point-to-site](/azure/vpn-gateway/work-remotely-support) を使用したリモート作業」を参照してください。

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>なぜポート 80 が必要なのですか？ トラフィックは平文で送信されていますか？

ポート 80 はポート 443 セッションへのリダイレクトなどにのみ使用され、顧客データは送信されないか、ポート 80 経由ではアクセスできません。 [暗号化](../compliance/encryption.md)では、Microsoft 365 の転送中および保存中のデータの暗号化の概要と、[](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic)SRTP を使用してメディア トラフィックを保護する方法Teams示します。

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-microsoft-365"></a>このアドバイスは、中国で世界中のユーザーインスタンスを使用しているユーザーに適用Microsoft 365?

**いいえ**、されません。  上記のアドバイスに対する 1 つの注意点は、PRC のユーザーが世界中のユーザーのインスタンスに接続Microsoft 365。 この地域ではクロスボーダー ネットワークの混雑が頻繁に発生するため、直接のインターネットの下りのパフォーマンスは変動する可能性があります。 当地域のほとんどのユーザーは、VPN を使用して企業ネットワークにトラフィックを取り込み、許可された MPLS 回線などを利用し、最適化されたパスを介して国外への送信を行っています。 詳しくは、中国ユーザー向けパフォーマンス[Microsoft 365の記事をご覧ください](microsoft-365-networking-china.md)。

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>スプリット トンネル構成は、ブラウザーで実行Teamsに機能しますか?

はい、注意点があります。 ほとんどのTeams機能は、「クライアントを取得する」に記載されているブラウザー[でMicrosoft Teams](/microsoftteams/get-clients#web-client)。

さらに、**Microsoft Edge 96** 以上では、[エッジ WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) ポリシーを有効にすることで、ピアツーピア トラフィックの VPN スプリット トンネリングをサポートしています。 現時点では、他のブラウザーがピアツーピア トラフィックの VPN スプリット トンネリングをサポートしていない場合があります。

## <a name="related-articles"></a>関連記事

[概要: VPN スプリット トンネリング (Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365のパフォーマンスの最適化](microsoft-365-networking-china.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365とパフォーマンスの調整](network-planning-and-performance.md)
