---
title: メール フロー ダッシュボードの承認済みでないドメイン レポート
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで承認されていないドメイン レポートを使用して、送信者のドメインが Microsoft 365 で構成されていないオンプレミス組織からのメッセージを監視する方法を学習できます。
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826943"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターの承認済みでない& レポート

セキュリティ & コンプライアンス **センターのメール** フロー ダッシュボード [に表示される [承認](mail-flow-insights-v2.md) 済みでないドメイン] レポートには、送信者のドメインが Microsoft 365 組織の承認済みドメインとして構成されていないオンプレミスの電子メール組織からのメッセージに関する情報が表示されます。

Microsoft 365 がこれらのメッセージの意図を悪意のあるものに証明するためのデータがある場合、Microsoft 365 によってこれらのメッセージが調整される可能性があります。 そのため、何が起こったかを把理解して問題を解決するのが重要です。

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードで承認されていないドメイン ウィジ&ジェット](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>承認されていないドメイン レポートのレポート ビュー

[承認されていないドメイン] **ウィジェットの** グラフをクリックすると、承認されていない **ドメイン レポートに表示** されます。

既定では、影響を受けるコネクタすべてのアクティビティが表示されます。 [データの **表示] をクリック**すると、ドロップダウンから特定のコネクタを選択できます。

グラフ内のデータ ポイント (日) にポイントすると、コネクタのメッセージの合計数が表示されます。

!["承認されていないドメイン" レポートのレポート ビュー](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>承認されていないドメイン レポートの詳細テーブル ビュー

レポート ビューで **詳細テーブルの表示** をクリックすると、次の情報が表示されます。

- **Date**
- **受信コネクタの名前**
- **送信元ドメイン**
- **メッセージ数**
- **サンプル メッセージ**: 影響を受けつメッセージのサンプルのメッセージ ID。

詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲****を指定できます**。

特定の日付範囲のレポートを 1 名以上の受信者にメールで送信するには、[ **ダウンロードを要求] をクリックします**。

表で行を選択すると、以下の情報を含むポップアップが表示されます。

- **Date**
- **受信コネクタの名前**
- **送信元ドメイン**
- **メッセージ数**
- **サンプル メッセージ**: [サンプル メッセージの **表示] をクリック** すると、影響 [を受けつ](message-trace-scc.md) つサンプル メッセージのメッセージトレース結果を表示できます。

![[承認されていないドメイン] レポートの [詳細] テーブル ビューで行を選択した後の詳細ポップアップ](../../media/mfi-non-accepted-domain-report-details-flyout.png)

レポート ビューに戻るには、[レポートの表示] **をクリックします**。

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。
