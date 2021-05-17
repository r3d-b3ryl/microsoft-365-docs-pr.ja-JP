---
title: Bookings でサービス提供を定義する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: サービス名、説明、場所、期間、価格などのサービス提供情報を入力する手順。 また、サービスを提供する資格がある従業員にタグを付けることもできます。
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962539"
---
# <a name="define-your-service-offerings-in-bookings"></a><span data-ttu-id="ae0c4-104">Bookings でサービス提供を定義する</span><span class="sxs-lookup"><span data-stu-id="ae0c4-104">Define your service offerings in Bookings</span></span>

<span data-ttu-id="ae0c4-105">Microsoft Bookings でサービス提供を定義する場合は、サービス名、説明、場所 (対人会議またはオンライン会議の開催を選択)、期間、顧客とスタッフへの既定のリマインダー、サービスに関する内部メモ、価格設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-105">When you define your service offerings in Microsoft Bookings, you set, a service name, description, location (choose whether you want to meet in person or have an online meeting), duration, default reminders to customers and staff, internal notes about the service, and pricing.</span></span> <span data-ttu-id="ae0c4-106">また、サービスを提供する資格がある従業員にタグを付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-106">You can also tag the employees who are qualified to provide the service.</span></span> <span data-ttu-id="ae0c4-107">その後、顧客がビジネス Web サイトに来て予定を予約すると、利用可能な予定の種類、サービスを提供するユーザーの選択、およびサービスのコストを正確に確認できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-107">Then, when customers come to your business web site to book an appointment, they can see exactly what types of appointments are available, choose the person they want to provide the service, and how much their service will cost.</span></span>

<span data-ttu-id="ae0c4-108">また、ユーザーが予約ページからサービスを予約するときに送信するメールの確認とリマインダーに、カスタマイズされた情報と URL を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-108">You can also add customized information and URLs to the email confirmation and reminders that you send when someone books a service through your booking page.</span></span>

## <a name="create-the-service-details"></a><span data-ttu-id="ae0c4-109">サービスの詳細情報を作成する</span><span class="sxs-lookup"><span data-stu-id="ae0c4-109">Create the service details</span></span>

