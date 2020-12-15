---
title: 課金プロファイルについて
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
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667779"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="e42d1-103">課金プロファイルについて</span><span class="sxs-lookup"><span data-stu-id="e42d1-103">Understand billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e42d1-104">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="e42d1-104">The admin center is changing.</span></span> <span data-ttu-id="e42d1-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e42d1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="e42d1-106">Microsoft から製品やサービスを購入する商用のお客様の場合、課金プロファイルを使用すると、請求書に含めるアイテムや請求書の支払い方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-106">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="e42d1-107">課金プロファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-107">Billing profiles include the following information:</span></span>

- <span data-ttu-id="e42d1-108">**課金アカウント** &ndash; プロファイルが関連付けされている請求アカウントの名前</span><span class="sxs-lookup"><span data-stu-id="e42d1-108">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="e42d1-109">**支払い方法** &ndash; クレジット カードまたはデビット カード、銀行口座、チェック、または電信送金</span><span class="sxs-lookup"><span data-stu-id="e42d1-109">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="e42d1-110">**連絡先情報** &ndash; 請求先住所と連絡先名</span><span class="sxs-lookup"><span data-stu-id="e42d1-110">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="e42d1-111">**請求書の設定** &ndash; 請求アカウントの国、オプションの PO 番号、および電子メールの添付ファイルとして請求書を受信するオプションに基づく通貨</span><span class="sxs-lookup"><span data-stu-id="e42d1-111">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="e42d1-112">**アクセス許可** &ndash; 請求プロファイルの変更、請求書の支払い、または請求プロファイルの支払い方法を使用して購入を行えるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e42d1-112">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="e42d1-113">課金プロファイルを使用して購入を制御し、請求書をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="e42d1-113">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="e42d1-114">請求プロファイルで購入した製品に対して月次請求書が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-114">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="e42d1-115">発注書番号や電子メールの請求書の設定の更新など、請求書をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-115">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="e42d1-116">最初の購入時に、請求アカウントの請求プロファイルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-116">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="e42d1-117">[課金プロファイル] ページで請求プロファイル <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">を作成</a> し、さらに請求書を設定できます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-117">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="e42d1-118">たとえば、組織内の部署ごとに購入を行う場合は、異なる請求プロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-118">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="e42d1-119">次回の請求日に、請求プロファイルごとに請求書が届く予定です。</span><span class="sxs-lookup"><span data-stu-id="e42d1-119">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="e42d1-120">課金プロファイル ロール</span><span class="sxs-lookup"><span data-stu-id="e42d1-120">Billing profile roles</span></span>

<span data-ttu-id="e42d1-121">課金プロファイルのロールには、購入を制御し、請求書を表示および管理するためのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="e42d1-121">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="e42d1-122">組織内の調達チームのメンバーなど、請求書を追跡、整理、支払うユーザーに、これらの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-122">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="e42d1-123">役割</span><span class="sxs-lookup"><span data-stu-id="e42d1-123">Role</span></span>                          | <span data-ttu-id="e42d1-124">説明</span><span class="sxs-lookup"><span data-stu-id="e42d1-124">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="e42d1-125">課金プロファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="e42d1-125">Billing profile owner</span></span>         | <span data-ttu-id="e42d1-126">課金プロファイルのすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="e42d1-126">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="e42d1-127">課金プロファイル投稿者</span><span class="sxs-lookup"><span data-stu-id="e42d1-127">Billing profile contributor</span></span>   | <span data-ttu-id="e42d1-128">課金プロファイルのアクセス許可以外のすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="e42d1-128">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="e42d1-129">課金プロファイル閲覧者</span><span class="sxs-lookup"><span data-stu-id="e42d1-129">Billing profile reader</span></span>        | <span data-ttu-id="e42d1-130">課金プロファイル内のすべてのデータの読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="e42d1-130">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="e42d1-131">請求書マネージャー</span><span class="sxs-lookup"><span data-stu-id="e42d1-131">Invoice manager</span></span>               | <span data-ttu-id="e42d1-132">課金プロファイル内のすべての情報を読み取り専用で表示し、請求書を表示および支払う</span><span class="sxs-lookup"><span data-stu-id="e42d1-132">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="e42d1-133">課金プロファイルの表示</span><span class="sxs-lookup"><span data-stu-id="e42d1-133">View billing profiles</span></span>

1. <span data-ttu-id="e42d1-134">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="e42d1-135">[ **課金プロファイル] を** 選択し、一覧から請求プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-135">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="e42d1-136">[概要 **] タブ** では、請求プロファイルの詳細を編集し、電子メールによる請求書の送信をオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-136">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="e42d1-137">[アクセス許可 **] タブでは** 、請求書を支払う役割をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-137">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="e42d1-138">Azure の **[与信残高]** タブで、Azure のお客様は、その請求プロファイルで使用される Azure クレジットのトランザクション残高履歴を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-138">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="e42d1-139">Azure の **[クレジット]** タブで、Azure のお客様は、その請求プロファイルに関連付けられている Azure クレジットの一覧と有効期限を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-139">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e42d1-140">Azure クレジットをお持ちない場合は **、Azure** クレジット残高タブまたは Azure クレジット **タブは表示** されません。</span><span class="sxs-lookup"><span data-stu-id="e42d1-140">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="e42d1-141">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="e42d1-141">Need help?</span></span> <span data-ttu-id="e42d1-142">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e42d1-142">Contact support.</span></span>

<span data-ttu-id="e42d1-143">Azure の料金について質問がある場合やサポートが必要な場合は <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">、Azure サポートでサポートリクエストを作成します</a>。</span><span class="sxs-lookup"><span data-stu-id="e42d1-143">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="e42d1-144">Microsoft 365 管理センターで請求プロファイルに関する質問やサポートが必要な場合は、ビジネス製品の [サポートにお問い合わせください](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="e42d1-144">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
