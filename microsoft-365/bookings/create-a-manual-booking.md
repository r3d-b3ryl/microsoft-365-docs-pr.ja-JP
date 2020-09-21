---
title: 手動予約を作成する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: 次の手順に従って、Microsoft の予約アプリを使用して予定を作成し、従業員を割り当てます。
ms.openlocfilehash: dffc63b1f638c551e40d22852b1ba6a73c5be869
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962563"
---
# <a name="create-a-manual-booking"></a><span data-ttu-id="3540b-103">手動予約を作成する</span><span class="sxs-lookup"><span data-stu-id="3540b-103">Create a manual booking</span></span>

<span data-ttu-id="3540b-104">予約のスケジュールとスタッフの割り当てには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3540b-104">Bookings can be scheduled and staffed in two different ways.</span></span> <span data-ttu-id="3540b-105">最初の方法は、お客様が自分の web サイトに追加したスタンドアロンの予約ページまたは組み込み予約ページを使用している場合です。</span><span class="sxs-lookup"><span data-stu-id="3540b-105">The first way is by the customer using a standalone booking page or an embedded booking page that you add to your website.</span></span> <span data-ttu-id="3540b-106">もう1つの方法は、顧客が予定を呼び出すときなど、自分または自分の従業員が手動で予約を入力できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="3540b-106">The other way is for you or one of your employees to enter the bookings manually, such as when a customer calls for an appointment.</span></span> <span data-ttu-id="3540b-107">この記事は手動のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3540b-107">This article covers the manual scenario.</span></span>

1. <span data-ttu-id="3540b-108">Microsoft 365 で、アプリ起動ツールを選択し、[ **予約**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3540b-108">In Microsoft 365, select the App launcher, and then select **Bookings**.</span></span>

   ![アプリ起動ツールでの予約の画像](../media/bookings-applauncher.png)

1. <span data-ttu-id="3540b-110">In the navigation pane, select **Calendar** \> **New booking**.</span><span class="sxs-lookup"><span data-stu-id="3540b-110">In the navigation pane, select **Calendar** \> **New booking**.</span></span>

   ![新しい予約 UI の画像](../media/bookings-newbooking.png)

1. <span data-ttu-id="3540b-112">提供するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="3540b-112">Select the service to be provided.</span></span> <span data-ttu-id="3540b-113">サービスのセットアップの手順については [、「Microsoft 予約のサービスオファーリングの定義](define-service-offerings.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3540b-113">See [Define your service offerings in Microsoft Bookings](define-service-offerings.md) for service setup instructions.</span></span>

1. <span data-ttu-id="3540b-114">顧客情報 (名前、メール アドレス、電話番号などの関連情報) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3540b-114">Enter the customer information, including name, email address, phone number, and other relevant details.</span></span>

1. <span data-ttu-id="3540b-115">サービスを提供するスタッフ メンバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="3540b-115">Select the staff member to provide the service.</span></span> <span data-ttu-id="3540b-116">表示されるスタッフ メンバー リストは、[サービス] ページでセットアップした内容によって決まります。</span><span class="sxs-lookup"><span data-stu-id="3540b-116">The list of staff members shown is based on what you set up on the services page.</span></span>

   ![スタッフリストの UI の画像](../media/bookings-staff-list.png)

1. <span data-ttu-id="3540b-p104">サービスの詳細情報 (日付、時刻、場所などの関連情報) を入力します。顧客の有効なメール アドレスを入力すると、[ **保存**] ボタンが [ **送信**] に変わり、確認が顧客に送信されるという注意が表示されます。顧客の確認には、予定表に追加する予定に関する添付ファイルも含まれます。選んだスタッフ メンバーにも、予定情報が記載された会議の招待が送信されるので、スタッフも自分の予定表に予定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3540b-p104">Enter the service details, including date, time, location, and other relevant information. Once you enter a valid email address for the customer, the **Save** button will change to **Send**, and you'll see a note telling you that a confirmation will be sent to the customer. The customer confirmation includes an attachment for them to add to their calendar. Selected staff members will also receive meeting invitations with the appointment information so they can add it to their personal calendars.</span></span>

1. <span data-ttu-id="3540b-122">[ **メール アラームを追加する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3540b-122">Select **Add an email reminder**.</span></span>

1. <span data-ttu-id="3540b-123">アラームを送信する時期、送信場所 (**顧客**、 **スタッフ**、 **すべての出席者**)、およびアラームメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="3540b-123">Specify when the reminder should be sent, where it should be sent (**Customer**, **Staff**, **All attendees**), and what the reminder message should be.</span></span>

1. <span data-ttu-id="3540b-124">Select **Save** \> **Send**.</span><span class="sxs-lookup"><span data-stu-id="3540b-124">Select **Save** \> **Send**.</span></span>

   <span data-ttu-id="3540b-125">お客様が受け取る通知のメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3540b-125">Here's an example email of the reminder your customer will receive:</span></span>

:::image type="content" source="../media/bookings-confirmed-email.png" alt-text="スクリーンショット: 手動による予約からの確認メールの例":::