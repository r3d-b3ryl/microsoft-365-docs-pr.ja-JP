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
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737967"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="5bdb8-103">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="5bdb8-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="5bdb8-p101">ユーザーのメールボックスを共有メールボックスに変換した場合、すべての既存のメールと予定表は保持されます。現在は、1 人のユーザーのみではなく何人かのユーザーがアクセスできる共有メールボックスにそれらが入っています。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-p101">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained. Only now it's in a shared mailbox where several people will be able to access it instead of one person. At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="5bdb8-107">**知っておく必要がある重要な点事項を次に示します**</span><span class="sxs-lookup"><span data-stu-id="5bdb8-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="5bdb8-108">共有メールボックスに変換する前に、変換するユーザー メールボックスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="5bdb8-109">そうでない場合、変換オプションがメールボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="5bdb8-110">ライセンスを削除した場合、メールボックスを変換するために再度それを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="5bdb8-111">ライセンスは、メールボックスを共有に変換した後に、ユーザー アカウントから削除できます。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="5bdb8-p103">共有メールボックスには、ライセンスを割り当てずに最大 50 GB のデータを保持できます。それより多くのデータを保持するには、ライセンスが割り当てられている必要があります。ライセンスを削除するために、一連の大きなメール (添付ファイルを含むメールなど) を共有メールボックスから削除して縮小する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-p103">Shared mailboxes can have up to 50 GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="5bdb8-p104">古いユーザー アカウントは削除しないでください。 それは共有メールボックスの固定に必要です。 ユーザー アカウントを既に削除している場合、「[削除済みユーザーのメールボックスを変換する](#convert-the-mailbox-of-a-deleted-user)」 (削除されたユーザーのメールボックスを変換する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="5bdb8-118">メールボックスが共有メールボックスに変換された後でも、ルールは変更されません。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="5bdb8-119">Exchange 管理センターを使用してメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="5bdb8-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="5bdb8-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="5bdb8-121">**[受信者]** \> **[メールボックス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="5bdb8-122">ユーザー メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-122">Select the user mailbox.</span></span> <span data-ttu-id="5bdb8-123">**[共有メールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="5bdb8-124">メールボックスが 50 GB 未満の場合は、ユーザーから[](../manage/remove-licenses-from-users.md)ライセンスを削除し、支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="5bdb8-125">ユーザーのアカウントを削除しない。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-125">Don't delete the user's account.</span></span> <span data-ttu-id="5bdb8-126">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="5bdb8-127">組織を退職する従業員のメールボックスを変換する場合は、追加の手順を実行して、当該の従業員が以後ログインできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="5bdb8-128">「Microsoft [365 から元従業員を削除する」を参照してください](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="5bdb8-129">メールボックスの変換中にユーザーのパスワードをリセットする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="5bdb8-130">ただし、パスワードがリセットされない場合、メールボックスの変換が終了した後も **元のユーザー名とパスワードは引き続き機能します**。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="5bdb8-131">共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5bdb8-132">共有メールボックスには、別途ライセンスが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="5bdb8-133">ただし、In-Place アーカイブを有効にするか、共有メールボックスに In-Place ホールドまたは訴訟ホールドを設定する場合は、exchange Online プラン 1 と Exchange Online Archiving または Exchange Online プラン 2 のライセンスをメールボックスに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="5bdb8-134">削除済みユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="5bdb8-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="5bdb8-p109">削除したユーザー アカウントの古いメールボックスを共有メールボックスに変換したいとします。これには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="5bdb8-137">[ユーザーのアカウントを復元](../add-users/restore-user.md)します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="5bdb8-138">Microsoft 365 ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="5bdb8-139">ユーザーのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="5bdb8-140">メールボックスが再作成されるまで 20 から 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="5bdb8-141">次いでページの指示に従い、それのユーザーのメールボックスを共有メールボックスに変換します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="5bdb8-142">終了したら、ユーザーのメールボックスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="5bdb8-143">ユーザーの古いメールボックスは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="5bdb8-144">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="5bdb8-145">共有メールボックスにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="5bdb8-146">共有メールボックスを変換して、ユーザーの (プライベート) メールボックスに戻す</span><span class="sxs-lookup"><span data-stu-id="5bdb8-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="5bdb8-147"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="5bdb8-148">**[受信者]** \> **[共有]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="5bdb8-149">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-149">Select the shared mailbox.</span></span> <span data-ttu-id="5bdb8-150">**[通常のメールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="5bdb8-151">管理センターに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-151">Go back to the admin center.</span></span> <span data-ttu-id="5bdb8-152">[**ユーザー**] で古い共有メールボックスに関連付けられているユーザー アカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="5bdb8-153">そのアカウントにライセンスを割り当て、パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="5bdb8-p113">メールボックスの設定には数分かかりますが、その後ではそのアカウントのユーザーの準備は完了します。それらのユーザーがサインインすると、共有メールボックス内にあったメールと予定表のアイテムが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="5bdb8-156">ハイブリッド環境でユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="5bdb8-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="5bdb8-157">Exchange ハイブリッド環境でユーザー メールボックスを共有メールボックスに変換する方法の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="5bdb8-158">オンプレミスの Exchange 環境でリモート共有メールボックスを作成または変更するコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5bdb8-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="5bdb8-159">Exchange ハイブリッド展開でディレクトリ同期を実行した後、共有メールボックスが予期せずユーザー メールボックスに変換される</span><span class="sxs-lookup"><span data-stu-id="5bdb8-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="5bdb8-160">組織の管理役割グループまたは受信者の管理役割グループのメンバーである場合は、Exchange 管理シェル を使用して、ユーザー メールボックスをオンプレミスの共有メールボックスに変更できます。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="5bdb8-161">たとえば、`Set-Mailbox -Identity mailbox1@contoso.com -Type Shared` などです。</span><span class="sxs-lookup"><span data-stu-id="5bdb8-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5bdb8-162">関連記事</span><span class="sxs-lookup"><span data-stu-id="5bdb8-162">Related articles</span></span>

[<span data-ttu-id="5bdb8-163">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="5bdb8-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="5bdb8-164">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="5bdb8-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="5bdb8-165">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="5bdb8-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="5bdb8-166">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="5bdb8-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="5bdb8-167">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="5bdb8-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
