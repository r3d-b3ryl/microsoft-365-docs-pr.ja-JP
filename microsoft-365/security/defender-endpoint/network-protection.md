---
title: ネットワーク保護を使用して、不正なサイトへの接続を防止する
description: ユーザーが既知の悪意のある不審なネットワーク アドレスにアクセスできないようにしてネットワークを保護する
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、ドメイン
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: ''
ms.openlocfilehash: f58c7afe9c6f532f7f6420d58bcd681778483680
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789340"
---
# <a name="protect-your-network"></a>ネットワークを保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="overview-of-network-protection"></a>ネットワーク保護の概要

ネットワーク保護は、インターネット ベースのイベントからデバイスを保護するのに役立ちます。 ネットワーク保護は、攻撃面の縮小機能です。 これにより、従業員がアプリケーションを介して危険なドメインにアクセスするのを防ぐことができます。 インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストするドメインは危険と見なされます。 ネットワーク保護は[、(](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)ドメインまたはホスト名に基づいて) 低評価ソースに接続しようとするすべての送信 HTTP トラフィックをブロックするために、Microsoft Defender SmartScreenの範囲を拡張します。

ネットワーク保護は、 [Web 保護](web-protection-overview.md) の保護をオペレーティング システム レベルに拡張します。 サポートされている他のブラウザーやブラウザー以外のアプリケーションに対して、Edge の Web 保護機能を提供します。 さらに、ネットワーク保護は、 [エンドポイントの検出と応答](overview-endpoint-detection-response.md)と共に使用する場合に、侵害のインジケーター (IOC) の可視性とブロックを提供します。 たとえば、ネットワーク保護は、特定のドメインまたはホスト名をブロックするために使用できる [カスタム インジケーター](manage-indicators.md) と連携します。

> [!TIP]
> ネットワーク保護のしくみについては、[demo.wd.microsoft.com のMicrosoft Defender for Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)のテストグラウンド サイトを参照してください。

> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

## <a name="requirements-for-network-protection"></a>ネットワーク保護の要件

ネットワーク保護には、Windows 10 ProまたはEnterpriseとリアルタイム保護Microsoft Defender ウイルス対策必要があります。

<br>

****

|Windows バージョン|Microsoft Defender ウイルス対策|
|---|---|
|Windows 10 バージョン 1709 以降 <p> Windows 11 <p> Windows Server 1803 以降|[リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md)と[クラウド配信](enable-cloud-protection-microsoft-defender-antivirus.md)保護Microsoft Defender ウイルス対策有効にする必要がある|
|

サービスを有効にした後、サービスとデバイス (エンドポイントとも呼ばれます) 間の接続を許可するようにネットワークまたはファイアウォールを構成することが必要になる場合があります。

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="configuring-network-protection"></a>ネットワーク保護の構成

ネットワーク保護を有効にする方法の詳細については、「ネットワーク保護を **[有効にする」を](enable-network-protection.md)** 参照してください。 グループ ポリシー、PowerShell、または MDM CSP を使用して、ネットワーク内のネットワーク保護を有効および管理します。

## <a name="viewing-network-protection-events"></a>ネットワーク保護イベントの表示

ネットワーク保護は[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)で最適に機能します。これにより、[アラート調査シナリオ](investigate-alerts.md)の一環として、エクスプロイト保護イベントとブロックに関する詳細なレポートが提供されます。

ネットワーク保護によって接続がブロックされると、アクション センターから通知が表示されます。 セキュリティ運用チームは、組織 [の](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) 詳細と連絡先情報を使用して通知をカスタマイズできます。 さらに、監視する特定の手法に合わせて、個々の攻撃面縮小ルールを有効にしたりカスタマイズしたりできます。

[また、監査モード](audit-windows-defender.md)を使用して、ネットワーク保護が有効になっている場合に組織にどのような影響を与えるかを評価することもできます。

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでネットワーク保護イベントを確認する

Microsoft Defender for Endpointは、[アラート調査シナリオ](investigate-alerts.md)の一環として、イベントとブロックに関する詳細なレポートを提供します。 これらの詳細は、[アラート キュー](review-alerts.md)のMicrosoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で表示することも、[高度な捜索](advanced-hunting-overview.md)を使用して表示することもできます。 [監査モード](audit-windows-defender.md)を使用している場合は、高度なハンティングを使用して、ネットワーク保護設定が有効になっている場合に環境にどのような影響を与えるかを確認できます。

高度なハンティングのクエリの例を次に示します。

