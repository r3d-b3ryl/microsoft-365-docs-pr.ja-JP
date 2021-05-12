---
title: ユーザーにライセンスを割り当てる
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: ユーザーにライセンスを割り当てる方法を説明します。
ms.date: 04/26/2021
ms.openlocfilehash: ef8169658c6aef03cf8ff0cf9714c980ce63b060
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332488"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="b1f5f-103">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b1f5f-103">Assign licenses to users</span></span>

<span data-ttu-id="b1f5f-104">[**アクティブなユーザー**] ページまたは [**ライセンス**] ページで、ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="b1f5f-105">使用する方法は、製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f5f-106">管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="b1f5f-107">[セルフサービス購入サブスクリプションを引き継ぐと](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="b1f5f-108">[ユーザーを追加すると同時にライセンスを割り当てる方法を説明します](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b1f5f-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="b1f5f-109">Before you begin</span></span>

- <span data-ttu-id="b1f5f-110">ライセンスを割り当てるには、グローバル、ライセンス、またはユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="b1f5f-111">詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="b1f5f-112">[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="b1f5f-113">グループ ベースのライセンスを使用するには、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/users-groups-roles/licensing-groups-assign)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="b1f5f-114">Sway などの一部のサービスでは、ユーザーに自動的に割り当てられるため、個別に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="b1f5f-115">[ライセンス] ページを使用して、ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b1f5f-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="b1f5f-116">[**ライセンス**] ページを使用してライセンスを割り当てる場合、特定の製品のライセンスを最大 20 人のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="b1f5f-117">[**ライセンス**] ページに、サブスクリプションがあるすべての製品のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="b1f5f-118">また、各製品のライセンスの総数、割り当てられているライセンスの数、および使用可能なライセンスの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b1f5f-119">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b1f5f-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**課金**] > [**ライセンス**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b1f5f-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**課金**] > [**ライセンス**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="b1f5f-122">製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-122">Select a product.</span></span>
3. <span data-ttu-id="b1f5f-123">製品の詳細ページで、[**ライセンスの割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="b1f5f-124">[**ユーザーにライセンスを割り当てる**] ウィンドウで、名前の入力を開始し、結果から名前を選択して一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="b1f5f-125">最大 20 人のユーザーを同時に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="b1f5f-126">特定のアイテムへのアクセス権を割り当てまたは削除するには、[**アプリとサービスをオンまたはオフにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="b1f5f-127">完了したら、**[割り当て]** を選択し、**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="b1f5f-128">競合がある場合、メッセージが表示され、問題の内容と修正方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="b1f5f-129">たとえば、競合するサービスを含むライセンスを選択した場合、各ライセンスに含まれるサービスを確認して再試行するように伝えるエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="b1f5f-130">ユーザーがアクセスできるアプリとサービスを変更する</span><span class="sxs-lookup"><span data-stu-id="b1f5f-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b1f5f-131">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-131">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b1f5f-132"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**課金**] > [**ライセンス**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b1f5f-133"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**課金**] > [**ライセンス**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-133">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="b1f5f-134">[**ライセンス**] ページで、特定のユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="b1f5f-135">右側のウィンドウで、アクセスを許可または削除するアプリとサービスを選択または選択解除します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="b1f5f-136">完了したら、[**保存**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="b1f5f-137">[アクティブなユーザー] ページでライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b1f5f-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="b1f5f-138">[**アクティブなユーザー**] ページを使用してライセンスを割り当てる場合、ユーザー ライセンスを製品に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="b1f5f-139">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b1f5f-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b1f5f-140">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b1f5f-141"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**課金**] > [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-141">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b1f5f-142"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**課金**] > [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-142">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="b1f5f-143">ライセンスを割り当てるユーザー名の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="b1f5f-144">上部で [**その他のオプション (...)**] を選択し、[**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-144">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="b1f5f-145">[**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンス割り当てに追加する**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-145">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="b1f5f-146">[**既存の製品に追加**] ウィンドウで、選択したユーザーに付与するライセンスのトグルを [**オン**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-146">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="b1f5f-147">既定では、それらのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-147">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="b1f5f-148">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-148">You can limit which services are available to the users.</span></span> <span data-ttu-id="b1f5f-149">ユーザーに設定しないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-149">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="b1f5f-150">ウィンドウの下部で、[**追加**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-150">At the bottom of the pane, select **Add** \> **Close**.</span></span>  


> [!NOTE]
> <span data-ttu-id="b1f5f-151">多数のユーザーにライセンスを割り当てる場合は、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/enterprise-users/licensing-groups-assign)」を使用します</span><span class="sxs-lookup"><span data-stu-id="b1f5f-151">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="b1f5f-152">1 人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b1f5f-152">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b1f5f-153">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b1f5f-154"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**課金**] > [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-154">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b1f5f-155"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**課金**] > [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-155">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="b1f5f-156">ライセンスを割り当てるユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-156">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="b1f5f-157">右側のウィンドウで、[**ライセンスとアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-157">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="b1f5f-158">[**ライセンス**] セクションを展開し、割り当てるライセンスのボックスを選択して、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-158">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="b1f5f-159">ゲスト ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b1f5f-159">Assign a license to a guest user</span></span>

<span data-ttu-id="b1f5f-160">ゲスト ユーザーを招待して、Azure Active Directory 管理センターで組織と共同作業できます。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-160">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="b1f5f-161">ゲスト ユーザーの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](/azure/active-directory/external-identities/what-is-b2b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-161">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="b1f5f-162">ゲスト ユーザーがいない場合は、「[クイック スタート: Azure Portal のディレクトリにゲスト ユーザーを追加する](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-162">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1f5f-163">次の手順を実行するには、全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-163">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="b1f5f-164"><a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="b1f5f-165">ナビゲーション ウィンドウで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-165">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="b1f5f-166">**[ユーザー | すべてのユーザー (プレビュー)]** ページで **[フィルターの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-166">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="b1f5f-167">**[フィールドの選択**] メニューから **[ユーザーの種類]** を選択して、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-167">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="b1f5f-168">次のメニューから **[ゲスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-168">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="b1f5f-169">結果のリストから、ライセンスが必要なユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-169">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="b1f5f-170">**[管理]** で **[ライセンス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-170">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="b1f5f-171">**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-171">Select **Assignments**.</span></span>
9. <span data-ttu-id="b1f5f-172">**[ライセンスの割り当ての更新]** ページで、ライセンスを割り当てる製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-172">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="b1f5f-173">右側で、ゲスト ユーザーにアクセスを許可しないサービスのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-173">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="b1f5f-174">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-174">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1f5f-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="b1f5f-175">Next steps</span></span>

<span data-ttu-id="b1f5f-176">ユーザーがまだ Office アプリをインストールしていない場合は、「[従業員クイック スタート ガイド](../../business-video/employee-quick-setup.md)」をユーザーと共有して、ユーザーが「[PC または Mac に Microsoft 365 または Office 2019 をダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1f5f-176">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="b1f5f-177">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="b1f5f-177">Related content</span></span>

<span data-ttu-id="b1f5f-178">[サブスクリプションとライセンスを理解する](../../commerce/licenses/subscriptions-and-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="b1f5f-178">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="b1f5f-179">[ユーザーからライセンスの割り当てを解除する](remove-licenses-from-users.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="b1f5f-179">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="b1f5f-180">[スクリプションのライセンスを購入または削除する](../../commerce/licenses/buy-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="b1f5f-180">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
