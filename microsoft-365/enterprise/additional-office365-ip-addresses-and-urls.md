---
title: Office 365 IP Address と URL Web サービスに含まれない、その他のエンドポイント
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/15/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: '概要: 新しいエンドポイント Web サービスには、特定のシナリオに対していくつかのエンドポイントが含まれていません。'
hideEdit: true
ms.openlocfilehash: 0d8980840e75bc08c8414bcfa5c99baf8a5cacd0
ms.sourcegitcommit: e6595be36bbaba244439bd59dbae935e2b258ded
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2022
ms.locfileid: "67449988"
---
# <a name="other-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Office 365 IP Address と URL Web サービスに含まれない、その他のエンドポイント

一部のネットワーク エンドポイントは以前に公開されており、[Office 365 IP アドレスと URL Web サービス](microsoft-365-ip-web-service.md)には含まれていませんでした。 Web サービスは、エンタープライズ境界ネットワーク間のOffice 365接続に必要なネットワーク エンドポイントを公開します。 現在、このスコープには次のものが含まれていません。

1. Microsoft データ センターからお客様のネットワーク (ハイブリッド サーバーの着信ネットワーク トラフィック) への必要なネットワーク接続。
2. 組織のネットワーク境界上 (送信サーバーのネットワーク トラフィック) のお客様のネットワーク上のサーバーからのネットワーク接続。
3. ユーザーが設定する、ネットワーク接続要件に関する特殊なシナリオ。
4. DNS 解決の接続要件 (下記の一覧には含まれていません)。
5. Internet Explorer または Microsoft Edge の信頼済みサイト。

DNS とは別に、これらのインスタンスは、説明されている特定のシナリオが必要でない限り、ほとんどのお客様にとって省略可能です。

<br>

****

