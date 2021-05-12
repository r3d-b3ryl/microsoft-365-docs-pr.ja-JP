---
title: パートナー関係の管理
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: tugu, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Microsoft 認定ソリューション プロバイダー (パートナー) と連携して、組織または学校の製品とサービスを購入および管理する方法について説明します。
ms.date: 04/13/2021
ms.openlocfilehash: 63c5595d14ca0a531f50875ea8058663b626bb89
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331576"
---
# <a name="manage-partner-relationships"></a><span data-ttu-id="544b0-103">パートナー関係の管理</span><span class="sxs-lookup"><span data-stu-id="544b0-103">Manage partner relationships</span></span>

<span data-ttu-id="544b0-104">Microsoft 認定ソリューション プロバイダー (パートナー) と連携して、組織または学校の製品とサービスを購入および管理できます。</span><span class="sxs-lookup"><span data-stu-id="544b0-104">You can work with Microsoft-certified solution providers (partners) to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="544b0-105">物事をセットアップするには、いくつかの手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="544b0-105">There are a few steps involved in getting things set up.</span></span>

1. <span data-ttu-id="544b0-106">管理者は、次のフォームを使用してパートナーを検索して連絡します <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a> 。</span><span class="sxs-lookup"><span data-stu-id="544b0-106">Admins find and contact a partner using the form at <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="544b0-107">パートナーは、パートナー関係を確立するために顧客に電子メール要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="544b0-107">Partners send an email request to customers to establish a partner relationship.</span></span>
3. <span data-ttu-id="544b0-108">お客様は、Microsoft 365 管理センターで招待を受け入れ、パートナーとの作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="544b0-108">Customers accept the invitation in Microsoft 365 admin center and start working with the partner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="544b0-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="544b0-109">Before you begin</span></span>

<span data-ttu-id="544b0-110">これらの手順を実行するには、グローバル管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="544b0-110">You must be either a Global or Billing admin to do these steps.</span></span> <span data-ttu-id="544b0-111">詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="544b0-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a><span data-ttu-id="544b0-112">パートナーが自分の組織や学校に対して何ができますか?</span><span class="sxs-lookup"><span data-stu-id="544b0-112">What can a partner do for my organization or school?</span></span>

<span data-ttu-id="544b0-113">パートナーが一緒に作業できる方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="544b0-113">There are several ways that a partner can work with you.</span></span> <span data-ttu-id="544b0-114">指定したビジネス ニーズに基づいて、ユーザーが自分の要求を送信するときに、これらの種類の 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="544b0-114">Based on your stated business needs, they choose one of these types when they send their request to work with you.</span></span>

| <span data-ttu-id="544b0-115">パートナーの種類</span><span class="sxs-lookup"><span data-stu-id="544b0-115">Partner type</span></span> | <span data-ttu-id="544b0-116">説明</span><span class="sxs-lookup"><span data-stu-id="544b0-116">Description</span></span> |
| ------ | ------------------- |
| <span data-ttu-id="544b0-117">リセラー</span><span class="sxs-lookup"><span data-stu-id="544b0-117">Reseller</span></span> | <span data-ttu-id="544b0-118">組織または学校に Microsoft 製品を販売するパートナー。</span><span class="sxs-lookup"><span data-stu-id="544b0-118">Partners that sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="544b0-119">委任された管理者</span><span class="sxs-lookup"><span data-stu-id="544b0-119">Delegated administrator</span></span> | <span data-ttu-id="544b0-120">組織または学校の製品とサービスを管理するパートナー。</span><span class="sxs-lookup"><span data-stu-id="544b0-120">Partners that manage products and services for your organization or school.</span></span> <span data-ttu-id="544b0-121">Azure Active Directory (AD) では、パートナーはテナントのグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="544b0-121">In Azure Active Directory (AD), the partner is a Global Administrator for your tenant.</span></span> <span data-ttu-id="544b0-122">この役割を使用すると、ユーザー アカウントの作成、ライセンスの割り当てと管理、パスワードのリセットなど、サービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="544b0-122">This role lets them manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="544b0-123">リセラー &委任された管理者</span><span class="sxs-lookup"><span data-stu-id="544b0-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="544b0-124">組織または学校に対して Microsoft 製品およびサービスを販売および管理するパートナー。</span><span class="sxs-lookup"><span data-stu-id="544b0-124">Partners that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="544b0-125">パートナー</span><span class="sxs-lookup"><span data-stu-id="544b0-125">Partner</span></span> | <span data-ttu-id="544b0-126">パートナーにテナント内のユーザー アカウントを与え、パートナーが代理で他の Microsoft サービスと作業します。</span><span class="sxs-lookup"><span data-stu-id="544b0-126">You give your partner a user account in your tenant, and they work with other Microsoft services on your behalf.</span></span> |
| <span data-ttu-id="544b0-127">Advisor</span><span class="sxs-lookup"><span data-stu-id="544b0-127">Advisor</span></span> | <span data-ttu-id="544b0-128">パートナーは、パスワードをリセットし、サポート インシデントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="544b0-128">Partners can reset passwords and handle support incidents for you.</span></span> |
| <span data-ttu-id="544b0-129">Microsoft Products & サービス契約 (MPSA) パートナー</span><span class="sxs-lookup"><span data-stu-id="544b0-129">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="544b0-130">MPSA プログラムを通じて複数のパートナーと協力した場合は、お互いに購入した情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="544b0-130">If you've worked with multiple partners through the MPSA program, you can allow them to see purchases made by each other.</span></span> |
| <span data-ttu-id="544b0-131">LINE-of-business (LOB) パートナー</span><span class="sxs-lookup"><span data-stu-id="544b0-131">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="544b0-132">パートナーは、組織または学校に固有の LOB アプリを開発、提出、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="544b0-132">Partners can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-partner"></a><span data-ttu-id="544b0-133">パートナーを検索する</span><span class="sxs-lookup"><span data-stu-id="544b0-133">Find a partner</span></span>

