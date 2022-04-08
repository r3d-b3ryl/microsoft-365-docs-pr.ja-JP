---
title: Microsoft Bookings でバッファー時間を設定する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Microsoft Bookingsで予定の前後にバッファー時間を設定し、機器のクリーンアップまたはリセットに時間を確保します。
ms.openlocfilehash: 28d4c7feb76770cb40f5a780c2d406dc3bfeef8d
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714705"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Microsoft Bookings でバッファー時間を設定する

> [!NOTE]
> この記事は、最新バージョンのMicrosoft Bookingsを操作するのに役立ちます。 以前のバージョンは、今後数か月で廃止される予定です。

一部の予定では、お客様と会う前または後に、部屋と機器のセットアップ、クリーンアップ、またはリセットに時間が必要になる場合があります。 または、顧客の予定間を移動している場合は、顧客を待たなくても、自分とチームが予定間を移動できるようにするための時間が必要になる場合があります。

予定の開始前、予定の終了後、またはその両方にバッファー時間を設定して、スタッフが次の予定の準備に必要な余分な時間を与えることができます。

## <a name="set-buffer-time-defaults"></a>バッファー時間の既定値の設定

バッファー時間の既定値は、Bookingsの **[サービスの詳細**] ページで設定されます。 このページに設定されているすべてのサービスの既定値と同様に、これらの既定値は、特定の顧客のニーズを満たすために、特定の予約に対してユーザーが編集できます。

バッファー時間の設定は、[ **サービスの詳細** ] ページにあります。 特定のサービスに対して設定する前に、バッファー時間の切り替えを選択してバッファー時間の設定を有効にする必要があります。 これにより、[ **Before** ] ドロップダウンと **[After** ] ドロップダウンが表示されます。これは、次に示すように、各予約の前後に保持する既定の時間を選択するために使用されます。

   ![バッファー時間が有効になっているBookingsの画像。](../media/bookings-buffertime.png)

<!--## Buffer time and appointment timing

To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff. For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.

Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment. The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment. Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.

   ![Image of Bookings appointment call-out with buffer time showing.](../media/bookings-buffertime-callout.png)
-->

## <a name="buffer-time-and-availability"></a>バッファー時間と空き時間

顧客は直接表示せず、設定したバッファー時間を変更できません。 ただし、サービスの全体的な期間を計算するためにバッファー時間が使用されるため、お客様は、バッファーと通常の予定の時間の両方で、ご自身と関連するスタッフを予約済みとして表示します。 また、顧客は、予定とそのバッファー時間の両方に十分な時間がある場合にのみ、自分とスタッフの可用性を確認します。

たとえば、15 分の予定前バッファー時間を持つ 1 時間の予定には、1 時間 15 分以上の使用可能な時間ブロックが必要です。 したがって、このサービスの予定は予定表の 75 分の時間ブロックを埋め、競合なく予約するには 75 分の空き時間が必要になります。
