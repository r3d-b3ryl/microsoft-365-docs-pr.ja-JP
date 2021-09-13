---
title: ネットワーク保護を使用して、悪いサイトへの接続を防止する
description: ユーザーが既知の悪意のあるネットワーク アドレスや疑わしいネットワーク アドレスにアクセスするのを防ぐことで、ネットワークを保護する
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、ドメイン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.openlocfilehash: 44f75b2912a8e54df6584a8f97d0f6e76cac6b15
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192710"
---
# <a name="protect-your-network"></a>ネットワークを保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="overview-of-network-protection"></a>ネットワーク保護の概要

ネットワーク保護は、インターネット ベースのイベントからデバイスを保護するのに役立ちます。 ネットワーク保護は、攻撃表面の縮小機能です。 これは、従業員がアプリケーションを通じて危険なドメインにアクセスするのを防ぐのに役立ちます。 インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストするドメインは危険と見なされます。 ネットワーク保護は[、Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)の範囲を拡張して、低評価ソース (ドメインまたはホスト名に基づく) への接続を試みるすべての送信 HTTP トラフィックをブロックします。

ネットワーク保護は、Web 保護の保護 [をオペレーティング](web-protection-overview.md) システム レベルまで拡張します。 Edge の Web 保護機能は、サポートされている他のブラウザーやブラウザー以外のアプリケーションに提供されます。 さらに、ネットワーク保護は、エンドポイントの検出と応答で使用する場合に、侵害の指標 (IOC) の可視性とブロック [を提供します](overview-endpoint-detection-response.md)。 たとえば、ネットワーク保護は、特定のドメイン [または](manage-indicators.md) ホスト名をブロックするために使用できるカスタムインジケーターと機能します。

