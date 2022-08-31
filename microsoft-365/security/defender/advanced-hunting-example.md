---
title: Microsoft Defender for Office 365の高度なハンティングの例
description: 高度な捜索を使用して電子メールの脅威の検索を開始する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 014802107d564fc24cf5e50a7513c390dcc943d5
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480064"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365の高度なハンティングの例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度な検出を使用してメールの脅威の検索を開始しますか? 実行する操作:

[Microsoft Defender for Office 365の記事](/microsoft-365/security/office-365-security/defender-for-office-365)の「[使用を開始する](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started)」セクションには、次のような論理的な早期構成用の単位があります。

1. 名前に "Anti" を含むすべてを構成します。
   - マルウェア対策
   - フィッシング詐欺対策
   - スパム対策
2. 名前に "安全" を含むすべてを設定します。
   - 安全なリンク
   - 安全な添付ファイル
3. ワークロードを保護する (例: SharePoint Online、OneDrive、Teams)。
4. ゼロ時間の自動消去で保護します。

[リンク](../office-365-security/protect-against-threats.md)をクリックすると、一気にジャンプして、第 1 日目から使用できる構成を入手できます。

**開始** の最後の手順は、**ゼロアワー自動消去**(ZAP) によるユーザー保護です。 ZAP で不審なメールや悪意のあるメール、配信後のメールの自動消去が成功したどうかを知るのはとても重要です。

問題を探し出す場合に、Kusto クエリ言語にすばやく移動できることは、2 つのセキュリティ センターを集約する利点です。 セキュリティ チームは、**ハンティング****高度なハンティング**\>の下で、[ここで](https://security.microsoft.com/advanced-hunting)次の手順を実行することで ZAP ミスを監視できます。

1. [高度な検索] ページで、[クエリ] をクリック **します**。
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

:::image type="content" source="../../media/ah-query-example-new.png" alt-text="クエリ パネルの上部で [クエリ] が選択され、Kusto クエリを実行して過去 7 日間の ZAP アクションをキャプチャする [高度なハンティング] ページ ([ハンティング] の下)。" lightbox="../../media/ah-query-example-new.png":::

このクエリのデータは、クエリ自体の下の結果パネルに表示されます。 結果には、カスタマイズ可能な結果セットに 'DeviceName', 'AccountDisplayName'、および 'ZapTime' が含まれています。 ユーザーの記録用に、結果をエクスポートすることもできます。 クエリがもう一度必要な場合は、**[保存する]** > **[以下の名前で保存する]** の順に選択し、クエリ、共有クエリ、またはコミュニティ クエリの一覧にそのクエリを追加します。

## <a name="related-information"></a>関連情報
- [高度なハンティングのベスト プラクティス](advanced-hunting-best-practices.md)
- [概要 - 高度なハンティング](advanced-hunting-overview.md)
