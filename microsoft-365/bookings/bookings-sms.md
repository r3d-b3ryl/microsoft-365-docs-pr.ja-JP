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
ms.openlocfilehash: 2aac74b89e5d83c4dec0840a7bb423a271e5eb5d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318025"
---
# <a name="configure-sms-text-notifications-and-reminders-in-microsoft-bookings"></a>Microsoft Bookings で SMS テキスト通知とリマインダーを構成する

Microsoft Bookings では、予定を予約するユーザーに送信する SMS テキスト通知を設定できます。 [Bookings] Web アプリまたは Bookings アプリの [Bookings] で SMS 通知を設定Teams。 出席者、顧客、またはパートナーは、セルフサービスの予約ページで SMS 通知を受け取る方法を選択またはオプトアウトすることもできます。 また、送信者に STOP と返信することで、SMS 通知の **受信** をオプトアウトすることもできます。

SMS 通知には、仮想予約の予定Teams会議リンクが含まれます。

## <a name="before-you-begin"></a>始める前に

出席者、顧客、またはパートナーは、SMS 通知を受け取る前に有効な米国またはカナダの電話番号を必要とします。

## <a name="configure-sms-notification-in-microsoft-bookings"></a>Microsoft Bookings で SMS 通知を構成する

> [!IMPORTANT]
> Microsoft Bookings は、2022 年 4 月 30 日まで、Bookings ライセンスをお持ちのお客様に対して無制限の SMS 通知を受け取ります。 プロモーション期間の終了に近づくにつれて、ライセンス要件に関する追加の詳細が提供されます。

次の 2 つの方法で、Bookings で SMS 通知を構成できます。

- Bookings Web アプリで、「Bookings でサービスを提供する内容を定義する」の「テキスト メッセージ通知を有効にする」の手順[に従](define-service-offerings.md)います。

- [予約] アプリの [Teams]  >  で、[設定 **予定** > の種類を追加する] に移動し、[テキスト メッセージを送信 **する] を選択します**。

## <a name="tracking-and-metrics-for-sms-notifications"></a>SMS 通知の追跡と指標

> [!NOTE]
> 管理センターで予約Teamsと予約Teamsを表示するには、管理者Teams必要があります。

組織の SMS 通知の使用状況に関する主要なデータは、管理センター Teams追跡できます。 利用状況レポートには、送信日時、配信元番号、メッセージの種類、イベントの種類、配信状態などのデータが含まれます。 プロモーション期間中に SMS 通知テレメトリを使用すると、2022 年 5 月 1 日以降の SMS 通知の予測と予算を支援できます。

1. 管理センター Teams、**仮想アクセスの SMS 通知。**

2. [レポート **の分析&] ページで、[** SMS 通知の使用状況] を選択します。

    :::image type="content" source="../media/analytics-reporting.png" alt-text="スクリーンショット: SMS テキスト通知管理センターの分析とTeamsページ":::

関連コンテンツ

[Microsoft Bookings](bookings-overview.md)\
[Microsoft Bookings のオン/オフを切り替えます](turn-bookings-on-or-off.md)\
[iOS と Android 用の Microsoft Bookings アプリを取得する](get-bookings-app.md)\
