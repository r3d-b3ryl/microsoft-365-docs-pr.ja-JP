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
description: Microsoft Bookings の予定の前または後にバッファー時間を設定して、機器のクリーンアップまたはリセットに時間を割り当て。
ms.openlocfilehash: a33159b0b5f168bbb61c88bc9b4181e05c8abbb1
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329321"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Microsoft Bookings でバッファー時間を設定する

一部の予定では、お客様と会う前または後に、部屋と備品のセットアップ、クリーンアップ、またはリセットに時間が必要になる場合があります。 または、顧客の予定間を移動している場合は、顧客を待たなくても、チームが予定間を移動できる時間が必要な場合があります。

予定が開始される前、予定が終了した後、または両方のバッファー時間を設定して、スタッフが次の予定の準備に必要な余分な時間をスタッフに提供できます。

## <a name="set-buffer-time-defaults"></a>バッファー時間の既定値の設定

バッファー時間の既定値は、Bookings の **[サービスの詳細** ] ページで設定されます。 このページで設定されているサービスの既定値と同様に、これらの既定値は、特定の顧客のニーズを満たすために、特定の予約に対してユーザーが編集できます。

バッファー時間の設定は、[サービスの詳細] ページの **[既定の** 期間ピッカー] **の下にあります** 。 特定のサービスに対して設定する前に、バッファー時間トグルを選択してバッファー時間設定を有効にする必要があります。 これにより、次 **に示すように**、予約の前と後に保持する既定の時間を選択するために使用される [Before] ドロップダウンと [After] ドロップダウンが表示されます。

   ![バッファー時間が有効になっている予約のイメージ。](../media/bookings-buffertime.png)

<!--## Buffer time and appointment timing

To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff. For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.

Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment. The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment. Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.

   ![Image of Bookings appointment call-out with buffer time showing.](../media/bookings-buffertime-callout.png)
-->

## <a name="buffer-time-and-availability"></a>バッファー時間と空き時間

顧客は直接表示しないし、設定したバッファー時間を変更できません。 ただし、バッファー時間はサービス全体の期間を計算するために使用されるため、バッファーと通常の予定時間の両方で、ユーザーと関連するスタッフが予約されたと表示されます。 また、予定とバッファー時間の両方に十分な時間がある場合にのみ、ユーザーとスタッフの空き時間が表示されます。

たとえば、15 分の予定前バッファー時間を持つ 1 時間の予定では、少なくとも 1 時間 15 分の利用可能なタイム ブロックが必要です。 したがって、このサービスの予定は、予定表の 75 分の時間を満たすため、競合なく予約するには 75 分の空き時間が必要になります。
