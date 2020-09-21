---
title: Microsoft Bookings でバッファー時間を設定する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Microsoft 予約の予定の前または後にバッファー時間を設定して、機器のクリーンアップまたはリセットの時間を確保します。
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962349"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a><span data-ttu-id="c3a48-103">Microsoft Bookings でバッファー時間を設定する</span><span class="sxs-lookup"><span data-stu-id="c3a48-103">Set buffer time in Microsoft Bookings</span></span>

<span data-ttu-id="c3a48-104">一部の予定には、お客様が会議室や備品をセットアップ、クリーンアップ、またはリセットするための時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3a48-104">Some of your appointments might require time before or after you meet with your customer to set up, clean up, or reset your room and equipment.</span></span> <span data-ttu-id="c3a48-105">また、お客様の予定間で出張している場合は、お客様がお客様を待たずに予定間を移動できるようにするための時間が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c3a48-105">Or if you’re on the road between customer appointments, you may need time to ensure you and your team can travel between appointments without making the customer wait.</span></span>

<span data-ttu-id="c3a48-106">定期的な予定の開始、予定の終了後、またはその両方を設定して、次の予定を準備するのに必要な時間をスタッフに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="c3a48-106">You can set buffer time before appointments start, after appointments end, or both to give staff the extra time they need to prepare for their next appointment.</span></span>

## <a name="set-buffer-time-defaults"></a><span data-ttu-id="c3a48-107">バッファー時間の既定値の設定</span><span class="sxs-lookup"><span data-stu-id="c3a48-107">Set buffer time defaults</span></span>

<span data-ttu-id="c3a48-108">バッファー時間の既定値は、[予約] の [ **サービスの詳細** ] ページで設定します。</span><span class="sxs-lookup"><span data-stu-id="c3a48-108">Buffer time defaults are set on the **Service details** page in Bookings.</span></span> <span data-ttu-id="c3a48-109">このページに設定されているすべてのサービスの既定値と同様に、特定のお客様のニーズを満たす特定の予約に対して、これらの既定値を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="c3a48-109">Like all service defaults set on this page, these defaults can be edited by you for a specific booking to meet specific customer needs.</span></span>

<span data-ttu-id="c3a48-110">バッファー時間の設定は、[**サービスの詳細**] ページの**既定の期間**選択のすぐ下にあります。</span><span class="sxs-lookup"><span data-stu-id="c3a48-110">The buffer time setting can be found just below the **Default duration** pickers on the **Service details** page.</span></span> <span data-ttu-id="c3a48-111">特定のサービスに設定する前に、バッファー時間の切り替えを選択することによって、バッファー時間の設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3a48-111">Before it can be set for a given service, you must enable the buffer time setting by selecting the buffer time toggle.</span></span> <span data-ttu-id="c3a48-112">これにより、次のように、各予約の前後に保持する既定の時間を選択するために使用さ**れるドロップダウン**の**前後**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3a48-112">This causes the **Before** and **After** drop-downs to appear, which are used to pick the default amount of time to hold before and after each booking, as shown here:</span></span>

   ![バッファー時間が有効な予約の画像](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a><span data-ttu-id="c3a48-114">バッファー時間と予定タイミング</span><span class="sxs-lookup"><span data-stu-id="c3a48-114">Buffer time and appointment timing</span></span>

<span data-ttu-id="c3a48-115">お客様との打ち合わせに関して混乱を避けるため、予約には、予定表のバッファー時間と実際の予定時間 (お客様が自分に会う時間) と、関連するスタッフへの電子メールの確認や事前通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3a48-115">To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff.</span></span> <span data-ttu-id="c3a48-116">たとえば、次に示すのは、予定に対して予約されている予定のうち、予定が15分前のバッファー時間を含む顧客との予定です。</span><span class="sxs-lookup"><span data-stu-id="c3a48-116">For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.</span></span>

<span data-ttu-id="c3a48-117">このイベント自体 (下の図の左側) には、実際のお客様の予定に対するバッファー時間と暗い網掛けの薄い網かけが表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3a48-117">Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment.</span></span> <span data-ttu-id="c3a48-118">予定の呼び出しアウト (イベントを選択したときに開かれます) は、特に、予定が 9: 00AM から 10: 00AM (Katie ヨルダン) になっていることを示し、予定の前に15分のバッファー時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3a48-118">The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment.</span></span> <span data-ttu-id="c3a48-119">スタッフへの確認と事前通知同様に、特定のバッファーおよび予定時間を参照します。顧客は、9: 00AM ~ 10: 00AM の予定時間を参照しているものだけを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3a48-119">Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.</span></span>

   ![時間が表示された予約済みの会議の画像](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a><span data-ttu-id="c3a48-121">バッファー時間と空き時間</span><span class="sxs-lookup"><span data-stu-id="c3a48-121">Buffer time and availability</span></span>

<span data-ttu-id="c3a48-122">お客様には、設定したバッファー時間は直接表示されず、変更もできません。</span><span class="sxs-lookup"><span data-stu-id="c3a48-122">Your customers don’t directly see and cannot change the buffer times you set.</span></span> <span data-ttu-id="c3a48-123">ただし、バッファー時間はサービス全体の期間を計算するために使用されるため、バッファーと定期的な予定時間の両方で、お客様と関連するスタッフが予約されています。</span><span class="sxs-lookup"><span data-stu-id="c3a48-123">However, because buffer time is used to calculate overall service duration, customers will see you and your relevant staff as booked during both buffer and regular appointment times.</span></span> <span data-ttu-id="c3a48-124">また、予定とバッファー時間の両方に十分な時間がある場合は、お客様とスタッフに対してのみ可用性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3a48-124">Customers also only see availability for you and your staff if there is enough time for both the appointment and its buffer time.</span></span>

<span data-ttu-id="c3a48-125">例として、15分前の予定のバッファー時間を持つ1時間の予定には、少なくとも1時間と15分の使用可能な時間帯が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3a48-125">As an example, a one-hour appointment with a 15-minute pre-appointment buffer time requires an available time block of at least 1 hour and 15 minutes.</span></span> <span data-ttu-id="c3a48-126">そのため、このサービスの予定では、予定表に75分の時間ブロックが入力され、競合することなく、ブックを75分の可用性が必要になります。</span><span class="sxs-lookup"><span data-stu-id="c3a48-126">An appointment for this service would therefore fill a 75-minute block of time on your calendar and needs 75 minutes of availability to book without conflict.</span></span>
