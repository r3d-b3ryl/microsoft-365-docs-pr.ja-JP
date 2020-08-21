---
title: メール フロー ダッシュボードの配信不能レポート
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで配信不能の詳細レポートを使用して、組織内の送信者からの配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) で最も頻出されるエラー コードを監視する方法を学習できます。
ms.openlocfilehash: bdc2a2a16f76f4e6ada629c82b86423422ab56c9
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826919"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターの配信 &不能レポート

セキュリティ &**コンプライアンス センターの**[メール フロー ダッシュボードの配信不能レポート](mail-flow-insights-v2.md)には、組織内のユーザーの配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) で最も発生するエラー コードが表示されます。 このレポートには、メール配信の問題のトラブルシューティングを行うための NDR の詳細が表示されます。

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードの配信不能レポート ウィ&ジェット](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>配信不能レポートのレポート ビュー

配信不能 **レポート ウィジ** ェットをクリックすると、配信不能 **レポートが開きます**。

既定では、すべてのエラー コードのアクティビティが表示されます。 [データの **表示] をクリック**すると、ドロップダウンから特定のエラー コードを選択できます。

グラフ内の特定の日付で特定の色 (エラー コード) の上に設定すると、エラーの合計メッセージ数が表示されます。

!["承認されていないドメイン" レポートのレポート ビュー](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>配信不能レポートの詳細テーブル ビュー

レポート ビューで **詳細テーブルの表示** をクリックすると、次の情報が表示されます。

- **Date**
- **配信不能レポート コード**
- **Count**
- **サンプル メッセージ**: 影響を受けつメッセージのサンプルのメッセージ ID。

詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲****を指定できます**。

特定の日付範囲のレポートを 1 名以上の受信者にメールで送信するには、[ **ダウンロードを要求] をクリックします**。

表で行を選択すると、以下の情報を含むポップアップが表示されます。

- **Date**
- **配信不能レポートのコード**: リンクをクリックすると、特定のエラー コードの原因と解決策に関する詳細を見つけ出します。
- **Count**
- **サンプル メッセージ**: [サンプル メッセージの **表示] をクリック** すると、影響 [を受けつ](message-trace-scc.md) つサンプル メッセージのメッセージトレース結果を表示できます。

![[Non-delivery report] レポートの [詳細] テーブル ビューで行を選択した後の詳細ポップアップ](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。
