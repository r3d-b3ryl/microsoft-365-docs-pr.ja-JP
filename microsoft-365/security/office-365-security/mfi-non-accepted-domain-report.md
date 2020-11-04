---
title: メールフローダッシュボードの承認されていないドメインレポート
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
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードで承認されていないドメインレポートを使用して、送信者のドメインが Microsoft 365 で構成されていないオンプレミスの組織からのメッセージを監視する方法を学習できます。
ms.openlocfilehash: 06acacb79c826cb465b3fd28086a7df9d64eabdc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877719"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターの承認されていないドメインレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)の承認されてい **ないドメイン** レポートには、送信者のドメインが Microsoft 365 組織の承認済みドメインとして構成されていないオンプレミスの電子メール組織からのメッセージに関する情報が表示されます。

これらのメッセージが悪意のあるものであることを証明するためのデータがある場合、Microsoft 365 はこれらのメッセージを調整する可能性があります。 そのため、何が起こっているのかを理解し、問題を修正することが重要です。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの承認されていないドメインウィジェット](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>承認されていないドメインレポートのレポートビュー

承認されてい **ないドメイン** ウィジェットのグラフをクリックすると、承認されてい **ないドメイン** レポートに移動します。

既定では、影響を受けるすべてのコネクタのアクティビティが表示されます。 [ **データの表示** ] をクリックすると、ドロップダウンから特定のコネクタを選択できます。

グラフのデータ要素 (日単位) の上にポインターを置くと、そのコネクタの合計メッセージ数が表示されます。

![承認されていないドメインレポートのレポートビュー](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>承認されていないドメインレポートの詳細テーブルビュー

レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **Date**
- **受信コネクタ名**
- **送信元ドメイン**
- **メッセージ数**
- **サンプルメッセージ** : 影響を受けるメッセージのサンプルのメッセージ id。

詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日** を含む日付範囲を指定できます。

特定の日付範囲のレポートに対して1人以上の受信者を電子メールで送信するには、[ **ダウンロードの依頼** ] をクリックします。

表の行を選択すると、次の情報を含むフライアウトが表示されます。

- **Date**
- **受信コネクタ名**
- **送信元ドメイン**
- **メッセージ数**
- **サンプルメッセージ** : [ **サンプルメッセージの表示** ] をクリックすると、影響を受けたメッセージのサンプルの [メッセージの追跡](message-trace-scc.md) 結果が表示されます。

![承認されていないドメインレポートの [詳細] テーブルビューで行を選択した後の詳細ポップアップ](../../media/mfi-non-accepted-domain-report-details-flyout.png)

レポートビューに戻るには、[ **レポートの表示** ] をクリックします。

## <a name="related-topics"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
