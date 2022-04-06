---
title: メール フロー ダッシュボードの配信不可レポート
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで配信不可の詳細レポートを使用して、組織内の送信者からの配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も頻繁に発生するエラー コードを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bc408f6bb28b11e77c49755b888c44e0ea4d9f57
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473741"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターの配信&レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[セキュリティ &](https://protection.office.com) コンプライアンス センターのメール フロー [](mail-flow-insights-v2.md) ダッシュボードの配信不可レポートには、組織内のユーザーの配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) で最も発生したエラー コードが表示されます。 このレポートには、メール配信の問題をトラブルシューティングするための、NDRs の詳細が表示されます。

:::image type="content" source="../../media/mfi-non-delivery-report-widget.png" alt-text="セキュリティ 管理コンプライアンス センターのメール フロー ダッシュボードの配信&ウィジェット" lightbox="../../media/mfi-non-delivery-report-widget.png":::

## <a name="report-view-for-the-non-delivery-report"></a>配信不可レポートのレポート ビュー

[配信不可レポート **] ウィジェットをクリック** すると、配信不可レポート **が表示されます**。

既定では、すべてのエラー コードのアクティビティが表示されます。 [データの表示 **] をクリックすると**、ドロップダウンから特定のエラー コードを選択できます。

グラフ内の特定の日に特定の色 (エラー コード) にカーソルを合わせると、エラーのメッセージの総数が表示されます。

:::image type="content" source="../../media/mfi-non-delivery-report-overview-view.png" alt-text="[非承諾ドメイン] レポートの [レポート] ビュー" lightbox="../../media/mfi-non-delivery-report-overview-view.png":::

## <a name="details-table-view-for-the-non-delivery-report"></a>配信不可レポートの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **配信不可レポート コード**
- **Count**
- **サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージの ID です。

詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲** を **指定できます**。

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

テーブル内の行を選択すると、次の情報を含むフライアウトが表示されます。

- **Date**
- **配信不可レポート コード**: リンクをクリックすると、特定のエラー コードの原因と解決策の詳細を確認できます。
- **Count**
- **サンプル メッセージ**: [サンプル メッセージの **表示] を** クリックすると [](message-trace-scc.md)、影響を受けるメッセージのサンプルのメッセージ トレース結果を確認できます。


:::image type="content" source="../../media/mfi-non-delivery-report-details-flyout.png" alt-text="[配信不可] レポートの [詳細] テーブル ビューで行を選択した後の詳細フライアウト" lightbox="../../media/mfi-non-delivery-report-details-flyout.png":::

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、「Security [& コンプライアンス センター」を参照してください](mail-flow-insights-v2.md)。
