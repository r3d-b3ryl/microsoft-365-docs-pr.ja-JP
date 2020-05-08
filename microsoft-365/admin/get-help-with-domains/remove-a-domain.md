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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Microsoft 365 から古いドメインを削除し、ユーザーとグループを別のドメインに移動する方法について説明します。
ms.openlocfilehash: ef0209d6ccb7534745172585fe599f627e386cb4
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140407"
---
# <a name="remove-a-domain"></a><span data-ttu-id="e0f1f-103">ドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="e0f1f-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e0f1f-104">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-104">The admin center is changing.</span></span> <span data-ttu-id="e0f1f-105">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="e0f1f-106">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e0f1f-107">別の Microsoft 365 サブスクリプションプランに追加する必要があるため、ドメインを削除していますか?</span><span class="sxs-lookup"><span data-stu-id="e0f1f-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="e0f1f-108">それとも、サブスクリプションをキャンセルするためですか?</span><span class="sxs-lookup"><span data-stu-id="e0f1f-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="e0f1f-109">[プランやサブスクリプションを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md)ことも、[サブスクリプションをキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="e0f1f-110">手順 1: ユーザーを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="e0f1f-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="e0f1f-111">ユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="e0f1f-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e0f1f-112">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e0f1f-113"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e0f1f-114">[**ユーザー** >の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e0f1f-115">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e0f1f-116">ページの上部にある [**その他のオプション**(**...**)] を選択し、[**ドメインの変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="e0f1f-117">[**ドメインの変更**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="e0f1f-p103">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e0f1f-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e0f1f-121">[**ユーザー** >の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e0f1f-122">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e0f1f-123">ページの上部で、[**その他** >の**ドメインの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e0f1f-124">[**ドメインの編集**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e0f1f-p104">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e0f1f-127"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e0f1f-128">[**ユーザー** >の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e0f1f-129">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e0f1f-130">ページの上部で、[**その他** >の**ドメインの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e0f1f-131">[**ドメインの編集**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e0f1f-p105">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="e0f1f-134">自分を移動する</span><span class="sxs-lookup"><span data-stu-id="e0f1f-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e0f1f-135">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e0f1f-136"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e0f1f-137">[**ユーザー** \>の**アクティブなユーザー**] に移動し、一覧から自分のアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="e0f1f-138">[**アカウント**] タブで、[**ユーザー名の管理**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="e0f1f-139">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e0f1f-140">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e0f1f-141">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e0f1f-142">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e0f1f-143">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e0f1f-144">[**ユーザー** \>の**アクティブなユーザー**] に移動し、リストで自分の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e0f1f-145">[**ユーザー名/電子メール**] セクションで、[**編集**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e0f1f-146">[プライマリ>**保存** > **として設定**] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e0f1f-147">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e0f1f-148">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e0f1f-149">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e0f1f-150">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e0f1f-151">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e0f1f-152">[**ユーザー** \>の**アクティブなユーザー**] に移動し、リストで自分の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e0f1f-153">[**ユーザー名/電子メール**] セクションで、[**編集**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e0f1f-154">[プライマリ>**保存** > **として設定**] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e0f1f-155">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e0f1f-156">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e0f1f-157">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e0f1f-158">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e0f1f-159">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="e0f1f-160">手順 2: グループを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="e0f1f-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e0f1f-161">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e0f1f-162">グループ名を選択し、[**電子メールアドレス, プライマリ**] の [**全般**] タブで [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="e0f1f-163">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e0f1f-164">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e0f1f-165">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e0f1f-166"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**グループ** > **グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e0f1f-167">グループ名を選択し、[**名前**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e0f1f-168">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e0f1f-169">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e0f1f-170">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e0f1f-171"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**グループ** > **グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e0f1f-172">グループ名を選択し、[**名前**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e0f1f-173">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e0f1f-174">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e0f1f-175">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="e0f1f-176">手順 3: 古いドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="e0f1f-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e0f1f-177">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e0f1f-178">管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e0f1f-179">管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="e0f1f-180">[**ドメイン**] ページで、削除するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="e0f1f-181">右側のウィンドウで、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="e0f1f-182">その他のプロンプトに従って、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="e0f1f-183">ドメインが削除されるまで、どれくらいかかりますか?</span><span class="sxs-lookup"><span data-stu-id="e0f1f-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="e0f1f-184">Microsoft 365 では、セキュリティグループ、配布リスト、ユーザー、Microsoft 365 グループなどの多くの場所で参照されていない場合、ドメインを削除するのには5分ほどかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="e0f1f-185">ドメインを使用する参照が多い場合、ドメインが削除されるまでに数時間 (1 日) 程度かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="e0f1f-p113">数百から数千のユーザーがいる場合は、PowerShell を使用してすべてのユーザーに対するクエリを実行してから、別のドメインに移動してください。これを行わないと、一部のユーザーが UI に表示されない可能性があり、ドメインを削除しようとしてもなぜか失敗します。詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="e0f1f-190">さらにサポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="e0f1f-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e0f1f-191">アカウントから [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) ドメインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="e0f1f-p114">それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../contact-support-for-business-products.md)、お手伝いいたします。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="e0f1f-195">関連記事</span><span class="sxs-lookup"><span data-stu-id="e0f1f-195">Related articles</span></span>

[<span data-ttu-id="e0f1f-196">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="e0f1f-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="e0f1f-197">Office 365 のドメインに関するヘルプ</span><span class="sxs-lookup"><span data-stu-id="e0f1f-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="e0f1f-198">別の一般法人向け Microsoft 365 プランに切り替える</span><span class="sxs-lookup"><span data-stu-id="e0f1f-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="e0f1f-199">サブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="e0f1f-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
