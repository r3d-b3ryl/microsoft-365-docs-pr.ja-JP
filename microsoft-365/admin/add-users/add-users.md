---
title: ユーザーを追加してライセンスを割り当てる
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: ユーザーを追加して、Microsoft 365 にライセンスを同時に割り当てる方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 016c98fc93bfa1a92274a5b991cf8adbd1131bc9
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015889"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="5013e-103">ユーザーを追加して、ライセンスを同時に割り当てる</span><span class="sxs-lookup"><span data-stu-id="5013e-103">Add users and assign licenses at the same time</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5013e-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="5013e-104">The admin center is changing.</span></span> <span data-ttu-id="5013e-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5013e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="5013e-106">チームのメンバーは、サインインして[Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395)にアクセスする前に、ユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5013e-106">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="5013e-107">ユーザー アカウントを追加する最も簡単な方法は、Microsoft 365 管理センターで 1 人ずつ追加する方法です。</span><span class="sxs-lookup"><span data-stu-id="5013e-107">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5013e-108">この手順を実行すると、ユーザーには Microsoft 365 ライセンス、サインイン資格情報、および Microsoft 365 メールボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="5013e-108">After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5013e-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="5013e-109">Before you begin</span></span>

<span data-ttu-id="5013e-110">ユーザーを追加してライセンスを割り当てるには、グローバル、ライセンス、またはユーザーの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5013e-110">You must be a Global, License, or a User admin to add users and assign licenses.</span></span> <span data-ttu-id="5013e-111">詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5013e-111">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="watch-add-users-in-the-admin-center"></a><span data-ttu-id="5013e-112">視聴: 管理センターでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="5013e-112">Watch: Add users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="5013e-113">ビデオで使用されている手順はユーザーを追加するための開始点とは異なりますが、残りの手順は次の手順と同じです。</span><span class="sxs-lookup"><span data-stu-id="5013e-113">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time"></a><span data-ttu-id="5013e-114">一度に1人ずつユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="5013e-114">Add users one at a time</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5013e-115"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5013e-115">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="5013e-116">[**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-116">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="5013e-117">[基本 **] ウィンドウで**、[基本的なユーザー情報] を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-117">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="5013e-118">**名前**姓と名、表示名、およびユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5013e-118">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="5013e-119">**ドメイン**ユーザーのアカウントのドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-119">**Domain** Choose the domain for the user's account.</span></span> <span data-ttu-id="5013e-120">たとえば、ユーザーの username が Jakob で、ドメインが contoso.com の場合は、jakob@contoso.com を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5013e-120">For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="5013e-121">**パスワードの設定**自動生成されたパスワードを使用するか、ユーザーに対して独自の強力なパスワードを作成するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-121">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="5013e-122">ユーザーは、90日後にパスワードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5013e-122">The user must change their password after 90 days.</span></span> <span data-ttu-id="5013e-123">または、[**初回サインイン時にこのユーザーにパスワードの変更を要求する**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="5013e-123">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="5013e-124">ユーザーが追加されたときに、パスワードを電子メールで送信するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-124">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="5013e-125">[**製品ライセンスの割り当て**] ウィンドウで、ユーザーの場所と適切なライセンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-125">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="5013e-126">利用可能なライセンスがない場合でも、ユーザーを追加し、追加のライセンスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="5013e-126">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="5013e-127">[**アプリ**] を展開し、アプリを選択または選択解除して、ユーザーがライセンスを持っているアプリを制限します。</span><span class="sxs-lookup"><span data-stu-id="5013e-127">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="5013e-128">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-128">Select **Next**.</span></span>
5. <span data-ttu-id="5013e-129">[**オプションの設定**] ウィンドウで、[**役割**] を展開してこのユーザーを管理者にします。[**プロファイル情報**] を展開して、ユーザーに関するその他の情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="5013e-129">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="5013e-130">[**次へ**] を選択し、新しいユーザーの設定を確認し、必要に応じて変更を加えてから、[**追加**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-130">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5013e-131"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5013e-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>
2. <span data-ttu-id="5013e-132">[**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-132">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="5013e-133">[**新しいユーザー**] ウィンドウで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5013e-133">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="5013e-134">完了したら、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-134">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="5013e-135">[**名前**] 名、姓、表示名、ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5013e-135">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="5013e-136">**ドメイン**たとえば、ユーザーの username が Jakob で、ドメインが contoso.com の場合は、jakob@contoso.com と入力することによってにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5013e-136">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="5013e-137">[**連絡先情報**] 展開して、携帯電話番号、住所などを入力します。</span><span class="sxs-lookup"><span data-stu-id="5013e-137">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="5013e-138">**Password**自動生成されたパスワードを使用するか、または展開して、ユーザーに強力なパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5013e-138">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="5013e-139">90日後にパスワードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5013e-139">They must change their password after 90 days.</span></span> <span data-ttu-id="5013e-140">または、[ **ユーザーが初回サインイン時にパスワードを変更する**] を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="5013e-140">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="5013e-141">[**役割**] このユーザーに管理者権限を割り当てる場合に展開します。</span><span class="sxs-lookup"><span data-stu-id="5013e-141">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="5013e-p109">[**製品ライセンス**] このセクションを展開し、適切なライセンスを選択します。利用可能なライセンスを持っていない場合でも、ユーザーを追加したり、追加のライセンスを購入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5013e-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5013e-144"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5013e-144">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>
2. <span data-ttu-id="5013e-145">[**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-145">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="5013e-146">[**新しいユーザー**] ウィンドウで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5013e-146">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="5013e-147">完了したら、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5013e-147">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="5013e-148">[**名前**] 名、姓、表示名、ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5013e-148">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="5013e-149">**ドメイン**たとえば、ユーザーの username が Jakob で、ドメインが contoso.com の場合は、jakob@contoso.com と入力することによってにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5013e-149">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="5013e-150">[**連絡先情報**] 展開して、携帯電話番号、住所などを入力します。</span><span class="sxs-lookup"><span data-stu-id="5013e-150">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="5013e-151">**Password**自動生成されたパスワードを使用するか、または展開して、ユーザーに強力なパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5013e-151">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="5013e-152">90日後にパスワードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5013e-152">They must change their password after 90 days.</span></span> <span data-ttu-id="5013e-153">または、[ **ユーザーが初回サインイン時にパスワードを変更する**] を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="5013e-153">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="5013e-154">[**役割**] このユーザーに管理者権限を割り当てる場合に展開します。</span><span class="sxs-lookup"><span data-stu-id="5013e-154">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="5013e-p112">[**製品ライセンス**] このセクションを展開し、適切なライセンスを選択します。利用可能なライセンスを持っていない場合でも、ユーザーを追加したり、追加のライセンスを購入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5013e-p112">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="5013e-157">一度に複数のユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="5013e-157">Add multiple users at the same time</span></span>

<span data-ttu-id="5013e-158">複数のユーザーを同時に追加するには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5013e-158">You can use any of the following methods to add multiple users at the same time:</span></span>
  
- <span data-ttu-id="5013e-159">**ユーザーをまとめて追加するには、スプレッドシートを使用します。**</span><span class="sxs-lookup"><span data-stu-id="5013e-159">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="5013e-160">「[同時に複数のユーザーを追加する](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5013e-160">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
- <span data-ttu-id="5013e-161">**アカウントの追加とライセンスの割り当てを自動化します。**</span><span class="sxs-lookup"><span data-stu-id="5013e-161">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="5013e-162">「[Office 365 PowerShell を使用してユーザー アカウントを作成する](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5013e-162">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="5013e-163">この方法は、Windows PowerShell コマンドレットについて詳しい知識のある場合に選んでください。</span><span class="sxs-lookup"><span data-stu-id="5013e-163">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="5013e-164">**ActiveDirectory を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="5013e-164">**Using ActiveDirectory?**</span></span> <span data-ttu-id="5013e-165">[Office 365 のディレクトリ同期をセットアップ](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)します。</span><span class="sxs-lookup"><span data-stu-id="5013e-165">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="5013e-166">Azure AD Connect ツールを使用して、Microsoft 365 の Active Directory ユーザーアカウント (およびその他の Active Directory オブジェクト) をレプリケートします。</span><span class="sxs-lookup"><span data-stu-id="5013e-166">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="5013e-167">同期では、ユーザー アカウントのみが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5013e-167">The sync only adds the user accounts.</span></span> <span data-ttu-id="5013e-168">電子メールやその他の Office アプリを使用するには、その前に、同期されたユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5013e-168">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="5013e-169">**Exchange Server から移行する場合**</span><span class="sxs-lookup"><span data-stu-id="5013e-169">**Migrating from Exchange?**</span></span> <span data-ttu-id="5013e-170">[複数のメールアカウントを Office 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5013e-170">See [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="5013e-171">カットオーバー、ステージング、またはハイブリッド Exchange のいずれかの方法を使用して、複数のメールボックスを Microsoft 365 に移行する場合、ユーザーは移行の一部として自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5013e-171">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="5013e-172">移行では、ユーザー アカウントのみが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5013e-172">The migration only adds the user accounts.</span></span> <span data-ttu-id="5013e-173">ユーザーが電子メールやその他の Office アプリを使用できるようにするには、その前にライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5013e-173">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="5013e-174">ユーザーにライセンスを割り当てない場合、30日の猶予期間後にメールボックスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="5013e-174">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="5013e-175">Microsoft 365 管理センターで[ライセンスをユーザーに割り当てる](../manage/assign-licenses-to-users.md)方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5013e-175">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5013e-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="5013e-176">Next steps</span></span>

<span data-ttu-id="5013e-177">ユーザーを追加すると、Microsoft からの電子メール通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5013e-177">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="5013e-178">電子メールには、ユーザーのユーザー ID とパスワードが含まれているため、Microsoft 365 にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="5013e-178">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="5013e-179">新しいパスワードは、通常のプロセスを使用して通知してください。</span><span class="sxs-lookup"><span data-stu-id="5013e-179">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="5013e-180">[Office アプリを PC または Mac にダウンロードしてインストール](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)する方法や、[モバイルデバイスで office アプリや電子メール](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)をセットアップする方法などの設定を行うために、[従業員のクイックスタートガイド](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)を新しいユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="5013e-180">Share the [Employee quickstart guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="5013e-181">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="5013e-181">Related content</span></span>

<span data-ttu-id="5013e-182">[Microsoft 365 (記事) に新しい従業員を追加](add-new-employee.md)します。</span><span class="sxs-lookup"><span data-stu-id="5013e-182">[Add a new employee to Microsoft 365](add-new-employee.md) (article)\</span></span>
<span data-ttu-id="5013e-183">[複数のユーザーを同時に Microsoft 365 (記事) に追加する](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)</span><span class="sxs-lookup"><span data-stu-id="5013e-183">[Add several users at the same time to Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time) (article)\</span></span>
<span data-ttu-id="5013e-184">[Microsoft 365 でユーザーを復元する](restore-user.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="5013e-184">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="5013e-185">[ユーザーへのライセンスの割り当て](../manage/assign-licenses-to-users.md)(記事) </span><span class="sxs-lookup"><span data-stu-id="5013e-185">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="5013e-186">[組織からユーザーを削除する](delete-a-user.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="5013e-186">[Delete a user from your organization](delete-a-user.md) (article)</span></span>