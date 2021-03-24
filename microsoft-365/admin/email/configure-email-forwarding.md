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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365 を使用して 1 つ以上のメール アカウントへのメール転送を設定します。
ms.openlocfilehash: cdefab3df59f1c57abbc221943b58c978ff582a9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050716"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="c7929-103">Microsoft 365 でのメール転送の構成</span><span class="sxs-lookup"><span data-stu-id="c7929-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c7929-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="c7929-104">The admin center is changing.</span></span> <span data-ttu-id="c7929-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7929-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c7929-106">組織の管理者として、ユーザーのメールボックスのメール転送をセットアップする会社の要件がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7929-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="c7929-107">メール転送を利用すれば、あるユーザーのメールボックスに送信されたメール メッセージを組織内外の別のユーザーのメールボックスに転送できます。</span><span class="sxs-lookup"><span data-stu-id="c7929-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7929-108">送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="c7929-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="c7929-109">詳細については [、「Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)で外部メールの自動転送を制御する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7929-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="c7929-110">メール転送を構成する</span><span class="sxs-lookup"><span data-stu-id="c7929-110">Configure email forwarding</span></span>

<span data-ttu-id="c7929-111">メール転送を設定する前に、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7929-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="c7929-112">メール転送を設定すると **、受信メールボックス** に送信された新しいメールだけが転送されます。</span><span class="sxs-lookup"><span data-stu-id="c7929-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="c7929-113">メール転送では、From アカウント  *に*  ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c7929-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="c7929-114">ユーザーが組織を去ったことによりメール転送を設定する場合には、別の方法として[そのユーザーのメールボックスを共有メールボックス変換](convert-user-mailbox-to-shared-mailbox.md)することです。</span><span class="sxs-lookup"><span data-stu-id="c7929-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="c7929-115">こうすることで、複数のユーザーがそのメールボックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c7929-115">This way several people can access it.</span></span> <span data-ttu-id="c7929-116">ただし、共有メールボックスは 50 GB 以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7929-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="c7929-117">これらの手順を実行するには、Microsoft 365 の Exchange 管理者またはグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7929-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="c7929-118">詳細については、「管理役割について [」を参照してください](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c7929-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c7929-119">管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=834822)** します。</span><span class="sxs-lookup"><span data-stu-id="c7929-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="c7929-120">メールを転送してプロパティ ページを開くユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="c7929-121">[メール] **タブで** 、[メール転送の **管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c7929-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="c7929-122">[電子メールの転送]ページで、[このメールボックスに送信されたメールを転送する] を選択し、転送先のアドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c7929-123">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7929-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c7929-124">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-124">Select **Save changes**.</span></span>

    <span data-ttu-id="c7929-125">**複数の電子メール アドレスに転送するには**、ユーザーに Outlook でアドレスに転送するルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7929-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c7929-126">詳細については、「ルールを使用して [メッセージを自動的に転送する」を参照してください](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="c7929-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="c7929-127">または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="c7929-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c7929-128">自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない!</span><span class="sxs-lookup"><span data-stu-id="c7929-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c7929-129">この操作を行った場合、メール転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="c7929-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c7929-130">管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=847686)** します。</span><span class="sxs-lookup"><span data-stu-id="c7929-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="c7929-131">メールを転送してプロパティ ページを開くユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="c7929-132">[メール **の設定]** を展開し、[メール転送] セクション **で** [編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c7929-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c7929-133">[メール転送] ページで、トグルを **[オン**] に設定し、転送先アドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c7929-134">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7929-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c7929-135">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-135">Select **Save**.</span></span>

   <span data-ttu-id="c7929-136">**複数の電子メール アドレスに転送するには**、ユーザーに Outlook でアドレスに転送するルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7929-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c7929-137">詳細については、「ルールを使用して [メッセージを自動的に転送する」を参照してください](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="c7929-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="c7929-138">または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="c7929-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c7929-139">自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない!</span><span class="sxs-lookup"><span data-stu-id="c7929-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c7929-140">この操作を行った場合、メール転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="c7929-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c7929-141">管理センターで、[ユーザーのアクティブな **ユーザー]** \> **[ページに移動](https://go.microsoft.com/fwlink/p/?linkid=850628)** します。</span><span class="sxs-lookup"><span data-stu-id="c7929-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="c7929-142">メールを転送してプロパティ ページを開くユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="c7929-143">[メール **の設定]** を展開し、[メール転送] セクション **で** [編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c7929-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c7929-144">[メール転送] ページで、トグルを **[オン**] に設定し、転送先アドレスを入力し、転送されたメールのコピーを保持するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c7929-145">このオプションが表示されない場合は、ライセンスがユーザー アカウントに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7929-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c7929-146">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7929-146">Select **Save**.</span></span>

   <span data-ttu-id="c7929-147">**複数の電子メール アドレスに転送するには**、ユーザーに Outlook でアドレスに転送するルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7929-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c7929-148">詳細については、「ルールを使用して [メッセージを自動的に転送する」を参照してください](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="c7929-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="c7929-149">または、管理センターで配布グループ[](../setup/create-distribution-lists.md)を作成し、その[](add-user-or-contact-to-distribution-list.md)配布グループにアドレスを追加し、この記事の手順を使用して DL をポイントする転送を設定します。</span><span class="sxs-lookup"><span data-stu-id="c7929-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c7929-150">自分のライセンスを転送または削除する電子メールのユーザーのアカウントを削除しない!</span><span class="sxs-lookup"><span data-stu-id="c7929-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c7929-151">この操作を行った場合、メール転送は停止します。</span><span class="sxs-lookup"><span data-stu-id="c7929-151">If you do, email forwarding will stop.</span></span>

::: moniker-end