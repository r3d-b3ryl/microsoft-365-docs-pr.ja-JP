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
ms.custom: ''
search.appverid:
- MET150
description: Microsoft を使用してアカウントを終了する方法について説明します。
ms.openlocfilehash: b71cfe8246b5e3e9471c76cf8043bad52840f194
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942855"
---
# <a name="close-your-account"></a><span data-ttu-id="85e7e-103">アカウントの使用を停止する</span><span class="sxs-lookup"><span data-stu-id="85e7e-103">Close your account</span></span>

<span data-ttu-id="85e7e-104">Microsoft でのアカウントの使用を停止すると、アカウントに関連するすべての情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="85e7e-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="85e7e-105">この情報には、サブスクリプション、ライセンス、支払方法、ユーザー、ユーザー データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="85e7e-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="85e7e-106">このプロセスを開始する前に、保持する必要のあるデータを必ずバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="85e7e-106">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="85e7e-107">手順 1: ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="85e7e-107">Step 1: Delete users</span></span>

<span data-ttu-id="85e7e-108">アカウントを閉じる手順を完了した1人のグローバル管理者を除くすべてのユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-108">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="85e7e-109">このプロセスの終了時にディレクトリを削除するには、その前に他のすべてのユーザーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e7e-109">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="85e7e-110">ユーザーがオンプレミスから同期されている場合は、まず sync をオフにしてから、Azure portal または Azure PowerShell コマンドレットを使用してクラウドディレクトリ内のユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-110">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="85e7e-111">ユーザーを削除するには、「 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: 1 人</a>以上のユーザーを削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e7e-111">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="85e7e-112"><a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell コマンドレットを使用して、ユーザーを一括で削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="85e7e-112">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="85e7e-113">組織が Azure AD と同期する Active Directory を使用している場合は、代わりに Active Directory からユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-113">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="85e7e-114">手順については、「 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Azure Active Directory でユーザーを一括削除</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e7e-114">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="85e7e-115">手順 2: すべてのアクティブなサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="85e7e-115">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="85e7e-116">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="85e7e-117">購読リストが**表**形式の場合は、右側の [**カード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-117">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="85e7e-118">アクティブなサブスクリプションを検索し、[**設定 & の操作**] セクションで、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-118">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="85e7e-119">画面の指示に従って、プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-119">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="85e7e-120">手順 1 ~ 4 を繰り返して、すべてのアクティブなサブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-120">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="85e7e-121">手順 3: 無効になっているすべてのサブスクリプションを削除する</span><span class="sxs-lookup"><span data-stu-id="85e7e-121">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="85e7e-122">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="85e7e-123">購読リストが**表**形式の場合は、右側の [**カード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-123">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="85e7e-124">[**サブスクリプションの状態**] の横で、[**無効**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-124">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="85e7e-125">無効になっているサブスクリプションを検索し、[**設定 & の操作**] セクションで、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-125">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="85e7e-126">[**サブスクリプションの削除**] ダイアログボックスで、[**影響について理解**しています] チェックボックスをオンにして、[**サブスクリプションの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-126">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="85e7e-127">無効化された各サブスクリプションについて、すべてのサブスクリプションが削除されるまで、ステップ4と5を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-127">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="85e7e-128">手順 4: 多要素認証を無効にする</span><span class="sxs-lookup"><span data-stu-id="85e7e-128">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="85e7e-129">管理センターで、[**ユーザー** > の<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="85e7e-130">[**多要素認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-130">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="85e7e-131">[多要素認証] ページで、現在使用中のグローバル管理者アカウント以外のすべてのアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="85e7e-131">On the multi-factor authentication page, disable all accounts except for the global admin account that you’re currently using.</span></span>

<span data-ttu-id="85e7e-132"><a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell を使用して、複数のユーザーに対して多要素認証を無効に</a>することもできます。</span><span class="sxs-lookup"><span data-stu-id="85e7e-132">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="85e7e-133">手順 5: Azure Active Directory のディレクトリを削除する</span><span class="sxs-lookup"><span data-stu-id="85e7e-133">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="85e7e-134">グローバル管理者アカウントを使用して、 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="85e7e-134">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="85e7e-135">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-135">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="85e7e-136">削除するディレクトリに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="85e7e-136">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="85e7e-137">[**ディレクトリの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-137">Select **Delete directory**.</span></span>

5. <span data-ttu-id="85e7e-138">ディレクトリが1つ以上のチェックに失敗した場合は、チェックを通過する方法に関する詳細情報へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="85e7e-138">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="85e7e-139">すべてのチェックに合格したら、[**削除**] を選択してプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="85e7e-139">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="85e7e-140">この最後の手順を完了すると、Microsoft とのアカウントが閉じられ、削除されます。</span><span class="sxs-lookup"><span data-stu-id="85e7e-140">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
