---
title: メール フローのマップ
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでメール フロー マップを使用して、コネクタを使用したりコネクタを使用せずに組織とメールがどのように流れるのかについて視覚化および追跡する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87a5780bd2485ba6ad3b295c09a30a4d7fc34277
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150562"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター&フロー マップ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

セキュリティ **/コンプライアンス センター** の [](mail-flow-insights-v2.md)メール フロー ダッシュボード [](https://protection.office.com)のメール フロー マップ&、メールが組織を通過する方法に関する洞察が得られる。 この情報を使用して、パターンの学習、異常の特定、発生した問題の修正を行います。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードのメール フロー &ウィジェット](../../media/mfi-mail-flow-map-widget.png)

既定では、ウィジェットはサンキー図と呼ばれるグラフに、前の日からのメール フロー *パターンを表示* します。 左矢印の左矢印と右矢印の右矢印を使用して、さまざまな日の情報 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) を表示できます。 それぞれの異なる色は、異なる受信コネクタまたは送信コネクタ (またはコネクタを使用しない) 上のメール フローを表します。 特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。

## <a name="report-view-for-the-mail-flow-map"></a>メール フロー マップのレポート ビュー

メール フロー マップ **ウィジェットをクリック** すると、メール フロー **マップ レポートにアクセス** できます。

レポート ビューでは、次のグラフを使用できます。

- **Show data for: Overview**: This is basically a larger view of the widget. 特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。

  ![メール フロー マップ レポートの概要ビュー](../../media/mfi-mail-flow-map-report-overview.png)

- **データの表示: 詳細**: このビューには、コネクタと宛先ドメインに関する詳細が表示されます。 上位の送信者と受信者のドメインが一覧表示され、残りは [その他] に **入れらます**。 特定の色とセクションにカーソルを合わせると、メッセージの数が表示されます。

  ![メール フロー マップ レポートの詳細ビュー](../../media/mfi-mail-flow-map-report-detail.png)

If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

関連する分析情報が利用可能な場合は、メール フロー マップの下に表示されます (たとえば、可能なメール ループの分析 [情報を修正します](mfi-mail-loop-insight.md))。

## <a name="details-table-view-for-the-mail-flow-map"></a>メール フロー マップの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **日付**
- **分類**
- **コネクタ/サードパーティのサービス プロバイダー**
- **送信者/受信者ドメイン**
- **メッセージ数**

詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲** を **指定できます**。

行を選択すると、同様の詳細がフライアウトに表示されます。

![メール フロー マップの詳細テーブルからの詳細フライアウト](../../media/mfi-mail-flow-map-view-details-table-details.png)

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="see-also"></a>こちらもご覧ください

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