> [!TIP]
> ネットワーク保護のしくみについては、「Microsoft Defender for [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Endpoint testground」の demo.wd.microsoft.com を参照してください。

## <a name="requirements-for-network-protection"></a>ネットワーク保護の要件

ネットワーク保護には、Windows 10 ProまたはEnterprise、リアルタイムMicrosoft Defender ウイルス対策保護が必要です。

<br>

****

|Windows バージョン|Microsoft Defender ウイルス対策|
|---|---|
|Windows 10バージョン 1709 以降 <p> Windowsサーバー 1803 以降|[Microsoft Defender ウイルス対策保護とクラウド](configure-real-time-protection-microsoft-defender-antivirus.md)[配信保護を有効](enable-cloud-protection-microsoft-defender-antivirus.md)にする必要があります|
|

サービスを有効にした後、サービスとデバイス (エンドポイントとも呼ばれます) 間の接続を許可するために、ネットワークまたはファイアウォールを構成する必要がある場合があります。

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="configuring-network-protection"></a>ネットワーク保護の構成

ネットワーク保護を有効にする方法の詳細については、「ネットワーク保護を有効 **[にする」を参照してください](enable-network-protection.md)**。 グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。

## <a name="viewing-network-protection-events"></a>ネットワーク保護イベントの表示

ネットワーク保護は [、Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)で最適に機能します。これにより、アラート調査シナリオの一環として、エクスプロイト保護イベントとブロックに関する詳細なレポート [が提供されます](investigate-alerts.md)。

ネットワーク保護が接続をブロックすると、アクション センターから通知が表示されます。 セキュリティ運用チームは、 [組織の詳細と](customize-attack-surface-reduction.md#customize-the-notification) 連絡先情報を使用して通知をカスタマイズできます。 さらに、個々の攻撃表面の縮小ルールを有効にし、監視する特定の手法に合わせてカスタマイズできます。

監査モードを使用 [して、](audit-windows-defender.md) ネットワーク保護が有効になっている場合に組織に与える影響を評価することもできます。

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>ポータルでネットワーク保護イベントをMicrosoft 365 Defenderする

Microsoft Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックに関する詳細 [なレポートを提供します](investigate-alerts.md)。 これらの詳細は、アラート キューの Microsoft 365 Defenderポータル ( ) または高度な検索 [https://security.microsoft.com](https://security.microsoft.com) を[使用して表示できます](advanced-hunting-overview.md)。 [](review-alerts.md) 監査モードを使用 [している場合](audit-windows-defender.md)は、高度な検索を使用して、ネットワーク保護設定が有効になっている場合に環境に与える影響を確認できます。

高度な検索のクエリの例を次に示します。

```kusto
DeviceEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>イベント ビューアーでネットワーク保護イベントWindows確認する

ネットワーク保護が悪意のある IP またはドメインWindowsアクセスをブロック (または監査) するときに作成されるイベントを確認するには、次のイベント ログを確認します。

1. [XML を直接コピーします](event-views.md)。

2. **[OK]** を選択します。

この手順では、ネットワーク保護に関連する次のイベントのみを表示するためにフィルター処理するカスタム ビューを作成します。

<br>

****

|イベント ID|説明|
|---|---|
|5007|設定が変更された場合のイベント|
|1125|監査モードでネットワーク保護が発生した場合のイベント|
|1126|ブロック モードでネットワーク保護が発生した場合のイベント|
|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>ネットワーク保護と TCP 3 ウェイ ハンドシェイク

ネットワーク保護では [、TCP/IP](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip)による 3 者間ハンドシェイクが完了した後で、サイトへのアクセスを許可またはブロックするかどうかを決定します。 したがって、サイトがネットワーク保護によってブロックされている場合、サイトが実際にブロックされている場合でも、Microsoft 365 Defender ポータルに under というアクションの種類が `ConnectionSuccess` `NetworkConnectionEvents` 表示される場合があります。 `NetworkConnectionEvents` は、ネットワーク保護ではなく TCP 層から報告されます。 3 ウェイ ハンドシェイクが完了すると、サイトへのアクセスがネットワーク保護によって許可またはブロックされます。

その動作の例を次に示します。

1. ユーザーがデバイス上の Web サイトにアクセスしようとしたとします。 サイトは危険なドメインでホストされ、ネットワーク保護によってブロックされる必要があります。  

2. TCP/IP による 3 ウェイ ハンドシェイクが開始されます。 完了する前に、アクション `NetworkConnectionEvents` がログに記録され、そのアクション `ActionType` がとして表示されます `ConnectionSuccess` 。 ただし、3 ウェイ ハンドシェイク プロセスが完了すると、ネットワーク保護によってサイトへのアクセスがブロックされます。 このすべてが非常に迅速に発生します。 同様のプロセスは[、Microsoft Defender SmartScreen。](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)3 者ハンドシェイクが完了すると、決定が完了し、サイトへのアクセスがブロックまたは許可されます。

3. このポータルMicrosoft 365 Defender、アラートがアラート キューに[一覧表示されます](alerts-queue.md)。 このアラートの詳細には、 と `NetworkConnectionEvents` の両方が含まれます `AlertEvents` 。 ActionType のアイテムがある場合でも、サイトがブロック `NetworkConnectionEvents` されているのを確認できます `ConnectionSuccess` 。

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>マルチ セッションをWindowsしている仮想デスクトップWindows 10 Enterpriseに関する考慮事項

マルチ ユーザーの性質上、Windows 10 Enterpriseに注意してください。

1. ネットワーク保護はデバイス全体の機能であり、特定のユーザー セッションを対象とすることはできません。

2. Web コンテンツ フィルター ポリシーもデバイス全体です。

3. ユーザー グループを区別する必要がある場合は、仮想デスクトップ ホスト プールと割り当てのWindows作成を検討してください。

4. 監査モードでネットワーク保護をテストし、展開する前に動作を評価します。

5. 多数のユーザーまたは多数のマルチユーザー セッションがある場合は、展開のサイズを変更してください。

### <a name="alternative-option-for-network-protection"></a>ネットワーク保護の代替オプション

Azure Windows 10 Enterprise Windows Virtual Desktop で使用されるマルチセッション 1909 以上の場合、Microsoft Edge のネットワーク保護は次の方法で有効にできます。

1. [ [ネットワーク保護を有効にする] を](enable-network-protection.md) 使用し、指示に従ってポリシーを適用します。

2. 次の PowerShell コマンドを実行します。 `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>ネットワーク保護のトラブルシューティング

ネットワーク保護が実行される環境のため、Microsoft はオペレーティング システムのプロキシ設定を検出できない場合があります。 場合によっては、ネットワーク保護クライアントがクラウド サービスにアクセスできない場合があります。 接続の問題を解決するには、E5 ライセンスをお持ちのお客様は、次のいずれかの Defender レジストリ キーを構成する必要があります。

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="see-also"></a>関連項目

- [ネットワーク保護の評価|](evaluate-network-protection.md) 機能の動作と、通常作成されるイベントを示す簡単なシナリオを実行します。
- [ネットワーク保護の有効化|](enable-network-protection.md) グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。
- [攻撃表面の縮小機能の構成Microsoft Intune](/mem/intune/protect/endpoint-security-asr-policy)
