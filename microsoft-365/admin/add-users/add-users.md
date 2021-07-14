---
title: ユーザーを追加してライセンスを割り当てる
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 各チーム メンバーは、一般法人向け Microsoft 365 にサインインしてアクセスする前に、ユーザー アカウントが必要になります。ユーザーを追加して、ライセンスを割り当てる方法について説明します。
ms.date: 07/01/2020
ms.openlocfilehash: aaba152e73fc7284f54a9f307783a66fb055a55c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394101"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="2edbf-104">ユーザーを追加して同時にライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2edbf-104">Add users and assign licenses at the same time</span></span>

<span data-ttu-id="2edbf-p102">チームのメンバーそれぞれに、[一般法人向け Microsoft 365](https://www.microsoft.com/microsoft-365/business) にサインインしてアクセスするためのユーザー アカウントが必要です。ユーザー アカウントを追加する最も簡単な方法は、Microsoft 365 管理センターで 1 人ずつ追加することです。この作業が完了すると、ユーザーに Microsoft 365 のライセンス、サインイン資格情報、および Microsoft 365 メールボックスが与えられます。</span><span class="sxs-lookup"><span data-stu-id="2edbf-p102">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business). The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center. After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2edbf-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="2edbf-108">Before you begin</span></span>

<span data-ttu-id="2edbf-109">ユーザーを追加してライセンスを割り当てるには、グローバル管理者、ライセンス管理者、またはユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2edbf-109">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="2edbf-110">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2edbf-110">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-user-in-the-admin-simplified-view"></a><span data-ttu-id="2edbf-111">管理者簡易ビューでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="2edbf-111">Add a user in the admin simplified view</span></span>

<span data-ttu-id="2edbf-112">管理センターにこのページが表示されている場合は、**管理者簡易ビュー** が表示されています。</span><span class="sxs-lookup"><span data-stu-id="2edbf-112">If you're seeing this page in the admin center, you're on the **admin simplified view**.</span></span> <span data-ttu-id="2edbf-113">以下の手順に従って、ユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-113">Follow the steps below to add a user.</span></span>

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="スクリーンショット: 簡易管理センター ビュー":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="2edbf-115"><https://admin.microsoft.com> で管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-115">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="2edbf-116"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2edbf-116">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2edbf-117"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2edbf-117">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="2edbf-118">[**別のユーザーのアカウントを作成する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-118">Select **Create an account for another person**.</span></span>
3. <span data-ttu-id="2edbf-119">[**ユーザー アカウントの追加**] ページで、サインインに使用する姓名、表示名、ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-119">On the **Add a user account** page, fill in the first and last name, display name, and username they'll use to sign in.</span></span>
4. <span data-ttu-id="2edbf-120">[**最大 5 つのメール アドレス...**] テキスト ボックスにユーザーのメール アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-120">Add the email address of the user in the **Up to 5 email addresses...** text box.</span></span> <span data-ttu-id="2edbf-121">これにより、新しいユーザーは Microsoft 365 サービスにサインインするために必要な情報を確実に取得できます。</span><span class="sxs-lookup"><span data-stu-id="2edbf-121">This will make sure the new user gets the information they need to sign into Microsoft 365 services.</span></span>
5. <span data-ttu-id="2edbf-122">この情報を保存する場合は、[**ユーザーの追加**] と [**サインイン情報のダウンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-122">Select **Add user** and **Download sign-in info** if you want to save this info.</span></span>

## <a name="watch-add-users-in-the-dashboard-view"></a><span data-ttu-id="2edbf-123">視聴: ダッシュボード ビューでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="2edbf-123">Watch: Add users in the dashboard view</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="2edbf-124">動画で使用されている手順では、ユーザーを追加するための出発点が異なっていますが、残りの手順は以下の手順と同じです。</span><span class="sxs-lookup"><span data-stu-id="2edbf-124">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a><span data-ttu-id="2edbf-125">ダッシュボード ビューで 1 人ずつユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="2edbf-125">Add users one at a time in the dashboard view</span></span>

:::image type="content" source="../../media/classic-admin-center.png" alt-text="スクリーンショット: 管理センターのダッシュボード ビュー":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="2edbf-127"><https://admin.microsoft.com> で管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-127">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="2edbf-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2edbf-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2edbf-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2edbf-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="2edbf-130">[**ユーザー**]  >  [**アクティブなユーザー**] の順に移動し、[**ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-130">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="2edbf-131">[**基本設定**] ウィンドウにユーザーの基本情報を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-131">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="2edbf-132">[**名前**] 姓、名、表示名、ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-132">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="2edbf-p106">[**ドメイン**] ユーザーのアカウントのドメインを選択します。たとえば、ユーザー名が Jakob、そのドメインが contoso.com の場合、「jakob@contoso.com」と入力してサインインします。</span><span class="sxs-lookup"><span data-stu-id="2edbf-p106">**Domain** Choose the domain for the user's account. For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="2edbf-135">[**パスワードの設定**] ユーザー用のパスワードとして、自動生成されたパスワードを使用するのか独自の強力なパスワードを作成するのかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-135">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="2edbf-p107">ユーザーは、90 日後にパスワードを変更する必要があります。または、[**初回サインイン時にこのユーザーにパスワードの変更を要求する**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="2edbf-p107">The user must change their password after 90 days. Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="2edbf-138">ユーザーが追加されたときに、パスワードをメールで送信するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-138">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="2edbf-139">[**製品ライセンスの割り当て**] ウィンドウで、ユーザーの場所と適切なライセンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-139">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="2edbf-140">利用可能なライセンスがない場合でも、ユーザーを追加し、追加のライセンスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="2edbf-140">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="2edbf-141">[**アプリ**] を展開し、アプリを選択または選択解除して、ユーザーにライセンスが付与されるアプリを制限します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-141">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="2edbf-142">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-142">Select **Next**.</span></span>
5. <span data-ttu-id="2edbf-143">[**オプションの設定**] ウィンドウで、このユーザーを管理者にする場合は [**役割**] を展開します。ユーザーに関する追加情報を入力する場合は、[**プロファイル情報**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-143">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="2edbf-144">[**次へ**] を選択し、新しいユーザーの設定を確認し、必要に応じて変更を行い、[**追加の完了**] を選択し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2edbf-144">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="2edbf-145">複数のユーザーを同時に追加する</span><span class="sxs-lookup"><span data-stu-id="2edbf-145">Add multiple users at the same time</span></span>

<span data-ttu-id="2edbf-146">複数のユーザーを同時に追加するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="2edbf-146">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="2edbf-147">**ユーザーをまとめて追加するには、スプレッドシートを使用します。**</span><span class="sxs-lookup"><span data-stu-id="2edbf-147">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="2edbf-148">「[同時に複数のユーザーを追加する](../../enterprise/add-several-users-at-the-same-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2edbf-148">See [Add several users at the same time](../../enterprise/add-several-users-at-the-same-time.md).</span></span>
- <span data-ttu-id="2edbf-p110">**アカウントの追加とライセンスの割り当てを自動化します。** 「[Microsoft 365 PowerShell を使用したユーザー アカウントの作成](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md)」を参照してください。この方法は、Windows PowerShell コマンドレットについて詳しい知識のある場合に選んでください。</span><span class="sxs-lookup"><span data-stu-id="2edbf-p110">**Automate adding accounts and assigning licenses.** See [Create user accounts with Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="2edbf-p111">**ActiveDirectory を使用している場合** [Microsoft 365 のディレクトリ同期を設定します](../../enterprise/set-up-directory-synchronization.md)。Azure AD Connect ツールを使用し、Microsoft 365 で Active Directory ユーザー アカウント (およびその他の Active Directory オブジェクト) を複製します。同期では、ユーザー アカウントのみが追加されます。同期されているユーザーがメールとその他の Office アプリを使用するには、そのユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2edbf-p111">**Using ActiveDirectory?** [Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md). Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365. The sync only adds the user accounts. You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="2edbf-157">**Exchange Server から移行する場合**</span><span class="sxs-lookup"><span data-stu-id="2edbf-157">**Migrating from Exchange?**</span></span> <span data-ttu-id="2edbf-158">「[複数のメール アカウントを Office 365 に移行する方法](/Exchange/mailbox-migration/mailbox-migration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2edbf-158">See [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="2edbf-159">カットオーバー、段階的方法、またはハイブリッド Exchange による方法のいずれかを使って、複数のメールボックスを Microsoft 365 に移行するときは、移行の一部としてユーザーが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2edbf-159">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="2edbf-160">移行では、ユーザー アカウントのみが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2edbf-160">The migration only adds the user accounts.</span></span> <span data-ttu-id="2edbf-161">ユーザーがメールとその他の Office アプリを使用するには、そのユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2edbf-161">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="2edbf-162">ユーザーにライセンスを割り当てない場合、30 日間の猶予期間が過ぎるとユーザーのメールボックスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="2edbf-162">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="2edbf-163">Microsoft 365 管理センターで[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2edbf-163">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2edbf-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="2edbf-164">Next steps</span></span>

<span data-ttu-id="2edbf-165">ユーザーを追加すると、Microsoft からメール通知が届きます。</span><span class="sxs-lookup"><span data-stu-id="2edbf-165">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="2edbf-166">メールには、ユーザーが Microsoft 365 にサインインするための Microsoft 365 のユーザー ID とパスワードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2edbf-166">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="2edbf-167">新しいパスワードは、通常のプロセスを使用して通知してください。</span><span class="sxs-lookup"><span data-stu-id="2edbf-167">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="2edbf-168">新しいユーザーと「[従業員のクイック スタート ガイド](../../business-video/employee-quick-setup.md)」を共有し、ユーザーが「[PC または Mac に Office アプリをダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2edbf-168">Share the [Employee quickstart guide](../../business-video/employee-quick-setup.md) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="2edbf-169">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="2edbf-169">Related content</span></span>

<span data-ttu-id="2edbf-170">[Microsoft 365 に新しい従業員を追加する](add-new-employee.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="2edbf-170">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="2edbf-171">[同時に複数のユーザーを Microsoft 365 に追加する](../../enterprise/add-several-users-at-the-same-time.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="2edbf-171">[Add several users at the same time to Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (article)</span></span>\
<span data-ttu-id="2edbf-172">[Microsoft 365 のユーザーを復元する](restore-user.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="2edbf-172">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="2edbf-173">[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="2edbf-173">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="2edbf-174">[組織からユーザーを削除する](delete-a-user.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="2edbf-174">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
