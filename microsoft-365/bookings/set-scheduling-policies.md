---
title: スケジュール ポリシーを設定する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4b2c84ec-64d3-4027-af4c-40f69e7b37c9
description: 業務のスケジュールポリシーを設定する方法について説明します。 スケジュールポリシーには、予定の長さ、および許容できる潜在顧客と取り消し時間が含まれます。
ms.openlocfilehash: 82cc9a66e82665040a1f0d08635cae10cd413d4b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419830"
---
# <a name="set-your-scheduling-policies"></a><span data-ttu-id="02bfa-104">スケジュール ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="02bfa-104">Set your scheduling policies</span></span>

<span data-ttu-id="02bfa-105">すべての予定が同じとは限りません。</span><span class="sxs-lookup"><span data-stu-id="02bfa-105">Not all appointments are the same.</span></span> <span data-ttu-id="02bfa-106">わずか数分で終わる予定や、数時間かかる予定があります。</span><span class="sxs-lookup"><span data-stu-id="02bfa-106">Some take only a few minutes, while others can take hours or more.</span></span> <span data-ttu-id="02bfa-107">Microsoft 予約の場合、予約ページは、ビジネスのスケジュールポリシーを設定する場所です。</span><span class="sxs-lookup"><span data-stu-id="02bfa-107">In Microsoft Bookings, the booking page is where you set the scheduling policies for your business.</span></span> <span data-ttu-id="02bfa-108">スケジュール ポリシーには、予定の長さ、リードタイムと取り消し時間の上限、予約変更の自動通知が含まれます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-108">Scheduling policies include the length of appointments, acceptable lead and cancellation times, and automatic notifications of booking changes.</span></span> <span data-ttu-id="02bfa-109">[サービス] ページ内のサービスごとに追加のカスタマイズを追加して、そのサービスにのみ適用される追加の期間設定とポリシーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-109">Additional customization can be added for each service within the Services page, with additional duration settings and policies that apply only to that service.</span></span>

