---
title: サブスクリプションが終了した場合、データとアクセスはどうなりますか?
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: 一般法人向け Office 365 のサブスクリプションが期限切れになった場合、無効になった場合、またはキャンセルされた場合に、データがどうなるかについて説明します。
ms.openlocfilehash: 2529d5027305a9ceaf71033b4de52a867b9fa9fb
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955675"
---
# <a name="what-happens-to-my-data-and-access-when-my-office-365-for-business-subscription-ends"></a><span data-ttu-id="10d1f-103">一般法人向け Office 365 のサブスクリプションが終了したとき、データとアクセスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="10d1f-103">What happens to my data and access when my Office 365 for business subscription ends?</span></span>

<span data-ttu-id="10d1f-104">期限切れ、またはキャンセルを決定したためにサブスクリプションが終了した場合、Office 365 サービス、アプリケーション、および顧客データへのアクセスは、サブスクリプションが完全にオフまたは*プロビジョニング解除*される前に複数の状態を経ます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-104">If your subscription ends—either because it expires, or because you decide to cancel—your access to Office 365 services, applications, and customer data go through multiple states before the subscription is fully turned off, or *deprovisioned*.</span></span> <span data-ttu-id="10d1f-105">この進行を認識している場合、手遅れになる前にサブスクリプションをアクティブな状態に戻すか、Office 365 を離れる場合には、最終的に削除される前にデータをバックアップするのが適切です。</span><span class="sxs-lookup"><span data-stu-id="10d1f-105">If you are aware of this progression, you'll be better equipped to return your subscription to an active state before it's too late, or—if you're leaving Office 365—back up your data before it is ultimately deleted.</span></span>
  
## <a name="office-365-for-business-subscription-lifecycle"></a><span data-ttu-id="10d1f-106">一般法人向け Office 365: サブスクリプションのライフサイクル</span><span class="sxs-lookup"><span data-stu-id="10d1f-106">Office 365 for business: Subscription lifecycle</span></span>
- <span data-ttu-id="10d1f-107">サブスクリプションの有効期限が切れると、次の段階を経ます: 期限切れ/無効/プロビジョニング解除。</span><span class="sxs-lookup"><span data-stu-id="10d1f-107">If your subscription expires, it goes through the following stages: Expired / Disabled / Deprovisioned.</span></span> <span data-ttu-id="10d1f-108">期限切れステージは、サブスクリプションが終了日に達するとすぐに始まります。</span><span class="sxs-lookup"><span data-stu-id="10d1f-108">The Expired stage starts immediately after the subscription has reached its end date.</span></span>
- <span data-ttu-id="10d1f-109">年間サブスクリプションで継続請求をオフにすると、有効期限が切れたサブスクリプションと同じステージを経ます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-109">If you turn off recurring billing on your annual subscription, it goes through the same stages as an expired subscription.</span></span> <span data-ttu-id="10d1f-110">最初のステージの開始は、年次サブスクリプションの記念日からであり、サブスクリプションの継続請求設定をオフにした日付からではありません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-110">The first stage starts are the anniversary of the annual subscription, not starting on the date that you turned off the subscription's recurring billing setting.</span></span>
- <span data-ttu-id="10d1f-111">月次サブスクリプションをキャンセルすると、すぐに (キャンセルの日付で) 無効になります。</span><span class="sxs-lookup"><span data-stu-id="10d1f-111">If you cancel your monthly subscription, it will be disabled immediately (at the date of cancellation).</span></span> <span data-ttu-id="10d1f-112">つまり、ユーザーはすぐに Office 365 の資産にアクセスできなくなり、その後 90 日間は管理者のみがデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-112">This means your users will lose access to the Office 365 assets immediately and only admins will have access to the data for the next 90 days.</span></span>

<span data-ttu-id="10d1f-113">以下の表は、購入した一般法人向け Office 365 のサブスクリプションの有効期限が切れたときの流れを説明しています。</span><span class="sxs-lookup"><span data-stu-id="10d1f-113">The following table explains what you can expect when a paid Office 365 for business subscription expires.</span></span>

