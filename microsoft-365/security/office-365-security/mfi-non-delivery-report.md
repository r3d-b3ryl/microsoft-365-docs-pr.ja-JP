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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで配信不可の詳細レポートを使用して、組織内の送信者からの配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も頻繁に発生するエラー コードを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2ac4d55557165c3f6cf327bcff529edc3dc16ad1fc08eb2a5a30828b7a57661
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "56770292"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターの配信&レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティ [&](https://protection.office.com)コンプライアンス センター[](mail-flow-insights-v2.md)のメール フロー ダッシュボードの配信不可レポートには、組織内のユーザーの配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も発生したエラー コードが表示されます。 このレポートには、メール配信の問題をトラブルシューティングするための、NDRs の詳細が表示されます。

![セキュリティ センターコンプライアンス センターのメール フロー ダッシュボードの配信&ウィジェット](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>配信不可レポートのレポート ビュー

[配信不可レポート **] ウィジェットをクリック** すると、[配信不可] **レポートにアクセスします**。

既定では、すべてのエラー コードのアクティビティが表示されます。 [データの表示 **] をクリックすると**、ドロップダウンから特定のエラー コードを選択できます。

グラフ内の特定の日に特定の色 (エラー コード) にカーソルを合わせると、エラーのメッセージの総数が表示されます。

![非承諾ドメイン レポートのレポート ビュー](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>配信不可レポートの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **配信不可レポート コード**
- **Count**
- **サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージの ID です。

詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲****を指定できます**。

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

テーブル内の行を選択すると、次の情報を含むフライアウトが表示されます。

- **Date**
- **配信不可レポート コード**: リンクをクリックすると、特定のエラー コードの原因と解決策の詳細を確認できます。
- **Count**
- **サンプル メッセージ**: [サンプル メッセージの [](message-trace-scc.md)**表示] を** クリックすると、影響を受けるメッセージのサンプルのメッセージ トレース結果を確認できます。

![[配信不可] レポートの [詳細] テーブル ビューで行を選択した後の詳細の飛び出し](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。
