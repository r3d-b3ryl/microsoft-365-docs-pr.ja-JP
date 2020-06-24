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
ms.openlocfilehash: f83b2069bd1b4c86e2198252a54ed2e8e5c55a04
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844682"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a><span data-ttu-id="ade19-103">Microsoft 365 for business のサブスクリプションとライセンスについて</span><span class="sxs-lookup"><span data-stu-id="ade19-103">Understand subscriptions and licenses in Microsoft 365 for business</span></span>

<span data-ttu-id="ade19-104">この記事では、サブスクリプションとライセンスの間の関係を説明し、[ライセンスを割り当てることができるユーザー](#find-out-who-can-assign-licenses)、[ライセンスを割り当てたときに発生すること](#understand-what-happens-when-you-assign-a-license-to-someone)、および[ユーザーが Office をインストールできるデバイスの数](#how-many-devices-can-people-install-office-on)についての追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ade19-104">This article explains the relationship between subscriptions and licenses, and provides additional information about [who can assign licenses](#find-out-who-can-assign-licenses), [understanding what happens when you assign a license to someone](#understand-what-happens-when-you-assign-a-license-to-someone), and [how many devices can people install Office on](#how-many-devices-can-people-install-office-on).</span></span> <span data-ttu-id="ade19-105">また、[ユーザー以外のメールボックスのライセンスについて](#understand-licenses-for-non-user-mailboxes)へのリンクや、[ライセンス管理に関する記事](#articles-about-managing-licenses)へのリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ade19-105">It also includes links to [understanding licenses for non-user mailboxes](#understand-licenses-for-non-user-mailboxes), and [Articles about managing licenses](#articles-about-managing-licenses).</span></span>
  
<span data-ttu-id="ade19-106">Microsoft 365 for business のサブスクリプションを購入する際には、月単位または年単位で支払いを行う一連のアプリケーションとサービスにサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ade19-106">When you buy a subscription to Microsoft 365 for business, you sign up for a set of applications and services that you pay for on a either a monthly or an annual basis.</span></span> <span data-ttu-id="ade19-107">サブスクリプションの一部として受信するアプリケーションとサービスは、Microsoft 365 for business または Microsoft 365 Business Standard など、購入した製品によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ade19-107">The applications and services that you receive as part of your subscription depend on which product you purchased, such as Microsoft 365 Apps for business or Microsoft 365 Business Standard.</span></span> <span data-ttu-id="ade19-108">各製品の内容を確認するには、「 [Microsoft 365 を購入](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)する」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ade19-108">You can review what comes with each product on the [Buy Microsoft 365 page](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).</span></span> 

<span data-ttu-id="ade19-109">[小規模および中規模企業向けに Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)で利用可能なさまざまなライセンスオプションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ade19-109">You can review different Licensing options available in [Microsoft 365 for small and medium-sized businesses](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)</span></span>

<span data-ttu-id="ade19-110">サブスクリプションを購入する場合、組織の人数に基づいて、必要なライセンス数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ade19-110">When you buy a subscription, you specify the number of licenses that you need, based on how many people you have in your organization.</span></span> <span data-ttu-id="ade19-111">購入の完了後、ユーザーのアカウントを作成し、各ユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ade19-111">After your purchase is complete, you create accounts for people, and then assign a license to each person.</span></span> <span data-ttu-id="ade19-112">組織のニーズの変化に応じて、新しいユーザーに対応するためにライセンスを追加購入したり、組織を離れるユーザーのライセンスを他のユーザーに再割り当てしたりできます。</span><span class="sxs-lookup"><span data-stu-id="ade19-112">As your organizational needs change, you can buy more licenses to accommodate new people, or reassign licenses to other users when someone leaves your organization.</span></span> 

<span data-ttu-id="ade19-113">複数のサブスクリプションがある場合、各サブスクリプションを使って異なるユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ade19-113">If you have more than one subscription, you can assign licenses to different people for each subscription.</span></span> <span data-ttu-id="ade19-114">たとえば、すべてのユーザーを microsoft 365 Business Standard サブスクリプションの一部としてすべての Microsoft 365 アプリケーションおよびサービスに割り当てることができますが、ユーザーのサブセットは、個別の Visio サブスクリプションを使用して Visio Online に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="ade19-114">For example, all of your users could be assigned to all Microsoft 365 applications and services as part of an Microsoft 365 Business Standard subscription, while a subset of users could also be assigned to Visio Online through a separate Visio subscription.</span></span> 

  
## <a name="find-out-who-can-assign-licenses"></a><span data-ttu-id="ade19-115">ライセンスを割り当てることができるユーザーを見つける</span><span class="sxs-lookup"><span data-stu-id="ade19-115">Find out who can assign licenses</span></span>

<span data-ttu-id="ade19-116">Different types of admins can work with licenses in different ways, depending on their roles.</span><span class="sxs-lookup"><span data-stu-id="ade19-116">Different types of admins can work with licenses in different ways, depending on their roles.</span></span> <span data-ttu-id="ade19-117">The following table lists the most common options.</span><span class="sxs-lookup"><span data-stu-id="ade19-117">The following table lists the most common options.</span></span> <span data-ttu-id="ade19-118">For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ade19-118">For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  
|<span data-ttu-id="ade19-119">**管理者ロール**</span><span class="sxs-lookup"><span data-stu-id="ade19-119">**Admin role**</span></span>|<span data-ttu-id="ade19-120">**ライセンスを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="ade19-120">**Assign a license**</span></span>|<span data-ttu-id="ade19-121">**ライセンスの削除**</span><span class="sxs-lookup"><span data-stu-id="ade19-121">**Remove a license**</span></span>|<span data-ttu-id="ade19-122">**追加ライセンスの購入**</span><span class="sxs-lookup"><span data-stu-id="ade19-122">**Purchase more licenses**</span></span>|<span data-ttu-id="ade19-123">**アカウントの削除**</span><span class="sxs-lookup"><span data-stu-id="ade19-123">**Delete an account**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ade19-124">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="ade19-124">Global admin</span></span>  <br/> |<span data-ttu-id="ade19-125">はい</span><span class="sxs-lookup"><span data-stu-id="ade19-125">Yes</span></span>  <br/> |<span data-ttu-id="ade19-126">はい</span><span class="sxs-lookup"><span data-stu-id="ade19-126">Yes</span></span>  <br/> |<span data-ttu-id="ade19-127">はい</span><span class="sxs-lookup"><span data-stu-id="ade19-127">Yes</span></span>  <br/> |<span data-ttu-id="ade19-128">はい</span><span class="sxs-lookup"><span data-stu-id="ade19-128">Yes</span></span>  <br/> |
|<span data-ttu-id="ade19-129">課金管理者</span><span class="sxs-lookup"><span data-stu-id="ade19-129">Billing admin</span></span>  <br/> |<span data-ttu-id="ade19-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-130">No</span></span>  <br/> |<span data-ttu-id="ade19-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-131">No</span></span>  <br/> |<span data-ttu-id="ade19-132">はい</span><span class="sxs-lookup"><span data-stu-id="ade19-132">Yes</span></span>  <br/> |<span data-ttu-id="ade19-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-133">No</span></span>  <br/> |
|<span data-ttu-id="ade19-134">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="ade19-134">User management admin</span></span>  <br/> |<span data-ttu-id="ade19-135">はい</span><span class="sxs-lookup"><span data-stu-id="ade19-135">Yes</span></span>  <br/> |<span data-ttu-id="ade19-136">はい</span><span class="sxs-lookup"><span data-stu-id="ade19-136">Yes</span></span>  <br/> |<span data-ttu-id="ade19-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-137">No</span></span>  <br/> |<span data-ttu-id="ade19-138">○</span><span class="sxs-lookup"><span data-stu-id="ade19-138">Yes</span></span>  <br/> |
|<span data-ttu-id="ade19-139">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="ade19-139">Service admin</span></span>  <br/> |<span data-ttu-id="ade19-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-140">No</span></span>  <br/> |<span data-ttu-id="ade19-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-141">No</span></span>  <br/> |<span data-ttu-id="ade19-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-142">No</span></span>  <br/> |<span data-ttu-id="ade19-143">×</span><span class="sxs-lookup"><span data-stu-id="ade19-143">No</span></span>  <br/> |
|<span data-ttu-id="ade19-144">パスワード管理者</span><span class="sxs-lookup"><span data-stu-id="ade19-144">Password admin</span></span>  <br/> |<span data-ttu-id="ade19-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-145">No</span></span>  <br/> |<span data-ttu-id="ade19-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-146">No</span></span>  <br/> |<span data-ttu-id="ade19-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-147">No</span></span>  <br/> |<span data-ttu-id="ade19-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="ade19-148">No</span></span>  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a><span data-ttu-id="ade19-149">ユーザーにライセンスを割り当てたときに行われることを理解する</span><span class="sxs-lookup"><span data-stu-id="ade19-149">Understand what happens when you assign a license to someone</span></span>

<span data-ttu-id="ade19-150">以下の表は、ライセンスをユーザーに割り当てたときに自動的に発生することを示しています。</span><span class="sxs-lookup"><span data-stu-id="ade19-150">The following table lists what automatically happens when you assign a license to someone:</span></span>
  
|<span data-ttu-id="ade19-151">**サブスクリプションにこのサービスがある場合**</span><span class="sxs-lookup"><span data-stu-id="ade19-151">**If the subscription has this service**</span></span>|<span data-ttu-id="ade19-152">**自動的に行われます**</span><span class="sxs-lookup"><span data-stu-id="ade19-152">**This automatically happens**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ade19-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ade19-153">Exchange Online</span></span>  <br/> |<span data-ttu-id="ade19-154">そのユーザーのメールボックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ade19-154">A mailbox is created for that person.</span></span>  <br/> <span data-ttu-id="ade19-155">このタスクを完了するための SLA については、 [「セットアップ...」を参照してください。Microsoft 365 管理センターのメッセージ](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="ade19-155">To learn about the SLA for this task to be completed, see ["Setting up..." messages in the Microsoft 365 admin center](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center).</span></span> |
|<span data-ttu-id="ade19-156">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ade19-156">SharePoint Online</span></span>  <br/> |<span data-ttu-id="ade19-157">既定の SharePoint Online チーム サイトの編集権限がそのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ade19-157">Edit permissions to the default SharePoint Online team site are assigned to that person.</span></span>  <br/> |
|<span data-ttu-id="ade19-158">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ade19-158">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="ade19-159">ライセンスに関連付けられた機能へのアクセス権がユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ade19-159">The person will have access to the features associated with the license.</span></span>  <br/> |
|<span data-ttu-id="ade19-160">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="ade19-160">Microsoft 365 Apps for enterprise</span></span>  <br/> |<span data-ttu-id="ade19-161">ユーザーは、最大 5 台の Mac または PC、5 台のタブレット、および 5 台のスマートフォンに Microsoft Office をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ade19-161">The person will be able to download Microsoft Office on up to 5 Macs or PCs, 5 tablets, and 5 smartphones.</span></span>  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a><span data-ttu-id="ade19-162">ユーザーが Office をインストールできるデバイスは何台ですか?</span><span class="sxs-lookup"><span data-stu-id="ade19-162">How many devices can people install Office on?</span></span>

<span data-ttu-id="ade19-163">サブスクリプションに以下の製品のいずれかが含まれている場合、各ユーザーは、最大 5 台の PC または Mac、5 台のタブレット、および 5 台のスマートフォンに Office をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ade19-163">If your subscription includes any of the following products, each person can install Office on up to 5 PCs or Mac, 5 tablets, and 5 phones.</span></span>
  
- <span data-ttu-id="ade19-164">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="ade19-164">Microsoft 365 Apps for business</span></span>
    
- <span data-ttu-id="ade19-165">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="ade19-165">Microsoft 365 Business Standard</span></span>
    
- <span data-ttu-id="ade19-166">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="ade19-166">Microsoft 365 Apps for enterprise</span></span>
    
- <span data-ttu-id="ade19-167">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="ade19-167">Office 365 Enterprise E3</span></span>
    
- <span data-ttu-id="ade19-168">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="ade19-168">Office 365 Enterprise E5</span></span>
    
## <a name="understand-licenses-for-non-user-mailboxes"></a><span data-ttu-id="ade19-169">ユーザー以外のメールボックスのライセンスについて</span><span class="sxs-lookup"><span data-stu-id="ade19-169">Understand licenses for non-user mailboxes</span></span>

<span data-ttu-id="ade19-170">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="ade19-170">You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB).</span></span> <span data-ttu-id="ade19-171">For more about non-user mailboxes, see the following articles:</span><span class="sxs-lookup"><span data-stu-id="ade19-171">For more about non-user mailboxes, see the following articles:</span></span>
  
- [<span data-ttu-id="ade19-172">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="ade19-172">Create a shared mailbox</span></span>](../../admin/email/create-a-shared-mailbox.md)
    
- <span data-ttu-id="ade19-173">他のすべての Microsoft 365 プランの[Exchange Online の共有メールボックス](https://go.microsoft.com/fwlink/p/?linkid=847433)。</span><span class="sxs-lookup"><span data-stu-id="ade19-173">[Shared Mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) for all other Microsoft 365 plans.</span></span> 
    
- [<span data-ttu-id="ade19-174">会議室メールボックスの作成と管理</span><span class="sxs-lookup"><span data-stu-id="ade19-174">Create and Manage Room Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [<span data-ttu-id="ade19-175">備品用メールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="ade19-175">Manage Equipment Mailboxes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a><span data-ttu-id="ade19-176">ライセンスの管理に関する記事</span><span class="sxs-lookup"><span data-stu-id="ade19-176">Articles about managing licenses</span></span>

- [<span data-ttu-id="ade19-177">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ade19-177">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)
    
- [<span data-ttu-id="ade19-178">ユーザーからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="ade19-178">Remove licenses from users</span></span>](../../admin/manage/remove-licenses-from-users.md)
    
- [<span data-ttu-id="ade19-179">サブスクリプションのライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="ade19-179">Buy licenses for your subscription</span></span>](buy-licenses.md)
    
- [<span data-ttu-id="ade19-180">別のサブスクリプションを購入する</span><span class="sxs-lookup"><span data-stu-id="ade19-180">Buy another subscription</span></span>](../buy-another-subscription.md)
    
- [<span data-ttu-id="ade19-181">アドオンを購入または編集する</span><span class="sxs-lookup"><span data-stu-id="ade19-181">Buy or edit an add-on</span></span>](../buy-or-edit-an-add-on.md)
    
- [<span data-ttu-id="ade19-182">サブスクリプションからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="ade19-182">Remove licenses from your subscription</span></span>](remove-licenses-from-subscription.md)
    
- [<span data-ttu-id="ade19-183">ライセンスの競合を解決する</span><span class="sxs-lookup"><span data-stu-id="ade19-183">Resolve license conflicts</span></span>](../../admin/manage/resolve-license-conflicts.md)
    
- [<span data-ttu-id="ade19-184">Yammer ユーザー ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="ade19-184">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
