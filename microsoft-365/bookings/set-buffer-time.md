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
description: Microsoft Bookings の予定の前または後にバッファー時間を設定して、機器のクリーンアップまたはリセットに時間を割り当て。
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962349"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a><span data-ttu-id="65448-103">Microsoft Bookings でバッファー時間を設定する</span><span class="sxs-lookup"><span data-stu-id="65448-103">Set buffer time in Microsoft Bookings</span></span>

<span data-ttu-id="65448-104">一部の予定では、お客様と会う前または後に、部屋と備品のセットアップ、クリーンアップ、またはリセットに時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="65448-104">Some of your appointments might require time before or after you meet with your customer to set up, clean up, or reset your room and equipment.</span></span> <span data-ttu-id="65448-105">または、顧客の予定間を移動している場合は、顧客を待たなくても、チームが予定間を移動できる時間が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="65448-105">Or if you’re on the road between customer appointments, you may need time to ensure you and your team can travel between appointments without making the customer wait.</span></span>

<span data-ttu-id="65448-106">予定が開始される前、予定が終了した後、または両方のバッファー時間を設定して、スタッフが次の予定の準備に必要な余分な時間をスタッフに提供できます。</span><span class="sxs-lookup"><span data-stu-id="65448-106">You can set buffer time before appointments start, after appointments end, or both to give staff the extra time they need to prepare for their next appointment.</span></span>

## <a name="set-buffer-time-defaults"></a><span data-ttu-id="65448-107">バッファー時間の既定値の設定</span><span class="sxs-lookup"><span data-stu-id="65448-107">Set buffer time defaults</span></span>

<span data-ttu-id="65448-108">バッファー時間の既定値は、Bookings の **[サービスの詳細** ] ページで設定されます。</span><span class="sxs-lookup"><span data-stu-id="65448-108">Buffer time defaults are set on the **Service details** page in Bookings.</span></span> <span data-ttu-id="65448-109">このページで設定されているサービスの既定値と同様に、これらの既定値は、特定の顧客のニーズを満たすために、特定の予約に対してユーザーが編集できます。</span><span class="sxs-lookup"><span data-stu-id="65448-109">Like all service defaults set on this page, these defaults can be edited by you for a specific booking to meet specific customer needs.</span></span>

<span data-ttu-id="65448-110">バッファー時間の設定は、[サービスの詳細] ページの **[既定の** 期間ピッカー] **の下にあります** 。</span><span class="sxs-lookup"><span data-stu-id="65448-110">The buffer time setting can be found just below the **Default duration** pickers on the **Service details** page.</span></span> <span data-ttu-id="65448-111">特定のサービスに対して設定する前に、バッファー時間トグルを選択してバッファー時間設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65448-111">Before it can be set for a given service, you must enable the buffer time setting by selecting the buffer time toggle.</span></span> <span data-ttu-id="65448-112">これにより、次に **示** すように、予約の前と後に保持する既定の時間を選択するために使用される [Before] ドロップダウンと [After] ドロップダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65448-112">This causes the **Before** and **After** drop-downs to appear, which are used to pick the default amount of time to hold before and after each booking, as shown here:</span></span>

   ![バッファー時間が有効になっている予約のイメージ](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a><span data-ttu-id="65448-114">バッファー時間と予定タイミング</span><span class="sxs-lookup"><span data-stu-id="65448-114">Buffer time and appointment timing</span></span>

<span data-ttu-id="65448-115">顧客がいつお客様と会うのかについて混乱を避けるため、Bookings は、バッファー時間と実際の予定時間 (顧客が顧客と会う予定の時間) を予定表に表示し、関連するスタッフに電子メールで確認とリマインダーを表示します。</span><span class="sxs-lookup"><span data-stu-id="65448-115">To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff.</span></span> <span data-ttu-id="65448-116">たとえば、予約前バッファー時間が 15 分を含む顧客との予定については、Bookings に表示される内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="65448-116">For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.</span></span>

<span data-ttu-id="65448-117">イベント自体 (下の図の左側) には、バッファー時間の明るい網かけと、実際の顧客予定の濃い網かけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65448-117">Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment.</span></span> <span data-ttu-id="65448-118">予定の呼び出し (イベントを選択すると開きます) は、特に予定が Katie Jordan の午前 9:00 から午前 10:00 までであり、予定の前に 15 分のバッファー時間と予定の 0 分後に含まれると具体的に示しています。</span><span class="sxs-lookup"><span data-stu-id="65448-118">The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment.</span></span> <span data-ttu-id="65448-119">スタッフへの確認とリマインダーは、同様に特定のバッファーと予定時間を参照しますが、顧客は午前 9:00 ~ 午前 10:00AM の予定時間を参照する確認とリマインダーのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="65448-119">Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.</span></span>

   ![バッファー時間を示す予約予定の呼び出しのイメージ](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a><span data-ttu-id="65448-121">バッファー時間と空き時間</span><span class="sxs-lookup"><span data-stu-id="65448-121">Buffer time and availability</span></span>

<span data-ttu-id="65448-122">顧客は直接表示しないし、設定したバッファー時間を変更できません。</span><span class="sxs-lookup"><span data-stu-id="65448-122">Your customers don’t directly see and cannot change the buffer times you set.</span></span> <span data-ttu-id="65448-123">ただし、バッファー時間はサービス全体の期間を計算するために使用されるため、バッファーと通常の予定時間の両方で、ユーザーと関連するスタッフが予約されたと表示されます。</span><span class="sxs-lookup"><span data-stu-id="65448-123">However, because buffer time is used to calculate overall service duration, customers will see you and your relevant staff as booked during both buffer and regular appointment times.</span></span> <span data-ttu-id="65448-124">また、予定とバッファー時間の両方に十分な時間がある場合にのみ、ユーザーとスタッフの空き時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="65448-124">Customers also only see availability for you and your staff if there is enough time for both the appointment and its buffer time.</span></span>

<span data-ttu-id="65448-125">たとえば、15 分の予定前バッファー時間を持つ 1 時間の予定では、少なくとも 1 時間 15 分の利用可能なタイム ブロックが必要です。</span><span class="sxs-lookup"><span data-stu-id="65448-125">As an example, a one-hour appointment with a 15-minute pre-appointment buffer time requires an available time block of at least 1 hour and 15 minutes.</span></span> <span data-ttu-id="65448-126">したがって、このサービスの予定は、予定表の 75 分の時間を満たすため、競合なく予約するには 75 分の空き時間が必要になります。</span><span class="sxs-lookup"><span data-stu-id="65448-126">An appointment for this service would therefore fill a 75-minute block of time on your calendar and needs 75 minutes of availability to book without conflict.</span></span>
