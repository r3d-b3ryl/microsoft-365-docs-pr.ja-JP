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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで[メール ループの修正] インサイトを使用して、組織内のメール ループを特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a74e7cc623dffd6bae6451f7488d8f630b607b2
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469143"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターで考えられるメール ループ&修正する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

メール ループが悪いのは、次の理由からです。

- システム リソースを無駄にしています。
- 組織のメール ボリューム クォータを使用します。
- 元のメッセージ送信者に、わかりにくい配信以外のレポート (NDRs またはバウンス メッセージとも呼ばれる) を送信します。

セキュリティ **&** コンプライアンス センターのメール フロー ダッシュボードの [推奨されるユーザー] [](mail-flow-insights-v2.md) 領域の [メール ループ [](https://protection.office.com)の修正] 領域で、組織内でメール ループが検出されると通知されます。

この分析情報は、条件が検出された後にのみ表示されます (メール ループが発生しない場合は、分析情報は表示されません)。

:::image type="content" source="../../media/mfi-fix-possible-mail-loop.png" alt-text="メール フロー ダッシュボードの [おすすめ] 領域の [低速メール フロー ルールの修正] インサイト" lightbox="../../media/mfi-fix-possible-mail-loop.png":::

ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報が表示されるフライアウトが表示されます。

- **ドメイン**
- **メッセージ数:** [サンプル メッセージの表示] を **クリックすると、** ループの影響を受けたメッセージのサンプルのメッセージ トレース結果を確認できます。[](message-trace-scc.md)
- **ドメインの種類**" たとえば、権限または権限の不備です。
- **MX レコード**: **ドメインの MX** レコードのホスト (メール サーバー) と優先度の値。
- **ループの理由****と修正方法**: 最も一般的なメール ループシナリオを特定し、ループを修正するための推奨アクションを提供します。

:::image type="content" source="../../media/mfi-fix-possible-mail-loop-details.png" alt-text="[可能なメール ループの分析情報を修正する] の [詳細の表示] をクリックした後に表示される詳細フライアウト" lightbox="../../media/mfi-fix-possible-mail-loop-details.png":::

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、「Security [& コンプライアンス センター」を参照してください](mail-flow-insights-v2.md)。
