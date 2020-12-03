---
title: メール転送を構成する
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
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365 を使用して、1つまたは複数の電子メールアカウントへのメール転送を設定します。
ms.openlocfilehash: c821d4363a053b432c4376d7b4fec4926df7b568
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560794"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="b10ed-103">メール転送を構成する</span><span class="sxs-lookup"><span data-stu-id="b10ed-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b10ed-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="b10ed-104">The admin center is changing.</span></span> <span data-ttu-id="b10ed-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="b10ed-106">組織の管理者として、ユーザーのメールボックスの電子メール転送を設定するには、会社の要件がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b10ed-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="b10ed-107">メール転送を利用すれば、あるユーザーのメールボックスに送信されたメール メッセージを組織内外の別のユーザーのメールボックスに転送できます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b10ed-108">送信スパムフィルターポリシーを使用して、外部の受信者への自動転送を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="b10ed-109">詳細については、「 [Microsoft 365 での自動外部電子メール転送の制御](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="b10ed-110">メール転送を構成する</span><span class="sxs-lookup"><span data-stu-id="b10ed-110">Configure email forwarding</span></span>

 <span data-ttu-id="b10ed-111">メール転送を設定する前に、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-111">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="b10ed-112">メール転送を設定すると、*差出人* メールボックスに送信された **新しい** メールだけが転送されます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="b10ed-113">電子メール転送では、送信  *元*  アカウントにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b10ed-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="b10ed-114">ユーザーが組織を去ったことによりメール転送を設定する場合には、別の方法として[そのユーザーのメールボックスを共有メールボックス変換](convert-user-mailbox-to-shared-mailbox.md)することです。</span><span class="sxs-lookup"><span data-stu-id="b10ed-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="b10ed-115">こうすることで、複数のユーザーがそのメールボックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-115">This way several people can access it.</span></span> <span data-ttu-id="b10ed-116">ただし、共有メールボックスは 50 GB 以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b10ed-116">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="b10ed-117">これらの手順を実行するには、Microsoft 365 の Exchange 管理者または全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b10ed-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="b10ed-118">詳細については、「 [管理者の役割につい](../add-users/about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b10ed-119">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="b10ed-120">転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-120">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="b10ed-121">[ **メール** ] タブで、[ **メール転送の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-121">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="b10ed-122">[電子メールの転送] ページで、[ **このメールボックスに送信されたすべてのメールを転送する**] を選択し、転送先アドレスを入力して、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b10ed-123">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b10ed-124">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-124">Select **Save changes**.</span></span>
    
    <span data-ttu-id="b10ed-125">**複数の電子メールアドレスに転送する** 場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b10ed-126">詳細については、「 [ルールを使用してメッセージを自動的に転送する](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b10ed-127">または、管理センターで [配布グループを作成](../setup/create-distribution-lists.md)し、 [そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b10ed-128">転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b10ed-129">その場合、電子メールの転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-129">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="b10ed-130">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="b10ed-131">転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-131">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="b10ed-132">[ **メールの設定**] を展開し、[ **電子メールの転送** ] セクションで [ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="b10ed-133">[電子メールの転送] ページで、 **[オン**] に切り替え、[転送先アドレス] を入力して、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b10ed-134">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b10ed-135">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-135">Select **Save**.</span></span>
    
    <span data-ttu-id="b10ed-136">**複数の電子メールアドレスに転送する** 場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b10ed-137">詳細については、「 [ルールを使用してメッセージを自動的に転送する](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b10ed-138">または、管理センターで [配布グループを作成](../setup/create-distribution-lists.md)し、 [そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b10ed-139">転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b10ed-140">その場合、電子メールの転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-140">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b10ed-141">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="b10ed-142">転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-142">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="b10ed-143">[ **メールの設定**] を展開し、[ **電子メールの転送** ] セクションで [ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="b10ed-144">[電子メールの転送] ページで、 **[オン**] に切り替え、[転送先アドレス] を入力して、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b10ed-145">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b10ed-146">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-146">Select **Save**.</span></span>
    
    <span data-ttu-id="b10ed-147">**複数の電子メールアドレスに転送する** 場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="b10ed-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b10ed-148">詳細については、「 [ルールを使用してメッセージを自動的に転送する](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b10ed-149">または、管理センターで [配布グループを作成](../setup/create-distribution-lists.md)し、 [そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b10ed-150">転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="b10ed-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b10ed-151">その場合、電子メールの転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="b10ed-151">If you do, email forwarding will stop.</span></span> 


::: moniker-end 
