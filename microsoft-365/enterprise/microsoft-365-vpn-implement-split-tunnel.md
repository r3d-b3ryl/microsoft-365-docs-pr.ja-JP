---
title: VPN スプリット トンネリングを実装するMicrosoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
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
ms.openlocfilehash: ee8c0929682370d581c9d1b5c738d682d3f91a01
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320439"
---
# <a name="implementing-vpn-split-tunneling-for-microsoft-365"></a>VPN スプリット トンネリングを実装するMicrosoft 365

>[!NOTE]
>この記事は、リモート ユーザーの最適化に関するMicrosoft 365の一部です。

>- VPN スプリット トンネリングを使用してリモート ユーザー Microsoft 365接続を最適化する方法の概要については、「[Overview: VPN split tunneling for remoteing for remote」を参照](microsoft-365-vpn-split-tunnel.md)Microsoft 365。
>- VPN スプリット トンネリングのシナリオの詳細な一覧については、「VPN スプリット トンネリングの一般的なシナリオ」を参照[Microsoft 365。](microsoft-365-vpn-common-scenarios.md)
>- VPN スプリット トンネリング環境でのTeamsメディア トラフィックのセキュリティ保護に関するガイダンスについては、「VPN スプリット トンネリングTeamsメディア トラフィックのセキュリティ[保護」を参照してください](microsoft-365-vpn-securing-teams.md)。
>- VPN 環境で Stream イベントとライブ イベントを構成する方法については、「VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項」 [を参照してください](microsoft-365-vpn-stream-and-live-events.md)。
>- 中国のユーザーに対するMicrosoft 365のパフォーマンスの最適化の詳細については、「中国のユーザー Microsoft 365[パフォーマンスの最適化」を参照してください](microsoft-365-networking-china.md)。

リモート ワーカーの接続を最適化するための Microsoft の推奨戦略は、問題を迅速に軽減し、いくつかの簡単な手順で高いパフォーマンスを提供する点に重点を置いて行っています。 次の手順では、ボトルネックが発生した VPN サーバーをバイパスするいくつかの定義済みエンドポイントの従来の VPN アプローチを調整します。 同等、あるいはより優れたセキュリティ モデルを異なるレイヤに適用することで、企業ネットワークの出口ですべてのトラフィックを保護する必要がなくなります。 ほとんどの場合、これは数時間で効果的に達成され、要件の需要と時間が可能な限り他のワークロードに対して拡張可能です。

## <a name="implement-vpn-split-tunneling"></a>スプリット トンネル VPN の実装

この記事では、VPN クライアント アーキテクチャを _VPN_ 強制トンネルから VPN 強制トンネルに移行するために必要な簡単な手順について説明します。ただし、Microsoft 365 の共通 [VPN](microsoft-365-vpn-common-scenarios.md) 分割トンネリング シナリオでは、いくつかの信頼できる例外を除き、VPN スプリット トンネル モデル [#2](microsoft-365-vpn-common-scenarios.md#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) を使用します。

次の図は、推奨している VPN スプリット トンネリング ソリューションのしくみを示しています。

![スプリット トンネル VPN ソリューションの詳細。](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. 最適化するエンドポイントを決める

[URL Microsoft 365 [IP](urls-and-ip-address-ranges.md) アドレス範囲] の記事では、最適化に必要な主要なエンドポイントを明確に特定し、それらを最適化として分類 **します**。 現在、最適化する必要がある URL は 4 つ、IP サブネットは 20 個です。 この小規模なエンドポイント グループは、Microsoft 365 サービスへのトラフィック量の約 70% から 80% を占め、Teams メディア向けエンドポイントなどの遅延に敏感なエンドポイントを含む。 基本的に、これは特別な管理が必要なトラフィックであり、従来のネットワーク パスや VPN インフラストラクチャに大なるプレッシャーをかかえるトラフィックです。

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
| Teams のメディア IP (URL なし) | UDP 3478、3479、3480、および3481 | リレー探索の割り当てとリアルタイム トラフィック。 これらは、メディア トラフィック (通話、会議などSkype for BusinessおよびMicrosoft Teamsに使用されるエンドポイントです。 ほとんどのエンドポイントは、Microsoft Teams クライアントが発信を確立するときに提供されます(サービスのリストにある必要な IP 内に含まれています)。 メディアの品質を最適化するには、UDP プロトコルを使用する必要があります。   |

上記の例では、**テナント** をテナント名Microsoft 365する必要があります。 たとえば **、contoso.onmicrosoft.com と** _contoso.sharepoint.com を_ _contoso-my.sharepoint.com。_

#### <a name="optimize-ip-address-ranges"></a>IP アドレスの範囲を最適化する

これらのエンドポイントが対応する IP アドレス範囲を記述する時点では、次のようになります。 この例、[Microsoft 365 IP および URL Web](microsoft-365-ip-web-service.md) サービス、[URL/IP](urls-and-ip-address-ranges.md) ページなどのスクリプトを使用して、構成を適用する際に更新プログラムを確認し、定期的にポリシーを設定してください。[](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category)

```markdown
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

[最適化] カテゴリ内のすべての現在の IP アドレス範囲のルートを追加するには、次のスクリプト バリエーションを使用して[、Microsoft 365 IP と URL Web](microsoft-365-ip-web-service.md) サービスに対して現在の一連の最適化 IP サブネットを照会し、ルート テーブルに追加できます。

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

VPN クライアントの設定を行い、**最適化** IP へのトラフィックがこの方法でルーティングされるようにしてください。 これにより、トラフィックは、Microsoft 365 サービスや接続エンドポイントをユーザーに可能な限り近く提供する [Azure Front Door](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) などの Microsoft 365 Service Front Door などのローカル Microsoft リソースを利用できます。 これにより、世界中のユーザーに高いパフォーマンス レベルを提供し、 [Microsoft](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) の世界クラスのグローバル ネットワークをフルに活用できます。これは、ユーザーの直接出力から数ミリ秒以内である可能性があります。

## <a name="howto-guides-for-common-vpn-platforms"></a>一般 VPN プラットフォームのHOWTO ガイド

このセクションでは、この領域で最も一般的なパートナーからのトラフィックをMicrosoft 365トンネリングを実装するための詳細なガイドへのリンクを提供します。 ガイドは利用可能になり次第、追加する予定です。

- **Windows 10 VPN クライアント**: ネイティブ Microsoft 365 VPN クライアントを使用したリモート ワーカーのトラフィックWindows 10 [最適化](/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco Anyconnect**：[ Anyconnect スプリット トンネリングを Office365 向けに最適化する](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect**: VPN スプリット 経由Microsoft 365 [トラフィックの最適化Tunnelアクセス ルートを除外する](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 Networks BIG-IP APM**: [BIG-IP APM](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365) を使用Microsoft 365 VPN を介したリモート アクセスでのトラフィックの最適化
- **Citrix Gateway**: [Office365 向けのCitrix Gateway VPN スプリット トンネルの最適化](https://docs.citrix.com/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse Secure**: [VPN トンネリング: スプリット](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417) トンネリングを構成して、アプリケーションからMicrosoft 365する方法
- **Check Point VPN**: [Split Tunnelおよび他Microsoft 365 SaaS アプリケーションを構成する方法](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="related-articles"></a>関連記事

[概要: VPN スプリット トンネリング (Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[VPN スプリット トンネリングの一般的なシナリオ (Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[VPN スプリット トンTeamsメディア トラフィックのセキュリティ保護](microsoft-365-vpn-securing-teams.md)

[VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365のパフォーマンスの最適化](microsoft-365-networking-china.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365とパフォーマンスの調整](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
