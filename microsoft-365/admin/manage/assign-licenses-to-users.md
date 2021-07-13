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
- AdminTemplateSet
search.appverid: MET150
description: 製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって、ライセンスを割り当てます。
ms.date: 04/26/2021
ms.openlocfilehash: 987572ae15ffdf6d2042c6e54eba586cd39ebcb9
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393717"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="cdcea-103">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cdcea-103">Assign licenses to users</span></span>

<span data-ttu-id="cdcea-104">[**アクティブなユーザー**] ページまたは [**ライセンス**] ページで、ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="cdcea-105">使用する方法は、製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cdcea-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="cdcea-106">管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cdcea-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="cdcea-107">[セルフサービス購入サブスクリプションを引き継ぐと](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="cdcea-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="cdcea-108">[ユーザーを追加すると同時にライセンスを割り当てる方法を説明します](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="cdcea-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cdcea-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="cdcea-109">Before you begin</span></span>

- <span data-ttu-id="cdcea-110">ライセンスを割り当てるには、グローバル、ライセンス、またはユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdcea-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="cdcea-111">詳細については、「[Microsoft 365 の管理者の役割](../add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdcea-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="cdcea-112">[Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-112">You can [assign Microsoft 365 licenses to user accounts with PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="cdcea-113">グループ ベースのライセンスを使用するには、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/users-groups-roles/licensing-groups-assign)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdcea-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="cdcea-114">Sway などの一部のサービスでは、ユーザーに自動的に割り当てられるため、個別に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cdcea-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="cdcea-115">[ライセンス] ページを使用して、ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cdcea-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="cdcea-116">[**ライセンス**] ページを使用してライセンスを割り当てる場合、特定の製品のライセンスを最大 20 人のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="cdcea-117">[**ライセンス**] ページに、サブスクリプションがあるすべての製品のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="cdcea-118">また、各製品のライセンスの総数、割り当てられているライセンスの数、および使用可能なライセンスの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cdcea-119">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="cdcea-120">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="cdcea-121">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="cdcea-122">製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-122">Select a product.</span></span>
3. <span data-ttu-id="cdcea-123">製品の詳細ページで、[**ライセンスの割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="cdcea-124">[**ユーザーにライセンスを割り当てる**] ウィンドウで、名前の入力を開始し、結果から名前を選択して一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="cdcea-125">最大 20 人のユーザーを同時に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="cdcea-126">特定のアイテムへのアクセス権を割り当てまたは削除するには、[**アプリとサービスをオンまたはオフにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="cdcea-127">完了したら、**[割り当て]** を選択し、**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="cdcea-128">競合がある場合、メッセージが表示され、問題の内容と修正方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="cdcea-129">たとえば、競合するサービスを含むライセンスを選択した場合、各ライセンスに含まれるサービスを確認して再試行するように伝えるエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="cdcea-130">ユーザーがアクセスできるアプリとサービスを変更する</span><span class="sxs-lookup"><span data-stu-id="cdcea-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cdcea-131">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-131">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="cdcea-132">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="cdcea-133">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="cdcea-134">[**ライセンス**] ページで、特定のユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="cdcea-135">右側のウィンドウで、アクセスを許可または削除するアプリとサービスを選択または選択解除します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="cdcea-136">完了したら、[**保存**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="cdcea-137">[アクティブなユーザー] ページでライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cdcea-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="cdcea-138">[**アクティブなユーザー**] ページを使用してライセンスを割り当てる場合、ユーザー ライセンスを製品に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="cdcea-139">複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cdcea-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cdcea-140">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="cdcea-141">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="cdcea-142">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="cdcea-143">ライセンスを割り当てるユーザー名の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="cdcea-144">上部にある [**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-144">At the top, select **Manage product licenses**.</span></span>
4. <span data-ttu-id="cdcea-145">[**製品ライセンスの管理**] ウィンドウで、[**さらに割り当てる: 既存のライセンスを保持し、さらに割り当てる**] \> [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-145">In the **Manage product licenses** pane, select **Assign more: Keep the existing licenses and assign more** \> **Next**.</span></span>
5. <span data-ttu-id="cdcea-146">[**ライセンス**] で、選択したユーザーに付与するライセンスのボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-146">Under **Licenses**, select the box for the license(s) that you want the selected users to have.</span></span>\
    <span data-ttu-id="cdcea-p107">既定では、そのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。ユーザーが使用できるサービスを制限するには、そのユーザーに設定しないサービスのボックスを [オフ] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-p107">By default, all services associated with those licenses are automatically assigned to the users. You can limit which services are available to the users. Deselect the boxes for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="cdcea-150">ウィンドウの下部にある [**変更の保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cdcea-150">At the bottom of the pane, select **Save changes**.</span></span>  
    <span data-ttu-id="cdcea-151">すべてのユーザーに十分なライセンスがない場合は、追加のライセンスを購入する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="cdcea-151">You might have to buy additional licneses if you don't have enough licenses for everyone.</span></span>


> [!NOTE]
> <span data-ttu-id="cdcea-152">多数のユーザーにライセンスを割り当てる場合は、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/enterprise-users/licensing-groups-assign)」を使用します</span><span class="sxs-lookup"><span data-stu-id="cdcea-152">If you want to assign licenses for a large number of users, use [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)</span></span>

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="cdcea-153">1 人のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cdcea-153">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cdcea-154">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="cdcea-155">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="cdcea-156">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="cdcea-157">ライセンスを割り当てるユーザーの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-157">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="cdcea-158">右側のウィンドウで、[**ライセンスとアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-158">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="cdcea-159">[**ライセンス**] セクションを展開し、割り当てるライセンスのボックスを選択して、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-159">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="cdcea-160">ゲスト ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cdcea-160">Assign a license to a guest user</span></span>

<span data-ttu-id="cdcea-161">ゲスト ユーザーを招待して、Azure Active Directory 管理センターで組織と共同作業できます。</span><span class="sxs-lookup"><span data-stu-id="cdcea-161">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="cdcea-162">ゲスト ユーザーの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](/azure/active-directory/external-identities/what-is-b2b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdcea-162">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="cdcea-163">ゲスト ユーザーがいない場合は、「[クイック スタート: Azure Portal のディレクトリにゲスト ユーザーを追加する](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdcea-163">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdcea-164">次の手順を実行するには、全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdcea-164">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="cdcea-165"><a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-165">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="cdcea-166">ナビゲーション ウィンドウで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-166">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="cdcea-167">**[ユーザー | すべてのユーザー (プレビュー)]** ページで **[フィルターの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-167">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="cdcea-168">**[フィールドの選択**] メニューから **[ユーザーの種類]** を選択して、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-168">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="cdcea-169">次のメニューから **[ゲスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-169">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="cdcea-170">結果のリストから、ライセンスが必要なユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-170">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="cdcea-171">**[管理]** で **[ライセンス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-171">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="cdcea-172">**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-172">Select **Assignments**.</span></span>
9. <span data-ttu-id="cdcea-173">**[ライセンスの割り当ての更新]** ページで、ライセンスを割り当てる製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-173">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="cdcea-174">右側で、ゲスト ユーザーにアクセスを許可しないサービスのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="cdcea-174">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="cdcea-175">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdcea-175">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cdcea-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="cdcea-176">Next steps</span></span>

<span data-ttu-id="cdcea-177">ユーザーがまだ Office アプリをインストールしていない場合は、「[従業員クイック スタート ガイド](../../business-video/employee-quick-setup.md)」をユーザーと共有して、ユーザーが「[PC または Mac に Microsoft 365 または Office 2019 をダウンロードしてインストールする方法](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」や「[モバイル デバイスで Office アプリとメールをセットアップする方法](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)」などを参照してセットアップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="cdcea-177">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](../../business-video/employee-quick-setup.md) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="cdcea-178">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="cdcea-178">Related content</span></span>

<span data-ttu-id="cdcea-179">[サブスクリプションとライセンスを理解する](../../commerce/licenses/subscriptions-and-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="cdcea-179">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="cdcea-180">[ユーザーからライセンスの割り当てを解除する](remove-licenses-from-users.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="cdcea-180">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="cdcea-181">[スクリプションのライセンスを購入または削除する](../../commerce/licenses/buy-licenses.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="cdcea-181">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>
