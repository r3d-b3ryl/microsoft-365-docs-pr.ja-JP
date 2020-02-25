---
title: ビジネスプランで Office 365 を変更できないのはなぜですか?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ROBOTS: NOINDEX
description: 変更プランを手動で行うか、サポートに連絡しなければならない理由について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 4f193db074dccb8146615b72febc62f47a44b7d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243137"
---
# <a name="why-cant-i-upgrade-plans"></a><span data-ttu-id="e69a3-103">プランをアップグレードできないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="e69a3-103">Why can't I upgrade plans?</span></span>

<span data-ttu-id="e69a3-104">[**アップグレード**] タブにプランが表示されない場合は、プランを自動的にアップグレードできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e69a3-104">If you don't see any plans on the **Upgrade** tab, it means your plan can't be upgraded automatically.</span></span> <span data-ttu-id="e69a3-105">場合によっては、アップグレード可能なプランを表示できるように問題を解決したり、代わりにプランを手動でアップグレードまたは変更したりすることができる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e69a3-105">In some cases, you might be able to resolve the issue so that you can view plans available for upgrade, or you might be able to upgrade or change plans manually, instead.</span></span>

> [!NOTE]
> <span data-ttu-id="e69a3-106">この記事は、新しい管理センターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-106">This article applies to the new admin center.</span></span> <span data-ttu-id="e69a3-107">新しい管理センターは、Microsoft 365 のすべての管理者が利用でき、ホームページの上部にある [**新しい管理センター**の切り替え] を選択して選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-107">The new admin center is available to all Microsoft 365 admins, and you can opt in by selecting **Try the new admin center** toggle located at the top of the Home page.</span></span> <span data-ttu-id="e69a3-108">詳細については、「[新しい Microsoft 365 管理センターについて](../../admin/microsoft-365-admin-center-preview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e69a3-108">For more information, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md).</span></span> <span data-ttu-id="e69a3-109">以前の管理センターに関する記事を表示するには、「 [Office 365 を「ビジネスプラン用に切り替えることができない理由](why-can-t-i-switch-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e69a3-109">To view the article about the old admin center, see [Why can't I switch Office 365 for business plans?](why-can-t-i-switch-plans.md).</span></span>

## <a name="why-are-there-no-plans-listed-to-upgrade"></a><span data-ttu-id="e69a3-110">アップグレードする計画が表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="e69a3-110">Why are there no plans listed to upgrade?</span></span>

### <a name="you-cant-upgrade-subscriptions-now-because-you-have-more-users-than-licenses"></a><span data-ttu-id="e69a3-111">ライセンス数を超えるユーザーがいるため、今はサブスクリプションをアップグレードできません。</span><span class="sxs-lookup"><span data-stu-id="e69a3-111">You can't upgrade subscriptions now because you have more users than licenses.</span></span>

<span data-ttu-id="e69a3-112">プランを自動的にアップグレードするには、すべてのユーザーに有効なライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e69a3-112">To upgrade plans automatically, all of your users need to be assigned valid licenses.</span></span> <span data-ttu-id="e69a3-113">購入した数より多くのライセンスを割り当てている場合は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに、解決する必要があるライセンスの競合があるという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-113">If you have assigned more licenses than you have purchased, you'll see an alert on the <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page that says you have a licensing conflict that needs to be resolved.</span></span> <span data-ttu-id="e69a3-114">[ライセンスの競合を解決する方法について説明](../../admin/manage/resolve-license-conflicts.md)します。</span><span class="sxs-lookup"><span data-stu-id="e69a3-114">[Learn how to resolve license conflicts](../../admin/manage/resolve-license-conflicts.md).</span></span> <span data-ttu-id="e69a3-115">ライセンスの競合を解決した後、[**アップグレード**] タブに [プラン] が表示されます。サポートされていない場合は、[手動でプランを変更](change-plans-manually.md)するか、[サポート] を[呼び出す](../../admin/contact-support-for-business-products.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-115">After you have resolved any licensing conflicts, you should see plans listed on the **Upgrade** tab. If not, you can [change plans manually](change-plans-manually.md), or [call support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="you-cant-upgrade-subscriptions-right-now-because-this-subscription-isnt-fully-set-up-or-the-service-isnt-available"></a><span data-ttu-id="e69a3-116">このサブスクリプションは完全に設定されていないか、サービス\'が使用できないため、今すぐサブスクリプションをアップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e69a3-116">You can't upgrade subscriptions right now because this subscription isn't fully set up or the service isn\'t available.</span></span>

<span data-ttu-id="e69a3-117">たとえば、いずれかのサービスにインシデントがある場合は、すべてのサービスが正常な状態になるまでアップグレードできません。</span><span class="sxs-lookup"><span data-stu-id="e69a3-117">For example, if one of the services has an incident, you won't be able to upgrade until all services are healthy.</span></span> <span data-ttu-id="e69a3-118">プロビジョニングまたはサービスの正常性の問題があるかどうかを確認するには、管理センターで、**ヘルス** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">サービスの正常</a>性ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e69a3-118">To see if there are provisioning or service health issues, in the admin center, go to the **Health** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">Service health</a> page.</span></span>

<span data-ttu-id="e69a3-119">サービスが完全にはプロビジョニングされていないか、サービス正常性に問題があることがわかった場合は、サービスが利用可能になるまで数時間待ってから、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="e69a3-119">If you find that a service is not fully provisioned, or you have a service health issue, please wait a few hours for your service to become available, and try again.</span></span> <span data-ttu-id="e69a3-120">それでも問題が解決しない場合は、サポートにお[問い合わせ](../../admin/contact-support-for-business-products.md)ください。</span><span class="sxs-lookup"><span data-stu-id="e69a3-120">If you still have a problem, please [call support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="you-cant-upgrade-plans-because-another-plan-is-in-the-process-of-being-upgraded-or-is-pending-a-credit-check"></a><span data-ttu-id="e69a3-121">別のプランがアップグレード中であるか、与信審査が保留中であるため、プランをアップグレードできません。</span><span class="sxs-lookup"><span data-stu-id="e69a3-121">You can't upgrade plans because another plan is in the process of being upgraded or is pending a credit check.</span></span>

<span data-ttu-id="e69a3-122">プランをアップグレードする前に、与信審査が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="e69a3-122">Wait until the credit check has been completed before upgrading plans.</span></span> <span data-ttu-id="e69a3-123">与信審査の完了には、最大で 2 営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e69a3-123">Credit checks can take up to two working days.</span></span>

### <a name="currently-this-subscription-is-not-eligible-to-upgrade"></a><span data-ttu-id="e69a3-124">現時点では、このサブスクリプションはアップグレード対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="e69a3-124">Currently, this subscription is not eligible to upgrade.</span></span>

<span data-ttu-id="e69a3-125">プランを[手動で変更](change-plans-manually.md)するか、[サポートに連絡](../../admin/contact-support-for-business-products.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-125">You can [change plans manually](change-plans-manually.md) or [call support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="i-see-a-different-message-than-whats-listed-here"></a><span data-ttu-id="e69a3-126">ここで挙がっているものとは別のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-126">I see a different message than what's listed here.</span></span>

<span data-ttu-id="e69a3-127">プランを[手動で変更](change-plans-manually.md)するか、[サポートに連絡](../../admin/contact-support-for-business-products.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-127">You can [change plans manually](change-plans-manually.md) or [call support](../../admin/contact-support-for-business-products.md).</span></span>

## <a name="additional-reasons-you-cant-upgrade"></a><span data-ttu-id="e69a3-128">アップグレードできないその他の理由</span><span class="sxs-lookup"><span data-stu-id="e69a3-128">Additional reasons you can't Upgrade</span></span>

### <a name="you-have-two-or-more-plans-for-the-same-product"></a><span data-ttu-id="e69a3-129">同じ製品に対して2つ以上のプランがある。</span><span class="sxs-lookup"><span data-stu-id="e69a3-129">You have two or more plans for the same product</span></span>

<span data-ttu-id="e69a3-130">[**アップグレード**] タブは、すべてのユーザーが同じプランを購読している場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-130">You can only use the **Upgrade** tab if all users subscribe to the same plan.</span></span> <span data-ttu-id="e69a3-131">たとえば、2つの Office 365 Business Premium プランがある場合は、そのうちの1つを別のプランに自動的にアップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e69a3-131">For example, if you have two Office 365 Business Premium plans, you won't be able to automatically upgrade one of them to another plan.</span></span>

### <a name="you-have-a-prepaid-plan"></a><span data-ttu-id="e69a3-132">プリペイド (先払い) プランを使用している</span><span class="sxs-lookup"><span data-stu-id="e69a3-132">You have a prepaid plan</span></span>

<span data-ttu-id="e69a3-133">サブスクリプションを事前に購入している場合は、[プランを手動で変更](change-plans-manually.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-133">If you've paid for your subscription in advance, you might be able to [change plans manually](change-plans-manually.md).</span></span> <span data-ttu-id="e69a3-134">ただし、現在のプランの期限が切れる前にプランをアップグレードする場合は、現在のサブスクリプションに残っている未使用期間のクレジットを受け取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="e69a3-134">However, you won't receive a credit for unused time remaining on your current subscription if you upgrade plans before the current plan expires.</span></span>

<span data-ttu-id="e69a3-135">ヘルプの[サポートを呼び出す](../../admin/contact-support-for-business-products.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-135">You can also [call support](../../admin/contact-support-for-business-products.md) for help.</span></span>

### <a name="you-have-a-government-or-non-profit-plan"></a><span data-ttu-id="e69a3-136">政府機関向けプランまたは非営利団体向けプランに加入している</span><span class="sxs-lookup"><span data-stu-id="e69a3-136">You have a government or non-profit plan</span></span>

<span data-ttu-id="e69a3-137">政府機関または非営利団体のプランをご利用の場合は、[プランを手動で変更](change-plans-manually.md)するか、[サポートに問い合わせ](../../admin/contact-support-for-business-products.md)てください。</span><span class="sxs-lookup"><span data-stu-id="e69a3-137">If you have a government or non-profit plan, you can [change plans manually](change-plans-manually.md) or [call support](../../admin/contact-support-for-business-products.md) for help.</span></span>

### <a name="the-subscription-that-you-want-to-upgrade-from-has-a-temporary-issue"></a><span data-ttu-id="e69a3-138">アップグレードの対象となるサブスクリプションに一時的な問題がある</span><span class="sxs-lookup"><span data-stu-id="e69a3-138">The subscription that you want to upgrade from has a temporary issue</span></span>

<span data-ttu-id="e69a3-139">サービスが大量のプランをアップグレードする過程にあるため、[**アップグレード**] タブにプランが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e69a3-139">You might not see any plans on the **Upgrade** tab because the service is in the process of upgrading a high volume of plans.</span></span> <span data-ttu-id="e69a3-140">最初の試行から 1 時間ほど待って、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="e69a3-140">Try again in about an hour after your first attempt.</span></span>

### <a name="the-plan-that-you-want-to-upgrade-to-isnt-a-supported-option"></a><span data-ttu-id="e69a3-141">アップグレード先のプランがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="e69a3-141">The plan that you want to upgrade to isn't a supported option</span></span>

<span data-ttu-id="e69a3-142">プランをアップグレードすると、現在のプランのサービスに基づいて、アップグレードに使用できるプランが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-142">When you upgrade plans, the plans that are available for you to upgrade to are displayed based on the services in your current plan.</span></span> <span data-ttu-id="e69a3-143">アップグレードできるのは、Exchange Online や SharePoint Online などのデータ関連サービスを持つプランのみです。または、それより上位のバージョンにアップグレードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-143">You can only upgrade to a plan that has the same data-related services, such as Exchange Online or SharePoint Online, or to a higher version of them.</span></span> <span data-ttu-id="e69a3-144">これにより、ユーザー\'はアップグレード中にこれらのサービスに関連するデータを失うことがなくなります。</span><span class="sxs-lookup"><span data-stu-id="e69a3-144">This ensures that users don\'t lose data related to those services during the upgrade.</span></span>

<span data-ttu-id="e69a3-145">プランが自動的にアップグレードされない場合は、代わりにプランを[手動で変更](change-plans-manually.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-145">If your plan isn't eligible to upgrade plans automatically, you might be able to [change plans manually](change-plans-manually.md), instead.</span></span> <span data-ttu-id="e69a3-146">ヘルプの[サポートを呼び出す](../../admin/contact-support-for-business-products.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="e69a3-146">You can also [call support](../../admin/contact-support-for-business-products.md) for help.</span></span>

### <a name="your-subscription-has-an-add-on"></a><span data-ttu-id="e69a3-147">サブスクリプションにアドオンがあります</span><span class="sxs-lookup"><span data-stu-id="e69a3-147">Your subscription has an Add-on</span></span>

<span data-ttu-id="e69a3-148">サブスクリプションにアドオンがある場合は、[プランを手動で変更](change-plans-manually.md)できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e69a3-148">If you have an Add-on with your subscription, you might be able to [change plans manually](change-plans-manually.md).</span></span>

### <a name="your-subscription-has-an-unpaid-balance"></a><span data-ttu-id="e69a3-149">サブスクリプションに未払い残高があります</span><span class="sxs-lookup"><span data-stu-id="e69a3-149">Your subscription has an unpaid balance</span></span>

<span data-ttu-id="e69a3-150">これを解決するには、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> ] ページでサブスクリプションを検索し、[**課金**] セクションの [**今すぐ購入**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="e69a3-150">To resolve this, find the subscription on the <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page, and select the **Pay now** link in the **Billing** section.</span></span> <span data-ttu-id="e69a3-151">支払いを行った後で、[**アップグレード**] タブをもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="e69a3-151">After the payment has been made, check the **Upgrade** tab again.</span></span>

## <a name="call-support-to-help-you-change-plans"></a><span data-ttu-id="e69a3-152">プランを変更するためのサポートへのお問い合わせ</span><span class="sxs-lookup"><span data-stu-id="e69a3-152">Call support to help you change plans</span></span>
[<span data-ttu-id="e69a3-153">Microsoft サポートに連絡する</span><span class="sxs-lookup"><span data-stu-id="e69a3-153">Call Microsoft support</span></span>](../../admin/contact-support-for-business-products.md)