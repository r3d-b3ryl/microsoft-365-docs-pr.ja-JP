---
title: メールフローダッシュボードの配信不能レポート
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある配信不能レポート (Ndr またはバウンスメッセージとも呼ばれる) で、組織内の送信者に対して発生する可能性の高いエラーコードを監視する方法について説明します。
ms.openlocfilehash: 4967b3b5c294566e46bbc715dd6702c23d618105
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877683"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターの配信不能レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)の **配信不能レポート** は、組織内のユーザーの配信不能レポート (ndr またはバウンスメッセージとも呼ばれる) で最も発生したエラーコードを示しています。 このレポートには、メール配信の問題のトラブルシューティングに使用できる Ndr の詳細が表示されます。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの配信不能レポートウィジェット](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>配信不能レポートのレポートビュー

**配信不能レポート** ウィジェットをクリックすると、 **配信不能レポート** に移動します。

既定では、すべてのエラーコードのアクティビティが表示されます。 [ **データの表示** ] をクリックすると、ドロップダウンから特定のエラーコードを選択できます。

グラフの特定の日の特定の色 (エラーコード) の上にカーソルを置くと、エラーが発生したメッセージの合計数が表示されます。

![承認されていないドメインレポートのレポートビュー](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>配信不能レポートの詳細表ビュー

レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **配信不能レポートのコード**
- **Count**
- **サンプルメッセージ** : 影響を受けるメッセージのサンプルのメッセージ id。

詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日** を含む日付範囲を指定できます。

特定の日付範囲のレポートに対して1人以上の受信者を電子メールで送信するには、[ **ダウンロードの依頼** ] をクリックします。

表の行を選択すると、次の情報を含むフライアウトが表示されます。

- **Date**
- **配信不能レポートコード** : 特定のエラーコードの原因と解決方法の詳細については、リンクをクリックして確認できます。
- **Count**
- **サンプルメッセージ** : [ **サンプルメッセージの表示** ] をクリックすると、影響を受けたメッセージのサンプルの [メッセージの追跡](message-trace-scc.md) 結果が表示されます。

![配信不能レポートの [詳細] テーブルビューで行を選択した後の詳細ポップアップ](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
