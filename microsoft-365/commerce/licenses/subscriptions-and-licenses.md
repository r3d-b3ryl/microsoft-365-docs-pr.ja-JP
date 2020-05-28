---
title: Microsoft 365 for business のサブスクリプションとライセンスについて
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: 'Microsoft 365 for business のサブスクリプションとライセンスについて説明し、ライセンスを割り当てることができるユーザーと、ユーザーにライセンスを割り当てるときの動作を確認します。 '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: 5ed1925fd51dd1798d4c6ab275494fde01535177
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402404"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a><span data-ttu-id="cb6c5-103">Microsoft 365 for business のサブスクリプションとライセンスについて</span><span class="sxs-lookup"><span data-stu-id="cb6c5-103">Understand subscriptions and licenses in Microsoft 365 for business</span></span>

<span data-ttu-id="cb6c5-104">この記事では、サブスクリプションとライセンスの間の関係を説明し、[ライセンスを割り当てることができるユーザー](#find-out-who-can-assign-licenses)、[ライセンスを割り当てたときに発生すること](#understand-what-happens-when-you-assign-a-license-to-someone)、および[ユーザーが Office をインストールできるデバイスの数](#how-many-devices-can-people-install-office-on)についての追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-104">This article explains the relationship between subscriptions and licenses, and provides additional information about [who can assign licenses](#find-out-who-can-assign-licenses), [understanding what happens when you assign a license to someone](#understand-what-happens-when-you-assign-a-license-to-someone), and [how many devices can people install Office on](#how-many-devices-can-people-install-office-on).</span></span> <span data-ttu-id="cb6c5-105">また、[ユーザー以外のメールボックスのライセンスについて](#understand-licenses-for-non-user-mailboxes)へのリンクや、[ライセンス管理に関する記事](#articles-about-managing-licenses)へのリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-105">It also includes links to [understanding licenses for non-user mailboxes](#understand-licenses-for-non-user-mailboxes), and [Articles about managing licenses](#articles-about-managing-licenses).</span></span>
  
<span data-ttu-id="cb6c5-106">Microsoft 365 for business のサブスクリプションを購入する際には、月単位または年単位で支払いを行う一連のアプリケーションとサービスにサインアップします。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-106">When you buy a subscription to Microsoft 365 for business, you sign up for a set of applications and services that you pay for on a either a monthly or an annual basis.</span></span> <span data-ttu-id="cb6c5-107">サブスクリプションの一部として受信するアプリケーションとサービスは、Microsoft 365 for business または Microsoft 365 Business Standard など、購入した製品によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-107">The applications and services that you receive as part of your subscription depend on which product you purchased, such as Microsoft 365 Apps for business or Microsoft 365 Business Standard.</span></span> <span data-ttu-id="cb6c5-108">各製品の内容を確認するには、「 [Microsoft 365 を購入](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)する」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-108">You can review what comes with each product on the [Buy Microsoft 365 page](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span></span> 

<span data-ttu-id="cb6c5-109">サブスクリプションを購入する場合、組織の人数に基づいて、必要なライセンス数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-109">When you buy a subscription, you specify the number of licenses that you need, based on how many people you have in your organization.</span></span> <span data-ttu-id="cb6c5-110">購入の完了後、ユーザーのアカウントを作成し、各ユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-110">After your purchase is complete, you create accounts for people, and then assign a license to each person.</span></span> <span data-ttu-id="cb6c5-111">組織のニーズの変化に応じて、新しいユーザーに対応するためにライセンスを追加購入したり、組織を離れるユーザーのライセンスを他のユーザーに再割り当てしたりできます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-111">As your organizational needs change, you can buy more licenses to accommodate new people, or reassign licenses to other users when someone leaves your organization.</span></span> 

<span data-ttu-id="cb6c5-112">複数のサブスクリプションがある場合、各サブスクリプションを使って異なるユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-112">If you have more than one subscription, you can assign licenses to different people for each subscription.</span></span> <span data-ttu-id="cb6c5-113">たとえば、すべてのユーザーを microsoft 365 Business Standard サブスクリプションの一部としてすべての Microsoft 365 アプリケーションおよびサービスに割り当てることができますが、ユーザーのサブセットは、個別の Visio サブスクリプションを使用して Visio Online に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-113">For example, all of your users could be assigned to all Microsoft 365 applications and services as part of an Microsoft 365 Business Standard subscription, while a subset of users could also be assigned to Visio Online through a separate Visio subscription.</span></span> 

  
## <a name="find-out-who-can-assign-licenses"></a><span data-ttu-id="cb6c5-114">ライセンスを割り当てることができるユーザーを見つける</span><span class="sxs-lookup"><span data-stu-id="cb6c5-114">Find out who can assign licenses</span></span>

<span data-ttu-id="cb6c5-p105">個々の管理者が実行できるライセンスに関する作業は、その役割によって異なります。以下の表は、最も一般的なオプションをまとめたものです。管理者の役割と権限の詳細については、「[Office 365 の管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-p105">Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  
|<span data-ttu-id="cb6c5-118">**管理者ロール**</span><span class="sxs-lookup"><span data-stu-id="cb6c5-118">**Admin role**</span></span>|<span data-ttu-id="cb6c5-119">**ライセンスを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="cb6c5-119">**Assign a license**</span></span>|<span data-ttu-id="cb6c5-120">**ライセンスの削除**</span><span class="sxs-lookup"><span data-stu-id="cb6c5-120">**Remove a license**</span></span>|<span data-ttu-id="cb6c5-121">**追加ライセンスの購入**</span><span class="sxs-lookup"><span data-stu-id="cb6c5-121">**Purchase more licenses**</span></span>|<span data-ttu-id="cb6c5-122">**アカウントの削除**</span><span class="sxs-lookup"><span data-stu-id="cb6c5-122">**Delete an account**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb6c5-123">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="cb6c5-123">Global admin</span></span>  <br/> |<span data-ttu-id="cb6c5-124">はい</span><span class="sxs-lookup"><span data-stu-id="cb6c5-124">Yes</span></span>  <br/> |<span data-ttu-id="cb6c5-125">はい</span><span class="sxs-lookup"><span data-stu-id="cb6c5-125">Yes</span></span>  <br/> |<span data-ttu-id="cb6c5-126">はい</span><span class="sxs-lookup"><span data-stu-id="cb6c5-126">Yes</span></span>  <br/> |<span data-ttu-id="cb6c5-127">はい</span><span class="sxs-lookup"><span data-stu-id="cb6c5-127">Yes</span></span>  <br/> |
|<span data-ttu-id="cb6c5-128">課金管理者</span><span class="sxs-lookup"><span data-stu-id="cb6c5-128">Billing admin</span></span>  <br/> |<span data-ttu-id="cb6c5-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-129">No</span></span>  <br/> |<span data-ttu-id="cb6c5-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-130">No</span></span>  <br/> |<span data-ttu-id="cb6c5-131">はい</span><span class="sxs-lookup"><span data-stu-id="cb6c5-131">Yes</span></span>  <br/> |<span data-ttu-id="cb6c5-132">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-132">No</span></span>  <br/> |
|<span data-ttu-id="cb6c5-133">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="cb6c5-133">User management admin</span></span>  <br/> |<span data-ttu-id="cb6c5-134">はい</span><span class="sxs-lookup"><span data-stu-id="cb6c5-134">Yes</span></span>  <br/> |<span data-ttu-id="cb6c5-135">はい</span><span class="sxs-lookup"><span data-stu-id="cb6c5-135">Yes</span></span>  <br/> |<span data-ttu-id="cb6c5-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-136">No</span></span>  <br/> |<span data-ttu-id="cb6c5-137">はい</span><span class="sxs-lookup"><span data-stu-id="cb6c5-137">Yes</span></span>  <br/> |
|<span data-ttu-id="cb6c5-138">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="cb6c5-138">Service admin</span></span>  <br/> |<span data-ttu-id="cb6c5-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-139">No</span></span>  <br/> |<span data-ttu-id="cb6c5-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-140">No</span></span>  <br/> |<span data-ttu-id="cb6c5-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-141">No</span></span>  <br/> |<span data-ttu-id="cb6c5-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-142">No</span></span>  <br/> |
|<span data-ttu-id="cb6c5-143">パスワード管理者</span><span class="sxs-lookup"><span data-stu-id="cb6c5-143">Password admin</span></span>  <br/> |<span data-ttu-id="cb6c5-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-144">No</span></span>  <br/> |<span data-ttu-id="cb6c5-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-145">No</span></span>  <br/> |<span data-ttu-id="cb6c5-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-146">No</span></span>  <br/> |<span data-ttu-id="cb6c5-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="cb6c5-147">No</span></span>  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a><span data-ttu-id="cb6c5-148">ユーザーにライセンスを割り当てたときに行われることを理解する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-148">Understand what happens when you assign a license to someone</span></span>

<span data-ttu-id="cb6c5-149">以下の表は、ライセンスをユーザーに割り当てたときに自動的に発生することを示しています。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-149">The following table lists what automatically happens when you assign a license to someone:</span></span>
  
|<span data-ttu-id="cb6c5-150">**サブスクリプションにこのサービスがある場合**</span><span class="sxs-lookup"><span data-stu-id="cb6c5-150">**If the subscription has this service**</span></span>|<span data-ttu-id="cb6c5-151">**自動的に行われます**</span><span class="sxs-lookup"><span data-stu-id="cb6c5-151">**This automatically happens**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cb6c5-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cb6c5-152">Exchange Online</span></span>  <br/> |<span data-ttu-id="cb6c5-153">そのユーザーのメールボックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-153">A mailbox is created for that person.</span></span>  <br/> <span data-ttu-id="cb6c5-154">このタスクを完了するための SLA については、 [「セットアップ...」を参照してください。Microsoft 365 管理センターのメッセージ](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-154">To learn about the SLA for this task to be completed, see ["Setting up..." messages in the Microsoft 365 admin center](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center).</span></span> |
|<span data-ttu-id="cb6c5-155">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb6c5-155">SharePoint Online</span></span>  <br/> |<span data-ttu-id="cb6c5-156">既定の SharePoint Online チーム サイトの編集権限がそのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-156">Edit permissions to the default SharePoint Online team site are assigned to that person.</span></span>  <br/> |
|<span data-ttu-id="cb6c5-157">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cb6c5-157">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="cb6c5-158">ライセンスに関連付けられた機能へのアクセス権がユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-158">The person will have access to the features associated with the license.</span></span>  <br/> |
|<span data-ttu-id="cb6c5-159">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="cb6c5-159">Microsoft 365 Apps for enterprise</span></span>  <br/> |<span data-ttu-id="cb6c5-160">ユーザーは、最大 5 台の Mac または PC、5 台のタブレット、および 5 台のスマートフォンに Microsoft Office をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-160">The person will be able to download Microsoft Office on up to 5 Macs or PCs, 5 tablets, and 5 smartphones.</span></span>  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a><span data-ttu-id="cb6c5-161">ユーザーが Office をインストールできるデバイスは何台ですか?</span><span class="sxs-lookup"><span data-stu-id="cb6c5-161">How many devices can people install Office on?</span></span>

<span data-ttu-id="cb6c5-162">サブスクリプションに以下の製品のいずれかが含まれている場合、各ユーザーは、最大 5 台の PC または Mac、5 台のタブレット、および 5 台のスマートフォンに Office をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-162">If your subscription includes any of the following products, each person can install Office on up to 5 PCs or Mac, 5 tablets, and 5 phones.</span></span>
  
- <span data-ttu-id="cb6c5-163">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="cb6c5-163">Microsoft 365 Apps for business</span></span>
    
- <span data-ttu-id="cb6c5-164">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="cb6c5-164">Microsoft 365 Business Standard</span></span>
    
- <span data-ttu-id="cb6c5-165">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="cb6c5-165">Microsoft 365 Apps for enterprise</span></span>
    
- <span data-ttu-id="cb6c5-166">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="cb6c5-166">Office 365 Enterprise E3</span></span>
    
- <span data-ttu-id="cb6c5-167">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="cb6c5-167">Office 365 Enterprise E5</span></span>
    
## <a name="understand-licenses-for-non-user-mailboxes"></a><span data-ttu-id="cb6c5-168">ユーザー以外のメールボックスのライセンスについて</span><span class="sxs-lookup"><span data-stu-id="cb6c5-168">Understand licenses for non-user mailboxes</span></span>

<span data-ttu-id="cb6c5-p106">リソース メールボックス、会議室メールボックス、共有メールボックスにライセンスを割り当てる必要はありません。ただし、記憶域のクォータが 50 ギガバイト (GB) を超えた場合は、ライセンスの割り当てが必要になります。ユーザー以外のメールボックスの詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-p106">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:</span></span>
  
- [<span data-ttu-id="cb6c5-171">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-171">Create a shared mailbox</span></span>](../../admin/email/create-a-shared-mailbox.md)
    
- <span data-ttu-id="cb6c5-172">他のすべての Microsoft 365 プランの[Exchange Online の共有メールボックス](https://go.microsoft.com/fwlink/p/?linkid=847433)。</span><span class="sxs-lookup"><span data-stu-id="cb6c5-172">[Shared Mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) for all other Microsoft 365 plans.</span></span> 
    
- [<span data-ttu-id="cb6c5-173">会議室メールボックスの作成と管理</span><span class="sxs-lookup"><span data-stu-id="cb6c5-173">Create and Manage Room Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [<span data-ttu-id="cb6c5-174">備品用メールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="cb6c5-174">Manage Equipment Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a><span data-ttu-id="cb6c5-175">ライセンスの管理に関する記事</span><span class="sxs-lookup"><span data-stu-id="cb6c5-175">Articles about managing licenses</span></span>

- [<span data-ttu-id="cb6c5-176">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cb6c5-176">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)
    
- [<span data-ttu-id="cb6c5-177">ユーザーからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-177">Remove licenses from users</span></span>](../../admin/manage/remove-licenses-from-users.md)
    
- [<span data-ttu-id="cb6c5-178">サブスクリプションのライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-178">Buy licenses for your subscription</span></span>](buy-licenses.md)
    
- [<span data-ttu-id="cb6c5-179">別のサブスクリプションを購入する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-179">Buy another subscription</span></span>](../buy-another-subscription.md)
    
- [<span data-ttu-id="cb6c5-180">アドオンを購入または編集する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-180">Buy or edit an add-on</span></span>](../buy-or-edit-an-add-on.md)
    
- [<span data-ttu-id="cb6c5-181">サブスクリプションからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-181">Remove licenses from your subscription</span></span>](remove-licenses-from-subscription.md)
    
- [<span data-ttu-id="cb6c5-182">ライセンスの競合を解決する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-182">Resolve license conflicts</span></span>](../../admin/manage/resolve-license-conflicts.md)
    
- [<span data-ttu-id="cb6c5-183">Yammer ユーザー ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="cb6c5-183">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
