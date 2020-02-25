---
title: 組織からユーザーを削除する
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
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: ユーザー アカウントを削除する方法を説明します。 ユーザーのメールと OneDrive のコンテンツの処置方法に関する決定や、製品ライセンスを保持するのか支払いを停止するのかに関する決定を行います。
ms.openlocfilehash: f54d0d4a39ff116b4bee6aceb10233344835a455
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241638"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="77cb9-104">組織からユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="77cb9-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="77cb9-105">**職場または学校で使用する*自分の\* Office 365 ユーザー アカウントを削除する方法をお探しの場合は、職場または大学のテクニカル サポートにこれらの手順の実行を依頼してください。*\*</span><span class="sxs-lookup"><span data-stu-id="77cb9-105">**Looking for how to delete your *own* Office 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="77cb9-106">ユーザーの削除について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="77cb9-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="77cb9-107">ユーザー アカウントを削除できるのは、職場や学校の [Office 365 グローバル管理者](about-admin-roles.md)またはユーザー管理のアクセス許可を持っている管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="77cb9-107">Only people who have [Office 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="77cb9-108">30 日後にユーザーのデータが永久に削除されるまではアカウントを[復元](restore-user.md)できます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="77cb9-p102">ユーザーの OneDrive データを保持する場合は、そのデータを別の場所に移動します。アカウントを削除してから 30 日以内であれば、この操作を行うことができます。「[元ユーザーのデータにアクセスしてバックアップを作成する](get-access-to-and-back-up-a-former-user-s-data.md)」を参照してください。SharePoint ファイルを移動する必要はありません。引き続きファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="77cb9-p103">ユーザーのメールを保持する場合は、アカウントを削除する**前に**、メールを別の場所に移動します。アカウントを既に削除した場合は、30 日以内であれば、復元してメール データを移動し、アカウントを削除できます。「[元ユーザーのデータにアクセスしてバックアップを作成する](get-access-to-and-back-up-a-former-user-s-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="77cb9-116">Office 365 Enterprise E3 などのエンタープライズ サブスクリプションがある場合、削除した Office 365 ユーザー アカウントのメールボックスを*非アクティブなメールボックス*に変更することで、そのメールボックスのデータを保持できます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted Office 365 user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="77cb9-117">詳細については、「[Exchange Online の非アクティブなメールボックスを管理する](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="77cb9-118">グローバル管理者: ユーザーを削除し、それらのユーザーのライセンスの支払いを停止し、それらのユーザーのメールと OneDrive のコンテンツの処置方法を選択する</span><span class="sxs-lookup"><span data-stu-id="77cb9-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="77cb9-119">グローバル管理者は、ユーザーを削除した際に、それらのユーザーのメールへのアクセス権を別のユーザーに付与したり、それらのユーザーの OneDrive コンテンツの処置方法を決定したりできます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="77cb9-120">考慮事項</span><span class="sxs-lookup"><span data-stu-id="77cb9-120">Things to consider...</span></span>

