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
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: be98bf810d00b6e39ba9d2674604a9fd2128a8cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198657"
---
# <a name="protect-your-network"></a>ネットワークを保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

ネットワーク保護は、インターネット ベースのイベントからデバイスの攻撃表面を減らすのに役立ちます。 これは、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐためです。 ネットワーク保護は [、Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の範囲を拡張して、低評価ソース (ドメインまたはホスト名に基づく) への接続を試みるすべての送信 HTTP トラフィックをブロックします。

ネットワーク保護は、Windows 10 バージョン 1709 から Windows でサポートされています。 

ネットワーク保護を有効にする方法の詳細については、「ネットワーク保護を有効 [にする」を参照してください](enable-network-protection.md)。 グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。

> [!TIP]
> ネットワーク保護の仕組みについては、「Microsoft Defender ATP testground サイト」demo.wd.microsoft.com [を参照](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) してください。

ネットワーク保護は [、Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)で最適に機能します。これにより、アラート調査シナリオの一環として、エクスプロイト保護イベントとブロックに関する詳細なレポート [が提供されます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。

ネットワーク保護が接続をブロックすると、アクション センターから通知が表示されます。 セキュリティ運用チームは、 [組織の詳細と](customize-attack-surface-reduction.md#customize-the-notification) 連絡先情報を使用して通知をカスタマイズできます。 さらに、個々の攻撃表面の縮小ルールを有効にし、監視する特定の手法に合わせてカスタマイズできます。

監査モードを使用 [して、](audit-windows-defender.md) ネットワーク保護が有効になっている場合に組織に与える影響を評価することもできます。

## <a name="requirements"></a>要件

ネットワーク保護には、Windows 10 Pro または Enterprise、および Microsoft Defender ウイルス対策のリアルタイム保護が必要です。

| Windows バージョン | Microsoft Defender ウイルス対策 |
|:---|:---|
| Windows 10 バージョン 1709 以降 <p>Windows Server 1803 以降 | [Microsoft Defender ウイルス対策のリアルタイム保護と](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md)[クラウド配信の保護を有効](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md)にする必要があります |

サービスを有効にした後、サービスとデバイス (エンドポイントとも呼ばれます) 間の接続を許可するために、ネットワークまたはファイアウォールを構成する必要がある場合があります。  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Microsoft Defender for Endpoint Security Center のネットワーク保護イベントを確認する

Microsoft Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックに関する詳細 [なレポートを提供します](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。

高度な検索を使用して、Microsoft Defender for Endpoint データ [を照会できます](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)。 監査モードを使用 [している場合](audit-windows-defender.md)は、高度な検索を使用して、ネットワーク保護設定が有効になっている場合に環境に与える影響を確認できます。

クエリの例を次に示します。

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Windows イベント ビューアーでネットワーク保護イベントを確認する

Windows イベント ログを確認して、ネットワーク保護が悪意のある IP またはドメインへのアクセスをブロック (または監査) するときに作成されるイベントを確認できます。

1. [XML を直接コピーします](event-views.md)。

2. **[OK]** をクリックします。

この手順では、ネットワーク保護に関連する次のイベントのみを表示するためにフィルター処理するカスタム ビューを作成します。

| イベント ID | 説明 |
|:---|:---|
| 5007 | 設定が変更された場合のイベント |
| 1125 | 監査モードでネットワーク保護が発生した場合のイベント |
| 1126 | ブロック モードでネットワーク保護が発生した場合のイベント |

## <a name="related-articles"></a>関連記事

- [ネットワーク保護の評価|](evaluate-network-protection.md) 機能の動作と、通常作成されるイベントを示す簡単なシナリオを実行します。

- [ネットワーク保護の有効化|](enable-network-protection.md) グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。
