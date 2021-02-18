---
title: 時間のかかるメール フロー ルールの修正のインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターで低速メール フロー ルールの修正の分析情報を使用して、組織の非効率的または破損したメール フロー ルール (トランスポート ルールとも呼ばれる) を特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a50fa0d36cb025f5d0627a2212254b9d08dc5d9c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290695"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで低速のメール フロー ルールの&を修正する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

非効率的なメール フロー ルール (トランスポート ルールとも呼ばれる) は、組織のメール フローの遅延につながる可能性があります。 このインサイトは、組織のメール フローに影響を与えるメール フロー ルールを報告します。 これらの種類のルールの例を次に示します。

- 大規模なグループ **の Is メンバーを** 使用する条件。
- 複雑な正規表現 (regex) パターンマッチングを使用する条件。
- 添付ファイルのコンテンツ チェックを使用する条件。

セキュリティ & コンプライアンス センターのメールフロー ダッシュボードの [推奨されるユーザー][](https://protection.office.com)領域にある [低速メール フロー ルールの修正] の分析情報は、メール フロー ルールの完了に時間がかかっている場合に通知します。 [](mail-flow-insights-v2.md)

この分析情報は、条件が検出された後にのみ表示されます (メール ループを使用しない場合、分析情報は表示されません)。

この通知を使用すると、メール フロー ルールを特定して微調整し、メール フローの遅延を減らすのに役立ちます。

![メール フロー ダッシュボードの [おすすめ] 領域で低速のメール フロー ルールの分析情報を修正する](../../media/mfi-fix-slow-mail-flow-rules.png)

ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報を含むフライアウトが表示されます。

- **ルール**: 概要をポイントすると、ルールのすべての条件、例外、およびアクションを表示できます。 概要をクリックすると、Exchange 管理センター (EAC) でルールを編集できます。
- **評価されるメッセージ** の数 : [サンプル メッセージの表示][](message-trace-scc.md)をクリックすると、ルールの影響を受けたメッセージのサンプルのメッセージ追跡結果を表示できます。
- **各メッセージに費やされた平均時間**
- **メッセージに費やした時間の中央** 値: 上半分と下位半分の時間データを分け合う中間値。

![[低速メール フロー ルールの修正] インサイトの [詳細の表示] をクリックした後に表示される詳細フライアウト](../../media/mfi-fix-slow-mail-flow-rules-details.png)

メール フロー ルールにおける条件と例外の詳細については、「[Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
