---
title: アカウントの使用を停止する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Microsoft を使用してアカウントを終了する方法について説明します。
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376319"
---
# <a name="close-your-account"></a><span data-ttu-id="addd2-103">アカウントの使用を停止する</span><span class="sxs-lookup"><span data-stu-id="addd2-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="addd2-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="addd2-104">The admin center is changing.</span></span> <span data-ttu-id="addd2-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="addd2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="addd2-106">Microsoft でのアカウントの使用を停止すると、アカウントに関連するすべての情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="addd2-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="addd2-107">この情報には、サブスクリプション、ライセンス、支払方法、ユーザー、ユーザー データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="addd2-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="addd2-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="addd2-108">Before you begin</span></span>

<span data-ttu-id="addd2-109">このプロセスを開始する前に、保持する必要があるすべてのデータをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="addd2-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="addd2-110">この記事に記載されているタスクを実行するには、グローバルまたは課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="addd2-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="addd2-111">詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="addd2-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="addd2-112">手順 1: ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="addd2-112">Step 1: Delete users</span></span>

<span data-ttu-id="addd2-113">1人のグローバル管理者以外のすべてのユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="addd2-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="addd2-114">グローバル管理者は、アカウントを終了するための手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="addd2-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="addd2-115">このプロセスの終了時にディレクトリを削除するには、その前に他のすべてのユーザーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="addd2-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="addd2-116">ユーザーがオンプレミスから同期されている場合は、まず sync をオフにしてから、Azure portal または Azure PowerShell コマンドレットを使用してクラウドディレクトリ内のユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="addd2-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="addd2-117">ユーザーを削除するには、「 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: 1 人</a>以上のユーザーを削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="addd2-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="addd2-118"><a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell コマンドレットを使用して、ユーザーを一括で削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="addd2-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="addd2-119">Microsoft Azure Active Directory (Azure AD) と同期する Active Directory を組織で使用している場合は、代わりに Active Directory からユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="addd2-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="addd2-120">手順については、「 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Azure Active Directory でユーザーを一括削除</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="addd2-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="addd2-121">手順 2: すべてのアクティブなサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="addd2-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="addd2-122">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="addd2-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="addd2-123">[ **製品** ] タブで、アクティブなサブスクリプションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="addd2-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="addd2-124">**その他の操作** (3 つのドット) を選択してから、**[このサブスクリプションをキャンセルする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="addd2-125">**[サブスクリプションのキャンセル]** ウィンドウで、キャンセルする理由を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="addd2-126">必要に応じて、フィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="addd2-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="addd2-127">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-127">Select **Save**.</span></span>
5. <span data-ttu-id="addd2-128">手順 1 ~ 4 を繰り返して、すべてのアクティブなサブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="addd2-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="addd2-129">手順 3: 無効になっているすべてのサブスクリプションを削除する</span><span class="sxs-lookup"><span data-stu-id="addd2-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="addd2-130">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="addd2-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="addd2-131">[ **製品** ] タブで、無効になっているサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="addd2-132">[サブスクリプションの詳細] ページの [ **サブスクリプションと支払いの設定** ] セクションで、[ **サブスクリプションの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="addd2-133">[ **サブスクリプションの削除** ] ウィンドウで、[ **サブスクリプションの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="addd2-134">[ **サブスクリプションの削除** ] ダイアログボックスで、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="addd2-135">無効にされた各サブスクリプションについて、すべてのサブスクリプションが削除されるまで手順 3 ~ 5 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="addd2-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="addd2-136">無効化されたサブスクリプションをすぐに削除できない場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">サポートに連絡してください</a>。</span><span class="sxs-lookup"><span data-stu-id="addd2-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="addd2-137">手順 4: 多要素認証を無効にする</span><span class="sxs-lookup"><span data-stu-id="addd2-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="addd2-138">グローバル管理者アカウントを使用して、管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="addd2-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="addd2-139">所有している役割を確認するには、「 [組織の管理者の役割を確認](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="addd2-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="addd2-140">[ユーザーの **Users**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="addd2-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="addd2-141">[ **多要素認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="addd2-142">[多要素認証] ページで、現在使用中のグローバル管理者アカウント以外のすべてのアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="addd2-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="addd2-143"><a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell を使用して、複数のユーザーに対して多要素認証を無効に</a>することもできます。</span><span class="sxs-lookup"><span data-stu-id="addd2-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="addd2-144">手順 5: Azure Active Directory のディレクトリを削除する</span><span class="sxs-lookup"><span data-stu-id="addd2-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="addd2-145">グローバル管理者アカウントを使用して、 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 管理センター</a> にサインインします。</span><span class="sxs-lookup"><span data-stu-id="addd2-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="addd2-146">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="addd2-147">削除する組織に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="addd2-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="addd2-148">[ **テナントの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="addd2-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="addd2-149">組織が1つ以上のチェックに失敗した場合は、チェックを通過する方法に関する詳細情報へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="addd2-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="addd2-150">すべてのチェックに合格したら、[ **削除** ] を選択してプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="addd2-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="addd2-151">この最後の手順を完了すると、Microsoft とのアカウントが閉じられ、削除されます。</span><span class="sxs-lookup"><span data-stu-id="addd2-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>