---
title: Microsoft Bookings で言語とタイム ゾーンを設定する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: Microsoft 予約の言語とタイムゾーンの設定を変更します。 予約が誤って作成された場合は、間違ったタイムゾーンに対して予約が設定されている可能性があります。
ms.openlocfilehash: 3e7709666d6426b11c275e46a18d43e7b7ab3526
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962433"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a><span data-ttu-id="2be76-104">Microsoft Bookings で言語とタイム ゾーンを設定する</span><span class="sxs-lookup"><span data-stu-id="2be76-104">Set language and time zones in Microsoft Bookings</span></span>

<span data-ttu-id="2be76-105">Microsoft の予約を使用していて、予約が間違った時刻に作成されている場合は、タイムゾーンの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be76-105">If you are using Microsoft Bookings and bookings are created at the wrong time, then your time zone settings might need to be changed.</span></span> <span data-ttu-id="2be76-106">同様に、一部の予約が間違った言語である場合は、言語設定の変更が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2be76-106">Likewise, if some bookings are in the wrong language, you might need to change your language settings.</span></span>

<span data-ttu-id="2be76-107">予約には、2つの異なる言語とタイムゾーンの設定があります。</span><span class="sxs-lookup"><span data-stu-id="2be76-107">There are two separate language and time zone settings for Bookings.</span></span> <span data-ttu-id="2be76-108">最初の設定は予約予定表の言語とタイムゾーンを制御し、ログインしているユーザーの個人用予定表の Outlook on the web 設定を使用して設定されます。</span><span class="sxs-lookup"><span data-stu-id="2be76-108">The first setting controls the language and time zone of the booking calendar and is set using the Outlook on the web settings for the personal calendar of the logged-in user.</span></span> <span data-ttu-id="2be76-109">2番目の設定は、顧客が使用するセルフサービス予約ページに影響し、そのページの言語とタイムゾーンのみを制御する [地域の設定] ページを使用して設定されます。</span><span class="sxs-lookup"><span data-stu-id="2be76-109">The second setting affects the self-service booking page that your customers use and is set using a "regional settings" page that controls language and time zone only for that page.</span></span>

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a><span data-ttu-id="2be76-110">予約予定表の言語とタイム ゾーンの設定</span><span class="sxs-lookup"><span data-stu-id="2be76-110">Setting language and time zone for a booking calendar</span></span>

<span data-ttu-id="2be76-111">予約予定表は、ログインしているユーザーの言語とタイムゾーンの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="2be76-111">The booking calendar uses the logged-in user’s language and time zone settings.</span></span> <span data-ttu-id="2be76-112">たとえば、ログインしているユーザーのタイムゾーンが東部標準時 (EST) に設定されている場合、予約予定表には既存の予定の開始時刻と終了時刻が EST で表示されます。</span><span class="sxs-lookup"><span data-stu-id="2be76-112">For example, If the logged-in user’s time zone is set to Eastern Standard Time (EST), then the booking calendar will show existing appointment start and end times in EST.</span></span> <span data-ttu-id="2be76-113">このタイムゾーンは、最初はユーザーの Microsoft 365 および Outlook on the web アカウントが作成されたときに設定されていました。</span><span class="sxs-lookup"><span data-stu-id="2be76-113">This time zone was originally set when the user’s Microsoft 365 and Outlook on the web accounts were created.</span></span>

<span data-ttu-id="2be76-114">予約予定表の言語とタイムゾーンを設定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="2be76-114">To set the language and time zone for the booking calendar:</span></span>

1. <span data-ttu-id="2be76-115">Microsoft 365 にログインし、次のスクリーンショットに示されているように、ランディングページで Outlook タイルを選択するか、Microsoft 365 アプリ起動ツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2be76-115">Log into Microsoft 365 and select the Outlook tile on the landing page (as shown in the screenshot below) or in the Microsoft 365 App Launcher.</span></span>

   ![Microsoft 365 ランディングページの Outlook タイルの画像](../media/bookings-outlook-tile.png)

1. <span data-ttu-id="2be76-117">Outlook が起動したら、画面の右上隅にある **歯車アイコン** を選択して、個人およびアカウントの設定を開き、[ **設定** ] パネルの検索ボックスで [タイムゾーン] を検索します。</span><span class="sxs-lookup"><span data-stu-id="2be76-117">After Outlook opens, select the **gear icon** in the upper, right-hand corner of the screen to open your personal and account settings, then search for “time zone” in the **Settings** panel search box.</span></span> <span data-ttu-id="2be76-118">このアカウントの現在の個人の言語とタイム ゾーンの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2be76-118">The panel will update to show your current personal language and time zone settings for this account.</span></span> <span data-ttu-id="2be76-119">前に説明したように、この設定は、予約予定表の言語とタイム ゾーンも制御します。</span><span class="sxs-lookup"><span data-stu-id="2be76-119">As noted above, this setting also controls the language and time zone of the booking calendar.</span></span>

1. <span data-ttu-id="2be76-120">[言語] また **は [現在のタイムゾーン** ] ボックスのドロップダウン矢印を選択し、目的の設定を選択して、言語またはタイムゾーンを変更します。</span><span class="sxs-lookup"><span data-stu-id="2be76-120">Change the language or time zone by selecting the drop-down arrow in the **Language or Current time zone** box and choosing the desired setting.</span></span>

1. <span data-ttu-id="2be76-121">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2be76-121">Click **Save**.</span></span> <span data-ttu-id="2be76-122">設定パネルが閉じ、web 上の Outlook が再起動し、新しい言語とタイムゾーンの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2be76-122">The Settings panel closes, Outlook on the web restarts, and the new language and time zone settings are applied.</span></span>

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a><span data-ttu-id="2be76-123">予約ページの言語とタイム ゾーンの設定</span><span class="sxs-lookup"><span data-stu-id="2be76-123">Setting the language and time zone for the booking page</span></span>

1. <span data-ttu-id="2be76-124">Microsoft 365 で、アプリ起動ツールを選択し、[ **予約**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2be76-124">In Microsoft 365, select the app launcher, and then select **Bookings**.</span></span>

1. <span data-ttu-id="2be76-125">ナビゲーションウィンドウで、[ **予約ページ** ] を選択し、[ **言語とタイムゾーンの設定の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2be76-125">In the navigation pane, select **Booking page** and select **Change language and time zone settings**.</span></span>

   ![スクリーンショット: 言語とタイムゾーンの設定の変更リンク](../media/bookings-region-language-timezone-settings.png)

1. <span data-ttu-id="2be76-127">言語と現在のタイムゾーンを選択し、[OK] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2be76-127">Select your language and current time zone and choose OK.</span></span>

   ![スクリーンショット: 言語とタイムゾーンの設定](../media/bookings-region-timezone-settings.png)
