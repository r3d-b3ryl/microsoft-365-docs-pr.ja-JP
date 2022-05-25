---
title: Microsoft 365の概要に合わせて Scheduler のスケジュール設定を調整する
ms.author: shivb
author: shivbijlani
manager: charlle
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: Microsoft 365の Scheduler のスケジュール設定を調整する方法について説明します。
ms.openlocfilehash: 4c6bf31472f9237f82905ce36f7db534a99896b0
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65670395"
---
<a name="scheduling-preferences"></a>スケジュール設定
======================

Scheduler では、開催者の会議をスケジュールするために、いくつかのOutlook設定が考慮されます。 Outlook クライアントを介した基本設定の変更は、Scheduler がCortanaに送信された後続の要求を処理する方法に自動的に反映されます。 たとえば、開催者が Outlook Web の [設定] ページでタイム ゾーンの基本設定を変更した場合、開催者によるそれ以降のすべての要求は既定で新しいタイム ゾーン値に設定されます。

<a name="supported-settings"></a>サポートされている設定
------------------

<a name="time-zone"></a>タイム ゾーン
---------

会議をスケジュールする適切な時間を決定するときに使用されるタイム ゾーン。 [タイム ゾーンの追加、削除、変更](https://support.microsoft.com/en-us/office/add-remove-or-change-time-zones-5ab3e10e-5a6c-46af-ab48-156fedf70c04)に関するドキュメントを参照してください。

<a name="work-hours-and-days"></a>作業時間と日数
-------------------

ほとんどの会議の種類では、Scheduler は開催者の週と会議時間の設定に従って時間をスケジュールします。 [Outlookドキュメントの「勤務時間と日数を変更](https://support.microsoft.com/en-us/office/change-your-work-hours-and-days-in-outlook-a27f261d-0681-415f-8ac1-388ab21e833f)する」を参照してください。

<a name="online-meetings"></a>オンライン会議
---------------

予定表オプションをオンにすると、Outlookと Scheduler からスケジュールしたすべての会議が、会議の詳細と共にオンラインで開催されます。 スケジューラは現在、会議プロバイダーとしてTeamsとSkypeをサポートしています。 [会議のすべての会議Teamsドキュメントを](https://support.microsoft.com/en-us/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f#bkmk_makeallteamsmtngs)参照してください。

<a name="default-meeting-duration"></a>既定の会議期間
------------------------

開催者が要求で目的の会議期間を指定しない場合、Scheduler は要求に優先する会議期間を使用します。 この設定は、Windows Outlook クライアントでのみ使用できます。

1. **[ファイル****オプション**] をクリックする >  

2. **ナビゲーション ウィンドウ** で **[予定表**] を選択します。

3. 既定の期間設定は、[**予定表****オプション]** の下にあります。

![Windowsの [Outlook カレンダー オプション] ダイアログ。 Scheduler が既定値として使用できるように、作業時間、既定の期間、および会議の短縮オプションを構成します。](../media/OutlookOptions.png)

<a name="avoid-back-to-back-meetings"></a>会議のバック ツー バックを回避する
---------------------------

Outlook、会議を自動的に遅く開始するか、会議を早期に終了して、バック ツー バックの会議を回避する設定が追加されました。 設定した場合、Scheduler では、基本設定に従って会議の期間も短縮されます。 Outlookドキュメントの[「既定の会議の長さを変更](https://techcommunity.microsoft.com/t5/hybrid-work/change-default-meeting-length-in-outlook-avoid-back-to-back/m-p/1247361)する」を参照してください。

##<a name="additional-note"></a>その他の注意

- Windows クライアントを使用する場合は、スケジューラとその他のOutlook クライアント間で環境設定が同期されるようにするには、次のオプションを設定する必要があります。

![Windowsの [Outlook カレンダー オプション] ダイアログ。 [クラウドでOutlook設定をMicrosoft Storeする] を有効にします。](../media/OutlookOptions2.png)
