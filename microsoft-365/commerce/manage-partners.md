---
title: ソリューションプロバイダーを操作する
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: Microsoft 認定のソリューションプロバイダーと協力して、組織または学校の製品とサービスを購入して管理することができます。
keywords: パートナー、ソリューションプロバイダ
ms.openlocfilehash: bb78e1a704529fd2d12ff49639913fe80b75be7a
ms.sourcegitcommit: a7edd3840226e67e82126bb9dee423b3458fef4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2019
ms.locfileid: "36994078"
---
# <a name="working-with-solution-providers-in-microsoft-store-for-business"></a><span data-ttu-id="8990f-104">ビジネス向け Microsoft Store のソリューションプロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="8990f-104">Working with solution providers in Microsoft Store for Business</span></span>

<span data-ttu-id="8990f-105">Microsoft 認定のソリューションプロバイダーと協力して、組織または学校の製品とサービスを購入して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="8990f-105">You can work with Microsoft-certified solution providers to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="8990f-106">設定を行うには、いくつかの手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="8990f-106">There's a few steps involved in getting the things set up.</span></span> 

<span data-ttu-id="8990f-107">プロセスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8990f-107">The process goes like this:</span></span>
- <span data-ttu-id="8990f-108">管理者は、Microsoft Store for Business で [**ソリューションプロバイダーの検索**] を使用してソリューションプロバイダーを検索し、そのプロバイダーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="8990f-108">Admins find and contact a solution provider using **Find a solution provider** in Microsoft Store for Business.</span></span> 
- <span data-ttu-id="8990f-109">ソリューションプロバイダーは、パートナーセンターからお客様のソリューションプロバイダになる要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="8990f-109">Solution providers send a request from Partner center to customers to become their solution provider.</span></span>
- <span data-ttu-id="8990f-110">お客様は、Microsoft Store for Business の招待を承諾し、ソリューションプロバイダの使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="8990f-110">Customers accept the invitation in Microsoft Store for Business and start working with the solution provider.</span></span>
- <span data-ttu-id="8990f-111">お客様は、Microsoft Store for Business のパートナーとの関係の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="8990f-111">Customers can manage settings for the relationship with Partner in Microsoft Store for Business.</span></span> 

## <a name="what-can-a-solution-provider-do-for-my-organization-or-school"></a><span data-ttu-id="8990f-112">組織または学校のソリューションプロバイダーには、どのようなものがありますか?</span><span class="sxs-lookup"><span data-stu-id="8990f-112">What can a solution provider do for my organization or school?</span></span>

<span data-ttu-id="8990f-113">ソリューションプロバイダーは、いくつかの方法で作業できます。</span><span class="sxs-lookup"><span data-stu-id="8990f-113">There are several ways that a solution provider can work with you.</span></span> <span data-ttu-id="8990f-114">ソリューションプロバイダーは、パートナーとして機能するために要求を送信するときに、これらのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8990f-114">Solution providers will choose one of these when they send their request to work as a partner with you.</span></span>

