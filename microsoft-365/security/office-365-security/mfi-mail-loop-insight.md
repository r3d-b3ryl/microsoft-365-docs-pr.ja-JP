---
title: メール ループの可能性の修正のインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ &/コンプライアンス センターのメール フロー ダッシュボードでメール ループの可能性に関する分析情報を使用して、組織のメール ループを特定し、修正する方法を学習できます。
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826955"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターのメール ループの可能性を&する

メール ループは、システム リソースを消費し、組織のメール量クォータを消費し、配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) を元の送信者に送信しているため、不正です。

セキュリティ **& コンプライアンス センターの**メール フロー ダッシュボードの **[推奨**されるメール[Mail flow dashboard](mail-flow-insights-v2.md)フロー] 領域でメール ループの可能性の分析情報により、組織内でメール ループが検出された場合に、そのユーザーにおすすめが表示されます。 この分析情報は、条件が検出された後にのみ表示されます (メール ループがない場合、分析情報は表示されません)。

![メール フロー ダッシュボードの [推奨されるユーザーの詳細] 領域の低速メール フロー ルールの分析情報を修正する](../../media/mfi-fix-possible-mail-loop.png)

ウィジェ **ットの [** 詳細の表示] をクリックすると、さらに情報を含むポップアップが表示されます。

- **ドメイン**
- **[メッセージ数]:**[ **サンプル メッセージの表示] をクリック** すると、 [ループの](message-trace-scc.md) 影響を受けていたメッセージのサンプルに関するメッセージ トレース結果を確認できます。
- **ドメインの**種類は、「権限のあるアイテム」または「権限のない」です。
- **MX レコード**: ドメインの MX**レコード**のホスト ( メール サーバー) と **Priority** の値。
- **ループの** 理由 **と解決方法**: 最も一般的なメール ループのシナリオを特定し、ループを修正するための推奨アクション (ある場合) を提供します。

![[修正] の [修正] の [詳細を表示] をクリックした後に表示される詳細ポップアップ](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。
