---
title: ユーザー メールボックスを共有メールボックスに変換する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '個人用メールボックスを、複数のユーザーがアクセスできる共有メールボックスに変換する方法について説明します。 '
ms.openlocfilehash: 481707b9d60d37b1d80d822467d17f66750f4f13
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255268"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="54bef-103">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="54bef-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="54bef-p101">ユーザーのメールボックスを共有メールボックスに変換した場合、すべての既存のメールと予定表は保持されます。現在は、1 人のユーザーのみではなく何人かのユーザーがアクセスできる共有メールボックスにそれらが入っています。</span><span class="sxs-lookup"><span data-stu-id="54bef-p101">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained. Only now it's in a shared mailbox where several people will be able to access it instead of one person. At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="54bef-107">**知っておく必要がある重要な点事項を次に示します**</span><span class="sxs-lookup"><span data-stu-id="54bef-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="54bef-108">共有メールボックスに変換する前に、変換するユーザー メールボックスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="54bef-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="54bef-109">そうでない場合、変換オプションがメールボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="54bef-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="54bef-110">ライセンスを削除した場合、メールボックスを変換するために再度それを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="54bef-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="54bef-111">ライセンスは、メールボックスを共有に変換した後に、ユーザー アカウントから削除できます。</span><span class="sxs-lookup"><span data-stu-id="54bef-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="54bef-p103">共有メールボックスは、ライセンスなしで、最大 50 GB のデータを保持することができます。 これ以上のデータを保持するには、ライセンスを割り当てる必要があります。 ライセンスを削除するには、(添付ファイルがあるものなど) 大きなメールを多数削除してサイズを小さくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54bef-p103">Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="54bef-p104">古いユーザー アカウントは削除しないでください。 それは共有メールボックスの固定に必要です。 ユーザー アカウントを既に削除している場合、「[削除済みユーザーのメールボックスを変換する](#convert-the-mailbox-of-a-deleted-user)」 (削除されたユーザーのメールボックスを変換する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54bef-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="54bef-118">メールボックスが共有メールボックスに変換された後でも、ルールは変更されません。</span><span class="sxs-lookup"><span data-stu-id="54bef-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="54bef-119">Exchange 管理センターを使用してメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="54bef-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="54bef-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="54bef-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="54bef-121">**[受信者]** \> **[メールボックス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="54bef-122">ユーザー メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-122">Select the user mailbox.</span></span> <span data-ttu-id="54bef-123">**[共有メールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="54bef-124">メールボックスが 50 GB 未満の場合は、[ユーザーからライセンス](../manage/remove-licenses-from-users.md)を削除し、その支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="54bef-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="54bef-125">ユーザーの古いメールボックスは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="54bef-125">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="54bef-126">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="54bef-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="54bef-127">組織を退職する従業員のメールボックスを変換する場合は、追加の手順を実行して、当該の従業員が以後ログインできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54bef-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="54bef-128">「[Office 365 から元従業員を削除する](../add-users/remove-former-employee.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54bef-128">Please see [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="54bef-129">共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54bef-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="54bef-130">Microsoft 365 管理センターを使用して、メールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="54bef-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="54bef-131">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="54bef-132">メールボックスを変換するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="54bef-133">ユーザーのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="54bef-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="54bef-134">メールボックスの変換中にユーザーのパスワードをリセットする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="54bef-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="54bef-135">ただし、パスワードがリセットされない場合、メールボックスの変換が終了した後も **元のユーザー名とパスワードは引き続き機能します**。</span><span class="sxs-lookup"><span data-stu-id="54bef-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="54bef-136">**[メール]** タブで、**[その他の操作]** の **[共有メールボックスに変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="54bef-137">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="54bef-138">メールボックスを変換するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="54bef-139">右側のウィンドウで、**[メール設定]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="54bef-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="54bef-140">**[詳細設定]** の横にある **[共有メールボックスに変換する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="54bef-141">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="54bef-142">メールボックスを変換するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="54bef-143">右側のウィンドウで、**[メール設定]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="54bef-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="54bef-144">**[詳細設定]** の横にある **[共有メールボックスに変換する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="54bef-145">メールボックスが 50 GB 未満の場合は、[ユーザーからライセンスを削除](../manage/remove-licenses-from-users.md)して、その支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="54bef-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="54bef-146">ユーザーの古いメールボックスは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="54bef-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="54bef-147">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="54bef-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="54bef-148">組織を退職する従業員のメールボックスを変換する場合は、追加の手順を実行して、当該の従業員が以後ログインできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54bef-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="54bef-149">「[Office 365 から元従業員を削除する](../add-users/remove-former-employee.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54bef-149">See [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="54bef-150">共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54bef-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="54bef-151">削除済みユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="54bef-151">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="54bef-p111">削除したユーザー アカウントの古いメールボックスを共有メールボックスに変換したいとします。これには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="54bef-p111">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="54bef-154">[ユーザーのアカウントを復元](../add-users/restore-user.md)します。</span><span class="sxs-lookup"><span data-stu-id="54bef-154">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="54bef-155">Office 365 のライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54bef-155">Make sure an Office 365 license is assigned to it.</span></span>

