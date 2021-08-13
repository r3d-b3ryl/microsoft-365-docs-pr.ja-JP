---
title: 予約を作成する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: 次の手順に従って予定を作成し、Microsoft Bookings アプリを通じて従業員を割り当てる。
ms.openlocfilehash: 3ac35cceea7413f6f4634df6474df2d07258debb1bdadb62893f443dc6c2df7b
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53803946"
---
# <a name="create-a-manual-booking"></a>予約を作成する

予約のスケジュールとスタッフの割り当てには 2 つの方法があります。 最初の方法は、スタンドアロンの予約ページまたは Web サイトに追加する埋め込み予約ページを使用する顧客です。 もう 1 つは、顧客から予約の電話がかかってきた場合のように管理者または従業員が予約を手動で入力する方法です。 この記事は手動のシナリオについて説明します。

1. [Microsoft 365] で[アプリ 起動ツール] を選択し、[予約]**を選択します**。

   ![アプリ 起動ツールの予約のイメージ](../media/bookings-applauncher.png)

1. In the navigation pane, select **Calendar** \> **New booking**.

   ![新しい予約 UI のイメージ](../media/bookings-newbooking.png)

1. 提供するサービスを選びます。 「 [サービスのセットアップ手順については、Microsoft Bookings で](define-service-offerings.md) サービス提供を定義する」を参照してください。

1. 顧客情報 (名前、メール アドレス、電話番号などの関連情報) を入力します。

1. サービスを提供するスタッフ メンバーを選びます。表示されるスタッフ メンバー リストは、[サービス] ページでセットアップした内容によって決まります。

   ![スタッフ リスト UI のイメージ](../media/bookings-staff-list.png)

1. サービスの詳細情報 (日付、時刻、場所などの関連情報) を入力します。顧客の有効なメール アドレスを入力すると、[ **保存**] ボタンが [ **送信**] に変わり、確認が顧客に送信されるという注意が表示されます。顧客の確認には、予定表に追加する予定に関する添付ファイルも含まれます。選んだスタッフ メンバーにも、予定情報が記載された会議の招待が送信されるので、スタッフも自分の予定表に予定を追加できます。

1. [ **メール アラームを追加する**] を選びます。

1. アラームをいつ送信する必要があるのか、どこに送信する必要があるのかを指定します (**顧客**、**スタッフ**、すべての出席者)、リマインダー メッセージの設定方法を指定します。

1. Select **Save** \> **Send**.

   顧客が受け取るリマインダーの電子メールの例を次に示します。

:::image type="content" source="../media/bookings-confirmed-email.png" alt-text="スクリーンショット: 手動予約からの確認メールの例":::