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
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターの低速メール フロールールの修正分析情報を使用して、組織内の非効率的なメール フロー ルールまたは破損したメール フロー ルール (トランスポート ルールとも呼ばれます) を特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 650389529f2a5d811f71b7c3f755d93e7e734d81
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128742"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターの低速メール フロー ルール分析情報を修正する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

非効率的なメール フロー ルール (トランスポート ルールとも呼ばれます) は、組織のメール フローの遅延につながる可能性があります。 この分析情報は、組織のメール フローに影響を与えるメール フロー ルールを報告します。 これらの種類のルールの例を次に示します。

- 大規模なグループに対して **Is メンバーを** 使用する条件。
- 複雑な正規表現 (正規表現) パターンマッチングを使用する条件。
- 添付ファイルのコンテンツ チェックインを使用する条件。

[セキュリティ & コンプライアンス センター](https://protection.office.com)の [[メール フロー](mail-flow-insights-v2.md) の推奨] ダッシュボードの [**推奨される** メール **フロー ルール**] の分析情報は、メール フロー ルールの完了に時間がかかりすぎる場合に通知します。

この分析情報は、条件が検出された後にのみ表示されます (メール ループがない場合、分析情報は表示されません)。

この通知を使用すると、メール フローの遅延を減らすのに役立つメール フロー ルールを特定し、微調整することができます。

:::image type="content" source="../../media/mfi-fix-slow-mail-flow-rules.png" alt-text="[メール フロー] ダッシュボードの [推奨されるユーザー] 領域の [低速メール フロー ルールの修正] 分析情報" lightbox="../../media/mfi-fix-slow-mail-flow-rules.png":::

ウィジェットの **[詳細の表示** ] をクリックすると、ポップアップが表示され、詳細情報が表示されます。

- **ルール**: 概要にマウス ポインターを合わせると、ルールのすべての条件、例外、およびアクションを確認できます。 概要をクリックすると、Exchange管理センター (EAC) で<https://admin.exchange.microsoft.com/#/transportrules>ルールを編集できます。
- **評価されたメッセージの数**: [ **サンプル メッセージの表示** ] をクリックすると、ルールの影響を受けたメッセージのサンプルのメッセージ [トレース](message-trace-scc.md) 結果を確認できます。
- **各メッセージに費やされた平均時間**
- **メッセージに費やされた中央値**: 上半分と下半分の時間データを区切る中央値。

:::image type="content" source="../../media/mfi-fix-slow-mail-flow-rules-details.png" alt-text="[低速メール フロー ルールの修正] 分析情報で [詳細の表示] をクリックした後に表示される [詳細] ポップアップ" lightbox="../../media/mfi-fix-slow-mail-flow-rules-details.png":::

メール フロー ルールにおける条件と例外の詳細については、「[Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
