---
title: メール フロー ダッシュボードの承認されていないドメイン レポート
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
description: 管理者は、セキュリティ & コンプライアンス センターの [メール フロー] ダッシュボードの [非承認済みドメイン] レポートを使用して、送信者のドメインがMicrosoft 365で構成されていないオンプレミス組織からのメッセージを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f16dfbafa12080058cd1784120e4bc2157e0cff
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470837"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターの承認されていないドメイン レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[セキュリティ & コンプライアンス センター](https://protection.office.com)の [[メール フロー] ダッシュボード](mail-flow-insights-v2.md)の **[承認されていないドメイン**] レポートには、送信者のドメインがMicrosoft 365組織内の承認済みドメインとして構成されていないオンプレミスの電子メール組織からのメッセージに関する情報が表示されます。

これらのメッセージの意図が悪意のあることを証明するデータがある場合、Microsoft 365はこれらのメッセージを調整する可能性があります。 したがって、何が起こっているかを理解し、問題を解決することが重要です。

:::image type="content" source="../../media/mfi-non-accepted-domain-report-widget.png" alt-text="セキュリティ & コンプライアンス センターの [メール フロー] ダッシュボードの [非承認済みドメイン] ウィジェット" lightbox="../../media/mfi-non-accepted-domain-report-widget.png":::

## <a name="report-view-for-the-non-accepted-domain-report"></a>承認されていないドメイン レポートのレポート ビュー

**[非承認済みドメイン**] ウィジェットのグラフをクリックすると、承認済み **ドメイン以外のレポートに** アクセスできます。

既定では、影響を受けるすべてのコネクタのアクティビティが表示されます。 [ **データの表示**] をクリックすると、ドロップダウンから特定のコネクタを選択できます。

グラフ内のデータ ポイント (日) にマウス ポインターを合わせると、コネクタのメッセージの合計数が表示されます。

:::image type="content" source="../../media/mfi-non-accepted-domain-report-overview-view.png" alt-text="承認されていないドメイン レポートのレポート ビュー" lightbox="../../media/mfi-non-accepted-domain-report-overview-view.png":::

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>[許可されていないドメイン] レポートの詳細テーブル ビュー

レポート ビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **受信コネクタ名**
- **送信元ドメイン**
- **メッセージ数**
- **サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージ ID。

詳細テーブル ビューで [**フィルター]** をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

特定の日付範囲のレポートを 1 人以上の受信者に電子メールで送信するには、[ **ダウンロードの要求**] をクリックします。

テーブル内の行を選択すると、ポップアップが表示され、次の情報が表示されます。

- **Date**
- **受信コネクタ名**
- **送信元ドメイン**
- **メッセージ数**
- **サンプル メッセージ**: [ **サンプル メッセージの表示** ] をクリックすると、影響を受けるメッセージのサンプルの [メッセージ トレース](message-trace-scc.md) 結果を確認できます。

:::image type="content" source="../../media/mfi-non-accepted-domain-report-details-flyout.png" alt-text="[許可されていないドメイン] レポートの [詳細] テーブル ビューで行を選択した後の [詳細] ポップアップ" lightbox="../../media/mfi-non-accepted-domain-report-details-flyout.png":::

レポート ビューに戻るには、[レポートの **表示**] をクリックします。

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
