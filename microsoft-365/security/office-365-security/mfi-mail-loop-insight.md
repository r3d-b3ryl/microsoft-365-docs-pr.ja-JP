---
title: メール ループの可能性の修正のインサイト
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで[メール ループの修正] インサイトを使用して、組織内のメール ループを特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 338c76e751ad8fd504ff8182c59fe2a4d8dfb9d8
ms.sourcegitcommit: 4b1bf6e4f4a0c016d148cdde7f7880dd774403d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2021
ms.locfileid: "59988237"
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

セキュリティ **&** コンプライアンス センターのメール フロー ダッシュボードの [推奨されるユーザー [](https://protection.office.com) ] 領域の [メール ループの修正] 領域で、組織内でメール ループが検出されると通知されます。  [](mail-flow-insights-v2.md)

この分析情報は、条件が検出された後にのみ表示されます (メール ループが発生しない場合は、分析情報は表示されません)。

![メール フロー ダッシュボードの [推奨されるユーザー] 領域で、メール フロー ルールの低速分析情報を修正します。](../../media/mfi-fix-possible-mail-loop.png)

ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報が表示されるフライアウトが表示されます。

- **ドメイン**
- **メッセージ数**: [サンプル メッセージの表示][](message-trace-scc.md)を **クリックすると、** ループの影響を受けたメッセージのサンプルのメッセージ トレース結果を確認できます。
- **ドメインの種類**" たとえば、権限を持つもの、権限が無い場合などです。
- **MX レコード**:**ドメインの** MXレコードのホスト (メール サーバー) と優先度の値。
- **ループの理由****と修正方法**: 最も一般的なメール ループシナリオを特定し、ループを修正するための推奨アクションを提供します。

![[可能なメール ループの分析情報を修正する] で [詳細の表示] をクリックした後に表示される詳細フライアウト。](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。
