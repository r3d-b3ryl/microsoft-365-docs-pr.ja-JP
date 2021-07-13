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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'プライベート メールボックスを、1 人ではなく複数のユーザーがアクセスできる共有メールボックスに変換する方法について説明します。 '
ms.openlocfilehash: caf3935b1ffb36989b2884c6811111531a061098
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393969"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="4683b-103">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="4683b-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="4683b-p101">ユーザーのメールボックスを共有メールボックスに変換した場合、すべての既存のメールと予定表は保持されます。現在は、1 人のユーザーのみではなく何人かのユーザーがアクセスできる共有メールボックスにそれらが入っています。</span><span class="sxs-lookup"><span data-stu-id="4683b-p101">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained. Only now it's in a shared mailbox where several people will be able to access it instead of one person. At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4683b-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="4683b-107">Before you begin</span></span>

<span data-ttu-id="4683b-108">**知っておく必要がある重要な点事項を次に示します**</span><span class="sxs-lookup"><span data-stu-id="4683b-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="4683b-109">共有メールボックスに変換する前に、変換するユーザー メールボックスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4683b-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="4683b-110">そうでない場合、変換オプションがメールボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="4683b-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="4683b-111">ライセンスを削除した場合、メールボックスを変換するために再度それを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4683b-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="4683b-112">ライセンスは、メールボックスを共有に変換した後に、ユーザー アカウントから削除できます。</span><span class="sxs-lookup"><span data-stu-id="4683b-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="4683b-113">共有メールボックスには、ライセンスが割り当てられていない場合、最大 50 GB のデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4683b-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="4683b-114">これ以上のデータを保持するには、ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4683b-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="4683b-115">ライセンスを削除するには、(添付ファイルがあるものなど) 大きなメールを多数削除してサイズを小さくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4683b-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="4683b-p104">古いユーザー アカウントは削除しないでください。 それは共有メールボックスの固定に必要です。 ユーザー アカウントを既に削除している場合、「[削除済みユーザーのメールボックスを変換する](#convert-the-mailbox-of-a-deleted-user)」 (削除されたユーザーのメールボックスを変換する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4683b-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="4683b-119">メールボックスが共有メールボックスに変換された後でも、ルールは変更されません。</span><span class="sxs-lookup"><span data-stu-id="4683b-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="4683b-120">Exchange 管理センターを使用してメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="4683b-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="4683b-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="4683b-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="4683b-122">**[受信者]** \> **[メールボックス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4683b-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="4683b-123">ユーザー メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4683b-123">Select the user mailbox.</span></span> <span data-ttu-id="4683b-124">**[共有メールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4683b-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="4683b-125">メールボックスが 50 GB より小さい場合は、ユーザー[](../manage/remove-licenses-from-users.md)からライセンスを削除し、支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="4683b-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="4683b-126">ユーザーのアカウントを削除しない。</span><span class="sxs-lookup"><span data-stu-id="4683b-126">Don't delete the user's account.</span></span> <span data-ttu-id="4683b-127">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="4683b-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="4683b-128">組織を退職する従業員のメールボックスを変換する場合は、追加の手順を実行して、当該の従業員が以後ログインできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4683b-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="4683b-129">「元[従業員を削除する」を参照Microsoft 365。](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="4683b-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4683b-130">メールボックスの変換中にユーザーのパスワードをリセットする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4683b-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="4683b-131">ただし、パスワードがリセットされない場合、メールボックスの変換が終了した後も **元のユーザー名とパスワードは引き続き機能します**。</span><span class="sxs-lookup"><span data-stu-id="4683b-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="4683b-132">共有メールボックスに関して知っておく必要のあるその他の情報については、「[共有メールボックスの詳細](about-shared-mailboxes.md)」および「[共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4683b-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4683b-133">共有メールボックスには、別途ライセンスが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="4683b-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="4683b-134">ただし、In-Place アーカイブを有効にするか、共有メールボックスに In-Place 保留または訴訟ホールドを設定する場合は、Exchange Online Archiving または Exchange Online プラン 2 ライセンスを持つ Exchange Online プラン 1 をメールボックスに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4683b-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="4683b-135">削除済みユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="4683b-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="4683b-p109">削除したユーザー アカウントの古いメールボックスを共有メールボックスに変換したいとします。これには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4683b-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="4683b-138">[ユーザーのアカウントを復元](../add-users/restore-user.md)します。</span><span class="sxs-lookup"><span data-stu-id="4683b-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="4683b-139">ライセンスが割りMicrosoft 365ライセンスが割り当てられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="4683b-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="4683b-140">ユーザーのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4683b-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="4683b-141">メールボックスが再作成されるまで 20 から 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="4683b-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="4683b-142">次いでページの指示に従い、それのユーザーのメールボックスを共有メールボックスに変換します。</span><span class="sxs-lookup"><span data-stu-id="4683b-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="4683b-143">終了したら、ユーザーのメールボックスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="4683b-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="4683b-144">ユーザーの古いメールボックスは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="4683b-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="4683b-145">共有メールボックスではそれをアンカーとして必要としています。</span><span class="sxs-lookup"><span data-stu-id="4683b-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="4683b-146">共有メールボックスにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4683b-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="4683b-147">共有メールボックスを変換して、ユーザーの (プライベート) メールボックスに戻す</span><span class="sxs-lookup"><span data-stu-id="4683b-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="4683b-148"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="4683b-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="4683b-149">**[受信者]** \> **[共有]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4683b-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="4683b-150">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4683b-150">Select the shared mailbox.</span></span> <span data-ttu-id="4683b-151">**[通常のメールボックスに変換]** で **[変換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4683b-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="4683b-152">管理センターに戻ります。</span><span class="sxs-lookup"><span data-stu-id="4683b-152">Go back to the admin center.</span></span> <span data-ttu-id="4683b-153">[**ユーザー**] で古い共有メールボックスに関連付けられているユーザー アカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="4683b-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="4683b-154">そのアカウントにライセンスを割り当て、パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4683b-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="4683b-p113">メールボックスの設定には数分かかりますが、その後ではそのアカウントのユーザーの準備は完了します。それらのユーザーがサインインすると、共有メールボックス内にあったメールと予定表のアイテムが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="4683b-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="4683b-157">ハイブリッド環境でユーザーのメールボックスを変換する</span><span class="sxs-lookup"><span data-stu-id="4683b-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="4683b-158">ハイブリッド環境でユーザー メールボックスを共有メールボックスに変換する方法のExchange参照してください。</span><span class="sxs-lookup"><span data-stu-id="4683b-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="4683b-159">オンプレミスのユーザー環境でリモート共有メールボックスを作成または変更Exchangeコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4683b-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="4683b-160">共有メールボックスは、ハイブリッド展開でディレクトリ同期を実行した後、予期Exchangeユーザー メールボックスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="4683b-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="4683b-161">組織の管理役割グループまたは受信者管理役割グループのメンバーである場合は、Exchange 管理シェルを使用して、ユーザー メールボックスをオンプレミスの共有メールボックスに変更できます。</span><span class="sxs-lookup"><span data-stu-id="4683b-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="4683b-162">たとえば、`Set-Mailbox -Identity mailbox1@contoso.com -Type Shared` などです。</span><span class="sxs-lookup"><span data-stu-id="4683b-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="4683b-163">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4683b-163">Related content</span></span>

<span data-ttu-id="4683b-164">[共有メールボックスについて](about-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4683b-164">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="4683b-165">[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4683b-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4683b-166">[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4683b-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4683b-167">[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4683b-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4683b-168">[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4683b-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>