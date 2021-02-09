---
title: メール ループの可能性の修正のインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでメール ループの可能性のあるインサイトを修正して、組織内のメール ループを特定して修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c9607f053fb5011b8c8af3c8bb2073a9d022909
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150233"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで考えられるメール ループ&修正

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

メール ループは、次の理由から悪い場合があります。

- システム リソースを無駄に使います。
- 組織のメール ボリューム クォータが消費されます。
- 元のメッセージ送信者に、混乱を招く配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) を送信します。

セキュリティ **&** コンプライアンス センターのメール フロー ダッシュボードの [](mail-flow-insights-v2.md)[推奨されるユーザー] 領域にある[推奨されるメール ループの分析情報を修正する] は、組織内でメール ループが検出されると通知します。  [](https://protection.office.com)

この分析情報は、条件が検出された後にのみ表示されます (メール ループを使用しない場合、分析情報は表示されません)。

![メール フロー ダッシュボードの [推奨されるユーザー] 領域で低速のメール フロー ルールの分析情報を修正する](../../media/mfi-fix-possible-mail-loop.png)

ウィジェットの [ **詳細の表示]** をクリックすると、詳細情報を含むフライアウトが表示されます。

- **ドメイン**
- **メッセージ数**: [サンプルメッセージの表示][](message-trace-scc.md)をクリックすると、ループの影響を受けたメッセージのサンプルのメッセージ追跡結果を確認できます。
- **ドメインの種類**" たとえば、権限がある、または権限が不必要です。
- **MX レコード**: ドメインのホスト(**メール サーバー**) と MX レコードの優先度の値。
- **ループの** 理由と **修正方法**: 最も一般的なメール ループ シナリオを特定し、ループを修正するための推奨アクションを提供します。

![[可能なメール ループの分析情報を修正する] の [詳細の表示] をクリックした後に表示される詳細フライアウト](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>こちらもご覧ください

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
