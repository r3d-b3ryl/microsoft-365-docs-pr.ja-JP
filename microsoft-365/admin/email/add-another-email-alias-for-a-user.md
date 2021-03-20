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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Microsoft 365 for business アカウントに関連付けられたメール エイリアスと呼ばれる複数の電子メール アドレスを持つ方法について説明します。 '
ms.openlocfilehash: 590782f7b22b1d26abef83f884d45da567f0425c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915952"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="6e2f7-103">ユーザーに別のメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="6e2f7-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6e2f7-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-104">The admin center is changing.</span></span> <span data-ttu-id="6e2f7-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="6e2f7-106">この記事は、ビジネス サブスクリプションを持つ Microsoft 365 管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="6e2f7-107">ホーム ユーザー向けではありません。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-107">It's not for home users.</span></span>
  
<span data-ttu-id="6e2f7-108">Microsoft 365 のプライマリ メール アドレスは、通常、アカウントの作成時にユーザーが割り当てられた電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="6e2f7-109">ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="6e2f7-110">また、複数の電子メール アドレスを Microsoft 365 for business アカウントに関連付けすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="6e2f7-111">これらの追加アドレスをエイリアスと呼びます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="6e2f7-112">たとえば、Jenna が電子メール アドレス jenna@contosoco.com を持っているが、jen@contosoco.com でメールを受け取りたい場合は、その名前で彼女を参照する人もいたとします。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="6e2f7-113">両方のメール アドレスが Jenna の受信トレイに移動できるよう、エイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="6e2f7-114">ユーザーあたり最大 400 個のエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="6e2f7-115">追加の料金やライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="6e2f7-116">複数のユーザーが 1 つの電子メール アドレスに送信されるメールを管理する場合 (info@NodPublishers.com、sales@NodPublishers.com メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="6e2f7-117">詳細については、「共有メールボックスの [作成」を参照してください](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="6e2f7-118">ユーザーにメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="6e2f7-118">Add email aliases to a user</span></span>
<span data-ttu-id="6e2f7-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="6e2f7-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="6e2f7-120">これを行うには [、管理者のアクセス許可](../add-users/about-admin-roles.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="6e2f7-121">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6e2f7-122">[アクティブ ユーザー **] ページ** で、[メール エイリアスの管理] > **ユーザーを選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="6e2f7-123">ユーザーにライセンスが割り当てられていない場合、このオプションは表示しません。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="6e2f7-124">[+ **エイリアスの追加] を選択** し、ユーザーの新しいエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="6e2f7-125">エラー メッセージが表示された場合は、パラメーター名 **'EmailAddresses,"** と一致するパラメーターが見つかりません。これは、テナントのセットアップを終了するにはもう少し時間がかかるか、最近追加した場合はカスタム ドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6e2f7-126">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6e2f7-127">しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6e2f7-128">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="6e2f7-129">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6e2f7-130">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6e2f7-131">リストに別のドメイン名を追加するには [、「Add a domain to Microsoft 365」を参照してください](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-131">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="6e2f7-132">完了したら、[変更の保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="6e2f7-133">Microsoft 365 全体で新しいエイリアスが設定されるのを 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="6e2f7-134">これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6e2f7-135">たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6e2f7-136">**ユーザーが返信すると *、From*  アドレスがメインの電子メール エイリアスです。**</span><span class="sxs-lookup"><span data-stu-id="6e2f7-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6e2f7-137">たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6e2f7-138">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="6e2f7-139">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="6e2f7-140">[**アクティブなユーザー**] ページで、編集するユーザー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="6e2f7-141">[ユーザー名 **/ メール エイリアス] の横にある [** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="6e2f7-142">エラー メッセージが表示された場合は、パラメーター名 **'EmailAddresses,"** と一致するパラメーターが見つかりません。これは、テナントのセットアップを終了するにはもう少し時間がかかるか、最近追加した場合はカスタム ドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6e2f7-143">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6e2f7-144">しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6e2f7-145">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="6e2f7-146">[エイリアス] の下 **のテキスト ボックス** に、新しいメール エイリアスの最初の部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="6e2f7-147">独自のドメインを Microsoft 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="6e2f7-148">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6e2f7-149">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6e2f7-150">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6e2f7-151">リストに別のドメイン名を追加するには [、「Add a domain to Microsoft 365」を参照してください](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-151">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="6e2f7-152">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="6e2f7-153">Microsoft 365 全体で新しいエイリアスが設定されるのを 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="6e2f7-154">これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6e2f7-155">たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6e2f7-156">**ユーザーが返信すると *、From*  アドレスがメインの電子メール エイリアスです。**</span><span class="sxs-lookup"><span data-stu-id="6e2f7-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6e2f7-157">たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6e2f7-158">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6e2f7-159">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="6e2f7-160">[**アクティブなユーザー**] ページで、編集するユーザー名を選びます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="6e2f7-161">[ユーザー名 **/ メール エイリアス] の横にある [** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="6e2f7-162">エラー メッセージが表示された場合は、パラメーター名 **'EmailAddresses,"** と一致するパラメーターが見つかりません。これは、テナントのセットアップを終了するにはもう少し時間がかかるか、最近追加した場合はカスタム ドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6e2f7-163">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6e2f7-164">しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6e2f7-165">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="6e2f7-166">[エイリアス] の下 **のテキスト ボックス** に、新しいメール エイリアスの最初の部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="6e2f7-167">独自のドメインを Microsoft 365 に追加した場合は、ドロップダウン リストを使って新しいメール エイリアスにそのドメインを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="6e2f7-168">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6e2f7-169">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6e2f7-170">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6e2f7-171">リストに別のドメイン名を追加するには [、「Add a domain to Microsoft 365」を参照してください](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-171">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="6e2f7-172">完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="6e2f7-173">Microsoft 365 全体で新しいエイリアスが設定されるのを 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="6e2f7-174">これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6e2f7-175">たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6e2f7-176">**ユーザーが返信すると *、From*  アドレスがメインの電子メール エイリアスです。**</span><span class="sxs-lookup"><span data-stu-id="6e2f7-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6e2f7-177">たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6e2f7-178">Eliza がメッセージに返信する場合、Sales@NodPublishers.com ではなく、Eliza のプライマリ メール アドレスが送信者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="6e2f7-179">"パラメーター名 EmailAddresses に一致するパラメーターが見つかりません" を取得しましたか?</span><span class="sxs-lookup"><span data-stu-id="6e2f7-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="6e2f7-180">"パラメーター名 **EmailAddresses** に一致するパラメーターが見つかりません" というエラー メッセージが表示された場合は、テナントのセットアップを完了するにはもう少し時間がかかっています。最近追加した場合は、カスタム ドメインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6e2f7-181">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6e2f7-182">しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6e2f7-183">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="6e2f7-184">GoDaddy または別のパートナーからサブスクリプションを購入した場合</span><span class="sxs-lookup"><span data-stu-id="6e2f7-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="6e2f7-185">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2f7-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="6e2f7-186">関連記事</span><span class="sxs-lookup"><span data-stu-id="6e2f7-186">Related articles</span></span>

[<span data-ttu-id="6e2f7-187">別のアドレスからメールを送信する</span><span class="sxs-lookup"><span data-stu-id="6e2f7-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="6e2f7-188">ユーザー名とメール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="6e2f7-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
