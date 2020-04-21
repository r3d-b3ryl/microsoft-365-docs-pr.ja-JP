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
ms.openlocfilehash: 21b2b17e5cab022f67c71c0d3858f8a03b45899b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628436"
---
# <a name="remove-a-domain"></a><span data-ttu-id="4d799-103">ドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="4d799-103">Remove a domain</span></span>

<span data-ttu-id="4d799-104">作成協力者: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span><span class="sxs-lookup"><span data-stu-id="4d799-104">Contributors: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span></span>
  
 <span data-ttu-id="4d799-105">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="4d799-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4d799-106">別の Microsoft 365 サブスクリプションプランに追加する必要があるため、ドメインを削除していますか?</span><span class="sxs-lookup"><span data-stu-id="4d799-106">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="4d799-107">それとも、サブスクリプションをキャンセルするためですか?</span><span class="sxs-lookup"><span data-stu-id="4d799-107">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="4d799-108">[プランやサブスクリプションを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md)ことも、[サブスクリプションをキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d799-108">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="4d799-109">手順 1: ユーザーを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="4d799-109">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="4d799-110">ユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="4d799-110">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4d799-111">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d799-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="4d799-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="4d799-113">[**ユーザー** >の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="4d799-114">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4d799-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="4d799-115">ページの上部にある [**その他のオプション**(**...**)] を選択し、[**ドメインの変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="4d799-116">[**ドメインの変更**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="4d799-p102">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d799-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d799-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="4d799-120">[**ユーザー** >の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="4d799-121">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4d799-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="4d799-122">ページの上部で、[**その他** >の**ドメインの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="4d799-123">[**ドメインの編集**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="4d799-p103">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d799-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d799-126"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="4d799-127">[**ユーザー** >の**アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="4d799-128">移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4d799-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="4d799-129">ページの上部で、[**その他** >の**ドメインの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="4d799-130">[**ドメインの編集**] ウィンドウで、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="4d799-p104">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d799-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="4d799-133">自分を移動する</span><span class="sxs-lookup"><span data-stu-id="4d799-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4d799-134">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d799-134">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="4d799-135"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-135">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="4d799-136">[**ユーザー** \>の**アクティブなユーザー**] に移動し、一覧から自分のアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-136">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="4d799-137">[**アカウント**] タブで、[**ユーザー名の管理**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-137">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="4d799-138">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-138">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="4d799-139">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="4d799-139">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="4d799-140">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d799-140">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="4d799-141">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d799-141">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="4d799-142">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d799-142">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d799-143">[**ユーザー** \>の**アクティブなユーザー**] に移動し、リストで自分の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-143">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="4d799-144">[**ユーザー名/電子メール**] セクションで、[**編集**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-144">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="4d799-145">[プライマリ>**保存** > **として設定**] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="4d799-145">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="4d799-146">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-146">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="4d799-147">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="4d799-147">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="4d799-148">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d799-148">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="4d799-149">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d799-149">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="4d799-150">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d799-150">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d799-151">[**ユーザー** \>の**アクティブなユーザー**] に移動し、リストで自分の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-151">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="4d799-152">[**ユーザー名/電子メール**] セクションで、[**編集**] を選択し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-152">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="4d799-153">[プライマリ>**保存** > **として設定**] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="4d799-153">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="4d799-154">上部で、自分のアカウント名を選択し、[**サインアウト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-154">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="4d799-155">新しいドメインと同じパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="4d799-155">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="4d799-156">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d799-156">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="4d799-157">詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d799-157">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="4d799-158">既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d799-158">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="4d799-159">手順 2: グループを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="4d799-159">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d799-160">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-160">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="4d799-161">グループ名を選択し、[**電子メールアドレス, プライマリ**] の [**全般**] タブで [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-161">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="4d799-162">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-162">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="4d799-163">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="4d799-163">Select **Save**, then **Close**.</span></span> <span data-ttu-id="4d799-164">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4d799-164">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d799-165"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**グループ** > **グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-165">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="4d799-166">グループ名を選択し、[**名前**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-166">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="4d799-167">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-167">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="4d799-168">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="4d799-168">Select **Save**, then **Close**.</span></span> <span data-ttu-id="4d799-169">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4d799-169">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d799-170"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**グループ** > **グループ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="4d799-171">グループ名を選択し、[**名前**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-171">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="4d799-172">ドロップダウンリストを使用して、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-172">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="4d799-173">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="4d799-173">Select **Save**, then **Close**.</span></span> <span data-ttu-id="4d799-174">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4d799-174">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="4d799-175">手順 3: 古いドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="4d799-175">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d799-176">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-176">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d799-177">管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d799-178">管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d799-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="4d799-179">[**ドメイン**] ページで、削除するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-179">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="4d799-180">右側のウィンドウで、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-180">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="4d799-181">その他のプロンプトに従って、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d799-181">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="4d799-182">ドメインが削除されるまで、どれくらいかかりますか?</span><span class="sxs-lookup"><span data-stu-id="4d799-182">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="4d799-183">Microsoft 365 では、セキュリティグループ、配布リスト、ユーザー、Microsoft 365 グループなどの多くの場所で参照されていない場合、ドメインを削除するのには5分ほどかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d799-183">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="4d799-184">ドメインを使用する参照が多い場合、ドメインが削除されるまでに数時間 (1 日) 程度かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="4d799-184">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="4d799-p112">数百から数千のユーザーがいる場合は、PowerShell を使用してすべてのユーザーに対するクエリを実行してから、別のドメインに移動してください。これを行わないと、一部のユーザーが UI に表示されない可能性があり、ドメインを削除しようとしてもなぜか失敗します。詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d799-p112">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="4d799-189">さらにサポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="4d799-189">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4d799-190">アカウントから [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) ドメインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4d799-190">You can't remove the [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) domain from your account.</span></span>
  
<span data-ttu-id="4d799-p113">それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../contact-support-for-business-products.md)、お手伝いいたします。</span><span class="sxs-lookup"><span data-stu-id="4d799-p113">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="4d799-194">関連記事</span><span class="sxs-lookup"><span data-stu-id="4d799-194">Related articles</span></span>

[<span data-ttu-id="4d799-195">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="4d799-195">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="4d799-196">Office 365 のドメインに関するヘルプ</span><span class="sxs-lookup"><span data-stu-id="4d799-196">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="4d799-197">別の Microsoft 365 for business プランに切り替える</span><span class="sxs-lookup"><span data-stu-id="4d799-197">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="4d799-198">サブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="4d799-198">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
