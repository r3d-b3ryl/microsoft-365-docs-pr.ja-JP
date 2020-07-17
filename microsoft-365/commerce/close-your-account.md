---
title: アカウントの使用を停止する
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Microsoft を使用してアカウントを終了する方法について説明します。
ms.openlocfilehash: a92b9f2053d9acf4e8233bee7a42047f51288943
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898923"
---
# <a name="close-your-account"></a><span data-ttu-id="75fd7-103">アカウントの使用を停止する</span><span class="sxs-lookup"><span data-stu-id="75fd7-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="75fd7-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="75fd7-104">The admin center is changing.</span></span> <span data-ttu-id="75fd7-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fd7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="75fd7-106">Microsoft でのアカウントの使用を停止すると、アカウントに関連するすべての情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="75fd7-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="75fd7-107">この情報には、サブスクリプション、ライセンス、支払方法、ユーザー、ユーザー データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="75fd7-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="75fd7-108">このプロセスを開始する前に、保持する必要のあるデータを必ずバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="75fd7-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="75fd7-109">手順 1: ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="75fd7-109">Step 1: Delete users</span></span>

<span data-ttu-id="75fd7-110">アカウントを閉じる手順を完了した1人のグローバル管理者を除くすべてのユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="75fd7-111">このプロセスの終了時にディレクトリを削除するには、その前に他のすべてのユーザーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fd7-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="75fd7-112">ユーザーがオンプレミスから同期されている場合は、まず sync をオフにしてから、Azure portal または Azure PowerShell コマンドレットを使用してクラウドディレクトリ内のユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="75fd7-113">ユーザーを削除するには、「 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: 1 人</a>以上のユーザーを削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fd7-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="75fd7-114"><a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell コマンドレットを使用して、ユーザーを一括で削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="75fd7-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="75fd7-115">組織が Azure AD と同期する Active Directory を使用している場合は、代わりに Active Directory からユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="75fd7-116">手順については、「 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Azure Active Directory でユーザーを一括削除</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fd7-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="75fd7-117">手順 2: すべてのアクティブなサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="75fd7-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="75fd7-118">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="75fd7-119">購読リストが**表**形式の場合は、右側の [**カード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="75fd7-120">アクティブなサブスクリプションを検索し、[**設定 & の操作**] セクションで、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="75fd7-121">画面の指示に従って、プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="75fd7-122">手順 1 ~ 4 を繰り返して、すべてのアクティブなサブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="75fd7-123">手順 3: 無効になっているすべてのサブスクリプションを削除する</span><span class="sxs-lookup"><span data-stu-id="75fd7-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="75fd7-124">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="75fd7-125">購読リストが**表**形式の場合は、右側の [**カード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="75fd7-126">[**サブスクリプションの状態**] の横で、[**無効**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="75fd7-127">無効になっているサブスクリプションを検索し、[**設定 & の操作**] セクションで、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="75fd7-128">[**サブスクリプションの削除**] ダイアログボックスで、[**影響について理解**しています] チェックボックスをオンにして、[**サブスクリプションの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="75fd7-129">無効化された各サブスクリプションについて、すべてのサブスクリプションが削除されるまで、ステップ4と5を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="75fd7-130">手順 4: 多要素認証を無効にする</span><span class="sxs-lookup"><span data-stu-id="75fd7-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="75fd7-131">管理センターで、[**ユーザー**の  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="75fd7-132">[**多要素認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="75fd7-133">[多要素認証] ページで、現在使用中のグローバル管理者アカウント以外のすべてのアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="75fd7-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="75fd7-134"><a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell を使用して、複数のユーザーに対して多要素認証を無効に</a>することもできます。</span><span class="sxs-lookup"><span data-stu-id="75fd7-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="75fd7-135">手順 5: Azure Active Directory のディレクトリを削除する</span><span class="sxs-lookup"><span data-stu-id="75fd7-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="75fd7-136">グローバル管理者アカウントを使用して、 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="75fd7-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="75fd7-137">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="75fd7-138">削除するディレクトリに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="75fd7-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="75fd7-139">[**ディレクトリの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="75fd7-140">ディレクトリが1つ以上のチェックに失敗した場合は、チェックを通過する方法に関する詳細情報へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75fd7-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="75fd7-141">すべてのチェックに合格したら、[**削除**] を選択してプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="75fd7-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="75fd7-142">この最後の手順を完了すると、Microsoft とのアカウントが閉じられ、削除されます。</span><span class="sxs-lookup"><span data-stu-id="75fd7-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
