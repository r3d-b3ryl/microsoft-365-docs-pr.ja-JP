---
title: 請求アカウントを理解する
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
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: 課金アカウントと、アカウント設定、請求書、支払い方法、および購入の管理に使用される方法について説明します。
ms.date: 03/17/2021
ms.openlocfilehash: 7b19c30a8a11a816d5cd8906cdb96da36688573c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394401"
---
# <a name="understand-billing-accounts"></a><span data-ttu-id="62789-103">請求アカウントを理解する</span><span class="sxs-lookup"><span data-stu-id="62789-103">Understand billing accounts</span></span>

<span data-ttu-id="62789-104">Microsoft 製品を試用または購入するためにサインアップすると、課金アカウントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="62789-104">A billing account is created when you sign up to try or buy Microsoft products.</span></span> <span data-ttu-id="62789-105">課金アカウントを使用して、アカウント設定、請求書、支払い方法、購入を管理します。</span><span class="sxs-lookup"><span data-stu-id="62789-105">You use your billing account to manage your account settings, invoices, payment methods, and purchases.</span></span> <span data-ttu-id="62789-106">複数の請求アカウントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62789-106">You can have access to multiple billing accounts.</span></span> <span data-ttu-id="62789-107">たとえば、Microsoft 365 に直接サインアップした場合、または組織の Enterprise Agreement、Microsoft 製品 & サービス契約、または Microsoft カスタマー 契約にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62789-107">For example, you signed up for Microsoft 365 directly, or you have access to your organization's Enterprise Agreement, Microsoft Product & Services Agreement or Microsoft Customer Agreement.</span></span> <span data-ttu-id="62789-108">これらのシナリオごとに、個別の請求アカウントを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="62789-108">For each of these scenarios, you would have a separate billing account.</span></span>

<span data-ttu-id="62789-109">現在、Microsoft 365 管理センターは、次の種類の請求アカウントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="62789-109">The Microsoft 365 admin center currently supports the following type of billing accounts:</span></span>

- <span data-ttu-id="62789-110">Microsoft Online Servicesプログラム: この課金アカウントは、サブスクリプションに直接サインアップするときにMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="62789-110">Microsoft Online Services Program: This billing account is created when you sign up for a Microsoft 365 subscription directly.</span></span>
- <span data-ttu-id="62789-111">Microsoft Products & サービス契約 (MPSA) プログラム: この請求アカウントは、組織がソフトウェアおよびオンライン サービスを購入するために MPSA ボリューム ライセンス契約に署名するときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="62789-111">Microsoft Products & Services Agreement (MPSA) Program: This billing account is created when your organization signs an MPSA Volume Licensing agreement to purchase software and online services.</span></span>
- <span data-ttu-id="62789-112">Microsoft カスタマー 契約: この請求アカウントは、組織が Microsoft 担当者、認定パートナー、または個別に購入するときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="62789-112">Microsoft Customer Agreement: This billing account is created when your organization works with a Microsoft representative, an authorized partner, or purchases independently.</span></span>

