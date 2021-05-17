---
title: 予約ページにカスタムおよび必須の質問を追加する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: オンラインで予定を予約するときに顧客に質問する必要がある場合は、予約ページにカスタムの質問と必要な質問を追加できます。
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419900"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="1f380-103">予約ページにカスタムおよび必須の質問を追加する</span><span class="sxs-lookup"><span data-stu-id="1f380-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="1f380-104">予約を使用すると、顧客が予定を予約するときに質問を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="1f380-105">また、必要な質問を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="1f380-106">質問をサービスに関連付けるので、各サービスに異なる質問セットを設定できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="1f380-107">たとえば、ヘアスタイリストは、ヘアカラーの予定を予約している顧客に、ブリーチやティントに対する既知のアレルギーを持っている場合に尋ねる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f380-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="1f380-108">これにより、ユーザーと顧客は予定の到着時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="1f380-109">予約ページで予定を作成するときに、カスタムの質問が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f380-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="1f380-110">スタッフは、予約カレンダーから新しい予約を作成するか、既存の予定を表示するときに、カスタムの質問を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f380-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="1f380-111">Bookings は、すべての質問をマスター リストに保存し、すべてのサービスに対して同じ質問を再作成する必要が生じないのでします。</span><span class="sxs-lookup"><span data-stu-id="1f380-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="1f380-112">また、質問が必須かオプションかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="1f380-113">質問に対する顧客の回答は、予約カレンダーで予定を確認すると確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="1f380-114">予約ページをカスタマイズしてカスタマイズする方法の詳細については、「予約ページをカスタマイズ [する」を参照してください](customize-booking-page.md)。</span><span class="sxs-lookup"><span data-stu-id="1f380-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="1f380-115">サービスにカスタム質問を追加する</span><span class="sxs-lookup"><span data-stu-id="1f380-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="1f380-116">サインインして[予約] Microsoft 365に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="1f380-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="1f380-117">[サービス] **に移動** し、既存のサービスを編集するか、[ **サービスの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f380-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="1f380-118">[ユーザー設定フィールド] **セクションまで下にスクロール** し、[変更] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f380-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="1f380-119">顧客の電子メール、電話番号、顧客住所、顧客メモなど、基本的な顧客情報に関する質問が既に追加されています。</span><span class="sxs-lookup"><span data-stu-id="1f380-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="1f380-120">これを初めて行う場合、顧客情報の質問は灰色で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f380-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="1f380-121">つまり、ユーザーにこの質問が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f380-121">That means that the user will see this question.</span></span> <span data-ttu-id="1f380-122">質問を選択すると、その周囲の強調表示ボックスが表示されなくなり、顧客にはその質問は表示されません。</span><span class="sxs-lookup"><span data-stu-id="1f380-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="1f380-123">この例では、電話番号と顧客メモがオフになっていて、2 つの新しいカスタム質問を作成しました。</span><span class="sxs-lookup"><span data-stu-id="1f380-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![カスタム質問画面の画像](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="1f380-125">質問を必須にする場合は、[必須] チェック **ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="1f380-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="1f380-126">顧客が必要な質問に答えるまで、予約を完了できない。</span><span class="sxs-lookup"><span data-stu-id="1f380-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="1f380-127">カスタム質問を作成するには、パネル **の上部から** [質問の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f380-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="1f380-128">質問を書き込み、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f380-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="1f380-129">質問をクリックして有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="1f380-129">Click on the question to enable it.</span></span> <span data-ttu-id="1f380-130">強調表示されたボックスが周囲に表示され、質問が有効になります。</span><span class="sxs-lookup"><span data-stu-id="1f380-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="1f380-131">ページ **の上部にある [OK]** をクリックし、[サービス **の保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f380-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="1f380-132">予約では、すべてのカスタム質問がマスター リストに保存されますので、同じ質問を繰り返し入力する必要なく、各サービスに簡単に質問を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="1f380-133">たとえば、別のサービスを開いた場合、最初のサービス用に作成した質問は [ユーザー設定フィールド] セクションに表示されますが、無効になります。</span><span class="sxs-lookup"><span data-stu-id="1f380-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="1f380-134">強調表示された四角形が表示され、質問が有効な場合は、質問をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f380-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="1f380-135">この例では、最初のサービスに追加された質問が、このサービスで利用できるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="1f380-136">このサービスに対して作成した質問は、すべてのサービスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-136">Any questions you create for this service will be available for all services.</span></span>

   ![複数のサービスに対して表示される質問のイメージ](../media/bookings-questions-services.png)

<span data-ttu-id="1f380-138">予約ページが既に公開されている場合は、他に何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1f380-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="1f380-139">顧客は、次回一緒に予約する場合に質問を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f380-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="1f380-140">予約ページがまだ公開されていない場合は、web サイトから予約ページに移動Outlookし、[保存して発行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f380-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="1f380-141">マスター リストから質問を削除できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="1f380-142">ただし、質問を削除すると、すべてのサービスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="1f380-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="1f380-143">質問を選択して、他のサービスに影響を及ぼすことを確認して無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1f380-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="1f380-144">強調表示された四角形に囲まれない場合は、質問が無効になっているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f380-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="1f380-145">カスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1f380-145">Customer experience</span></span>

<span data-ttu-id="1f380-146">顧客が予定を予約すると、基本的な顧客情報の質問が [詳細の追加 **] セクションに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="1f380-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="1f380-147">追加するカスタマイズされた質問は、[追加情報の提供 **] セクションに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="1f380-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![質問が有効な場合に表示されるユーザーのイメージ](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="1f380-149">スタッフエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1f380-149">Staff experience</span></span>

<span data-ttu-id="1f380-150">顧客が予定を予約すると、スタッフは予約カレンダーに質問と顧客の回答を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f380-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="1f380-151">それを表示するには、[予約カレンダー] **に移動** \> **し** 、予定を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f380-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![質問が有効な場合にスタッフに表示される画像](../media/bookings-questions-staff.png)
