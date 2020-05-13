---
title: 代理管理の FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: このトピックでは、委任された Microsoft 365 の管理タスクを実行する Microsoft パートナーとリセラーに関する Faq と回答を示します。
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209525"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="478f2-103">代理管理の FAQ</span><span class="sxs-lookup"><span data-stu-id="478f2-103">Delegated administration FAQ</span></span>

<span data-ttu-id="478f2-104">このトピックでは、他のテナント (企業) の Exchange Online Protection (EOP) を管理する機能など、委任された管理タスクを実行することを望む Microsoft パートナーとリセラーによく寄せられる質問とその回答を示します。</span><span class="sxs-lookup"><span data-stu-id="478f2-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a><span data-ttu-id="478f2-105">リセラーで、お客様のテナントを管理する必要がある。これはどのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="478f2-105">I'm a reseller and I need to manage my customer's tenants; how does this work?</span></span>

<span data-ttu-id="478f2-106">Microsoft のパートナーまたは販売店で、Microsoft advisor にサインアップする場合は、管理センター内でテナントを管理するためのアクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="478f2-106">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="478f2-107">これは委任された管理と呼ばれ、組織内の管理者であるかのように、Microsoft 365 テナント (EOP 設定を含む) を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="478f2-107">This is known as delegated administration, and it allows you to manage their Microsoft 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="478f2-108">委任された管理を実行する手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="478f2-108">The steps for performing delegated administration are as follows:</span></span>

1. <span data-ttu-id="478f2-109">[Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。</span><span class="sxs-lookup"><span data-stu-id="478f2-109">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="478f2-110">委任された管理にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="478f2-110">Sign up for delegated administration.</span></span> <span data-ttu-id="478f2-111">お客様のアカウントの管理を開始する前に、代理管理者として承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="478f2-111">Before you can start administering a customer's account, they must authorize you as a delegated administrator.</span></span> <span data-ttu-id="478f2-112">承認を得るには、まず[委任管理の申し出を送信](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)します。</span><span class="sxs-lookup"><span data-stu-id="478f2-112">To obtain their approval, you first [send them an offer for delegated administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> <span data-ttu-id="478f2-113">(お客様に後で委任された管理を提供することもできます)。</span><span class="sxs-lookup"><span data-stu-id="478f2-113">(You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="478f2-114">「[サブスクリプションアドバイザーパートナーを追加、変更、または削除する](https://docs.microsoft.com/office365/admin/misc/add-partner)」の手順に従って、委任された管理者アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="478f2-114">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/office365/admin/misc/add-partner).</span></span>

<span data-ttu-id="478f2-115">代理管理を設定する方法の詳細については[、「パートナー: ビジネスを構築し、パートナーサブスクリプションを管理](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="478f2-115">Visit [Partners: Build your business and administer partner subscription](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up delegated administration.</span></span>

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a><span data-ttu-id="478f2-116">お客様は、リセラーではなく、サブテナントの代理管理者を設定する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="478f2-116">I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?</span></span>

<span data-ttu-id="478f2-117">現時点で、代理管理が行えるのはリセラーとパートナーのみです。</span><span class="sxs-lookup"><span data-stu-id="478f2-117">Delegated administration is only available for resellers and partners at this time.</span></span> <span data-ttu-id="478f2-118">しかし、サブ テナント (企業) に適用するのに役立つ Windows PowerShell のサンプル スクリプトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="478f2-118">However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies).</span></span> <span data-ttu-id="478f2-119">詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="478f2-119">For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a><span data-ttu-id="478f2-120">サブ テナント管理者がわたしのポリシーを変更できないようにすることができますか？</span><span class="sxs-lookup"><span data-stu-id="478f2-120">Can I prevent my sub-tenant admin from modifying my policy?</span></span>

<span data-ttu-id="478f2-121">現在、Microsoft 365 にはこの機能はありません。</span><span class="sxs-lookup"><span data-stu-id="478f2-121">Microsoft 365 does not currently have this capability.</span></span>

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a><span data-ttu-id="478f2-122">自分のすべてのサブ テナントを統合したレポートを取得できますか？</span><span class="sxs-lookup"><span data-stu-id="478f2-122">Can I get consolidated reporting across all of my sub-tenants?</span></span>

<span data-ttu-id="478f2-123">この時点では、管理している会社を超えた統合レポートを Microsoft 365 管理センターのレポートで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="478f2-123">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="478f2-124">ただし、これは[Microsoft Graph](https://docs.microsoft.com/graph/overview)を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="478f2-124">However, you can do this by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
