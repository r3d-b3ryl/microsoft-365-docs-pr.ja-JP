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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'ユーザーに別のユーザーのメールボックスにアクセスする権利を与える方法について説明します。 これにより、ユーザーは他のユーザーのメールボックスからメールを読み取り、メールを送信する権利を与えられます。 '
ms.openlocfilehash: 3fb920fb6f15a2ca48c5676e9b25afd1aa5263f1
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431667"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="08195-104">別のユーザーにメールボックス アクセス許可を付与する - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="08195-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="08195-105">管理者として、一部のユーザーに別のユーザーのメールボックスへのアクセスを許可する会社要件を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="08195-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="08195-106">たとえば、アシスタントが上司のメールボックスの内容を読み取ったり、そこからメールを送信したりできるようにすること、または特定のユーザーが別のユーザーの代理でメールを送信できるようにすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="08195-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="08195-107">このトピックでは、これを実現する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="08195-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="08195-108">共有メールボックスの作成および管理の方法については、「[共有メールボックスを作成する](../email/create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08195-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="08195-109">メールボックスのアクセス許可をどのように設定しますか?</span><span class="sxs-lookup"><span data-stu-id="08195-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="08195-p103">メールボックスのアクセス許可を使用すると、他のユーザーにメールボックスへの読み取り/書き込みのアクセス許可を付与できます。以下の記事では、この機能の設定および使用に必要なヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="08195-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="08195-112">**アクセス許可の設定**</span><span class="sxs-lookup"><span data-stu-id="08195-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="08195-p104">アクセス許可を設定する最初のステップは、他のユーザーが特定のメールボックスで実行できるアクションを決定することです。ユーザーはそのメールボックスからメールを読み取ること、他のユーザーの代理としてメールを送信すること、そのメールボックスが送信元のように偽装してメールを送信することができます。それぞれのアクセス許可を設定する方法については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08195-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="08195-116">別のユーザーのメールボックスからメールを読み取る</span><span class="sxs-lookup"><span data-stu-id="08195-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="08195-117">別のユーザーのメールボックスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="08195-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="08195-118">別のユーザーの代理でメールを送信する</span><span class="sxs-lookup"><span data-stu-id="08195-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="08195-119">**変更の伝達:**</span><span class="sxs-lookup"><span data-stu-id="08195-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="08195-120">アクセス許可を設定すると、変更がシステム全体に伝達されるまでに最大で 60 分かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08195-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="08195-121">**アクセス許可の設定後に使用する方法:**</span><span class="sxs-lookup"><span data-stu-id="08195-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="08195-p105">アクセス許可が付与された後に、メールボックスにアクセスするには、いくつかの異なる方法があります。このヘルプについては、次の記事を参照してください。[別のユーザーのメールボックスにアクセスする](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="08195-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="08195-124">別のユーザーのメールボックスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="08195-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="08195-125">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="08195-126">(送信許可を与える予定の) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="08195-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="08195-127">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="08195-128">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="08195-129">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="08195-130">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="08195-131">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="08195-132">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="08195-133">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="08195-134">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="08195-135">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="08195-136">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="08195-137">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="08195-138">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="08195-139">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="08195-140">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="08195-141">別のユーザーのメールボックスのメールを読み取る</span><span class="sxs-lookup"><span data-stu-id="08195-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="08195-142">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="08195-143">(読み取りを許可するメールボックスを持つ) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="08195-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="08195-144">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="08195-145">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="08195-146">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="08195-147">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="08195-148">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="08195-149">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="08195-150">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="08195-151">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="08195-152">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="08195-153">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="08195-154">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="08195-155">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="08195-156">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="08195-157">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="08195-158">別のユーザーの代理でメールを送信する</span><span class="sxs-lookup"><span data-stu-id="08195-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="08195-159">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="08195-160">(**代理送信**許可を与える予定の) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="08195-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="08195-161">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="08195-162">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="08195-163">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="08195-164">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="08195-165">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="08195-166">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="08195-167">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="08195-168">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="08195-169">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="08195-170">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="08195-171">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="08195-172">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="08195-173">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="08195-174">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08195-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="08195-175">Outlook および一般法人向け Outlook on the web での送信および読み取り</span><span class="sxs-lookup"><span data-stu-id="08195-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="08195-p106">別のユーザーのメールボックスからメールを送信する方法については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08195-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="08195-178">他のユーザーのメールおよび予定表のアイテムを管理する</span><span class="sxs-lookup"><span data-stu-id="08195-178">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="08195-179">別のユーザーまたはグループからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="08195-179">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
