---
title: Office 365 で標準または対象指定リリース オプションを設定する
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Microsoft 365 管理センターで新しい製品および機能の更新プログラムのリリースオプションをセットアップする方法について説明します。
ms.openlocfilehash: 2d4940003c791e50926eff46aaf6a299e60fb9aa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254925"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="7eaa5-103">Office 365 で標準または対象指定リリース オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="7eaa5-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="7eaa5-p101">Office 365 では、新しい製品の更新プログラムと機能をリリースと同時に受信できます。数年ごとに高い費用をかけて更新を行う必要はありません。組織でこれらの更新プログラムを受信する方法を管理できます。たとえば、組織で先に更新プログラムを受信するように先行リリースにサインアップできます。お客様は、特定の個人のみがその更新プログラムを受信するということを指定できます。そうでなければ、既定のリリース スケジュールどおりのままにして、後で更新プログラムを受信することもできます。この記事では、さまざまなリリース オプションと、組織に使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7eaa5-p102">この記事で説明する Office 365 更新プログラムは、Office 365、SharePoint Online、Exchange Online に適用されますが、Skype for Business、および関連のサービスには適用されません。これらのリリース オプションは、Office 365 への変更をリリースするための、対象を限定したベスト エフォート型の方法ですが、常に、またすべての更新プログラムに対して保証されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="7eaa5-113">しくみ - リリースの検証</span><span class="sxs-lookup"><span data-stu-id="7eaa5-113">How it works - release validation</span></span>

<span data-ttu-id="7eaa5-114">新しいリリースはすべて、最初に機能チームによってテストおよび検証され、次に Office 365 機能チーム全体によって、その後にすべての Microsoft が評価されます。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="7eaa5-115">内部テストと検証が終わったら、次の手順は参加しているお客様に向けた **対象指定リリース** (以前は先行リリースと呼ばれていました) です。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="7eaa5-116">各リリース リングで、Microsoft はフィードバックを収集し、主要な利用状況メトリックを監視することでさらに品質を検証します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="7eaa5-117">この革新的な一連の検証は、全世界のリリースの信頼性を最大限に高めるためにあります。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="7eaa5-118">各リリースを、次の図で示します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-118">The releases are pictured in the following figure.</span></span> 
  
