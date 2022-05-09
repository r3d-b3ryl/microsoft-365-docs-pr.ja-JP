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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでメール フロー マップを使用して、コネクタを使用せずに組織との間のメール フローを視覚化し、追跡する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd8df34c9484b7a2b8aa2bdd57d160e22f71d247
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473807"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターのメール フロー マップ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[セキュリティ & コンプライアンス センター](https://protection.office.com)の [[メール フロー] ダッシュボード](mail-flow-insights-v2.md)の [メール **フロー] マップ** は、メールが組織を通過する方法に関する分析情報を提供します。 この情報を使用して、パターンを学習し、異常を特定し、発生した問題を修正することができます。

:::image type="content" source="../../media/mfi-mail-flow-map-widget.png" alt-text="セキュリティ & コンプライアンス センターの [メール フロー] ダッシュボードの [メール フロー マップ] ウィジェット" lightbox="../../media/mfi-mail-flow-map-widget.png":::

既定では、ウィジェットは前日のメール フロー パターンを *Sankey* ダイアグラムと呼ばれるグラフに表示します。 左矢印の左方向 ![を使用できます。](../../media/scc-left-arrow.png) 異なる日の情報を表示するには、右方向矢印と右方向キー ![を押](../../media/scc-right-arrow.png) します。 それぞれの異なる色は、異なる受信コネクタまたは送信コネクタ (またはコネクタを使用しない) 経由のメール フローを表します。 特定の色の上にマウス ポインターを置くと、その種類のコネクタに対するメッセージの数が表示されます。

## <a name="report-view-for-the-mail-flow-map"></a>メール フロー マップのレポート ビュー

**[メール フロー マップ**] ウィジェットをクリックすると、[**メール フロー マップ**] レポートに移動します。

レポート ビューでは、次のグラフを使用できます。

- **データの表示: 概要**: これは基本的にウィジェットの大きなビューです。 特定の色の上にマウス ポインターを置くと、その種類のコネクタに対するメッセージの数が表示されます。

    :::image type="content" source="../../media/mfi-mail-flow-map-report-overview.png" alt-text="メール フロー マップ レポートの [概要] ビュー" lightbox="../../media/mfi-mail-flow-map-report-overview.png":::

- **データの表示: 詳細**: このビューには、コネクタと宛先ドメインに関する詳細が表示されます。 上位の送信者ドメインと受信者ドメインが一覧表示され、残りは **[その他]** に配置されます。 特定の色とセクションにマウス ポインターを合わせると、メッセージの数が表示されます。

    :::image type="content" source="../../media/mfi-mail-flow-map-report-detail.png" alt-text="メール フロー マップ レポートの詳細ビュー" lightbox="../../media/mfi-mail-flow-map-report-detail.png":::

レポート ビューで [**フィルター]** をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

特定の日付範囲のレポートを 1 人以上の受信者に電子メールで送信するには、[ **ダウンロードの要求**] をクリックします。

使用可能な場合は、関連する分析情報がメール フロー マップの下に表示されます (たとえば、[ [Fix possible mail loop insight]\(可能なメール ループ分析情報を修正する\](mfi-mail-loop-insight.md))

## <a name="details-table-view-for-the-mail-flow-map"></a>メール フロー マップの詳細テーブル ビュー

レポート ビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **[カテゴリ]**
- **コネクタ/サード パーティのサービス プロバイダー**
- **Sender/Recipient ドメイン**
- **メッセージ数**

詳細テーブル ビューで [**フィルター]** をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

行を選択すると、同様の詳細がポップアップに表示されます。

:::image type="content" source="../../media/mfi-mail-flow-map-view-details-table-details.png" alt-text="メール フロー マップの詳細テーブルからの詳細ポップアップ" lightbox="../../media/mfi-mail-flow-map-view-details-table-details.png":::

特定の日付範囲のレポートを 1 人以上の受信者に電子メールで送信するには、[ **ダウンロードの要求**] をクリックします。

レポート ビューに戻るには、[レポートの **表示**] をクリックします。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
