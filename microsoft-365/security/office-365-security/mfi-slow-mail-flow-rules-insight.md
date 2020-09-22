---
title: 時間のかかるメール フロー ルールの修正のインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターにある [低速なメールフロールールの詳細を修正する] を使用して、組織内の非効率的または壊れたメールフロールール (トランスポートルールとも呼ばれます) を特定して修正する方法を学習できます。
ms.openlocfilehash: 2f9a35534ab4377cff164b38eeb66dd55c48d5b9
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199267"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターでの低速メールフロールールの洞察を修正する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


非効率的なメールフロールール (トランスポートルールとも呼ばれます) は、組織のメールフロー遅延につながる可能性があります。 この洞察は、組織のメールフローに影響を与えるメールフロールールを報告します。 これらの種類のルールの例を次に示します。

- **が**大規模なグループの場合、を使用する条件。
- 複合正規表現 (regex) パターンマッチングを使用する条件。
- 添付ファイルのコンテンツチェックを使用する条件。

「セキュリティの**低速メール**フロールール」では、[セキュリティ & コンプライアンスセンター](https://protection.office.com)のメール[フローダッシュボード](mail-flow-insights-v2.md)の**推奨事項につい**て理解しています。メールフロールールの完了に時間がかかりすぎた場合に通知します。 この洞察は、条件が検出された後にのみ表示されます (メールループがない場合は、洞察は見られません)。

メールフローの遅延を減らすために、この通知を使用して、メールフロールールを識別し、微調整することができます。

![メールフローダッシュボードのお住まいの地域で推奨されるメールフロールールの詳細を修正する](../../media/mfi-fix-slow-mail-flow-rules.png)

ウィジェットの [ **詳細の表示** ] をクリックすると、詳細情報を含むフライアウトが表示されます。

- **ルール**: 概要にマウスカーソルを移動すると、ルールのすべての条件、例外、およびアクションが表示されます。 概要をクリックして、Exchange 管理センター (EAC) でルールを編集できます。
- 評価された**メッセージの数**: [**サンプルメッセージの表示**] をクリックすると、ルールの影響を受けたメッセージのサンプルのメッセージの[追跡](message-trace-scc.md)結果が表示されます。
- **各メッセージにかかった平均時間**
- **メッセージにかかった平均**時間: 時間データの下半分から上半分を区切る中央値。

![[Fix the details mail flow rules] の [詳細の表示] をクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Exchange Online のメールフロールールにおける条件と例外の詳細については、「 [Exchange online のメールフロールールの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。

## <a name="related-topics"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