![Office 365 のリリース検証リング](../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="7eaa5-120">重要な更新プログラムについては、Office のお客様には、 [Microsoft 365 ロードマップ](https://products.office.com/business/office-365-roadmap)による通知が最初に行われます。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="7eaa5-121">更新プログラムのロールアウトが近づくにつれて、 [Office 365 メッセージセンター](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)を経由して通知されます。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="7eaa5-122">[管理センター](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)を使用してメッセージセンターにアクセスするには、Office 365 または Azure AD アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="7eaa5-123">Office 365 ホームプランユーザーには管理センターがありません。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="7eaa5-124">標準リリース</span><span class="sxs-lookup"><span data-stu-id="7eaa5-124">Standard release</span></span>

<span data-ttu-id="7eaa5-125">これは、ユーザーがすべてのお客様に幅広くリリースされている場合に最新の更新プログラムを受信する既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="7eaa5-126">ユーザーの大部分を**標準のリリース**と IT プロフェッショナルおよびパワーユーザーに任せて、新しい機能を評価し、ビジネスユーザーと役員をサポートするチームを**準備すること**をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7eaa5-127">対象指定リリースから標準リリースに切り替えた場合、ユーザーは標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="7eaa5-128">対象となるリリース</span><span class="sxs-lookup"><span data-stu-id="7eaa5-128">Targeted release</span></span>

<span data-ttu-id="7eaa5-p106">このオプションでは、お客様とお客様のユーザーは最新の更新プログラムを先に確認できて、早い時点でフィードバックをすることで製品像の決定に協力できます。更新プログラムを個人で早く受信するか、組織全体で早く受信するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7eaa5-p107">大規模な更新プログラムまたは複雑な更新プログラムは、悪影響を受けるユーザーがいないようにするために他の更新プログラムに比べて時間がかかる場合があります。 リリースは、予定どおりになる保証はありません。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="7eaa5-133">組織全体の対象指定リリース</span><span class="sxs-lookup"><span data-stu-id="7eaa5-133">Targeted release for entire organization</span></span>

<span data-ttu-id="7eaa5-134">このオプションに対して[管理センターでリリースオプションを設定](#set-up-the-release-option-in-the-admin-center)すると、すべてのユーザーが対象となるリリースの手順を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="7eaa5-135">ユーザー数が 300 を超える組織では、このオプションにテスト サブスクリプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="7eaa5-136">テスト サブスクリプションについては、Microsoft の担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="7eaa5-137">選択したユーザーの対象指定リリース</span><span class="sxs-lookup"><span data-stu-id="7eaa5-137">Targeted release for selected users</span></span>

<span data-ttu-id="7eaa5-138">このオプションに対して[管理センターでリリースオプションを設定](#set-up-the-release-option-in-the-admin-center)した場合は、特定のユーザー (通常は power users) を定義して、機能に早期にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="7eaa5-139">対象指定リリースの利点</span><span class="sxs-lookup"><span data-stu-id="7eaa5-139">Benefits of Targeted release</span></span>

<span data-ttu-id="7eaa5-140">対象指定リリースでは、管理者、変更マネージャー、Office 365 更新プログラムを担当するその他のユーザーが次のことをできるようになるため、新しい変更プログラムを準備できます。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="7eaa5-141">組織内のすべてのユーザーにリリースされる前に、新しい更新プログラムをテストおよび検証する。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="7eaa5-142">更新プログラムが全世界でリリースされる前に、ユーザー通知およびドキュメントを準備する。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="7eaa5-143">今後の変更に関する社内ヘルプ デスクを準備する。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="7eaa5-144">コンプライアンスとセキュリティ レビューに合格する。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="7eaa5-145">機能制御を必要に応じて使用して、エンド ユーザーに対する更新プログラムのリリースを制御する。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="7eaa5-146">管理センターでリリースオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="7eaa5-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="7eaa5-p109">組織で Office 365 更新プログラムを受信する方法は、次の手順で変更できます。参加するには Office 365 のグローバル管理者でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7eaa5-p110">Office 365 で次の変更が有効になるまで、最大で 24 時間かかる場合があります。対象指定リリースをいったん有効にした後に無効にすると、予定された標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="7eaa5-151">管理センターで、[**設定** > ]**設定**に移動し、[**組織プロファイル**] タブの [**リリース環境設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="7eaa5-152">対象指定リリースを無効にするには、[ **Standard release**] を選択し、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="7eaa5-153">組織内のすべてのユーザーに対して対象指定リリースを有効にするには、[すべて**のユーザーに対象**とするリリース] を選択し、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="7eaa5-154">組織内の一部のユーザーに対して対象指定リリースを有効にするには、[**選択したユーザーの対象指定リリース**] を選択し、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="7eaa5-155">一度に1人のユーザーを追加する場合は **[ユーザーを選択**する] を選択し、ユーザーを一括して追加する場合は [**アップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="7eaa5-156">ユーザーの追加が完了したら、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="7eaa5-157">対象となるリリース版の Office を取得する</span><span class="sxs-lookup"><span data-stu-id="7eaa5-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="7eaa5-p111">Office の対象指定リリース ビルドをインストールするには、[次の手順に従います](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead)。これにより、Windows デスクトップ用の Office 2016 の新機能をいち早く利用できます。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="7eaa5-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="7eaa5-160">Learn more</span></span>

<span data-ttu-id="7eaa5-161">[Office 365 メッセージセンター](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)の[メッセージを管理](https://docs.microsoft.com/office365/admin/manage/message-center)して、今後の office 365 の更新プログラムとリリースに関する通知を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7eaa5-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
