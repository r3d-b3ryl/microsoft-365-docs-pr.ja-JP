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
ms.openlocfilehash: fa8e37b5e924f1b38755a953f40d8b70011213d0
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698281"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="cceef-103">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="cceef-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="cceef-p101">ユーザーのメールボックスを共有メールボックスに変換した場合、すべての既存のメールと予定表は保持されます。現在は、1 人のユーザーのみではなく何人かのユーザーがアクセスできる共有メールボックスにそれらが入っています。</span><span class="sxs-lookup"><span data-stu-id="cceef-p101">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained. Only now it's in a shared mailbox where several people will be able to access it instead of one person. At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="cceef-107">**知っておく必要がある重要な点事項を次に示します**</span><span class="sxs-lookup"><span data-stu-id="cceef-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="cceef-108">共有メールボックスに変換する前に、変換するユーザー メールボックスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cceef-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="cceef-109">そうでない場合、変換オプションがメールボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="cceef-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="cceef-110">ライセンスを削除した場合、メールボックスを変換するために再度それを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cceef-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="cceef-111">ライセンスは、メールボックスを共有に変換した後に、ユーザー アカウントから削除できます。</span><span class="sxs-lookup"><span data-stu-id="cceef-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="cceef-p103">共有メールボックスには、ライセンスを割り当てずに最大 50 GB のデータを保持できます。それより多くのデータを保持するには、ライセンスが割り当てられている必要があります。ライセンスを削除するために、一連の大きなメール (添付ファイルを含むメールなど) を共有メールボックスから削除して縮小する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="cceef-p103">Shared mailboxes can have up to 50 GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="cceef-p104">古いユーザー アカウントは削除しないでください。 それは共有メールボックスの固定に必要です。 ユーザー アカウントを既に削除している場合、「[削除済みユーザーのメールボックスを変換する](#convert-the-mailbox-of-a-deleted-user)」 (削除されたユーザーのメールボックスを変換する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cceef-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="cceef-118">メールボックスが共有メールボックスに変換された後でも、ルールは変更されません。</span><span class="sxs-lookup"><span data-stu-id="cceef-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="cceef-119">Exchange 管理センターを使用してメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="cceef-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="cceef-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="cceef-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="cceef-121">**[受信者]** \> **[メールボックス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cceef-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="cceef-122">ユーザー メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="cceef-122">Select the user mailbox.</span></span> <span data-ttu-id="cceef-123">**[共有メールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cceef-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="cceef-124">メールボックスが 50 GB 未満の場合は、ユーザーから[](../manage/remove-licenses-from-users.md)ライセンスを削除し、支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="cceef-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="cceef-125">ユーザーのアカウントを削除しない。</span><span class="sxs-lookup"><span data-stu-id="cceef-125">Don't delete the user's account.</span></span> <span data-ttu-id="cceef-126">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="cceef-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="cceef-127">組織を退職する従業員のメールボックスを変換する場合は、追加の手順を実行して、当該の従業員が以後ログインできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cceef-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="cceef-128">「Microsoft [365 から元従業員を削除する」を参照してください](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="cceef-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="cceef-129">メールボックスの変換中にユーザーのパスワードをリセットする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cceef-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="cceef-130">ただし、パスワードがリセットされない場合、メールボックスの変換が終了した後も **元のユーザー名とパスワードは引き続き機能します**。</span><span class="sxs-lookup"><span data-stu-id="cceef-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="cceef-131">共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cceef-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cceef-132">共有メールボックスには、別途ライセンスが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="cceef-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="cceef-133">ただし、In-Place アーカイブを有効にするか、共有メールボックスに In-Place ホールドまたは訴訟ホールドを設定する場合は、Exchange Online プラン 1 と Exchange Online Archiving または Exchange Online プラン 2 のライセンスをメールボックスに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cceef-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="cceef-134">削除済みユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="cceef-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="cceef-p109">削除したユーザー アカウントの古いメールボックスを共有メールボックスに変換したいとします。これには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cceef-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="cceef-137">[ユーザーのアカウントを復元](../add-users/restore-user.md)します。</span><span class="sxs-lookup"><span data-stu-id="cceef-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="cceef-138">Microsoft 365 ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cceef-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="cceef-139">ユーザーのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="cceef-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="cceef-140">メールボックスが再作成されるまで 20 から 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="cceef-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="cceef-141">次いでページの指示に従い、それのユーザーのメールボックスを共有メールボックスに変換します。</span><span class="sxs-lookup"><span data-stu-id="cceef-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="cceef-142">終了したら、ユーザーのメールボックスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="cceef-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="cceef-143">ユーザーの古いメールボックスは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="cceef-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="cceef-144">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="cceef-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="cceef-145">共有メールボックスにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cceef-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="cceef-146">共有メールボックスを変換して、ユーザーの (プライベート) メールボックスに戻す</span><span class="sxs-lookup"><span data-stu-id="cceef-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="cceef-147"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="cceef-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="cceef-148">**[受信者]** \> **[共有]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cceef-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="cceef-149">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="cceef-149">Select the shared mailbox.</span></span> <span data-ttu-id="cceef-150">**[通常のメールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cceef-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="cceef-151">管理センターに戻ります。</span><span class="sxs-lookup"><span data-stu-id="cceef-151">Go back to the admin center.</span></span> <span data-ttu-id="cceef-152">[**ユーザー**] で古い共有メールボックスに関連付けられているユーザー アカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="cceef-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="cceef-153">そのアカウントにライセンスを割り当て、パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="cceef-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="cceef-p113">メールボックスの設定には数分かかりますが、その後ではそのアカウントのユーザーの準備は完了します。それらのユーザーがサインインすると、共有メールボックス内にあったメールと予定表のアイテムが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="cceef-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="cceef-156">ハイブリッド環境でユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="cceef-156">Convert a user's mailbox in a hybrid environment</span></span>