| <span data-ttu-id="8990f-115">ソリューションプロバイダ関数</span><span class="sxs-lookup"><span data-stu-id="8990f-115">Solution provider function</span></span> | <span data-ttu-id="8990f-116">説明</span><span class="sxs-lookup"><span data-stu-id="8990f-116">Description</span></span> | 
| ------ | ------------------- | 
| <span data-ttu-id="8990f-117">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="8990f-117">Reseller</span></span> | <span data-ttu-id="8990f-118">ソリューションプロバイダーは、組織または学校に Microsoft 製品を販売しています。</span><span class="sxs-lookup"><span data-stu-id="8990f-118">Solution providers sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="8990f-119">代理管理者</span><span class="sxs-lookup"><span data-stu-id="8990f-119">Delegated administrator</span></span> | <span data-ttu-id="8990f-120">ソリューションプロバイダは、組織または学校の製品とサービスを管理します。</span><span class="sxs-lookup"><span data-stu-id="8990f-120">Solution provider manages products and services for your organization or school.</span></span> <span data-ttu-id="8990f-121">Azure Active Directory (AD) では、パートナーはテナントのグローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="8990f-121">In Azure Active Directory (AD), the Partner will be a Global Administrator for tenant.</span></span> <span data-ttu-id="8990f-122">これにより、ユーザーアカウントの作成、ライセンスの割り当てと管理、パスワードのリセットなどのサービスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="8990f-122">This allows them to manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="8990f-123">販売店 & 代理管理者</span><span class="sxs-lookup"><span data-stu-id="8990f-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="8990f-124">組織または学校への Microsoft 製品とサービスを販売および管理するソリューションプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="8990f-124">Solution providers that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="8990f-125">パートナー</span><span class="sxs-lookup"><span data-stu-id="8990f-125">Partner</span></span> | <span data-ttu-id="8990f-126">ソリューションプロバイダーにテナントのユーザーアカウントを提供し、他の Microsoft サービスに代わって作業することができます。</span><span class="sxs-lookup"><span data-stu-id="8990f-126">You can give your solution provider a user account in your tenant, and they work on your behalf with other Microsoft services.</span></span> |
| <span data-ttu-id="8990f-127">Microsoft 製品 & サービス契約 (MPSA) パートナー</span><span class="sxs-lookup"><span data-stu-id="8990f-127">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="8990f-128">MPSA プログラムを使用して複数のソリューションプロバイダーを使用した場合、パートナーが相互に購入したものを確認できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8990f-128">If you've worked with multiple solution providers through the MPSA program, you can allow partners to see purchases made by each other.</span></span> |
| <span data-ttu-id="8990f-129">OEM PC パートナー</span><span class="sxs-lookup"><span data-stu-id="8990f-129">OEM PC partner</span></span> | <span data-ttu-id="8990f-130">ソリューションプロバイダーは、[自動操縦を使用して管理](https://docs.microsoft.com/microsoft-store/add-profile-to-devices)している pc のデバイス id をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="8990f-130">Solution providers can upload device IDs for PCs that you're [managing with Autopilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).</span></span>   |
| <span data-ttu-id="8990f-131">基幹業務 (LOB) パートナー</span><span class="sxs-lookup"><span data-stu-id="8990f-131">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="8990f-132">ソリューションプロバイダーは、組織または学校に固有の LOB アプリを開発、提出、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="8990f-132">Solution providers can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-solution-provider"></a><span data-ttu-id="8990f-133">ソリューションプロバイダーを検索する</span><span class="sxs-lookup"><span data-stu-id="8990f-133">Find a solution provider</span></span>

<span data-ttu-id="8990f-134">ビジネスおよび教育機関向けの Microsoft Store には、パートナーを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="8990f-134">You can find partner in Microsoft Store for Business and Education.</span></span> 

1. <span data-ttu-id="8990f-135">教育機関向け[Microsoft store For Business](https://businessstore.microsoft.com/)または[microsoft store](https://educationstore.microsoft.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8990f-135">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com/) or [Microsoft Store for Education](https://educationstore.microsoft.com/).</span></span>
2. <span data-ttu-id="8990f-136">[**ソリューションプロバイダーの検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8990f-136">Select **Find a solution provider**.</span></span>
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-find-partner.png)
-->
3. <span data-ttu-id="8990f-137">リストを絞り込むか、ソリューションプロバイダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="8990f-137">Refine the list, or search for a solution provider.</span></span> 
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-provider-list.png)
-->
4. <span data-ttu-id="8990f-138">作業を希望するソリューションプロバイダーが見つかったら、[**連絡先**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8990f-138">When you find a solution provider you're interested in working with, click **Contact**.</span></span>
5. <span data-ttu-id="8990f-139">フォームを完成させ、送信します。</span><span class="sxs-lookup"><span data-stu-id="8990f-139">Complete and send the form.</span></span>

<span data-ttu-id="8990f-140">ソリューションプロバイダーは、ユーザーと連絡を取ります。</span><span class="sxs-lookup"><span data-stu-id="8990f-140">The solution provider will get in touch with you.</span></span> <span data-ttu-id="8990f-141">詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8990f-141">You'll have a chance to learn more about them.</span></span> <span data-ttu-id="8990f-142">ソリューションプロバイダーを使用して作業する場合は、パートナーセンターから電子メール招待状を送信します。</span><span class="sxs-lookup"><span data-stu-id="8990f-142">If you decide to work with the solution provider, they will send you an email invitation from Partner Center.</span></span> 

## <a name="work-with-a-solution-provider"></a><span data-ttu-id="8990f-143">ソリューションプロバイダーを操作する</span><span class="sxs-lookup"><span data-stu-id="8990f-143">Work with a solution provider</span></span>

<span data-ttu-id="8990f-144">ソリューションプロバイダーを見つけて、それを使用することにした場合は、パートナーセンターから共同で作業するための招待状が送信されます。</span><span class="sxs-lookup"><span data-stu-id="8990f-144">Once you've found a solution provider and decided to work with them, they'll send you an invitation to work together from Partner Center.</span></span> <span data-ttu-id="8990f-145">Business または教育機関向け Microsoft Store では、招待状を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8990f-145">In Microsoft Store for Business or Education, you'll need to accept the invitation.</span></span> <span data-ttu-id="8990f-146">その後、アクセス許可を管理できます。</span><span class="sxs-lookup"><span data-stu-id="8990f-146">After that, you can manage their permissions.</span></span>

<span data-ttu-id="8990f-147">**ソリューションプロバイダーへの招待を承諾するには**</span><span class="sxs-lookup"><span data-stu-id="8990f-147">**To accept a solution provider invitation**</span></span>
1. <span data-ttu-id="8990f-148">[**電子メールのフォロー] リンク**-ソリューションプロバイダーからソリューションプロバイダへの招待を受け入れるためのリンクを含む電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="8990f-148">**Follow email link** - You'll receive an email with a link to accept the solution provider invitation from your solution provider.</span></span> <span data-ttu-id="8990f-149">このリンクにより、ビジネスまたは教育機関向け Microsoft Store に移動します。</span><span class="sxs-lookup"><span data-stu-id="8990f-149">The link will take you to Microsoft Store for Business or Education.</span></span>
2. <span data-ttu-id="8990f-150">**招待を承諾**する-[**パートナーへの招待を承諾**する] で、[**承認**] を選択して招待状を承諾し、Microsoft Cloud Agreement の条項に同意して、ソリューションプロバイダーの作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="8990f-150">**Accept invitation** - On **Accept Partner Invitation**, select **Authorize** to accept the invitation, accept terms of the Microsoft Cloud Agreement, and start working with the solution provider.</span></span> 
<!---
![Image shows accepting an invitation from a solution provider in Microsoft Store for Business.](images/msft-accept-partner.png)
--> 
## <a name="delegate-admin-privileges"></a><span data-ttu-id="8990f-151">管理者権限を委任する</span><span class="sxs-lookup"><span data-stu-id="8990f-151">Delegate admin privileges</span></span>

<span data-ttu-id="8990f-152">ソリューションプロバイダーによる要求に応じて、招待の承諾の一部として、委任された管理者権限をソリューションプロバイダーに付与することが同意されます。</span><span class="sxs-lookup"><span data-stu-id="8990f-152">Depending on the request made by the solution provider, part of accepting the invitation will include agreeing to give delegated admin privileges to the solution provider.</span></span> <span data-ttu-id="8990f-153">これは、ソリューションプロバイダ要求が代理管理者として機能する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="8990f-153">This will happen when the solution provider request includes acting as a delegated administrator.</span></span> <span data-ttu-id="8990f-154">詳細については、「 [AZURE AD での管理者権限の委任](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8990f-154">For more information, see [Delegated admin privileges in Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span> 

<span data-ttu-id="8990f-155">管理者特権をソリューションプロバイダーに委任しない場合は、招待を承諾するのではなく、キャンセルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8990f-155">If you don't want to delegate admin privileges to the solution provider, you'll need to cancel the invitation instead of accepting it.</span></span> 

<span data-ttu-id="8990f-156">管理者特権をソリューションプロバイダーに委任する場合は、後で削除できます。</span><span class="sxs-lookup"><span data-stu-id="8990f-156">If you delegate admin privileges to a solution provider, you can remove that later.</span></span> 

<span data-ttu-id="8990f-157">**代理人の管理者権限を削除するには**</span><span class="sxs-lookup"><span data-stu-id="8990f-157">**To remove delegate admin privileges**</span></span>
1. <span data-ttu-id="8990f-158">教育機関向け[Microsoft store For Business](https://businessstore.microsoft.com/)または[microsoft store](https://educationstore.microsoft.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8990f-158">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com/) or [Microsoft Store for Education](https://educationstore.microsoft.com/).</span></span>
2. <span data-ttu-id="8990f-159">**パートナー**の選択</span><span class="sxs-lookup"><span data-stu-id="8990f-159">Select **Partner**</span></span>
3. <span data-ttu-id="8990f-160">管理するパートナーを選びます。</span><span class="sxs-lookup"><span data-stu-id="8990f-160">Choose the Partner you want to manage.</span></span>
4. <span data-ttu-id="8990f-161">[委任された**アクセス許可の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8990f-161">Select **Remove Delegated Permissions**.</span></span> 

<span data-ttu-id="8990f-162">ソリューションプロバイダーは、たとえば、販売店として作業することができます。</span><span class="sxs-lookup"><span data-stu-id="8990f-162">The solution provider will still be able to work with you, for example, as a Reseller.</span></span> 
