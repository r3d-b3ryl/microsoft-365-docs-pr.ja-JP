---
title: ドメインを削除する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Microsoft 365 から古いドメインを削除し、ユーザーとグループを別のドメインに移動する方法について説明します。
ms.openlocfilehash: 6f5e36a897316c8cdc057a725957c54e7eb53edc
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079763"
---
# <a name="remove-a-domain"></a><span data-ttu-id="3513e-103">ドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="3513e-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3513e-104">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="3513e-104">The admin center is changing.</span></span> <span data-ttu-id="3513e-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3513e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="3513e-106">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3513e-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3513e-107">別の Microsoft 365 サブスクリプションプランに追加する必要があるため、ドメインを削除していますか?</span><span class="sxs-lookup"><span data-stu-id="3513e-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="3513e-108">それとも、サブスクリプションをキャンセルするためですか?</span><span class="sxs-lookup"><span data-stu-id="3513e-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="3513e-109">[プランやサブスクリプションを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md)ことも、[サブスクリプションをキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="3513e-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="3513e-110">手順 1: ユーザーを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="3513e-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="3513e-111">ユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="3513e-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3513e-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="3513e-113">[**ユーザー** > の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="3513e-114">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3513e-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="3513e-115">ページの上部にある [**その他のオプション**(**...**)] を選択し、[**ドメインの変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="3513e-116">[**ドメインの変更**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="3513e-117">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="3513e-117">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="3513e-118">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="3513e-118">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3513e-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="3513e-120">[**ユーザー** > の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="3513e-121">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3513e-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="3513e-122">ページの上部で、[**その他**のドメインの編集] を選択し > **Edit domains**ます。</span><span class="sxs-lookup"><span data-stu-id="3513e-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="3513e-123">[**ドメインの編集**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="3513e-124">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="3513e-124">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="3513e-125">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="3513e-125">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3513e-126"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="3513e-127">[**ユーザー** > の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="3513e-128">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3513e-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="3513e-129">ページの上部で、[**その他**のドメインの編集] を選択し > **Edit domains**ます。</span><span class="sxs-lookup"><span data-stu-id="3513e-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="3513e-130">[**ドメインの編集**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="3513e-131">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span><span class="sxs-lookup"><span data-stu-id="3513e-131">You'll need to do this for yourself, too, if you're on the domain that you want to remove.</span></span> <span data-ttu-id="3513e-132">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span><span class="sxs-lookup"><span data-stu-id="3513e-132">When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="3513e-133">自分を移動する</span><span class="sxs-lookup"><span data-stu-id="3513e-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3513e-134"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="3513e-135">[**ユーザー** \> の**アクティブなユーザー**] に移動し、一覧から自分のアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="3513e-136">[**アカウント**] タブで、[**ユーザー名の管理**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="3513e-137">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="3513e-138">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3513e-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="3513e-139">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="3513e-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="3513e-140">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3513e-140">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="3513e-141">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3513e-141">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3513e-142">[**ユーザー** \> の**アクティブなユーザー**] に移動し、リストで自分の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="3513e-143">[**ユーザー名/電子メール**] セクションで、[**編集**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="3513e-144">[**プライマリの保存として設定**] を選択し > **Save** > **Close**ます。</span><span class="sxs-lookup"><span data-stu-id="3513e-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="3513e-145">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="3513e-146">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3513e-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="3513e-147">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="3513e-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="3513e-148">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3513e-148">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="3513e-149">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3513e-149">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3513e-150">[**ユーザー** \> の**アクティブなユーザー**] に移動し、リストで自分の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="3513e-151">[**ユーザー名/電子メール**] セクションで、[**編集**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="3513e-152">[**プライマリの保存として設定**] を選択し > **Save** > **Close**ます。</span><span class="sxs-lookup"><span data-stu-id="3513e-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="3513e-153">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="3513e-154">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3513e-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="3513e-155">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="3513e-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="3513e-156">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3513e-156">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="3513e-157">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3513e-157">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="3513e-158">手順 2: グループを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="3513e-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3513e-159">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="3513e-160">グループ名を選択し、[**電子メールアドレス, プライマリ**] の [**全般**] タブで [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="3513e-161">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="3513e-162">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="3513e-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="3513e-163">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3513e-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3513e-164"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**グループ** > **グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="3513e-165">グループ名を選択し、[**名前**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="3513e-166">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="3513e-167">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="3513e-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="3513e-168">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3513e-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3513e-169"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**グループ** > **グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="3513e-170">グループ名を選択し、[**名前**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="3513e-171">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="3513e-172">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="3513e-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="3513e-173">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3513e-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="3513e-174">手順 3: 古いドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="3513e-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3513e-175">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3513e-176">管理センターで、[ドメインの**セットアップ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3513e-177">管理センターで、[ドメインの**セットアップ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3513e-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="3513e-178">[**ドメイン**] ページで、削除するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="3513e-179">右側のウィンドウで、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="3513e-180">その他のプロンプトに従って、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3513e-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="3513e-181">ドメインが削除されるまで、どれくらいかかりますか?</span><span class="sxs-lookup"><span data-stu-id="3513e-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="3513e-182">Microsoft 365 では、セキュリティグループ、配布リスト、ユーザー、Microsoft 365 グループなどの多くの場所で参照されていない場合、ドメインを削除するのには5分ほどかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3513e-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="3513e-183">ドメインを使用する参照が多い場合、ドメインが削除されるまでに数時間 (1 日) 程度かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="3513e-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="3513e-184">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain.</span><span class="sxs-lookup"><span data-stu-id="3513e-184">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain.</span></span> <span data-ttu-id="3513e-185">Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why.</span><span class="sxs-lookup"><span data-stu-id="3513e-185">Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why.</span></span> <span data-ttu-id="3513e-186">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span><span class="sxs-lookup"><span data-stu-id="3513e-186">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="3513e-187">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="3513e-187">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="3513e-188">さらにヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="3513e-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3513e-189">アカウントから [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) ドメインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="3513e-189">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="3513e-190">Still not working?</span><span class="sxs-lookup"><span data-stu-id="3513e-190">Still not working?</span></span> <span data-ttu-id="3513e-191">Your domain might need to be manually removed.</span><span class="sxs-lookup"><span data-stu-id="3513e-191">Your domain might need to be manually removed.</span></span> <span data-ttu-id="3513e-192">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span><span class="sxs-lookup"><span data-stu-id="3513e-192">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="3513e-193">関連記事</span><span class="sxs-lookup"><span data-stu-id="3513e-193">Related articles</span></span>

[<span data-ttu-id="3513e-194">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="3513e-194">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="3513e-195">Microsoft 365 ドメインのヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="3513e-195">Get help with Microsoft 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="3513e-196">別の Microsoft 365 for business プランに切り替える</span><span class="sxs-lookup"><span data-stu-id="3513e-196">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="3513e-197">サブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="3513e-197">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
