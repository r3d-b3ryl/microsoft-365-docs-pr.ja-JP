---
title: ユーザー メールボックスを共有メールボックスに変換する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '個人用メールボックスを、複数のユーザーがアクセスできる共有メールボックスに変換する方法について説明します。 '
ms.openlocfilehash: bc867c9b43656e40149eb7cd7a7e5ce186c10798
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445689"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="85595-103">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="85595-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="85595-p101">ユーザーのメールボックスを共有メールボックスに変換した場合、すべての既存のメールと予定表は保持されます。現在は、1 人のユーザーのみではなく何人かのユーザーがアクセスできる共有メールボックスにそれらが入っています。</span><span class="sxs-lookup"><span data-stu-id="85595-p101">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained. Only now it's in a shared mailbox where several people will be able to access it instead of one person. At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="85595-107">**知っておく必要がある重要な点事項を次に示します**</span><span class="sxs-lookup"><span data-stu-id="85595-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="85595-108">共有メールボックスに変換する前に、変換するユーザー メールボックスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85595-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="85595-109">そうでない場合、変換オプションがメールボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="85595-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="85595-110">ライセンスを削除した場合、メールボックスを変換するために再度それを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="85595-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="85595-111">ライセンスは、メールボックスを共有に変換した後に、ユーザー アカウントから削除できます。</span><span class="sxs-lookup"><span data-stu-id="85595-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="85595-p103">共有メールボックスは、ライセンスが割り当てられていないと最大 50 GB のデータを持つことができます。より多くのデータを保持するには、ライセンスが割り当てられている必要があります。ライセンスを削除できるように、大量の大規模なメール (添付ファイル付きのメールなど) を共有メールボックスから削除して縮小する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="85595-p103">Shared mailboxes can have up to 50 GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="85595-p104">古いユーザー アカウントは削除しないでください。 それは共有メールボックスの固定に必要です。 ユーザー アカウントを既に削除している場合、「[削除済みユーザーのメールボックスを変換する](#convert-the-mailbox-of-a-deleted-user)」 (削除されたユーザーのメールボックスを変換する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85595-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="85595-118">メールボックスが共有メールボックスに変換された後でも、ルールは変更されません。</span><span class="sxs-lookup"><span data-stu-id="85595-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="85595-119">Exchange 管理センターを使用してメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="85595-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="85595-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="85595-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="85595-121">**[受信者]** \> **[メールボックス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="85595-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="85595-122">ユーザー メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="85595-122">Select the user mailbox.</span></span> <span data-ttu-id="85595-123">**[共有メールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85595-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="85595-124">メールボックスが 50 GB より小さい場合は、 [ユーザーからライセンス](../manage/remove-licenses-from-users.md)を削除して、その支払いを停止することができます。</span><span class="sxs-lookup"><span data-stu-id="85595-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="85595-125">ユーザーのアカウントは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="85595-125">Don't delete the user's account.</span></span> <span data-ttu-id="85595-126">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="85595-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="85595-127">組織を退職する従業員のメールボックスを変換する場合は、追加の手順を実行して、当該の従業員が以後ログインできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85595-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="85595-128">「 [Microsoft 365 から元従業員を削除する](../add-users/remove-former-employee.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85595-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="85595-129">メールボックスの変換中にユーザーのパスワードをリセットする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="85595-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="85595-130">ただし、パスワードがリセットされない場合、メールボックスの変換が終了した後も **元のユーザー名とパスワードは引き続き機能します**。</span><span class="sxs-lookup"><span data-stu-id="85595-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="85595-131">共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85595-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="85595-132">共有メールボックスには、別途ライセンスが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="85595-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="85595-133">ただし、共有メールボックスに In-Place アーカイブを有効にする場合、または In-Place ホールドまたは訴訟ホールドを設定する場合は、exchange online のプラン1を exchange online アーカイブまたは Exchange online Plan 2 ライセンスを使用してメールボックスに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85595-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="85595-134">削除済みユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="85595-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="85595-p109">削除したユーザー アカウントの古いメールボックスを共有メールボックスに変換したいとします。これには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="85595-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="85595-137">[ユーザーのアカウントを復元](../add-users/restore-user.md)します。</span><span class="sxs-lookup"><span data-stu-id="85595-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="85595-138">Microsoft 365 ライセンスが割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="85595-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="85595-139">ユーザーのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="85595-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="85595-140">メールボックスが再作成されるまで 20 から 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="85595-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="85595-141">次いでページの指示に従い、それのユーザーのメールボックスを共有メールボックスに変換します。</span><span class="sxs-lookup"><span data-stu-id="85595-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="85595-142">終了したら、ユーザーのメールボックスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="85595-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="85595-143">ユーザーの古いメールボックスは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="85595-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="85595-144">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="85595-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="85595-145">共有メールボックスにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="85595-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="85595-146">共有メールボックスを変換して、ユーザーの (プライベート) メールボックスに戻す</span><span class="sxs-lookup"><span data-stu-id="85595-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="85595-147"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="85595-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="85595-148">**[受信者]** \> **[共有]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="85595-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="85595-149">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="85595-149">Select the shared mailbox.</span></span> <span data-ttu-id="85595-150">**[通常のメールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85595-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="85595-151">管理センターに戻ります。</span><span class="sxs-lookup"><span data-stu-id="85595-151">Go back to the admin center.</span></span> <span data-ttu-id="85595-152">[**ユーザー**] で古い共有メールボックスに関連付けられているユーザー アカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="85595-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="85595-153">そのアカウントにライセンスを割り当て、パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="85595-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="85595-p113">メールボックスの設定には数分かかりますが、その後ではそのアカウントのユーザーの準備は完了します。それらのユーザーがサインインすると、共有メールボックス内にあったメールと予定表のアイテムが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="85595-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="85595-156">ハイブリッド環境でユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="85595-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="85595-157">この共有メールボックスがハイブリッド環境にある場合、ユーザーのメールボックスをオンプレミスに戻し、ユーザーのメールボックスを共有メールボックスに変換して、共有メールボックスをクラウドに移動することを**強くお勧めします** (ほとんど必須)。</span><span class="sxs-lookup"><span data-stu-id="85595-157">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="85595-158">その理由は次のとおりです。クラウド内のメールボックスを変換すると、変換はされますが、まだオンプレミスではメールボックスがユーザーのメールボックスであると認識されます。これは、新しい現実がオンプレミスに同期されないためです。</span><span class="sxs-lookup"><span data-stu-id="85595-158">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="85595-159">通常、これは問題にはなりませんが、オンプレミスの属性 (メールボックスがユーザーのメールボックスであると考えられる) がそれらの属性の新しいクラウドバージョンを上書きし、その結果としてメールボックスが変換される可能性がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="85595-159">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="85595-160">これは問題です。ユーザーのメールボックスにはライセンスが必要であるか、**30 日後に削除される**ためです。</span><span class="sxs-lookup"><span data-stu-id="85595-160">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="85595-161">既に、これが発生する原因のほとんどに対処してありますが、ごく希に、まだ発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="85595-161">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="85595-162">セキュリティを保護し、メールボックスをオンプレミスに戻してから変換してから、共有メールボックスをクラウドに戻すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85595-162">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="85595-163">この推奨されるソリューションは、オンプレミスのユーザーメールボックスの存在が一時的なものであるため、ハイブリッド環境の使用許諾契約に違反することはありません。</span><span class="sxs-lookup"><span data-stu-id="85595-163">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="85595-164">ユーザーメールボックスまたは共有メールボックスをオンプレミスの組織に保持していて、クラウドに戻していない場合は、ライセンスに違反することになります。</span><span class="sxs-lookup"><span data-stu-id="85595-164">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="85595-165">"Organization Management/受信者管理" 役割グループのメンバーである場合は、Exchange 管理シェルを使用して、ユーザーのメールボックスをオンプレミスの共有メールボックスに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="85595-165">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="85595-166">たとえば、`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared` などです。</span><span class="sxs-lookup"><span data-stu-id="85595-166">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="85595-167">[共有メールボックスが予期せずユーザーのメールボックスに変換され](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)た場合のインスタンスについては、このサポートソリューションの回避策を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85595-167">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="85595-168">関連記事</span><span class="sxs-lookup"><span data-stu-id="85595-168">Related articles</span></span>

[<span data-ttu-id="85595-169">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="85595-169">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="85595-170">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="85595-170">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="85595-171">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="85595-171">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="85595-172">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="85595-172">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="85595-173">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="85595-173">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
