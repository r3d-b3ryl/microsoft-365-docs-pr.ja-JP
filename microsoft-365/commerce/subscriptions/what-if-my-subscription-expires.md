---
title: サブスクリプションが終了したとき、データとアクセスはどうなりますか?
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
description: Office 365 for business のサブスクリプションの有効期限が切れたとき、または無効にされたとき、またはキャンセルしたときに、データがどうなるかについて説明します。
ms.openlocfilehash: 717beff94255fe669f9ce9bc733300679ffc3d53
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257674"
---
# <a name="what-happens-to-my-data-and-access-when-my-office-365-for-business-subscription-ends"></a><span data-ttu-id="d5ad4-103">一般法人向け Office 365 のサブスクリプションが終了したとき、データとアクセスはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="d5ad4-103">What happens to my data and access when my Office 365 for business subscription ends?</span></span>

<span data-ttu-id="d5ad4-104">サブスクリプションの有効期限が切れた場合、または解約を決定した場合は、Office 365 サービス、アプリケーション、および顧客データへのアクセスは、サブスクリプションが完全にオフになる前に、または*停止*される前に、複数の状態を通過します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-104">If your subscription ends—either because it expires, or because you decide to cancel—your access to Office 365 services, applications, and customer data go through multiple states before the subscription is fully turned off, or *deprovisioned*.</span></span> <span data-ttu-id="d5ad4-105">この進行状況を認識している場合は、サブスクリプションを遅すぎる前にアクティブな状態に戻すことができます。または、Office 365 を離れている場合は、最終的にデータが削除される前にデータをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-105">If you are aware of this progression, you'll be better equipped to return your subscription to an active state before it's too late, or—if you're leaving Office 365—back up your data before it is ultimately deleted.</span></span>
  
## <a name="office-365-for-business-subscription-lifecycle"></a><span data-ttu-id="d5ad4-106">一般法人向け Office 365:サブスクリプションのライフサイクル</span><span class="sxs-lookup"><span data-stu-id="d5ad4-106">Office 365 for business: Subscription lifecycle</span></span>
- <span data-ttu-id="d5ad4-107">サブスクリプションの有効期限が切れると、次の各ステージが実行されます。期限切れ/無効/停止。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-107">If your subscription expires, it goes through the following stages: Expired / Disabled / Deprovisioned.</span></span> <span data-ttu-id="d5ad4-108">期限切れのステージは、サブスクリプションが終了日に達した直後に開始されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-108">The Expired stage starts immediately after the subscription has reached its end date.</span></span>
- <span data-ttu-id="d5ad4-109">年間のサブスクリプションで定期的な請求をオフにした場合は、期限切れのサブスクリプションと同じステージが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-109">If you turn off recurring billing on your annual subscription, it goes through the same stages as an expired subscription.</span></span> <span data-ttu-id="d5ad4-110">最初の段階では、サブスクリプションの定期請求の設定をオフにした日付から開始するのではなく、年間のサブスクリプションの記念日が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-110">The first stage starts are the anniversary of the annual subscription, not starting on the date that you turned off the subscription's recurring billing setting.</span></span>
- <span data-ttu-id="d5ad4-111">毎月のサブスクリプションを取り消すと、そのサブスクリプションはすぐに無効になります (取り消しの日付)。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-111">If you cancel your monthly subscription, it will be disabled immediately (at the date of cancellation).</span></span> <span data-ttu-id="d5ad4-112">これは、ユーザーが直ちに Office 365 アセットにアクセスできなくなり、管理者のみが次の90日間データにアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-112">This means your users will lose access to the Office 365 assets immediately and only admins will have access to the data for the next 90 days.</span></span>

<span data-ttu-id="d5ad4-113">次の表では、有料の Office 365 サブスクリプションの有効期限が切れたときに予想できることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-113">The following table explains what you can expect when a paid Office 365 for business subscription expires.</span></span>

