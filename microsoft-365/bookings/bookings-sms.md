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
ms.openlocfilehash: 5e340aafbbf88ab1c3747aa87ce27ed62ecd3cad
ms.sourcegitcommit: ebaa70d0da4a600efe52b5008eaddb511d36df8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66687720"
---
# <a name="configure-sms-text-notifications-and-reminders-in-microsoft-bookings"></a>Microsoft Bookingsで SMS テキスト通知とリマインダーを構成する

Microsoft Bookingsでは、予定を予約しているユーザーに送信する SMS テキスト通知を設定できます。 Bookings Web アプリまたは Teams の Bookings アプリで SMS 通知を設定できます。 出席者、顧客、パートナーは、セルフサービスの予約ページで SMS 通知を受け取ることをオプトインまたはオプトアウトすることもできます。 また、送信者に **STOP** を返信することで、SMS 通知の受信をオプトアウトすることもできます。

SMS 通知には、仮想予約の予定の Teams 会議リンクが含まれます。

> [!Note]
> Bookings ライセンスをお持ちのお客様向けに、2022 年 9 月 30 日まで無制限の SMS 通知を提供します。 プロモーション期間の終わりに近づくにつれて、ライセンス要件に関する追加の詳細が提供されます。 プロモーション期間の後に価格の詳細を受け取るには、アカウント チームまたはサポートにお問い合わせください。

## <a name="before-you-begin"></a>はじめに

SMS 通知を受け取る前に、出席者、顧客、パートナーに有効な米国、カナダ、または英国の電話番号が必要です。

## <a name="configure-sms-notification-in-microsoft-bookings"></a>Microsoft Bookingsで SMS 通知を構成する

Bookings では、次の方法で SMS 通知を構成できます。

- Bookings Web アプリで、「[Bookings でサービスオファリングを定義](define-service-offerings.md)する」トピックの **テキスト メッセージ通知を有効にする** 手順に従います。

- Teams の Booking アプリで、[ **設定] 予定** > **の種類 [予定の種類** > **の追加** ] に移動し、[ **テキスト メッセージの送信**] を選択します。

## <a name="tracking-and-metrics-for-sms-notifications"></a>SMS 通知の追跡とメトリック

> [!NOTE]
> Teams 管理センターで Teams と Bookings のデータを表示するには、Teams 管理者である必要があります。

Teams 管理センターでは、組織内の SMS 通知の使用状況に関する重要なデータを追跡できます。 使用状況レポートには、送信された日時、配信元番号、メッセージの種類、イベントの種類、配信状態などのデータが含まれます。 プロモーション期間中に SMS 通知テレメトリを使用すると、2022 年 9 月 30 日以降の SMS 通知の予測と予算を支援できます。

1. Teams 管理センターの **Virtual Visits SMS 通知**。

2. [ **Analytics & レポート** ] ページで、[SMS 通知の使用状況] を選択します。

    :::image type="content" source="../media/analytics-reporting.png" alt-text="スクリーンショット: Teams 管理センターの SMS テキスト通知分析とレポート ページ":::

関連コンテンツ

[Microsoft Bookings](bookings-overview.md)\
[Microsoft Bookingsをオンまたはオフにする](turn-bookings-on-or-off.md)\
[iOS と Android 用のMicrosoft Bookings アプリを取得する](get-bookings-app.md)\
