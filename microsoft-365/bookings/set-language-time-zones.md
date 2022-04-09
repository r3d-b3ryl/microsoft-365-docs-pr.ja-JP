---
title: Microsoft Bookings で言語とタイム ゾーンを設定する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: Microsoft Bookingsで言語とタイム ゾーンの設定を変更します。 間違った時刻に予約が作成された場合、間違ったタイム ゾーンにBookingsが設定されている可能性があります。
ms.openlocfilehash: cb6735640f85456568f0d0492a265046ab127e9c
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "64746973"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a>Microsoft Bookings で言語とタイム ゾーンを設定する

> [!NOTE]
> この記事は、最新バージョンのMicrosoft Bookingsを操作するのに役立ちます。 以前のバージョンは、今後数か月で廃止される予定です。

Microsoft Bookingsを使用していて、間違った時刻に予約が作成された場合は、タイム ゾーンの設定を変更する必要があります。 同様に、一部の予約が間違った言語の場合は、言語設定の変更が必要になる場合があります。

Bookingsには、2 つの言語とタイム ゾーンの設定があります。 最初の設定は、予約予定表の言語とタイム ゾーンを制御し、ログインしているユーザーの個人用予定表のOutlook on the web設定を使用して設定します。 2 番目の設定は、顧客が使用するセルフサービス予約ページに影響し、そのページの言語とタイム ゾーンのみを制御する "地域設定" ページを使用して設定されます。

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a>予約予定表の言語とタイム ゾーンの設定

予約予定表では、ログインしているユーザーの言語とタイム ゾーンの設定が使用されます。 たとえば、ログインしているユーザーのタイム ゾーンが東部標準時 (EST) に設定されている場合、予約予定表には既存の予定の開始時刻と終了時刻が EST で表示されます。 このタイム ゾーンは、ユーザーのMicrosoft 365アカウントとOutlook on the web アカウントが作成されたときに設定されていました。

予約カレンダーの言語とタイム ゾーンを設定するには:

1. Microsoft 365にログインし、ランディング ページ (下のスクリーンショットに示すように) または Microsoft 365 アプリ 起動ツールでOutlook タイルを選択します。

   :::image type="content" source="../media/bookings-outlook-tile.png" alt-text="ランディング ページのタイルMicrosoft 365 Outlookします。":::

1. Outlook開いたら、画面の右上隅にある **歯車アイコン** を選択して個人用とアカウントの設定を開き、**設定** パネル検索ボックスで "タイム ゾーン" を検索します。 このアカウントの現在の個人の言語とタイム ゾーンの設定が表示されます。 前に説明したように、この設定は、予約予定表の言語とタイム ゾーンも制御します。

1. [言語] ボックスまたは [現在のタイム ゾーン] ボックスでドロップダウン矢印を選択し、目的の設定を選択して、 **言語またはタイム ゾーン** を変更します。

1. **[保存]** をクリックします。 設定 パネルが閉じ、Outlook on the web再起動され、新しい言語とタイム ゾーンの設定が適用されます。

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a>予約ページの言語とタイム ゾーンの設定

1. Microsoft 365で、アプリ起動ツールを選択し、**Bookings** を選択します。

1. ナビゲーション ウィンドウで[ **予約] ページ** を選択し、[ **言語とタイム ゾーンの設定の変更**] を選択します。

   ![スクリーンショット: 言語とタイム ゾーンの設定を変更するリンク。](../media/bookings-region-language-timezone-settings.png)

1. 言語と現在のタイム ゾーンを選択し、[OK] を選択 **します**。

   :::image type="content" source="../media/bookings-region-timezone-settings-1.png" alt-text="言語とタイム ゾーンの設定。":::