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
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6fb72c68d69c6844c981c7575bcfed3811a8d20e55a51485d78e26ec447becfe
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53867981"
---
# <a name="protect-your-network"></a>ネットワークを保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

ネットワーク保護は、インターネット ベースのイベントからデバイスの攻撃表面を減らすのに役立ちます。 これは、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐためです。 ネットワーク保護は[、Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)の範囲を拡張して、低評価ソース (ドメインまたはホスト名に基づく) への接続を試みるすべての送信 HTTP トラフィックをブロックします。

ネットワーク保護は、Windowsバージョン 1709 Windows 10からサポートされます。 ネットワーク保護は他のオペレーティング システムではまだサポートされていませんが、Web 保護は、新しいオペレーティング システムを使用Microsoft EdgeサポートChromium。 詳細については、「Web 保護」 [を参照してください](web-protection-overview.md)。

ネットワーク保護は、Web 保護の保護 [をオペレーティング](web-protection-overview.md) システム レベルまで拡張します。 Edge の Web 保護機能は、サポートされている他のブラウザーやブラウザー以外のアプリケーションに提供されます。 さらに、ネットワーク保護は、エンドポイントの検出と応答で使用する場合に、侵害の指標 (IOC) の可視性とブロック [を提供します](overview-endpoint-detection-response.md)。 たとえば、ネットワーク保護はカスタム インジケーターと [動作します](manage-indicators.md)。

ネットワーク保護を有効にする方法の詳細については、「ネットワーク保護を有効 [にする」を参照してください](enable-network-protection.md)。 グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。

> [!TIP]
> ネットワーク保護のしくみについては、「Microsoft Defender for [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Endpoint testground」の demo.wd.microsoft.com を参照してください。

ネットワーク保護は [、Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)で最適に機能します。これにより、アラート調査シナリオの一環として、エクスプロイト保護イベントとブロックに関する詳細なレポート [が提供されます](investigate-alerts.md)。

ネットワーク保護が接続をブロックすると、アクション センターから通知が表示されます。 セキュリティ運用チームは、 [組織の詳細と](customize-attack-surface-reduction.md#customize-the-notification) 連絡先情報を使用して通知をカスタマイズできます。 さらに、個々の攻撃表面の縮小ルールを有効にし、監視する特定の手法に合わせてカスタマイズできます。

監査モードを使用 [して、](audit-windows-defender.md) ネットワーク保護が有効になっている場合に組織に与える影響を評価することもできます。

## <a name="requirements"></a>Requirements

ネットワーク保護には、Windows 10 ProまたはEnterprise、リアルタイムMicrosoft Defender ウイルス対策保護が必要です。

| Windows バージョン | Microsoft Defender ウイルス対策 |
|:---|:---|
| Windows 10バージョン 1709 以降 <p>Windowsサーバー 1803 以降 | [Microsoft Defender ウイルス対策保護とクラウド](configure-real-time-protection-microsoft-defender-antivirus.md)[配信保護を有効](enable-cloud-protection-microsoft-defender-antivirus.md)にする必要があります |

サービスを有効にした後、サービスとデバイス (エンドポイントとも呼ばれます) 間の接続を許可するために、ネットワークまたはファイアウォールを構成する必要がある場合があります。  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Microsoft Defender for Endpoint Security Center のネットワーク保護イベントを確認する

Microsoft Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックに関する詳細 [なレポートを提供します](investigate-alerts.md)。

高度な検索を使用して、Microsoft Defender for Endpoint データ [を照会できます](advanced-hunting-overview.md)。 監査モードを使用 [している場合](audit-windows-defender.md)は、高度な検索を使用して、ネットワーク保護設定が有効になっている場合に環境に与える影響を確認できます。

クエリの例を次に示します。

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>イベント ビューアーでネットワーク保護イベントWindows確認する

ネットワーク保護が悪意のある IP またはドメインWindowsアクセスをブロック (または監査) するときに作成されるイベントを確認するには、次のイベント ログを確認します。

1. [XML を直接コピーします](event-views.md)。

2. **[OK]** をクリックします。

この手順では、ネットワーク保護に関連する次のイベントのみを表示するためにフィルター処理するカスタム ビューを作成します。

| イベント ID | 説明 |
|:---|:---|
| 5007 | 設定が変更された場合のイベント |
| 1125 | 監査モードでネットワーク保護が発生した場合のイベント |
| 1126 | ブロック モードでネットワーク保護が発生した場合のイベント |

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

## <a name="related-articles"></a>関連記事

- [ネットワーク保護の評価|](evaluate-network-protection.md) 機能の動作と、通常作成されるイベントを示す簡単なシナリオを実行します。

- [ネットワーク保護の有効化|](enable-network-protection.md) グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。
