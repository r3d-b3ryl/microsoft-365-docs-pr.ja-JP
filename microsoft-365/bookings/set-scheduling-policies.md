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
description: ビジネスのスケジュール ポリシーを設定する方法について説明します。 スケジュール ポリシーには、予定の長さ、および受け入れ可能なリードとキャンセルの時間が含まれます。
ms.openlocfilehash: 82cc9a66e82665040a1f0d08635cae10cd413d4b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419830"
---
# <a name="set-your-scheduling-policies"></a><span data-ttu-id="0d814-104">スケジュール ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="0d814-104">Set your scheduling policies</span></span>

<span data-ttu-id="0d814-105">すべての予定が同じとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0d814-105">Not all appointments are the same.</span></span> <span data-ttu-id="0d814-106">わずか数分で終わる予定や、数時間かかる予定があります。</span><span class="sxs-lookup"><span data-stu-id="0d814-106">Some take only a few minutes, while others can take hours or more.</span></span> <span data-ttu-id="0d814-107">Microsoft Bookings では、予約ページでビジネスのスケジュール ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="0d814-107">In Microsoft Bookings, the booking page is where you set the scheduling policies for your business.</span></span> <span data-ttu-id="0d814-108">スケジュール ポリシーには、予定の長さ、リードタイムと取り消し時間の上限、予約変更の自動通知が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0d814-108">Scheduling policies include the length of appointments, acceptable lead and cancellation times, and automatic notifications of booking changes.</span></span> <span data-ttu-id="0d814-109">[サービス] ページ内の各サービスに対して追加のカスタマイズを追加し、そのサービスにのみ適用される追加の期間設定とポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d814-109">Additional customization can be added for each service within the Services page, with additional duration settings and policies that apply only to that service.</span></span>

<span data-ttu-id="0d814-110">ここで設定したポリシーは、最上位レベルのポリシーになります。</span><span class="sxs-lookup"><span data-stu-id="0d814-110">The policies you set here are the top-level policies.</span></span> <span data-ttu-id="0d814-111">このポリシーは、サービスごとに変更しない限り、提供するすべてのサービスに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d814-111">They are automatically applied to all the services you offer unless you choose to modify them on a per-service basis.</span></span> <span data-ttu-id="0d814-112">たとえば、最初のコンサルティングなど、ほとんどのサービスでは、キャンセルに関する 1 日の通知が受け入れられるとします。</span><span class="sxs-lookup"><span data-stu-id="0d814-112">For example, let's say that for most services, such as initial consultations, one-day notice for cancellations is acceptable.</span></span> <span data-ttu-id="0d814-113">ただし、ゴルフ レッスンなど、施設の予約や手数料が必要なサービスの場合、3 日前までの通知を必須にすることもあります。</span><span class="sxs-lookup"><span data-stu-id="0d814-113">But for those services that require facility reservations or fees, such as golf lessons, you might require three days' notice.</span></span> <span data-ttu-id="0d814-114">このサービスレベルのポリシーは、[サービス] ページで設定できます。</span><span class="sxs-lookup"><span data-stu-id="0d814-114">You can set this service-level policy on the Services page.</span></span> <span data-ttu-id="0d814-115">手順については、「[サービスの提供内容を定義する](define-service-offerings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d814-115">See [Define your service offerings](define-service-offerings.md) for instructions.</span></span>

## <a name="types-of-scheduling-policies"></a><span data-ttu-id="0d814-116">スケジュール ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="0d814-116">Types of scheduling policies</span></span>

<span data-ttu-id="0d814-117">次の表に、予約ページで使用できるさまざまなスケジュール ポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0d814-117">This table explains the various scheduling policies available on the booking page.</span></span>

