---
title: メール フロー ダッシュボードの配信不可レポート
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで配信の詳細レポートを使用して、組織内の送信者からの配信前レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も頻繁に発生するエラー コードを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd27fc818a46a983874a04f0e313c622e047ea5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029836"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターの配信&レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[セキュリティ](https://protection.office.com)& コンプライアンス センター[](mail-flow-insights-v2.md)のメール フロー ダッシュボードの配信不可レポートには、組織内のユーザーの配信レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も発生したエラー コードが表示されます。  このレポートには、メール配信の問題をトラブルシューティングするための、NDRs の詳細が表示されます。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの配信&ウィジェット](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>配信前レポートのレポート ビュー

配信レポートウィジェット **をクリック** すると、配信先以外の **レポートにアクセスできます**。

既定では、すべてのエラー コードのアクティビティが表示されます。 [データの **表示] をクリック** すると、ドロップダウンから特定のエラー コードを選択できます。

グラフの特定の日に特定の色 (エラー コード) をポイントすると、エラーのメッセージの総数が表示されます。

![[非承諾ドメイン] レポートのレポート ビュー](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>配信不可レポートの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **日付**
- **配信不可レポート コード**
- **Count**
- **サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージ ID。

詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

テーブル内の行を選択すると、次の情報を含むフライアウトが表示されます。

- **日付**
- **配信レポートのコード**: リンクをクリックすると、特定のエラー コードの原因と解決策の詳細を確認できます。
- **Count**
- **サンプル メッセージ**: [サンプル メッセージの表示 [](message-trace-scc.md)]**を** クリックすると、影響を受けるメッセージのサンプルのメッセージ追跡結果を表示できます。

![配信不可レポートの [詳細] テーブル ビューで行を選択した後の詳細フライアウト](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
