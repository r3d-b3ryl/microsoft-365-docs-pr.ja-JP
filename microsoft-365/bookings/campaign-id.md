---
title: Bookings ページ URL にマーケティング キャンペーン ID を追加する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
description: Bookings ページ URL にキャンペーン ID を追加する方法
ms.openlocfilehash: 003f7665faa03070c8b608afc778528420cba8e8
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65637940"
---
# <a name="add-a-marketing-campaign-id-to-a-bookings-page-url"></a>Bookings ページ URL にマーケティング キャンペーン ID を追加する

Booking ページ URL の末尾にキャンペーン ID を追加して、Bookings マーケティング キャンペーンを追跡します。

キャンペーン ID を使用して、マーケティング キャンペーンの動作を確認します。 Bookings ページ URL の末尾に選択したキャンペーン ID を追加し、さまざまなマーケティング プラットフォームでキャンペーン ID を使用して、どのキャンペーンが顧客と接続されているかを確認します。

## <a name="add-campaign-id"></a>キャンペーン ID を追加する

1. Microsoft 365でアプリ起動ツールを選択し、**Bookings** を選択します。

2. 予定表を選択し、左側のナビゲーション ウィンドウで **[Booking page**] を選択し、予約ページの URL をコピーし、メモ帳などのテキスト編集プログラムに貼り付けます。

    :::image type="content" source="../media/copy-booking-page-url.png" alt-text="スクリーンショット: Bookings ページ URL をコピーして、マーケティング用のキャンペーン ID を追加できるようにします":::

3. Booking ページ URL の末尾にキャンペーン ID を追加します。 たとえば、予約ページの URL が次のような場合は、 [https://outlook.office365.com/owa/calendar/TailspinToys@contosopetscom.onmicrosoft.com/bookings/](https://outlook.office365.com/owa/calendar/TailspinToys@contosopetscom.onmicrosoft.com/bookings/)最後に追加する ID を選択します。 たとえば、Twitter ページから予約の詳細を追跡する場合は、URL の末尾に Twitter を追加できます。 Twitter ページに追加する新しい URL は次のようになります [https://outlook.office365.com/owa/calendar/TailspinToys@contosopetscom.onmicrosoft.com/bookings/?RefID=Twitter](https://outlook.office365.com/owa/calendar/TailspinToys@contosopetscom.onmicrosoft.com/bookings/?RefID=Twitter)。 さまざまなキャンペーン ID を使用して、実行中のマーケティング キャンペーンを追跡します。

> [!NOTE]
> キャンペーン ID の文字は、英数字、アンダースコア、ハイフンのいずれかである必要があります。 Web ブラウザーにコピーして貼り付けることで、キャンペーン ID URL をテストしてください。

## <a name="track-campaign-ids"></a>キャンペーン ID を追跡する

Bookingsカレンダーの過去 4 か月間のアクティビティを示すレポート (TSV ファイル) をダウンロードすることで、キャンペーンの動作を追跡できます。 TSV ファイルには 4 か月間のデータが表示されますが、1 年間に異なる 4 か月間を選択できます。 レポートをダウンロードする方法の詳細については、「[Bookingsのレポート情報」を](reporting-info.md)参照してください。
