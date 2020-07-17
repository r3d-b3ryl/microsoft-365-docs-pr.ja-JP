---
title: 課金プロフィールを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 請求プロファイルが請求書をサポートする方法について説明します。
keywords: 課金プロファイル、請求書、料金、管理された費用
ms.openlocfilehash: 2979909e3b916cc4bc8704f32a821b13fa6090e0
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741714"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="4a33f-104">課金プロフィールを管理する</span><span class="sxs-lookup"><span data-stu-id="4a33f-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4a33f-105">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="4a33f-105">The admin center is changing.</span></span> <span data-ttu-id="4a33f-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a33f-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4a33f-107">Microsoft の製品やサービスを購入している商用のお客様の場合、課金プロファイルを使用して、請求書に含めるアイテムをカスタマイズしたり、請求書に支払いを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="4a33f-108">請求プロファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="4a33f-109">**課金アカウント** &ndash;プロファイルが関連付けられている請求先アカウントの名前</span><span class="sxs-lookup"><span data-stu-id="4a33f-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="4a33f-110">**支払い方法** &ndash;クレジットカードまたはデビットカード、銀行口座、小切手、または電信振替</span><span class="sxs-lookup"><span data-stu-id="4a33f-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="4a33f-111">**連絡先情報** &ndash;請求先住所と連絡先の名前</span><span class="sxs-lookup"><span data-stu-id="4a33f-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="4a33f-112">**請求書の設定** &ndash;請求先アカウントの国に基づく通貨、オプションの PO 番号、および請求書を電子メールの添付ファイルとして受信するオプション</span><span class="sxs-lookup"><span data-stu-id="4a33f-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="4a33f-113">**アクセス許可** &ndash;請求プロファイルの変更、支払いを行う、請求書の支払い方法を使用して購入できるようにする権限</span><span class="sxs-lookup"><span data-stu-id="4a33f-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="4a33f-114">請求プロファイルを使用して、購入を制御し、請求書をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="4a33f-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="4a33f-115">月次請求書は、請求プロファイルを購入した製品に対して生成されます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="4a33f-116">請求書は、[発注書番号] および [電子メールの請求書の設定を更新する] のようにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="4a33f-117">最初の購入時に、課金プロファイルが自動的に請求アカウントに作成されます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="4a33f-118">[<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">課金プロファイル</a>] ページで請求プロファイルを作成し、さらに請求書を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="4a33f-119">たとえば、組織内の部署ごとに購入するときに、さまざまな課金プロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="4a33f-120">次の請求日に、請求プロファイルごとに請求書を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4a33f-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="4a33f-121">課金プロファイルの役割</span><span class="sxs-lookup"><span data-stu-id="4a33f-121">Billing profile roles</span></span>

<span data-ttu-id="4a33f-122">請求プロファイルの役割には、購入を制御し、請求書を表示および管理するためのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="4a33f-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="4a33f-123">これらの役割は、組織内の調達チームのメンバーと同様に、請求書を追跡、整理、および支払いするユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="4a33f-124">Role</span><span class="sxs-lookup"><span data-stu-id="4a33f-124">Role</span></span>                          | <span data-ttu-id="4a33f-125">説明</span><span class="sxs-lookup"><span data-stu-id="4a33f-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="4a33f-126">課金プロファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="4a33f-126">Billing profile owner</span></span>         | <span data-ttu-id="4a33f-127">課金プロファイルのすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="4a33f-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="4a33f-128">課金プロファイル共同作成者</span><span class="sxs-lookup"><span data-stu-id="4a33f-128">Billing profile contributor</span></span>   | <span data-ttu-id="4a33f-129">課金プロファイルのアクセス許可以外のすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="4a33f-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="4a33f-130">課金プロファイルリーダー</span><span class="sxs-lookup"><span data-stu-id="4a33f-130">Billing profile reader</span></span>        | <span data-ttu-id="4a33f-131">請求プロファイル内のすべての読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="4a33f-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="4a33f-132">請求書マネージャー</span><span class="sxs-lookup"><span data-stu-id="4a33f-132">Invoice manager</span></span>               | <span data-ttu-id="4a33f-133">課金プロファイルに含まれるすべての情報を読み取り専用で表示および支払する</span><span class="sxs-lookup"><span data-stu-id="4a33f-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="4a33f-134">課金プロファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="4a33f-134">View billing profiles</span></span>

1. <span data-ttu-id="4a33f-135">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4a33f-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="4a33f-136">[**課金プロファイル**] を選択し、リストから請求プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4a33f-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="4a33f-137">[**概要**] タブでは、請求プロファイルの詳細を編集したり、請求書を電子メールで送信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="4a33f-138">[**権限**] タブでは、請求書を支払いするためにユーザーに役割を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="4a33f-139">[ **Azure クレジットバランス**] タブでは、azure のお客様は、その請求書プロファイルで使用されている azure クレジットのトランザクションバランス履歴を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="4a33f-140">[ **Azure クレジット**] タブでは、azure のお客様は、その請求プロファイルに関連付けられている azure クレジットの一覧と有効期限日を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a33f-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4a33f-141">Azure クレジットをお持ちでない場合、[ **azure クレジットバランス**] タブまたは [ **azure**クレジット] タブは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4a33f-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="4a33f-142">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="4a33f-142">Need help?</span></span> <span data-ttu-id="4a33f-143">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4a33f-143">Contact support.</span></span>

<span data-ttu-id="4a33f-144">ご質問がある場合や Azure の料金についてサポートが必要な場合は、 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">azure サポートを使用してサポート要求を作成して</a>ください。</span><span class="sxs-lookup"><span data-stu-id="4a33f-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="4a33f-145">ご質問がある場合や、Microsoft 365 管理センターの課金プロファイルについてのヘルプが必要な場合は、[ビジネス製品のサポートにお問い合わせください](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="4a33f-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