| <span data-ttu-id="d5ad4-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-114">**Active**</span></span>                                                             | <span data-ttu-id="d5ad4-115">**期限<br/>切れ (30\*日)**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-115">**Expired <br/>(30 days\*)**</span></span>                                                | <span data-ttu-id="d5ad4-116">**無効<br/>(90 日\*)**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-116">**Disabled <br/>(90 days\*)**</span></span>                                               | <span data-ttu-id="d5ad4-117">**プロビジョニング解除**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-117">**Deprovisioned**</span></span>                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="d5ad4-118">*すべてのデータにアクセス可能*</span><span class="sxs-lookup"><span data-stu-id="d5ad4-118">*Data accessible to all*</span></span>                                               | <span data-ttu-id="d5ad4-119">*すべてのデータにアクセス可能*</span><span class="sxs-lookup"><span data-stu-id="d5ad4-119">*Data accessible to all*</span></span>                                                     | <span data-ttu-id="d5ad4-120">*データは管理者のみがアクセスできます。*</span><span class="sxs-lookup"><span data-stu-id="d5ad4-120">*Data accessible to admins only*</span></span>                                             | <span data-ttu-id="d5ad4-121">**他の<br/>サービスによって使用されていない場合、Azure Active Directory が削除されます。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-121">**Data deleted<br/>Azure Active Directory is removed, if not in use by other services**</span></span> |
| <span data-ttu-id="d5ad4-122">ユーザーは Office 365、データ、および Office アプリケーションへの通常のアクセスが可能</span><span class="sxs-lookup"><span data-stu-id="d5ad4-122">Users have normal access to Office 365, data, and Office applications</span></span>  | <span data-ttu-id="d5ad4-123">ユーザーが Office 365、ファイル、アプリケーションに通常アクセスできる</span><span class="sxs-lookup"><span data-stu-id="d5ad4-123">Users have normal access to Office 365, files, and applications</span></span>              | <span data-ttu-id="d5ad4-124">ユーザーが Office 365、ファイル、またはアプリケーションにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="d5ad4-124">Users can't access Office 365, files, or applications</span></span>                        | <span data-ttu-id="d5ad4-125">ユーザーが Office 365、ファイル、またはアプリケーションにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="d5ad4-125">Users can't access Office 365, files, or applications</span></span>                                     |
| <span data-ttu-id="d5ad4-126">管理者は Office 365、データ、および Office アプリケーションへの通常のアクセスが可能</span><span class="sxs-lookup"><span data-stu-id="d5ad4-126">Admins have normal access to Office 365, data, and Office applications</span></span> | <span data-ttu-id="d5ad4-127">管理者は管理センターにアクセスできる</span><span class="sxs-lookup"><span data-stu-id="d5ad4-127">Admins can access the admin center</span></span>                                           | <span data-ttu-id="d5ad4-128">管理者は管理センターにアクセスできますが、ユーザーにライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-128">Admins can access the admin center, but can't assign licenses to users</span></span>       | <span data-ttu-id="d5ad4-129">管理者は管理センターにアクセスして、他のサブスクリプションを購入して管理できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-129">Admins can access the admin center to purchase and manage other subscriptions</span></span>             |
|                                                                        | <span data-ttu-id="d5ad4-130">グローバルまたは課金管理者が管理センターでサブスクリプションを再アクティブ化できる</span><span class="sxs-lookup"><span data-stu-id="d5ad4-130">Global or billing admins can reactivate the subscription in the admin center</span></span> | <span data-ttu-id="d5ad4-131">グローバルまたは課金管理者が管理センターでサブスクリプションを再アクティブ化できる</span><span class="sxs-lookup"><span data-stu-id="d5ad4-131">Global or billing admins can reactivate the subscription in the admin center</span></span> |                                                                                           |