1. <span data-ttu-id="ae0c4-110">[サービスの管理] [ページに移動し、[](https://outlook.office.com/bookings/services) サービスの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-110">Go to the [Manage services page](https://outlook.office.com/bookings/services) and select **Add a service**.</span></span>

2. <span data-ttu-id="ae0c4-111">**サービス名**: サービスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-111">**Service name**: enter the name of your service.</span></span> <span data-ttu-id="ae0c4-112">これは、[予定表] ページのドロップダウン メニューに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-112">This is the name that will appear in the drop-down menu on the Calendar page.</span></span> <span data-ttu-id="ae0c4-113">この名前は、[予定表] ページに予定を手動で追加すると表示され、[セルフサービス] ページにタイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-113">This name will also appear when anyone manually adds an appointment on the Calendar page, and it will appear as a tile on the Self-service page.</span></span>

3. <span data-ttu-id="ae0c4-114">**説明**: ユーザーがセルフサービス ページの情報アイコンをクリックすると、入力した説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-114">**Description**: The description you enter is what will appear when a user clicks the information icon on the Self-service page.</span></span>

4. <span data-ttu-id="ae0c4-115">**既定の** 場所: この場所は、スタッフと顧客の両方の確認メールとリマインダー メールに表示される場所であり、予約用に作成された予定表イベントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-115">**Default location**: This location is what will be displayed on confirmation and reminder emails for both staff and customers, and it will be displayed on the calendar event created for the booking.</span></span>

5. <span data-ttu-id="ae0c4-116">**オンライン会議の追加**: この設定は、スタッフ メンバーの既定のクライアントとして構成する予定に応じて、Teams または Skype を介して、各予定のオンライン会議を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-116">**Add online meeting**: This setting enables or disables online meetings for each appointment, either via Teams or Skype, depending on which one you configure as the default client for the staff member.</span></span>

    - <span data-ttu-id="ae0c4-117">有効:</span><span class="sxs-lookup"><span data-stu-id="ae0c4-117">Enabled:</span></span>

        - <span data-ttu-id="ae0c4-118">予約に固有の Teams または Skype 会議へのリンクが、スタッフと顧客の予定表の両方の予定表イベントにダイヤルイン情報と共に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-118">A link to a Teams or Skype meeting, unique to the booking, will be added to the calendar event on both the staff's and the customers' calendars, along with dial-in information.</span></span>
        - <span data-ttu-id="ae0c4-119">会議に参加するリンクは、次の例に示すように、すべての確認メールとリマインダー メールに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-119">The link to join the meeting will be added to all confirmation and reminder emails, as shown in the following example:</span></span>

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Bookings で会議に参加Teamsリンクの例":::

        > [!NOTE]
        > <span data-ttu-id="ae0c4-121">Teams会議は、Teams モバイル アプリ、Teams デスクトップ アプリ、Web ブラウザー、または電話ダイヤルインを介して参加できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-121">Teams meetings can be joined via the Teams mobile app, the Teams desktop app, in a Web browser, or via the phone dial-in.</span></span> <span data-ttu-id="ae0c4-122">仮想予定の予約をTeams最適なエクスペリエンスを得る上で、テナントの既定のオンライン会議サービスとして会議を有効にすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-122">We strongly recommend enabling Teams as the default online meeting service for your tenant, for the best experience booking virtual appointments.</span></span>

    - <span data-ttu-id="ae0c4-123">無効:</span><span class="sxs-lookup"><span data-stu-id="ae0c4-123">Disabled:</span></span>
        - <span data-ttu-id="ae0c4-124">予定には会議オプションが含まれるのではなく、オンライン会議の追加が有効になっているときに表示される会議関連のすべてのフィールドは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-124">Appointments will not contain a meeting option, and all of the meeting-related fields that appear when **Add online meeting** is enabled will not be shown.</span></span>

6. <span data-ttu-id="ae0c4-125">**既定の期間**: これは、すべての会議を予約する期間です。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-125">**Default duration**: This is how long all meetings will be booked for.</span></span> <span data-ttu-id="ae0c4-126">時刻は、予約中に選択された開始時刻からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-126">The time is blocked beginning from the start time, which is selected during booking.</span></span> <span data-ttu-id="ae0c4-127">スタッフの予定表では、完全な予定時間がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-127">The full appointment time will be blocked on the staff's calendars.</span></span>

7. <span data-ttu-id="ae0c4-128">**顧客が予約できない** バッファー時間 : この設定を有効にすると、予定が予約されるごとにスタッフの予定表に余分な時間を追加できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-128">**Buffer time your customer can’t book**: Enabling this setting allows for the addition of extra time to the staff’s calendar every time an appointment is booked.</span></span>

    <span data-ttu-id="ae0c4-129">時間はスタッフの予定表でブロックされ、空き時間情報に影響します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-129">The time will be blocked on the staff’s calendar and impact free/busy information.</span></span> <span data-ttu-id="ae0c4-130">つまり、予定が午後 3 時に終了し、10 分間のバッファー時間が会議の最後に追加された場合、スタッフの予定表は午後 3 時 10 分までビジー状態で予約不可として表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-130">This means if an appointment ends at 3:00 pm and 10 minutes of buffer time has been added to the end of the meeting, the staff’s calendar will show as busy and non-bookable until 3:10pm.</span></span> <span data-ttu-id="ae0c4-131">これは、患者のグラフを確認する医師や、関連するアカウント情報を準備する財務アドバイザーなど、会議の準備に時間が必要な場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-131">This can be useful if your staff needs time before a meeting to prepare, such as a doctor reviewing a patient’s chart, or a financial advisor preparing relevant account information.</span></span> <span data-ttu-id="ae0c4-132">他のユーザーが別の場所に移動する時間が必要な場合など、会議の後にも便利です。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-132">It can also be useful after a meeting, such as when someone needs time to travel to another location.</span></span>

8. <span data-ttu-id="ae0c4-133">**顧客が予約** を管理する : この設定は、予約が Bookings Web アプリの [予定表] タブで予約されている場合に、顧客が予約を変更またはキャンセルできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-133">**Let the customer manage their booking**: This setting determines whether or notthe customer can modify or cancel their booking, provided it was booked through the Calendar tab on the Bookings Web app.</span></span>

    - <span data-ttu-id="ae0c4-134">有効:</span><span class="sxs-lookup"><span data-stu-id="ae0c4-134">Enabled:</span></span>

        <span data-ttu-id="ae0c4-135">[ **予約の管理]** ボタンが顧客確認メールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-135">The **Manage Booking** button appears on the customer confirmation email.</span></span> <span data-ttu-id="ae0c4-136">このボタンを顧客が選択すると、次の 3 つのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-136">When this button is selected by the customer, three options appear:</span></span>
        - <span data-ttu-id="ae0c4-137">**再スケジュール** このオプションを選択すると、ユーザーはサービス固有の Self-Service ページに移動し、元の予約から同じサービスと同じスタッフ メンバーの新しい日時を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-137">**Reschedule** Selecting this option brings the user to a service-specific Self-Service page, where they can select a new time and/or date for the same service and same staff member from the original booking.</span></span> <span data-ttu-id="ae0c4-138">既定では、元のスタッフ メンバーが再スケジュールされた予約に接続されている場合でも、スタッフ メンバーを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-138">Note that even though the original staff member is attached to the rescheduled booking by default, the user does have the option of changing the staff member as well.</span></span>
        - <span data-ttu-id="ae0c4-139">**予約のキャンセル** これにより、予約が取り消され、スタッフの予定表から削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-139">**Cancel booking** This cancels the booking and removes it from the staff's calendar.</span></span>
        - <span data-ttu-id="ae0c4-140">**新しい予約** このオプションを使用すると、新しいSelf-Serviceスケジュールを設定するために、すべてのサービスとスタッフが一覧表示されたページにユーザーが移動します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-140">**New booking** This option brings the user to the Self-Service page with all services and staff listed, for scheduling a new booking.</span></span>

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Bookings の [予約の管理] ボタン":::

        <span data-ttu-id="ae0c4-142">この設定は、ユーザーがページにアクセスする場合にのみ有効にSelf-Service勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-142">We only recommend leaving this setting enabled if you are comfortable with customers accessing the Self-Service page.</span></span>

    - <span data-ttu-id="ae0c4-143">無効:</span><span class="sxs-lookup"><span data-stu-id="ae0c4-143">Disabled:</span></span>

        <span data-ttu-id="ae0c4-144">ユーザーは、Bookings Web アプリの [予定表] タブから予約を行う際に予約を再スケジュールまたはキャンセルする機能を持つ必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-144">The user will have no ability to reschedule or cancel their booking when they book through the Calendar tab on the Bookings Web app.</span></span> <span data-ttu-id="ae0c4-145">ただし、[予約] ページSelf-Service、この設定が無効になっている場合でも、[予約の管理] ボタンとそのすべてのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-145">When booking through the Self-Service page, however, customers will still have the **Manage Booking** button and all of its options, even when this setting is disabled.</span></span>

        <span data-ttu-id="ae0c4-146">ページへのアクセスを制限する場合は、この設定をSelf-Service勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-146">We recommend disabling this setting if you want to limit access to the Self-Service page.</span></span> <span data-ttu-id="ae0c4-147">さらに、確認メールやリマインダーメールにテキストを追加し、その他の方法で予約を変更する方法 (オフィスに電話をしたり、ヘルプ デスクにメールを送るなど) を行う方法を顧客に伝えます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-147">Additionally, we suggest adding text to your confirmation and reminder emails that tells your customers how to make changes to their booking through other means, such as by calling the office or emailing the help desk.</span></span>

9. <span data-ttu-id="ae0c4-148">**イベントごとの最大出席者数** この設定では、複数のユーザーが同じ予定時間と同じスタッフ (フィットネス クラスなど) を予約する機能を必要とするサービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-148">**Maximum attendees per event** This setting allows you to create services that require the ability for multiple people to book the same appointment time and the same staff (such as a fitness class).</span></span> <span data-ttu-id="ae0c4-149">選択したサービス、スタッフ、および時間の予定タイム スロットは、ユーザーが指定した出席者の最大数に達するまで予約できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-149">The appointment time slot for the selected service, staff, and time will be available to book until the maximum number of attendees, specified by you, has been reached.</span></span> <span data-ttu-id="ae0c4-150">現在の予定の容量と出席者は、Bookings Web アプリの [予定表] タブで表示できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-150">Current appointment capacity and attendees can be viewed in the Calendar tab in the Bookings Web app.</span></span>

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Bookings で最大出席者数を設定する例":::

10. <span data-ttu-id="ae0c4-152">**既定の価格**  これは、ページに表示される価格Self-Serviceです。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-152">**Default price**  This is the price that will display on the Self-Service page.</span></span> <span data-ttu-id="ae0c4-153">[ **価格が設定されていない** ] が選択されている場合、価格またはコストまたは価格への参照は表示されません。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-153">If **Price not set** is selected, then no price or reference to cost or pricing will appear.</span></span>

11. <span data-ttu-id="ae0c4-154">**メモ** このフィールドは、予約されたスタッフの予約イベント、および Bookings Web アプリの [予定表] タブに表示されるイベントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-154">**Notes** This field appears in the booking event for booked staff, as well as on the event that appears on the Calendar tab in the Bookings web app.</span></span>

12. <span data-ttu-id="ae0c4-155">**ユーザー設定フィールド** このセクションでは、顧客が正しく予約するために回答する必要がある場合に、質問を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-155">**Custom Fields** This section allows questions to be added, or removed, if the customer needs to answer any in order to successfully book.</span></span>

    - <span data-ttu-id="ae0c4-156">顧客の電子メール、電話番号、住所、メモは取り外し不可のフィールドですが、各フィールドの横にある[必須] の選択を解除すると、それらをオプションにできます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-156">Customer email, phone number, address, and notes are non-removable fields, but you can make them optional by deselecting **Required** beside each field.</span></span>

    - <span data-ttu-id="ae0c4-157">[質問の追加] を選択すると、複数の選択肢またはテキスト応答の **質問を追加できます**。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-157">You can add a multiple choice or text-response question by selecting **Add a question**.</span></span>

        <span data-ttu-id="ae0c4-158">ユーザー設定フィールドは、特定の予定が予約される度に必要な情報を収集するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-158">Custom fields can be useful when collecting information that is needed every time the specific appointment is booked.</span></span> <span data-ttu-id="ae0c4-159">例としては、診療所訪問前の保険会社、ローン相談のローンの種類、学術的なアドバイスのための主要な研究、または候補者の面接の申請者 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-159">Examples include insurance provider prior to a clinic visit, loan type for loan consultations, major of study for academic advising, or applicant ID for candidate interviews.</span></span>

13. <span data-ttu-id="ae0c4-160">**アラームと確認** どちらの種類の電子メールも、予定の前に指定した期間に、顧客、スタッフ メンバー、または両方に送信されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-160">**Reminders and Confirmations** Both types of emails are sent out to customers, staff members, or both, at a specified time period before the appointment.</span></span> <span data-ttu-id="ae0c4-161">好みに応じて、予定ごとに複数のメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-161">Multiple messages can be created for each appointment, according to your preference.</span></span>

    - <span data-ttu-id="ae0c4-162">既定の確認メールとアラーム メールには、顧客/クライアント名、スタッフ メンバーの名前、予約されたサービスまたは予定、予定の時刻など、予定に関する基本情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-162">The default confirmation and reminder emails include basic information about the appointment, such as the customer/client name, staff member's name, the service or appointment booked, and the time of the appointment.</span></span> <span data-ttu-id="ae0c4-163">オンライン会議の場合は、参加するリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-163">For online meetings, a link to join will also be included.</span></span> <span data-ttu-id="ae0c4-164">この設定が有効になっている場合 (手順 8 で前述したように) 予約を管理する機能も含めできます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-164">The ability to manage the booking can also be included, if this setting is enabled (as described above in step 8).</span></span>

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Bookings からの確認メール":::

    - <span data-ttu-id="ae0c4-166">必要に応じて、再スケジュールに関する情報や、顧客が予定に持ち込む必要があるものなど、ここに必要な追加のテキストを含めできます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-166">Optionally, you can include any additional text you would like here, such as information about rescheduling or what customers should bring for the appointment.</span></span> <span data-ttu-id="ae0c4-167">[電子メールの確認の追加情報] フィールドに表示される、元の確認メールに追加されたカスタマイズされたテキスト **の例を次に示** します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-167">The following is an example of customized text added to the original confirmation email, seen in the **Additional information for Email Confirmation** field:</span></span>

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Bookings メールの追加情報":::

14. <span data-ttu-id="ae0c4-169">**顧客のテキスト メッセージ通知を有効にする** 選択されている場合携帯ショートメールメッセージは顧客に送信されますが、オプトインした場合にのみ送信されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-169">**Enable text message notifications for your customer** If selected, SMS messages are sent to the customer, but only if they opt-in.</span></span>

    - <span data-ttu-id="ae0c4-170">手動の予約とページの [オプトイン] ボックスSelf-Serviceします。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-170">Opt-in box on the manual booking and Self-Service Page:</span></span>

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Bookings のオプトイン ボックス":::

    - <span data-ttu-id="ae0c4-172">テキスト メッセージ通知は次のようになります (現在、携帯ショートメールは北米でのみ利用可能です)。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-172">Text message notifications will look like the following (note that SMS notifications are currently only available in North America):</span></span>

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Bookings からのテキスト通知":::

15. <span data-ttu-id="ae0c4-174">**発行オプション** このサービスを Self-Service ページで予約可能にするか、Bookings Web アプリの [予定表] タブでのみ予約可能にするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-174">**Publishing options** Choose whether to have this service appear as bookable on the Self-Service page, or to make the service bookable only on the Calendar tab within the Bookings Web app.</span></span>

16. <span data-ttu-id="ae0c4-175">**スケジュール ポリシー** この設定では、予定時間の表示方法と、予約の作成またはキャンセルが可能な期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-175">**Scheduling Policy** This setting determines how appointment times are viewed, and the time period in which bookings can be made or cancelled.</span></span>

17. <span data-ttu-id="ae0c4-176">**電子メール通知** 組織のスタッフと顧客またはクライアントに電子メールを送信する時間を設定します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-176">**Email notifications** Sets when emails are sent to organization staff and to customers or clients.</span></span>

18. <span data-ttu-id="ae0c4-177">**スタッフ** このチェック ボックスをオンにすると、顧客またはクライアントは予定の特定のスタッフ メンバーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-177">**Staff** Selecting this checkbox allows customers or clients to choose a specific staff member for their appointment.</span></span>

    - <span data-ttu-id="ae0c4-178">有効:</span><span class="sxs-lookup"><span data-stu-id="ae0c4-178">Enabled:</span></span>

        <span data-ttu-id="ae0c4-179">顧客は、予約時に予定に割り当てられたすべてのスタッフから、予約ページSelf-Serviceできます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-179">Customers can choose from all staff assigned to the appointment when booking on the Self-Service page.</span></span> <span data-ttu-id="ae0c4-180">[すべてのユーザー] の **オプションを** 選択すると、予約は予定に割り当てる利用可能なスタッフ メンバーをランダムに選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-180">Selecting the option of **Anyone** will make Bookings choose an available staff member at random to assign to the appointment.</span></span>

    - <span data-ttu-id="ae0c4-181">無効:</span><span class="sxs-lookup"><span data-stu-id="ae0c4-181">Disabled:</span></span>

        <span data-ttu-id="ae0c4-182">[サービス] ページからSelf-Service、サービスと日時を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-182">Customers booking via the Self-Service page can select a service and a time and date.</span></span> <span data-ttu-id="ae0c4-183">利用可能なスタッフはランダムに予約されます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-183">The available staff will be booked at random.</span></span> <span data-ttu-id="ae0c4-184">Bookings Web アプリの [予定表] タブで予約すると、特定のスタッフを引き続き選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-184">Note that specific staff can still be selected when booked through the Calendar tab in the Bookings Web app.</span></span>

19. <span data-ttu-id="ae0c4-185">**可用性** 次のオプションは、サービスを予約できる時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-185">**Availability** The following options determine when the service can be booked:</span></span>

    - <span data-ttu-id="ae0c4-186">**スタッフが無料の場合は予約可能** サービスは、スタッフが営業時間内に空き時間に基づいて空き時間を維持します。時間の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-186">**Bookable when staff are free** The service maintains availability based on when staff are free within business hours, with no extra time restrictions.</span></span>

    - <span data-ttu-id="ae0c4-187">**カスタム時間 (毎週繰り返し)** サービスには、さらに制限できる可用性の層が追加されています (営業時間またはスタッフの時間による制限に加えて)。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-187">**Custom hours (recurring weekly)** The service has an added layer of availability that can be further restricted (in addition to restricting by business hours or with staff hours).</span></span> <span data-ttu-id="ae0c4-188">サービスが特定の時間にのみ提供または実行できる場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-188">Use this option when your service can only be provided or performed at a specific time.</span></span>

    - <span data-ttu-id="ae0c4-189">**日付範囲に異なる可用性を設定する** この設定は、定期的にではなく、特定の時点での可用性に影響します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-189">**Set different availability for a date range** This setting impacts availability at a specific point in time, instead of a recurring basis.</span></span> <span data-ttu-id="ae0c4-190">たとえば、サービスに必要なコンピューターが一時的にサービスを受け、使用できない場合、または休日のために組織が閉じている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-190">For example, this could be used when a machine that is needed for the service is temporarily being serviced and unavailable, or when an organization is closed for a holiday.</span></span>

20. <span data-ttu-id="ae0c4-191">**スタッフの割り当て** 特定のサービスで予約可能なスタッフ ([スタッフ] タブにスタッフ メンバーが追加されている場合) を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-191">**Assign Staff** Select the staff (provided you have added staff members to the Staff tab) who will be bookable for that specific service.</span></span> <span data-ttu-id="ae0c4-192">個々のスタッフを選択すると、すべてのスタッフがサービスに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ae0c4-192">Selecting no individual staff will result in all staff being assigned to the service.</span></span>