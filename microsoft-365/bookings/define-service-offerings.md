---
title: 予約でのサービス提供の定義
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: サービス名、説明、場所、期間、価格を含むサービスオファーリング情報の入力手順。 また、サービスを提供する資格がある従業員にタグを付けることもできます。
ms.openlocfilehash: 60b77633b9845b3c269f6773c1fb8a26256fbdc5
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419872"
---
# <a name="define-your-service-offerings-in-bookings"></a><span data-ttu-id="ee900-104">予約でのサービス提供の定義</span><span class="sxs-lookup"><span data-stu-id="ee900-104">Define your service offerings in Bookings</span></span>

<span data-ttu-id="ee900-105">Microsoft の予約でサービスオファーリングを定義するときは、サービス名、説明、場所 (個人を会議に参加するか、オンライン会議を開催するかを選択します)、期間、顧客とスタッフへの既定のアラーム、サービスに関する内部メモ、および価格を設定します。</span><span class="sxs-lookup"><span data-stu-id="ee900-105">When you define your service offerings in Microsoft Bookings, you set, a service name, description, location (choose whether you want to meet in person or have an online meeting), duration, default reminders to customers and staff, internal notes about the service, and pricing.</span></span> <span data-ttu-id="ee900-106">また、サービスを提供する資格がある従業員にタグを付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="ee900-106">You can also tag the employees who are qualified to provide the service.</span></span> <span data-ttu-id="ee900-107">次に、顧客がビジネス web サイトにアクセスして予定を予約したときに、どの種類の予定を利用できるようにするかを確認したり、サービスの提供を希望する人物を選択したり、サービスのコストをどの程度のものにするかを選択したりできます。</span><span class="sxs-lookup"><span data-stu-id="ee900-107">Then, when customers come to your business web site to book an appointment, they can see exactly what types of appointments are available, choose the person they want to provide the service, and how much their service will cost.</span></span>

<span data-ttu-id="ee900-108">予約ページを通じて他のユーザーがサービスにアクセスしたときに送信される電子メールの確認と事前通知に、カスタマイズされた情報と Url を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee900-108">You can also add customized information and URLs to the email confirmation and reminders that you send when someone books a service through your booking page.</span></span>

