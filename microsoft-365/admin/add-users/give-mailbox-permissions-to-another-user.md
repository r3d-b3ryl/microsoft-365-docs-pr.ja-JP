---
title: 別のユーザーにメールボックス アクセス許可を付与する - 管理者ヘルプ
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 他のユーザーのメールボックスにアクセスする権利をユーザーに与えます。このアクセス権を持つユーザーは、他のユーザーのメールボックスからメールを読んだり送信したりできます。
ms.openlocfilehash: 3514be02f2ef82b727edfcf86c0bd3f6b8515510
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535964"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="a5d3a-103">別のユーザーにメールボックス アクセス許可を付与する - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="a5d3a-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="a5d3a-104">管理者として、一部のユーザーに別のユーザーのメールボックスへのアクセスを許可する会社要件を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-104">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="a5d3a-105">たとえば、アシスタントが上司のメールボックスの内容を読み取ったり、そこからメールを送信したりできるようにすること、または特定のユーザーが別のユーザーの代理でメールを送信できるようにすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-105">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="a5d3a-106">このトピックでは、これを実現する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-106">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="a5d3a-107">共有メールボックスの作成および管理の方法については、「[共有メールボックスを作成する](../email/create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="a5d3a-108">メールボックスのアクセス許可をどのように設定しますか?</span><span class="sxs-lookup"><span data-stu-id="a5d3a-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="a5d3a-p102">メールボックスのアクセス許可を使用すると、他のユーザーにメールボックスへの読み取り/書き込みのアクセス許可を付与できます。以下の記事では、この機能の設定および使用に必要なヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="a5d3a-111">**アクセス許可の設定**</span><span class="sxs-lookup"><span data-stu-id="a5d3a-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="a5d3a-p103">アクセス許可を設定する最初のステップは、他のユーザーが特定のメールボックスで実行できるアクションを決定することです。ユーザーはそのメールボックスからメールを読み取ること、他のユーザーの代理としてメールを送信すること、そのメールボックスが送信元のように偽装してメールを送信することができます。それぞれのアクセス許可を設定する方法については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="a5d3a-115">別のユーザーのメールボックスからメールを読み取る</span><span class="sxs-lookup"><span data-stu-id="a5d3a-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="a5d3a-116">別のユーザーのメールボックスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="a5d3a-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="a5d3a-117">別のユーザーの代理でメールを送信する</span><span class="sxs-lookup"><span data-stu-id="a5d3a-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="a5d3a-118">**変更の伝達:**</span><span class="sxs-lookup"><span data-stu-id="a5d3a-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="a5d3a-119">アクセス許可を設定すると、変更がシステム全体に伝達されるまでに最大で 60 分かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="a5d3a-120">**アクセス許可の設定後に使用する方法:**</span><span class="sxs-lookup"><span data-stu-id="a5d3a-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="a5d3a-p104">アクセス許可が付与された後に、メールボックスにアクセスするには、いくつかの異なる方法があります。このヘルプについては、次の記事を参照してください:[別のユーザーのメールボックスにアクセスする](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="a5d3a-123">アクセス許可は、現在の組織のテナント内でのみ、セットアップできます。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="a5d3a-124">テナント外のユーザーが、メールボックスのアクセス許可をセットアップすることはできません。　　</span><span class="sxs-lookup"><span data-stu-id="a5d3a-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="a5d3a-125">別のユーザーのメールボックスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="a5d3a-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5d3a-126">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="a5d3a-127">(送信許可を与える予定の) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="a5d3a-128">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="a5d3a-129">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="a5d3a-130">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="a5d3a-131">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a5d3a-132">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="a5d3a-133">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="a5d3a-134">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="a5d3a-135">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="a5d3a-136">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5d3a-137">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="a5d3a-138">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="a5d3a-139">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="a5d3a-140">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="a5d3a-141">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="a5d3a-142">別のユーザーのメールボックスのメールを読み取る</span><span class="sxs-lookup"><span data-stu-id="a5d3a-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5d3a-143">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="a5d3a-144">(読み取りを許可するメールボックスを持つ) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="a5d3a-145">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="a5d3a-146">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="a5d3a-147">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="a5d3a-148">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="a5d3a-149">[**読み取り**] および [**管理**] の権限は、Exchange 管理センターで付与された場合、[**フル アクセス**] 権限と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="a5d3a-150">[フル アクセス] 権限では、**[メールボックス所有者として送信する]** または **[代理人として送信する]** の権限は付与されません。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a5d3a-151">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="a5d3a-152">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="a5d3a-153">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="a5d3a-154">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="a5d3a-155">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5d3a-156">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="a5d3a-157">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="a5d3a-158">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="a5d3a-159">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="a5d3a-160">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="a5d3a-161">別のユーザーの代理でメールを送信する</span><span class="sxs-lookup"><span data-stu-id="a5d3a-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5d3a-162">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="a5d3a-163">(**代理送信** 許可を与える予定の) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="a5d3a-164">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="a5d3a-165">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="a5d3a-166">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="a5d3a-167">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a5d3a-168">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="a5d3a-169">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="a5d3a-170">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="a5d3a-171">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="a5d3a-172">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5d3a-173">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="a5d3a-174">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="a5d3a-175">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="a5d3a-176">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="a5d3a-177">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d3a-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="a5d3a-178">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="a5d3a-178">Related content</span></span>
  
<span data-ttu-id="a5d3a-179">[他のユーザーのメールおよび予定表のアイテムを管理する](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (記事)</span><span class="sxs-lookup"><span data-stu-id="a5d3a-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)</span></span>
    
<span data-ttu-id="a5d3a-180">[別のユーザーまたはグループからメールを送信する](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (記事)</span><span class="sxs-lookup"><span data-stu-id="a5d3a-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)</span></span>

<span data-ttu-id="a5d3a-181">[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (動画)</span><span class="sxs-lookup"><span data-stu-id="a5d3a-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

