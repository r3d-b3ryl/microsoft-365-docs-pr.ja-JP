---
title: 標準または対象指定リリースオプションを設定する
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Microsoft 365 管理センターで新しい製品および機能の更新プログラムのリリースオプションをセットアップする方法について説明します。
ms.openlocfilehash: 3baec050f33893357b25c832552643cf3a6d10d0
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502881"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="47218-103">標準または対象指定リリースオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="47218-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="47218-104">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="47218-104">The admin center is changing.</span></span> <span data-ttu-id="47218-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47218-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="47218-106">Microsoft 365 では、数年ごとに費用のかかる更新プログラムを実行する代わりに、新しい製品の更新プログラムと機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="47218-106">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="47218-107">組織がこれらの更新を受信する方法を管理できます。</span><span class="sxs-lookup"><span data-stu-id="47218-107">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="47218-108">たとえば、初期リリースにサインアップして、組織が最初に更新を受け取るようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="47218-108">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="47218-109">特定の個人のみが更新を受信するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="47218-109">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="47218-110">または、[既定のリリーススケジュール] をそのまま使用し、更新プログラムを後で受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="47218-110">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="47218-111">この記事では、さまざまなリリースオプションと、それらを組織で使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47218-111">This article explains the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="47218-112">この記事に記載されている Microsoft 365 更新プログラムは、Microsoft 365、SharePoint Online、および Exchange Online に適用されます。</span><span class="sxs-lookup"><span data-stu-id="47218-112">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="47218-113">これらは、Skype for Business および関連するサービスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="47218-113">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="47218-114">これらのリリースオプションは、Microsoft 365 への変更をリリースするための最善の方法ですが、常に、またはすべての更新プログラムに対して保証することはできません。</span><span class="sxs-lookup"><span data-stu-id="47218-114">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="47218-115">アプリケーションの更新プログラムチャネルの詳細については、「 [Microsoft 365 アプリの更新プログラムチャネルの概要](https://docs.microsoft.com/deployoffice/overview-update-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47218-115">For information about update channels for applications, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="47218-116">しくみ - リリースの検証</span><span class="sxs-lookup"><span data-stu-id="47218-116">How it works - release validation</span></span>

<span data-ttu-id="47218-117">新しいリリースはすべて、最初に機能チームによってテストおよび検証され、次に Microsoft 365 機能チーム全体によって、その後にすべての Microsoft が評価されます。</span><span class="sxs-lookup"><span data-stu-id="47218-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="47218-118">内部テストと検証が終わったら、次の手順は参加しているお客様に向けた **対象指定リリース** (以前は先行リリースと呼ばれていました) です。</span><span class="sxs-lookup"><span data-stu-id="47218-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="47218-119">各リリース リングで、Microsoft はフィードバックを収集し、主要な利用状況メトリックを監視することでさらに品質を検証します。</span><span class="sxs-lookup"><span data-stu-id="47218-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="47218-120">この革新的な一連の検証は、全世界のリリースの信頼性を最大限に高めるためにあります。</span><span class="sxs-lookup"><span data-stu-id="47218-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="47218-121">各リリースを、次の図で示します。</span><span class="sxs-lookup"><span data-stu-id="47218-121">The releases are pictured in the following figure.</span></span> 
  
![Microsoft 365 のリリース検証リング](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="47218-123">重要な更新プログラムについては、お客様には[Microsoft 365 ロードマップ](https://products.office.com/business/office-365-roadmap)による通知が最初に行われます。</span><span class="sxs-lookup"><span data-stu-id="47218-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="47218-124">更新プログラムのロールアウトが近づくにつれて、 [Microsoft 365 メッセージセンター](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)を経由して通知されます。</span><span class="sxs-lookup"><span data-stu-id="47218-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="47218-125">[管理センター](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)を使用してメッセージセンターにアクセスするには、Microsoft 365 または Azure AD アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="47218-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="47218-126">Microsoft 365 home プランユーザーには管理センターがありません。</span><span class="sxs-lookup"><span data-stu-id="47218-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="47218-127">標準リリース</span><span class="sxs-lookup"><span data-stu-id="47218-127">Standard release</span></span>

<span data-ttu-id="47218-128">これは、ユーザーがすべてのお客様に幅広くリリースされている場合に最新の更新プログラムを受信する既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="47218-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="47218-129">ユーザーの大部分を**標準のリリース**と IT プロフェッショナルおよびパワーユーザーに任せて、新しい機能を評価し、ビジネスユーザーと役員をサポートするチームを**準備すること**をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47218-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="47218-130">対象指定リリースから標準リリースに切り替えた場合、ユーザーは標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47218-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="47218-131">対象となるリリース</span><span class="sxs-lookup"><span data-stu-id="47218-131">Targeted release</span></span>

<span data-ttu-id="47218-p107">このオプションでは、お客様とお客様のユーザーは最新の更新プログラムを先に確認できて、早い時点でフィードバックをすることで製品像の決定に協力できます。更新プログラムを個人で早く受信するか、組織全体で早く受信するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="47218-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="47218-p108">大規模な更新プログラムまたは複雑な更新プログラムは、悪影響を受けるユーザーがいないようにするために他の更新プログラムに比べて時間がかかる場合があります。 リリースは、予定どおりになる保証はありません。</span><span class="sxs-lookup"><span data-stu-id="47218-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="47218-136">組織全体の対象指定リリース</span><span class="sxs-lookup"><span data-stu-id="47218-136">Targeted release for entire organization</span></span>

<span data-ttu-id="47218-137">このオプションに対して[管理センターでリリースオプションを設定](#set-up-the-release-option-in-the-admin-center)すると、すべてのユーザーが対象となるリリースの手順を取得できます。</span><span class="sxs-lookup"><span data-stu-id="47218-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="47218-138">ユーザー数が 300 を超える組織では、このオプションにテスト サブスクリプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47218-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="47218-139">テスト サブスクリプションについては、Microsoft の担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="47218-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="47218-140">選択したユーザーの対象指定リリース</span><span class="sxs-lookup"><span data-stu-id="47218-140">Targeted release for selected users</span></span>

<span data-ttu-id="47218-141">このオプションに対して[管理センターでリリースオプションを設定](#set-up-the-release-option-in-the-admin-center)した場合は、特定のユーザー (通常は power users) を定義して、機能に早期にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="47218-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="47218-142">対象指定リリースの利点</span><span class="sxs-lookup"><span data-stu-id="47218-142">Benefits of Targeted release</span></span>

<span data-ttu-id="47218-143">対象指定リリースでは、管理者、変更マネージャー、または Microsoft 365 更新プログラムを担当するその他のユーザーに、次のことを許可することにより、今後の変更を準備することができます。</span><span class="sxs-lookup"><span data-stu-id="47218-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="47218-144">組織内のすべてのユーザーにリリースされる前に、新しい更新プログラムをテストおよび検証する。</span><span class="sxs-lookup"><span data-stu-id="47218-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="47218-145">更新プログラムが全世界でリリースされる前に、ユーザー通知およびドキュメントを準備する。</span><span class="sxs-lookup"><span data-stu-id="47218-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="47218-146">今後の変更に関する社内ヘルプ デスクを準備する。</span><span class="sxs-lookup"><span data-stu-id="47218-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="47218-147">コンプライアンスとセキュリティ レビューに合格する。</span><span class="sxs-lookup"><span data-stu-id="47218-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="47218-148">機能制御を必要に応じて使用して、エンド ユーザーに対する更新プログラムのリリースを制御する。</span><span class="sxs-lookup"><span data-stu-id="47218-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="47218-149">管理センターでリリースオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="47218-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="47218-150">次の手順に従って、組織が Microsoft 365 の更新プログラムを受信する方法を変更できます。</span><span class="sxs-lookup"><span data-stu-id="47218-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="47218-151">オプトインするには、Microsoft 365 のグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47218-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="47218-152">以下の変更が Microsoft 365 で有効になるまで、最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="47218-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="47218-153">対象指定リリースをいったん有効にした後に無効にすると、予定された標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47218-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="47218-154">管理センターで、[**設定**] [組織  >  **設定**] に移動し、[**組織プロファイル**] タブの [**リリース環境設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47218-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="47218-155">対象指定リリースを無効にするには、[ **Standard release**] を選択し、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47218-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="47218-156">組織内のすべてのユーザーに対して対象指定リリースを有効にするには、[すべて**のユーザーに対象**とするリリース] を選択し、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47218-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="47218-157">組織内の一部のユーザーに対して対象指定リリースを有効にするには、[**選択したユーザーの対象指定リリース**] を選択し、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47218-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="47218-158">一度に1人のユーザーを追加する場合は **[ユーザーを選択**する] を選択し、ユーザーを一括して追加する場合は [**アップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47218-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="47218-159">ユーザーの追加が完了したら、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47218-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="47218-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="47218-160">Learn more</span></span>

<span data-ttu-id="47218-161">[Microsoft 365 メッセージセンター](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)の[メッセージを管理](https://docs.microsoft.com/office365/admin/manage/message-center)して、今後の microsoft 365 の更新プログラムとリリースに関する通知を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47218-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
