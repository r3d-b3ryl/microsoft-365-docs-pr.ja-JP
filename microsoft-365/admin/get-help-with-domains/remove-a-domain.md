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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: ユーザーから古いドメインを削除し、Microsoft 365別のドメインに移動するか、サブスクリプションをキャンセルする方法について学習します。
ms.openlocfilehash: 227ca3e58a4c6278278048deeffcf68c1d659546
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393873"
---
# <a name="remove-a-domain"></a><span data-ttu-id="99f0d-103">ドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="99f0d-103">Remove a domain</span></span>

 <span data-ttu-id="99f0d-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99f0d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="99f0d-105">別のサブスクリプション プランにドメインを追加する場合、ドメインをMicrosoft 365しますか?</span><span class="sxs-lookup"><span data-stu-id="99f0d-105">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="99f0d-106">それとも、サブスクリプションをキャンセルするためですか?</span><span class="sxs-lookup"><span data-stu-id="99f0d-106">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="99f0d-107">[プランやサブスクリプションを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md)ことも、[サブスクリプションをキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="99f0d-107">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>

### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="99f0d-108">手順 1: ユーザーを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="99f0d-108">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="99f0d-109">ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="99f0d-109">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="99f0d-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-110">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="99f0d-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="99f0d-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

::: moniker-end

2. <span data-ttu-id="99f0d-113">**[ユーザー]** > **[アクティブ ユーザー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="99f0d-114">移動するすべてのユーザーの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="99f0d-115">ページの上部で、[ドメインの変更] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="99f0d-115">At the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="99f0d-116">[ドメイン **の変更] ウィンドウで** 、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="99f0d-p102">削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="99f0d-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

#### <a name="move-yourself"></a><span data-ttu-id="99f0d-119">自分を移動する</span><span class="sxs-lookup"><span data-stu-id="99f0d-119">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="99f0d-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="99f0d-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="99f0d-122"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-122">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

::: moniker-end

2. <span data-ttu-id="99f0d-123">[ユーザーの **アクティブ** \> **なユーザー]** に移動し、一覧からアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-123">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="99f0d-124">[アカウント **] タブで** 、[ユーザー名の **管理] を選択** し、別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-124">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>

4. <span data-ttu-id="99f0d-125">上部でアカウント名を選択し、[サインアウト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="99f0d-125">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="99f0d-126">新しいドメインと同じパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-126">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="99f0d-p103">また、PowerShell を使用してユーザーを別のドメインに移動することもできます。詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain) を使用します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-p103">You can also use PowerShell to move users to another domain. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).</span></span>

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="99f0d-130">手順 2: グループを別のドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="99f0d-130">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="99f0d-131">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="99f0d-132">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">で、[</a>グループ グループ] **ページ** > **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="99f0d-133">管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>グループ グループ] **ページ** > **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-133">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

::: moniker-end

2. <span data-ttu-id="99f0d-134">グループ名を選択し、[メール アドレス] の [全般] タブの **[** プライマリ] で、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="99f0d-134">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="99f0d-135">ドロップダウン リストを使用して別のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-135">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="99f0d-136">[**保存**]、[**閉じる**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="99f0d-136">Select **Save**, then **Close**.</span></span> <span data-ttu-id="99f0d-137">削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-137">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="99f0d-138">手順 3: 古いドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="99f0d-138">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="99f0d-139">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="99f0d-140">管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-140">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="99f0d-141">管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">に移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-141">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="99f0d-142">[ドメイン **] ページ** で、削除するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-142">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="99f0d-143">右側のウィンドウで、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="99f0d-143">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="99f0d-144">追加のプロンプトに従って、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="99f0d-144">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="99f0d-145">ドメインが削除されるまで、どれくらいかかりますか?</span><span class="sxs-lookup"><span data-stu-id="99f0d-145">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="99f0d-146">Microsoft 365 がセキュリティ グループ、配布リスト、ユーザー、Microsoft 365 グループなどの多くの場所で参照されていない場合、ドメインを削除するにはわずか 5 分かかります。</span><span class="sxs-lookup"><span data-stu-id="99f0d-146">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="99f0d-147">ドメインを使用する参照が多い場合、ドメインが削除されるまでに数時間 (1 日) 程度かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="99f0d-147">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>

<span data-ttu-id="99f0d-p106">数百から数千のユーザーがいる場合は、PowerShell を使用してすべてのユーザーに対するクエリを実行してから、別のドメインに移動してください。これを行わないと、一部のユーザーが UI に表示されない可能性があり、ドメインを削除しようとしてもなぜか失敗します。詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain) を使用します。</span><span class="sxs-lookup"><span data-stu-id="99f0d-p106">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).</span></span>

## <a name="still-need-help"></a><span data-ttu-id="99f0d-152">さらにヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="99f0d-152">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="99f0d-153">アカウントから [".onmicrosoft.com"](../setup/domains-faq.yml) ドメインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="99f0d-153">You can't remove the [".onmicrosoft.com"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="99f0d-154">ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".onmicrosoft.com" アドレスに戻されます。</span><span class="sxs-lookup"><span data-stu-id="99f0d-154">When you remove a domain, user accounts will revert back to the ".onmicrosoft.com" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="99f0d-p108">それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../../business-video/get-help-support.md)、お手伝いいたします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-p108">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md) and we'll help you take care of it!</span></span>

::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> <span data-ttu-id="99f0d-158">アカウントから [".onmicrosoft.de"](../setup/domains-faq.yml) ドメインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="99f0d-158">You can't remove the [".onmicrosoft.de"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="99f0d-159">ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".onmicrosoft.de" アドレスに戻されます。</span><span class="sxs-lookup"><span data-stu-id="99f0d-159">When you remove a domain, user accounts will revert back to the ".onmicrosoft.de" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="99f0d-p110">それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true)、お手伝いいたします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-p110">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true) and we'll help you take care of it!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="99f0d-163">アカウントから [".partner.onmschina.cn"](../setup/domains-faq.yml) ドメインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="99f0d-163">You can't remove the [".partner.onmschina.cn"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="99f0d-164">ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".partner.onmschina.cn" アドレスに戻されます。</span><span class="sxs-lookup"><span data-stu-id="99f0d-164">When you remove a domain, user accounts will revert back to the ".partner.onmschina.cn" address as the Primary SMTP/UserprincipalName.</span></span>

<span data-ttu-id="99f0d-p112">それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true)、お手伝いいたします。</span><span class="sxs-lookup"><span data-stu-id="99f0d-p112">Still not working? Your domain might need to be manually removed. [Give us a call](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) and we'll help you take care of it!</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="99f0d-168">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="99f0d-168">Related content</span></span>

<span data-ttu-id="99f0d-169">[ドメインの FAQ](../setup/domains-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="99f0d-169">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

<span data-ttu-id="99f0d-170">[ビジネス プランの別のMicrosoft 365に切り替える](../../commerce/subscriptions/switch-to-a-different-plan.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="99f0d-170">[Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md) (article)</span></span>

<span data-ttu-id="99f0d-171">[サブスクリプションをキャンセルする](../../commerce/subscriptions/cancel-your-subscription.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="99f0d-171">[Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md) (article)</span></span>
