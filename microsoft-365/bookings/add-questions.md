---
title: 予約ページにカスタムおよび必要な質問を追加する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: 予定をオンラインで予約するときにお客様に質問する必要がある場合は、カスタムの質問と必要な質問を予約ページに追加することができます。
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419900"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="7e28d-103">予約ページにカスタムおよび必要な質問を追加する</span><span class="sxs-lookup"><span data-stu-id="7e28d-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="7e28d-104">予約を使用すると、予定を予約している場合に、顧客にたずねる質問を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="7e28d-105">また、必要な質問を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="7e28d-106">質問をサービスに関連付けることで、各サービスに異なる一連の質問を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="7e28d-107">たとえば、ヘア stylist の予定を予約しているユーザーが、bleaches または濃淡に対する既知の allergies を持っている場合に、髪の色を予約していることがあります。</span><span class="sxs-lookup"><span data-stu-id="7e28d-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="7e28d-108">これにより、お客様とお客様は、予定に到着する時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="7e28d-109">予約ページで予定を作成するときに、カスタムの質問が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="7e28d-110">予約予定表から新しい予約を作成したり、既存の予定を表示したりすると、スタッフにカスタム質問が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="7e28d-111">予約では、すべての質問がマスターリストに保存されるので、すべてのサービスについて同じ質問を再作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7e28d-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="7e28d-112">質問を必須にするか、省略可能にするかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="7e28d-113">予約予定表で自分の予定を確認すると、お客様の質問に対する回答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="7e28d-114">予約ページをカスタマイズおよびカスタマイズする方法の詳細については、「 [予約ページをカスタマイズ](customize-booking-page.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e28d-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="7e28d-115">サービスにカスタムの質問を追加する</span><span class="sxs-lookup"><span data-stu-id="7e28d-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="7e28d-116">Microsoft 365 にサインインして、[ **予約**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7e28d-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="7e28d-117">[ **サービス** ] に移動し、既存のサービスを編集するか **、サービスを追加**します。</span><span class="sxs-lookup"><span data-stu-id="7e28d-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="7e28d-118">[ **ユーザー設定フィールド** ] セクションまで下にスクロールし、[ **変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e28d-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="7e28d-119">お客様の電子メール、電話番号、お客様の住所、お客様のメモなど、いくつかの基本的な顧客情報に関する質問が既に追加されています。</span><span class="sxs-lookup"><span data-stu-id="7e28d-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="7e28d-120">初めてこれを行うときは、お客様の情報に関する質問が灰色で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="7e28d-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="7e28d-121">これは、ユーザーにこの質問が表示されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7e28d-121">That means that the user will see this question.</span></span> <span data-ttu-id="7e28d-122">質問を選択すると、その中の強調表示ボックスが非表示になり、お客様に質問するメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7e28d-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="7e28d-123">この例では、電話番号とお客様のノートがオフになっており、質問をするために2つの新しいカスタム質問を作成しました。</span><span class="sxs-lookup"><span data-stu-id="7e28d-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![カスタム質問画面の画像](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="7e28d-125">必要な質問を行うには、 **必要な** チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7e28d-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="7e28d-126">お客様は、必要な質問に回答しない限り、予約を完了できません。</span><span class="sxs-lookup"><span data-stu-id="7e28d-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="7e28d-127">カスタム質問を作成するには、パネルの上部にある [ **質問の追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e28d-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="7e28d-128">質問を記入し、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e28d-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="7e28d-129">その質問をクリックして有効にします。</span><span class="sxs-lookup"><span data-stu-id="7e28d-129">Click on the question to enable it.</span></span> <span data-ttu-id="7e28d-130">強調表示されたボックスが周囲に表示され、質問が有効になります。</span><span class="sxs-lookup"><span data-stu-id="7e28d-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="7e28d-131">ページの上部にある [ **Ok** ] をクリックし、 **サービスを保存**します。</span><span class="sxs-lookup"><span data-stu-id="7e28d-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="7e28d-132">予約では、同じ質問を繰り返し入力することなく、各サービスに質問を簡単に追加できるように、すべてのカスタム質問がマスターリストに保存されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="7e28d-133">たとえば、別のサービスを開いた場合、最初のサービスに対して作成した質問が [ユーザー設定フィールド] セクションに表示されますが、wil は無効になります。</span><span class="sxs-lookup"><span data-stu-id="7e28d-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="7e28d-134">[質問] をクリックすると、強調表示された四角形が表示され、質問が有効になります。</span><span class="sxs-lookup"><span data-stu-id="7e28d-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="7e28d-135">この例では、最初のサービスに対して追加された質問がこのサービスで利用可能であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="7e28d-136">このサービスに対して作成した質問はすべてのサービスで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="7e28d-136">Any questions you create for this service will be available for all services.</span></span>

   ![複数のサービスについて表示される質問の画像](../media/bookings-questions-services.png)

<span data-ttu-id="7e28d-138">予約ページが既に公開されている場合は、他に何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7e28d-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="7e28d-139">お客様には、次の質問が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="7e28d-140">予約ページがまだ公開されていない場合は、web 上の Outlook から **予約ページ** に移動して、[ **保存して発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e28d-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="7e28d-141">マスターリストから質問を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="7e28d-142">ただし、質問を削除すると、すべてのサービスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="7e28d-143">他のサービスに影響がないように、この質問を選択して無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e28d-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="7e28d-144">強調表示されていない四角形で囲まれていない場合は、質問が無効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="7e28d-145">カスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="7e28d-145">Customer experience</span></span>

<span data-ttu-id="7e28d-146">顧客が予定を予約すると、[ **詳細の追加** ] セクションにお客様に関する基本的な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="7e28d-147">カスタマイズした質問がある場合は、「 **追加情報を提供** する」セクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![質問が有効になった場合にお客様に表示される画像](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="7e28d-149">スタッフの作業状況</span><span class="sxs-lookup"><span data-stu-id="7e28d-149">Staff experience</span></span>

<span data-ttu-id="7e28d-150">顧客が予定を予約している場合、会議予定表の質問とお客様の回答がスタッフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="7e28d-151">これを確認するには、[**予約**予定表] に移動して、 \> **Calendar**予定を開きます。</span><span class="sxs-lookup"><span data-stu-id="7e28d-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![質問が有効になったときのスタッフの表示イメージ](../media/bookings-questions-staff.png)