| <span data-ttu-id="10d1f-114">**アクティブ**</span><span class="sxs-lookup"><span data-stu-id="10d1f-114">**Active**</span></span>                                                             | <span data-ttu-id="10d1f-115">**期限切れ <br/>(30 日間\*)**</span><span class="sxs-lookup"><span data-stu-id="10d1f-115">**Expired <br/>(30 days\*)**</span></span>                                                | <span data-ttu-id="10d1f-116">**無効 <br/>(90 日間\*)**</span><span class="sxs-lookup"><span data-stu-id="10d1f-116">**Disabled <br/>(90 days\*)**</span></span>                                               | <span data-ttu-id="10d1f-117">**プロビジョニング解除**</span><span class="sxs-lookup"><span data-stu-id="10d1f-117">**Deprovisioned**</span></span>                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="10d1f-118">*すべてのユーザーがデータ アクセス可能*</span><span class="sxs-lookup"><span data-stu-id="10d1f-118">*Data accessible to all*</span></span>                                               | <span data-ttu-id="10d1f-119">*すべてのユーザーがデータ アクセス可能*</span><span class="sxs-lookup"><span data-stu-id="10d1f-119">*Data accessible to all*</span></span>                                                     | <span data-ttu-id="10d1f-120">*管理者のみがデータ アクセス可能*</span><span class="sxs-lookup"><span data-stu-id="10d1f-120">*Data accessible to admins only*</span></span>                                             | <span data-ttu-id="10d1f-121">**データ削除済み<br/>他のサービスで使用されていない場合、Azure Active Directory は削除されます**</span><span class="sxs-lookup"><span data-stu-id="10d1f-121">**Data deleted<br/>Azure Active Directory is removed, if not in use by other services**</span></span> |
| <span data-ttu-id="10d1f-122">ユーザーは Office 365、データ、および Office アプリケーションに通常通りアクセスできます</span><span class="sxs-lookup"><span data-stu-id="10d1f-122">Users have normal access to Office 365, data, and Office applications</span></span>  | <span data-ttu-id="10d1f-123">ユーザーは Office 365、ファイル、およびアプリケーションに通常通りアクセスできます</span><span class="sxs-lookup"><span data-stu-id="10d1f-123">Users have normal access to Office 365, files, and applications</span></span>              | <span data-ttu-id="10d1f-124">ユーザーは Office 365、ファイル、またはアプリケーションにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="10d1f-124">Users can't access Office 365, files, or applications</span></span>                        | <span data-ttu-id="10d1f-125">ユーザーは Office 365、ファイル、またはアプリケーションにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="10d1f-125">Users can't access Office 365, files, or applications</span></span>                                     |
| <span data-ttu-id="10d1f-126">管理者は Office 365、データ、および Office アプリケーションに通常通りアクセスできます</span><span class="sxs-lookup"><span data-stu-id="10d1f-126">Admins have normal access to Office 365, data, and Office applications</span></span> | <span data-ttu-id="10d1f-127">管理者は管理センターにアクセスできますが、ユーザーにライセンスを割り当てることはできません</span><span class="sxs-lookup"><span data-stu-id="10d1f-127">Admins can access the admin center, but can't assign licenses to users</span></span>   | <span data-ttu-id="10d1f-128">管理者は管理センターにアクセスできますが、ユーザーにライセンスを割り当てることはできません</span><span class="sxs-lookup"><span data-stu-id="10d1f-128">Admins can access the admin center, but can't assign licenses to users</span></span>       | <span data-ttu-id="10d1f-129">管理者は管理センターにアクセスし、他のサブスクリプションを購入して管理することができます</span><span class="sxs-lookup"><span data-stu-id="10d1f-129">Admins can access the admin center to purchase and manage other subscriptions</span></span>             |
|                                                                        | <span data-ttu-id="10d1f-130">グローバル管理者または課金管理者は、管理センターでサブスクリプションを再アクティブ化できます</span><span class="sxs-lookup"><span data-stu-id="10d1f-130">Global or billing admins can reactivate the subscription in the admin center</span></span> | <span data-ttu-id="10d1f-131">グローバル管理者または課金管理者は、管理センターでサブスクリプションを再アクティブ化できます</span><span class="sxs-lookup"><span data-stu-id="10d1f-131">Global or billing admins can reactivate the subscription in the admin center</span></span> |                                                                                           |

