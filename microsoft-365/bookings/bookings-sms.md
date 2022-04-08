---
title: Microsoft Bookingsで SMS テキスト通知とリマインダーを構成する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
description: Microsoft Bookingsのクライアント、顧客、パートナーに対して SMS テキスト通知を構成する方法について説明します。
ms.openlocfilehash: 46f58081bc9df799323c0c5e85253d4593d9c3c7
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64715255"
---
# <a name="configure-sms-text-notifications-and-reminders-in-microsoft-bookings"></a>Microsoft Bookingsで SMS テキスト通知とリマインダーを構成する

> [!NOTE]
> この記事は、最新バージョンのMicrosoft Bookingsを操作するのに役立ちます。 以前のバージョンは、今後数か月で廃止される予定です。

Microsoft Bookingsでは、予定を予約しているユーザーに送信する SMS テキスト通知を設定できます。 Bookings Web アプリまたは TeamsのBookings アプリのBookingsで SMS 通知を設定できます。 出席者、顧客、パートナーは、セルフサービスの予約ページで SMS 通知を受け取ることをオプトインまたはオプトアウトすることもできます。 また、送信者に **STOP** を返信することで、SMS 通知の受信をオプトアウトすることもできます。

SMS 通知には、仮想予約予定のTeams会議リンクが含まれます。

## <a name="before-you-begin"></a>はじめに

出席者、顧客、パートナーは、SMS 通知を受け取る前に、有効な米国またはカナダの電話番号が必要です。

## <a name="configure-sms-notification-in-microsoft-bookings"></a>Microsoft Bookingsで SMS 通知を構成する

BOOKINGSで SMS 通知を構成するには、次の方法があります。

- Bookings Web アプリで、「Bookingsサービスの定義」トピックの **テキスト メッセージ通知を有効にする** 手順 [に](define-service-offerings.md)従います。

- Teamsの Booking アプリで、**設定** > **Appointment typeAdd** **予定の** > 種類に移動し、[**テキスト メッセージの送信**] を選択します。

## <a name="tracking-and-metrics-for-sms-notifications"></a>SMS 通知の追跡とメトリック

> [!NOTE]
> Teams管理センターでTeamsデータとBookingsデータを表示するには、Teams管理者である必要があります。

Teams管理センターでは、組織内の SMS 通知の使用状況に関する重要なデータを追跡できます。 使用状況レポートには、送信された日時、配信元番号、メッセージの種類、イベントの種類、配信状態などのデータが含まれます。 プロモーション期間中に SMS 通知テレメトリを使用すると、2022 年 5 月 1 日以降の SMS 通知の予測と予算を支援できます。

1. Teams管理センターで、**Virtual Visits SMS 通知**。

2. [ **Analytics & レポート** ] ページで、[SMS 通知の使用状況] を選択します。

    :::image type="content" source="../media/analytics-reporting.png" alt-text="スクリーンショット: Teams管理センターの SMS テキスト通知分析とレポート ページ":::

関連コンテンツ

[Microsoft Bookings](bookings-overview.md)\
[Microsoft Bookingsをオンまたはオフにする](turn-bookings-on-or-off.md)\
[iOS と Android 用のMicrosoft Bookings アプリを取得する](get-bookings-app.md)\
