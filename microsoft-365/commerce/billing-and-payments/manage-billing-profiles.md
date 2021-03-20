---
title: 課金プロファイルを理解する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- Commerce
search.appverid:
- MET150
description: 請求プロファイルが請求書をサポートする方法について学習します。
ms.openlocfilehash: 2f56b9a3edbbbe14927df64bed8b699a68826c9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911868"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="6cd89-103">課金プロファイルを理解する</span><span class="sxs-lookup"><span data-stu-id="6cd89-103">Understand billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6cd89-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="6cd89-104">The admin center is changing.</span></span> <span data-ttu-id="6cd89-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cd89-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="6cd89-106">Microsoft から製品やサービスを購入する商用顧客の場合、請求プロファイルを使用すると、請求書に含まれるアイテムと請求書の支払い方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-106">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="6cd89-107">課金プロファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-107">Billing profiles include the following information:</span></span>

- <span data-ttu-id="6cd89-108">**課金アカウント** &ndash; プロファイルが関連付けされている請求先アカウントの名前</span><span class="sxs-lookup"><span data-stu-id="6cd89-108">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="6cd89-109">**支払い方法** &ndash; クレジット カードまたはデビット カード、銀行口座、チェック、または電信送金</span><span class="sxs-lookup"><span data-stu-id="6cd89-109">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="6cd89-110">**連絡先情報** &ndash; 請求先住所と連絡先名</span><span class="sxs-lookup"><span data-stu-id="6cd89-110">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="6cd89-111">**請求書の設定** &ndash; 請求先アカウントの国、オプションの PO 番号、および電子メールの添付ファイルとして請求書を受け取るオプションに基づく通貨</span><span class="sxs-lookup"><span data-stu-id="6cd89-111">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="6cd89-112">**アクセス許可** &ndash; 請求プロファイルの変更、請求書の支払い、または請求プロファイルの支払い方法を使用して購入を行う権限</span><span class="sxs-lookup"><span data-stu-id="6cd89-112">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="6cd89-113">課金プロファイルを使用して、購入を制御し、請求書をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6cd89-113">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="6cd89-114">請求プロファイルを使用して購入した製品に対して、月次請求書が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-114">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="6cd89-115">発注書番号の更新や電子メールの請求書の設定など、請求書をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-115">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="6cd89-116">最初の購入時に、請求アカウントの請求プロファイルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-116">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="6cd89-117">[請求プロファイル] ページで請求プロファイルを <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">作成して</a> 、より多くの請求書を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-117">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="6cd89-118">たとえば、組織内の各部門に対して購入を行う際に、異なる請求プロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-118">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="6cd89-119">次の請求日に、請求プロファイルごとに請求書を受け取る予定です。</span><span class="sxs-lookup"><span data-stu-id="6cd89-119">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="6cd89-120">課金プロファイルの役割</span><span class="sxs-lookup"><span data-stu-id="6cd89-120">Billing profile roles</span></span>

<span data-ttu-id="6cd89-121">課金プロファイルのロールには、購入を制御し、請求書を表示および管理するためのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="6cd89-121">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="6cd89-122">組織内の調達チームのメンバーなど、請求書を追跡、整理、支払うユーザーにこれらの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-122">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="6cd89-123">Role</span><span class="sxs-lookup"><span data-stu-id="6cd89-123">Role</span></span>                          | <span data-ttu-id="6cd89-124">説明</span><span class="sxs-lookup"><span data-stu-id="6cd89-124">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="6cd89-125">課金プロファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="6cd89-125">Billing profile owner</span></span>         | <span data-ttu-id="6cd89-126">課金プロファイルに関するすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="6cd89-126">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="6cd89-127">課金プロファイル投稿者</span><span class="sxs-lookup"><span data-stu-id="6cd89-127">Billing profile contributor</span></span>   | <span data-ttu-id="6cd89-128">課金プロファイルのアクセス許可を除くすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="6cd89-128">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="6cd89-129">課金プロファイル リーダー</span><span class="sxs-lookup"><span data-stu-id="6cd89-129">Billing profile reader</span></span>        | <span data-ttu-id="6cd89-130">課金プロファイル内のすべてのデータの読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="6cd89-130">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="6cd89-131">請求書マネージャー</span><span class="sxs-lookup"><span data-stu-id="6cd89-131">Invoice manager</span></span>               | <span data-ttu-id="6cd89-132">請求書の表示と支払い、および請求プロファイル内のすべての情報の読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="6cd89-132">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="6cd89-133">請求プロファイルの表示</span><span class="sxs-lookup"><span data-stu-id="6cd89-133">View billing profiles</span></span>

1. <span data-ttu-id="6cd89-134">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6cd89-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="6cd89-135">[ **課金プロファイル] を** 選択し、一覧から請求プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="6cd89-135">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="6cd89-136">[概要 **] タブ** で、請求プロファイルの詳細を編集し、電子メールによる請求書の送信をオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-136">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="6cd89-137">[アクセス許可 **] タブ** で、請求書を支払う役割をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-137">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="6cd89-138">[Azure クレジット **残高] タブ** で、Azure のお客様は、その請求プロファイルで使用される Azure クレジットのトランザクション残高履歴を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-138">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="6cd89-139">Azure の **[クレジット] タブ** で、Azure のお客様は、その請求プロファイルに関連付けられている Azure クレジットの一覧と有効期限を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6cd89-139">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6cd89-140">Azure クレジットを持ってない場合は、[Azure クレジット残高] タブまたは **[Azure** クレジット] **タブは表示** されません。</span><span class="sxs-lookup"><span data-stu-id="6cd89-140">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="6cd89-141">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="6cd89-141">Need help?</span></span> <span data-ttu-id="6cd89-142">サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6cd89-142">Contact support.</span></span>

<span data-ttu-id="6cd89-143">Azure の料金に関する質問やサポートが必要な場合は、Azure サポートを <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">使用してサポート 要求を作成します</a>。</span><span class="sxs-lookup"><span data-stu-id="6cd89-143">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="6cd89-144">Microsoft 365 管理センターで請求プロファイルに関する質問やヘルプが必要な場合は、ビジネス [製品のサポートにお問い合わせください](/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="6cd89-144">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](/office365/admin/contact-support-for-business-products).</span></span>