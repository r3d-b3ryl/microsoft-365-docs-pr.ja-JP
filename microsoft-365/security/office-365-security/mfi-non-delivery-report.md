---
title: メール フロー ダッシュボードの配信不能レポート
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで配信不能の詳細レポートを使用して、組織内の送信者からの配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) で最も頻繁に発生するエラー コードを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 663e145bcf9d6dc95f0f71b3b0b50a78419ed989
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64973511"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターの配信不能レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[セキュリティ & コンプライアンス センター](https://protection.office.com)の [メール フロー ダッシュボード](mail-flow-insights-v2.md)の **配信不能レポート** には、組織内のユーザーの配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) で最も検出されたエラー コードが表示されます。 このレポートには NDR の詳細が表示されるので、電子メール配信の問題のトラブルシューティングを行うことができます。

:::image type="content" source="../../media/mfi-non-delivery-report-widget.png" alt-text="セキュリティ & コンプライアンス センターのメール フロー ダッシュボードの配信不能レポート ウィジェット" lightbox="../../media/mfi-non-delivery-report-widget.png":::

## <a name="report-view-for-the-non-delivery-report"></a>配信不能レポートのレポート ビュー

**配信不能レポート** ウィジェットをクリックすると、**配信不能レポート** が表示されます。

既定では、すべてのエラー コードのアクティビティが表示されます。 [ **データの表示]** をクリックすると、ドロップダウンから特定のエラー コードを選択できます。

グラフ内の特定の日の特定の色 (エラー コード) にマウス ポインターを合わせると、エラーのメッセージの合計数が表示されます。

:::image type="content" source="../../media/mfi-non-delivery-report-overview-view.png" alt-text="承認されていないドメイン レポートのレポート ビュー" lightbox="../../media/mfi-non-delivery-report-overview-view.png":::

## <a name="details-table-view-for-the-non-delivery-report"></a>配信不能レポートの詳細テーブル ビュー

レポート ビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **配信不能レポート コード**
- **Count**
- **サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージ ID。

詳細テーブル ビューで [**フィルター]** をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

特定の日付範囲のレポートを 1 人以上の受信者に電子メールで送信するには、[ **ダウンロードの要求**] をクリックします。

テーブル内の行を選択すると、ポップアップが表示され、次の情報が表示されます。

- **Date**
- **配信不能レポート コード**: リンクをクリックすると、特定のエラー コードの原因と解決策の詳細を確認できます。
- **Count**
- **サンプル メッセージ**: [ **サンプル メッセージの表示** ] をクリックすると、影響を受けるメッセージのサンプルの [メッセージ トレース](message-trace-scc.md) 結果を確認できます。

:::image type="content" source="../../media/mfi-non-delivery-report-details-flyout.png" alt-text="配信不能レポートの [詳細] テーブル ビューで行を選択した後の [詳細] ポップアップ" lightbox="../../media/mfi-non-delivery-report-details-flyout.png":::

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
