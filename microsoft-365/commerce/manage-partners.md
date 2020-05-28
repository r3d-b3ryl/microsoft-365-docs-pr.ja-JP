---
title: パートナー関係を管理する
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Microsoft 認定ソリューションプロバイダ (パートナー) と協力して、組織または学校の製品とサービスを購入して管理する方法について説明します。
keywords: パートナー、ソリューションプロバイダ
ms.openlocfilehash: 752c9e0237bbdde7be996b5675848e948e866dce
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402596"
---
# <a name="manage-partner-relationships"></a><span data-ttu-id="2587e-104">パートナー関係を管理する</span><span class="sxs-lookup"><span data-stu-id="2587e-104">Manage partner relationships</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2587e-105">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="2587e-105">The admin center is changing.</span></span> <span data-ttu-id="2587e-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2587e-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="2587e-107">Microsoft 認定ソリューションプロバイダー (パートナー) と協力して、組織または学校の製品とサービスを購入して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2587e-107">You can work with Microsoft-certified solution providers (partners) to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="2587e-108">設定を行うには、いくつかの手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2587e-108">There are a few steps involved in getting things set up.</span></span>

- <span data-ttu-id="2587e-109">管理者は、でフォームを使用してパートナーを検索して連絡し <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a> ます。</span><span class="sxs-lookup"><span data-stu-id="2587e-109">Admins find and contact a partner using the form at <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
- <span data-ttu-id="2587e-110">パートナーは、パートナー関係を確立するための電子メール要求をお客様に送信します。</span><span class="sxs-lookup"><span data-stu-id="2587e-110">Partners send an email request to customers to establish a partner relationship.</span></span>
- <span data-ttu-id="2587e-111">お客様は、Microsoft 365 管理センターで招待を承諾し、パートナーとの作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="2587e-111">Customers accept the invitation in Microsoft 365 admin center and start working with the partner.</span></span>

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a><span data-ttu-id="2587e-112">組織または学校に対してパートナーは何を行うことができますか?</span><span class="sxs-lookup"><span data-stu-id="2587e-112">What can a partner do for my organization or school?</span></span>

<span data-ttu-id="2587e-113">パートナーは、いくつかの方法でお互いに協力することができます。</span><span class="sxs-lookup"><span data-stu-id="2587e-113">There are several ways that a partner can work with you.</span></span> <span data-ttu-id="2587e-114">指定したビジネスニーズに基づいて、ユーザーが自分と連携する要求を送信するときに、これらの種類のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-114">Based on your stated business needs, they choose one of these types when they send their request to work with you.</span></span>

