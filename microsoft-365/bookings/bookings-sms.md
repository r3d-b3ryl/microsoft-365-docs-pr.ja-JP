---
title: Microsoft Bookings で SMS テキスト通知とリマインダーを構成する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
description: Microsoft Bookings でクライアント、顧客、パートナー向け SMS テキスト通知を構成する方法について説明します。
ms.openlocfilehash: be5d1d93754707be8217c5c3e17ec7d9f158e501
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204841"
---
# <a name="configure-sms-text-notifications-and-reminders-in-microsoft-bookings"></a>Microsoft Bookings で SMS テキスト通知とリマインダーを構成する

Microsoft Bookings では、予定を予約するユーザーに送信する SMS テキスト通知を設定できます。 [Bookings] Web アプリまたは Bookings アプリの [Bookings] で SMS 通知を設定Teams。 出席者、顧客、またはパートナーは、セルフサービスの予約ページで SMS 通知を受け取る方法を選択またはオプトアウトすることもできます。 また、送信者に STOP と返信することで、SMS 通知の **受信** をオプトアウトすることもできます。

SMS 通知には、仮想予約の予定Teams会議リンクが含まれます。

## <a name="before-you-begin"></a>はじめに

出席者、顧客、またはパートナーは、SMS 通知を受け取る前に有効な米国またはカナダの電話番号を必要とします。

## <a name="configure-sms-notification-in-microsoft-bookings"></a>Microsoft Bookings で SMS 通知を構成する

> [!IMPORTANT]
> Microsoft Bookings は、2022 年 2 月 28 日まで、Bookings ライセンスをお持ちのお客様に対して無制限の SMS 通知を受け取ります。 プロモーション期間の終了に近づくにつれて、ライセンス要件に関する追加の詳細が提供されます。 Bookings ライセンスの詳細については、「Bookings ライセンス [」を参照してください](/microsoft-365/bookings/bookings-faq?view=o365-worldwide#who-has-access-to-microsoft-bookings-)。

次の 2 つの方法で、Bookings で SMS 通知を構成できます。

- Bookings Web アプリで、「Bookingsでサービスを提供する内容を定義する」の「テキスト メッセージ通知を有効にする」の手順[に従](define-service-offerings.md)います。

- [予約] アプリの [Teams] で、[予定設定の種類の追加] に移動し、[テキスト メッセージを送信する  >    >  **] を選択します**。

## <a name="tracking-and-metrics-for-sms-notifications"></a>SMS 通知の追跡と指標

> [!NOTE]
> 管理センターで Teamsと予約データTeams表示するには、管理者であるTeams必要があります。

組織の SMS 通知の使用状況に関する主要なデータは、管理センター Teamsできます。 利用状況レポートには、送信日時、配信元番号、メッセージの種類、イベントの種類、配信状態などのデータが含まれます。 プロモーション期間中に SMS 通知テレメトリを使用すると、2022 年 3 月 1 日以降の SMS 通知の予測と予算を支援できます。

1. 管理センター Teams、**仮想アクセスの SMS 通知** です。

2. [レポート **の分析&] ページで、[SMS** 通知の使用状況] を選択します。

    :::image type="content" source="../media/analytics-reporting.png" alt-text="スクリーンショット: SMS テキスト通知管理センターの分析とTeamsページ":::

関連コンテンツ

[Microsoft Bookings](bookings-overview.md)\
[Microsoft Bookings のオン/オフを切り替えます](turn-bookings-on-or-off.md)\
[iOS と Android 用の Microsoft Bookings アプリを取得する](get-bookings-app.md)\
