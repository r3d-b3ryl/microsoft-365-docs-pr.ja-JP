---
title: Microsoft Defender for microsoft Defender for Office 365
description: 高度な検索を使用して電子メールの脅威の検索を開始する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0226be17f475250d5d50d363596bd115f27ce6cd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191541"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Microsoft Defender for microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度な検出を使用してメールの脅威の検索を開始しますか? 実行する操作:

[Microsoft Defender for Office 365の記事](/microsoft-365/security/office-365-security/defender-for-office-365)の「[使用を開始する](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started)」セクションには、次のような論理的な早期構成用の単位があります。

1. 名前に 'Anti' を含むすべてを構成します。
   - マルウェア対策
   - フィッシング詐欺対策
   - スパム対策
2. 名前に 'セーフ' を含むすべてを設定します。
   - 安全なリンク
   - 安全な添付ファイル
3. ワークロードを保護する (例: SharePointオンライン、OneDrive、およびTeams)。
4. 0 時間自動削除で保護します。

[リンク](../office-365-security/protect-against-threats.md)をクリックすると、一気にジャンプして、第 1 日目から使用できる構成を入手できます。

**開始** の最後の手順は、**ゼロアワー自動消去**(ZAP) によるユーザー保護です。 ZAP で不審なメールや悪意のあるメール、配信後のメールの自動消去が成功したどうかを知るのはとても重要です。

問題を探し出す場合に、Kusto クエリ言語にすばやく移動できることは、2 つのセキュリティ センターを集約する利点です。 セキュリティ チームは、次の手順を実行して、ZAP ミスを監視 [](https://security.microsoft.com/advanced-hunting) \> **できます**。

1. [高度な検索] ページで、[クエリ] を **クリックします**。
1. 次のクエリを[クエリ] ウィンドウにコピーします。
1. **[クエリの実行]** を選択します。

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="クエリ パネルの上部で [クエリ] を選択し、過去 7 日間の ZAP アクションをキャプチャするために Kusto クエリを実行した [高度な検索] ページ ([ハンティング] の下)。":::

このクエリのデータは、クエリ自体の下の結果パネルに表示されます。 結果には、カスタマイズ可能な結果セットに 'DeviceName', 'AccountDisplayName'、および 'ZapTime' が含まれています。 ユーザーの記録用に、結果をエクスポートすることもできます。 クエリがもう一度必要な場合は、**[保存する]** > **[以下の名前で保存する]** の順に選択し、クエリ、共有クエリ、またはコミュニティ クエリの一覧にそのクエリを追加します。

## <a name="related-information"></a>関連情報
- [高度な狩猟のベスト プラクティス](advanced-hunting-best-practices.md)
- [概要 - 高度な検索](advanced-hunting-overview.md)