| <span data-ttu-id="2587e-115">パートナーの種類</span><span class="sxs-lookup"><span data-stu-id="2587e-115">Partner type</span></span> | <span data-ttu-id="2587e-116">説明</span><span class="sxs-lookup"><span data-stu-id="2587e-116">Description</span></span> |
| ------ | ------------------- |
| <span data-ttu-id="2587e-117">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="2587e-117">Reseller</span></span> | <span data-ttu-id="2587e-118">組織または学校に Microsoft 製品を販売するパートナー。</span><span class="sxs-lookup"><span data-stu-id="2587e-118">Partners that sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="2587e-119">代理管理者</span><span class="sxs-lookup"><span data-stu-id="2587e-119">Delegated administrator</span></span> | <span data-ttu-id="2587e-120">組織または学校の製品とサービスを管理するパートナー。</span><span class="sxs-lookup"><span data-stu-id="2587e-120">Partners that manage products and services for your organization or school.</span></span> <span data-ttu-id="2587e-121">Azure Active Directory (AD) では、パートナーはテナントのグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="2587e-121">In Azure Active Directory (AD), the partner is a Global Administrator for your tenant.</span></span> <span data-ttu-id="2587e-122">この役割により、ユーザーアカウントの作成、ライセンスの割り当てと管理、パスワードのリセットなどのサービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2587e-122">This role lets them manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="2587e-123">販売店 & 代理管理者</span><span class="sxs-lookup"><span data-stu-id="2587e-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="2587e-124">組織または学校に Microsoft 製品とサービスを販売および管理するパートナー。</span><span class="sxs-lookup"><span data-stu-id="2587e-124">Partners that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="2587e-125">パートナー</span><span class="sxs-lookup"><span data-stu-id="2587e-125">Partner</span></span> | <span data-ttu-id="2587e-126">自分のテナントでパートナーにユーザーアカウントを提供し、自分の代わりに他の Microsoft サービスと連携します。</span><span class="sxs-lookup"><span data-stu-id="2587e-126">You give your partner a user account in your tenant, and they work with other Microsoft services on your behalf.</span></span> |
| <span data-ttu-id="2587e-127">様</span><span class="sxs-lookup"><span data-stu-id="2587e-127">Advisor</span></span> | <span data-ttu-id="2587e-128">パートナーは、パスワードをリセットし、サポートインシデントを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="2587e-128">Partners can reset passwords and handle support incidents for you.</span></span> |
| <span data-ttu-id="2587e-129">Microsoft 製品 & サービス契約 (MPSA) パートナー</span><span class="sxs-lookup"><span data-stu-id="2587e-129">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="2587e-130">MPSA プログラムを使用して複数のパートナーと協力してきた場合は、互いに購入したものを表示することを許可できます。</span><span class="sxs-lookup"><span data-stu-id="2587e-130">If you've worked with multiple partners through the MPSA program, you can allow them to see purchases made by each other.</span></span> |
| <span data-ttu-id="2587e-131">OEM PC パートナー</span><span class="sxs-lookup"><span data-stu-id="2587e-131">OEM PC partner</span></span> | <span data-ttu-id="2587e-132">パートナーは、[自動操縦を使用](https://docs.microsoft.com/microsoft-store/add-profile-to-devices)して管理している pc のデバイス id をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="2587e-132">Partners can upload device IDs for PCs that you're [managing with Autopilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).</span></span> |
| <span data-ttu-id="2587e-133">基幹業務 (LOB) パートナー</span><span class="sxs-lookup"><span data-stu-id="2587e-133">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="2587e-134">パートナーは、組織または学校に固有の LOB アプリを開発、提出、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="2587e-134">Partners can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-partner"></a><span data-ttu-id="2587e-135">パートナーを検索する</span><span class="sxs-lookup"><span data-stu-id="2587e-135">Find a partner</span></span>

1. <span data-ttu-id="2587e-136"><a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a> に移動します。</span><span class="sxs-lookup"><span data-stu-id="2587e-136">Go to <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="2587e-137">自分の場所を入力し、組織のサイズを選択し、必要なサービスの種類のキーワードを追加して、[**移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-137">Enter your location, choose your organization size, add keywords for the type of services you need, then select **Go**.</span></span>
3. <span data-ttu-id="2587e-138">1つ以上のパートナーを選択し、[**選択したプロバイダーに連絡**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-138">Choose one or more partners, then select **Contact selected providers**.</span></span>
4. <span data-ttu-id="2587e-139">業務上の必要性について説明するようにフォームを完成させ、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-139">Complete the form to describe your business needs, then select **Send**.</span></span>

<span data-ttu-id="2587e-140">パートナーは、自分と連絡をとって、自分についての情報を得る機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="2587e-140">The partner contacts you and gives you a chance to learn more about them.</span></span> <span data-ttu-id="2587e-141">それらを使用することにした場合は、パートナー関係を確立するために電子メール招待状を送信します。</span><span class="sxs-lookup"><span data-stu-id="2587e-141">If you decide to work with them, they send you an email invitation to establish a partner relationship.</span></span>

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a><span data-ttu-id="2587e-142">パートナー関係と Microsoft カスタマーアグリーメントを確認して同意する</span><span class="sxs-lookup"><span data-stu-id="2587e-142">Review and accept a partner relationship and Microsoft Customer Agreement</span></span>

<span data-ttu-id="2587e-143">パートナーを見つけ、それを使用することを決定したら、電子メール招待状を送信します。</span><span class="sxs-lookup"><span data-stu-id="2587e-143">After you find a partner and decide to work with them, they send you an email invitation.</span></span>

1. <span data-ttu-id="2587e-144">電子メールで、Microsoft 365 管理センターに移動するリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-144">In the email, select the link to go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="2587e-145">[**契約の承諾 & パートナーの承認**] ページで、 **Microsoft カスタマーアグリーメント**のリンクを選択し、ドキュメントを参照します。</span><span class="sxs-lookup"><span data-stu-id="2587e-145">On the **Accept agreement & authorize partner** page, select the link for the **Microsoft Customer Agreement**, and read the document.</span></span>
3. <span data-ttu-id="2587e-146">このチェックボックスをオンにして、契約を読んだことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2587e-146">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="2587e-147">[**同意 & 承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-147">Select **Accept & Authorize**.</span></span>
5. <span data-ttu-id="2587e-148">作業しているパートナーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2587e-148">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="2587e-149">詳細を表示するには、任意のパートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-149">Select any partner to see details.</span></span>

## <a name="review-and-accept-a-microsoft-customer-agreement"></a><span data-ttu-id="2587e-150">Microsoft カスタマーアグリーメントを確認して同意する</span><span class="sxs-lookup"><span data-stu-id="2587e-150">Review and accept a Microsoft Customer Agreement</span></span>

<span data-ttu-id="2587e-151">パートナーがすでにお客様に登録されていない場合は、お客様の代わりにサブスクリプションを購入または管理できるように、契約書に同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2587e-151">If you already have a partner but haven’t yet signed a Microsoft Customer Agreement, you must accept the agreement before they can make purchases or manage your subscriptions on your behalf.</span></span>

1. <span data-ttu-id="2587e-152">パートナーから電子メールを受信した場合は、リンクを選択して Microsoft 365 管理センターに移動するか、[<a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">同意</a>する] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2587e-152">If you receive an email from your partner, select the link to go to the Microsoft 365 admin center, or go to the <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Accept agreement</a> page.</span></span>
2. <span data-ttu-id="2587e-153">**Microsoft カスタマーアグリーメント**のリンクを選択し、ドキュメントを参照します。</span><span class="sxs-lookup"><span data-stu-id="2587e-153">Select the link for the **Microsoft Customer Agreement** and read the document.</span></span>
3. <span data-ttu-id="2587e-154">このチェックボックスをオンにして、契約を読んだことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2587e-154">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="2587e-155">**[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-155">Select **Accept**.</span></span>
5. <span data-ttu-id="2587e-156">作業しているパートナーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2587e-156">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="2587e-157">詳細を表示するには、任意のパートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-157">Select any partner to see details.</span></span>

## <a name="remove-partner-admin-privileges"></a><span data-ttu-id="2587e-158">パートナー管理者権限を削除する</span><span class="sxs-lookup"><span data-stu-id="2587e-158">Remove partner admin privileges</span></span>

<span data-ttu-id="2587e-159">パートナーによって行われた要求に応じて、招待を承諾する一部には、委任された管理者権限を付与することが同意されます。</span><span class="sxs-lookup"><span data-stu-id="2587e-159">Depending on the request made by the partner, part of accepting the invitation includes agreeing to give delegated admin privileges to the them.</span></span> <span data-ttu-id="2587e-160">詳細については、「 [AZURE AD での管理者権限の委任](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2587e-160">For more information, see [Delegated admin privileges in Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span>

<span data-ttu-id="2587e-161">管理者特権をパートナーに委任しない場合は、招待を承諾するのではなく、キャンセルします。</span><span class="sxs-lookup"><span data-stu-id="2587e-161">If you don't want to delegate admin privileges to the partner, cancel the invitation instead of accepting it.</span></span>

<span data-ttu-id="2587e-162">パートナーに管理者権限を委任する場合は、いつでもそれらの権限を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="2587e-162">If you delegate admin privileges to a partner, you can remove those privileges at any time.</span></span> <span data-ttu-id="2587e-163">管理者権限を削除しても、パートナー関係は削除されません。</span><span class="sxs-lookup"><span data-stu-id="2587e-163">Removing admin privileges doesn’t remove the partner relationship.</span></span> <span data-ttu-id="2587e-164">ユーザーは、たとえば販売店として作業することができます。</span><span class="sxs-lookup"><span data-stu-id="2587e-164">They can still work with you, for example, as a Reseller.</span></span>

1. <span data-ttu-id="2587e-165">管理センターで、 **[課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">アカウント</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2587e-165">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing accounts</a> page.</span></span>
2. <span data-ttu-id="2587e-166">[**課金アカウント**] ページで、[**パートナー関係**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-166">On the **Billing accounts** page, select the **Partner relationships** tab.</span></span>
3. <span data-ttu-id="2587e-167">パートナーの名前を含む行を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-167">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="2587e-168">[パートナー] ページで、[**管理者ロールの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-168">On the partner page, select **Remove admin roles**.</span></span>

## <a name="delete-a-partner-relationship"></a><span data-ttu-id="2587e-169">パートナー関係を削除する</span><span class="sxs-lookup"><span data-stu-id="2587e-169">Delete a partner relationship</span></span>

<span data-ttu-id="2587e-170">パートナーとの共同作業を行わないと判断した場合は、関係を終了することができます。</span><span class="sxs-lookup"><span data-stu-id="2587e-170">If you decide that you don’t want to work with a partner anymore, you can end the relationship.</span></span> <span data-ttu-id="2587e-171">ただし、パートナーが委任された管理者またはアドバイザーの場合のみ、リレーションシップを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2587e-171">However, you can only delete relationships where the partner is either a Delegated Administrator or an Advisor.</span></span> <span data-ttu-id="2587e-172">他のすべてのパートナーの種類については、パートナーに連絡してリレーションシップを終了させるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2587e-172">For all other partner types, contact your partner to end the relationship.</span></span>

1. <span data-ttu-id="2587e-173">管理センターで、 **[課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">アカウント</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2587e-173">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing accounts</a> page.</span></span>
2. <span data-ttu-id="2587e-174">[**課金アカウント**] ページで、[**パートナー関係**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-174">On the **Billing accounts** page, select the **Partner relationships** tab.</span></span>
3. <span data-ttu-id="2587e-175">パートナーの名前を含む行を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-175">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="2587e-176">[パートナーの詳細] ページで、[**パートナーの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2587e-176">On the partner detail page, select **Delete partner**.</span></span>
