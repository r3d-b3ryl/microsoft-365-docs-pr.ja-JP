---
title: VPN スプリット トンTeamsメディア トラフィックのセキュリティ保護
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
description: VPN スプリット トンTeamsメディア トラフィックのセキュリティ保護
ms.openlocfilehash: 0f16ed8f7f9721a79375f05f7b889bc8aab2d824
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331024"
---
# <a name="securing-teams-media-traffic-for-vpn-split-tunneling"></a>VPN スプリット トンTeamsメディア トラフィックのセキュリティ保護

>[!NOTE]
>この記事は、リモート ユーザーの最適化に関するMicrosoft 365の一部です。

>- VPN スプリット トンネリングを使用してリモート ユーザー Microsoft 365接続を最適化する方法の概要については、「[Overview: VPN split tunneling for remoteing for remote」を参照](microsoft-365-vpn-split-tunnel.md)Microsoft 365。
>- VPN スプリット トンネリングの実装に関する詳細なガイダンスについては、「VPN スプリット トンネリングの実装」を参照[Microsoft 365。](microsoft-365-vpn-implement-split-tunnel.md)
>- VPN スプリット トンネリングのシナリオの詳細な一覧については、「VPN スプリット トンネリングの一般的なシナリオ」を参照[Microsoft 365。](microsoft-365-vpn-common-scenarios.md)
>- VPN 環境で Stream イベントとライブ イベントを構成する方法については、「VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項」 [を参照してください](microsoft-365-vpn-stream-and-live-events.md)。
>- 中国のユーザーに対するMicrosoft 365のパフォーマンスの最適化の詳細については、「中国のユーザー Microsoft 365[パフォーマンスの最適化」を参照してください](microsoft-365-networking-china.md)。

一部Microsoft Teams管理者は、スプリット トンネリング モデルを使用して、Teamsフローがどのように動作し、接続がセキュリティで保護されるのかについて詳細な情報を必要とする場合があります。

## <a name="configuration"></a>構成

通話と会議の両方で、Teams メディアに対して必要なオプティマイズ IP サブネットが正しく配置されている限り、Teams が [GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) 関数を呼び出して、特定の宛先に使用するルートに対応するローカル インターフェイスを特定すると、上記の Microsoft IP ブロックの Microsoft 宛先に対してローカル インターフェイスが返されます。

一部の VPN クライアント ソフトウェアでは、URL に基づいてルーティング操作が可能です。 ただし、Teams のメディア トラフィックには URL が関連付けられていないため、このトラフィックのルーティングの制御は IP サブネットを使用して行う必要があります。

特定の状況では、Teams クライアントの設定とは関係なく、メディア トラフィックは正しいルートが設定されていても VPN トンネルを通過します。 このシナリオが発生した場合は、ファイアウォール ルールを使用して、VPN を使用Teams IP サブネットまたはポートの使用をブロックすれば十分です。

>[!IMPORTANT]
>すべての VPN シナリオTeams方法を使用してメディア トラフィックを確実にルーティングするには、ユーザーが Microsoft Teams クライアント バージョン **1.3.00.13565** 以上を実行している必要があります。 このバージョンには、クライアントが使用可能なネットワーク パスを検出する方法の改善が含まれています。

シグナリング トラフィックは HTTPS 経由で実行され、メディア トラフィックほど遅延に敏感ではなく、URL/IP データで許可としてマークされ、必要に応じて VPN クライアントを介して安全にルーティングできます。

>[!NOTE]
>Microsoft Edge **96 以上では**、ピアツーピア トラフィックの VPN スプリット トンネリングもサポートしています。 つまり、たとえば、エッジ上の Web クライアントに対して VPN Teamsトンネリングを利用できます。 Edge で実行されている Web サイト用に設定する場合は、 [Edge WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) ポリシーを有効にする追加の手順を実行します。

### <a name="security"></a>セキュリティ

スプリット トンネルを回避するための一般的な引数の 1 つは、セキュリティが低い、つまり VPN トンネルを通過しないトラフィックは、VPN トンネルに適用される暗号化方式の恩恵を受け、セキュリティが低い。

これに対する主な反論は、機密性、認証、および RTP トラフィックに対する再生攻撃の保護を提供するリアルタイム転送プロトコル (RTP) のプロファイルである「_Secure Real-Time Transport Protocol (SRTP)_」によってメディアのトラフィックがすでに暗号化されていることです。  SRTP 自体は、ランダムに生成されたセッションキーに依存します。これは、TLS で保護された出力チャネルを介して交換されます。 これについては、[セキュリティガイド](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)で詳しく説明していますが、重要な部分はメディアの暗号化です。

メディア トラフィックは SRTP を使用して暗号化されます。SRTP は、セキュリティ保護された乱数ジェネレータによって生成され、シグナル出力 TLS チャネルで交換されるセッションキーを使用します。 さらに、仲介サーバーとその内部の次ホップの間で双方向に流れるメディアも、SRTP を使用して暗号化されます。

Skype for Business Online は、_Traversal Using Relay around NAT (TURN)_ を介したメディア リレーへの安全なアクセスのためのユーザー名/パスワードを生成します。 メディア リレーは、TLS で保護された SIP チャネル上でユーザー名/パスワードを交換します。 VPN トンネルを使用してクライアントを企業ネットワークに接続する場合でも、サービスに到達するために企業ネットワークを離れる場合、トラフィックは引き続き SRTP 形式でフローする必要があります。

Teams が NAT _(STUN)_ 増幅攻撃の音声やセッション トラバーサル ユーティリティなどの一般的なセキュリティ上の懸念を軽減する方法については、「[5.1 Security Considerations for Implementers](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)」を参照してください。

リモートワーク環境での最新のセキュリティ管理については、「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」を参照してください。

### <a name="testing"></a>テスト

ポリシーが適用された後、期待通り動作しているのを確認する必要があります。 ローカル インターネット接続を使用するようにパスが正しく設定されているかどうかテストするには、いくつかの方法があります。

- トレース ルート[Microsoft 365含](https://aka.ms/netonboard)めて、接続テストを実行する接続テストを実行します。 また、このツールに VPN テストを追加し、さらに分析情報を提供する必要があります。

- 分割トンネル **のスコープ内** のエンドポイントへの単純な tracert には、次に示すパスが表示されます。

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  その後、ローカル ISP を経由してこのエンドポイントへのパスが表示され、スプリット トンネリング用に構成した Teams範囲の IP に解決する必要があります。

- Wireshark などのツールを使用してネットワーク キャプチャを取得します。  発信中に UDP でフィルタリングすると、 Teams の「**最適化**」範囲の IP アドレスに流れるトラフィックが表示されます。 このトラフィックに VPN トンネルが使用されている場合、メディア トラフィックはトレースに表示されません。

## <a name="additional-support-logs"></a>追加のサポート ログ

トラブル シューティングのためにさらにデータが必要な場合、または Microsoft のサポートが必要な場合は、次の情報を集めておくと、解決策を迅速に見つけることができます。 Microsoft サポートの **TSS Windows CMD ベースのユニバーサル TroubleShooting スクリプト** ツールセットを使用すると、関連するログを簡単に収集できます。 使用に関するツールと手順については、次のページをご覧ください <https://aka.ms/TssTools>。

## <a name="related-articles"></a>関連記事

[概要: VPN スプリット トンネリング (Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[VPN スプリット トンネリングを実装するMicrosoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[VPN スプリット トンネリングの一般的なシナリオ (Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365のパフォーマンスの最適化](microsoft-365-networking-china.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365とパフォーマンスの調整](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
