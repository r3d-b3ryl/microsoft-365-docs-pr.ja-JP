---
title: 課金プロファイルを管理する
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
ms.custom: ''
search.appverid:
- MET150
description: 請求プロファイルが請求書をサポートする方法について説明します。
keywords: 課金プロファイル、請求書、料金、管理された費用
ms.openlocfilehash: 4b46709cf877ea8689f72b66d5ac357272e4737d
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753546"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="9be77-104">課金プロファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="9be77-104">Manage billing profiles</span></span>
<span data-ttu-id="9be77-105">Microsoft の製品やサービスを購入している商用のお客様の場合、課金プロファイルを使用して、請求書に含めるアイテムをカスタマイズしたり、請求書に支払いを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9be77-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="9be77-106">請求プロファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9be77-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="9be77-107">**課金アカウント** &ndash;プロファイルが関連付けられている請求先アカウントの名前</span><span class="sxs-lookup"><span data-stu-id="9be77-107">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="9be77-108">**支払い方法** &ndash;貸方またはデビットカード、銀行口座、小切手、または電信送金</span><span class="sxs-lookup"><span data-stu-id="9be77-108">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="9be77-109">**連絡先情報** &ndash;請求先の住所と連絡先の名前</span><span class="sxs-lookup"><span data-stu-id="9be77-109">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="9be77-110">**請求書の設定** &ndash;金額請求先アカウントの国に基づく通貨、オプションの PO 番号、および請求書を電子メールの添付ファイルとして受信するオプション</span><span class="sxs-lookup"><span data-stu-id="9be77-110">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="9be77-111">課金プロファイルの変更、支払い、請求プロファイルの支払い方法を使用して購入を行うことができる**アクセス** &ndash;許可のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9be77-111">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="9be77-112">請求プロファイルを使用して、購入を制御し、請求書をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="9be77-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="9be77-113">月次請求書は、請求プロファイルを購入した製品に対して生成されます。</span><span class="sxs-lookup"><span data-stu-id="9be77-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="9be77-114">請求書は、[発注書番号] および [電子メールの請求書の設定を更新する] のようにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9be77-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="9be77-115">最初の購入時に、課金プロファイルが自動的に請求アカウントに作成されます。</span><span class="sxs-lookup"><span data-stu-id="9be77-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="9be77-116">[<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">課金プロファイル</a>] ページで請求プロファイルを作成し、さらに請求書を設定できます。</span><span class="sxs-lookup"><span data-stu-id="9be77-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="9be77-117">たとえば、組織内の部署ごとに購入するときに、さまざまな課金プロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9be77-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="9be77-118">次の請求日に、請求プロファイルごとに請求書を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9be77-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="9be77-119">課金プロファイルの役割</span><span class="sxs-lookup"><span data-stu-id="9be77-119">Billing profile roles</span></span>

<span data-ttu-id="9be77-120">請求プロファイルの役割には、購入を制御し、請求書を表示および管理するためのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="9be77-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="9be77-121">これらの役割は、組織内の調達チームのメンバーと同様に、請求書を追跡、整理、および支払いするユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9be77-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="9be77-122">Role</span><span class="sxs-lookup"><span data-stu-id="9be77-122">Role</span></span>                          | <span data-ttu-id="9be77-123">説明</span><span class="sxs-lookup"><span data-stu-id="9be77-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="9be77-124">課金プロファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="9be77-124">Billing profile owner</span></span>         | <span data-ttu-id="9be77-125">課金プロファイルのすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="9be77-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="9be77-126">課金プロファイル共同作成者</span><span class="sxs-lookup"><span data-stu-id="9be77-126">Billing profile contributor</span></span>   | <span data-ttu-id="9be77-127">課金プロファイルのアクセス許可以外のすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="9be77-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="9be77-128">課金プロファイルリーダー</span><span class="sxs-lookup"><span data-stu-id="9be77-128">Billing profile reader</span></span>        | <span data-ttu-id="9be77-129">請求プロファイル内のすべての読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="9be77-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="9be77-130">請求書マネージャー</span><span class="sxs-lookup"><span data-stu-id="9be77-130">Invoice manager</span></span>               | <span data-ttu-id="9be77-131">課金プロファイルに含まれるすべての情報を読み取り専用で表示および支払する</span><span class="sxs-lookup"><span data-stu-id="9be77-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="9be77-132">課金プロファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="9be77-132">View billing profiles</span></span>

1. <span data-ttu-id="9be77-133">管理センターで、[**課金請求書** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">& の支払い</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9be77-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="9be77-134">[**課金プロファイル**] を選択し、リストから請求プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9be77-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="9be77-135">[**概要**] タブでは、請求プロファイルの詳細を編集したり、請求書を電子メールで送信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9be77-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="9be77-136">[**権限**] タブでは、請求書を支払いするためにユーザーに役割を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9be77-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="9be77-137">[ **Azure クレジットバランス**] タブでは、azure のお客様は、その請求書プロファイルで使用されている azure クレジットのトランザクションバランス履歴を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9be77-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="9be77-138">[ **Azure クレジット**] タブでは、azure のお客様は、その請求プロファイルに関連付けられている azure クレジットの一覧と有効期限日を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9be77-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9be77-139">Azure クレジットをお持ちでない場合、[ **azure クレジットバランス**] タブまたは [ **azure**クレジット] タブは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9be77-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="9be77-140">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="9be77-140">Need help?</span></span> <span data-ttu-id="9be77-141">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="9be77-141">Contact support.</span></span>

<span data-ttu-id="9be77-142">ご質問がある場合や Azure の料金についてサポートが必要な場合は、 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">azure サポートを使用してサポート要求を作成して</a>ください。</span><span class="sxs-lookup"><span data-stu-id="9be77-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="9be77-143">ご質問がある場合や、Microsoft 365 管理センターの課金プロファイルについてのヘルプが必要な場合は、[ビジネス製品のサポートにお問い合わせください](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="9be77-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>