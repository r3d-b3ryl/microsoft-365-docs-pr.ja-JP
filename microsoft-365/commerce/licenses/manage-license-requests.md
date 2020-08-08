---
title: ライセンス要求を管理する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Microsoft 365 for business サブスクリプションのユーザーからのライセンス要求を確認し、承認または拒否する方法について説明します。
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597660"
---
# <a name="manage-license-requests"></a><span data-ttu-id="a8887-103">ライセンス要求を管理する</span><span class="sxs-lookup"><span data-stu-id="a8887-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="a8887-104">この記事の情報は、セルフサービスで購入した製品にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8887-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="a8887-105">詳細については、「[セルフサービス購入](../subscriptions/self-service-purchase-faq.md)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8887-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="a8887-106">組織でセルフサービス購入を無効にした場合は、ライセンス要求を使用してユーザーのライセンス要求プロセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a8887-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="a8887-107">ユーザーが、ブロックしている製品に対してセルフサービス購入を試行すると、管理者にライセンスの要求を送信することができます。要求を行うときに、製品のライセンスが必要な他のユーザーの名前を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a8887-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="a8887-108">ユーザーがセルフサービス購入を禁止している場合、Microsoft はマーケティングメールを送信しません。</span><span class="sxs-lookup"><span data-stu-id="a8887-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="a8887-109">また、製品の試用版を使用している場合、購入を求めるメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a8887-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="a8887-110">詳細については、「 [Manage self service 購入 (管理者)](../subscriptions/manage-self-service-purchases-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8887-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="a8887-111">ライセンス要求を表示および管理するために、管理者は**ライセンス**ページの [**要求**] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8887-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="a8887-112">一覧には、要求された製品の名前、ライセンスを要求したユーザーの名前、要求された日付、および要求の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8887-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="a8887-113">管理者はリストにフィルターを適用して、保留中または完了した要求を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a8887-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="a8887-114">要求は30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8887-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a8887-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="a8887-115">Before you begin</span></span>

<span data-ttu-id="a8887-116">この記事に記載されているタスクを実行するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8887-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="a8887-117">詳細については、[「管理者の役割について」](../../admin/add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8887-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="a8887-118">独自の要求プロセスを使用する</span><span class="sxs-lookup"><span data-stu-id="a8887-118">Use your own request process</span></span>

<span data-ttu-id="a8887-119">組織に独自の要求プロセスがある場合は、代わりにそのプロセスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8887-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="a8887-120">ユーザーがライセンスを要求したときに表示されるメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8887-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8887-121">独自の要求処理を使用した場合、要求は [**要求**] タブに表示されません。メッセージを追加する前の要求は、承認または拒否するまで表示され続けます。</span><span class="sxs-lookup"><span data-stu-id="a8887-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="a8887-122">管理センターで、[**課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動して、[**要求**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="a8887-123">**代わりに、[既存の要求プロセスを使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="a8887-124">右側のウィンドウで、[**メッセージ**] ボックスに、ユーザーがライセンスを要求したときに表示するメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="a8887-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="a8887-125">組織のポリシーまたはその他のドキュメントへのリンクも含める場合は、[**ドキュメントへのリンク (省略可能)** ] テキストボックスに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8887-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="a8887-126">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-126">Select **Save**.</span></span>

<span data-ttu-id="a8887-127">[**要求**] リストに戻ると、**自分のライセンス要求プロセスを使用している**というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8887-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="a8887-128">ユーザーに送信されるメッセージを変更するには、[**既存の要求プロセスを代わりに使用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="a8887-129">独自の要求プロセスの使用を中止する</span><span class="sxs-lookup"><span data-stu-id="a8887-129">Stop using your own request process</span></span>

1. <span data-ttu-id="a8887-130">管理センターで、[**課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動して、[**要求**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="a8887-131">**代わりに、[既存の要求プロセスを使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="a8887-132">右側のウィンドウで、 **[組織の要求プロセスを使用する**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a8887-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="a8887-133">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="a8887-134">ライセンス要求を承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="a8887-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="a8887-135">管理センターで、[**課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動して、[**要求**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="a8887-136">レビューする要求を含む行を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="a8887-137">右側のウィンドウには、製品にライセンスを求めるユーザーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8887-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="a8887-138">要求全体を拒否するには、[**承認しない**] を選択し、ダイアログボックスで [**承認しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="a8887-139">要求に対して一部のユーザーを拒否し、他のユーザーを承認するには、削除するユーザーの名前によって [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="a8887-140">[**これらのユーザーに割り当てられない**] の下の名前が移動されます。</span><span class="sxs-lookup"><span data-stu-id="a8887-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="a8887-141">製品が複数ある場合は、[**製品の選択**] で、ライセンスの割り当てに使用する製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="a8887-142">ユーザーに特定のアプリとサービスへのアクセスを拒否するには、[**アプリとサービスのオン/オフ**] を展開し、除外するチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a8887-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="a8887-143">ウィンドウの下部にある、テキストボックスにオプションのメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="a8887-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="a8887-144">完了したら、[**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8887-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="a8887-145">右側のウィンドウに、要求の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8887-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="a8887-146">右側のウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a8887-146">Close the right pane.</span></span>
    <span data-ttu-id="a8887-147">ユーザーは、要求が承認または拒否されたという電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="a8887-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="a8887-148">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="a8887-148">Related content</span></span>

<span data-ttu-id="a8887-149">[ユーザーへのライセンスの割り当て](../../admin/manage/assign-licenses-to-users.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="a8887-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="a8887-150">[ユーザーを別のサブスクリプションに移動する](../subscriptions/move-users-different-subscription.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="a8887-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="a8887-151">[サブスクリプションライセンスを購入または削除](buy-licenses.md)する (記事)</span><span class="sxs-lookup"><span data-stu-id="a8887-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>