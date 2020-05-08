---
title: ユーザーに別のメール エイリアスを追加する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Microsoft 365 for business アカウントに関連付けられている電子メールエイリアスと呼ばれる複数の電子メールアドレスを設定する方法について説明します。 '
ms.openlocfilehash: 603b2f42d603ae5172c66b6f78bc55f8d44c81f5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140514"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="d8e3a-103">ユーザーに別のメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="d8e3a-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d8e3a-104">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-104">The admin center is changing.</span></span> <span data-ttu-id="d8e3a-105">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="d8e3a-106">この記事は、ビジネスサブスクリプションを所有する Microsoft 365 管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="d8e3a-107">ホーム ユーザー向けではありません。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-107">It's not for home users.</span></span>
  
<span data-ttu-id="d8e3a-108">Microsoft 365 のプライマリ電子メールアドレスは、通常、アカウントの作成時にユーザーが割り当てられた電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="d8e3a-109">ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="d8e3a-110">また、Microsoft 365 for business アカウントに関連付けられている電子メールアドレスを複数持つこともできます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="d8e3a-111">これらの追加アドレスをエイリアスと呼びます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="d8e3a-112">たとえば、Jenna が電子メールアドレス jenna@contosoco.com を持っているとしますが、ユーザーがその名前で自分を参照している場合は、jen@contosoco.com で電子メールを受信したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="d8e3a-113">両方の電子メールアドレスが Jenna の受信トレイに送られるように、のエイリアスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="d8e3a-114">ユーザーあたり最大 400 個のエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="d8e3a-115">追加の料金やライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="d8e3a-116">Info@NodPublishers.com や sales@NodPublishers.com などの1つの電子メールアドレスに送信された電子メールを複数のユーザーが管理できるようにする場合は、共有メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="d8e3a-117">詳細については、「[共有メールボックスを作成](create-a-shared-mailbox.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="d8e3a-118">ユーザーにメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="d8e3a-118">Add email aliases to a user</span></span>
<span data-ttu-id="d8e3a-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="d8e3a-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="d8e3a-120">これを行うには、[管理者のアクセス許可](../add-users/about-admin-roles.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="d8e3a-121">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="d8e3a-122">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="d8e3a-123">[**アクティブなユーザー** ] ページで、[ユーザー >**メールエイリアスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-123">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="d8e3a-124">ユーザーにライセンスが割り当てられていない場合、このオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-124">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="d8e3a-125">[ **+ エイリアスの追加**] を選択し、ユーザーの新しい別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-125">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="d8e3a-126">"**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-126">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d8e3a-127">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-127">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d8e3a-128">しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-128">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d8e3a-129">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-129">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="d8e3a-130">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-130">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d8e3a-131">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-131">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d8e3a-132">一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-132">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="d8e3a-133">完了したら、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-133">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="d8e3a-134">Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-134">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="d8e3a-135">これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-135">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d8e3a-136">たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-136">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d8e3a-137">**ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。**</span><span class="sxs-lookup"><span data-stu-id="d8e3a-137">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d8e3a-138">たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-138">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d8e3a-139">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-139">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="d8e3a-140">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="d8e3a-141">[ **アクティブなユーザー**] ページで、編集するユーザー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-141">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="d8e3a-142">[**ユーザー名/メールエイリアス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-142">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="d8e3a-143">"**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-143">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d8e3a-144">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-144">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d8e3a-145">しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-145">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d8e3a-146">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-146">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="d8e3a-147">[**エイリアス**] の下のテキストボックスに、新しい電子メールエイリアスの最初の部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-147">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="d8e3a-148">独自のドメインを Office 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-148">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="d8e3a-149">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-149">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d8e3a-150">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-150">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d8e3a-151">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-151">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d8e3a-152">一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-152">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="d8e3a-153">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-153">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="d8e3a-154">Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-154">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="d8e3a-155">これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-155">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d8e3a-156">たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-156">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d8e3a-157">**ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。**</span><span class="sxs-lookup"><span data-stu-id="d8e3a-157">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d8e3a-158">たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-158">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d8e3a-159">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-159">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d8e3a-160">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="d8e3a-161">[ **アクティブなユーザー**] ページで、編集するユーザー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-161">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="d8e3a-162">[**ユーザー名/メールエイリアス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-162">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="d8e3a-163">"**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-163">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d8e3a-164">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-164">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d8e3a-165">しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-165">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d8e3a-166">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-166">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="d8e3a-167">[**エイリアス**] の下のテキストボックスに、新しい電子メールエイリアスの最初の部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-167">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="d8e3a-168">独自のドメインを Office 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-168">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="d8e3a-169">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-169">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d8e3a-170">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-170">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="d8e3a-171">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-171">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="d8e3a-172">一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-172">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="d8e3a-173">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-173">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="d8e3a-174">Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-174">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="d8e3a-175">これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-175">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="d8e3a-176">たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-176">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="d8e3a-177">**ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。**</span><span class="sxs-lookup"><span data-stu-id="d8e3a-177">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="d8e3a-178">たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-178">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="d8e3a-179">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-179">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="d8e3a-180">"パラメーター名 EmailAddresses に一致するパラメーターが見つかりません" が表示されましたか?</span><span class="sxs-lookup"><span data-stu-id="d8e3a-180">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="d8e3a-181">"**パラメーター名が電子メールアドレスに一致するパラメーターが見つかりません**" というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかっていること、または、ユーザーが最近追加された場合はカスタムドメインを使用していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-181">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="d8e3a-182">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-182">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="d8e3a-183">しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-183">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="d8e3a-184">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-184">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="d8e3a-185">GoDaddy または別のパートナーからサブスクリプションを購入した場合</span><span class="sxs-lookup"><span data-stu-id="d8e3a-185">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="d8e3a-186">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e3a-186">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d8e3a-187">関連記事</span><span class="sxs-lookup"><span data-stu-id="d8e3a-187">Related articles</span></span>

[<span data-ttu-id="d8e3a-188">別のアドレスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="d8e3a-188">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="d8e3a-189">ユーザー名とメール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="d8e3a-189">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

