---
title: 課金プロファイルを理解する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
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
- commerce_billing
search.appverid: MET150
description: 請求プロファイルが請求書をサポートする方法について学習します。
ms.date: 04/02/2021
ms.openlocfilehash: 36d762e50627763b7856ed1fe6c109e8da2b4789
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332032"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="78a7e-103">課金プロファイルを理解する</span><span class="sxs-lookup"><span data-stu-id="78a7e-103">Understand billing profiles</span></span>

<span data-ttu-id="78a7e-104">Microsoft から製品やサービスを購入する商用顧客の場合、請求プロファイルを使用すると、請求書に含まれるアイテムと請求書の支払い方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-104">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="78a7e-105">課金プロファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-105">Billing profiles include the following information:</span></span>

- <span data-ttu-id="78a7e-106">**課金アカウント** &ndash; プロファイルが関連付けされている請求先アカウントの名前</span><span class="sxs-lookup"><span data-stu-id="78a7e-106">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="78a7e-107">**支払い方法** &ndash; クレジット カードまたはデビット カード、銀行口座、チェック、または電信送金</span><span class="sxs-lookup"><span data-stu-id="78a7e-107">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="78a7e-108">**連絡先情報** &ndash; 請求先住所と連絡先名</span><span class="sxs-lookup"><span data-stu-id="78a7e-108">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="78a7e-109">**請求書の設定** &ndash; 請求先アカウントの国、オプションの PO 番号、および電子メールの添付ファイルとして請求書を受け取るオプションに基づく通貨</span><span class="sxs-lookup"><span data-stu-id="78a7e-109">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="78a7e-110">**アクセス許可** &ndash; 請求プロファイルの変更、請求書の支払い、または請求プロファイルの支払い方法を使用して購入を行う権限</span><span class="sxs-lookup"><span data-stu-id="78a7e-110">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="78a7e-111">課金プロファイルを使用して、購入を制御し、請求書をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="78a7e-111">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="78a7e-112">請求プロファイルを使用して購入した製品に対して、月次請求書が生成されます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-112">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="78a7e-113">発注書番号の更新や電子メールの請求書の設定など、請求書をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-113">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="78a7e-114">最初の購入時に、請求アカウントの請求プロファイルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-114">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="78a7e-115">[請求プロファイル] ページで請求プロファイルを <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">作成して</a> 、より多くの請求書を設定できます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-115">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="78a7e-116">たとえば、組織内の各部門に対して購入を行う際に、異なる請求プロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-116">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="78a7e-117">次の請求日に、請求プロファイルごとに請求書を受け取る予定です。</span><span class="sxs-lookup"><span data-stu-id="78a7e-117">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="78a7e-118">課金プロファイルの役割</span><span class="sxs-lookup"><span data-stu-id="78a7e-118">Billing profile roles</span></span>

<span data-ttu-id="78a7e-119">課金プロファイルのロールには、購入を制御し、請求書を表示および管理するためのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="78a7e-119">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="78a7e-120">組織内の調達チームのメンバーなど、請求書を追跡、整理、支払うユーザーにこれらの役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-120">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="78a7e-121">役割</span><span class="sxs-lookup"><span data-stu-id="78a7e-121">Role</span></span>                         | <span data-ttu-id="78a7e-122">説明</span><span class="sxs-lookup"><span data-stu-id="78a7e-122">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="78a7e-123">課金プロファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="78a7e-123">Billing profile owner</span></span>        | <span data-ttu-id="78a7e-124">課金プロファイルに関するすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="78a7e-124">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="78a7e-125">課金プロファイル投稿者</span><span class="sxs-lookup"><span data-stu-id="78a7e-125">Billing profile contributor</span></span>  | <span data-ttu-id="78a7e-126">課金プロファイルのアクセス許可を除くすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="78a7e-126">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="78a7e-127">課金プロファイル リーダー</span><span class="sxs-lookup"><span data-stu-id="78a7e-127">Billing profile reader</span></span>       | <span data-ttu-id="78a7e-128">課金プロファイル内のすべてのデータの読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="78a7e-128">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="78a7e-129">請求書マネージャー</span><span class="sxs-lookup"><span data-stu-id="78a7e-129">Invoice manager</span></span>              | <span data-ttu-id="78a7e-130">請求書の表示と支払い、および請求プロファイル内のすべての情報の読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="78a7e-130">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-billing-profiles"></a><span data-ttu-id="78a7e-131">請求プロファイルの表示</span><span class="sxs-lookup"><span data-stu-id="78a7e-131">View billing profiles</span></span>

1. <span data-ttu-id="78a7e-132">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="78a7e-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="78a7e-133">[ **課金プロファイル] を** 選択し、一覧から請求プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="78a7e-133">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="78a7e-134">[概要 **] タブ** で、請求プロファイルの詳細を編集し、電子メールによる請求書の送信をオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-134">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>
    - <span data-ttu-id="78a7e-135">[アクセス許可 **] タブ** で、請求書を支払う役割をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-135">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>
    - <span data-ttu-id="78a7e-136">[Azure クレジット **残高] タブ** で、Azure のお客様は、その請求プロファイルで使用される Azure クレジットのトランザクション残高履歴を確認できます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-136">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>
    - <span data-ttu-id="78a7e-137">Azure の **[クレジット] タブ** で、Azure のお客様は、その請求プロファイルに関連付けられている Azure クレジットの一覧と有効期限を確認できます。</span><span class="sxs-lookup"><span data-stu-id="78a7e-137">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78a7e-138">Azure クレジットを持ってない場合は、[Azure クレジット残高] タブまたは **[Azure** クレジット] **タブは表示** されません。</span><span class="sxs-lookup"><span data-stu-id="78a7e-138">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="78a7e-139">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="78a7e-139">Need help?</span></span> <span data-ttu-id="78a7e-140">サポートに連絡</span><span class="sxs-lookup"><span data-stu-id="78a7e-140">Contact support</span></span>

<span data-ttu-id="78a7e-141">Azure の料金に関する質問やサポートが必要な場合は、Azure サポートを <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">使用してサポート 要求を作成します</a>。</span><span class="sxs-lookup"><span data-stu-id="78a7e-141">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="78a7e-142">Microsoft 365 管理センターで請求プロファイルに関する質問やヘルプが必要な場合は、ビジネス [製品のサポートにお問い合わせください](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="78a7e-142">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](../../business-video/get-help-support.md).</span></span>
