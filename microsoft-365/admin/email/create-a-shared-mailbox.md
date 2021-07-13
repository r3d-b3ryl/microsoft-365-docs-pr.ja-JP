---
title: 共有メールボックスを作成する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: 共有メールボックスを作成すると、社内の複数のユーザーが 1 つのメール アドレスに送付されたメールを閲覧したり、回答したりできます。
ms.openlocfilehash: 6fff7b1eaa73944bc4dd744046ad97ee9d2379b1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393189"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="30b54-103">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="30b54-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="30b54-104">組織でハイブリッド Exchange 環境を使用する場合は、オンプレミスの Exchange 管理センター (EAC) を使用して、共有メールボックスを作成および管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b54-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="30b54-105">「[Exchange 管理センターで共有メールボックスを作成する](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b54-105">See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span></span><br><br>
> <span data-ttu-id="30b54-106">共有メールボックスと Outlook 用 Microsoft 365 グループのどちらを作成すればよいかわからない場合は、「[グループを比較する](../create-groups/compare-groups.md)」のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b54-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="30b54-107">現在、共有メールボックスを Microsoft 365 グループに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="30b54-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="30b54-108">この機能をご希望の場合は、[こちらから投票](https://go.microsoft.com/fwlink/?linkid=871518)してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="30b54-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="30b54-p103">共有メールボックスの作成は簡単なので、ユーザーのグループが共通のメール アドレス (info@contoso.com など) を監視して、そこからメールを送信することができます。共有メールボックスに送信されたメッセージにグループのユーザーが返信すると、そのメールは、個別のユーザーからではなく共有メールボックスから送信されたように表示されます。</span><span class="sxs-lookup"><span data-stu-id="30b54-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="30b54-p104">共有メールボックスには共有の予定表も含まれています。全員が予定を入力できる場所として、共有の予定表を利用したい小規模企業は数多くあります。たとえば、客先に訪問する社員が 3 人いる場合、全員で共有の予定表を使用して予定を入力できます。これで、誰がどこにいるのかが常にわかるようになります。</span><span class="sxs-lookup"><span data-stu-id="30b54-p104">Shared mailboxes include a shared calendar. A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="30b54-115">共有メールボックスを作成する前に、「[共有メールボックスについて](about-shared-mailboxes.md)」を読んで詳細をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="30b54-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="30b54-116">共有メールボックスを作成し、メンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="30b54-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="30b54-117">グローバル管理者アカウント、または Exchange の管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="30b54-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="30b54-118">"**このページへのアクセス許可がないため、この操作を実行できません**" というメッセージが表示される場合、そのユーザーは管理者ではありません。</span><span class="sxs-lookup"><span data-stu-id="30b54-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="30b54-119">管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="30b54-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="30b54-120">[[管理センター]](https://go.microsoft.com/fwlink/p/?linkid=848041) で、**[グループ]** \> **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="30b54-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="30b54-121">[[管理センター]](https://go.microsoft.com/fwlink/p/?linkid=850627) で、**[グループ]** \> **[共有メールボックス]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="30b54-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="30b54-122">**[共有メールボックス]** ページで、**[+ メールボックスの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="30b54-123">共有メールボックスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="30b54-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="30b54-124">その後、ウィザードでメール アドレスが選ばれますが、自分で編集することができます。</span><span class="sxs-lookup"><span data-stu-id="30b54-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![共有メールボックスに名前を付けます。](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="30b54-126">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-126">Select **Add**.</span></span> <span data-ttu-id="30b54-127">メンバーを追加できるようになるまで、数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="30b54-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="30b54-128">**[次のステップ]** で、**[このメールボックスにメンバーを追加する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="30b54-129">メンバーは、この共有メールボックスへの受信メールと送信した返信を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="30b54-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![[メンバーの追加] を選択する](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="30b54-131">**[+ メンバーの追加]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-131">Select the **+Add members** button.</span></span> <span data-ttu-id="30b54-132">この共有メールボックスの使用を許可するユーザーをクリックしてチェック マークを付け、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![共有メールボックスにメンバーを割り当てる](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="30b54-134">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-134">Select **Close**.</span></span>

<span data-ttu-id="30b54-135">これで共有メールボックスを作成できました。共有の予定表も含まれています。</span><span class="sxs-lookup"><span data-stu-id="30b54-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="30b54-136">次の手順として、「共有メールボックス アカウントのサインインをブロックする」に進みます。</span><span class="sxs-lookup"><span data-stu-id="30b54-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="30b54-137">使用するアクセス許可</span><span class="sxs-lookup"><span data-stu-id="30b54-137">Which permissions should you use?</span></span>

<span data-ttu-id="30b54-138">共有メールボックスと一緒に以下のアクセス許可が使用できます。</span><span class="sxs-lookup"><span data-stu-id="30b54-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="30b54-139">**[フル アクセス]**: [フル アクセス] アクセス許可を使用すれば、共有メールボックスを開いて、そのメールボックスの所有者として作業できます。</span><span class="sxs-lookup"><span data-stu-id="30b54-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="30b54-140">共有メールボックスにアクセスした後、予定表アイテムを作成したり、メール メッセージの読み取り、表示、削除、変更を行ったり、タスクと予定表の連絡先を作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="30b54-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="30b54-141">ただし、[フル アクセス] アクセス許可を持っているユーザーは、[メールボックス所有者として送信する] または [代理人として送信する] アクセス許可も持っている場合に限り、共有メールボックスから電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="30b54-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="30b54-142">**[メールボックス所有者として送信する]**: [メールボックス所有者として送信する] アクセス許可を使用すれば、メールの送信時に共有メールボックスを代理で処理できます。</span><span class="sxs-lookup"><span data-stu-id="30b54-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="30b54-143">たとえば、Katerina がマーケティング部門の共有メールボックスにログインして、メールを送信する場合、そのメールはマーケティング部門が送信したように見えます。</span><span class="sxs-lookup"><span data-stu-id="30b54-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="30b54-144">**[代理人として送信する]**: [代理人として送信する] アクセス許可を使用すれば、共有メールボックスの代わりにメールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="30b54-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="30b54-145">たとえば、John が共有メールボックス Reception Building 32 にログインしてメールを送信すると、メールが「Reception Building 32 の代わりに John」によって送信されたように見えます。</span><span class="sxs-lookup"><span data-stu-id="30b54-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="30b54-146">EAC を使って [代理人として送信する] アクセス許可を付与することはできません。_GrantSendonBehalf_ パラメーターと共に **Set-Mailbox** コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b54-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="30b54-147">EAC を使用して共有メールボックスの委任を編集する</span><span class="sxs-lookup"><span data-stu-id="30b54-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="30b54-148">EAC で、**[受信者]** \> **[共有]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="30b54-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="30b54-149">共有メールボックスを選択し、**[編集]** ![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="30b54-150">**[メールボックスの委任]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="30b54-151">[フル アクセス] および [メールボックス所有者として送信する] アクセス許可を付与または削除するには、**[追加]** ![[追加] アイコン](../../media/ITPro-EAC-AddIcon.png)または **[削除]** ![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif)を選択して、アクセス許可を付与するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="30b54-p115">フル アクセスのアクセス許可を使用すれば、ユーザーはメールボックスを開き、その中でアイテムを作成/変更することができます。「差出人を指定して送信する」アクセス許可を使用すれば、メールボックスの所有者以外のユーザーでも、この共有メールボックスから電子メールを送信することができます。共有メールボックスを正常に操作するには、両方のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="30b54-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="30b54-155">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="30b54-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="30b54-156">共有メールボックス アカウントのサインインをブロックする</span><span class="sxs-lookup"><span data-stu-id="30b54-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="30b54-157">どの共有メールボックスにも、対応するユーザー アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="30b54-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="30b54-158">共有メールボックスを作成する際に、パスワードの入力を求められなかったことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="30b54-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="30b54-159">このアカウントにはパスワードが設定されていますが、そのパスワードはシステムで生成され、ユーザーにはわかりません。</span><span class="sxs-lookup"><span data-stu-id="30b54-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="30b54-160">ユーザーは、そのアカウントを使用して共有メールボックスにログインする訳ではありません。</span><span class="sxs-lookup"><span data-stu-id="30b54-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="30b54-161">では、管理者が共有メールボックスのユーザー アカウントのパスワードをリセットした場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="30b54-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="30b54-162">また、攻撃者がその共有メールボックス アカウントの資格情報にアクセスできるようになった場合はどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="30b54-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="30b54-163">そうなれば、そのユーザー アカウントで共有メールボックスにログインして、メールを送信することが可能になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="30b54-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="30b54-164">これを防ぐために、この共有メールボックスに関連付けられているアカウントのサインインをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b54-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="30b54-165">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="30b54-166">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="30b54-167">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
::: moniker-end

1. <span data-ttu-id="30b54-168">ユーザー アカウントの一覧から、共有メールボックスのアカウントを探します (例: フィルターを **[ライセンス未付与のユーザー]** に変更する)。</span><span class="sxs-lookup"><span data-stu-id="30b54-168">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

1. <span data-ttu-id="30b54-169">そのユーザーを選択してプロパティ ウィンドウを開き、**[このユーザーをブロックする]** アイコンを選択します ![[このユーザーをブロックする] アイコンのスクリーンショット](../../media/block-user-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="30b54-169">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="30b54-170">**注**: アカウントが既にブロックされている場合、上部に **[サインインはブロック済み]** と表示され、アイコンは **[このユーザーのブロックを解除する]** になります。</span><span class="sxs-lookup"><span data-stu-id="30b54-170">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

1. <span data-ttu-id="30b54-171">**[このユーザーをブロックしますか?]** ウィンドウで、**[このユーザーのサインインをブロックする]** を選択し、**[変更の保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-171">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

<span data-ttu-id="30b54-172">Azure AD PowerShell を使用してアカウントのサインインをブロックする方法 (同時に多数のアカウントをブロックする方法など) の詳細については、「[Office 365 PowerShell でユーザー アカウントをブロックする](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b54-172">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="30b54-173">共有メールボックスを Outlook に追加する</span><span class="sxs-lookup"><span data-stu-id="30b54-173">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="30b54-174">お客様の職場で自動マッピングを有効にしている場合 (既定では、ほとんどのユーザーが有効にします)、共有メールボックスは、ユーザーが Outlook を閉じて再起動した後にユーザーの Outlook アプリに自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="30b54-174">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="30b54-175">自動マッピングはユーザーのメールボックスに設定されますが、共有メールボックスには設定されません。  </span><span class="sxs-lookup"><span data-stu-id="30b54-175">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="30b54-176">つまり、セキュリティ グループを使用して、共有メールボックスへのアクセス権を持つユーザーを管理する場合、自動マッピングは機能しません。</span><span class="sxs-lookup"><span data-stu-id="30b54-176">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="30b54-177">そのため、自動マッピングが必要な場合は、明示的にアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b54-177">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="30b54-178">自動マッピングは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="30b54-178">Automapping is on by default.</span></span> <span data-ttu-id="30b54-179">この機能をオフにする方法については、「[Outlook for Office 365 で共有メールボックスの自動マッピングを削除する方法](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b54-179">To learn how to turn it off, see [Remove automapping for a shared mailbox](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="30b54-180">Outlook の共有メールボックスの詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b54-180">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="30b54-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Outlook で共有メールボックスを開いて使用する</a></span><span class="sxs-lookup"><span data-stu-id="30b54-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="30b54-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">共有メールボックスを Outlook on the web に追加する</a></span><span class="sxs-lookup"><span data-stu-id="30b54-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="30b54-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook Mobile に共有メールボックスを追加する</a></span><span class="sxs-lookup"><span data-stu-id="30b54-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="30b54-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Outlook for Mac で共有フォルダーまたはメールボックスを開く</a></span><span class="sxs-lookup"><span data-stu-id="30b54-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="30b54-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">共有メールボックスにルールを追加する</a></span><span class="sxs-lookup"><span data-stu-id="30b54-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="30b54-186">モバイル デバイス (スマートフォンまたはタブレット) で共有メールボックスを使用する</span><span class="sxs-lookup"><span data-stu-id="30b54-186">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="30b54-187">モバイル デバイスでは、次の 2 つの方法で共有メールボックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="30b54-187">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="30b54-188">共有メールボックスを <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS アプリ</a>、または <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android モバイル アプリ</a>に追加する。</span><span class="sxs-lookup"><span data-stu-id="30b54-188">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="30b54-189">手順については、「<a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook Mobile に共有メールボックスを追加する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b54-189">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="30b54-190">ブラウザーを開き、サインインして、Outlook on the web に移動します。</span><span class="sxs-lookup"><span data-stu-id="30b54-190">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="30b54-191">Outlook on the web から、共有メールボックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="30b54-191">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="30b54-192">手順については、「<a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">共有メールボックスを Outlook on the web に追加する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b54-192">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="30b54-193">共有メールボックスは Outlook for iOS アプリ、または Outlook for Android モバイル アプリにのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="30b54-193">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="30b54-194">共有の予定表を使う</span><span class="sxs-lookup"><span data-stu-id="30b54-194">Use the shared calendar</span></span>

<span data-ttu-id="30b54-p120">共有メールボックスを作成すると、共有予定表が自動的に作成されます。SharePoint の予定表と比較して、予定や他の人の居場所を把握するのに便利です。共有予定表は Outlook に統合され、SharePoint の予定表に比べてはるかに簡単に利用することができます。</span><span class="sxs-lookup"><span data-stu-id="30b54-p120">When you created the shared mailbox, you automatically created a shared calendar. We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are. A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="30b54-198">Outlook アプリで予定表ビューに移動し、共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="30b54-198">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="30b54-199">予定を入力すると、共有メールボックスのメンバー全員がその予定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="30b54-199">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="30b54-200">共有メールボックスのすべてのメンバーは、予定表での予定の作成、表示、および管理を、個人的な予定の場合と同様に行えます。</span><span class="sxs-lookup"><span data-stu-id="30b54-200">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="30b54-201">共有メールボックスのメンバーになっているすべてのユーザーは、共有の予定表に加えられた変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="30b54-201">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-content"></a><span data-ttu-id="30b54-202">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="30b54-202">Related content</span></span>

<span data-ttu-id="30b54-203">[共有メールボックスについて](about-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="30b54-203">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="30b54-204">[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="30b54-204">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="30b54-205">[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="30b54-205">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="30b54-206">[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="30b54-206">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="30b54-207">[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="30b54-207">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>