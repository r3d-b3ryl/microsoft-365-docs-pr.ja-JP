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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでメール フロー マップを使用して、コネクタを使用したりコネクタを使用せずに組織とメールのフローを視覚化したり追跡したりする方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f507f7f01999492d17e168a2a56da906bfcb52d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290587"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター&フロー マップ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

セキュリティ **/コンプライアンス センター** の [](mail-flow-insights-v2.md)メール フロー ダッシュボード [](https://protection.office.com)のメール フロー マップ&、メールが組織を通過する方法に関する洞察が得られる。 この情報を使用して、パターンの学習、異常の特定、発生した問題の修正を行います。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードのメール フロー &ウィジェット](../../media/mfi-mail-flow-map-widget.png)

既定では、ウィジェットは、サンキー図と呼ばれるグラフに、前の日からのメール フロー *パターンを表示* します。 左矢印の左矢印と右矢印の右矢印を使用して、さまざまな日の情報 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) を表示できます。 それぞれの異なる色は、異なる受信コネクタまたは送信コネクタ (またはコネクタを使用しない) 上のメール フローを表します。 特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。

## <a name="report-view-for-the-mail-flow-map"></a>メール フロー マップのレポート ビュー

メール フロー マップ **ウィジェットをクリック** すると、メール フロー **マップ レポートにアクセス** できます。

レポート ビューでは、次のグラフを使用できます。

- **Show data for: Overview**: This is basically a larger view of the widget. 特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。

  ![メール フロー マップ レポートの概要ビュー](../../media/mfi-mail-flow-map-report-overview.png)

- **データの表示: 詳細**: このビューには、コネクタと宛先ドメインに関する詳細が表示されます。 上位の送信者と受信者のドメインが一覧表示され、残りは [その他] に **入れらます**。 特定の色とセクションにカーソルを合わせると、メッセージの数が表示されます。

  ![メール フロー マップ レポートの詳細ビュー](../../media/mfi-mail-flow-map-report-detail.png)

レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲****を指定できます**。

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

関連する分析情報が使用可能な場合は、メール フロー マップの下に表示されます (たとえば、可能なメール ループの分析 [情報を修正します](mfi-mail-loop-insight.md))。

## <a name="details-table-view-for-the-mail-flow-map"></a>メール フロー マップの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **日付**
- **カテゴリ**
- **コネクタ/サードパーティのサービス プロバイダー**
- **送信者/受信者ドメイン**
- **メッセージ数**

詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。

行を選択すると、同様の詳細がフライアウトに表示されます。

![メール フロー マップの詳細テーブルからの詳細フライアウト](../../media/mfi-mail-flow-map-view-details-table-details.png)

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