3. <span data-ttu-id="54bef-156">ユーザーのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="54bef-156">Reset the user's password.</span></span>
    
4. <span data-ttu-id="54bef-157">メールボックスが再作成されるまで 20 から 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="54bef-157">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="54bef-158">次いでページの指示に従い、それのユーザーのメールボックスを共有メールボックスに変換します。</span><span class="sxs-lookup"><span data-stu-id="54bef-158">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="54bef-159">終了したら、ユーザーのメールボックスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="54bef-159">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="54bef-160">ユーザーの古いメールボックスは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="54bef-160">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="54bef-161">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="54bef-161">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="54bef-162">共有メールボックスにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="54bef-162">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="54bef-163">共有メールボックスを変換して、ユーザーの (プライベート) メールボックスに戻す</span><span class="sxs-lookup"><span data-stu-id="54bef-163">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="54bef-164"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="54bef-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="54bef-165">**[受信者]** \> **[共有]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-165">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="54bef-166">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-166">Select the shared mailbox.</span></span> <span data-ttu-id="54bef-167">**[通常のメールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54bef-167">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="54bef-168">管理センターに戻ります。</span><span class="sxs-lookup"><span data-stu-id="54bef-168">Go back to the admin center.</span></span> <span data-ttu-id="54bef-169">[**ユーザー**] で古い共有メールボックスに関連付けられているユーザー アカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="54bef-169">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="54bef-170">そのアカウントにライセンスを割り当て、パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="54bef-170">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="54bef-p115">メールボックスの設定には数分かかりますが、その後ではそのアカウントのユーザーの準備は完了します。それらのユーザーがサインインすると、共有メールボックス内にあったメールと予定表のアイテムが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="54bef-p115">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="54bef-173">ハイブリッド環境でユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="54bef-173">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="54bef-174">この共有メールボックスがハイブリッド環境にある場合、ユーザーのメールボックスをオンプレミスに戻し、ユーザーのメールボックスを共有メールボックスに変換して、共有メールボックスをクラウドに移動することを**強くお勧めします** (ほとんど必須)。</span><span class="sxs-lookup"><span data-stu-id="54bef-174">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="54bef-175">その理由は次のとおりです。クラウド内のメールボックスを変換すると、変換はされますが、まだオンプレミスではメールボックスがユーザーのメールボックスであると認識されます。これは、新しい現実がオンプレミスに同期されないためです。</span><span class="sxs-lookup"><span data-stu-id="54bef-175">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="54bef-176">通常、これは問題にはなりませんが、オンプレミスの属性 (メールボックスがユーザーのメールボックスであると考えられる) がそれらの属性の新しいクラウドバージョンを上書きし、その結果としてメールボックスが変換される可能性がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="54bef-176">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="54bef-177">これは問題です。ユーザーのメールボックスにはライセンスが必要であるか、**30 日後に削除される**ためです。</span><span class="sxs-lookup"><span data-stu-id="54bef-177">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="54bef-178">既に、これが発生する原因のほとんどに対処してありますが、ごく希に、まだ発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="54bef-178">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="54bef-179">安全を確保し、メールボックスをオンプレミスに戻すことが最善策になります。</span><span class="sxs-lookup"><span data-stu-id="54bef-179">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="54bef-180">組織管理や受信者管理の一員の場合は、Exchange 管理シェルを使用して、ユーザーのメールボックスをオンプレミスの共有メールボックスに変更できます。</span><span class="sxs-lookup"><span data-stu-id="54bef-180">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="54bef-181">たとえば、`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared` などです。</span><span class="sxs-lookup"><span data-stu-id="54bef-181">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="54bef-182">たとえば、[共有メールボックスが予期せずにユーザーのメールボックスに変換される](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)場合については、このサポート ソリューションの回避策を参照してください</span><span class="sxs-lookup"><span data-stu-id="54bef-182">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="54bef-183">関連記事</span><span class="sxs-lookup"><span data-stu-id="54bef-183">Related articles</span></span>

[<span data-ttu-id="54bef-184">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="54bef-184">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="54bef-185">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="54bef-185">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="54bef-186">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="54bef-186">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="54bef-187">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="54bef-187">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="54bef-188">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="54bef-188">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
