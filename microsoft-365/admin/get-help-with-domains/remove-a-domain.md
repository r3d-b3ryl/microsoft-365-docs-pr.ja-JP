---
title: ドメインを削除する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.openlocfilehash: f4281eb793e6a832e3bd7f31484a97ccd5065bf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915616"
---
# <a name="remove-a-domain"></a><span data-ttu-id="e2cf4-103">ドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="e2cf4-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e2cf4-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-104">The admin center is changing.</span></span> <span data-ttu-id="e2cf4-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="e2cf4-106">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-106">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e2cf4-107">別の Microsoft 365 サブスクリプション プランにドメインを追加するためにドメインを削除しますか?</span><span class="sxs-lookup"><span data-stu-id="e2cf4-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="e2cf4-108">それとも、サブスクリプションをキャンセルするためですか?</span><span class="sxs-lookup"><span data-stu-id="e2cf4-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="e2cf4-109">[プランやサブスクリプションを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md)ことも、[サブスクリプションをキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="e2cf4-110">手順 1: ユーザーを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="e2cf4-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="e2cf4-111">ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="e2cf4-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2cf4-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e2cf4-113">**[ユーザー]** > **[アクティブなユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e2cf4-114">移動するすべてのユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e2cf4-115">ページ **の上部にある** [その他のオプション (**...]**) を選択し、[ドメインの変更 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="e2cf4-116">[ドメイン **の変更] ウィンドウで** 、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="e2cf4-p103">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2cf4-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e2cf4-120">**[ユーザー]** > **[アクティブなユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e2cf4-121">移動するすべてのユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e2cf4-122">ページの上部で、[その他の編集ドメイン > **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e2cf4-123">[ドメイン **の編集] ウィンドウで** 、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e2cf4-p104">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2cf4-126"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e2cf4-127">**[ユーザー]** > **[アクティブなユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e2cf4-128">移動するすべてのユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e2cf4-129">ページの上部で、[その他の編集ドメイン > **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e2cf4-130">[ドメイン **の編集] ウィンドウで** 、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e2cf4-p105">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="e2cf4-133">自分を移動する</span><span class="sxs-lookup"><span data-stu-id="e2cf4-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2cf4-134"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e2cf4-135">[ユーザーの **アクティブ** \> **なユーザー]** に移動し、一覧からアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="e2cf4-136">[アカウント **] タブで** 、[ユーザー名の **管理] を選択** し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="e2cf4-137">上部でアカウント名を選択し、[サインアウト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e2cf4-138">新しいドメインと同じパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e2cf4-139">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e2cf4-140">詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-140">See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e2cf4-141">既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-141">To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2cf4-142">[ユーザーの **アクティブ** \> **なユーザー]** に移動し、一覧で自分の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e2cf4-143">[ユーザー名 **/ メール] セクションで** 、[編集] **を選択** し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e2cf4-144">[保存 **閉じる] をプライマリ** > **として設定を** > **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e2cf4-145">上部でアカウント名を選択し、[サインアウト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e2cf4-146">新しいドメインと同じパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e2cf4-147">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e2cf4-148">詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-148">See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e2cf4-149">既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-149">To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2cf4-150">[ユーザーの **アクティブ** \> **なユーザー]** に移動し、一覧で自分の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e2cf4-151">[ユーザー名 **/ メール] セクションで** 、[編集] **を選択** し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e2cf4-152">[保存 **閉じる] をプライマリ** > **として設定を** > **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e2cf4-153">上部でアカウント名を選択し、[サインアウト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e2cf4-154">新しいドメインと同じパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e2cf4-155">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e2cf4-156">詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-156">See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e2cf4-157">既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-157">To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="e2cf4-158">手順 2: グループを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="e2cf4-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2cf4-159">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e2cf4-160">グループ名を選択し、[メール アドレス] の [全般] タブの **[** プライマリ] で、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="e2cf4-161">ドロップダウン リストを使用して別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e2cf4-162">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e2cf4-163">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2cf4-164">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">で、[</a>グループ グループ] **ページ** > **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e2cf4-165">グループ名を選択し、[名前] の横にある **[編集** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e2cf4-166">ドロップダウン リストを使用して別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e2cf4-167">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e2cf4-168">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2cf4-169">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>グループ グループ] **ページ** > **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e2cf4-170">グループ名を選択し、[名前] の横にある **[編集** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e2cf4-171">ドロップダウン リストを使用して別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e2cf4-172">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e2cf4-173">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="e2cf4-174">手順 3: 古いドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="e2cf4-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2cf4-175">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2cf4-176">管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2cf4-177">管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="e2cf4-178">[ドメイン **] ページ** で、削除するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="e2cf4-179">右側のウィンドウで、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="e2cf4-180">追加のプロンプトに従って、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="e2cf4-181">ドメインが削除されるまで、どれくらいかかりますか?</span><span class="sxs-lookup"><span data-stu-id="e2cf4-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="e2cf4-182">セキュリティ グループ、配布リスト、ユーザー、Microsoft 365 グループなど、多くの場所で参照されていない場合、Microsoft 365 がドメインを削除するにはわずか 5 分かかります。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="e2cf4-183">ドメインを使用する参照が多い場合、ドメインが削除されるまでに数時間 (1 日) 程度かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="e2cf4-p113">数百から数千のユーザーがいる場合は、PowerShell を使用してすべてのユーザーに対するクエリを実行してから、別のドメインに移動してください。これを行わないと、一部のユーザーが UI に表示されない可能性があり、ドメインを削除しようとしてもなぜか失敗します。詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="e2cf4-188">さらにヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="e2cf4-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e2cf4-189">アカウントから [".onmicrosoft.com"](../setup/domains-faq.yml) ドメインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-189">You can't remove the [".onmicrosoft.com"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="e2cf4-190">ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".onmicrosoft.com" アドレスに戻されます。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-190">When you remove a domain, user accounts will revert back to the ".onmicrosoft.com" address as the Primary SMTP/UserprincipalName.</span></span>
  
<span data-ttu-id="e2cf4-191">まだ動作していませんか?</span><span class="sxs-lookup"><span data-stu-id="e2cf4-191">Still not working?</span></span> <span data-ttu-id="e2cf4-192">ドメインを手動で削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-192">Your domain might need to be manually removed.</span></span> <span data-ttu-id="e2cf4-193">[電話をして](../contact-support-for-business-products.md) 、お客様の面倒を見るお手伝いをします。</span><span class="sxs-lookup"><span data-stu-id="e2cf4-193">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="e2cf4-194">関連記事</span><span class="sxs-lookup"><span data-stu-id="e2cf4-194">Related articles</span></span>

[<span data-ttu-id="e2cf4-195">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="e2cf4-195">Domains FAQ</span></span>](../setup/domains-faq.yml)

[<span data-ttu-id="e2cf4-196">別の一般法人向け Microsoft 365 プランに切り替える</span><span class="sxs-lookup"><span data-stu-id="e2cf4-196">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="e2cf4-197">サブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="e2cf4-197">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)