<span data-ttu-id="d5ad4-132">\* ほとんどの場合、ほとんどの国や地域で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-132">\*For most offers, in most countries and regions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5ad4-133">**"顧客データ" とは**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-133">**What is "customer data"?**</span></span> <span data-ttu-id="d5ad4-134">[Microsoft Online Service](https://go.microsoft.com/fwlink/p/?LinkId=613649)の使用条件で定義されている顧客データとは、お客様が Office 365 サービスを使用して、microsoft によって提供された、またはお客様の代わりに提供されるすべてのテキスト、サウンド、画像ファイルを含むすべてのデータを指します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-134">Customer data, as defined in the [Microsoft Online Service Terms](https://go.microsoft.com/fwlink/p/?LinkId=613649), refers to all data, including all text, sound, or image files that are provided to Microsoft by, or on behalf of, the customer through the customer's use of Office 365 services.</span></span> <span data-ttu-id="d5ad4-135">顧客データの保護の詳細については、「 [Microsoft Service Trust Portal で作業を開始](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-135">To learn more about the protection of customer data, see the [Get started with the Microsoft Service Trust Portal](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662).</span></span>
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a><span data-ttu-id="d5ad4-136">サブスクリプションの有効期限切れが近い場合</span><span class="sxs-lookup"><span data-stu-id="d5ad4-136">What are my options if my subscription is about to expire?</span></span>

<span data-ttu-id="d5ad4-137">サブスクリプションがアクティブな間、ユーザーとエンドユーザーは、データへの通常のアクセス、電子メールや OneDrive for Business、Office アプリケーションなどのサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-137">While a subscription is active, you and your end users have normal access to your data, services like email and OneDrive for Business, and Office applications.</span></span> <span data-ttu-id="d5ad4-138">管理者は、サブスクリプションが有効期限に近づくと、電子メールと管理センターの一連の通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-138">As the admin, you'll receive a series of notifications via email and in the admin center as your subscription nears its expiration date.</span></span>
  
<span data-ttu-id="d5ad4-139">実際にサブスクリプションの期限日になる前は、以下のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-139">Before the subscription actually reaches its expiration date, you have a few options:</span></span>

::: moniker range="o365-worldwide"
  
- <span data-ttu-id="d5ad4-140">**サブスクリプションの定期的な請求を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-140">**Enable recurring billing for the subscription.**</span></span>

  - <span data-ttu-id="d5ad4-141">**定期的な請求書**が既に有効になっている場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-141">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="d5ad4-142">サブスクリプションは自動的に請求されます。現在の支払い頻度に応じて、追加の年または月に請求されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-142">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="d5ad4-143">何らかの理由で**定期的**な請求書をオフにした場合は、いつ[でも課金を再開](renew-your-subscription.md)できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-143">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

  - <span data-ttu-id="d5ad4-144">プリペイドカードを使用して Office 365 Business を購入した場合は、サブスクリプションの[定期請求を有効](renew-your-subscription.md)にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-144">If you purchased Office 365 Business with a prepaid card, you can [turn on Recurring billing](renew-your-subscription.md) for your subscription.</span></span>

  - <span data-ttu-id="d5ad4-p108">1 年間のプリペイド サブスクリプションを利用するオープン ボリューム ライセンス ユーザーの場合は、パートナーに連絡して、新しいプロダクト キーを購入してください。[ボリューム ライセンス サービス センター](https://go.microsoft.com/fwlink/p/?LinkID=282016)でキーをアクティブ化する手順をメールで受け取ります。新しいパートナーまたは以前のパートナーを見つける方法の詳細については、「[Office 365 パートナーまたはリセラーを見つける](../../admin/manage/find-your-partner-or-reseller.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p108">If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key. You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). To learn how to find a new partner, or the partner you've worked with in the past, see [Find your Office 365 partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).</span></span>

  - <span data-ttu-id="d5ad4-148">Office 365 Business をお持ちの場合、「[サブスクリプションの継続請求を管理する](renew-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-148">If you have Office 365 Business, see [Manage recurring billing for your subscription](renew-your-subscription.md).</span></span>

- <span data-ttu-id="d5ad4-149">**そのままサブスクリプションを期限切れにする**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-149">**Let the subscription expire.**</span></span>

  - <span data-ttu-id="d5ad4-150">クレジットカードまたは請求書で支払いを行っていて、サブスクリプションを続行しない場合は、[定期的な請求をオフ](renew-your-subscription.md)にします。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-150">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="d5ad4-151">有効期限日を過ぎるとサブスクリプションは期限切れになり、関連するメール通知はすべて無視できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-151">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

  - <span data-ttu-id="d5ad4-152">パートナーと連携するオープンボリュームライセンスのお客様は、何もしなくてもサブスクリプションの有効期限が切れることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-152">If you're an Open Volume Licensing customer working with a partner, you can let your subscription expire by taking no action.</span></span>

  - <span data-ttu-id="d5ad4-153">Office 365 Small Business Premium のお客様で、Office 365 にご参加いただき、プロダクトキーでライセンス認証を行っている場合は、何もしなくてもサブスクリプションを有効期限切れにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-153">If you're a Office 365 Small Business Premium customer, and you prepaid for Office 365 and activated it with a product key, you can let your subscription expire by taking no action.</span></span>

- <span data-ttu-id="d5ad4-154">**サブスクリプションの有効期限が切れる前にキャンセルします。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-154">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="d5ad4-155">詳細については、「[サブスクリプションのキャンセル](cancel-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-155">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
  
- <span data-ttu-id="d5ad4-156">**サブスクリプションの定期的な請求を管理します。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-156">**Manage recurring billing for the subscription.**</span></span>

  - <span data-ttu-id="d5ad4-157">**定期的な請求書**が既に有効になっている場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-157">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="d5ad4-158">サブスクリプションは自動的に請求されます。現在の支払い頻度に応じて、追加の年または月に請求されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-158">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="d5ad4-159">何らかの理由で**定期的**な請求書をオフにした場合は、いつ[でも課金を再開](renew-your-subscription.md)できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-159">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

  - <span data-ttu-id="d5ad4-160">プリペイドカードを使用して Office 365 Business を購入した場合は、サブスクリプションの[定期請求を有効](renew-your-subscription.md)にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-160">If you purchased Office 365 Business with a prepaid card, you can [turn on Recurring billing](renew-your-subscription.md) for your subscription.</span></span>

  - <span data-ttu-id="d5ad4-p112">1 年間のプリペイド サブスクリプションを利用するオープン ボリューム ライセンス ユーザーの場合は、パートナーに連絡して、新しいプロダクト キーを購入してください。[ボリューム ライセンス サービス センター](https://go.microsoft.com/fwlink/p/?LinkID=282016)でキーをアクティブ化する手順をメールで受け取ります。新しいパートナーまたは以前のパートナーを見つける方法の詳細については、「[Office 365 パートナーまたはリセラーを見つける](../../admin/manage/find-your-partner-or-reseller.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p112">If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key. You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). To learn how to find a new partner, or the partner you've worked with in the past, see [Find your Office 365 partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).</span></span>

  - <span data-ttu-id="d5ad4-164">Office 365 Business をご使用の場合は、「[一般法人向け Office 365 の更新](renew-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-164">If you have Office 365 Business, see [Renew Office 365 for business](renew-your-subscription.md).</span></span>

- <span data-ttu-id="d5ad4-165">**そのままサブスクリプションを期限切れにする**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-165">**Let the subscription expire.**</span></span>

  - <span data-ttu-id="d5ad4-166">クレジットカードまたは請求書で支払いを行っていて、サブスクリプションを続行しない場合は、[定期的な請求をオフ](renew-your-subscription.md)にします。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-166">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="d5ad4-167">有効期限日を過ぎるとサブスクリプションは期限切れになり、関連するメール通知はすべて無視できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-167">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

  - <span data-ttu-id="d5ad4-168">パートナーと連携するオープンボリュームライセンスのお客様は、何もしなくてもサブスクリプションの有効期限が切れることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-168">If you're an Open Volume Licensing customer working with a partner, you can let your subscription expire by taking no action.</span></span>

  - <span data-ttu-id="d5ad4-169">Office 365 Small Business Premium のお客様で、Office 365 にご参加いただき、プロダクトキーでライセンス認証を行っている場合は、何もしなくてもサブスクリプションを有効期限切れにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-169">If you're a Office 365 Small Business Premium customer, and you prepaid for Office 365 and activated it with a product key, you can let your subscription expire by taking no action.</span></span>

- <span data-ttu-id="d5ad4-170">**サブスクリプションの有効期限が切れる前にキャンセルします。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-170">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="d5ad4-171">詳細については、「[サブスクリプションのキャンセル](cancel-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-171">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- <span data-ttu-id="d5ad4-172">**サブスクリプションを更新する**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-172">**Renew the subscription.**</span></span> <span data-ttu-id="d5ad4-173">**定期的な請求書**が既に有効になっている場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-173">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="d5ad4-174">サブスクリプションは自動的に請求されます。現在の支払い頻度に応じて、追加の年または月に請求されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-174">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="d5ad4-175">何らかの理由で**定期的**な請求書をオフにした場合は、いつ[でも課金を再開](renew-your-subscription.md)できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-175">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

- <span data-ttu-id="d5ad4-176">**そのままサブスクリプションを期限切れにする**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-176">**Let the subscription expire.**</span></span> <span data-ttu-id="d5ad4-177">クレジットカードまたは請求書で支払いを行っていて、サブスクリプションを続行しない場合は、[定期的な請求をオフ](renew-your-subscription.md)にします。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-177">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="d5ad4-178">有効期限日を過ぎるとサブスクリプションは期限切れになり、関連するメール通知はすべて無視できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-178">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

- <span data-ttu-id="d5ad4-179">**サブスクリプションの有効期限が切れる前にキャンセルします。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-179">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="d5ad4-180">詳細については、「[サブスクリプションのキャンセル](cancel-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-180">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a><span data-ttu-id="d5ad4-181">サブスクリプションの有効期限が切れた場合</span><span class="sxs-lookup"><span data-stu-id="d5ad4-181">What happens after my subscription expires?</span></span>
<span data-ttu-id="d5ad4-182">サブスクリプションの有効期限が切れると、最終的に削除される前に、複数の状態が発生します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-182">If you let your subscription expire, it goes through multiple states before it is ultimately deleted.</span></span> <span data-ttu-id="d5ad4-183">これにより、管理者は、サービスを継続する場合は再アクティブ化する時間、サブスクリプションを必要としなくなった場合はデータをバックアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-183">This gives you, as the admin, time to reactivate if you want to continue the service, or to back up your data if you decide you no longer want the subscription.</span></span>
  
<span data-ttu-id="d5ad4-184">サブスクリプションの各状態で想定される動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-184">Here's what you can expect when your subscription is in each state.</span></span>
  
### <a name="state-expired"></a><span data-ttu-id="d5ad4-185">状態: 期限切れ</span><span class="sxs-lookup"><span data-stu-id="d5ad4-185">State: Expired</span></span>
  
::: moniker range="o365-worldwide"

 <span data-ttu-id="d5ad4-p119">**想定される動作:** 期限切れの状態は、 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298) 経由で購入したサブスクリプションを含む、ほとんどのサブスクリプションおよびほとんどの国と地域で 30 日間です。ボリューム ライセンス製品の場合、Microsoft Open を除いて、期限切れの状態は 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p119">**What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions. For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 <span data-ttu-id="d5ad4-p120">**想定される動作:** 期限切れの状態は、 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298) 経由で購入したサブスクリプションを含む、ほとんどのサブスクリプションおよびほとんどの国と地域で 30 日間です。ボリューム ライセンス製品の場合、Microsoft Open を除いて、期限切れの状態は 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p120">**What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions. For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 <span data-ttu-id="d5ad4-190">**想定される動作:** 猶予期間は、ほとんどのサブスクリプションおよび大部分の国と地域で 30 日間です。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-190">**What to expect:** The expired state is 30 days for most subscriptions, in most countries and regions.</span></span>

::: moniker-end

<span data-ttu-id="d5ad4-191">この状態では、ユーザーは Office 365 ポータル、Office アプリケーション、および電子メールや SharePoint Online などのサービスへの通常のアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-191">In this state, users have normal access to the Office 365 portal, Office applications, and services such as email and SharePoint Online.</span></span>
  
<span data-ttu-id="d5ad4-192">管理者は管理センターにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-192">As an admin, you still have access to the admin center.</span></span> <span data-ttu-id="d5ad4-193">グローバルまたは課金管理者が[サブスクリプションを再アクティブ化](reactivate-your-subscription.md)して、Office 365 を引き続き使用できることを心配しないでください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-193">Don't worry—global or billing admins can [reactivate the subscription](reactivate-your-subscription.md) and continue using Office 365.</span></span> <span data-ttu-id="d5ad4-194">再アクティブ化しない場合は、必ず[データをバックアップ](back-up-data-before-switching-plans.md)してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-194">If you don't reactivate, be sure to [back up your data](back-up-data-before-switching-plans.md).</span></span>
  
### <a name="state-disabled"></a><span data-ttu-id="d5ad4-195">状態: 無効</span><span class="sxs-lookup"><span data-stu-id="d5ad4-195">State: Disabled</span></span>
  
::: moniker range="o365-worldwide"

 <span data-ttu-id="d5ad4-p122">**想定される動作:** 期限切れ状態のときにサブスクリプションを再アクティブ化しなければ、無効状態に移行します。この期間は、ほとんどのサブスクリプションおよびほとんどの国と地域で 90 日間です。ボリューム ライセンス製品の場合、無効状態の期間は 30 日間です。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p122">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions. For Volume Licensing products, the disabled state lasts 30 days.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 <span data-ttu-id="d5ad4-p123">**想定される動作:** 期限切れ状態のときにサブスクリプションを再アクティブ化しなければ、無効状態に移行します。この期間は、ほとんどのサブスクリプションおよびほとんどの国と地域で 90 日間です。ボリューム ライセンス製品の場合、無効状態の期間は 30 日間です。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p123">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions. For Volume Licensing products, the disabled state lasts 30 days.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 <span data-ttu-id="d5ad4-200">**想定される動作:** 期限切れ状態のときにサブスクリプションを再アクティブ化しなければ、無効状態に移行します。期間は、ほとんどのサブスクリプションおよび大部分の国と地域で 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-200">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which is 90 days for most subscriptions, in most countries and regions.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="d5ad4-201">この状態では、アクセスが大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-201">In this state, your access decreases significantly.</span></span> <span data-ttu-id="d5ad4-202">ユーザーがサインインできない、または電子メールや SharePoint Online などのサービスにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-202">Your users can't sign in, or access services like email or SharePoint Online.</span></span> <span data-ttu-id="d5ad4-203">Office アプリケーションは、最終的に読み取り専用で機能制限モードに移行し、ライセンスのない[製品通知](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)を表示します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-203">Office applications eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).</span></span> <span data-ttu-id="d5ad4-204">引き続きサインインして管理センターにアクセスすることはできますが、ユーザーにライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-204">You can still sign in and get to the admin center, but can't assign licenses to users.</span></span> <span data-ttu-id="d5ad4-205">チームサイトのすべてのユーザーデータ、電子メール、およびファイルを含むお客様のデータは、自分と他の管理者のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-205">Your customer data, including all user data, email, and files on team sites, is available only to you and other admins.</span></span>

::: moniker-end

<span data-ttu-id="d5ad4-p125">全体管理者または課金管理者は、[サブスクリプションを再アクティブ化](reactivate-your-subscription.md)し、すべての顧客データをそのまま残して Office 365 を引き続き使用することができます。再アクティブ化しない場合は、必ず[データをバックアップ](back-up-data-before-switching-plans.md)してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p125">As a global or billing admin, you can [reactivate the subscription](reactivate-your-subscription.md) and continue using Office 365 with all of your customer data intact. If you choose not to reactivate, be sure to [back up your data](back-up-data-before-switching-plans.md).</span></span>

### <a name="state-deprovisioned"></a><span data-ttu-id="d5ad4-208">状態: 停止</span><span class="sxs-lookup"><span data-stu-id="d5ad4-208">State: Deprovisioned</span></span>
  
 <span data-ttu-id="d5ad4-209">**想定される動作:** 猶予状態または無効状態でサブスクリプションを再アクティブ化しない場合は、サブスクリプションのサービス提供が停止されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-209">**What to expect:** If you don't reactivate your subscription while it is in grace or disabled, the subscription is deprovisioned.</span></span>
  
<span data-ttu-id="d5ad4-p126">管理者とユーザーは、サブスクリプションに付属するサービスや Office アプリケーションへアクセスすることができなくなります。すべての顧客データ (ユーザー データ、ドキュメント、メールなど) は完全に削除され、いかなる方法でも復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p126">Admins and users no longer have access to the services or Office applications that came with the subscription. All customer data—from user data to documents and email—is permanently deleted and unable to be recovered in any way.</span></span>
  
<span data-ttu-id="d5ad4-212">この段階で、サブスクリプションを再アクティブ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-212">At this point, you can't reactivate the subscription.</span></span> <span data-ttu-id="d5ad4-213">ただし、グローバルまたは課金管理者は、管理センターにアクセスして他のサブスクリプションを管理することも、ビジネスニーズに合わせて新しいサブスクリプションを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-213">However, as a global or billing admin, you can still access the admin center to manage other subscriptions, or to buy new subscriptions to meet your business needs.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5ad4-214">サービス提供が停止されているものと同じ種類の新しいサブスクリプションを追加しても、サービス提供が停止されているサブスクリプションと関連付けられたデータが復元されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-214">Adding a new subscription of the same type that has been deprovisioned does not restore the data that was associated with the deprovisioned subscription.</span></span>

### <a name="what-happens-when-my-trial-ends"></a><span data-ttu-id="d5ad4-215">試用期間が終了した場合</span><span class="sxs-lookup"><span data-stu-id="d5ad4-215">What happens when my trial ends?</span></span>

<span data-ttu-id="d5ad4-216">試用期間が終了しても、Office 365 を無料で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-216">When your trial ends, you won't be able to continue using Office 365 for free.</span></span> <span data-ttu-id="d5ad4-217">この場合、いくつかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-217">You have a few options:</span></span>

::: moniker range="o365-worldwide"
- <span data-ttu-id="d5ad4-218">**購入するOffice 365。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-218">**Buy Office 365.**</span></span> <span data-ttu-id="d5ad4-219">試用期間が経過すると、猶予期間に入り、Office 365 を購入するまでの期間がさらに 30 日間与えられます (大部分の国と地域のほとんどの試用版が対象)。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-219">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="d5ad4-220">試用版を有料サブスクリプションに切り替える方法については、「[一般法人向け Office 365 の試用版を購入する](../buy-a-subscription-from-your-free-trial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-220">To learn how to convert your trial into a paid subscription, see [Buy your trial version of Office 365 for business](../buy-a-subscription-from-your-free-trial.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"
- <span data-ttu-id="d5ad4-221">**購入するOffice 365。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-221">**Buy Office 365.**</span></span> <span data-ttu-id="d5ad4-222">試用期間が経過すると、猶予期間に入り、Office 365 を購入するまでの期間がさらに 30 日間与えられます (大部分の国と地域のほとんどの試用版が対象)。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-222">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="d5ad4-223">試用版を有料サブスクリプションに切り替える方法については、「[一般法人向け Office 365 の試用版を購入する](../buy-a-subscription-from-your-free-trial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-223">To learn how to convert your trial into a paid subscription, see [Buy your trial version of Office 365 for business](../buy-a-subscription-from-your-free-trial.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"
- <span data-ttu-id="d5ad4-224">**購入するOffice 365。**</span><span class="sxs-lookup"><span data-stu-id="d5ad4-224">**Buy Office 365.**</span></span> <span data-ttu-id="d5ad4-225">試用期間が経過すると、猶予期間に入り、Office 365 を購入するまでの期間がさらに 30 日間与えられます (大部分の国と地域のほとんどの試用版が対象)。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-225">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="d5ad4-226">試用版を有料サブスクリプションに切り替える方法については、「[Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md)」(21Vianet が運営する Office 365 のサブスクリプションを購入する、または試用する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-226">To learn how to convert your trial into a paid subscription, see [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).</span></span>

::: moniker-end

- <span data-ttu-id="d5ad4-p132">**試用期間を延長する**Office 365 を評価する時間がさらに必要なときには、試用期間を延長できる場合があります。[試用期間を延長する](../extend-your-trial.md)方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p132">**Extend your trial.** Need more time to evaluate Office 365? In certain cases, you may be able to [extend your trial](../extend-your-trial.md).</span></span>

- <span data-ttu-id="d5ad4-p133">**試用版をキャンセルするか期限切れにする**Office 365 を購入しない場合は、試用版を期限切れにするか、[キャンセルする](cancel-your-subscription.md)ことができます。必要なデータは必ずバックアップしてください。30 日の猶予期間の終了直後に、試用版のアカウント情報とデータは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-p133">**Cancel the trial or let it expire.** If you decide not to buy Office 365, you can let your trial expire or [cancel it](cancel-your-subscription.md). Be sure to back up any data you want to keep. Soon after the 30 day grace period, your trial account information and data is permanently erased.</span></span>

## <a name="what-happens-if-i-cancel-a-subscription"></a><span data-ttu-id="d5ad4-234">サブスクリプションをキャンセルした場合</span><span class="sxs-lookup"><span data-stu-id="d5ad4-234">What happens if I cancel a subscription?</span></span>

<span data-ttu-id="d5ad4-235">サブスクリプションを期間終了日よりも前に解約した場合、サブスクリプションは期限切れの状態をスキップして、ほとんどの国や地域で、ほとんどのサブスクリプションでは90日に無効化された状態に進みます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-235">If you cancel your subscription before its term end date, the subscription skips the expired state and moves directly into the disabled state, which is 90 days for most subscriptions, in most countries and regions.</span></span> <span data-ttu-id="d5ad4-236">キャンセルする前に[データをバックアップ](back-up-data-before-switching-plans.md)することをお勧めしますが、管理者としては、無効な状態のときでも、組織のデータにアクセスしてバックアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-236">We recommend that you [back up your data](back-up-data-before-switching-plans.md) before canceling, but as an admin, you can still access and back up data for your organization while it is in the disabled state.</span></span> <span data-ttu-id="d5ad4-237">残された顧客データは 90 日後に削除され、キャンセル後、180 日以内に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-237">Any customer data that you leave behind may be deleted after 90 days, and will be deleted no later than 180 days after cancellation.</span></span>
  
<span data-ttu-id="d5ad4-238">サブスクリプションをキャンセルした場合に想定される動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-238">Here's what to expect for you and your users if you cancel a subscription.</span></span>
  
- <span data-ttu-id="d5ad4-239">**管理者アクセス**管理者は引き続きサインインして、管理センターにアクセスし、必要に応じて他のサブスクリプションを購入できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-239">**Admin access** Admins can still sign in and access the admin center, and buy other subscriptions as needed.</span></span> <span data-ttu-id="d5ad4-240">グローバルまたは課金管理者は、すべてのデータを保持したまま[サブスクリプションを再アクティブ化](reactivate-your-subscription.md)するのに90日を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-240">As a global or billing admin, you have 90 days to [reactivate the subscription](reactivate-your-subscription.md) with all data intact.</span></span>

- <span data-ttu-id="d5ad4-241">**ユーザーアクセス**ユーザーが OneDrive for business などのサービスを使用したり、顧客データにアクセスしたりすることはできません。たとえば、チームサイトの電子メールやドキュメントなどです。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-241">**User access** Your users won't be able to use services like OneDrive for Business, or access customer data—for example, email or documents on team sites.</span></span> <span data-ttu-id="d5ad4-242">Word、Excel などの Office アプリケーションは、最終的に読み取り専用の機能制限モードになり、 [ライセンスのない製品通知](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-242">Office applications, like Word and Excel, will eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).</span></span>

<span data-ttu-id="d5ad4-243">取り消す方法については、「[サブスクリプションの取り消し](cancel-your-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-243">To learn how to cancel, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d5ad4-244">一般的な無効期間が終了する前にサブスクリプションデータを削除する場合は、優先プロビジョニングを要求できます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-244">If you want your subscription data to be deleted before the typical Disabled period is over, you can request expedited deprovisioning.</span></span> <span data-ttu-id="d5ad4-245">プロビジョニングの優先解除を依頼した場合、サブスクリプション データはキャンセルから 3 日以内に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-245">When you request expedited deprovisioning, your subscription data is deleted within 3 days of cancellation.</span></span> <span data-ttu-id="d5ad4-246">優先プロビジョニング機能を使用するには、[サポート] を[呼び出し](../../admin/contact-support-for-business-products.md)ます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-246">To use expedited deprovisioning, [call support](../../admin/contact-support-for-business-products.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d5ad4-247">このページに記載された情報には、「[Microsoft ポリシーの免責事項および変更に関する通知 (英語)](https://go.microsoft.com/fwlink/p/?LinkId=613651)」が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-247">The information on this page is subject to the [Microsoft Policy Disclaimer and Change Notice](https://go.microsoft.com/fwlink/p/?LinkId=613651).</span></span> <span data-ttu-id="d5ad4-248">このサイトに定期的に戻り、変更内容を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-248">Return to this site periodically to review any changes.</span></span>
