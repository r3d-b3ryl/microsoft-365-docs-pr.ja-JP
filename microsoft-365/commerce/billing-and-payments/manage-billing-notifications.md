---
title: 請求通知と請求書の添付ファイルを管理する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: 請求通知メールと請求書添付ファイルを受け取るユーザーを管理する方法について学習します。
ms.openlocfilehash: 8997a4d3ca575c60214adbedccc018e6768850cd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911856"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="1c83e-103">請求通知と請求書の添付ファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="1c83e-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="1c83e-104">[ **課金通知]** ページでは、組織の請求通知メールを受け取るユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="1c83e-105">このページには、組織の請求書を電子メールの添付ファイルとして受け [取るオプションも用意されています](#receive-your-organizations-invoices-as-email-attachments)。</span><span class="sxs-lookup"><span data-stu-id="1c83e-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1c83e-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="1c83e-106">Before you begin</span></span>

<span data-ttu-id="1c83e-107">この記事で説明する手順を実行するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c83e-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="1c83e-108">課金管理者は、以下のセクションで説明されている通り、これらの変更の一部を行えます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="1c83e-109">詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c83e-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="1c83e-110">メールを受信する言語を変更する</span><span class="sxs-lookup"><span data-stu-id="1c83e-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="1c83e-111">課金管理者は、このセクションの手順も実行できます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="1c83e-112">請求通知メールは、組織の優先言語で送信されます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="1c83e-113">優先する言語を変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="1c83e-114">Microsoft 365 管理センターで、[請求通知]**ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="1c83e-115">[課金通知 **の設定] セクションで** 、[通知設定の **編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="1c83e-116">[課金通知 **の設定] ウィンドウ** の [優先言語] **で** 、使用する言語を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="1c83e-117">請求通知を受け取るユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="1c83e-117">Change who receives billing notifications</span></span>

<span data-ttu-id="1c83e-118">組織の請求通知は、すべてのグローバル管理者および課金管理者のプライマリおよび代替メール アドレスに送信されます。グローバル管理者ロールまたは課金管理者ロールを持つユーザーを変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="1c83e-119">[課金通知] ページを使用して管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1c83e-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="1c83e-120">管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="1c83e-121">[請求 **通知を受け取る** 管理者] セクションで、説明テキストの [ **課金管理者** ] または **[グローバル** 管理者] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="1c83e-122">右側のウィンドウの [割り当てられた管理者] **タブ** で、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="1c83e-123">[管理者 **の追加]** ウィンドウで、ユーザーの表示名またはユーザー名を入力し、候補の一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="1c83e-124">完了するまで、複数のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="1c83e-125">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-125">Select **Save**.</span></span> <span data-ttu-id="1c83e-126">ユーザーが割り当てられた管理者の一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="1c83e-127">[課金通知] ページを使用して管理者の役割を削除する</span><span class="sxs-lookup"><span data-stu-id="1c83e-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="1c83e-128">管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="1c83e-129">[請求 **通知を受け取る** 管理者] セクションで、説明テキストの [ **課金管理者** ] または **[グローバル** 管理者] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="1c83e-130">右側のウィンドウの [割り **当てられた管理者** ] タブで、役割から削除するユーザーを選択し、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="1c83e-131">確認ボックスで、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="1c83e-132">割り当てられた管理者の一覧からユーザーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="1c83e-133">管理者のメール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="1c83e-133">Change the email addresses for admins</span></span>

<span data-ttu-id="1c83e-134">組織内の他の管理者のプライマリメール アドレスと代替メール アドレスを変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="1c83e-135">課金管理者は、自分のプライマリメール アドレスと代替メール アドレスを変更できますが、他の管理者は変更できません。</span><span class="sxs-lookup"><span data-stu-id="1c83e-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="1c83e-136">管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="1c83e-137">[請求 **通知を受け取る管理者] セクションで** 、名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="1c83e-138">右側のウィンドウで、必要に応じてプライマリメール アドレスと代替メール アドレスを追加または更新し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="1c83e-139">組織の連絡先メールを変更する</span><span class="sxs-lookup"><span data-stu-id="1c83e-139">Change your organization's contact email</span></span>

<span data-ttu-id="1c83e-140">グローバル管理者と課金管理者に加えて、請求通知は組織の連絡先メール アドレスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="1c83e-141">電子メール アドレスを変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="1c83e-142">管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="1c83e-143">[請求 **通知を受け取る組織の連絡先] で**、組織の連絡先を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="1c83e-144">右側のウィンドウで、使用するメール アドレスを入力し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="1c83e-145">組織の請求書をメール添付ファイルとして受け取る</span><span class="sxs-lookup"><span data-stu-id="1c83e-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="1c83e-146">課金管理者は、このセクションの手順も実行できます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="1c83e-147">新しい請求書の準備ができたら、組織の請求書のコピーを PDF ファイルとして請求書通知メールに添付できます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="1c83e-148">次の手順を使用して、添付ファイルとして請求書を受信します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="1c83e-149">管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="1c83e-150">[課金 **通知の設定] で**、[通知設定 **の編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="1c83e-151">[請求通知 **の設定] ウィンドウ** の **[請求書** メールに PDF を添付する] で、チェック ボックスをオンにして、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="1c83e-152">請求書の添付ファイルの受信をいつでも停止するには、上記の手順に従い、手順 3 の [請求書メールに **PDF** を添付する] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1c83e-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="1c83e-153">請求プロファイルがある場合は、</span><span class="sxs-lookup"><span data-stu-id="1c83e-153">What if I have a billing profile?</span></span>

<span data-ttu-id="1c83e-154">課金プロファイルがある場合、この記事で説明する手順の一部は、一部のサブスクリプションで若干異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c83e-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="1c83e-155">このセクションでは、これらの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-155">This section describes those differences.</span></span> [<span data-ttu-id="1c83e-156">請求プロファイルを持っているかどうかは、どのように確認できますか?</span><span class="sxs-lookup"><span data-stu-id="1c83e-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="1c83e-157">請求通知を受け取るユーザー</span><span class="sxs-lookup"><span data-stu-id="1c83e-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="1c83e-158">請求通知メールは、次のいずれかの役割が割り当てられているユーザーのプライマリおよび代替メール アドレスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="1c83e-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="1c83e-159">課金プロファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="1c83e-159">Billing profile owner</span></span>
- <span data-ttu-id="1c83e-160">課金プロファイル投稿者</span><span class="sxs-lookup"><span data-stu-id="1c83e-160">Billing profile contributor</span></span>
- <span data-ttu-id="1c83e-161">請求書マネージャー</span><span class="sxs-lookup"><span data-stu-id="1c83e-161">Invoice manager</span></span>

<span data-ttu-id="1c83e-162">課金プロファイルの役割と管理方法の詳細については、「Azure での Microsoft Customer Agreement の管理 [役割について」を参照してください](/azure/cost-management-billing/manage/understand-mca-roles)。</span><span class="sxs-lookup"><span data-stu-id="1c83e-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="1c83e-163">組織の請求通知を受け取るユーザーを変更するには、次の手順を使用して、ユーザーに割り当てられた役割を変更します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="1c83e-164">管理センターで、[支払い] ページの [**請求&**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="1c83e-165">[課金プロファイル **] タブ** で、請求プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="1c83e-166">[課金プロファイル **の役割] セクション** で、課金プロファイル所有者、請求プロファイル投稿者、または請求書マネージャーの役割を割り当てるか **、削除します**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="1c83e-167">電子メールの添付ファイルとして請求書を受け取る</span><span class="sxs-lookup"><span data-stu-id="1c83e-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="1c83e-168">請求書通知の添付ファイルとして請求書を受け取る場合は、次の手順を使用して、特定の請求プロファイルに対してこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1c83e-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="1c83e-169">管理センターで、[支払い] ページの [**請求&**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="1c83e-170">[課金プロファイル **] タブを選択** し、一覧から請求プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c83e-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="1c83e-171">[請求プロファイルの詳細] ページの **[電子メール** の添付ファイルで請求書を取得する] で、トグルを [オン] に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="1c83e-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="1c83e-172">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="1c83e-172">Related content</span></span>

<span data-ttu-id="1c83e-173">[課金内容または請求書を表示する](view-your-bill-or-invoice.md) (article)</span><span class="sxs-lookup"><span data-stu-id="1c83e-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="1c83e-174">[Microsoft 365 for business の請求書](understand-your-invoice2.md) または請求書について (記事)</span><span class="sxs-lookup"><span data-stu-id="1c83e-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="1c83e-175">[ユーザーを追加し、同時にライセンスを割り当てる](../../admin/add-users/add-users.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="1c83e-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>