| <span data-ttu-id="0d814-118">ポリシー</span><span class="sxs-lookup"><span data-stu-id="0d814-118">Policy</span></span> | <span data-ttu-id="0d814-119">説明</span><span class="sxs-lookup"><span data-stu-id="0d814-119">Explanation</span></span> |
|---|---|
| <span data-ttu-id="0d814-120">時間の増分</span><span class="sxs-lookup"><span data-stu-id="0d814-120">Time increments</span></span> | <span data-ttu-id="0d814-121">予定間の間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="0d814-121">Determines the intervals between appointments.</span></span> <span data-ttu-id="0d814-122">時間の増分を 5 分から 4 時間に設定できます。</span><span class="sxs-lookup"><span data-stu-id="0d814-122">You can set your time increments from 5 minutes to 4 hours.</span></span> <span data-ttu-id="0d814-123">また、独自のカスタマイズされた時間増分を設定できます。</span><span class="sxs-lookup"><span data-stu-id="0d814-123">You can also set your own customized time increments.</span></span> <span data-ttu-id="0d814-124">たとえば、15 分の間隔は、顧客が 8:00、8:15、8:30 など、60 分間の予定をスケジュールできるという意味です。</span><span class="sxs-lookup"><span data-stu-id="0d814-124">An interval of 15 minutes, for example, means a customer could schedule a 60-minute appointment at 8:00, 8:15, 8:30, and so on.</span></span> <span data-ttu-id="0d814-125">逆に、60 分の間隔は、予定が 1 時間にしか利用できないという意味です。</span><span class="sxs-lookup"><span data-stu-id="0d814-125">Conversely, a 60-minute interval means that appointments are only available on the hour.</span></span> <span data-ttu-id="0d814-126">(サービス期間を設定するには、「 [サービスサービスを定義する.」を参照](define-service-offerings.md)してください)。</span><span class="sxs-lookup"><span data-stu-id="0d814-126">(To set service durations, see [Define your service offerings](define-service-offerings.md).)</span></span> |
| <span data-ttu-id="0d814-127">リードタイム (時間)</span><span class="sxs-lookup"><span data-stu-id="0d814-127">Lead time in hours</span></span> | <span data-ttu-id="0d814-128">スケジュールが設定された予定に基づいてスタッフ割り当て計画を立てるので、各日付にサービスを利用しに来る顧客の数を事前に把握しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="0d814-128">You build your staffing plan based on the appointments that are scheduled so it's important to know in advance how many customers are coming in for service on any particular day.</span></span> <span data-ttu-id="0d814-129">リード タイム ポリシーを使用すると、顧客が予定を予約またはキャンセルする必要がある時間数を事前に指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d814-129">The lead time policy enables you to specify the number of hours in advance that customers must book or cancel an appointment.</span></span> |
| <span data-ttu-id="0d814-130">事前の最大日数</span><span class="sxs-lookup"><span data-stu-id="0d814-130">Maximum days in advance</span></span> | <span data-ttu-id="0d814-p106">顧客がどのくらい前に予定を設定できるかを制限するには、この設定を使います。365 日以上の場合に最大値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="0d814-p106">If you want to limit how far in advance customers can book appointments, then this is the setting for you! You can set the maximum for 365 days or more.</span></span> |
| <span data-ttu-id="0d814-133">予約が作成または変更されたときに通知する</span><span class="sxs-lookup"><span data-stu-id="0d814-133">Notify when a booking is created or changed</span></span> | <span data-ttu-id="0d814-p107">顧客が予定を設定したとき、または既存の予定を変更したときにメールを受信するには、このオプションをオンにします。メールは、[勤務先情報] ページに指定したメールボックスに送信されます。詳細については、「[勤務先情報を入力する](enter-business-information.md)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="0d814-p107">Select this option when you want to receive an email any time a customer books an appointment or changes an existing one. The email will go to the mailbox specified on the Business information page. See [Enter your business information](enter-business-information.md) for details.</span></span> |

## <a name="set-your-policies"></a><span data-ttu-id="0d814-137">ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="0d814-137">Set your policies</span></span>

1. <span data-ttu-id="0d814-138">[Microsoft 365] でアプリ 起動ツールを選択し、[予約] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d814-138">In Microsoft 365, select the app launcher, and then select Bookings.</span></span>

1. <span data-ttu-id="0d814-139">ナビゲーション ウィンドウで、[ **予約ページ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0d814-139">In the navigation pane, select **Booking page**.</span></span>

1. <span data-ttu-id="0d814-140">[スケジュール ポリシー] セクションでポリシー **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="0d814-140">Select your policies under the **Scheduling policy** section.</span></span>

1. <span data-ttu-id="0d814-141">[ **保存して公開**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0d814-141">Select **Save and publish**.</span></span>

## <a name="publish-the-booking-page"></a><span data-ttu-id="0d814-142">予約ページを公開する</span><span class="sxs-lookup"><span data-stu-id="0d814-142">Publish the booking page</span></span>

<span data-ttu-id="0d814-143">予約ページを公開する準備ができたら、[ **保存して公開**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0d814-143">When you're ready to publish your booking page, select **Save and publish**.</span></span> <span data-ttu-id="0d814-144">詳細については [、「予約ページのカスタマイズと発行](customize-booking-page.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d814-144">See [Customize and publish your booking page](customize-booking-page.md) for more information.</span></span>
