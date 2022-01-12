---
title: 時間のかかるメール フロー ルールの修正のインサイト
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターで [低速メール フロー ルールの修正] 分析情報を使用して、組織内の非効率的または壊れたメール フロー ルール (トランスポート ルールとも呼ばれる) を特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9866761e683e15d34d81b8ea0962d974b0b474da
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61935223"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターでメール フロー ルールの分析情報が遅&修正する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

非効率的なメール フロー ルール (トランスポート ルールとも呼ばれる) は、組織のメール フローの遅延につながる可能性があります。 この分析情報は、組織のメール フローに影響を与えるメール フロー ルールを報告します。 これらの種類のルールの例を次に示します。

- 大規模なグループ **の Is メンバーを** 使用する条件。
- 複雑な正規表現 (regex) パターンマッチングを使用する条件。
- 添付ファイルのコンテンツ チェックインを使用する条件。

セキュリティ [&](https://protection.office.com)コンプライアンス センターのメールフロー ダッシュボードの[](mail-flow-insights-v2.md)[推奨されるユーザー] 領域にある [メール フロー ルールの修正] インサイトは、メール フロー ルールの完了に時間がかかっているときに通知します。

この分析情報は、条件が検出された後にのみ表示されます (メール ループが発生しない場合は、分析情報は表示されません)。

この通知を使用すると、メール フロー ルールを特定して微調整し、メール フローの遅延を減らすのに役立ちます。

![メール フロー ダッシュボードの [推奨されるユーザー] 領域で、メール フロー ルールの低速分析情報を修正します。](../../media/mfi-fix-slow-mail-flow-rules.png)

ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報が表示されるフライアウトが表示されます。

- **ルール**: 概要にカーソルを合わせると、ルールのすべての条件、例外、およびアクションが表示されます。 概要をクリックすると、管理センター (EAC) の Exchangeを編集できます <https://admin.exchange.microsoft.com/#/transportrules> 。
- **評価されるメッセージの** 数 : [サンプル メッセージの表示][](message-trace-scc.md)をクリックすると、ルールの影響を受けたメッセージのサンプルのメッセージ トレース結果を確認できます。
- **各メッセージに費やされた平均時間**
- **メッセージに費やされた時間の** 中央値 : 上半分と下半分の時間データを分離する中央値。

![[低速メール フロー ルールの修正] インサイトの [詳細の表示] をクリックした後に表示される詳細フライアウト。](../../media/mfi-fix-slow-mail-flow-rules-details.png)

メール フロー ルールにおける条件と例外の詳細については、「[Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。