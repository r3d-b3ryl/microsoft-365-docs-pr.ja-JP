---
title: 標準リリースオプションまたはターゲット リリース オプションを設定する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 新しい製品と機能の更新プログラムのリリース オプションを設定する方法については、Microsoft 365 管理センター。
ms.openlocfilehash: ba9c3a71807728e18b612f0b63aff80d04a46a90
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392529"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="53cbe-103">標準リリースオプションまたはターゲット リリース オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="53cbe-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53cbe-104">このMicrosoft 365の更新プログラムは、オンライン、オンライン、およびMicrosoft 365、SharePointに適用Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="53cbe-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="53cbe-105">これらのリリース オプションは、Microsoft 365に対する変更をリリースするための最善の努力の方法ですが、すべての時間またはすべての更新プログラムについて保証することはできません。</span><span class="sxs-lookup"><span data-stu-id="53cbe-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="53cbe-106">これらのサービスは、Microsoft 365 Apps、Skype for Business、Microsoft Teamsには適用されません。</span><span class="sxs-lookup"><span data-stu-id="53cbe-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="53cbe-107">リリース オプションの詳細については、「Microsoft 365 Appsの更新プログラム チャネルの概要」[を参照Microsoft 365 Apps。](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="53cbe-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="53cbe-108">このMicrosoft 365、数年ごとにコストの高い更新プログラムを実行する代わりに、新しい製品の更新プログラムと機能が利用できると受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="53cbe-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="53cbe-109">組織がこれらの更新プログラムを受け取る方法を管理できます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="53cbe-110">たとえば、組織が最初に更新プログラムを受け取る前に、早期リリースにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="53cbe-111">特定の個人だけが更新プログラムを受け取る方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="53cbe-112">または、既定のリリース スケジュールのままで、後で更新プログラムを受信することもできます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="53cbe-113">この記事では、さまざまなリリース オプションと、それらを組織で使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53cbe-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="53cbe-114">しくみ - リリースの検証</span><span class="sxs-lookup"><span data-stu-id="53cbe-114">How it works - release validation</span></span>

<span data-ttu-id="53cbe-115">すべての新しいリリースは、最初に機能チームによってテストされ、検証され、次に、Microsoft 365機能チーム全体が、その後に Microsoft のすべてによって検証されます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="53cbe-116">内部テストと検証が終わったら、次の手順は参加しているお客様に向けた **対象指定リリース** (以前は先行リリースと呼ばれていました) です。</span><span class="sxs-lookup"><span data-stu-id="53cbe-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="53cbe-117">各リリース リングで、Microsoft はフィードバックを収集し、主要な利用状況メトリックを監視することでさらに品質を検証します。</span><span class="sxs-lookup"><span data-stu-id="53cbe-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="53cbe-118">この革新的な一連の検証は、全世界のリリースの信頼性を最大限に高めるためにあります。</span><span class="sxs-lookup"><span data-stu-id="53cbe-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="53cbe-119">各リリースを、次の図で示します。</span><span class="sxs-lookup"><span data-stu-id="53cbe-119">The releases are pictured in the following figure.</span></span> 
  
![ユーザーの検証リングを解放Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="53cbe-121">重要な更新プログラムの場合、お客様は最初はロードマップによって[Microsoft 365されます](https://products.office.com/business/office-365-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="53cbe-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="53cbe-122">更新プログラムが展開に近づくにつれて、メッセージ センターからMicrosoft 365[されます](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)。</span><span class="sxs-lookup"><span data-stu-id="53cbe-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="53cbe-123">管理センターからMicrosoft 365メッセージ センター ADアクセスするには、管理者アカウントまたは Azure アカウントが[必要です](/office365/admin/admin-overview/about-the-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="53cbe-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="53cbe-124">Microsoft 365ユーザーに管理センターが設定されていない場合。</span><span class="sxs-lookup"><span data-stu-id="53cbe-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="53cbe-125">標準リリース</span><span class="sxs-lookup"><span data-stu-id="53cbe-125">Standard release</span></span>

<span data-ttu-id="53cbe-126">これは、ユーザーがすべての顧客に広範にリリースされると、ユーザーが最新の更新プログラムを受け取る既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="53cbe-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="53cbe-127">優れた方法は、標準リリースおよび IT  Pros および Power Users の大部分のユーザーをターゲット リリースに残して、新機能を評価し、ビジネス ユーザーとエグゼクティブをサポートするためのチームを準備する方法です。</span><span class="sxs-lookup"><span data-stu-id="53cbe-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="53cbe-128">対象指定リリースから標準リリースに切り替えた場合、ユーザーは標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53cbe-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="53cbe-129">対象となるリリース</span><span class="sxs-lookup"><span data-stu-id="53cbe-129">Targeted release</span></span>

<span data-ttu-id="53cbe-p106">このオプションでは、お客様とお客様のユーザーは最新の更新プログラムを先に確認できて、早い時点でフィードバックをすることで製品像の決定に協力できます。更新プログラムを個人で早く受信するか、組織全体で早く受信するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="53cbe-p107">大規模な更新プログラムまたは複雑な更新プログラムは、悪影響を受けるユーザーがいないようにするために他の更新プログラムに比べて時間がかかる場合があります。 リリースは、予定どおりになる保証はありません。</span><span class="sxs-lookup"><span data-stu-id="53cbe-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="53cbe-134">組織全体の対象指定リリース</span><span class="sxs-lookup"><span data-stu-id="53cbe-134">Targeted release for entire organization</span></span>

<span data-ttu-id="53cbe-135">管理センター [でこのオプションのリリース](#set-up-the-release-option-in-the-admin-center) オプションを設定すると、すべてのユーザーが対象のリリース エクスペリエンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="53cbe-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="53cbe-136">ユーザー数が 300 を超える組織では、このオプションにテスト サブスクリプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53cbe-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="53cbe-137">テスト サブスクリプションについては、Microsoft の担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="53cbe-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="53cbe-138">選択したユーザーの対象指定リリース</span><span class="sxs-lookup"><span data-stu-id="53cbe-138">Targeted release for selected users</span></span>

<span data-ttu-id="53cbe-139">このオプション [の管理センター](#set-up-the-release-option-in-the-admin-center) でリリース オプションを設定する場合は、特定のユーザー (通常は電源ユーザー) を定義して、機能と機能への早期アクセスを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="53cbe-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="53cbe-140">対象指定リリースの利点</span><span class="sxs-lookup"><span data-stu-id="53cbe-140">Benefits of Targeted release</span></span>

<span data-ttu-id="53cbe-141">対象のリリースでは、管理者、変更マネージャー、または更新プログラムを担当する他Microsoft 365、次の変更に備えて、次の情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="53cbe-142">組織内のすべてのユーザーにリリースされる前に、新しい更新プログラムをテストおよび検証する。</span><span class="sxs-lookup"><span data-stu-id="53cbe-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="53cbe-143">更新プログラムが全世界でリリースされる前に、ユーザー通知およびドキュメントを準備する。</span><span class="sxs-lookup"><span data-stu-id="53cbe-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="53cbe-144">今後の変更に関する社内ヘルプ デスクを準備する。</span><span class="sxs-lookup"><span data-stu-id="53cbe-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="53cbe-145">コンプライアンスとセキュリティ レビューに合格する。</span><span class="sxs-lookup"><span data-stu-id="53cbe-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="53cbe-146">機能制御を必要に応じて使用して、エンド ユーザーに対する更新プログラムのリリースを制御する。</span><span class="sxs-lookup"><span data-stu-id="53cbe-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="53cbe-147">管理センターでリリース オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="53cbe-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="53cbe-148">次の手順に従って、組織Microsoft 365更新プログラムを受け取る方法を変更できます。</span><span class="sxs-lookup"><span data-stu-id="53cbe-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="53cbe-149">オプトインを行う場合は、Microsoft 365管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="53cbe-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="53cbe-150">以下の変更が適用される場合は、最大で 24 時間かかる場合Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="53cbe-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="53cbe-151">対象指定リリースをいったん有効にした後に無効にすると、予定された標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53cbe-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="53cbe-152">管理センターで、[組織の設定] 設定に移動し **、[** 組織プロファイル] タブの [基本設定のリリース  >  ]**を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="53cbe-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="53cbe-153">対象リリースを無効にするには、[標準リリース] **を選択し**、[変更の保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="53cbe-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="53cbe-154">組織内のすべてのユーザーの対象リリースを有効にするには、[すべてのユーザーの対象リリース] を選択し、[変更の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="53cbe-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="53cbe-155">組織内の一部のユーザーの対象リリースを有効にするには、[選択したユーザーの対象リリース] を選択し、[変更の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="53cbe-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="53cbe-156">[**ユーザーを一度** に 1 人追加するユーザーを選択する] を選択するか、アップロード **ユーザー** を一括で追加します。</span><span class="sxs-lookup"><span data-stu-id="53cbe-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="53cbe-157">ユーザーの追加が完了したら、[変更の保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="53cbe-157">When you're done adding users, select **Save changes**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="53cbe-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="53cbe-158">Next steps</span></span>

<span data-ttu-id="53cbe-159">メッセージ センターで[メッセージ](/office365/admin/manage/message-center)を管理して、Microsoft 365[更新](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)プログラムとリリースに関する通知Microsoft 365確認します。</span><span class="sxs-lookup"><span data-stu-id="53cbe-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-content"></a><span data-ttu-id="53cbe-160">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="53cbe-160">Related content</span></span>

<span data-ttu-id="53cbe-161">[インサイダー プログラムOffice参加する](https://insider.office.com/join/windows)(記事)</span><span class="sxs-lookup"><span data-stu-id="53cbe-161">[Join the Office Insider Program](https://insider.office.com/join/windows) (article)</span></span>