> [!NOTE] 
> <span data-ttu-id="cceef-157">2018 年 10 月 11 日から、Exchange ハイブリッド展開は、オンプレミスの Exchange Server 環境で、Exchange Server 2013 の累積的な更新プログラム 21 および Exchange Server 2016 の累積的な更新プログラム 10 から始まるリモート共有メールボックスの作成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cceef-157">Starting October 11th, 2018, Exchange hybrid deployment supports the creation of remote shared mailboxes starting in Cumulative Update 21 for Exchange Server 2013 and Cumulative Update 10 for Exchange Server 2016 in an on-premises Exchange Server environment.</span></span> <span data-ttu-id="cceef-158">新しい -shared パラメーターを使用して、リモート共有メールボックスを直接 _作成または変更_ できます。</span><span class="sxs-lookup"><span data-stu-id="cceef-158">You can directly create or modify a remote shared mailbox by using the new _-shared_ parameter.</span></span> <span data-ttu-id="cceef-159">詳細については、「コマンドレット」を参照して、オンプレミスの Exchange 環境でリモート共有メールボックス [を作成または変更します](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange)。</span><span class="sxs-lookup"><span data-stu-id="cceef-159">For more information, visit [Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange).</span></span>

<span data-ttu-id="cceef-160">この共有メールボックスがハイブリッド環境内にいて、上記のシナリオに当てはかからない場合は、ユーザー メールボックスをオンプレミスに戻し、ユーザー メールボックスを共有メールボックスに変換してから、共有メールボックスをクラウドに移動 **することを強く** 推奨します (ほとんど必要です)。</span><span class="sxs-lookup"><span data-stu-id="cceef-160">If this shared mailbox is in a hybrid environment and not falling under the above scenario, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="cceef-161">その理由は次のとおりです。クラウド内のメールボックスを変換すると、変換はされますが、まだオンプレミスではメールボックスがユーザーのメールボックスであると認識されます。これは、新しい現実がオンプレミスに同期されないためです。</span><span class="sxs-lookup"><span data-stu-id="cceef-161">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="cceef-162">通常、これは問題にはなりませんが、オンプレミスの属性 (メールボックスがユーザーのメールボックスであると考えられる) がそれらの属性の新しいクラウドバージョンを上書きし、その結果としてメールボックスが変換される可能性がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="cceef-162">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="cceef-163">これは問題です。ユーザーのメールボックスにはライセンスが必要であるか、**30 日後に削除される** ためです。</span><span class="sxs-lookup"><span data-stu-id="cceef-163">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="cceef-164">既に、これが発生する原因のほとんどに対処してありますが、ごく希に、まだ発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cceef-164">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="cceef-165">安全で、メールボックスをオンプレミスに戻し、変換してから、共有メールボックスをクラウドに戻すのが最善です。</span><span class="sxs-lookup"><span data-stu-id="cceef-165">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="cceef-166">オンプレミスのユーザー メールボックスの存在は一時的なだけなので、この推奨ソリューションはハイブリッド環境のライセンス契約に違反しません。</span><span class="sxs-lookup"><span data-stu-id="cceef-166">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="cceef-167">ユーザー メールボックスまたは共有メールボックスをオンプレミス組織で維持し、クラウドに戻していない場合は、ライセンスに違反します。</span><span class="sxs-lookup"><span data-stu-id="cceef-167">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>


> [!NOTE]
> <span data-ttu-id="cceef-168">組織の管理役割グループまたは受信者の管理役割グループのメンバーである場合は、Exchange 管理シェルを使用して、ユーザー メールボックスをオンプレミスの共有メールボックスに変更できます。</span><span class="sxs-lookup"><span data-stu-id="cceef-168">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="cceef-169">たとえば、`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared` などです。</span><span class="sxs-lookup"><span data-stu-id="cceef-169">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="cceef-170">共有メールボックスが予期せずユーザーのメールボックスに変換された場合のインスタンスについては、このサポート ソリューションの回避策 [を参照してください](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)。</span><span class="sxs-lookup"><span data-stu-id="cceef-170">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="cceef-171">関連記事</span><span class="sxs-lookup"><span data-stu-id="cceef-171">Related articles</span></span>

[<span data-ttu-id="cceef-172">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="cceef-172">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="cceef-173">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="cceef-173">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="cceef-174">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="cceef-174">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="cceef-175">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="cceef-175">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="cceef-176">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="cceef-176">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