<span data-ttu-id="10d1f-132">\*ほとんどの国と地域で、ほとんどのオファーについて。</span><span class="sxs-lookup"><span data-stu-id="10d1f-132">\*For most offers, in most countries and regions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10d1f-133">**"顧客データ" とは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="10d1f-133">**What is "customer data"?**</span></span> <span data-ttu-id="10d1f-134">[Microsoft オンライン サービス条件](https://go.microsoft.com/fwlink/p/?LinkId=613649) に定義されている顧客データとは、お客様がお客様自身による Office 365 サービスの使用を通じてMicrosoft またはその代理人に提供するすべてのデータを指します。これにはすべてのテキスト、サウンド、イメージ ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-134">Customer data, as defined in the [Microsoft Online Service Terms](https://go.microsoft.com/fwlink/p/?LinkId=613649), refers to all data, including all text, sound, or image files that are provided to Microsoft by, or on behalf of, the customer through the customer's use of Office 365 services.</span></span> <span data-ttu-id="10d1f-135">顧客データの保護の詳細については、「[Microsoft Service Trust Portal の使用を開始する](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-135">To learn more about the protection of customer data, see the [Get started with the Microsoft Service Trust Portal](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662).</span></span>
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a><span data-ttu-id="10d1f-136">サブスクリプションの有効期限切れが近い場合</span><span class="sxs-lookup"><span data-stu-id="10d1f-136">What are my options if my subscription is about to expire?</span></span>

<span data-ttu-id="10d1f-137">サブスクリプションの有効期間中、自分と自分が管理するユーザーは、自分のデータ、サービス (メール、OneDrive for Business など)、Office アプリケーションに通常どおりアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-137">While a subscription is active, you and your end users have normal access to your data, services like email and OneDrive for Business, and Office applications.</span></span> <span data-ttu-id="10d1f-138">管理者には、サブスクリプションの期限日が近いことが、メールと管理センター経由で通知されます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-138">As the admin, you'll receive a series of notifications via email and in the admin center as your subscription nears its expiration date.</span></span>
  
<span data-ttu-id="10d1f-139">実際にサブスクリプションの期限日になる前は、以下のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-139">Before the subscription actually reaches its expiration date, you have a few options:</span></span>

::: moniker range="o365-worldwide"
  
- <span data-ttu-id="10d1f-140">**サブスクリプションの継続請求を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-140">**Enable recurring billing for the subscription.**</span></span>

  - <span data-ttu-id="10d1f-141">**継続請求**が既に有効になっている場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-141">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="10d1f-142">サブスクリプションは自動的に請求され、現在の支払回数に応じて、追加された年分または月分の料金が課せられます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-142">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="10d1f-143">何らかの理由で**継続請求**を有効にした場合は、いつでも[継続請求を無効に戻す](renew-your-subscription.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-143">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

  - <span data-ttu-id="10d1f-144">プリペイド カードで Office 365 Business を購入した場合は、サブスクリプションの[継続請求](renew-your-subscription.md)を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-144">If you purchased Office 365 Business with a prepaid card, you can [turn on Recurring billing](renew-your-subscription.md) for your subscription.</span></span>

  - <span data-ttu-id="10d1f-p108">プリペイド版の1年間のサブスクリプションを備えた Open Volume ライセンスをお持ちの場合は、パートナーに連絡して新しいプロダクトキーを購入してください。[ボリュームライセンスサービスセンター](https://go.microsoft.com/fwlink/p/?LinkID=282016)でキーをライセンス認証するために、電子メールで指示を受信します。新しいパートナー、または過去に作業したパートナーを検索する方法については、「[パートナーまたは販売店を検索](../../admin/manage/find-your-partner-or-reseller.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p108">If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key. You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). To learn how to find a new partner, or the partner you've worked with in the past, see [Find your partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).</span></span>

  - <span data-ttu-id="10d1f-148">Office 365 Business をお持ちの場合、「[サブスクリプションの継続請求を管理する](renew-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-148">If you have Office 365 Business, see [Manage recurring billing for your subscription](renew-your-subscription.md).</span></span>

- <span data-ttu-id="10d1f-149">**そのままサブスクリプションを期限切れにします。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-149">**Let the subscription expire.**</span></span>

  - <span data-ttu-id="10d1f-150">クレジット カードまたは請求書を使って支払っており、サブスクリプションを継続しない場合は、[継続請求を無効にします](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="10d1f-150">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="10d1f-151">サブスクリプションは期限日で期限切れとなり、関連するすべてのメール通知は無視して構いません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-151">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

  - <span data-ttu-id="10d1f-152">パートナーと連携しているオープン ボリューム ライセンス ユーザーの場合は、手続きを取らなければ、サブスクリプションを期限切れにすることができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-152">If you're an Open Volume Licensing customer working with a partner, you can let your subscription expire by taking no action.</span></span>

  - <span data-ttu-id="10d1f-153">Office 365 Small Business Premium ユーザーであり、Office 365 の支払いとプロダクト キーによるアクティブ化が終わっている場合は、手続きを取らなければ、サブスクリプションを期限切れにすることができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-153">If you're a Office 365 Small Business Premium customer, and you prepaid for Office 365 and activated it with a product key, you can let your subscription expire by taking no action.</span></span>

- <span data-ttu-id="10d1f-154">**サブスクリプションの有効期限が切れる前にキャンセルします。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-154">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="10d1f-155">詳細については、「[サブスクリプションをキャンセルする](cancel-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-155">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
  
- <span data-ttu-id="10d1f-156">**サブスクリプションの継続請求を管理します。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-156">**Manage recurring billing for the subscription.**</span></span>

  - <span data-ttu-id="10d1f-157">**継続請求**が既に有効になっている場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-157">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="10d1f-158">サブスクリプションは自動的に請求され、現在の支払回数に応じて、追加された年分または月分の料金が課せられます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-158">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="10d1f-159">何らかの理由で**継続請求**を有効にした場合は、いつでも[継続請求を無効に戻す](renew-your-subscription.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-159">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

  - <span data-ttu-id="10d1f-160">プリペイド カードで Office 365 Business を購入した場合は、サブスクリプションの[継続請求](renew-your-subscription.md)を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-160">If you purchased Office 365 Business with a prepaid card, you can [turn on Recurring billing](renew-your-subscription.md) for your subscription.</span></span>

  - <span data-ttu-id="10d1f-p112">プリペイド版の1年間のサブスクリプションを備えた Open Volume ライセンスをお持ちの場合は、パートナーに連絡して新しいプロダクトキーを購入してください。[ボリュームライセンスサービスセンター](https://go.microsoft.com/fwlink/p/?LinkID=282016)でキーをライセンス認証するために、電子メールで指示を受信します。新しいパートナー、または過去に作業したパートナーを検索する方法については、「[パートナーまたは販売店を検索](../../admin/manage/find-your-partner-or-reseller.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p112">If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key. You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). To learn how to find a new partner, or the partner you've worked with in the past, see [Find your partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).</span></span>

  - <span data-ttu-id="10d1f-164">Office 365 Business を使用している場合は、「[サブスクリプションの更新](renew-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-164">If you have Office 365 Business, see [Renew your subscription](renew-your-subscription.md).</span></span>

- <span data-ttu-id="10d1f-165">**そのままサブスクリプションを期限切れにする**</span><span class="sxs-lookup"><span data-stu-id="10d1f-165">**Let the subscription expire.**</span></span>

  - <span data-ttu-id="10d1f-166">クレジット カードまたは請求書を使って支払っており、サブスクリプションを継続しない場合は、[継続請求を無効にします](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="10d1f-166">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="10d1f-167">サブスクリプションは期限日で期限切れとなり、関連するすべてのメール通知は無視して構いません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-167">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

  - <span data-ttu-id="10d1f-168">パートナーと連携しているオープン ボリューム ライセンス ユーザーの場合は、手続きを取らなければ、サブスクリプションを期限切れにすることができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-168">If you're an Open Volume Licensing customer working with a partner, you can let your subscription expire by taking no action.</span></span>

  - <span data-ttu-id="10d1f-169">Office 365 Small Business Premium ユーザーであり、Office 365 の支払いとプロダクト キーによるアクティブ化が終わっている場合は、手続きを取らなければ、サブスクリプションを期限切れにすることができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-169">If you're a Office 365 Small Business Premium customer, and you prepaid for Office 365 and activated it with a product key, you can let your subscription expire by taking no action.</span></span>

- <span data-ttu-id="10d1f-170">**サブスクリプションの有効期限が切れる前にキャンセルします。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-170">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="10d1f-171">詳細については、「[サブスクリプションをキャンセルする](cancel-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-171">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- <span data-ttu-id="10d1f-172">**サブスクリプションを更新します。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-172">**Renew the subscription.**</span></span> <span data-ttu-id="10d1f-173">**継続請求**が既に有効になっている場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-173">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="10d1f-174">サブスクリプションは自動的に請求され、現在の支払回数に応じて、追加された年分または月分の料金が課せられます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-174">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="10d1f-175">何らかの理由で**継続請求**を有効にした場合は、いつでも[継続請求を無効に戻す](renew-your-subscription.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-175">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

- <span data-ttu-id="10d1f-176">**そのままサブスクリプションを期限切れにします。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-176">**Let the subscription expire.**</span></span> <span data-ttu-id="10d1f-177">クレジット カードまたは請求書を使って支払っており、サブスクリプションを継続しない場合は、[継続請求を無効にします](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="10d1f-177">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="10d1f-178">有効期限日を過ぎるとサブスクリプションは期限切れになり、関連するメール通知はすべて無視できます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-178">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

- <span data-ttu-id="10d1f-179">**サブスクリプションの有効期限が切れる前にキャンセルします。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-179">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="10d1f-180">詳細については、「[サブスクリプションをキャンセルする](cancel-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-180">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a><span data-ttu-id="10d1f-181">サブスクリプションの有効期限が切れた場合</span><span class="sxs-lookup"><span data-stu-id="10d1f-181">What happens after my subscription expires?</span></span>
<span data-ttu-id="10d1f-182">サブスクリプションの有効期限が切れた場合、最終的に削除される前に複数の状態を経ます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-182">If you let your subscription expire, it goes through multiple states before it is ultimately deleted.</span></span> <span data-ttu-id="10d1f-183">これにより管理者には、サービスを継続する場合は再アクティブ化する時間、今後サブスクリプションを使用しない場合はデータをバックアップする時間があります。</span><span class="sxs-lookup"><span data-stu-id="10d1f-183">This gives you, as the admin, time to reactivate if you want to continue the service, or to back up your data if you decide you no longer want the subscription.</span></span>
  
<span data-ttu-id="10d1f-184">サブスクリプションの各状態で想定される動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="10d1f-184">Here's what you can expect when your subscription is in each state.</span></span>
  
### <a name="state-expired"></a><span data-ttu-id="10d1f-185">状態: 期限切れ</span><span class="sxs-lookup"><span data-stu-id="10d1f-185">State: Expired</span></span>
  
::: moniker range="o365-worldwide"

 <span data-ttu-id="10d1f-p119">**想定される動作:** 期限切れの状態は、 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298) 経由で購入したサブスクリプションを含む、ほとんどのサブスクリプションおよびほとんどの国と地域で 30 日間です。ボリューム ライセンス製品の場合、Microsoft Open を除いて、期限切れの状態は 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p119">**What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions. For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 <span data-ttu-id="10d1f-p120">**想定される動作:** 期限切れの状態は、 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298) 経由で購入したサブスクリプションを含む、ほとんどのサブスクリプションおよびほとんどの国と地域で 30 日間です。ボリューム ライセンス製品の場合、Microsoft Open を除いて、期限切れの状態は 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p120">**What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions. For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 <span data-ttu-id="10d1f-190">**想定される動作:** 猶予期間は、ほとんどのサブスクリプションおよび大部分の国と地域で 30 日間です。</span><span class="sxs-lookup"><span data-stu-id="10d1f-190">**What to expect:** The expired state is 30 days for most subscriptions, in most countries and regions.</span></span>

::: moniker-end

<span data-ttu-id="10d1f-191">この状態で、ユーザーは、Office 365 ポータル、Office アプリケーション、サービス (メールや SharePoint Online など) に正常にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-191">In this state, users have normal access to the Office 365 portal, Office applications, and services such as email and SharePoint Online.</span></span>
  
<span data-ttu-id="10d1f-192">管理者は管理センターにアクセスできますが、ユーザーにライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-192">As an admin, you still have access to the admin center, but can't assign licenses to users.</span></span> <span data-ttu-id="10d1f-193">グローバルまたは課金管理者は[、サブスクリプションを再アクティブ化](reactivate-your-subscription.md)して、Office 365 を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-193">Global or billing admins can [reactivate the subscription](reactivate-your-subscription.md) and continue using Office 365.</span></span> <span data-ttu-id="10d1f-194">再アクティブ化しない場合は、必ず[データをバックアップ](back-up-data-before-switching-plans.md)してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-194">If you don't reactivate, be sure to [back up your data](back-up-data-before-switching-plans.md).</span></span>
  
### <a name="state-disabled"></a><span data-ttu-id="10d1f-195">状態: 無効</span><span class="sxs-lookup"><span data-stu-id="10d1f-195">State: Disabled</span></span>
  
::: moniker range="o365-worldwide"

 <span data-ttu-id="10d1f-p122">**想定される動作:** 期限切れ状態のときにサブスクリプションを再アクティブ化しなければ、無効状態に移行します。この期間は、ほとんどのサブスクリプションおよびほとんどの国と地域で 90 日間です。ボリューム ライセンス製品の場合、無効状態の期間は 30 日間です。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p122">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions. For Volume Licensing products, the disabled state lasts 30 days.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 <span data-ttu-id="10d1f-p123">**想定される動作:** 期限切れ状態のときにサブスクリプションを再アクティブ化しなければ、無効状態に移行します。この期間は、ほとんどのサブスクリプションおよびほとんどの国と地域で 90 日間です。ボリューム ライセンス製品の場合、無効状態の期間は 30 日間です。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p123">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions. For Volume Licensing products, the disabled state lasts 30 days.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 <span data-ttu-id="10d1f-200">**想定される動作:** 期限切れ状態のときにサブスクリプションを再アクティブ化しなければ、無効状態に移行します。期間は、ほとんどのサブスクリプションおよび大部分の国と地域で 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="10d1f-200">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which is 90 days for most subscriptions, in most countries and regions.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="10d1f-201">この状態では、アクセス権が大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="10d1f-201">In this state, your access decreases significantly.</span></span> <span data-ttu-id="10d1f-202">ユーザーはサインインすることも、メールや SharePoint Online などのサービスにアクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-202">Your users can't sign in, or access services like email or SharePoint Online.</span></span> <span data-ttu-id="10d1f-203">Office アプリケーションは最終的に読み取り専用の機能制限モードに移り、[ライセンスのない製品通知](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-203">Office applications eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).</span></span> <span data-ttu-id="10d1f-204">サインインして管理センターにアクセスすることはできますが、ユーザーにライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-204">You can still sign in and get to the admin center, but can't assign licenses to users.</span></span> <span data-ttu-id="10d1f-205">すべてのユーザー データ、メール、チーム サイト上のファイルを含む顧客データは、あなたと他の管理者のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-205">Your customer data, including all user data, email, and files on team sites, is available only to you and other admins.</span></span>

::: moniker-end

<span data-ttu-id="10d1f-p125">全体管理者または課金管理者は、[サブスクリプションを再アクティブ化](reactivate-your-subscription.md)し、すべての顧客データをそのまま残して Office 365 を引き続き使用することができます。再アクティブ化しない場合は、必ず[データをバックアップ](back-up-data-before-switching-plans.md)してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p125">As a global or billing admin, you can [reactivate the subscription](reactivate-your-subscription.md) and continue using Office 365 with all of your customer data intact. If you choose not to reactivate, be sure to [back up your data](back-up-data-before-switching-plans.md).</span></span>

### <a name="state-deprovisioned"></a><span data-ttu-id="10d1f-208">状態: プロビジョニング解除</span><span class="sxs-lookup"><span data-stu-id="10d1f-208">State: Deprovisioned</span></span>
  
 <span data-ttu-id="10d1f-209">**想定される動作:** 猶予状態または無効状態でサブスクリプションを再アクティブ化しない場合は、サブスクリプションのサービス提供が停止されます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-209">**What to expect:** If you don't reactivate your subscription while it is in grace or disabled, the subscription is deprovisioned.</span></span>
  
<span data-ttu-id="10d1f-p126">管理者とユーザーは、サブスクリプションに付属するサービスや Office アプリケーションへアクセスすることができなくなります。すべての顧客データ (ユーザー データ、ドキュメント、メールなど) は完全に削除され、いかなる方法でも復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p126">Admins and users no longer have access to the services or Office applications that came with the subscription. All customer data—from user data to documents and email—is permanently deleted and unable to be recovered in any way.</span></span>
  
<span data-ttu-id="10d1f-212">この時点では、サブスクリプションを再アクティブ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-212">At this point, you can't reactivate the subscription.</span></span> <span data-ttu-id="10d1f-213">しかし、全体管理者または課金管理者は、引き続き管理センター にアクセスして、他のサブスクリプションの管理や、ビジネス ニーズに合わせた新しいサブスクリプションの購入を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-213">However, as a global or billing admin, you can still access the admin center to manage other subscriptions, or to buy new subscriptions to meet your business needs.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10d1f-214">サービス提供が停止されているものと同じ種類の新しいサブスクリプションを追加しても、サービス提供が停止されているサブスクリプションと関連付けられたデータが復元されることはありません。</span><span class="sxs-lookup"><span data-stu-id="10d1f-214">Adding a new subscription of the same type that has been deprovisioned does not restore the data that was associated with the deprovisioned subscription.</span></span>

### <a name="what-happens-when-my-trial-ends"></a><span data-ttu-id="10d1f-215">試用期間が終了した場合</span><span class="sxs-lookup"><span data-stu-id="10d1f-215">What happens when my trial ends?</span></span>

<span data-ttu-id="10d1f-216">試用期間が終了すると、Office 365 を無料で使えなくなります。</span><span class="sxs-lookup"><span data-stu-id="10d1f-216">When your trial ends, you won't be able to continue using Office 365 for free.</span></span> <span data-ttu-id="10d1f-217">この場合、いくつかの選択肢があります。 </span><span class="sxs-lookup"><span data-stu-id="10d1f-217">You have a few options:</span></span>

::: moniker range="o365-worldwide"
- <span data-ttu-id="10d1f-218">**購入するOffice 365。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-218">**Buy Office 365.**</span></span> <span data-ttu-id="10d1f-219">試用期間が経過すると、猶予期間に入り、Office 365 を購入するまでの期間がさらに 30 日間与えられます (大部分の国と地域のほとんどの試用版が対象)。</span><span class="sxs-lookup"><span data-stu-id="10d1f-219">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="10d1f-220">試用版を有料サブスクリプションに切り替える方法については、「[一般法人向け Office 365 の試用版を購入する](../buy-a-subscription-from-your-free-trial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-220">To learn how to convert your trial into a paid subscription, see [Buy your trial version of Office 365 for business](../buy-a-subscription-from-your-free-trial.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"
- <span data-ttu-id="10d1f-221">**購入するOffice 365。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-221">**Buy Office 365.**</span></span> <span data-ttu-id="10d1f-222">試用期間が経過すると、猶予期間に入り、Office 365 を購入するまでの期間がさらに 30 日間与えられます (大部分の国と地域のほとんどの試用版が対象)。</span><span class="sxs-lookup"><span data-stu-id="10d1f-222">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="10d1f-223">試用版を有料サブスクリプションに切り替える方法については、「[一般法人向け Office 365 の試用版を購入する](../buy-a-subscription-from-your-free-trial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-223">To learn how to convert your trial into a paid subscription, see [Buy your trial version of Office 365 for business](../buy-a-subscription-from-your-free-trial.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"
- <span data-ttu-id="10d1f-224">**購入するOffice 365。**</span><span class="sxs-lookup"><span data-stu-id="10d1f-224">**Buy Office 365.**</span></span> <span data-ttu-id="10d1f-225">試用期間が経過すると、猶予期間に入り、Office 365 を購入するまでの期間がさらに 30 日間与えられます (大部分の国と地域のほとんどの試用版が対象)。</span><span class="sxs-lookup"><span data-stu-id="10d1f-225">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="10d1f-226">試用版を有料サブスクリプションに切り替える方法については、「[Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md)」(21Vianet が運営する Office 365 のサブスクリプションを購入する、または試用する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-226">To learn how to convert your trial into a paid subscription, see [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).</span></span>

::: moniker-end

- <span data-ttu-id="10d1f-p132">**試用期間を延長する**Office 365 を評価する時間がさらに必要なときには、試用期間を延長できる場合があります。[試用期間を延長する](../extend-your-trial.md)方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p132">**Extend your trial.** Need more time to evaluate Office 365? In certain cases, you may be able to [extend your trial](../extend-your-trial.md).</span></span>

- <span data-ttu-id="10d1f-p133">**試用版をキャンセルするか期限切れにする**Office 365 を購入しない場合は、試用版を期限切れにするか、[キャンセルする](cancel-your-subscription.md)ことができます。必要なデータは必ずバックアップしてください。30 日の猶予期間の終了直後に、試用版のアカウント情報とデータは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-p133">**Cancel the trial or let it expire.** If you decide not to buy Office 365, you can let your trial expire or [cancel it](cancel-your-subscription.md). Be sure to back up any data you want to keep. Soon after the 30 day grace period, your trial account information and data is permanently erased.</span></span>

## <a name="what-happens-if-i-cancel-a-subscription"></a><span data-ttu-id="10d1f-234">サブスクリプションをキャンセルした場合</span><span class="sxs-lookup"><span data-stu-id="10d1f-234">What happens if I cancel a subscription?</span></span>

<span data-ttu-id="10d1f-235">期間の終了日より前にサブスクリプションをキャンセルすると、サブスクリプションは期限切れ状態をスキップし、ほとんどの国と地域で無効状態 (ほとんどのサブスクリプションにおいて 90 日間) に直接移行します。</span><span class="sxs-lookup"><span data-stu-id="10d1f-235">If you cancel your subscription before its term end date, the subscription skips the expired state and moves directly into the disabled state, which is 90 days for most subscriptions, in most countries and regions.</span></span> <span data-ttu-id="10d1f-236">キャンセルする前に[データをバックアップする](back-up-data-before-switching-plans.md)ことをお勧めしますが、管理者として、無効状態にあっても組織のデータに引き続きアクセスしてバックアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-236">We recommend that you [back up your data](back-up-data-before-switching-plans.md) before canceling, but as an admin, you can still access and back up data for your organization while it is in the disabled state.</span></span> <span data-ttu-id="10d1f-237">残された顧客データは 90 日後に削除され、キャンセル後、180 日以内に削除されます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-237">Any customer data that you leave behind may be deleted after 90 days, and will be deleted no later than 180 days after cancellation.</span></span>
  
<span data-ttu-id="10d1f-238">サブスクリプションをキャンセルした場合に想定される動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="10d1f-238">Here's what to expect for you and your users if you cancel a subscription.</span></span>
  
- <span data-ttu-id="10d1f-239">**管理者アクセス** 管理者は、サインインして管理センターにアクセスでき、必要に応じて、他のサブスクリプションを購入できます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-239">**Admin access** Admins can still sign in and access the admin center, and buy other subscriptions as needed.</span></span> <span data-ttu-id="10d1f-240">全体管理者または課金管理者の場合は、すべてのデータを維持したまま[サブスクリプションを再アクティブ化する](reactivate-your-subscription.md)ことができる期間が 90 日間あります。</span><span class="sxs-lookup"><span data-stu-id="10d1f-240">As a global or billing admin, you have 90 days to [reactivate the subscription](reactivate-your-subscription.md) with all data intact.</span></span>

- <span data-ttu-id="10d1f-241">**ユーザー アクセス** ユーザーは、OneDrive for Business などのサービスの使用や、顧客データ (チーム サイトのメール、ドキュメントなど) へのアクセスができなくなります。</span><span class="sxs-lookup"><span data-stu-id="10d1f-241">**User access** Your users won't be able to use services like OneDrive for Business, or access customer data—for example, email or documents on team sites.</span></span> <span data-ttu-id="10d1f-242">Word、Excel などの Office アプリケーションは、最終的に読み取り専用の機能制限モードになり、 [ライセンスのない製品通知](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-242">Office applications, like Word and Excel, will eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).</span></span>

<span data-ttu-id="10d1f-243">キャンセルする方法については、「[サブスクリプションをキャンセルする](cancel-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-243">To learn how to cancel, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="10d1f-244">一般的な無効期間が終了する前にサブスクリプション データを削除する場合は、プロビジョニングの優先解除を依頼できます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-244">If you want your subscription data to be deleted before the typical Disabled period is over, you can request expedited deprovisioning.</span></span> <span data-ttu-id="10d1f-245">プロビジョニングの優先解除をリクエストすると、キャンセルから 3 日以内にサブスクリプション データが削除されます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-245">When you request expedited deprovisioning, your subscription data is deleted within 3 days of cancellation.</span></span> <span data-ttu-id="10d1f-246">プロビジョニングの優先解除を利用する場合は、[サポートに連絡してください](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="10d1f-246">To use expedited deprovisioning, [call support](../../admin/contact-support-for-business-products.md).</span></span>

> [!NOTE]
> <span data-ttu-id="10d1f-247">このページに記載された情報には、「[Microsoft ポリシーの免責事項および変更に関する通知 (英語)](https://go.microsoft.com/fwlink/p/?LinkId=613651)」が適用されます。</span><span class="sxs-lookup"><span data-stu-id="10d1f-247">The information on this page is subject to the [Microsoft Policy Disclaimer and Change Notice](https://go.microsoft.com/fwlink/p/?LinkId=613651).</span></span> <span data-ttu-id="10d1f-248">このサイトに定期的にアクセスして、変更がないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="10d1f-248">Return to this site periodically to review any changes.</span></span>