<span data-ttu-id="77cb9-121">作業を開始する前に、ユーザーのメールと OneDrive コンテンツの処置方法、ライセンスを保持するのかそれとも支払いを停止するのかについて検討します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="77cb9-122">製品のライセンス</span><span class="sxs-lookup"><span data-stu-id="77cb9-122">Product licenses</span></span>  <br/> |<span data-ttu-id="77cb9-123">ライセンスをユーザーから削除してライセンスを組織のサブスクリプションから削除すると、ライセンスに対する支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-123">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="77cb9-124">このオプションを選択した場合、ライセンスがサブスクリプションから自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-124">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="77cb9-125">パートナー経由またはボリューム ライセンスを通して購入したライセンスは**削除できません**。</span><span class="sxs-lookup"><span data-stu-id="77cb9-125">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="77cb9-126">年間プランのお支払いを行っている場合、または課金サイクルの途中の時期の場合、契約が満了するまではサブスクリプションからライセンスを削除できません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-126">If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="77cb9-127">OneDrive のコンテンツ</span><span class="sxs-lookup"><span data-stu-id="77cb9-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="77cb9-128">ユーザーがファイルを OneDrive に保存していた場合、これらのファイルへのアクセス権を別のユーザーに付与することができます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="77cb9-129">保持するファイルは、OneDrive のファイルに対して設定されている保持期間内に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77cb9-129">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="77cb9-130">**既定の保持期間は 30 日です。**</span><span class="sxs-lookup"><span data-stu-id="77cb9-130">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="77cb9-131">ユーザーを削除した後に保持期間内にファイルを移動しない場合、OneDrive のコンテンツは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-131">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="77cb9-132">削除されたアカウントの OneDrive ファイルを保持する日数を増やすには、「[削除されたユーザーの OneDrive の保持期間を設定する](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-132">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span></span>  <br/><br/> <span data-ttu-id="77cb9-133">**重要!**</span><span class="sxs-lookup"><span data-stu-id="77cb9-133">**Important!**</span></span> <span data-ttu-id="77cb9-134">削除されたユーザーが個人のコンピューターを使用して SharePoint および OneDrive からファイルをダウンロードしていた場合、ユーザーが自分のコンピューターに保存したファイルを管理者が削除する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="77cb9-135">OneDrive から同期されたファイルに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="77cb9-136">メール</span><span class="sxs-lookup"><span data-stu-id="77cb9-136">Email</span></span>  <br/> | <span data-ttu-id="77cb9-137">削除したユーザーのメールへのアクセス権を別のユーザーに付与すると、削除されたユーザーのメールボックスは共有メールボックスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-137">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="77cb9-138">メールボックスの新しい所有者は、メールボックスにアクセスして新しいメールを監視できます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-138">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="77cb9-139">以下のオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="77cb9-139">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="77cb9-140">表示名を変更する - [アクティブなユーザー] リストで共有メールボックスを簡単に識別できるように、表示名を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77cb9-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="77cb9-141">自動応答を有効にする - 丁寧な文面のメッセージが自動応答用に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="77cb9-141">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="77cb9-142">組織内のユーザーと組織外のユーザーに異なる自動応答を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-142">You can send a different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="77cb9-143">エイリアスをクリーンアップする - エイリアスとは、ユーザーの追加のメール アドレスのことです。</span><span class="sxs-lookup"><span data-stu-id="77cb9-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="77cb9-144">組織によっては、エイリアスを使用していません。エイリアスがない場合、何も操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="77cb9-145">ユーザーがエイリアスを持っている場合はそれらを削除し、それらのメール アドレスを再利用できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77cb9-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="77cb9-146">削除しない場合、削除されたメールボックスの保持期間が経過するまで、これらのメール アドレスを再利用できません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-146">Otherwise, you can’t re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="77cb9-147">既定では、削除したメールボックスは 30 日間回復可能です。</span><span class="sxs-lookup"><span data-stu-id="77cb9-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="77cb9-148">詳細については、「 [Exchange Online のユーザー メールボックスを削除または復元する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="77cb9-149">Active Directory</span><span class="sxs-lookup"><span data-stu-id="77cb9-149">Active Directory</span></span>  <br/> |<span data-ttu-id="77cb9-150">お客様の一般法人で Azure AD と同期している **Active Directory** を使用する場合は、Active Directory からユーザー アカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77cb9-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="77cb9-151">Office 365 からこの操作を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-151">You can't do it through Office 365.</span></span> <span data-ttu-id="77cb9-152">手順については、「[ユーザー アカウントを削除する](https://go.microsoft.com/fwlink/p/?linkid=841808)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="77cb9-153">作業の開始</span><span class="sxs-lookup"><span data-stu-id="77cb9-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="77cb9-154">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="77cb9-155">ユーザーを削除する手順は、ガイドに従って実行できます。以下の方法でガイドを開始できます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="77cb9-156">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="77cb9-157">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="77cb9-158">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="77cb9-159">削除するユーザーを選択し、[**ユーザーの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="77cb9-160">ユーザー管理の管理者: Office 365 から 1 人または複数のユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="77cb9-160">User management admin: Delete one or more users from Office 365</span></span>


 <span data-ttu-id="77cb9-p113">**重要:**[アカウントを共有メールボックスに変換した場合や](../email/convert-user-mailbox-to-shared-mailbox.md) 、アカウントでメールの転送を設定した場合、ユーザーのアカウントを削除しないでください。これらの機能を有効にするには、アカウントを残す必要があります。共有メールボックスに変換した場合は、 [ライセンスの支払いを停止する](#stop-paying-for-the-license)できるため、支払を行うことはありません。メールの転送をセットアップしている場合は、ライセンスを削除することはできません。削除すると、メールの転送が停止され、メールボックスは無効にされます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-p113">**IMPORTANT**: Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account. Those functions need the account there. If you've converted it to a shared mailbox, you can [Stop paying for the license](#stop-paying-for-the-license) from it so you aren't paying for it. If you set up email forwarding, you cannot remove the license. Doing so will stop the email forwarding and inactivate the mailbox.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="77cb9-166">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="77cb9-167">削除するユーザーの名前を選択し、[**その他のオプション**] (**...**) を選択し、[**ユーザー の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-167">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="77cb9-168">これによりユーザーのアカウントは削除されますが、**ライセンスの支払いは継続します**。</span><span class="sxs-lookup"><span data-stu-id="77cb9-168">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="77cb9-169">ライセンスの支払いを停止するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-169">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="77cb9-170">または、ライセンスを別のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-170">Or, you can assign the license to another user.</span></span> <span data-ttu-id="77cb9-171">ライセンスが自動的に別のユーザーに割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-171">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="77cb9-172">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-172">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="77cb9-173">削除するユーザーの名前を選択し、[**一括操作**] ウィンドウで [**ユーザー の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-173">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="77cb9-174">これによりユーザーのアカウントは削除されますが、**ライセンスの支払いは継続します**。</span><span class="sxs-lookup"><span data-stu-id="77cb9-174">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="77cb9-175">ライセンスの支払いを停止するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-175">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="77cb9-176">または、ライセンスを別のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-176">Or, you can assign the license to another user.</span></span> <span data-ttu-id="77cb9-177">ライセンスが自動的に別のユーザーに割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-177">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="77cb9-178">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-178">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="77cb9-179">削除するユーザーの名前を選択し、[**一括操作**] ウィンドウで [**ユーザー の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-179">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="77cb9-180">これによりユーザーのアカウントは削除されますが、**ライセンスの支払いは継続します**。</span><span class="sxs-lookup"><span data-stu-id="77cb9-180">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="77cb9-181">ライセンスの支払いを停止するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-181">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="77cb9-182">または、ライセンスを別のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-182">Or, you can assign the license to another user.</span></span> <span data-ttu-id="77cb9-183">ライセンスが自動的に別のユーザーに割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-183">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="77cb9-184">ライセンスの支払いを停止する</span><span class="sxs-lookup"><span data-stu-id="77cb9-184">Stop paying for the license</span></span>

<span data-ttu-id="77cb9-185">ライセンス数を減らす作業は別の手順になり、グローバル管理者または請求管理者のみがこれを行えます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-185">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="77cb9-186">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-186">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span> <span data-ttu-id="77cb9-187">このオプションが表示されない場合は、グローバル管理者または請求管理者ではないことを意味します。この場合、この手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-187">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="77cb9-188">(サブスクリプションが複数ある場合は) サブスクリプションを選択し、[**ライセンスの追加/削除**] を選択してライセンスを削除します。こうすることで、新しい従業員を採用するまでライセンスの支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-188">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="77cb9-189">将来、新しいユーザーを組織のサブスクリプションに追加する手順を実行すると、ライセンスの購入を求めるメッセージが表示されるため、手間が省けます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-189">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="77cb9-190">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-190">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="77cb9-191">このオプションが表示されない場合は、グローバル管理者または請求管理者ではないことを意味します。この場合、この手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-191">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="77cb9-192">(サブスクリプションが複数ある場合は) サブスクリプションを選択し、[**ライセンスの追加/削除**] を選択してライセンスを削除します。こうすることで、新しい従業員を採用するまでライセンスの支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-192">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="77cb9-193">将来、新しいユーザーを組織のサブスクリプションに追加する手順を実行すると、ライセンスの購入を求めるメッセージが表示されるため、手間が省けます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-193">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="77cb9-194">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-194">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="77cb9-195">このオプションが表示されない場合は、グローバル管理者または請求管理者ではないことを意味します。この場合、この手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-195">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="77cb9-196">(サブスクリプションが複数ある場合は) サブスクリプションを選択し、[**ライセンスの追加/削除**] を選択してライセンスを削除します。こうすることで、新しい従業員を採用するまでライセンスの支払いを停止できます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-196">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="77cb9-197">将来、新しいユーザーを組織のサブスクリプションに追加する手順を実行すると、ライセンスの購入を求めるメッセージが表示されるため、手間が省けます。</span><span class="sxs-lookup"><span data-stu-id="77cb9-197">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="77cb9-198">多数のユーザーを同時に削除する</span><span class="sxs-lookup"><span data-stu-id="77cb9-198">Delete many users at the same time</span></span>

<span data-ttu-id="77cb9-199">[Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell コマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-199">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="77cb9-200">ユーザーの削除に関する問題を解決する</span><span class="sxs-lookup"><span data-stu-id="77cb9-200">Fix issues with deleting a user</span></span>

<span data-ttu-id="77cb9-201">ユーザーを削除するときに発生する最も一般的な問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-201">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="77cb9-202">**"ユーザーが削除できません。後でもう一度お試しください。" の行でエラーが発生しました。**</span><span class="sxs-lookup"><span data-stu-id="77cb9-202">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="77cb9-203">アカウントでメール転送が設定されているかどうか、共有メールボックスに変換されているかどうかをダブルチェックします。</span><span class="sxs-lookup"><span data-stu-id="77cb9-203">Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="77cb9-204">これらの両方でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-204">Both of these will cause that error.</span></span> <span data-ttu-id="77cb9-205">メール転送を設定している場合、または共有メールボックスに変換した場合は、アカウントを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-205">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="77cb9-206">**ユーザーを削除するための適切なアクセス許可がありません**。</span><span class="sxs-lookup"><span data-stu-id="77cb9-206">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="77cb9-207">ユーザーを削除できるのは、[Office 365 のグローバル管理者またはユーザー管理の管理者](about-admin-roles.md)のみです。</span><span class="sxs-lookup"><span data-stu-id="77cb9-207">Only people who are [Office 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="77cb9-208">通常は、学校または職場のテクニカル サポートです。</span><span class="sxs-lookup"><span data-stu-id="77cb9-208">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="77cb9-p122">**ユーザーを削除しても、その名前がグローバル アドレス帳に表示され続けます** 。これは、業務で Active Directory を使用している場合に発生します。Active Directory からユーザー アカウントを削除する必要があります。手順については、TechNet の記事の「 [ユーザー アカウントを削除する](https://go.microsoft.com/fwlink/p/?linkid=841808)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77cb9-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="77cb9-213">**自分のコンピューターから Office 365 を削除する場合は、[サブスクリプションのキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)に移動します。**</span><span class="sxs-lookup"><span data-stu-id="77cb9-213">**Do you want to delete Office 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="77cb9-214">関連記事</span><span class="sxs-lookup"><span data-stu-id="77cb9-214">Related articles</span></span>

[<span data-ttu-id="77cb9-215">ユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="77cb9-215">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="77cb9-216">メールボックスを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="77cb9-216">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="77cb9-217">Office 365 から元従業員を削除する</span><span class="sxs-lookup"><span data-stu-id="77cb9-217">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="77cb9-218">Office 365 に新しい従業員を追加する</span><span class="sxs-lookup"><span data-stu-id="77cb9-218">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="77cb9-219">[ユーザー アカウントを削除する](https://go.microsoft.com/fwlink/p/?linkid=841808):Azure AD と同期している **Active Directory** を組織で使用している場合は、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-219">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="77cb9-220">Office 365 からこの操作を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="77cb9-220">You can't do it through Office 365.</span></span>