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
# <a name="reporting-info-for-bookings"></a><span data-ttu-id="cc603-103">Bookings のレポート情報</span><span class="sxs-lookup"><span data-stu-id="cc603-103">Reporting info for Bookings</span></span>

<span data-ttu-id="cc603-104">これで、予約カレンダーの 4 か月ビューが TSV ファイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc603-104">You can now see a four month view of your Bookings calendar in a TSV file.</span></span> <span data-ttu-id="cc603-105">TSV ファイルには 4 か月分のデータが表示されますが、1 年間で異なる 4 か月の期間を選択できます。</span><span class="sxs-lookup"><span data-stu-id="cc603-105">The TSV file will show you four months of data, but you can select different four month periods over the course of a year.</span></span>

<span data-ttu-id="cc603-106">この予定レベルの情報を使用して、Bookings カレンダーを中心に顧客のアクティビティを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="cc603-106">This appointment level information can be used to visualize the customer activity around your Bookings calendar.</span></span> <span data-ttu-id="cc603-107">TSV ファイルはタブ区切り値ファイルです。</span><span class="sxs-lookup"><span data-stu-id="cc603-107">TSV files are tab separated value files.</span></span> <span data-ttu-id="cc603-108">このようなファイルを表示または編集するには、テキスト エディターやスプレッドシート プログラム (テキスト エディターなど) を使用Excel。</span><span class="sxs-lookup"><span data-stu-id="cc603-108">You can view or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>

## <a name="see-four-months-of-booking-activity"></a><span data-ttu-id="cc603-109">予約アクティビティの 4 か月を確認する</span><span class="sxs-lookup"><span data-stu-id="cc603-109">See four months of Booking activity</span></span>

1. <span data-ttu-id="cc603-110">[予約] カレンダー ダッシュボードで **、[TSV として他のデータをエクスポートする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc603-110">On the Bookings calendar dashboard, select **Export more data as TSV**.</span></span>

:::image type="content" source="../media/bookings-activities.png" alt-text="スクリーンショット: 予約アクティビティの 4 か月":::

1. <span data-ttu-id="cc603-112">新しい名前でファイルを保存し、.xls xlsx 形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc603-112">Save the file with a new name, and specify .xls or xlsx format.</span></span>

1. <span data-ttu-id="cc603-113">ファイルを開き、予約カレンダーの 4 か月ビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="cc603-113">Open the file to see the four month view of your Bookings calendar.</span></span>

1. <span data-ttu-id="cc603-114">レポートの日付を選択し、[エクスポート] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc603-114">Choose the date for your report and select **Export**.</span></span>

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="スクリーンショット: 時間範囲を選択し、データを TSV ファイルにエクスポートします。":::

1. <span data-ttu-id="cc603-116">ダウンロードしたレポートには、既存のフィールドに加えて、新しい一連のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc603-116">The downloaded report contains a new set of fields in addition to the existing fields.</span></span>

<span data-ttu-id="cc603-117">レポートには、次のフィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc603-117">The report includes the following fields.</span></span>

 - <span data-ttu-id="cc603-118">**日付/時刻**</span><span class="sxs-lookup"><span data-stu-id="cc603-118">**Date & Time**</span></span>
- <span data-ttu-id="cc603-119">**顧客名**</span><span class="sxs-lookup"><span data-stu-id="cc603-119">**Customer Name**</span></span>
- <span data-ttu-id="cc603-120">**顧客メール**</span><span class="sxs-lookup"><span data-stu-id="cc603-120">**Customer Email**</span></span>
- <span data-ttu-id="cc603-121">**顧客電話**</span><span class="sxs-lookup"><span data-stu-id="cc603-121">**Customer Phone**</span></span>
- <span data-ttu-id="cc603-122">**顧客の住所**</span><span class="sxs-lookup"><span data-stu-id="cc603-122">**Customer Address**</span></span>
- <span data-ttu-id="cc603-123">**スタッフ**</span><span class="sxs-lookup"><span data-stu-id="cc603-123">**Staff**</span></span>
- <span data-ttu-id="cc603-124">**サービス**</span><span class="sxs-lookup"><span data-stu-id="cc603-124">**Service**</span></span>
- <span data-ttu-id="cc603-125">**Location**</span><span class="sxs-lookup"><span data-stu-id="cc603-125">**Location**</span></span>
- <span data-ttu-id="cc603-126">**期間 (分)**</span><span class="sxs-lookup"><span data-stu-id="cc603-126">**Duration (minutes)**</span></span>
- <span data-ttu-id="cc603-127">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="cc603-127">**Event Type**</span></span>

<span data-ttu-id="cc603-128">改善されたレポートには、次のフィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc603-128">The improved report now contains the following fields.</span></span>

- <span data-ttu-id="cc603-129">**価格の種類**   サービスの作成時にサービスに設定される既定の価格の種類。</span><span class="sxs-lookup"><span data-stu-id="cc603-129">**Pricing Type**   Default pricing type set for a service when creating the service.</span></span>
- <span data-ttu-id="cc603-130">**価格**   選択した価格の種類に対応する価格。</span><span class="sxs-lookup"><span data-stu-id="cc603-130">**Price**   Price corresponding to the pricing type chosen.</span></span>
- <span data-ttu-id="cc603-131">**通貨**   ビジネス用に設定された通貨の種類。</span><span class="sxs-lookup"><span data-stu-id="cc603-131">**Currency**   Currency type set for a business.</span></span>
- <span data-ttu-id="cc603-132">**Cc Attendees**   予約の電子メール通知を受信する受信者。</span><span class="sxs-lookup"><span data-stu-id="cc603-132">**Cc Attendees**   The recipients who will be receiving the email notifications for a booking.</span></span> <span data-ttu-id="cc603-133">これは、予約の作成時にTeamsアプリから指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc603-133">This can be specified from the Teams app when creating a booking.</span></span>
- <span data-ttu-id="cc603-134">**サインアップした出席者数**   グループ予約サービスを予約したユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="cc603-134">**Signed Up Attendees Count**   How many customers booked a group booking service.</span></span>
- <span data-ttu-id="cc603-135">**テキスト通知が有効**  ユーザーがテキスト関連の通知携帯ショートメールを受け取るかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc603-135">**Text Notifications Enabled**   Whether customers can receive SMS text-related notifications.</span></span>
- <span data-ttu-id="cc603-136">**ユーザー設定フィールド**   1 つの予約に関連する質問と回答はすべて、このフィールドに組み合わされます。</span><span class="sxs-lookup"><span data-stu-id="cc603-136">**Custom Fields**   All the questions and answers related to a single booking are combined in this field.</span></span>
- <span data-ttu-id="cc603-137">**予約 ID**   これは、グループ サービスの同じ予約を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cc603-137">**Booking ID**   This is helpful to identify the same bookings of a group service.</span></span>
