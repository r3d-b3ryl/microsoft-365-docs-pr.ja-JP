---
title: ライセンス要求の管理
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: ビジネス サブスクリプションのユーザーからのライセンス要求を確認および承認またはMicrosoft 365する方法について学習します。
ms.date: 06/07/2021
ms.openlocfilehash: 23258d21ebb413c56323aa4dab25cee60baf2be0
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256809"
---
# <a name="manage-license-requests"></a><span data-ttu-id="cf7e2-103">ライセンス要求の管理</span><span class="sxs-lookup"><span data-stu-id="cf7e2-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="cf7e2-104">この記事の情報は、セルフサービス購入製品にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="cf7e2-105">詳細については、「セルフサービス購入 [に関するよく寄せられる質問」を参照してください](../subscriptions/self-service-purchase-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="cf7e2-106">組織内でセルフサービス購入を無効にした場合は、ライセンス要求を使用してユーザーのライセンス要求プロセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="cf7e2-107">ユーザーがブロックした製品のセルフサービス購入を試みる場合は、管理者からライセンスの要求を送信できます。要求を行う場合は、製品のライセンスも必要とする他のユーザーの名前を追加できます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="cf7e2-108">ユーザーによるセルフサービスの購入をブロックした場合、Microsoft はマーケティングメールを送信しません。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="cf7e2-109">また、製品の試用版を使用している場合、製品の購入を求めるメッセージは表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="cf7e2-110">詳細については、「セルフサービス購入 [の管理 (Admin)」を参照してください](../subscriptions/manage-self-service-purchases-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="cf7e2-111">ライセンス要求を表示および管理するために、管理者は[ライセンス] ページの [要求] タブ **を使用** します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="cf7e2-112">一覧には、要求された製品の名前、ライセンスを要求するユーザーの名前、要求された日付、要求の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="cf7e2-113">管理者はリストをフィルター処理して、保留中または完了した要求を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="cf7e2-114">要求は 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cf7e2-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="cf7e2-115">Before you begin</span></span>

<span data-ttu-id="cf7e2-116">この記事のタスクを実行するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="cf7e2-117">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="cf7e2-118">独自の要求プロセスを使用する</span><span class="sxs-lookup"><span data-stu-id="cf7e2-118">Use your own request process</span></span>

<span data-ttu-id="cf7e2-119">組織に独自の要求プロセスがある場合は、代わりにそれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="cf7e2-120">ユーザーがライセンスを要求するときに表示されるメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf7e2-121">独自の要求プロセスを使用する場合は、[要求] タブに要求 **は表示** されません。メッセージを追加する前の既存の要求は、メッセージを承認または拒否するまで引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="cf7e2-122">管理センターで、[課金ライセンス] ページ **に**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">移動</a>し、[要求]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="cf7e2-123">[代 **わりに既存の要求プロセスを使用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="cf7e2-124">右側のウィンドウの [メッセージ] **ボックスに、** ユーザーがライセンスを要求するときに表示するメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="cf7e2-125">組織ポリシーや他のドキュメントへのリンクも含める場合は、[ドキュメントへのリンク] (オプション **)** テキスト ボックスに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="cf7e2-126">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-126">Select **Save**.</span></span>

<span data-ttu-id="cf7e2-127">要求リストに戻 **った** 場合は、独自のライセンス要求プロセスを使用しているという **メッセージが表示されます**。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="cf7e2-128">ユーザーに送信されるメッセージを変更するには、[代わりに既存の要求プロセスを使用する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="cf7e2-129">独自の要求プロセスの使用を停止する</span><span class="sxs-lookup"><span data-stu-id="cf7e2-129">Stop using your own request process</span></span>

1. <span data-ttu-id="cf7e2-130">管理センターで、[課金ライセンス] ページ **に**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">移動</a>し、[要求]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="cf7e2-131">[代 **わりに既存の要求プロセスを使用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="cf7e2-132">右側のウィンドウで、[組織の要求プロセスを使用する] チェック **ボックス** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="cf7e2-133">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="cf7e2-134">ライセンス要求を承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="cf7e2-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="cf7e2-135">管理センターで、[課金ライセンス] ページ **に**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">移動</a>し、[要求]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="cf7e2-136">確認する要求を含む行を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="cf7e2-137">右側のウィンドウには、製品のライセンスを必要とするユーザーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="cf7e2-138">要求全体を拒否するには、[承認しない] を **選択** し、ダイアログ ボックスで [承認しない **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="cf7e2-139">要求に対して一部のユーザーを拒否し、他のユーザーを承認するには、削除するユーザーの名前で X を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="cf7e2-140">[これらのユーザーに割り当てない] **の下に名前が移動されます**。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="cf7e2-141">複数の製品がある場合は、[製品の選択] で、ライセンスの割り当てに使用する製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="cf7e2-142">ユーザーが特定のアプリやサービスへのアクセスを拒否するには、[アプリとサービスを有効またはオフにする] を展開し、除外するアプリのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="cf7e2-143">ウィンドウの下部に、テキスト ボックスにオプションのメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="cf7e2-144">完了したら、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="cf7e2-145">右側のウィンドウには、要求の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="cf7e2-146">右側のウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-146">Close the right pane.</span></span>
    <span data-ttu-id="cf7e2-147">ユーザーは、要求が承認または拒否されたという電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="cf7e2-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="cf7e2-148">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="cf7e2-148">Related content</span></span>

<span data-ttu-id="cf7e2-149">[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="cf7e2-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="cf7e2-150">[ユーザーを別のサブスクリプションに移動](../subscriptions/move-users-different-subscription.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="cf7e2-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="cf7e2-151">[サブスクリプション ライセンスを購入または削除する](buy-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="cf7e2-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>
