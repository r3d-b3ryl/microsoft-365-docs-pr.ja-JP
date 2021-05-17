---
title: Microsoft Bookings の情報を報告する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: Bookings アクティビティの 4 か月ビューを表示する方法を確認する
ms.openlocfilehash: ad0a21454cfe28cec521e545e587105e8f8a7454
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887229"
---
# <a name="reporting-info-for-bookings"></a>Bookings のレポート情報

これで、予約カレンダーの 4 か月ビューが TSV ファイルに表示されます。 TSV ファイルには 4 か月分のデータが表示されますが、1 年間で異なる 4 か月の期間を選択できます。

この予定レベルの情報を使用して、Bookings カレンダーを中心に顧客のアクティビティを視覚化できます。 TSV ファイルはタブ区切り値ファイルです。 このようなファイルを表示または編集するには、テキスト エディターやスプレッドシート プログラム (テキスト エディターなど) を使用Excel。

## <a name="see-four-months-of-booking-activity"></a>予約アクティビティの 4 か月を確認する

1. [予約] カレンダー ダッシュボードで **、[TSV として他のデータをエクスポートする] を選択します**。

:::image type="content" source="../media/bookings-activities.png" alt-text="スクリーンショット: 予約アクティビティの 4 か月":::

1. 新しい名前でファイルを保存し、.xls xlsx 形式を指定します。

1. ファイルを開き、予約カレンダーの 4 か月ビューを表示します。

1. レポートの日付を選択し、[エクスポート] を **選択します**。

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="スクリーンショット: 時間範囲を選択し、データを TSV ファイルにエクスポートします。":::

1. ダウンロードしたレポートには、既存のフィールドに加えて、新しい一連のフィールドが含まれています。

レポートには、次のフィールドが含まれます。

 - **日付/時刻**
- **顧客名**
- **顧客メール**
- **顧客電話**
- **顧客の住所**
- **スタッフ**
- **サービス**
- **Location**
- **期間 (分)**
- **イベントの種類**

改善されたレポートには、次のフィールドが含まれます。

- **価格の種類**   サービスの作成時にサービスに設定される既定の価格の種類。
- **価格**   選択した価格の種類に対応する価格。
- **通貨**   ビジネス用に設定された通貨の種類。
- **Cc Attendees**   予約の電子メール通知を受信する受信者。 これは、予約の作成時にTeamsアプリから指定できます。
- **サインアップした出席者数**   グループ予約サービスを予約したユーザーの数。
- **テキスト通知が有効**  ユーザーがテキスト関連の通知携帯ショートメールを受け取るかどうかを指定します。
- **ユーザー設定フィールド**   1 つの予約に関連する質問と回答はすべて、このフィールドに組み合わされます。
- **予約 ID**   これは、グループ サービスの同じ予約を識別するのに役立ちます。