```kusto
DeviceNetworkEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked', 'ConnectionSuccess')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Windows イベント ビューアーでネットワーク保護イベントを確認する

Windows イベント ログを確認して、ネットワーク保護が悪意のある IP またはドメインへのアクセスをブロック (または監査) したときに作成されたイベントを確認できます。

1. [XML を直接コピーします](event-views.md)。

2. [**OK**] を選択します。

この手順では、ネットワーク保護に関連する次のイベントのみを表示するようにフィルター処理するカスタム ビューを作成します。

<br>

****

|イベント ID|説明|
|---|---|
|5007|設定が変更された場合のイベント|
|1125|ネットワーク保護が監査モードで起動した場合のイベント|
|1126|ブロック モードでネットワーク保護が発生した場合のイベント|
|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>ネットワーク保護と TCP の 3 方向ハンドシェイク

ネットワーク保護では、サイトへのアクセスを許可するかブロックするかの決定は、 [TCP/IP 経由の 3 方向ハンドシェイク](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip)が完了した後に行われます。 したがって、サイトがネットワーク保護によってブロックされると、サイトが実際にブロックされていても、Microsoft 365 Defender ポータルでアクションの`ConnectionSuccess``NetworkConnectionEvents`種類が表示される場合があります。 `NetworkConnectionEvents` は、ネットワーク保護からではなく、TCP レイヤーから報告されます。 3 方向ハンドシェイクが完了すると、サイトへのアクセスがネットワーク保護によって許可またはブロックされます。

そのしくみの例を次に示します。

1. ユーザーがデバイス上の Web サイトにアクセスしようとするとします。 サイトは危険なドメインでホストされ、ネットワーク保護によってブロックされる必要があります。  

2. TCP/IP 経由の 3 方向ハンドシェイクが開始されます。 完了する前に `NetworkConnectionEvents` 、アクションがログに記録され、次 `ActionType` のように `ConnectionSuccess`一覧表示されます。 ただし、3 方向ハンドシェイク プロセスが完了するとすぐに、ネットワーク保護によってサイトへのアクセスがブロックされます。 このすべてが非常に迅速に行われます。 同様のプロセスは[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)で発生します。3 方向ハンドシェイクが完了すると、決定が行われ、サイトへのアクセスがブロックまたは許可されます。

3. Microsoft 365 Defender ポータルでは、アラートキューに[アラート](alerts-queue.md)が一覧表示されます。 そのアラートの詳細には、 `NetworkConnectionEvents` 両方と `AlertEvents`. ActionType が .. のアイテムも含 `NetworkConnectionEvents` まれている場合でも、サイトがブロックされていることがわかります `ConnectionSuccess`。

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>マルチセッションを実行する仮想デスクトップWindows 10 Enterprise Windowsに関する考慮事項

Windows 10 Enterpriseのマルチユーザーの性質上、次の点に留意してください。

1. ネットワーク保護はデバイス全体の機能であり、特定のユーザー セッションを対象にすることはできません。

2. Web コンテンツ フィルター ポリシーもデバイス全体です。

3. ユーザー グループを区別する必要がある場合は、個別のWindows Virtual Desktop ホスト プールと割り当てを作成することを検討してください。

4. ネットワーク保護を監査モードでテストし、ロールアウトする前にその動作を評価します。

5. 多数のユーザーまたは多数のマルチユーザー セッションがある場合は、デプロイのサイズを変更することを検討してください。

### <a name="alternative-option-for-network-protection"></a>ネットワーク保護の代替オプション

Windows 10 Enterprise Multi-Session 1909 以降では、Azure 上の Windows Virtual Desktop で使用されます。Microsoft Edgeのネットワーク保護は、次の方法を使用して有効にすることができます。

1. [[ネットワーク保護を有効にする]](enable-network-protection.md) を使用し、指示に従ってポリシーを適用します。

2. 次の PowerShell コマンドを実行します。
  - `Set-MpPreference -EnableNetworkProtection Enabled`
  - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
  - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
  - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>ネットワーク保護のトラブルシューティング

ネットワーク保護が実行される環境により、Microsoft はオペレーティング システム プロキシ設定を検出できない可能性があります。 場合によっては、ネットワーク保護クライアントが Cloud Service に到達できない場合があります。 接続の問題を解決するには、E5 ライセンスをお持ちのお客様は、次のいずれかのレジストリ キーを構成する必要があります。

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="see-also"></a>関連項目

- [ネットワーク保護|を評価する](evaluate-network-protection.md) 機能のしくみと、通常作成されるイベントを示す簡単なシナリオを実行します。
- [ネットワーク保護|を有効にする](enable-network-protection.md)グループ ポリシー、PowerShell、または MDM CSP を使用して、ネットワーク内のネットワーク保護を有効および管理します。
- [Microsoft Intuneでの攻撃面の縮小機能の構成](/mem/intune/protect/endpoint-security-asr-policy)
