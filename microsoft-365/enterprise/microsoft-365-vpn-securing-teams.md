---
title: VPN 分割トンネリングのための Teams メディア トラフィックのセキュリティ保護
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
description: VPN 分割トンネリングのための Teams メディア トラフィックのセキュリティ保護
ms.openlocfilehash: 715d5e02ef01db9ef1c75a063ef5a2771d425f5c
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64715387"
---
# <a name="securing-teams-media-traffic-for-vpn-split-tunneling"></a>VPN 分割トンネリングのための Teams メディア トラフィックのセキュリティ保護

>[!NOTE]
>この記事は、リモート ユーザーの最適化Microsoft 365対処する一連の記事の一部です。

>- VPN 分割トンネリングを使用してリモート ユーザーのMicrosoft 365接続を最適化する方法の概要については、「[概要: Microsoft 365の VPN 分割トンネリング」を](microsoft-365-vpn-split-tunnel.md)参照してください。
>- VPN 分割トンネリングの実装に関する詳細なガイダンスについては、「[Microsoft 365用の VPN 分割トンネリングの実装」を](microsoft-365-vpn-implement-split-tunnel.md)参照してください。
>- VPN 分割トンネリングのシナリオの詳細な一覧については、「[Microsoft 365の一般的な VPN 分割トンネリング シナリオ」を](microsoft-365-vpn-common-scenarios.md)参照してください。
>- VPN 環境で Stream イベントとライブ イベントを構成する方法については、「VPN 環境での [Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)」を参照してください。
>- 中国のユーザーに対Microsoft 365世界規模のテナント パフォーマンスを最適化する方法については、「中国ユーザー[のパフォーマンスの最適化Microsoft 365」を参照してください](microsoft-365-networking-china.md)。

一部のMicrosoft Teams管理者は、分割トンネリング モデルを使用したTeamsでの通話フローの動作と接続のセキュリティ保護方法に関する詳細な情報を必要とする場合があります。

## <a name="configuration"></a>構成

呼び出しと会議の両方で、必要な Teams メディア用のオプティマイズ IP サブネットがルート テーブルに正しく配置されている限り、Teamsが [GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) 関数を呼び出して、特定の宛先に使用する必要があるルートに対応するローカル インターフェイスを判断すると、上記の Microsoft IP ブロックの Microsoft 宛先に対してローカル インターフェイスが返されます。

一部の VPN クライアント ソフトウェアでは、URL に基づいてルーティング操作が可能です。 ただし、Teams のメディア トラフィックには URL が関連付けられていないため、このトラフィックのルーティングの制御は IP サブネットを使用して行う必要があります。

特定の状況では、Teams クライアントの設定とは関係なく、メディア トラフィックは正しいルートが設定されていても VPN トンネルを通過します。 このシナリオが発生した場合は、ファイアウォール規則を使用して、Teams IP サブネットまたはポートで VPN を使用できないようにすれば十分です。

>[!IMPORTANT]
>Teamsメディア トラフィックがすべての VPN シナリオで目的の方法でルーティングされるようにするには、ユーザーがクライアント バージョン **1.3.00.13565** 以降Microsoft Teams実行していることを確認してください。 このバージョンには、クライアントが使用可能なネットワーク パスを検出する方法の機能強化が含まれています。

シグナリング トラフィックは HTTPS 経由で実行され、メディア トラフィックほど待ち時間に依存せず、URL/IP データで **許可** としてマークされるため、必要に応じて VPN クライアント経由で安全にルーティングできます。

>[!NOTE]
>Microsoft Edge **96 以降では、** ピアツーピア トラフィックの VPN 分割トンネリングもサポートされています。 つまり、たとえば、顧客はエッジ上の web クライアントTeams VPN 分割トンネリングの利点を得ることができます。 Edge で実行されている Web サイト用に設定する必要があるお客様は、Edge [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) ポリシーを無効にする追加の手順を実行することで、それを実現できます。