<span data-ttu-id="02bfa-110">ここで設定したポリシーは、最上位レベルのポリシーになります。</span><span class="sxs-lookup"><span data-stu-id="02bfa-110">The policies you set here are the top-level policies.</span></span> <span data-ttu-id="02bfa-111">このポリシーは、サービスごとに変更しない限り、提供するすべてのサービスに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-111">They are automatically applied to all the services you offer unless you choose to modify them on a per-service basis.</span></span> <span data-ttu-id="02bfa-112">たとえば、最初の consultations など、ほとんどのサービスについては、キャンセルの1日の通知が可能であるとします。</span><span class="sxs-lookup"><span data-stu-id="02bfa-112">For example, let's say that for most services, such as initial consultations, one-day notice for cancellations is acceptable.</span></span> <span data-ttu-id="02bfa-113">ただし、ゴルフ レッスンなど、施設の予約や手数料が必要なサービスの場合、3 日前までの通知を必須にすることもあります。</span><span class="sxs-lookup"><span data-stu-id="02bfa-113">But for those services that require facility reservations or fees, such as golf lessons, you might require three days' notice.</span></span> <span data-ttu-id="02bfa-114">このサービスレベルのポリシーは、[サービス] ページで設定できます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-114">You can set this service-level policy on the Services page.</span></span> <span data-ttu-id="02bfa-115">手順については、「[サービスの提供内容を定義する](define-service-offerings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02bfa-115">See [Define your service offerings](define-service-offerings.md) for instructions.</span></span>

## <a name="types-of-scheduling-policies"></a><span data-ttu-id="02bfa-116">スケジュール ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="02bfa-116">Types of scheduling policies</span></span>

<span data-ttu-id="02bfa-117">次の表に、予約ページで利用できるさまざまなスケジュールポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="02bfa-117">This table explains the various scheduling policies available on the booking page.</span></span>

| <span data-ttu-id="02bfa-118">ポリシー</span><span class="sxs-lookup"><span data-stu-id="02bfa-118">Policy</span></span> | <span data-ttu-id="02bfa-119">説明</span><span class="sxs-lookup"><span data-stu-id="02bfa-119">Explanation</span></span> |
|---|---|
| <span data-ttu-id="02bfa-120">時間の増分</span><span class="sxs-lookup"><span data-stu-id="02bfa-120">Time increments</span></span> | <span data-ttu-id="02bfa-121">予定間の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="02bfa-121">Determines the intervals between appointments.</span></span> <span data-ttu-id="02bfa-122">時間の増分は5分から4時間に設定できます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-122">You can set your time increments from 5 minutes to 4 hours.</span></span> <span data-ttu-id="02bfa-123">カスタマイズした時間単位を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-123">You can also set your own customized time increments.</span></span> <span data-ttu-id="02bfa-124">たとえば、15分間隔では、顧客は60分の予定を8:00、8:15、8:30 にスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-124">An interval of 15 minutes, for example, means a customer could schedule a 60-minute appointment at 8:00, 8:15, 8:30, and so on.</span></span> <span data-ttu-id="02bfa-125">反対に、60分間隔では、予定が1時間にのみ使用可能であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="02bfa-125">Conversely, a 60-minute interval means that appointments are only available on the hour.</span></span> <span data-ttu-id="02bfa-126">(サービスの期間を設定するには、「 [サービス内容を定義](define-service-offerings.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="02bfa-126">(To set service durations, see [Define your service offerings](define-service-offerings.md).)</span></span> |
| <span data-ttu-id="02bfa-127">リードタイム (時間)</span><span class="sxs-lookup"><span data-stu-id="02bfa-127">Lead time in hours</span></span> | <span data-ttu-id="02bfa-128">スケジュールが設定された予定に基づいてスタッフ割り当て計画を立てるので、各日付にサービスを利用しに来る顧客の数を事前に把握しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="02bfa-128">You build your staffing plan based on the appointments that are scheduled so it's important to know in advance how many customers are coming in for service on any particular day.</span></span> <span data-ttu-id="02bfa-129">リードタイムポリシーを使用すると、顧客が予定を予約またはキャンセルする必要のある時間数を事前に指定できます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-129">The lead time policy enables you to specify the number of hours in advance that customers must book or cancel an appointment.</span></span> |
| <span data-ttu-id="02bfa-130">事前の最大日数</span><span class="sxs-lookup"><span data-stu-id="02bfa-130">Maximum days in advance</span></span> | <span data-ttu-id="02bfa-p106">顧客がどのくらい前に予定を設定できるかを制限するには、この設定を使います。365 日以上の場合に最大値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-p106">If you want to limit how far in advance customers can book appointments, then this is the setting for you! You can set the maximum for 365 days or more.</span></span> |
| <span data-ttu-id="02bfa-133">予約が作成または変更されたときに通知する</span><span class="sxs-lookup"><span data-stu-id="02bfa-133">Notify when a booking is created or changed</span></span> | <span data-ttu-id="02bfa-p107">顧客が予定を設定したとき、または既存の予定を変更したときにメールを受信するには、このオプションをオンにします。メールは、[勤務先情報] ページに指定したメールボックスに送信されます。詳細については、「[勤務先情報を入力する](enter-business-information.md)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="02bfa-p107">Select this option when you want to receive an email any time a customer books an appointment or changes an existing one. The email will go to the mailbox specified on the Business information page. See [Enter your business information](enter-business-information.md) for details.</span></span> |

## <a name="set-your-policies"></a><span data-ttu-id="02bfa-137">ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="02bfa-137">Set your policies</span></span>

1. <span data-ttu-id="02bfa-138">Microsoft 365 で、アプリ起動ツールを選択し、[予約] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfa-138">In Microsoft 365, select the app launcher, and then select Bookings.</span></span>

1. <span data-ttu-id="02bfa-139">ナビゲーション ウィンドウで、[ **予約ページ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-139">In the navigation pane, select **Booking page**.</span></span>

1. <span data-ttu-id="02bfa-140">[ **スケジュールポリシー** ] セクションで、ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfa-140">Select your policies under the **Scheduling policy** section.</span></span>

1. <span data-ttu-id="02bfa-141">[ **保存して公開**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-141">Select **Save and publish**.</span></span>

## <a name="publish-the-booking-page"></a><span data-ttu-id="02bfa-142">予約ページを公開する</span><span class="sxs-lookup"><span data-stu-id="02bfa-142">Publish the booking page</span></span>

<span data-ttu-id="02bfa-143">予約ページを公開する準備ができたら、[ **保存して公開**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02bfa-143">When you're ready to publish your booking page, select **Save and publish**.</span></span> <span data-ttu-id="02bfa-144">詳細については、「 [予約ページのカスタマイズと公開](customize-booking-page.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02bfa-144">See [Customize and publish your booking page](customize-booking-page.md) for more information.</span></span>