<span data-ttu-id="62789-113">[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">課金アカウント]</a> ページには、Microsoft の商用アカウントのビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62789-113">The <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Billing accounts</a> page provides a view of your commercial accounts with Microsoft.</span></span> <span data-ttu-id="62789-114">既定では、組織には、直接購入時に、またはボリューム ライセンスの取り決めによって受け入れられる契約に関連付けられた請求アカウントが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="62789-114">By default, your organization has at least one billing account associated with an agreement that is accepted either at the time of a direct purchase, or through a Volume Licensing arrangement.</span></span>

## <a name="understand-billing-account-details"></a><span data-ttu-id="62789-115">課金アカウントの詳細を理解する</span><span class="sxs-lookup"><span data-stu-id="62789-115">Understand billing account details</span></span>

<span data-ttu-id="62789-116">[課金アカウント] **詳細ページの** 上部にはアカウント プロファイルが表示され、組織に関する法的情報と税金情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="62789-116">The top of the **Billing accounts** detail page is your account profile and contains legal and tax information about your organization.</span></span> <span data-ttu-id="62789-117">プロフィールを更新して、法的な住所と電話番号を変更できます。</span><span class="sxs-lookup"><span data-stu-id="62789-117">You can update your profile to change your legal address and phone number.</span></span> <span data-ttu-id="62789-118">このアカウントは、購入した製品に対して支払う法人です。</span><span class="sxs-lookup"><span data-stu-id="62789-118">This account is the legal entity that pays for the products that you purchase.</span></span>

<span data-ttu-id="62789-119">次の表に、[課金アカウント] 詳細ページに表示される重要 **な用語を** 示します。</span><span class="sxs-lookup"><span data-stu-id="62789-119">The following table lists the important terms that you see in the **Billing accounts** detail page.</span></span>

| <span data-ttu-id="62789-120">フィールド名</span><span class="sxs-lookup"><span data-stu-id="62789-120">Field name</span></span> | <span data-ttu-id="62789-121">説明</span><span class="sxs-lookup"><span data-stu-id="62789-121">Description</span></span> |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="62789-122">販売先住所</span><span class="sxs-lookup"><span data-stu-id="62789-122">Sold-to address</span></span> | <span data-ttu-id="62789-123">支払いを担当し、請求書で識別される法人。</span><span class="sxs-lookup"><span data-stu-id="62789-123">The legal entity responsible for payment and identified on the invoice.</span></span> <span data-ttu-id="62789-124">ここに記載されている住所は、購入時に別の配送先住所を提供することを選択しない限り、税率を決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="62789-124">The address provided here is used to determine your tax rate unless you opt to provide an alternative shipping address during your purchase.</span></span> <span data-ttu-id="62789-125">詳細については、「[税金情報](billing-and-payments/tax-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62789-125">For more information, see [Tax information](billing-and-payments/tax-information.md).</span></span> |
| <span data-ttu-id="62789-126">セグメント</span><span class="sxs-lookup"><span data-stu-id="62789-126">Segment</span></span> | <span data-ttu-id="62789-127">組織のビジネス セグメント (商用、教育、政府機関、非営利) を識別する読み取り専用フィールド。</span><span class="sxs-lookup"><span data-stu-id="62789-127">A read-only field that identifies the business segment of your organization (Commercial, Education, Government, or Non-profit).</span></span> |
| <span data-ttu-id="62789-128">アカウントの状態</span><span class="sxs-lookup"><span data-stu-id="62789-128">Account status</span></span> | <span data-ttu-id="62789-129">Microsoft での商用アカウントの状態を指定する読み取り専用フィールド。</span><span class="sxs-lookup"><span data-stu-id="62789-129">A read-only field that specifies the status of your commercial account with Microsoft.</span></span> |
| <span data-ttu-id="62789-130">Tax ID</span><span class="sxs-lookup"><span data-stu-id="62789-130">Tax ID</span></span> | <span data-ttu-id="62789-131">米国外の場合は、VAT または現地同等の付加価値税を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62789-131">If you are outside the United States, you must provide a VAT or local equivalent.</span></span> <span data-ttu-id="62789-132">詳細については、「[税金情報](billing-and-payments/tax-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62789-132">For more information, see [Tax information](billing-and-payments/tax-information.md).</span></span> |
| <span data-ttu-id="62789-133">契約</span><span class="sxs-lookup"><span data-stu-id="62789-133">Agreement</span></span> | <span data-ttu-id="62789-134">請求アカウントが作成されると、直接購入またはボリューム ライセンス契約を通じて、組織の署名者は、アカウントの & 条件の概要を示す契約を受け入れるか、または署名します。</span><span class="sxs-lookup"><span data-stu-id="62789-134">When a billing account is created, either through a direct purchase or a Volume Licensing arrangement, a signatory for the organization accepts, or signs, an agreement that outlines the terms & conditions of the account.</span></span> <span data-ttu-id="62789-135">該当する場合、このビューには契約履歴が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="62789-135">If applicable, this view lists an agreement history.</span></span> <span data-ttu-id="62789-136">更新された条項に同意する必要がある場合は、[契約の承認] の **リンクが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="62789-136">If you're required to accept updated terms, a link for **Approve agreement** is displayed.</span></span> |
| <span data-ttu-id="62789-137">課金プロファイル</span><span class="sxs-lookup"><span data-stu-id="62789-137">Billing profiles</span></span> | <span data-ttu-id="62789-138">請求プロファイルは、請求書を受け取るユーザー、請求書の配信方法、支払い条件、および PO 番号など、請求書のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="62789-138">A billing profile defines properties of your invoice, like who receives the bill, how the bill is delivered, payment terms, and a PO number.</span></span> <span data-ttu-id="62789-139">組織全体に課金を分散するには、複数の請求プロファイルを作成し、購入時に適切な請求プロファイルを特定できます。</span><span class="sxs-lookup"><span data-stu-id="62789-139">To distribute billing across your organization, you can create multiple billing profiles and identify the appropriate billing profile at the time of purchase.</span></span> <span data-ttu-id="62789-140">請求プロファイルの詳細と、それらを使用して組織のより柔軟な請求オプションを構築する方法については、「請求プロファイルについて [」を参照してください](billing-and-payments/manage-billing-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="62789-140">For more information about billing profiles and how you can use them to build more flexible billing options for your organization, [Understand billing profiles](billing-and-payments/manage-billing-profiles.md).</span></span> |

> [!NOTE]
> <span data-ttu-id="62789-141">販売先の名前または住所 **を** 変更する必要があるが、[編集] リンクが表示されない場合は、サポートに問い合わせ、[変更する必要](../business-video/get-help-support.md)があります。</span><span class="sxs-lookup"><span data-stu-id="62789-141">If you need to change the **Sold-to** name or address, but don't see an **Edit** link, you must [contact support](../business-video/get-help-support.md) to change it.</span></span> <span data-ttu-id="62789-142">販売名の **変更を** 要求するには、クレジット チェックが必要です。</span><span class="sxs-lookup"><span data-stu-id="62789-142">Requests for a **Sold-to** name change will require a credit check.</span></span> <span data-ttu-id="62789-143">この [フォームに記入](https://www.microsoft.com/download/details.aspx?id=102732)し、サポートに問い合わせするときに、次のいずれかのドキュメントを Microsoft と共有する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="62789-143">Complete [this form](https://www.microsoft.com/download/details.aspx?id=102732), and be ready to share one of following documents with Microsoft when you contact support:</span></span>
>
> - <span data-ttu-id="62789-144">政府発行の文書または登録書</span><span class="sxs-lookup"><span data-stu-id="62789-144">Government-issued document or registration letter</span></span>
> - <span data-ttu-id="62789-145">ローカル企業のレジストリから印刷する</span><span class="sxs-lookup"><span data-stu-id="62789-145">Print out of the local company's registry</span></span>
>
> <span data-ttu-id="62789-146">サポートは、顧客名だけが変更される名前と住所の変更に役立ちますが、エンティティは変わりません。</span><span class="sxs-lookup"><span data-stu-id="62789-146">Support can help with name and address changes where only the customer name changes, but the entity remains the same.</span></span> <span data-ttu-id="62789-147">提供されているドキュメントは、エンティティの名前だけが変更されたと明確に示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="62789-147">Documentation provided should clearly show that only the entity's name has changed.</span></span> <span data-ttu-id="62789-148">ビジネスの売却、コントロールの変更、顧客アフィリエイトの売却または「スピンオフ」など、取引の結果が変更された場合は、Microsoft Seller にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="62789-148">If the change is the result of a transaction, including the sale of business, a change of controls, or a divestiture or "spinoff" of a Customer Affiliate, please contact your Microsoft Seller.</span></span>

## <a name="shipping-addresses"></a><span data-ttu-id="62789-149">配送先住所</span><span class="sxs-lookup"><span data-stu-id="62789-149">Shipping addresses</span></span>

<span data-ttu-id="62789-150">このセクションでは、請求先アカウントに関連付けられている配送先住所を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="62789-150">This section lists the shipping addresses associated with your billing account.</span></span> <span data-ttu-id="62789-151">購入を行う場合は、このアドレスを使用して、購入の出荷または使用場所を特定できます。</span><span class="sxs-lookup"><span data-stu-id="62789-151">When you make a purchase, you can use this address to identify where your purchase is shipped or used.</span></span> <span data-ttu-id="62789-152">配送先住所は編集可能です。</span><span class="sxs-lookup"><span data-stu-id="62789-152">The shipping address is editable.</span></span> <span data-ttu-id="62789-153">配送先住所を追加するか、既存の住所を更新できます。</span><span class="sxs-lookup"><span data-stu-id="62789-153">You can add a shipping address or update the existing address.</span></span> <span data-ttu-id="62789-154">このアドレスは、購入の税率を決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="62789-154">This address is used to determine the tax rate for your purchase.</span></span>

## <a name="understand-access-to-billing-accounts"></a><span data-ttu-id="62789-155">課金アカウントへのアクセスを理解する</span><span class="sxs-lookup"><span data-stu-id="62789-155">Understand access to billing accounts</span></span>

<span data-ttu-id="62789-156">他のユーザーには、ロールとアクセス許可を使用して、Microsoft 365 管理センターアカウントへのアクセス権を提供できます。</span><span class="sxs-lookup"><span data-stu-id="62789-156">You can provide others with access to the billing account in the Microsoft 365 admin center through roles and permissions.</span></span> <span data-ttu-id="62789-157">課金アカウントへのアクセスを許可できるのは、請求アカウントの所有者のみです。</span><span class="sxs-lookup"><span data-stu-id="62789-157">Only a billing account owner can grant access to a billing account.</span></span> <span data-ttu-id="62789-158">次のいずれかの役割をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="62789-158">You can assign one of the following roles to users:</span></span>

- <span data-ttu-id="62789-159">**課金アカウントの所有者** &mdash; アクセス許可の割り当て、アカウントの編集、契約の署名、アカウントの表示を行えます。</span><span class="sxs-lookup"><span data-stu-id="62789-159">**Billing account owner** &mdash; Can assign permissions, edit accounts, sign agreements, and view accounts.</span></span>
- <span data-ttu-id="62789-160">**課金アカウントの投稿者** &mdash; アカウントの編集、契約への署名、アカウントの表示を行えます。</span><span class="sxs-lookup"><span data-stu-id="62789-160">**Billing account contributor** &mdash; Can edit accounts, sign agreements, and view accounts.</span></span>
- <span data-ttu-id="62789-161">**課金アカウント リーダー** &mdash; アカウントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="62789-161">**Billing account reader** &mdash; Can view accounts.</span></span>

> [!Note]
> <span data-ttu-id="62789-162">課金アカウントの役割は課金アカウントにのみ適用され、他の課金シナリオにはMicrosoft 365 管理センターされません。</span><span class="sxs-lookup"><span data-stu-id="62789-162">Billing account roles only apply to billing accounts, and don't apply to other Microsoft 365 admin center scenarios.</span></span>

## <a name="related-content"></a><span data-ttu-id="62789-163">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="62789-163">Related content</span></span>

<span data-ttu-id="62789-164">[税金情報](billing-and-payments/tax-information.md) (記事) </span><span class="sxs-lookup"><span data-stu-id="62789-164">[Tax information](billing-and-payments/tax-information.md) (article) </span></span>\
<span data-ttu-id="62789-165">[請求プロファイルについて](billing-and-payments/manage-billing-profiles.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="62789-165">[Understand billing profiles](billing-and-payments/manage-billing-profiles.md) (article)</span></span>
