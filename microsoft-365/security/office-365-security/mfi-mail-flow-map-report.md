---
title: メール フローのマップ
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでメール フロー マップを使用して、コネクタを使用してコネクタを使用せずに組織と組織間のメール フローを視覚化および追跡する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd8df34c9484b7a2b8aa2bdd57d160e22f71d247
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473807"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターのメール フロー &マップ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティ **コンプライアンス センターの** [メール [](mail-flow-insights-v2.md) フロー] ダッシュボード&メール [](https://protection.office.com) フロー マップは、組織のメールフローに関する分析情報を提供します。 この情報を使用して、パターンの学習、異常の特定、発生した問題の修正を行います。

:::image type="content" source="../../media/mfi-mail-flow-map-widget.png" alt-text="セキュリティ センター コンプライアンス センターのメール フロー ダッシュボードのメール フロー マップ &ウィジェット" lightbox="../../media/mfi-mail-flow-map-widget.png":::

既定では、ウィジェットには、サンキー図と呼ばれるグラフに、前の日のメール フロー *パターンが表示* されます。 左矢印左矢印を ![使用できます。](../../media/scc-left-arrow.png) 右矢印 右 ![矢印を使用](../../media/scc-right-arrow.png) して、異なる日の情報を表示します。 各異なる色は、異なる受信コネクタまたは送信コネクタ (またはコネクタを使用しない) 上のメール フローを表します。 特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。

## <a name="report-view-for-the-mail-flow-map"></a>メール フロー マップのレポート ビュー

メール フロー マップ **ウィジェットをクリックすると** 、メール フロー マップ **レポートにアクセス** できます。

レポート ビューでは、次のグラフを使用できます。

- **[データの表示: 概要**]: これは基本的にウィジェットのより大きなビューです。 特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。

    :::image type="content" source="../../media/mfi-mail-flow-map-report-overview.png" alt-text="メール フロー マップ レポートの概要ビュー" lightbox="../../media/mfi-mail-flow-map-report-overview.png":::

- **データの表示: 詳細**: このビューには、コネクタと宛先ドメインに関する詳細が表示されます。 上位の送信者と受信者のドメインが一覧表示され、残りは [その他] に設定 **されます**。 特定の色とセクションにカーソルを合わせると、メッセージの数が表示されます。

    :::image type="content" source="../../media/mfi-mail-flow-map-report-detail.png" alt-text="メール フロー マップ レポートの詳細ビュー" lightbox="../../media/mfi-mail-flow-map-report-detail.png":::

レポート ビューで **[フィルター]** をクリックすると、開始日と終了日で日付 **範囲****を指定できます**。

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

メール フロー マップが利用可能な場合は、関連する分析情報がメール フロー マップの下に表示されます (たとえば、可能なメール ループ分析情報 [の修正](mfi-mail-loop-insight.md)など)。

## <a name="details-table-view-for-the-mail-flow-map"></a>メール フロー マップの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **[カテゴリ]**
- **コネクタ/サードパーティ のサービス プロバイダー**
- **送信者/受信者ドメイン**
- **メッセージ数**

詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲** を **指定できます**。

行を選択すると、同様の詳細がフライアウトに表示されます。

:::image type="content" source="../../media/mfi-mail-flow-map-view-details-table-details.png" alt-text="メール フロー マップの詳細テーブルからの詳細フライアウト" lightbox="../../media/mfi-mail-flow-map-view-details-table-details.png":::

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、「Security [& コンプライアンス センター」を参照してください](mail-flow-insights-v2.md)。
