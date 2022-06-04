---
title: Scheduler for Microsoft 365 のスケジュール設定の調整の概要
ms.author: shivb
author: shivbijlani
manager: charlle
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: Scheduler for Microsoft 365 のスケジュール設定を調整する方法について説明します。
ms.openlocfilehash: 34594db45883a7f746b9905661b1dedc8e5e4f6a
ms.sourcegitcommit: c216ffa5da8f431e4380bb133a234ae7d94144c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2022
ms.locfileid: "65893434"
---
# <a name="scheduling-preferences-used-by-scheduler"></a>Scheduler で使用されるスケジュール設定

Scheduler では、複数の Outlook 環境設定を使用して、開催者の会議をスケジュールします。 Outlook クライアントで基本設定を変更すると、Scheduler が Cortana に送信された要求を処理する方法に影響します。 たとえば、Outlook Web の設定ページで開催者がタイム ゾーンの基本設定を変更した場合、その後に続く開催者によるすべての要求は既定で新しいタイム ゾーンに設定されます。

## <a name="supported-settings"></a>サポートされている設定

- **タイム ゾーン**。 会議に適した時間を決定するタイム ゾーン スケジューラ ユーザー。 詳細については [、「タイム ゾーンの追加、削除、または変更](https://support.microsoft.com/en-us/office/add-remove-or-change-time-zones-5ab3e10e-5a6c-46af-ab48-156fedf70c04) 」を参照してください。

- **作業時間と日数**。 ほとんどの会議の種類では、Scheduler は開催者の勤務時間と会議時間の設定に従って時間を選択します。 詳細については、「 [Outlook で作業時間と日数を変更](https://support.microsoft.com/en-us/office/change-your-work-hours-and-days-in-outlook-a27f261d-0681-415f-8ac1-388ab21e833f) する」を参照してください。

- **オンライン会議。** 予定表オプションをオンにすると、Outlook と Scheduler からスケジュールしたすべての会議が、会議の詳細と共にオンラインで開催されます。 スケジューラは現在、会議プロバイダーとして Teams と Skype をサポートしています。 詳細については、「 [すべての会議を Teams 会議にする](https://support.microsoft.com/en-us/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f#bkmk_makeallteamsmtngs) 」を参照してください。

- **既定の会議期間**。 開催者が要求で目的の会議期間を指定しない場合、Scheduler は要求に優先する会議期間を使用します。 この設定は、Windows Outlook クライアントでのみ使用できます。

   1. [ **ファイル** > **オプション] を** 選択すると、[Outlook オプション] ダイアログが表示されます。

   2. ダイアログの左側にある一覧から [ **予定表** ] を選択します。

   3. ダイアログの右側にある予定表オプションの設定で、 **新しい予定と会議の既定の期間** を選択します。

      :::image type="content" source="../media/OutlookOptions.png" alt-text="Windows の Outlook 予定表オプション ダイアログでは、作業時間、既定の会議期間を設定し、Scheduler で使用する会議を短縮することができます。":::

- **バック ツー バックの会議は避けてください**。 Outlook 設定では、会議の遅延を開始したり、会議を早期に終了したりして、会議のバック ツー バックを回避できます。 また、スケジューラは、設定した設定に従って会議の期間を短縮できます。 詳細については、「 [既定の会議の長さを変更](https://techcommunity.microsoft.com/t5/hybrid-work/change-default-meeting-length-in-outlook-avoid-back-to-back/m-p/1247361) する」を参照してください。

> [!NOTE]
> Windows クライアントを使用する場合は、[ **Outlook の設定をクラウドに保存** する] を選択して、Scheduler やその他の Outlook クライアント間で環境設定を同期する必要があります。
> :::image type="content" source="../media/OutlookOptions2.png" alt-text="Windows の [Outlook 予定表オプション] ダイアログ。[Outlook の設定をクラウドに保存する] を選択して、クライアント間でスケジュール設定を同期します。":::
