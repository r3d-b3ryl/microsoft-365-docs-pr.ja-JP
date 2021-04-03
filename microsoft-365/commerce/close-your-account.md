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
description: Microsoft でアカウントを閉じる方法について説明します。
ms.openlocfilehash: 0ee0a649a9adb93ecdbb1cd9dbedbc04dfb46ba0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579748"
---
# <a name="close-your-account"></a><span data-ttu-id="72d7f-103">アカウントの使用を停止する</span><span class="sxs-lookup"><span data-stu-id="72d7f-103">Close your account</span></span>

<span data-ttu-id="72d7f-104">Microsoft でのアカウントの使用を停止すると、アカウントに関連するすべての情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="72d7f-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="72d7f-105">この情報には、サブスクリプション、ライセンス、支払方法、ユーザー、ユーザー データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="72d7f-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="72d7f-106">開始する前に</span><span class="sxs-lookup"><span data-stu-id="72d7f-106">Before you begin</span></span>

<span data-ttu-id="72d7f-107">このプロセスを開始する前に、保持する必要があるすべてのデータをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="72d7f-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="72d7f-108">この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="72d7f-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="72d7f-109">詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72d7f-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="72d7f-110">手順 1: ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="72d7f-110">Step 1: Delete users</span></span>

<span data-ttu-id="72d7f-111">1 人のグローバル管理者を除くすべてのユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="72d7f-112">グローバル管理者は、アカウントを閉じる手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="72d7f-113">このプロセスの最後にディレクトリを削除する前に、他のすべてのユーザーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72d7f-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="72d7f-114">ユーザーがオンプレミスから同期されている場合は、まず同期をオフにしてから、Azure portal または Azure PowerShell コマンドレットを使用してクラウド ディレクトリ内のユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="72d7f-115">ユーザーを削除するには、「ユーザー管理管理者 <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">: 1 人または複数のユーザーを削除する」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="72d7f-115">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="72d7f-116"><a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser PowerShell コマンドレット</a>を使用して、ユーザーを一括で削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="72d7f-116">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="72d7f-117">組織で Microsoft Azure Active Directory (Azure Active Directory )と同期する Active Directory を使用している場合は、代AD Active Directory からユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="72d7f-118">手順については <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">、「Azure Active Directory のユーザーを一括削除する」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="72d7f-118">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="72d7f-119">手順 2: すべてのアクティブなサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="72d7f-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="72d7f-120">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="72d7f-121">[製品 **] タブ** で、アクティブなサブスクリプションを探します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="72d7f-122">**[その他の操作]** (3 つのドット) を選択してから、**[サブスクリプションのキャンセル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="72d7f-123">**[サブスクリプションのキャンセル]** ウィンドウで、キャンセルする理由を選択します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="72d7f-124">必要に応じて、フィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="72d7f-125">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-125">Select **Save**.</span></span>
5. <span data-ttu-id="72d7f-126">手順 1 ~ 4 を繰り返して、アクティブなすべてのサブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="72d7f-127">手順 3: 無効なすべてのサブスクリプションを削除する</span><span class="sxs-lookup"><span data-stu-id="72d7f-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="72d7f-128">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="72d7f-129">[製品 **] タブ** で、無効なサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="72d7f-130">[サブスクリプションの詳細] ページの [ **サブスクリプションと支払** いの設定] セクションで、[サブスクリプションの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72d7f-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="72d7f-131">[サブスクリプションの **削除] ウィンドウで** 、[サブスクリプションの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72d7f-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="72d7f-132">[サブスクリプションの **削除] ダイアログ ボックス** で、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72d7f-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="72d7f-133">無効にしたサブスクリプションごとに、すべてのサブスクリプションが削除されるまで手順 3 ~ 5 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="72d7f-134">無効になっているサブスクリプションを直ちに削除できない場合は、サポート <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">にお問い合わせください</a></span><span class="sxs-lookup"><span data-stu-id="72d7f-134">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="72d7f-135">手順 4: 多要素認証を無効にする</span><span class="sxs-lookup"><span data-stu-id="72d7f-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="72d7f-136">グローバル管理者アカウントを使用して管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="72d7f-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="72d7f-137">持っている役割を確認するには、「組織内の [管理者の役割を確認する」を参照してください](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="72d7f-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="72d7f-138">[ユーザーのアクティブ **なユーザー**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">] ページに移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="72d7f-139">[ **多要素認証] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72d7f-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="72d7f-140">多要素認証ページで、現在使用しているグローバル管理者アカウントを除くすべてのアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="72d7f-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="72d7f-141">PowerShell を <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">使用して、複数のユーザーの多要素認証を無効にできます</a>。</span><span class="sxs-lookup"><span data-stu-id="72d7f-141">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="72d7f-142">手順 5: Azure Active Directory のディレクトリを削除する</span><span class="sxs-lookup"><span data-stu-id="72d7f-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="72d7f-143">グローバル管理者アカウントで <a href="https://aad.portal.azure.com/" target="_blank">Azure AD管理センター</a> にサインインします。</span><span class="sxs-lookup"><span data-stu-id="72d7f-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="72d7f-144">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="72d7f-145">削除する組織に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="72d7f-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="72d7f-146">[テナント **の削除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72d7f-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="72d7f-147">組織で 1 つ以上のチェックに失敗した場合は、チェックに合格する方法の詳細へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72d7f-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="72d7f-148">すべてのチェックに合格したら、[削除] **を選択して** プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="72d7f-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="72d7f-149">この最後の手順を完了すると、Microsoft のアカウントは閉じ、削除されます。</span><span class="sxs-lookup"><span data-stu-id="72d7f-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>