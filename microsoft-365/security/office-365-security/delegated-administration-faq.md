---
title: 代理管理の FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 管理者は、microsoft のパートナーと販売店のための Microsoft 365 で、委任された管理タスクについてよく寄せられる質問と回答を確認できます。
ms.openlocfilehash: 3efadc8793778bfabe10922e8e29044747d60ad0
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866697"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="16a89-103">代理管理の FAQ</span><span class="sxs-lookup"><span data-stu-id="16a89-103">Delegated administration FAQ</span></span>

<span data-ttu-id="16a89-104">この記事では、microsoft パートナーおよび販売店で、Microsoft 365 での代理管理タスクについてよく寄せられる質問とその回答について説明します。</span><span class="sxs-lookup"><span data-stu-id="16a89-104">This article provides frequently asked questions and answers about delegated administration tasks in Microsoft 365 for Microsoft partners and resellers.</span></span> <span data-ttu-id="16a89-105">代理管理には、他のテナント (企業) の Exchange Online Protection (EOP) 設定を管理する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="16a89-105">Delegated administration includes the ability to manage Exchange Online Protection (EOP) settings for other tenants (companies).</span></span>

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a><span data-ttu-id="16a89-106">リセラーで、お客様のテナントを管理する必要がある。</span><span class="sxs-lookup"><span data-stu-id="16a89-106">I'm a reseller and I need to manage my customer tenants.</span></span> <span data-ttu-id="16a89-107">これはどのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="16a89-107">How does this work?</span></span>

<span data-ttu-id="16a89-108">Microsoft のパートナーまたは販売店の場合は、Microsoft advisor にサインアップすると、お客様の Microsoft 365 組織に委任された _管理_ 機能を要求できます。</span><span class="sxs-lookup"><span data-stu-id="16a89-108">If you're a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request _delegated administration_ capabilities in your customer's Microsoft 365 organization.</span></span>

<span data-ttu-id="16a89-109">委任された管理では、組織内の管理者であるかのように、Microsoft 365 (EOP の設定を含む) を管理できます。</span><span class="sxs-lookup"><span data-stu-id="16a89-109">Delegated administration allows you to manage Microsoft 365  (including EOP settings) as if you were an admin within that organization.</span></span> <span data-ttu-id="16a89-110">委任された管理を構成する手順については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="16a89-110">The steps to configure delegated administration are described in the following list:</span></span>

1. <span data-ttu-id="16a89-111">[Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。</span><span class="sxs-lookup"><span data-stu-id="16a89-111">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="16a89-112">委任された管理にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="16a89-112">Sign up for delegated administration.</span></span> <span data-ttu-id="16a89-113">お客様のテナントの管理を開始する前に、代理管理者として承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16a89-113">Before you can start administering a customer's tenant, they must authorize you as a delegated administrator.</span></span> <span data-ttu-id="16a89-114">承認を得るには、まず [委任管理の申し出を送信](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)します。</span><span class="sxs-lookup"><span data-stu-id="16a89-114">To obtain their approval, you first [send them an offer for delegated administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> <span data-ttu-id="16a89-115">また、後でお客様に委任された管理を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="16a89-115">You can also offer delegated administration to your customer at a later time.</span></span>

3. <span data-ttu-id="16a89-116">「 [サブスクリプションアドバイザーパートナーを追加、変更、または削除する](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)」の手順に従って、委任された管理者アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="16a89-116">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).</span></span>

<span data-ttu-id="16a89-117">代理管理を設定する方法の詳細については [、「パートナー: ビジネスを構築し、パートナーサブスクリプションを管理](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16a89-117">Visit [Partners: Build your business and administer partner subscription](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up delegated administration.</span></span>

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a><span data-ttu-id="16a89-118">お客様は、販売店ではありません。</span><span class="sxs-lookup"><span data-stu-id="16a89-118">I'm a customer, not a reseller.</span></span> <span data-ttu-id="16a89-119">委任された管理者を自分のサブテナントに設定するには、どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="16a89-119">How can set up delegated administrator for my subtenants?</span></span>

<span data-ttu-id="16a89-120">委任された管理は、リセラーとパートナーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="16a89-120">Delegated administration is only available for resellers and partners.</span></span> <span data-ttu-id="16a89-121">ただし、サンプルの PowerShell スクリプトを使用すると、サブテナント (企業) にポリシーを適用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="16a89-121">However, there's a sample PowerShell script that will help you apply policies to your subtenants (companies).</span></span> <span data-ttu-id="16a89-122">詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16a89-122">For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a><span data-ttu-id="16a89-123">自分のサブテナント管理者が自分のポリシーを変更できないようにすることはできますか。</span><span class="sxs-lookup"><span data-stu-id="16a89-123">Can I prevent my subtenant admin from modifying my policy?</span></span>

<span data-ttu-id="16a89-124">いいえ。</span><span class="sxs-lookup"><span data-stu-id="16a89-124">No.</span></span> <span data-ttu-id="16a89-125">現在、Microsoft 365 にはこの機能はありません。</span><span class="sxs-lookup"><span data-stu-id="16a89-125">Microsoft 365 does not currently have this capability.</span></span>

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a><span data-ttu-id="16a89-126">すべてのサブテナントでレポートを統合することはできますか?</span><span class="sxs-lookup"><span data-stu-id="16a89-126">Can I get consolidated reporting across all of my subtenants?</span></span>

<span data-ttu-id="16a89-127">Microsoft 365 管理センターのレポートでは、管理している会社を超えた統合レポートを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="16a89-127">Consolidated reporting across the companies you manage isn't available in Microsoft 365 admin center reports.</span></span> <span data-ttu-id="16a89-128">ただし、 [Microsoft Graph](https://docs.microsoft.com/graph/overview)を使用してレポートを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="16a89-128">However, you can get reports by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
