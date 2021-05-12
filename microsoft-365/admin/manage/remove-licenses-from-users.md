---
title: ユーザーからライセンスの割り当てを解除する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: ユーザー アカウントからのライセンスの割り当てを解除する方法について学習します。
ms.date: 07/01/2020
ms.openlocfilehash: 6f2cbf65e1d6a38a4b1ed00976d4dd473d7331e9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332416"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="7f595-103">ユーザーからライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="7f595-103">Unassign licenses from users</span></span>

<span data-ttu-id="7f595-104">ユーザーからのライセンスの割り当てを解除するには、[アクティブなユーザー] ページまたは [ライセンス] ページ **を使用** します。</span><span class="sxs-lookup"><span data-stu-id="7f595-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="7f595-105">使用する方法は、特定のユーザーからの製品ライセンスの割り当てを解除するか、特定の製品からのユーザー ライセンスの割り当てを解除するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7f595-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="7f595-106">管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7f595-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="7f595-107">[セルフサービス購入サブスクリプションを引き継ぐと](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7f595-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7f595-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="7f595-108">Before you begin</span></span>

- <span data-ttu-id="7f595-109">ライセンスの割り当てを解除するには、グローバル、ライセンス、ユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f595-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="7f595-110">詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f595-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="7f595-111">[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="7f595-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="7f595-112">ライセンスが [割り当てられたユーザー](../add-users/delete-a-user.md) アカウントを削除して、ライセンスを他のユーザーが利用できるようすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7f595-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="7f595-113">ユーザー アカウントを削除すると、そのユーザーのライセンスをすぐに他のユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="7f595-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="7f595-114">[ライセンス] ページを使用してライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="7f595-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="7f595-115">[ライセンス] ページ **を使用して** ライセンスの割り当てを解除すると、最大 20 人のユーザーの特定の製品のライセンスの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="7f595-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7f595-116">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7f595-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7f595-117"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**課金**] > [**ライセンス**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7f595-117">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7f595-118"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**課金**] > [**ライセンス**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7f595-118">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="7f595-119">ライセンスの割り当てを解除する製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="7f595-120">ライセンスの割り当てを解除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="7f595-121">[ライセンス **の割り当て解除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7f595-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="7f595-122">[ライセンスの **割り当て解除] ボックス** で、[割り当 **て解除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7f595-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="7f595-123">[アクティブ ユーザー] ページを使用してライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="7f595-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="7f595-124">[アクティブ ユーザー] **ページを使用して** ライセンスの割り当てを解除すると、ユーザーからの製品ライセンスの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="7f595-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="7f595-125">1 人のユーザーからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="7f595-125">Unassign licenses from one user</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="7f595-126">管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7f595-127"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**課金**] > [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-127">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7f595-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**課金**] > [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="7f595-129">ライセンスの割り当てを解除するユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="7f595-130">右側のウィンドウで、[**ライセンスとアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="7f595-131">[ライセンス **] セクションを展開** し、割り当てを解除するライセンスのボックスをオフにして、[変更の保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7f595-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="7f595-132">複数のユーザーからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="7f595-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7f595-133">管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-133">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7f595-134"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**課金**] > [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7f595-135"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**課金**] > [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-135">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="7f595-136">ライセンスの割り当てを解除するユーザーの名前の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="7f595-137">上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-137">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="7f595-138">[**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てを置き換える**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7f595-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="7f595-139">[既存の製品の **置き** 換え] ウィンドウの下部で、[選択したユーザーからすべての製品ライセンスを削除する]チェック ボックスをオンにし、[閉じる] を選択 \> **します**。</span><span class="sxs-lookup"><span data-stu-id="7f595-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="7f595-140">ライセンスを削除すると、ユーザーのデータは何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="7f595-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="7f595-141">ユーザーからライセンスが削除されると、そのアカウントに関連付けられたデータは 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="7f595-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="7f595-142">30 日間の猶予期間の後、データは削除され、回復できません。</span><span class="sxs-lookup"><span data-stu-id="7f595-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="7f595-143">ユーザーが OneDrive for Business Microsoft 365管理センターから削除されたか、Active Directory 同期によって削除されない限り、OneDrive for Businessに保存されたファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="7f595-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="7f595-144">詳細については、「保持と[削除OneDriveを参照してください](/onedrive/retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="7f595-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="7f595-145">ライセンスが削除されると、ユーザーのメールボックスは、コンテンツ検索や電子情報開示ツールなどの電子情報開示ツールを使用してAdvanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="7f595-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="7f595-146">詳細については、「コンテンツ検索」の「切断されたメールボックスまたはライセンス解除されたメールボックスを検索する」[を参照Microsoft 365。](../../compliance/content-search.md)</span><span class="sxs-lookup"><span data-stu-id="7f595-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="7f595-147">Office 365 Enterprise E3 のような Enterprise サブスクリプションがある場合、Exchange Online を使用すると、非アクティブなメールボックスを使用して、削除されたユーザー アカウントのメールボックス データを[保持できます](../../compliance/inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7f595-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="7f595-148">詳細については、「アクティブでないメールボックスを作成して管理する」を参照[Exchange Online。](../../compliance/create-and-manage-inactive-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="7f595-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="7f595-149">ライセンスが削除された後でユーザーの Microsoft 365 データへのアクセスをブロックする方法、および後でデータにアクセスする方法については、「元従業員を削除する」を[参照してください](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="7f595-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="7f595-150">ユーザーのライセンスを削除し、Office アプリがまだインストールされている場合は、Office でライセンス[](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)認証されていない製品とライセンス認証エラーが表示され、Office アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f595-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7f595-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="7f595-151">Next steps</span></span>

<span data-ttu-id="7f595-152">未使用のライセンスを他のユーザー[](../../managed-desktop/get-started/assign-licenses.md)に再割り当てしない場合は、[](../../commerce/licenses/buy-licenses.md)必要以上に多くのライセンスを支払わない状態でサブスクリプションからライセンスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="7f595-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="7f595-153">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="7f595-153">Related content</span></span>

<span data-ttu-id="7f595-154">[サブスクリプションからライセンスを削除](../../commerce/licenses/buy-licenses.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="7f595-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="7f595-155">[ユーザーにライセンスを割り当てる](assign-licenses-to-users.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="7f595-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="7f595-156">[ビジネス向けサブスクリプションとライセンスMicrosoft 365理解](../../commerce/licenses/subscriptions-and-licenses.md)する (記事)</span><span class="sxs-lookup"><span data-stu-id="7f595-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
