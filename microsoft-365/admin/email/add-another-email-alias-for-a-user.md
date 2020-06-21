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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Microsoft 365 for business アカウントに関連付けられている電子メールエイリアスと呼ばれる複数の電子メールアドレスを設定する方法について説明します。 '
ms.openlocfilehash: c0e71ef150ccf592ea4f808a5e6609e1675767a4
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780291"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="cdd98-103">ユーザーに別のメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="cdd98-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cdd98-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="cdd98-104">The admin center is changing.</span></span> <span data-ttu-id="cdd98-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="cdd98-106">この記事は、ビジネスサブスクリプションを所有する Microsoft 365 管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="cdd98-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="cdd98-107">ホーム ユーザー向けではありません。</span><span class="sxs-lookup"><span data-stu-id="cdd98-107">It's not for home users.</span></span>
  
<span data-ttu-id="cdd98-108">Microsoft 365 のプライマリ電子メールアドレスは、通常、アカウントの作成時にユーザーが割り当てられた電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="cdd98-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="cdd98-109">ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="cdd98-110">また、Microsoft 365 for business アカウントに関連付けられている電子メールアドレスを複数持つこともできます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="cdd98-111">これらの追加アドレスをエイリアスと呼びます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="cdd98-112">たとえば、Jenna が電子メールアドレス jenna@contosoco.com を持っているとしますが、ユーザーがその名前で自分を参照している場合は、jen@contosoco.com で電子メールを受信したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="cdd98-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="cdd98-113">両方の電子メールアドレスが Jenna の受信トレイに送られるように、のエイリアスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="cdd98-114">ユーザーあたり最大 400 個のエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="cdd98-115">追加の料金やライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cdd98-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="cdd98-116">Info@NodPublishers.com や sales@NodPublishers.com などの1つの電子メールアドレスに送信された電子メールを複数のユーザーが管理できるようにする場合は、共有メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="cdd98-117">詳細については、「[共有メールボックスを作成](create-a-shared-mailbox.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="cdd98-118">ユーザーにメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="cdd98-118">Add email aliases to a user</span></span>
<span data-ttu-id="cdd98-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="cdd98-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="cdd98-120">これを行うには、[管理者のアクセス許可](../add-users/about-admin-roles.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="cdd98-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="cdd98-121">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="cdd98-122">[**アクティブなユーザー** ] ページで、[ユーザー >**メールエイリアスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="cdd98-123">ユーザーにライセンスが割り当てられていない場合、このオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cdd98-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="cdd98-124">[ **+ エイリアスの追加**] を選択し、ユーザーの新しい別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="cdd98-125">"**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="cdd98-126">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="cdd98-127">しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="cdd98-128">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="cdd98-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="cdd98-129">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="cdd98-130">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="cdd98-131">一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-131">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="cdd98-132">完了したら、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="cdd98-133">Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-133">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="cdd98-134">これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="cdd98-135">たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="cdd98-136">**ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。**</span><span class="sxs-lookup"><span data-stu-id="cdd98-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="cdd98-137">たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。</span><span class="sxs-lookup"><span data-stu-id="cdd98-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="cdd98-138">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="cdd98-139">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="cdd98-140">[ **アクティブなユーザー**] ページで、編集するユーザー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="cdd98-141">[**ユーザー名/メールエイリアス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="cdd98-142">"**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="cdd98-143">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="cdd98-144">しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="cdd98-145">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="cdd98-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="cdd98-146">[**エイリアス**] の下のテキストボックスに、新しい電子メールエイリアスの最初の部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="cdd98-147">独自のドメインを Office 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-147">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="cdd98-148">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cdd98-149">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="cdd98-150">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="cdd98-151">一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-151">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="cdd98-152">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="cdd98-153">Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-153">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="cdd98-154">これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="cdd98-155">たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="cdd98-156">**ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。**</span><span class="sxs-lookup"><span data-stu-id="cdd98-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="cdd98-157">たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。</span><span class="sxs-lookup"><span data-stu-id="cdd98-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="cdd98-158">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cdd98-159">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="cdd98-160">[ **アクティブなユーザー**] ページで、編集するユーザー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="cdd98-161">[**ユーザー名/メールエイリアス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="cdd98-162">"**パラメーター名 ' EmailAddresses" と一致するパラメーターが見つからない**というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかることを意味します。または、ユーザーが最近追加した場合はカスタムドメインになります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="cdd98-163">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="cdd98-164">しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="cdd98-165">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="cdd98-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="cdd98-166">[**エイリアス**] の下のテキストボックスに、新しい電子メールエイリアスの最初の部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="cdd98-167">独自のドメインを Office 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-167">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="cdd98-168">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cdd98-169">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="cdd98-170">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="cdd98-171">一覧に別のドメイン名を追加するには、「 [Office 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-171">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="cdd98-172">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="cdd98-173">Office 365 全体に新しいエイリアスが設定されるまで 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-173">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="cdd98-174">これで、ユーザーにはプライマリアドレスとエイリアスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="cdd98-175">たとえば、Eliza Hoffman のプライマリアドレス、Eliza@NodPublishers.com、およびエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="cdd98-176">**ユーザーが返信すると、*差出人*アドレスはプライマリ電子メールエイリアスになります。**</span><span class="sxs-lookup"><span data-stu-id="cdd98-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="cdd98-177">たとえば、メッセージが Sales@NodPublishers.com に送信され、Eliza の受信トレイに到着したとします。</span><span class="sxs-lookup"><span data-stu-id="cdd98-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="cdd98-178">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdd98-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="cdd98-179">"パラメーター名 EmailAddresses に一致するパラメーターが見つかりません" が表示されましたか?</span><span class="sxs-lookup"><span data-stu-id="cdd98-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="cdd98-180">"**パラメーター名が電子メールアドレスに一致するパラメーターが見つかりません**" というエラーメッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかっていること、または、ユーザーが最近追加された場合はカスタムドメインを使用していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="cdd98-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="cdd98-181">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="cdd98-182">しばらく待ってからセットアップ処理を完了してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="cdd98-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="cdd98-183">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="cdd98-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="cdd98-184">GoDaddy または別のパートナーからサブスクリプションを購入した場合</span><span class="sxs-lookup"><span data-stu-id="cdd98-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="cdd98-185">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd98-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="cdd98-186">関連記事</span><span class="sxs-lookup"><span data-stu-id="cdd98-186">Related articles</span></span>

[<span data-ttu-id="cdd98-187">別のアドレスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="cdd98-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="cdd98-188">ユーザー名とメール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="cdd98-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

