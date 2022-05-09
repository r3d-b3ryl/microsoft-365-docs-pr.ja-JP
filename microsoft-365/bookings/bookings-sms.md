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
ms.openlocfilehash: 8183f89a73d3a9fa8573bfaa55935865eeb794dd
ms.sourcegitcommit: 5b321693214e3859f5af8f1774d2a5ff685ab3b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65014960"
---
# <a name="configure-sms-text-notifications-and-reminders-in-microsoft-bookings"></a>Microsoft Bookingsで SMS テキスト通知とリマインダーを構成する

Microsoft Bookingsでは、予定を予約しているユーザーに送信する SMS テキスト通知を設定できます。 Bookings Web アプリまたは TeamsのBookings アプリのBookingsで SMS 通知を設定できます。 出席者、顧客、パートナーは、セルフサービスの予約ページで SMS 通知を受け取ることをオプトインまたはオプトアウトすることもできます。 また、送信者に **STOP** を返信することで、SMS 通知の受信をオプトアウトすることもできます。

SMS 通知には、仮想予約予定のTeams会議リンクが含まれます。

> [!Note]
> Bookings ライセンスをお持ちのお客様には、2022 年 9 月 30 日まで無制限の SMS 通知を提供します。 プロモーション期間の終わりに近づくにつれて、ライセンス要件に関する追加の詳細が提供されます。 プロモーション期間の後に価格の詳細を受け取るには、アカウント チームまたはサポートにお問い合わせください。

## <a name="before-you-begin"></a>開始する前に

出席者、顧客、パートナーは、SMS 通知を受け取る前に、有効な米国またはカナダの電話番号が必要です。

## <a name="configure-sms-notification-in-microsoft-bookings"></a>Microsoft Bookingsで SMS 通知を構成する

BOOKINGSで SMS 通知を構成するには、次の方法があります。

- Bookings Web アプリで、「Bookingsサービスの定義」トピックの **テキスト メッセージ通知を有効にする** 手順 [に](define-service-offerings.md)従います。

- Teamsの Booking アプリで、**設定** > **Appointment typeAdd** **予定の** > 種類に移動し、[**テキスト メッセージの送信**] を選択します。

## <a name="tracking-and-metrics-for-sms-notifications"></a>SMS 通知の追跡とメトリック

> [!NOTE]
> Teams管理センターでTeamsデータとBookingsデータを表示するには、Teams管理者である必要があります。

Teams管理センターでは、組織内の SMS 通知の使用状況に関する重要なデータを追跡できます。 使用状況レポートには、送信された日時、配信元番号、メッセージの種類、イベントの種類、配信状態などのデータが含まれます。 プロモーション期間中に SMS 通知テレメトリを使用すると、2022 年 9 月 30 日以降の SMS 通知の予測と予算を支援できます。

1. Teams管理センターで、**Virtual Visits SMS 通知**。

2. [ **Analytics & レポート** ] ページで、[SMS 通知の使用状況] を選択します。

    :::image type="content" source="../media/analytics-reporting.png" alt-text="スクリーンショット: Teams管理センターの SMS テキスト通知分析とレポート ページ":::

関連コンテンツ

[Microsoft Bookings](bookings-overview.md)\
[Microsoft Bookingsをオンまたはオフにする](turn-bookings-on-or-off.md)\
[iOS と Android 用のMicrosoft Bookings アプリを取得する](get-bookings-app.md)\
