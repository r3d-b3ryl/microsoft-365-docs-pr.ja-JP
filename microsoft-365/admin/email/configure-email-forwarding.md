---
title: メール転送を構成する
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
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365 を使用して、1つまたは複数の電子メールアカウントへのメール転送を設定します。
ms.openlocfilehash: 5807649fa43d094fd8f05cf63e2905d7cdb6dd7d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628917"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="cbf46-103">メール転送を構成する</span><span class="sxs-lookup"><span data-stu-id="cbf46-103">Configure email forwarding</span></span>
  
<span data-ttu-id="cbf46-104">組織の管理者として、ユーザーのメールボックスの電子メール転送を設定するには、会社の要件がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="cbf46-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="cbf46-105">メール転送を利用すれば、あるユーザーのメールボックスに送信されたメール メッセージを組織内外の別のユーザーのメールボックスに転送できます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="cbf46-106">メール転送を構成する</span><span class="sxs-lookup"><span data-stu-id="cbf46-106">Configure email forwarding</span></span>

 <span data-ttu-id="cbf46-107">メール転送を設定する前に、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cbf46-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="cbf46-108">メール転送を設定すると *、そのメール*ボックスに送信された**新しい**メールだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="cbf46-109">電子メール転送では、送信*元*アカウントにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="cbf46-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="cbf46-110">ユーザーが組織を去ったことによりメール転送を設定する場合には、別の方法として[そのユーザーのメールボックスを共有メールボックス変換](convert-user-mailbox-to-shared-mailbox.md)することです。</span><span class="sxs-lookup"><span data-stu-id="cbf46-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="cbf46-111">こうすることで、複数のユーザーがそのメールボックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-111">This way several people can access it.</span></span> <span data-ttu-id="cbf46-112">ただし、共有メールボックスは 50 GB 以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbf46-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="cbf46-113">これらの手順を実行するには、Microsoft 365 の Exchange 管理者または全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbf46-113">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="cbf46-114">詳細については、「[管理者の役割につい](../add-users/about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbf46-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="cbf46-115">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="cbf46-116">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="cbf46-117">転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="cbf46-118">[**メール**] タブで、[**メール転送の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="cbf46-119">[電子メールの転送] ページで、[**このメールボックスに送信されたすべてのメールを転送する**] を選択し、転送先アドレスを入力して、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="cbf46-120">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="cbf46-121">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="cbf46-122">**複数の電子メールアドレスに転送する**場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-122">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="cbf46-123">詳細については、「[ルールを使用してメッセージを自動的に転送する](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbf46-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="cbf46-124">または、管理センターで[配布グループを作成](../setup/create-distribution-lists.md)し、[そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="cbf46-125">転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="cbf46-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="cbf46-126">その場合、電子メールの転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="cbf46-127">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="cbf46-128">転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="cbf46-129">[**メールの設定**] を展開し、[**電子メールの転送**] セクションで [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="cbf46-130">[電子メールの転送] ページで、 **[オン**] に切り替え、[転送先アドレス] を入力して、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="cbf46-131">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="cbf46-132">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-132">Select **Save**.</span></span>
    
    <span data-ttu-id="cbf46-133">**複数の電子メールアドレスに転送する**場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="cbf46-134">詳細については、「[ルールを使用してメッセージを自動的に転送する](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbf46-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="cbf46-135">または、管理センターで[配布グループを作成](../setup/create-distribution-lists.md)し、[そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="cbf46-136">転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="cbf46-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="cbf46-137">その場合、電子メールの転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="cbf46-138">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="cbf46-139">転送する電子メールがあるユーザーの名前を選択して、[プロパティ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="cbf46-140">[**メールの設定**] を展開し、[**電子メールの転送**] セクションで [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="cbf46-141">[電子メールの転送] ページで、 **[オン**] に切り替え、[転送先アドレス] を入力して、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="cbf46-142">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="cbf46-143">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-143">Select **Save**.</span></span>
    
    <span data-ttu-id="cbf46-144">**複数の電子メールアドレスに転送する**場合は、アドレスに転送するために Outlook でルールをセットアップするようにユーザーに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="cbf46-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="cbf46-145">詳細については、「[ルールを使用してメッセージを自動的に転送する](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbf46-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="cbf46-146">または、管理センターで[配布グループを作成](../setup/create-distribution-lists.md)し、[そこにアドレスを追加](add-user-or-contact-to-distribution-list.md)してから、この記事の手順に従って DL を指すように転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="cbf46-147">転送しているメールのユーザーのアカウントを削除したり、ライセンスを削除したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="cbf46-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="cbf46-148">その場合、電子メールの転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="cbf46-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