1. <span data-ttu-id="544b0-134"><a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a> に移動します。</span><span class="sxs-lookup"><span data-stu-id="544b0-134">Go to <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="544b0-135">場所を入力し、組織のサイズを選択し、必要なサービスの種類にキーワードを追加し、[移動] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="544b0-135">Enter your location, choose your organization size, add keywords for the type of services you need, then select **Go**.</span></span>
3. <span data-ttu-id="544b0-136">1 つ以上のパートナーを選択し、[選択 **したプロバイダーに連絡する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="544b0-136">Choose one or more partners, then select **Contact selected providers**.</span></span>
4. <span data-ttu-id="544b0-137">フォームに入力してビジネス ニーズを説明し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="544b0-137">Complete the form to describe your business needs, then select **Send**.</span></span>

<span data-ttu-id="544b0-138">パートナーが連絡を取り、その詳細を知る機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="544b0-138">The partner contacts you and gives you a chance to learn more about them.</span></span> <span data-ttu-id="544b0-139">パートナーと一緒に作業する場合は、パートナー関係を確立するための電子メールの招待状が送信されます。</span><span class="sxs-lookup"><span data-stu-id="544b0-139">If you decide to work with them, they send you an email invitation to establish a partner relationship.</span></span>

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a><span data-ttu-id="544b0-140">パートナー関係と Microsoft カスタマー 契約の確認と承諾</span><span class="sxs-lookup"><span data-stu-id="544b0-140">Review and accept a partner relationship and Microsoft Customer Agreement</span></span>

<span data-ttu-id="544b0-141">パートナーを見つけて、パートナーと一緒に作業すると、招待メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="544b0-141">After you find a partner and decide to work with them, they send you an email invitation.</span></span>

1. <span data-ttu-id="544b0-142">電子メールで、リンクを選択して Microsoft 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="544b0-142">In the email, select the link to go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="544b0-143">[パートナー **の承認&同意** する] ページで **、Microsoft カスタマー** 契約のリンクを選択し、ドキュメントを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="544b0-143">On the **Accept agreement & authorize partner** page, select the link for the **Microsoft Customer Agreement**, and read the document.</span></span>
3. <span data-ttu-id="544b0-144">このボックスをオンにして、契約を読んだと確認します。</span><span class="sxs-lookup"><span data-stu-id="544b0-144">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="544b0-145">[承認 **する] &を選択します**。</span><span class="sxs-lookup"><span data-stu-id="544b0-145">Select **Accept & Authorize**.</span></span>
5. <span data-ttu-id="544b0-146">作業しているパートナーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="544b0-146">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="544b0-147">詳細を表示するには、任意のパートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="544b0-147">Select any partner to see details.</span></span>

## <a name="review-and-accept-a-microsoft-customer-agreement"></a><span data-ttu-id="544b0-148">Microsoft カスタマー 契約の確認と承諾</span><span class="sxs-lookup"><span data-stu-id="544b0-148">Review and accept a Microsoft Customer Agreement</span></span>

<span data-ttu-id="544b0-149">パートナーが既に存在するが、Microsoft カスタマー 契約にまだ署名していない場合は、契約に同意してから、そのパートナーが代わりにサブスクリプションを購入または管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="544b0-149">If you already have a partner but haven’t yet signed a Microsoft Customer Agreement, you must accept the agreement before they can make purchases or manage your subscriptions on your behalf.</span></span>

1. <span data-ttu-id="544b0-150">パートナーからメールを受け取った場合は、リンクを選択して Microsoft 365 管理センターに移動するか、[契約の承諾] <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">ページに移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="544b0-150">If you receive an email from your partner, select the link to go to the Microsoft 365 admin center, or go to the <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Accept agreement</a> page.</span></span>
2. <span data-ttu-id="544b0-151">Microsoft Customer Agreement のリンクを **選択し** 、ドキュメントを読み取る。</span><span class="sxs-lookup"><span data-stu-id="544b0-151">Select the link for the **Microsoft Customer Agreement** and read the document.</span></span>
3. <span data-ttu-id="544b0-152">このボックスをオンにして、契約を読んだと確認します。</span><span class="sxs-lookup"><span data-stu-id="544b0-152">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="544b0-153">**[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="544b0-153">Select **Accept**.</span></span>
5. <span data-ttu-id="544b0-154">作業しているパートナーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="544b0-154">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="544b0-155">詳細を表示するには、任意のパートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="544b0-155">Select any partner to see details.</span></span>

## <a name="remove-partner-admin-roles"></a><span data-ttu-id="544b0-156">パートナー管理者の役割を削除する</span><span class="sxs-lookup"><span data-stu-id="544b0-156">Remove partner admin roles</span></span>

<span data-ttu-id="544b0-157">パートナーによる要求に応じて、招待を受け入れる際に、グローバル管理者とヘルプデスク管理者の役割を付与することに同意します。</span><span class="sxs-lookup"><span data-stu-id="544b0-157">Depending on the request made by the partner, when you accept the invitation, you agree to give them Global and Helpdesk admin roles.</span></span> <span data-ttu-id="544b0-158">これらの管理者の役割をパートナーに与える場合は、Azure サーバーで委任された管理者特権を自動的に付与AD。</span><span class="sxs-lookup"><span data-stu-id="544b0-158">When you give these admin roles to a partner, you automatically grant them delegated admin privileges in Azure AD.</span></span> <span data-ttu-id="544b0-159">詳細については、「Azure AD での委任された管理者 [特権」を参照してください](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)。</span><span class="sxs-lookup"><span data-stu-id="544b0-159">To learn more, see [Delegated admin privileges in Azure AD](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span>

<span data-ttu-id="544b0-160">管理者の役割をパートナーに与えたくない場合は、招待を受け入れる代わりにキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="544b0-160">If you don't want to give the admin roles to the partner, cancel the invitation instead of accepting it.</span></span>

<span data-ttu-id="544b0-161">管理者の役割は、パートナーからいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="544b0-161">You can remove admin roles from a partner at any time.</span></span> <span data-ttu-id="544b0-162">管理者ロールを削除しても、パートナー関係は削除されます。</span><span class="sxs-lookup"><span data-stu-id="544b0-162">Removing the admin roles doesn’t remove the partner relationship.</span></span> <span data-ttu-id="544b0-163">リセラーなど、別の容量で引き続き作業できます。</span><span class="sxs-lookup"><span data-stu-id="544b0-163">They can still work with you in a different capacity, such as a Reseller.</span></span> <span data-ttu-id="544b0-164">パートナーと仕事をしなくなった場合は、パートナーに問い合わせ、関係を終了してください。</span><span class="sxs-lookup"><span data-stu-id="544b0-164">If you decide that you don’t want to work with a partner anymore, contact your partner to end the relationship.</span></span>

1. <span data-ttu-id="544b0-165">管理センターで、[設定パートナーの関係 **]**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">ページに移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="544b0-165">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span>
2. <span data-ttu-id="544b0-166">[パートナー **の関係] ページ** で、削除するパートナーの名前を含む行を選択します。</span><span class="sxs-lookup"><span data-stu-id="544b0-166">On the **Partner relationships** page, select the row that contains the name of the partner that you want to remove.</span></span>
3. <span data-ttu-id="544b0-167">パートナーの名前を含む行を選択します。</span><span class="sxs-lookup"><span data-stu-id="544b0-167">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="544b0-168">パートナー ページで、[役割の削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="544b0-168">On the partner page, select **Remove roles**.</span></span>
5. <span data-ttu-id="544b0-169">[役割の **削除] ダイアログ ボックスで** 、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="544b0-169">In the **Remove roles?** dialog box, select **Yes**.</span></span>