> [!NOTE]
> <span data-ttu-id="ee900-109">予約は、Microsoft 365 Business Standard、Microsoft 365 A3、または Microsoft 365 A5 サブスクリプションを使用しているお客様に対して、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="ee900-109">Bookings is turned on by default for customers who have the Microsoft 365 Business Standard, Microsoft 365 A3, or Microsoft 365 A5 subscriptions.</span></span> <span data-ttu-id="ee900-110">予約は、Office 365 Enterprise E3 および Office 365 Enterprise E5 を持つお客様も利用できますが、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="ee900-110">Bookings is also available to customers who have Office 365 Enterprise E3 and Office 365 Enterprise E5, but it is turned off by default.</span></span> <span data-ttu-id="ee900-111">開始するには、「 [Microsoft 予約へのアクセスを取得](get-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee900-111">To get started, see [Get access to Microsoft Bookings](get-access.md).</span></span> <span data-ttu-id="ee900-112">予約をオンまたはオフにするには、「 [組織の予約を有効または無効](turn-bookings-on-or-off.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee900-112">To turn Bookings on or off, see [Turn Bookings on or off for your organization](turn-bookings-on-or-off.md).</span></span>

## <a name="create-the-service-details"></a><span data-ttu-id="ee900-113">サービスの詳細情報を作成する</span><span class="sxs-lookup"><span data-stu-id="ee900-113">Create the service details</span></span>

1. <span data-ttu-id="ee900-114">[サービスの [管理] ページ](https://outlook.office.com/bookings/services) に移動し、[ **サービスの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee900-114">Go to the [Manage services page](https://outlook.office.com/bookings/services) and select **Add a service**.</span></span>

2. <span data-ttu-id="ee900-115">**サービス名**: サービスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ee900-115">**Service name**: enter the name of your service.</span></span> <span data-ttu-id="ee900-116">これは、[カレンダー] ページのドロップダウンメニューに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="ee900-116">This is the name that will appear in the drop-down menu on the Calendar page.</span></span> <span data-ttu-id="ee900-117">この名前は、予定表ページに手動で予定を追加した場合にも表示され、セルフサービスページにタイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-117">This name will also appear when anyone manually adds an appointment on the Calendar page, and it will appear as a tile on the Self-service page.</span></span>

3. <span data-ttu-id="ee900-118">**説明**: 入力する説明は、ユーザーがセルフサービスページの情報アイコンをクリックしたときに表示される内容です。</span><span class="sxs-lookup"><span data-stu-id="ee900-118">**Description**: The description you enter is what will appear when a user clicks the information icon on the Self-service page.</span></span>

4. <span data-ttu-id="ee900-119">**既定の場所**: この場所は、スタッフと顧客の両方の確認と事前通知の電子メールに表示され、予約用に作成された予定表イベントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-119">**Default location**: This location is what will be displayed on confirmation and reminder emails for both staff and customers, and it will be displayed on the calendar event created for the booking.</span></span>

5. <span data-ttu-id="ee900-120">**オンライン会議の追加**: この設定では、スタッフメンバーの既定のクライアントとして構成されているかどうかに応じて、Teams または Skype から、各予定のオンライン会議を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ee900-120">**Add online meeting**: This setting enables or disables online meetings for each appointment, either via Teams or Skype, depending on which one you configure as the default client for the staff member.</span></span>

    - <span data-ttu-id="ee900-121">い</span><span class="sxs-lookup"><span data-stu-id="ee900-121">Enabled:</span></span>

        - <span data-ttu-id="ee900-122">予約に固有の Teams または Skype 会議へのリンクは、スタッフと顧客の予定表の両方の予定表イベントに、ダイヤルイン情報と共に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-122">A link to a Teams or Skype meeting, unique to the booking, will be added to the calendar event on both the staff's and the customers' calendars, along with dial-in information.</span></span>
        - <span data-ttu-id="ee900-123">次の例に示すように、会議に参加するためのリンクは、すべての確認および事前通知の電子メールに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-123">The link to join the meeting will be added to all confirmation and reminder emails, as shown in the following example:</span></span>

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="「予約」の「Teams 会議に参加する」へのリンクの例":::

        > [!NOTE]
        > <span data-ttu-id="ee900-125">Teams 会議は、Teams モバイルアプリ、Teams デスクトップアプリ、Web ブラウザー、または電話ダイヤルイン経由で参加できます。</span><span class="sxs-lookup"><span data-stu-id="ee900-125">Teams meetings can be joined via the Teams mobile app, the Teams desktop app, in a Web browser, or via the phone dial-in.</span></span> <span data-ttu-id="ee900-126">最適な予約の仮想予定を作成するには、テナントの既定のオンライン会議サービスとして Teams を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ee900-126">We strongly recommend enabling Teams as the default online meeting service for your tenant, for the best experience booking virtual appointments.</span></span>

    - <span data-ttu-id="ee900-127">党</span><span class="sxs-lookup"><span data-stu-id="ee900-127">Disabled:</span></span>
        - <span data-ttu-id="ee900-128">予定には会議オプションは含まれず、 **オンライン会議の追加** が有効になっている場合に表示されるすべての会議関連フィールドは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ee900-128">Appointments will not contain a meeting option, and all of the meeting-related fields that appear when **Add online meeting** is enabled will not be shown.</span></span>

6. <span data-ttu-id="ee900-129">**既定の期間**: これは、すべての会議が予約される期間です。</span><span class="sxs-lookup"><span data-stu-id="ee900-129">**Default duration**: This is how long all meetings will be booked for.</span></span> <span data-ttu-id="ee900-130">時間は予約時に選択された開始時刻からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ee900-130">The time is blocked beginning from the start time, which is selected during booking.</span></span> <span data-ttu-id="ee900-131">完全な予定時間は、スタッフの予定表でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ee900-131">The full appointment time will be blocked on the staff's calendars.</span></span>

7. <span data-ttu-id="ee900-132">[**お客様が予約できないバッファー時間**]: この設定を有効にすると、予定が予約されるたびにスタッフの予定表に追加の時間を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ee900-132">**Buffer time your customer can’t book**: Enabling this setting allows for the addition of extra time to the staff’s calendar every time an appointment is booked.</span></span>

    <span data-ttu-id="ee900-133">この時間は、スタッフの予定表ではブロックされ、空き時間情報に影響します。</span><span class="sxs-lookup"><span data-stu-id="ee900-133">The time will be blocked on the staff’s calendar and impact free/busy information.</span></span> <span data-ttu-id="ee900-134">これは、予定が 3:00 pm に終了し、バッファー時間が10分後に会議の最後に追加された場合に、スタッフの予定表が [取り込み中] と [10pm] ではなく、3: まで表示されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ee900-134">This means if an appointment ends at 3:00 pm and 10 minutes of buffer time has been added to the end of the meeting, the staff’s calendar will show as busy and non-bookable until 3:10pm.</span></span> <span data-ttu-id="ee900-135">これは、患者のグラフを確認する医師や、関連するアカウント情報を準備する財務顧問など、スタッフが準備を行う前に時間を必要とする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ee900-135">This can be useful if your staff needs time before a meeting to prepare, such as a doctor reviewing a patient’s chart, or a financial advisor preparing relevant account information.</span></span> <span data-ttu-id="ee900-136">他の場所に移動する時間が必要になった場合など、会議の後にも役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="ee900-136">It can also be useful after a meeting, such as when someone needs time to travel to another location.</span></span>

8. <span data-ttu-id="ee900-137">**お客様に予約の管理を許可**します。この設定により、お客様は、予約 Web アプリの [予定表] タブで予約されていた場合に、その予約を変更またはキャンセルできるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ee900-137">**Let the customer manage their booking**: This setting determines whether or notthe customer can modify or cancel their booking, provided it was booked through the Calendar tab on the Bookings Web app.</span></span>

    - <span data-ttu-id="ee900-138">い</span><span class="sxs-lookup"><span data-stu-id="ee900-138">Enabled:</span></span>

        <span data-ttu-id="ee900-139">[ **予約の管理** ] ボタンが、顧客の確認メールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-139">The **Manage Booking** button appears on the customer confirmation email.</span></span> <span data-ttu-id="ee900-140">お客様がこのボタンを選択すると、次の3つのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-140">When this button is selected by the customer, three options appear:</span></span>
        - <span data-ttu-id="ee900-141">再**スケジュール**このオプションを選択すると、サービス固有のセルフサービスページが表示されます。このページでは、同じサービスの新しい日時や、元の予約と同じスタッフメンバーを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="ee900-141">**Reschedule** Selecting this option brings the user to a service-specific Self-Service page, where they can select a new time and/or date for the same service and same staff member from the original booking.</span></span> <span data-ttu-id="ee900-142">既定では、元のスタッフメンバーが再スケジュールされた予約に関連付けられている場合でも、ユーザーはスタッフメンバーも変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ee900-142">Note that even though the original staff member is attached to the rescheduled booking by default, the user does have the option of changing the staff member as well.</span></span>
        - <span data-ttu-id="ee900-143">**予約のキャンセル** これにより、予約が取り消され、スタッフの予定表から削除されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-143">**Cancel booking** This cancels the booking and removes it from the staff's calendar.</span></span>
        - <span data-ttu-id="ee900-144">**新しい予約** このオプションを選択すると、新しい予約を予約するために、すべてのサービスとスタッフが一覧表示されたセルフサービスページにユーザーが移動します。</span><span class="sxs-lookup"><span data-stu-id="ee900-144">**New booking** This option brings the user to the Self-Service page with all services and staff listed, for scheduling a new booking.</span></span>

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="予約の [予約の管理] ボタン":::

        <span data-ttu-id="ee900-146">セルフサービスページにアクセスするお客様に慣れている場合にのみ、この設定を有効にしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ee900-146">We only recommend leaving this setting enabled if you are comfortable with customers accessing the Self-Service page.</span></span>

    - <span data-ttu-id="ee900-147">党</span><span class="sxs-lookup"><span data-stu-id="ee900-147">Disabled:</span></span>

        <span data-ttu-id="ee900-148">予約 Web アプリの [予定表] タブで予約されている場合、ユーザーは予約を再スケジュールまたはキャンセルすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ee900-148">The user will have no ability to reschedule or cancel their booking when they book through the Calendar tab on the Bookings Web app.</span></span> <span data-ttu-id="ee900-149">ただし、セルフサービスページを通じて予約する場合は、この設定を無効にしても、お客様は [ **予約の管理** ] ボタンとすべてのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee900-149">When booking through the Self-Service page, however, customers will still have the **Manage Booking** button and all of its options, even when this setting is disabled.</span></span>

        <span data-ttu-id="ee900-150">セルフサービスページへのアクセスを制限する場合は、この設定を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ee900-150">We recommend disabling this setting if you want to limit access to the Self-Service page.</span></span> <span data-ttu-id="ee900-151">また、office を呼び出したり、ヘルプデスクに電子メールで送信したりするなど、他の手段を通じて予約を変更する方法についてお客様に知らせるために、確認と事前通知の電子メールにテキストを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ee900-151">Additionally, we suggest adding text to your confirmation and reminder emails that tells your customers how to make changes to their booking through other means, such as by calling the office or emailing the help desk.</span></span>

9. <span data-ttu-id="ee900-152">**イベント1人あたりの最大出席者** 数この設定では、複数のユーザーが同じ予約時間と同じスタッフ (フィットネスクラスなど) を予約することを必要とするサービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ee900-152">**Maximum attendees per event** This setting allows you to create services that require the ability for multiple people to book the same appointment time and the same staff (such as a fitness class).</span></span> <span data-ttu-id="ee900-153">選択したサービス、スタッフ、および時間の予定時間帯は、自分が指定した出席者の最大数に達するまで、予約が可能になります。</span><span class="sxs-lookup"><span data-stu-id="ee900-153">The appointment time slot for the selected service, staff, and time will be available to book until the maximum number of attendees, specified by you, has been reached.</span></span> <span data-ttu-id="ee900-154">現在の予定の容量と出席者は、予約 Web アプリの [予定表] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-154">Current appointment capacity and attendees can be viewed in the Calendar tab in the Bookings Web app.</span></span>

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="予約の最大出席者を設定する例":::

10. <span data-ttu-id="ee900-156">**既定の価格**  これは、セルフサービスページに表示される価格です。</span><span class="sxs-lookup"><span data-stu-id="ee900-156">**Default price**  This is the price that will display on the Self-Service page.</span></span> <span data-ttu-id="ee900-157">[価格] が設定され **てい** ない場合は、料金または価格に対する参照は表示されません。</span><span class="sxs-lookup"><span data-stu-id="ee900-157">If **Price not set** is selected, then no price or reference to cost or pricing will appear.</span></span>

11. <span data-ttu-id="ee900-158">**メモ** このフィールドは、予約済みスタッフの予約イベント、および予約 web アプリの [予定表] タブに表示されるイベントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-158">**Notes** This field appears in the booking event for booked staff, as well as on the event that appears on the Calendar tab in the Bookings web app.</span></span>

12. <span data-ttu-id="ee900-159">**ユーザー設定フィールド** このセクションでは、お客様が適切な予約を行うために回答する必要がある場合に、質問を追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ee900-159">**Custom Fields** This section allows questions to be added, or removed, if the customer needs to answer any in order to successfully book.</span></span>

    - <span data-ttu-id="ee900-160">お客様のメール、電話番号、住所、メモは取り外し可能なフィールドではありませんが、各フィールドの横の [ **必須** ] をオフにすることによってオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ee900-160">Customer email, phone number, address, and notes are non-removable fields, but you can make them optional by deselecting **Required** beside each field.</span></span>

    - <span data-ttu-id="ee900-161">[ **質問の追加**] を選択すると、複数選択またはテキスト応答の質問を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ee900-161">You can add a multiple choice or text-response question by selecting **Add a question**.</span></span>

        <span data-ttu-id="ee900-162">ユーザー設定フィールドは、特定の予定が予約されるたびに必要な情報を収集するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ee900-162">Custom fields can be useful when collecting information that is needed every time the specific appointment is booked.</span></span> <span data-ttu-id="ee900-163">例としては、クリニック訪問の前の保険会社、ローン consultations のための融資の種類、教育のための重要な調査のための、応募者 ID などが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="ee900-163">Examples include insurance provider prior to a clinic visit, loan type for loan consultations, major of study for academic advising, or applicant ID for candidate interviews.</span></span>

13. <span data-ttu-id="ee900-164">**アラームと** 確認両方の種類の電子メールは、予定の前に指定された期間に顧客、スタッフメンバー、またはその両方に送信されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-164">**Reminders and Confirmations** Both types of emails are sent out to customers, staff members, or both, at a specified time period before the appointment.</span></span> <span data-ttu-id="ee900-165">ユーザーの設定に従って、各予定に対して複数のメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ee900-165">Multiple messages can be created for each appointment, according to your preference.</span></span>

    - <span data-ttu-id="ee900-166">既定の確認メッセージとアラームの電子メールには、お客様/クライアント名、スタッフメンバー名、サービスまたは予定の予約、予定時間など、予定に関する基本的な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee900-166">The default confirmation and reminder emails include basic information about the appointment, such as the customer/client name, staff member's name, the service or appointment booked, and the time of the appointment.</span></span> <span data-ttu-id="ee900-167">オンライン会議では、参加へのリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee900-167">For online meetings, a link to join will also be included.</span></span> <span data-ttu-id="ee900-168">この設定が有効になっている場合は、予約を管理する機能も含めることができます (上記の手順8を参照)。</span><span class="sxs-lookup"><span data-stu-id="ee900-168">The ability to manage the booking can also be included, if this setting is enabled (as described above in step 8).</span></span>

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="予約からの確認メール":::

    - <span data-ttu-id="ee900-170">必要に応じて、必要に応じて、再スケジュールに関する情報や、予定に必要な顧客を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ee900-170">Optionally, you can include any additional text you would like here, such as information about rescheduling or what customers should bring for the appointment.</span></span> <span data-ttu-id="ee900-171">次に、元の確認メールに追加された、[ **電子メールの追加情報** ] フィールドに表示されるカスタマイズされたテキストの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ee900-171">The following is an example of customized text added to the original confirmation email, seen in the **Additional information for Email Confirmation** field:</span></span>

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="予約メールの追加情報":::

14. <span data-ttu-id="ee900-173">**顧客に対してテキストメッセージ通知を有効にする** 選択されている場合、SMS メッセージは顧客に送信されますが、オプトインされている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="ee900-173">**Enable text message notifications for your customer** If selected, SMS messages are sent to the customer, but only if they opt-in.</span></span>

    - <span data-ttu-id="ee900-174">手動予約およびセルフサービスページのオプトインボックス:</span><span class="sxs-lookup"><span data-stu-id="ee900-174">Opt-in box on the manual booking and Self-Service Page:</span></span>

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="予約のオプトインボックス":::

    - <span data-ttu-id="ee900-176">テキストメッセージ通知は次のようになります (現時点では、SMS 通知は北アメリカでのみ利用可能であることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="ee900-176">Text message notifications will look like the following (note that SMS notifications are currently only available in North America):</span></span>

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="予約からのテキスト通知":::

15. <span data-ttu-id="ee900-178">**発行オプション** このサービスをセルフサービスページで能として表示するかどうかを選択するか、または予約 Web アプリ内の [予定表] タブでのみサービスを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ee900-178">**Publishing options** Choose whether to have this service appear as bookable on the Self-Service page, or to make the service bookable only on the Calendar tab within the Bookings Web app.</span></span>

16. <span data-ttu-id="ee900-179">**スケジュールポリシー** この設定では、予定の時間を表示する方法、および予約を作成または取り消しできる期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee900-179">**Scheduling Policy** This setting determines how appointment times are viewed, and the time period in which bookings can be made or cancelled.</span></span>

17. <span data-ttu-id="ee900-180">**電子メール通知** 電子メールを組織のスタッフおよび顧客またはクライアントに送信するタイミングを設定します。</span><span class="sxs-lookup"><span data-stu-id="ee900-180">**Email notifications** Sets when emails are sent to organization staff and to customers or clients.</span></span>

18. <span data-ttu-id="ee900-181">**スタッフ** このチェックボックスをオンにすると、顧客またはクライアントが自分の予定に対して特定のスタッフメンバーを選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ee900-181">**Staff** Selecting this checkbox allows customers or clients to choose a specific staff member for their appointment.</span></span>

    - <span data-ttu-id="ee900-182">い</span><span class="sxs-lookup"><span data-stu-id="ee900-182">Enabled:</span></span>

        <span data-ttu-id="ee900-183">お客様は、セルフサービスページで予約する際に、予定に割り当てられているすべてのスタッフから選択できます。</span><span class="sxs-lookup"><span data-stu-id="ee900-183">Customers can choose from all staff assigned to the appointment when booking on the Self-Service page.</span></span> <span data-ttu-id="ee900-184">[ **すべてのユーザー** ] のオプションを選択すると、予定に割り当てるために、ランダムに利用可能なスタッフメンバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ee900-184">Selecting the option of **Anyone** will make Bookings choose an available staff member at random to assign to the appointment.</span></span>

    - <span data-ttu-id="ee900-185">党</span><span class="sxs-lookup"><span data-stu-id="ee900-185">Disabled:</span></span>

        <span data-ttu-id="ee900-186">セルフサービスページ経由で予約している顧客は、サービスと時刻と日付を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ee900-186">Customers booking via the Self-Service page can select a service and a time and date.</span></span> <span data-ttu-id="ee900-187">利用可能なスタッフはランダムに予約されます。</span><span class="sxs-lookup"><span data-stu-id="ee900-187">The available staff will be booked at random.</span></span> <span data-ttu-id="ee900-188">予約 Web アプリの [予定表] タブを通じて、特定のスタッフが選択されたままになっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ee900-188">Note that specific staff can still be selected when booked through the Calendar tab in the Bookings Web app.</span></span>

19. <span data-ttu-id="ee900-189">**可用性** 次のオプションを使用して、サービスを予約できる時期を決定します。</span><span class="sxs-lookup"><span data-stu-id="ee900-189">**Availability** The following options determine when the service can be booked:</span></span>

    - <span data-ttu-id="ee900-190">**スタッフが空いている場合の bookableこのサービスは、営業時間内にスタッフが空いている時期に基づいて可用性を維持し、付加的な時間制限はありません。**</span><span class="sxs-lookup"><span data-stu-id="ee900-190">**Bookable when staff are free** The service maintains availability based on when staff are free within business hours, with no extra time restrictions.</span></span>

    - <span data-ttu-id="ee900-191">**ユーザー設定の時間 (定期的に週単位)** このサービスには、さらに制限できる追加の可用性層があります (営業時間単位またはスタッフ時間での制限に加えて)。</span><span class="sxs-lookup"><span data-stu-id="ee900-191">**Custom hours (recurring weekly)** The service has an added layer of availability that can be further restricted (in addition to restricting by business hours or with staff hours).</span></span> <span data-ttu-id="ee900-192">特定の時間にサービスを提供または実行できるようにする場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee900-192">Use this option when your service can only be provided or performed at a specific time.</span></span>

    - <span data-ttu-id="ee900-193">**日付範囲のさまざまな可用性を設定する** この設定は、定期的なものではなく、特定の時点での可用性に影響します。</span><span class="sxs-lookup"><span data-stu-id="ee900-193">**Set different availability for a date range** This setting impacts availability at a specific point in time, instead of a recurring basis.</span></span> <span data-ttu-id="ee900-194">たとえば、サービスに必要なコンピューターが一時的にサービスと使用不能になっている場合や、休日に対して組織が閉鎖されている場合に、これを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ee900-194">For example, this could be used when a machine that is needed for the service is temporarily being serviced and unavailable, or when an organization is closed for a holiday.</span></span>

20. <span data-ttu-id="ee900-195">**スタッフの割り当て** スタッフを選択し (スタッフメンバーを [スタッフ] タブに追加している場合)、その特定のサービスに対して書籍を提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ee900-195">**Assign Staff** Select the staff (provided you have added staff members to the Staff tab) who will be bookable for that specific service.</span></span> <span data-ttu-id="ee900-196">個々のスタッフを選択しないと、すべてのスタッフがサービスに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ee900-196">Selecting no individual staff will result in all staff being assigned to the service.</span></span>