### <a name="security"></a>セキュリティ

分割トンネルを回避するための一般的な引数の 1 つは、これを行う安全性が低い、つまり VPN トンネルを経由しないトラフィックは、VPN トンネルに適用される暗号化スキームのメリットを得られないため、安全性が低くなります。

これに対する主な反論は、機密性、認証、および RTP トラフィックに対する再生攻撃の保護を提供するリアルタイム転送プロトコル (RTP) のプロファイルである「_Secure Real-Time Transport Protocol (SRTP)_」によってメディアのトラフィックがすでに暗号化されていることです。  SRTP 自体は、ランダムに生成されたセッションキーに依存します。これは、TLS で保護された出力チャネルを介して交換されます。 これについては、[セキュリティガイド](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)で詳しく説明していますが、重要な部分はメディアの暗号化です。

メディア トラフィックは SRTP を使用して暗号化されます。SRTP は、セキュリティ保護された乱数ジェネレータによって生成され、シグナル出力 TLS チャネルで交換されるセッションキーを使用します。 さらに、仲介サーバーとその内部の次ホップの間で双方向に流れるメディアも、SRTP を使用して暗号化されます。

Skype for Business Online は、_Traversal Using Relay around NAT (TURN)_ を介したメディア リレーへの安全なアクセスのためのユーザー名/パスワードを生成します。 メディア リレーは、TLS で保護された SIP チャネル上でユーザー名/パスワードを交換します。 VPN トンネルを使用してクライアントを企業ネットワークに接続する場合でも、サービスに到達するために企業ネットワークから出るときにトラフィックは SRTP 形式でフローする必要があることに注意してください。

_NAT (STUN) 増幅攻撃に対する音声またはセッション トラバーサル ユーティリティ_ などの一般的なセキュリティ上の懸念を軽減Teams方法については、[実装者のセキュリティに関する 5.1 の考慮事項を参照](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)してください。

リモートワーク環境での最新のセキュリティ管理については、「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」を参照してください。

### <a name="testing"></a>テスト

ポリシーが設定されたら、それが期待どおりに機能していることを確認する必要があります。 ローカル インターネット接続を使用するようにパスが正しく設定されているかどうかテストするには、いくつかの方法があります。

- 上記のようなトレース ルートを含め、接続テストを実行するMicrosoft 365接続[テスト](https://aka.ms/netonboard)を実行します。 また、追加の分析情報を提供する必要がある VPN テストもこのツールに追加しています。

- 分割トンネルのスコープ内のエンドポイントへの単純な **トレース** は、次のようにパスを示す必要があります。

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  次に、ローカル ISP 経由でこのエンドポイントへのパスが表示されます。このパスは、分割トンネリング用に構成したTeams範囲の IP に解決する必要があります。

- Wireshark などのツールを使用してネットワーク キャプチャを取得します。  発信中に UDP でフィルタリングすると、 Teams の「**最適化**」範囲の IP アドレスに流れるトラフィックが表示されます。 このトラフィックに VPN トンネルが使用されている場合、メディア トラフィックはトレースに表示されません。

## <a name="additional-support-logs"></a>追加のサポート ログ

トラブル シューティングのためにさらにデータが必要な場合、または Microsoft のサポートが必要な場合は、次の情報を集めておくと、解決策を迅速に見つけることができます。 Microsoft サポートの **TSS Windows CMD ベースのユニバーサル TroubleShooting スクリプト ツールセット** は、関連するログを簡単な方法で収集するのに役立ちます。 使用に関するツールと手順については、次の場所を <https://aka.ms/TssTools>参照してください。

## <a name="related-articles"></a>関連記事

[概要: Microsoft 365の VPN 分割トンネリング](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365用の VPN 分割トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365の一般的な VPN 分割トンネリング シナリオ](microsoft-365-vpn-common-scenarios.md)

[VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)

[中国ユーザーのMicrosoft 365パフォーマンスの最適化](microsoft-365-networking-china.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365ネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
