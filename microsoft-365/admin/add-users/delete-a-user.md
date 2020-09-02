---
title: 組織からユーザーを削除する
f1.keywords:
- NOCSH
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
- Adm_TOC
- SPO_Content
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: ユーザーアカウントを削除する方法について説明します。 ユーザーの電子メールと OneDrive コンテンツの処理方法を決定します。 製品のライセンスを保持するか、または製品の支払いを停止するかを決定します。
ms.openlocfilehash: bcccaa13614114c9588c43d857336bce44a84147
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324562"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="23186-105">組織からユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="23186-105">Delete a user from your organization</span></span>
  
<span data-ttu-id="23186-106">**職場または学校で使用する*自分の\* Microsoft 365 ユーザー アカウントを削除する方法をお探しの場合は、職場または大学のテクニカル サポートにこれらの手順の実行を依頼してください。*\*</span><span class="sxs-lookup"><span data-stu-id="23186-106">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>

## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="23186-107">ユーザーの削除について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="23186-107">What you need to know about deleting users</span></span>

- <span data-ttu-id="23186-108">ユーザー アカウントを削除できるのは、職場や学校の [Microsoft 365 グローバル管理者](about-admin-roles.md)またはユーザー管理のアクセス許可を持っている管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="23186-108">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span>
- <span data-ttu-id="23186-109">30 日後にユーザーのデータが永久に削除されるまではアカウントを[復元](restore-user.md)できます。</span><span class="sxs-lookup"><span data-stu-id="23186-109">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span>
- <span data-ttu-id="23186-110">ユーザーの OneDrive データを保持する場合は、別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="23186-110">If you want to keep the user's OneDrive data, move it to a different location.</span></span> <span data-ttu-id="23186-111">アカウントを削除した後、30日以内にデータを移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="23186-111">You can even move the data up to 30 days after deleting the account.</span></span> <span data-ttu-id="23186-112">「 [元ユーザーのデータにアクセスしてバックアップを作成する](get-access-to-and-back-up-a-former-user-s-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-112">See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span> <span data-ttu-id="23186-113">SharePoint ファイルを移動する必要はありません。引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23186-113">You don't need to move their SharePoint files; you'll still have access to them.</span></span>
- <span data-ttu-id="23186-p103">ユーザーのメールを保持する場合は、アカウントを削除する**前に**、メールを別の場所に移動します。アカウントを既に削除した場合は、30 日以内であれば、復元してメール データを移動し、アカウントを削除できます。「[元ユーザーのデータにアクセスしてバックアップを作成する](get-access-to-and-back-up-a-former-user-s-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
- <span data-ttu-id="23186-117">Office 365 Enterprise E3 などのエンタープライズ サブスクリプションがある場合、削除したユーザー アカウントのメールボックスを*非アクティブなメールボックス*に変更することで、そのメールボックスのデータを保持できます。</span><span class="sxs-lookup"><span data-stu-id="23186-117">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="23186-118">詳細については、「[Exchange Online の非アクティブなメールボックスを管理する](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-118">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="23186-119">グローバル管理者: ユーザーを削除し、それらのユーザーのライセンスの支払いを停止し、それらのユーザーのメールと OneDrive のコンテンツの処置方法を選択する</span><span class="sxs-lookup"><span data-stu-id="23186-119">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="23186-120">グローバル管理者は、ユーザーを削除した際に、それらのユーザーのメールへのアクセス権を別のユーザーに付与したり、それらのユーザーの OneDrive コンテンツの処置方法を決定したりできます。</span><span class="sxs-lookup"><span data-stu-id="23186-120">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span>

### <a name="things-to-consider"></a><span data-ttu-id="23186-121">考慮事項</span><span class="sxs-lookup"><span data-stu-id="23186-121">Things to consider...</span></span>

<span data-ttu-id="23186-122">作業を開始する前に、ユーザーのメールと OneDrive コンテンツの処置方法、ライセンスを保持するのかそれとも支払いを停止するのかについて検討します。</span><span class="sxs-lookup"><span data-stu-id="23186-122">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|<span data-ttu-id="23186-123">アイテム</span><span class="sxs-lookup"><span data-stu-id="23186-123">Item</span></span> | <span data-ttu-id="23186-124">説明</span><span class="sxs-lookup"><span data-stu-id="23186-124">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="23186-125">製品のライセンス</span><span class="sxs-lookup"><span data-stu-id="23186-125">Product licenses</span></span>  <br/> |<span data-ttu-id="23186-126">ライセンスをユーザーから削除してライセンスを組織のサブスクリプションから削除すると、ライセンスに対する支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="23186-126">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="23186-127">このオプションを選択した場合、ライセンスがサブスクリプションから自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="23186-127">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="23186-128">パートナー経由またはボリューム ライセンスを通して購入したライセンスは**削除できません**。</span><span class="sxs-lookup"><span data-stu-id="23186-128">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="23186-129">年間プランに支払っている場合や、請求サイクルの途中にいる場合は、コミットメントが完了するまでライセンスをサブスクリプションから削除できません。</span><span class="sxs-lookup"><span data-stu-id="23186-129">If you're paying for an annual plan or if you're in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="23186-130">OneDrive のコンテンツ</span><span class="sxs-lookup"><span data-stu-id="23186-130">OneDrive content</span></span>  <br/> |<span data-ttu-id="23186-131">ユーザーがファイルを OneDrive に保存していた場合、これらのファイルへのアクセス権を別のユーザーに付与することができます。</span><span class="sxs-lookup"><span data-stu-id="23186-131">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="23186-132">保持するファイルは、OneDrive のファイルに対して設定されている保持期間内に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23186-132">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="23186-133">**既定の保持期間は 30 日です。**</span><span class="sxs-lookup"><span data-stu-id="23186-133">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="23186-134">ユーザーを削除した後に保持期間内にファイルを移動しない場合、OneDrive のコンテンツは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="23186-134">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="23186-135">削除されたアカウントの OneDrive ファイルを保持する日数を増やすには、「[削除されたユーザーの OneDrive の保持期間を設定する](https://docs.microsoft.com/onedrive/set-retention)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-135">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://docs.microsoft.com/onedrive/set-retention).</span></span>  <br/><br/> <span data-ttu-id="23186-136">**重要!**</span><span class="sxs-lookup"><span data-stu-id="23186-136">**Important!**</span></span> <span data-ttu-id="23186-137">削除されたユーザーが個人のコンピューターを使用して SharePoint および OneDrive からファイルをダウンロードしていた場合、ユーザーが自分のコンピューターに保存したファイルを管理者が削除する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="23186-137">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="23186-138">OneDrive から同期されたファイルに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23186-138">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="23186-139">メール</span><span class="sxs-lookup"><span data-stu-id="23186-139">Email</span></span>  <br/> | <span data-ttu-id="23186-140">削除したユーザーのメールへのアクセス権を別のユーザーに付与すると、削除されたユーザーのメールボックスは共有メールボックスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="23186-140">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="23186-141">メールボックスの新しい所有者は、メールボックスにアクセスして新しいメールを監視できます。</span><span class="sxs-lookup"><span data-stu-id="23186-141">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="23186-142">以下のオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="23186-142">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="23186-143">表示名を変更する-[ **アクティブなユーザー** ] リストで共有メールボックスを簡単に識別できるように、表示名を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="23186-143">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the **Active users** list.</span></span>  <br/>  <span data-ttu-id="23186-144">自動応答を有効にする - 丁寧な文面のメッセージが自動応答用に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="23186-144">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="23186-145">組織内のユーザーや組織外のユーザーに、さまざまな自動返信を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="23186-145">You can send different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="23186-146">エイリアスをクリーンアップする - エイリアスとは、ユーザーの追加のメール アドレスのことです。</span><span class="sxs-lookup"><span data-stu-id="23186-146">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="23186-147">組織によっては、エイリアスを使用していません。エイリアスがない場合、何も操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="23186-147">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="23186-148">ユーザーがエイリアスを持っている場合は、それらのメールアドレスを再利用できるように、それらを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="23186-148">If the user does have aliases, we recommend removing them so that you can reuse those email addresses.</span></span> <span data-ttu-id="23186-149">それ以外の場合、削除されたメールボックスの保存期間が経過するまで、これらの電子メールアドレスを再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="23186-149">Otherwise, you can't reuse those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="23186-150">既定では、削除したメールボックスは 30 日間回復可能です。</span><span class="sxs-lookup"><span data-stu-id="23186-150">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="23186-151">詳細については、「 [Exchange Online のユーザー メールボックスを削除または復元する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-151">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="23186-152">Active Directory</span><span class="sxs-lookup"><span data-stu-id="23186-152">Active Directory</span></span>  <br/> |<span data-ttu-id="23186-153">お客様の一般法人で Azure AD と同期している **Active Directory** を使用する場合は、Active Directory からユーザー アカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23186-153">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="23186-154">Office 365 からこの操作を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="23186-154">You can't do it through Office 365.</span></span> <span data-ttu-id="23186-155">手順については、「[ユーザー アカウントを削除する](https://go.microsoft.com/fwlink/p/?linkid=841808)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-155">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |

### <a name="get-started"></a><span data-ttu-id="23186-156">作業の開始</span><span class="sxs-lookup"><span data-stu-id="23186-156">Get started</span></span>

<span data-ttu-id="23186-157">ユーザーを削除する手順は、ガイドに従って実行できます。以下の方法でガイドを開始できます。</span><span class="sxs-lookup"><span data-stu-id="23186-157">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="23186-158">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="23186-159">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="23186-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="23186-160">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="23186-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="23186-161">削除するユーザーを選択し、[ **ユーザーの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-161">Select the user that you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="23186-162">ユーザー管理の管理者: Office 365 から 1 人または複数のユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="23186-162">User management admin: Delete one or more users from Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23186-p113">アカウントを[共有メールボックスに変換した場合](../email/convert-user-mailbox-to-shared-mailbox.md)や、アカウントでメールの転送を設定した場合、ユーザーのアカウントを削除しないでください。これらの機能には、アカウントが必要です。共有メールボックスにはライセンスは必要ありません。アカウントを共有メールボックスに変換した場合は、[ライセンスの支払いを停止](#stop-paying-for-the-license)できます。アカウントでメール転送を設定している場合、ライセンスを削除することはできません。これを行うと、メールの転送が停止し、メールボックスが非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="23186-p113">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account. Those functions still need the account. A shared mailbox doesn't require a license. If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license). If you've set up email forwarding on the account, you can't remove the license. Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="23186-169">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="23186-170">削除するユーザーの名前を選択し、[**その他のオプション**] (**...**) を選択し、[**ユーザー の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-170">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="23186-171">これによりユーザーのアカウントは削除されますが、**ライセンスの支払いは継続します**。</span><span class="sxs-lookup"><span data-stu-id="23186-171">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="23186-172">ライセンスの支払いを停止するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-172">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="23186-173">または、ライセンスを別のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="23186-173">Or, you can assign the license to another user.</span></span> <span data-ttu-id="23186-174">ライセンスが自動的に別のユーザーに割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="23186-174">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="23186-175">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-175">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="23186-176">削除するユーザーの名前を選択し、[**一括操作**] ウィンドウで [**ユーザー の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-176">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="23186-177">これによりユーザーのアカウントは削除されますが、**ライセンスの支払いは継続します**。</span><span class="sxs-lookup"><span data-stu-id="23186-177">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="23186-178">ライセンスの支払いを停止するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-178">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="23186-179">または、ライセンスを別のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="23186-179">Or, you can assign the license to another user.</span></span> <span data-ttu-id="23186-180">ライセンスが自動的に別のユーザーに割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="23186-180">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23186-181">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-181">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="23186-182">削除するユーザーの名前を選択し、[**一括操作**] ウィンドウで [**ユーザー の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-182">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="23186-183">これによりユーザーのアカウントは削除されますが、**ライセンスの支払いは継続します**。</span><span class="sxs-lookup"><span data-stu-id="23186-183">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="23186-184">ライセンスの支払いを停止するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-184">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="23186-185">または、ライセンスを別のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="23186-185">Or, you can assign the license to another user.</span></span> <span data-ttu-id="23186-186">ライセンスが自動的に別のユーザーに割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="23186-186">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="23186-187">ライセンスの支払いを停止する</span><span class="sxs-lookup"><span data-stu-id="23186-187">Stop paying for the license</span></span>

<span data-ttu-id="23186-188">ライセンス数を減らす作業は別の手順になり、グローバル管理者または請求管理者のみがこれを行えます。</span><span class="sxs-lookup"><span data-stu-id="23186-188">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="23186-189">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="23186-189">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span> <span data-ttu-id="23186-190">このオプションが表示されない場合は、グローバル管理者または請求管理者ではないことを意味します。この場合、この手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="23186-190">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="23186-191">[ **製品** ] タブで、ライセンスを削除するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-191">On the **Products** tab, select the subscription that you want to remove licenses for.</span></span>

3. <span data-ttu-id="23186-192">[サブスクリプションの詳細] ページで、[ **ライセンスの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-192">On the subscription details page, select **Remove licenses**.</span></span>

4. <span data-ttu-id="23186-193">[ **ライセンスの削除** ] ウィンドウの [ **新しい数量**] の下にある [ **ライセンスの合計** 数] ボックスに、このサブスクリプションで使用するライセンスの総数を入力します。</span><span class="sxs-lookup"><span data-stu-id="23186-193">In the **Remove licenses** pane, under **New quantity**, in the **Total licenses** box, enter the total number of licenses that you want for this subscription.</span></span> <span data-ttu-id="23186-194">たとえば、100ライセンスを所有していて、そのうちの5つを削除する場合は、「95」と入力します。</span><span class="sxs-lookup"><span data-stu-id="23186-194">For example, if you have 100 licenses and you want to remove five of them, enter 95.</span></span>

5. <span data-ttu-id="23186-195">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23186-195">Select **Save**.</span></span>

<span data-ttu-id="23186-196">将来、新しいユーザーを組織のサブスクリプションに追加する手順を実行すると、ライセンスの購入を求めるメッセージが表示されるため、手間が省けます。</span><span class="sxs-lookup"><span data-stu-id="23186-196">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="23186-197">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="23186-197">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="23186-198">このオプションが表示されない場合は、グローバル管理者または請求管理者ではないことを意味します。この場合、この手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="23186-198">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="23186-199">(サブスクリプションが複数ある場合は) サブスクリプションを選択し、[**ライセンスの追加/削除**] を選択してライセンスを削除します。こうすることで、新しい従業員を採用するまでライセンスの支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="23186-199">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="23186-200">将来、新しいユーザーを組織のサブスクリプションに追加する手順を実行すると、ライセンスの購入を求めるメッセージが表示されるため、手間が省けます。</span><span class="sxs-lookup"><span data-stu-id="23186-200">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23186-201">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="23186-201">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="23186-202">このオプションが表示されない場合は、グローバル管理者または請求管理者ではないことを意味します。この場合、この手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="23186-202">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="23186-203">(サブスクリプションが複数ある場合は) サブスクリプションを選択し、[**ライセンスの追加/削除**] を選択してライセンスを削除します。こうすることで、新しい従業員を採用するまでライセンスの支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="23186-203">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="23186-204">将来、新しいユーザーを組織のサブスクリプションに追加する手順を実行すると、ライセンスの購入を求めるメッセージが表示されるため、手間が省けます。</span><span class="sxs-lookup"><span data-stu-id="23186-204">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="23186-205">多数のユーザーを同時に削除する</span><span class="sxs-lookup"><span data-stu-id="23186-205">Delete many users at the same time</span></span>

<span data-ttu-id="23186-206">[Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell コマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-206">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="23186-207">ユーザーの削除に関する問題を解決する</span><span class="sxs-lookup"><span data-stu-id="23186-207">Fix issues with deleting a user</span></span>

<span data-ttu-id="23186-208">ユーザーを削除するときに発生する最も一般的な問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="23186-208">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="23186-209">**"ユーザーが削除できません。後でもう一度お試しください。" の行でエラーが発生しました。**</span><span class="sxs-lookup"><span data-stu-id="23186-209">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="23186-210">アカウントに電子メール転送が設定されているかどうかを再確認するか、共有メールボックスに変換します。</span><span class="sxs-lookup"><span data-stu-id="23186-210">Double-check whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="23186-211">これらの両方でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="23186-211">Both of these will cause that error.</span></span> <span data-ttu-id="23186-212">メール転送を設定している場合、または共有メールボックスに変換した場合は、アカウントを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="23186-212">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="23186-213">**ユーザーを削除するための適切なアクセス許可がありません**。</span><span class="sxs-lookup"><span data-stu-id="23186-213">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="23186-214">ユーザーを削除できるのは、[Microsoft 365 のグローバル管理者またはユーザー管理の管理者](about-admin-roles.md)のみです。</span><span class="sxs-lookup"><span data-stu-id="23186-214">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="23186-215">通常は、学校または職場のテクニカル サポートです。</span><span class="sxs-lookup"><span data-stu-id="23186-215">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="23186-216">**ユーザーを削除しても、その名前がグローバル アドレス帳に表示され続けます** 。</span><span class="sxs-lookup"><span data-stu-id="23186-216">**You delete the user but their name continues appear in your global address book**.</span></span> <span data-ttu-id="23186-217">これは、業務で Active Directory を使用している場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="23186-217">This happens when a business is using Active Directory.</span></span> <span data-ttu-id="23186-218">Active Directory からユーザーアカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23186-218">You must delete the users account from Active Directory.</span></span> <span data-ttu-id="23186-219">手順については、「[ユーザーアカウントを削除する](https://go.microsoft.com/fwlink/p/?linkid=841808)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23186-219">For instructions, see [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

<span data-ttu-id="23186-220">**自分のコンピューターから Microsoft 365 を削除する場合は、[サブスクリプションのキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)に移動します。**</span><span class="sxs-lookup"><span data-stu-id="23186-220">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>

## <a name="related-articles"></a><span data-ttu-id="23186-221">関連記事</span><span class="sxs-lookup"><span data-stu-id="23186-221">Related articles</span></span>

[<span data-ttu-id="23186-222">ユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="23186-222">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="23186-223">メールボックスを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="23186-223">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="23186-224">Office 365 から元従業員を削除する</span><span class="sxs-lookup"><span data-stu-id="23186-224">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="23186-225">Office 365 に新しい従業員を追加する</span><span class="sxs-lookup"><span data-stu-id="23186-225">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="23186-226">[ユーザー アカウントを削除する](https://go.microsoft.com/fwlink/p/?linkid=841808):Azure AD と同期している **Active Directory** を組織で使用している場合は、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="23186-226">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="23186-227">Office 365 からこの操作を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="23186-227">You can't do it through Office 365.</span></span>