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
ms.openlocfilehash: af12cfe3acad9e12ca3983c9fa13f52b72f0a467
ms.sourcegitcommit: 16e018f8b6eef5dad48eabf179691ead3cebe533
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2020
ms.locfileid: "49725155"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="8e42e-104">別のユーザーにメールボックス アクセス許可を付与する - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="8e42e-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="8e42e-105">管理者として、一部のユーザーに別のユーザーのメールボックスへのアクセスを許可する会社要件を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="8e42e-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="8e42e-106">たとえば、アシスタントが上司のメールボックスの内容を読み取ったり、そこからメールを送信したりできるようにすること、または特定のユーザーが別のユーザーの代理でメールを送信できるようにすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e42e-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="8e42e-107">このトピックでは、これを実現する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="8e42e-108">共有メールボックスの作成および管理の方法については、「[共有メールボックスを作成する](../email/create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e42e-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="8e42e-109">メールボックスのアクセス許可をどのように設定しますか?</span><span class="sxs-lookup"><span data-stu-id="8e42e-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="8e42e-p103">メールボックスのアクセス許可を使用すると、他のユーザーにメールボックスへの読み取り/書き込みのアクセス許可を付与できます。以下の記事では、この機能の設定および使用に必要なヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="8e42e-112">**アクセス許可の設定**</span><span class="sxs-lookup"><span data-stu-id="8e42e-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="8e42e-p104">アクセス許可を設定する最初のステップは、他のユーザーが特定のメールボックスで実行できるアクションを決定することです。ユーザーはそのメールボックスからメールを読み取ること、他のユーザーの代理としてメールを送信すること、そのメールボックスが送信元のように偽装してメールを送信することができます。それぞれのアクセス許可を設定する方法については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e42e-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="8e42e-116">別のユーザーのメールボックスからメールを読み取る</span><span class="sxs-lookup"><span data-stu-id="8e42e-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="8e42e-117">別のユーザーのメールボックスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="8e42e-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="8e42e-118">別のユーザーの代理でメールを送信する</span><span class="sxs-lookup"><span data-stu-id="8e42e-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="8e42e-119">**変更の伝達:**</span><span class="sxs-lookup"><span data-stu-id="8e42e-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="8e42e-120">アクセス許可を設定すると、変更がシステム全体に伝達されるまでに最大で 60 分かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e42e-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="8e42e-121">**アクセス許可の設定後に使用する方法:**</span><span class="sxs-lookup"><span data-stu-id="8e42e-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="8e42e-p105">アクセス許可が付与された後に、メールボックスにアクセスするには、いくつかの異なる方法があります。このヘルプについては、次の記事を参照してください:[別のユーザーのメールボックスにアクセスする](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)。</span><span class="sxs-lookup"><span data-stu-id="8e42e-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="8e42e-124">アクセス許可は、現在の組織のテナント内でのみ、セットアップできます。</span><span class="sxs-lookup"><span data-stu-id="8e42e-124">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="8e42e-125">テナント外のユーザーが、メールボックスのアクセス許可をセットアップすることはできません。　　</span><span class="sxs-lookup"><span data-stu-id="8e42e-125">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="8e42e-126">別のユーザーのメールボックスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="8e42e-126">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8e42e-127">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="8e42e-128">(送信許可を与える予定の) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="8e42e-128">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="8e42e-129">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-129">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="8e42e-130">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-130">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="8e42e-131">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-131">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="8e42e-132">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-132">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8e42e-133">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="8e42e-134">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-134">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="8e42e-135">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-135">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="8e42e-136">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-136">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="8e42e-137">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-137">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8e42e-138">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="8e42e-139">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-139">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="8e42e-140">[**差出人を指定して送信する**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-140">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="8e42e-141">[**アクセス許可を追加する**] を選択してから、このユーザーが送信できるようにするユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-141">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="8e42e-142">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-142">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="8e42e-143">別のユーザーのメールボックスのメールを読み取る</span><span class="sxs-lookup"><span data-stu-id="8e42e-143">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8e42e-144">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="8e42e-145">(読み取りを許可するメールボックスを持つ) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="8e42e-145">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="8e42e-146">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-146">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="8e42e-147">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-147">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="8e42e-148">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-148">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="8e42e-149">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-149">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="8e42e-150">[**読み取り**] および [**管理**] の権限は、Exchange 管理センターで付与された場合、[**フル アクセス**] 権限と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8e42e-150">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="8e42e-151">[フル アクセス] 権限では、**[メールボックス所有者として送信する]** または **[代理人として送信する]** の権限は付与されません。</span><span class="sxs-lookup"><span data-stu-id="8e42e-151">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8e42e-152">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="8e42e-153">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-153">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="8e42e-154">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-154">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="8e42e-155">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-155">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="8e42e-156">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-156">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8e42e-157">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="8e42e-158">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-158">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="8e42e-159">[**読み取りと管理**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-159">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="8e42e-160">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの読み取りを許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-160">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="8e42e-161">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-161">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="8e42e-162">別のユーザーの代理でメールを送信する</span><span class="sxs-lookup"><span data-stu-id="8e42e-162">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8e42e-163">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="8e42e-164">(**代理送信** 許可を与える予定の) ユーザーの名前を選択して、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="8e42e-164">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="8e42e-165">[**メール**] タブで、[**メールボックスへのアクセス許可の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-165">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="8e42e-166">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-166">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="8e42e-167">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-167">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="8e42e-168">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-168">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8e42e-169">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="8e42e-170">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-170">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="8e42e-171">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-171">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="8e42e-172">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-172">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="8e42e-173">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-173">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8e42e-174">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="8e42e-175">目的のユーザーを選択し、[**メール設定**] を展開して、[**メールボックスのアクセス許可**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-175">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="8e42e-176">[**代理送信**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-176">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="8e42e-177">[**アクセス許可を追加する**] を選択し、このメールボックスからのメールの代理送信を許可するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-177">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="8e42e-178">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e42e-178">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="8e42e-179">Outlook および一般法人向け Outlook on the web での送信および読み取り</span><span class="sxs-lookup"><span data-stu-id="8e42e-179">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="8e42e-p108">別のユーザーのメールボックスからメールを送信する方法については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e42e-p108">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="8e42e-182">他のユーザーのメールおよび予定表のアイテムを管理する</span><span class="sxs-lookup"><span data-stu-id="8e42e-182">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="8e42e-183">別のユーザーまたはグループからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="8e42e-183">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