|行|用途|Destination (転送先)|型|
|---|---|---|---|
|1|**PST とファイル インジェスト用の [インポート サービス](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6)**|その他の要件については、 [Import Service](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) を参照してください。|特殊な送信シナリオ|
|2|**[Office 365 用の Microsoft サポート/回復アシスタント](https://diagnostics.office.com/#/)**|`https://autodiscover.outlook.com` <br> <https://officecdn.microsoft.com> <br> <https://api.diagnostics.office.com> <br> `https://apibasic.diagnostics.office.com` <br> <https://autodiscover-s.outlook.com> <br> `https://cloudcheckenabler.azurewebsites.net` <br> <https://login.live.com> <br> <https://login.microsoftonline.com> <br> <https://login.windows.net> <br> <https://o365diagtelemetry.trafficmanager.net> <br> <https://odc.officeapps.live.com> <br> <https://offcatedge.azureedge.net> <br> <https://officeapps.live.com> <br> <https://outlook.office365.com> <br> <https://outlookdiagnostics.azureedge.net>|送信サーバー トラフィック|
|3|**Azure AD Connect (SSO オプション付き)** <p> WinRM &リモート PowerShell|顧客の STS 環境 (AD FS サーバーおよび AD FS プロキシ) \| TCP ポート 80 と 443|受信サーバー トラフィック|
|4|AD FS プロキシ サーバーなどの **STS** (フェデレーションのお客様のみ)|顧客の STS (AD FS プロキシなど)\|ポート TCP 443 または TCP 49443 (ClientTLS使用)|受信サーバー トラフィック|
|5|**[Exchange Online ユニファイド メッセージング/SBC 統合](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers)**|オンプレミス セッション ボーダー コントローラーと \*.um.outlook.com 間の双方向|送信サーバー専用トラフィック|
|6|**メールボックスの移行**<p>メールボックスの移行がオンプレミス[の Exchange ハイブリッド](/exchange/exchange-deployment-assistant)からOffice 365に開始されると、Office 365は公開されている Exchange Web サービス (EWS)/メールボックス レプリケーション サービス (MRS) サーバーに接続します。 特定のソース IP 範囲からの受信接続のみを許可する必要がある場合は、OFFICE 365 URL & IP 範囲の **Exchange Online** テーブルに記載されている IP アドレスの [許可規則を作成します](urls-and-ip-address-ranges.md)。 <p> 発行された EWS エンドポイント (OWA など) への接続がブロックされないようにするには、接続を制限する前に、MRS プロキシが別の FQDN とパブリック IP アドレスに解決されていることを確認します。|顧客のオンプレミス EWS/MRS プロキシ <br> TCP ポート 443|受信サーバー トラフィック|
|7 |Free/Busy 共有などの **[Exchange ハイブリッド](/exchange/exchange-deployment-assistant)共存関数**。|顧客のオンプレミス Exchange サーバーのバージョン|受信サーバー トラフィック|
|8 |**[Exchange ハイブリッド](/exchange/exchange-deployment-assistant) プロキシ認証**|顧客のオンプレミス STS|受信サーバー トラフィック|
|9 |[Exchange ハイブリッド](/exchange/exchange-deployment-assistant)構成ウィザードを使用して **[Exchange ハイブリッドを構成](/exchange/hybrid-configuration-wizard)** するために使用します <p> 注: これらのエンドポイントは、Exchange ハイブリッドの構成にのみ必要です。|TCP ポート 80 と 443 の domains.live.com は、Exchange 2010 SP3 ハイブリッド構成ウィザードでのみ必要です <p> GCC High、DoD IP アドレス: 40.118.209.192/32、168.62.190.41/32 <p> Worldwide Commercial & GCC: \*.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net; <br> aka.ms/hybridwizard; <br> \*shcwreleaseprod.blob.core.windows.net/shcw/;|送信サーバー専用トラフィック|
|10|**AutoDetect サービス** は、[Outlook for iOS および Android を使用したハイブリッド モダン認証を使用](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)する [Exchange ハイブリッド](/exchange/exchange-deployment-assistant) シナリオで使用されます。 <p> `<email_domain>.outlookmobile.com` <br> `<email_domain>.outlookmobile.us` <br> `52.125.128.0/20` <br> `52.127.96.0/23`|顧客の TCP 443 のオンプレミス Exchange サーバー|受信サーバー トラフィック|
|11|**Exchange ハイブリッド Azure AD 認証**|*.msappproxy.net|TCP 送信サーバー専用トラフィック|
|12 |Office 2016 のSkype for Businessには、UDP ポートを使用する **ビデオ ベースの画面共有** が含まれています。 Office 2013 以前のSkype for Business クライアントでは、以前は TCP ポート 443 経由で RDP を使用しました。|TCP ポート 443 が 52.112.0.0/14 に開きます|Office 2013 以前の Skype for Business の古いクライアント バージョン|
|13|Skype for Business Online への **ハイブリッド オンプレミス サーバー接続** をSkype for Businessする|13.107.64.0/18, 52.112.0.0/14 <br> UDP ポート 50,000-59,999 <br> TCP ポート 50,000-59,999; 5061|Skype for Business オンプレミス サーバーの送信接続性|
|14|オンプレミスハイブリッド接続を備えた **クラウド PSTN** では、オンプレミス ホストに対して開かれたネットワーク接続が必要です。 Skype for Business Online ハイブリッド構成の詳細については、|「[Skype for Business Server と Office 365 間のハイブリッド接続を計画する](/skypeforbusiness/hybrid/plan-hybrid-connectivity)」を参照してください。|Skype for Business オンプレミス ハイブリッド受信|
|15|**認証と ID FQDN** <p> FQDN (`secure.aadcdn.microsoftonline-p.com`) を機能させるには、クライアントの Internet Explorer (IE) またはエッジの信頼済みサイト ゾーンに含める必要があります。||信頼済みサイト|
|16|**Microsoft Teams FQDN** <p> Internet Explorer または Microsoft Edge を使用している場合は、最初にサード パーティの cookie を有効にし、信頼済みサイトに (スイート製品全体の FQDN、CDN、および 14 行目に記載されているテレメトリに加え) Teams の FQDN を追加する必要があります。詳細については、「[Microsoft Teams の既知の問題](/microsoftteams/known-issues)」を参照してください。||信頼済みサイト|
|17 |**Sharepoint Online と OneDrive for Business FQDN** <p> 「\<tenant\>」が入ったすべての FQDN (「.sharepoint.com」) を機能させるには、クライアントの IE または Edge の信頼済みサイト ゾーンに含める必要があります。スイート製品全体の FQDN、CDN、および 14 行目に記載されているテレメトリに加えて、これらのエンドポイントも追加する必要があります。||信頼済みサイト|
|18 |**Yammer**  <br> Yammer はブラウザーでのみ利用でき、認証されたユーザーはプロキシを経由する必要があります。Yammer のすべての FQDN をさせるには、クライアントの IE またはエッジの信頼済みサイト ゾーンに含める必要があります。||信頼済みサイト|
|19|**[Azure AD Connect](/azure/active-directory/hybrid/)** を使用して、オンプレミスのユーザー アカウントを Azure AD に同期します。|詳細については、「[ハイブリッド ID で必要なポートとプロトコル](/azure/active-directory/hybrid/reference-connect-ports)」、「[Azure AD の接続のトラブルシューティング](/azure/active-directory/hybrid/tshoot-connect-connectivity)」、および「[Azure AD Connect Health エージェントのインストール](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints)」を参照してください。|送信サーバー専用トラフィック|
|20|**[中国で Azure AD Connect](/azure/active-directory/hybrid/)** と 21 ViaNet を使用して、オンプレミスのユーザー アカウントを Azure AD に同期します。|\*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <br> secure.aadcdn.partner.microsoftonline-p.cn:443 <br> \*.partner.microsoftonline.cn:443 <p> 「[Azure AD の接続に関する問題のトラブルシューティング](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity)」も参照してください。|送信サーバー専用トラフィック|
| 21|**Microsoft Stream** (Azure AD ユーザー トークンが必要)。 <br> Office 365 ワールドワイド (GCC を含む)|\*.cloudapp.net <br> \*.api.microsoftstream.com <br> \*.notification.api.microsoftstream.com <br> amp.azure.net <br> api.microsoftstream.com <br> az416426.vo.msecnd.net <br> s0.assets-yammer.com <br> vortex.data.microsoft.com <br> web.microsoftstream.com <br> TCP ポート 443|受信サーバー トラフィック|
|22|多要素認証要求には **MFA サーバー** を使用します。これは、サーバーの新しいインストールと、Active Directory Domain Services (AD DS) での設定の両方です。|[Azure AD 多要素認証サーバーの概要に関する](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)ページを参照してください。|送信サーバー専用トラフィック|
|23|**Microsoft Graph 変更通知** <p> 開発者は [、変更通知](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0&preserve-view=true) を使用して、Microsoft Graph のイベントをサブスクライブできます。|Public Cloud: 52.159.23.209, 52.159.17.84, 52.147.213.251, 52.147.213.181, 13.85.192.59, 13.85.192.123, 20.9.36.45, 20.9.35.166, 20.96.21.67, 20.69.245.215, 137.135.11.161, 137.135.11.116, 52.159.107.50, 52.159.107.4, 52.229.38.131, 52.183.67.212, 52.142.114.29, 52.142.115.31, 51.124.75.43, 51.124.73.177, 20.44.210.83, 20.44.210.146, 40.80.232.177, 40.80.232.118, 20.48.12.75, 20.48.11.201, 104.215.13.23, 104.215.6.169, 52.148.24.136, 52.148.27.39, 40.76.162.99, 40.76.162.42,40.74.203.28, 40.74.203.27, 13.86.37.15, 52.154.246.238, 20.96.21.98, 20.96.21.115, 137.135.11.222, 137.135.11.250, 52.159.109.205, 52.159.102.72, 52.151.30.78, 52.191.173.85, 51.104.159.213, 51.104.159.181, 51.138.90.7, 51.138.90.52, 52.148.115.48, 52.148.114.238, 40.80.233.14, 40.80.239.196, 20.48.14.35, 20.48.15.147, 104.215.18.55, 104.215.12.254, 20.199.102.157, 20.199.102.73, 13.87.81.123, 13.87.81.35, 20.111.9.46, 20.111.9.77, 13.87.81.133, 13.87.81.141 <p> Microsoft Cloud for US Government: 52.244.33.45、52.244.35.174、52.243.157.104、 52.243.157.105、52.182.25.254、52.182.25.110、52.181.25.67、52.181.25.66、 52.244.111.156、52.244.111.170、52.243.147.249、52.243.148.1 9、52.182.32.51、52.182.32.143、52.181.24.199、52.181.24.220 <p> 21Vianet によって運用される Microsoft Cloud China: 42.159.72.35、42.159.72.47、 42.159.180.55、42.159.180.56、40.125.138.23、40.125.136.69、40.72.155.199、40.72.155.216 <br> TCP ポート 443 <p> 注: 開発者は、サブスクリプションの作成時にさまざまなポートを指定できます。|受信サーバー トラフィック|
|24|**ネットワーク接続状態インジケーター**<p>コンピューターがインターネットに接続されているかどうかを判断するためにWindows 10と 11 によって使用されます (Windows 以外のクライアントには適用されません)。 この URL に到達できない場合、Windows はインターネットに接続されていないと想定し、M365 Apps for Enterprise はアクティブ化の状態を確認しようとせず、Exchange やその他のサービスへの接続が失敗します。|www.msftconnecttest.com <br> 13.107.4.52<p>Windows 11 Enterprise[の接続エンドポイントの管理と、Windows 10 Enterprise](/windows/privacy/manage-windows-11-endpoints)[バージョン 21H2 の接続エンドポイントの管理](/windows/privacy/manage-windows-21h2-endpoints)に関するページも参照してください。|送信サーバー専用トラフィック|
|25|**モバイル デバイスでの Teams の通知**<p>Android および Apple モバイル デバイスで、着信通話やその他の Teams サービスのプッシュ通知を Teams クライアントに受信するために使用されます。 これらのポートがブロックされると、モバイル デバイスへのプッシュ通知はすべて失敗します。|特定のポートについては、 [Google Firebase のドキュメントの FCM ポートとファイアウォール](https://firebase.google.com/docs/cloud-messaging/concept-options#messaging-ports-and-your-firewall) と [Apple デバイスに Apple プッシュ通知が届いていない場合](https://support.apple.com/en-us/HT203609)に関するページを参照してください。|送信サーバー専用トラフィック|

## <a name="related-topics"></a>関連項目

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)
  
[Microsoft 365 の接続を監視する](./monitor-connectivity.md)
  
[クライアント接続](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[コンテンツ配信ネットワーク](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Azure IP 範囲とサービス タグ – パブリック クラウド](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP 範囲とサービス タグ – 米国政府機関クラウド](https://www.microsoft.com/download/details.aspx?id=57063)

[Azure IP 範囲とサービス タグ – Germany Cloud](https://www.microsoft.com/download/details.aspx?id=57064)

[Azure IP 範囲とサービス タグ – China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft パブリック IP スペース](https://www.microsoft.com/download/details.aspx?id=53602)
