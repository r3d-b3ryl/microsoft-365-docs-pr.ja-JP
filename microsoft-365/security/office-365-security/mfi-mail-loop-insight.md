---
title: メール ループの可能性の修正のインサイト
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターの [メール フロー] ダッシュボードの [Fix possible mail loop insight] を使用して、組織内のメール ループを特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a74e7cc623dffd6bae6451f7488d8f630b607b2
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469143"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターで考えられるメール ループの分析情報を修正する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

メール ループは次の理由で正しくありません。

- システム リソースを浪費します。
- 組織のメール 量クォータを使用します。
- 配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) を元のメッセージ送信者に送信します。

[セキュリティ & コンプライアンス センター](https://protection.office.com)の [推奨されるメール [フロー] ダッシュボード](mail-flow-insights-v2.md)の [**推奨** されるメール ループ] の分析情報を **修正** すると、組織内でメール ループが検出されたときに通知されます。

この分析情報は、条件が検出された後にのみ表示されます (メール ループがない場合、分析情報は表示されません)。

:::image type="content" source="../../media/mfi-fix-possible-mail-loop.png" alt-text="[メール フロー] ダッシュボードの [推奨されるユーザー] 領域の [低速メール フロー ルールの修正] 分析情報" lightbox="../../media/mfi-fix-possible-mail-loop.png":::

ウィジェットの **[詳細の表示** ] をクリックすると、ポップアップが表示され、詳細情報が表示されます。

- **ドメイン**
- **メッセージの数**: [ **サンプル メッセージの表示** ] をクリックすると、ループの影響を受けたメッセージのサンプルのメッセージ [トレース](message-trace-scc.md) 結果を確認できます。
- **[ドメインの種類**] たとえば、[権限あり] または [権限なし] です。
- **MX レコード**: ドメインの MX レコードのホスト (**メール サーバー**) と **優先度** の値。
- **Loop理由** と **修正方法**: 最も一般的なメール ループのシナリオを特定し、ループを修正するための推奨されるアクションを提供します。

:::image type="content" source="../../media/mfi-fix-possible-mail-loop-details.png" alt-text="[Fix possible mail loop insight] の [詳細の表示] をクリックした後に表示される [詳細] ポップアップ" lightbox="../../media/mfi-fix-possible-mail-loop-details.png":::

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
