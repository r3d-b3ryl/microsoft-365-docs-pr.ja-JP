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
description: ユーザーを追加して、同時に Microsoft 365 にライセンスを割り当てる方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: 412774c9786abc01e94c5a350871f9d34586cce4
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114155"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="5a7d9-103">ユーザーを追加して同時にライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5a7d9-103">Add users and assign licenses at the same time</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5a7d9-104">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-104">The admin center is changing.</span></span> <span data-ttu-id="5a7d9-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="5a7d9-106">[一般法人向け Microsoft 365](https://www.microsoft.com/microsoft-365/business) にサインインしてアクセスする前に、チームの各ユーザーにはユーザー アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-106">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="5a7d9-107">ユーザー アカウントを追加する最も簡単な方法は、Microsoft 365 管理センターで 1 人ずつ追加する方法です。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-107">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5a7d9-108">この手順を実行すると、Microsoft 365 ライセンス、サインイン用の資格情報、および Microsoft 365 メールボックスがユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-108">After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5a7d9-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="5a7d9-109">Before you begin</span></span>

<span data-ttu-id="5a7d9-110">ユーザーを追加してライセンスを割り当てるには、グローバル管理者、ライセンス管理者、またはユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-110">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="5a7d9-111">詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-111">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="watch-add-users-in-the-admin-center"></a><span data-ttu-id="5a7d9-112">視聴: 管理センターでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="5a7d9-112">Watch: Add users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="5a7d9-113">動画で使用されている手順では、ユーザーを追加するための出発点が異なっていますが、残りの手順は以下の手順と同じです。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-113">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time"></a><span data-ttu-id="5a7d9-114">ユーザーを 1 人ずつ追加する</span><span class="sxs-lookup"><span data-stu-id="5a7d9-114">Add users one at a time</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5a7d9-115"><https://admin.microsoft.com> で管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-115">Go to the admin center at <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="5a7d9-116">[**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-116">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="5a7d9-117">[**基本設定**] ウィンドウにユーザーの基本情報を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-117">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="5a7d9-118">[**名前**] 姓、名、表示名、ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-118">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="5a7d9-119">[**ドメイン**] ユーザーのアカウントのドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-119">**Domain** Choose the domain for the user's account.</span></span> <span data-ttu-id="5a7d9-120">たとえば、ユーザー名が Jakob、そのドメインが contoso.com の場合、「jakob@contoso.com」と入力してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-120">For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="5a7d9-121">[**パスワードの設定**] ユーザー用のパスワードとして、自動生成されたパスワードを使用するのか独自の強力なパスワードを作成するのかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-121">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="5a7d9-122">ユーザーは 90 日後にパスワードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-122">The user must change their password after 90 days.</span></span> <span data-ttu-id="5a7d9-123">または、[**初回サインイン時にこのユーザーにパスワードの変更を要求する**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-123">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="5a7d9-124">ユーザーが追加されたときに、パスワードをメールで送信するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-124">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="5a7d9-125">[**製品ライセンスの割り当て**] ウィンドウで、ユーザーの場所と適切なライセンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-125">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="5a7d9-126">利用可能なライセンスがない場合でも、ユーザーを追加し、追加のライセンスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-126">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="5a7d9-127">[**アプリ**] を展開し、アプリを選択または選択解除して、ユーザーにライセンスが付与されるアプリを制限します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-127">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="5a7d9-128">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-128">Select **Next**.</span></span>
5. <span data-ttu-id="5a7d9-129">[**オプションの設定**] ウィンドウで、このユーザーを管理者にする場合は [**役割**] を展開します。ユーザーに関する追加情報を入力する場合は、[**プロファイル情報**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-129">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="5a7d9-130">[**次へ**] を選択し、新しいユーザーの設定を確認し、必要に応じて変更を行い、[**追加の完了**] を選択し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-130">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5a7d9-131"><https://portal.office.de/adminportal> で管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-131">Go to the admin center at <https://portal.office.de/adminportal>.</span></span>
2. <span data-ttu-id="5a7d9-132">[**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-132">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="5a7d9-133">[**新しいユーザー**] ウィンドウで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-133">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="5a7d9-134">完了したら、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-134">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="5a7d9-135">[**名前**] 名、姓、表示名、ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-135">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="5a7d9-136">[**ドメイン**] たとえば、ユーザー名が Jakob、そのドメインが contoso.com の場合、「jakob@contoso.com」と入力してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-136">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="5a7d9-137">[**連絡先情報**] 展開して、携帯電話番号、住所などを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-137">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="5a7d9-138">[**パスワード**] 自動生成されたパスワードを使用するか、展開してユーザーに強力なパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-138">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="5a7d9-139">ユーザーは 90 日後にパスワードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-139">They must change their password after 90 days.</span></span> <span data-ttu-id="5a7d9-140">または、[ **ユーザーが初回サインイン時にパスワードを変更する**] を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-140">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="5a7d9-141">[**役割**] このユーザーに管理者権限を割り当てる場合に展開します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-141">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="5a7d9-p109">[**製品ライセンス**] このセクションを展開し、適切なライセンスを選択します。利用可能なライセンスを持っていない場合でも、ユーザーを追加したり、追加のライセンスを購入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5a7d9-144"><https://portal.partner.microsoftonline.cn> で管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-144">Go to the admin center at <https://portal.partner.microsoftonline.cn>.</span></span>
2. <span data-ttu-id="5a7d9-145">[**ユーザー**] > [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-145">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="5a7d9-146">[**新しいユーザー**] ウィンドウで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-146">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="5a7d9-147">完了したら、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-147">When you're finished, select **Add**.</span></span>
    - <span data-ttu-id="5a7d9-148">[**名前**] 名、姓、表示名、ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-148">**Name** Fill in first, last, display name, and user name.</span></span>
    - <span data-ttu-id="5a7d9-149">[**ドメイン**] たとえば、ユーザー名が Jakob、そのドメインが contoso.com の場合、「jakob@contoso.com」と入力してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-149">**Domain** For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in to by typing jakob@contoso.com.</span></span>
    - <span data-ttu-id="5a7d9-150">[**連絡先情報**] 展開して、携帯電話番号、住所などを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-150">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span>
    - <span data-ttu-id="5a7d9-151">[**パスワード**] 自動生成されたパスワードを使用するか、展開してユーザーに強力なパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-151">**Password** Use the autogenerated password or expand to specify a strong password for the user.</span></span> <span data-ttu-id="5a7d9-152">ユーザーは 90 日後にパスワードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-152">They must change their password after 90 days.</span></span> <span data-ttu-id="5a7d9-153">または、[ **ユーザーが初回サインイン時にパスワードを変更する**] を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-153">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    - <span data-ttu-id="5a7d9-154">[**役割**] このユーザーに管理者権限を割り当てる場合に展開します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-154">**Roles** Expand if you need to make this user an admin.</span></span>
    - <span data-ttu-id="5a7d9-p112">[**製品ライセンス**] このセクションを展開し、適切なライセンスを選択します。利用可能なライセンスを持っていない場合でも、ユーザーを追加したり、追加のライセンスを購入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-p112">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span>

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="5a7d9-157">複数のユーザーを同時に追加する</span><span class="sxs-lookup"><span data-stu-id="5a7d9-157">Add multiple users at the same time</span></span>

<span data-ttu-id="5a7d9-158">複数のユーザーを同時に追加するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-158">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="5a7d9-159">**ユーザーをまとめて追加するには、スプレッドシートを使用します。**</span><span class="sxs-lookup"><span data-stu-id="5a7d9-159">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="5a7d9-160">「[同時に複数のユーザーを追加する](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-160">See [Add several users at the same time](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time).</span></span>
- <span data-ttu-id="5a7d9-161">**アカウントの追加とライセンスの割り当てを自動化します。**</span><span class="sxs-lookup"><span data-stu-id="5a7d9-161">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="5a7d9-162">「[Microsoft 365 の PowerShell を使用してユーザー アカウントを作成する](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-162">See [Create user accounts with Microsoft 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell).</span></span> <span data-ttu-id="5a7d9-163">この方法は、Windows PowerShell コマンドレットについて詳しい知識のある場合に選んでください。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-163">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="5a7d9-164">**ActiveDirectory を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="5a7d9-164">**Using ActiveDirectory?**</span></span> <span data-ttu-id="5a7d9-165">[Microsoft 365 のディレクトリ同期をセットアップ](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-165">[Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="5a7d9-166">Azure AD Connect ツールを使用し、Microsoft 365 で Active Directory ユーザー アカウント (およびその他の Active Directory オブジェクト) を複製します。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-166">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365.</span></span> <span data-ttu-id="5a7d9-167">同期では、ユーザー アカウントのみが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-167">The sync only adds the user accounts.</span></span> <span data-ttu-id="5a7d9-168">同期されているユーザーがメールとその他の Office アプリを使用するには、そのユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-168">You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="5a7d9-169">**Exchange Server から移行する場合**</span><span class="sxs-lookup"><span data-stu-id="5a7d9-169">**Migrating from Exchange?**</span></span> <span data-ttu-id="5a7d9-170">「[複数のメール アカウントを Office 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-170">See [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="5a7d9-171">カットオーバー、段階的方法、またはハイブリッド Exchange による方法のいずれかを使って、複数のメールボックスを Microsoft 365 に移行するときは、移行の一部としてユーザーが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-171">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="5a7d9-172">移行では、ユーザー アカウントのみが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-172">The migration only adds the user accounts.</span></span> <span data-ttu-id="5a7d9-173">ユーザーがメールとその他の Office アプリを使用するには、そのユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-173">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="5a7d9-174">ユーザーにライセンスを割り当てない場合、30 日間の猶予期間が過ぎるとユーザーのメールボックスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-174">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="5a7d9-175">Microsoft 365 管理センターで[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-175">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a7d9-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="5a7d9-176">Next steps</span></span>

<span data-ttu-id="5a7d9-177">ユーザーを追加すると、Microsoft からメール通知が届きます。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-177">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="5a7d9-178">メールには、ユーザーが Microsoft 365 にサインインするための Microsoft 365 のユーザー ID とパスワードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-178">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="5a7d9-179">新しいパスワードは、通常のプロセスを使用して通知してください。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-179">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="5a7d9-180">新しいユーザーと「[従業員のクイック スタート ガイド](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)」を共有し、ユーザーが「[PC または Mac に Office アプリをダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-180">Share the [Employee quickstart guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="5a7d9-181">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="5a7d9-181">Related content</span></span>

<span data-ttu-id="5a7d9-182">[Microsoft 365 に新しい従業員を追加する](add-new-employee.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="5a7d9-182">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="5a7d9-183">[同時に複数のユーザーを Microsoft 365 に追加する](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (記事)</span><span class="sxs-lookup"><span data-stu-id="5a7d9-183">[Add several users at the same time to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (article)</span></span>\
<span data-ttu-id="5a7d9-184">[Microsoft 365 のユーザーを復元する](restore-user.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="5a7d9-184">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="5a7d9-185">[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="5a7d9-185">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="5a7d9-186">[組織からユーザーを削除する](delete-a-user.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="5a7d9-186">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
