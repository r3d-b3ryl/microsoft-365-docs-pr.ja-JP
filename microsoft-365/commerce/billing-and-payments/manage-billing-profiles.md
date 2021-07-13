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
- AdminTemplateSet
search.appverid: MET150
description: 請求プロファイルが請求書をサポートする方法について学習します。
ms.date: 04/02/2021
ms.openlocfilehash: ecea09a9ceea12fa92b92eac3e5a7595b2510042
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394631"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="4cd0e-103">課金プロファイルを理解する</span><span class="sxs-lookup"><span data-stu-id="4cd0e-103">Understand billing profiles</span></span>

<span data-ttu-id="4cd0e-104">請求プロファイルには、支払い方法、請求先情報、その他の請求書設定 (発注書番号、電子メール請求書の設定など) が含まれる。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="4cd0e-105">請求プロファイルを使用して、Microsoft から購入した製品の支払いを行います。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="4cd0e-106">課金プロファイルは、ユーザーがセルフサービス購入を行う際に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="4cd0e-107">各請求プロファイルは個別に請求されます。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="4cd0e-108">請求プロファイルは、製品とサービスを購入する顧客は、Microsoft.com の [サービスの購入] ページではMicrosoft 365 管理センター。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="4cd0e-109">課金プロファイルの役割とは</span><span class="sxs-lookup"><span data-stu-id="4cd0e-109">What are billing profile roles?</span></span>

<span data-ttu-id="4cd0e-110">課金プロファイルのロールには、購入を制御し、請求書を表示および管理するためのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="4cd0e-111">これらの役割を、請求書の追跡、整理、支払いを行うユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="4cd0e-112">たとえば、組織内の調達チームのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="4cd0e-113">Role</span><span class="sxs-lookup"><span data-stu-id="4cd0e-113">Role</span></span>                         | <span data-ttu-id="4cd0e-114">説明</span><span class="sxs-lookup"><span data-stu-id="4cd0e-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="4cd0e-115">課金プロファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="4cd0e-115">Billing profile owner</span></span>        | <span data-ttu-id="4cd0e-116">課金プロファイルに関するすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="4cd0e-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="4cd0e-117">課金プロファイル投稿者</span><span class="sxs-lookup"><span data-stu-id="4cd0e-117">Billing profile contributor</span></span>  | <span data-ttu-id="4cd0e-118">課金プロファイルのアクセス許可を除くすべてを管理する</span><span class="sxs-lookup"><span data-stu-id="4cd0e-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="4cd0e-119">課金プロファイル リーダー</span><span class="sxs-lookup"><span data-stu-id="4cd0e-119">Billing profile reader</span></span>       | <span data-ttu-id="4cd0e-120">課金プロファイル内のすべてのデータの読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="4cd0e-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="4cd0e-121">請求書マネージャー</span><span class="sxs-lookup"><span data-stu-id="4cd0e-121">Invoice manager</span></span>              | <span data-ttu-id="4cd0e-122">請求書の表示と支払い、および請求プロファイル内のすべての情報の読み取り専用ビュー</span><span class="sxs-lookup"><span data-stu-id="4cd0e-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="4cd0e-123">請求プロファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="4cd0e-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="4cd0e-124">これらの手順に従い、請求プロファイルの一覧が空の場合は、請求プロファイルを持たなかったり、この機能を使用できないという意味です。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="4cd0e-125">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="4cd0e-126">[請求プロファイル **] タブを** 選択し、一覧から請求プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="4cd0e-127">各請求プロファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="4cd0e-128">**課金プロファイルの名前と状態** &ndash; 請求プロファイルの一意の名前と、課金プロファイルが購入に対してアクティブか無効かを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="4cd0e-129">**請求書の設定** &ndash; 請求先アカウントの国に基づく通貨、請求書の頻度と日付に関する情報、電子メールの添付ファイルとして請求書を受信するオプション、およびオプションの PO 番号フィールド</span><span class="sxs-lookup"><span data-stu-id="4cd0e-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="4cd0e-130">**支払い方法** &ndash; プロファイルのプライマリ支払い方法とバックアップ支払い方法がある場合は、その支払い方法を表示します。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="4cd0e-131">**課金アカウント** &ndash; プロファイルが関連付けされている請求先アカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="4cd0e-132">課金アカウントの詳細については、「請求アカウントについて [」を参照してください](../manage-billing-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="4cd0e-133">**連絡先情報** &ndash; 請求先住所と連絡先名と電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="4cd0e-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="4cd0e-134">**課金プロファイルの役割** &ndash; そのプロファイルの処理を行う請求プロファイル の役割の 1 つが割り当てられているユーザーの一覧。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="4cd0e-135">たとえば、請求書の支払い、PO 番号の追加、または購入に使用される支払い方法の置換を行います。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="4cd0e-136">請求プロファイルの役割は、組織内のユーザーにのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="4cd0e-137">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="4cd0e-137">Need help?</span></span> <span data-ttu-id="4cd0e-138">サポートにお問い合せください</span><span class="sxs-lookup"><span data-stu-id="4cd0e-138">Contact support</span></span>

<span data-ttu-id="4cd0e-139">Azure の料金に関する質問やサポートが必要な場合は、Azure サポートを <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">使用してサポート 要求を作成します</a>。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="4cd0e-140">請求プロファイルに関する質問やサポートが必要な場合はMicrosoft 365 管理センター[サポートにお問い合わせください](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0e-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="4cd0e-141">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4cd0e-141">Related content</span></span>

<span data-ttu-id="4cd0e-142">[課金プロファイルを使用してサブスクリプションの支払い](pay-for-subscription-billing-profile.md) 方法 (記事)</span><span class="sxs-lookup"><span data-stu-id="4cd0e-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="4cd0e-143">[請求先アカウント](../manage-billing-accounts.md) について (記事)</span><span class="sxs-lookup"><span data-stu-id="4cd0e-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="4cd0e-144">[支払い方法の管理](manage-payment-methods.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4cd0e-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
