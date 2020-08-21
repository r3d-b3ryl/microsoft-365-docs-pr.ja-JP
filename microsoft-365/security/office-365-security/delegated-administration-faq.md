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
description: このトピックでは、委任された Microsoft 365 管理タスクを実行する Microsoft パートナーとリセラーに関する FAQ と回答について説明します。
ms.openlocfilehash: 01781437bbc7e8fe5c035ea23e4392e734e0231f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827089"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="b4bbc-103">代理管理の FAQ</span><span class="sxs-lookup"><span data-stu-id="b4bbc-103">Delegated administration FAQ</span></span>

<span data-ttu-id="b4bbc-104">このトピックでは、代理管理タスクを実行する必要がある Microsoft パートナーとリセラーに関してよく寄せられる質問と回答について説明します。これには、他のテナント (企業) で Exchange Online Protection (EOP) を管理する機能も含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a><span data-ttu-id="b4bbc-105">再販業者で、お客様のテナントを管理する必要があります。この処理のしくみ</span><span class="sxs-lookup"><span data-stu-id="b4bbc-105">I'm a reseller and I need to manage my customer's tenants; how does this work?</span></span>

<span data-ttu-id="b4bbc-106">Microsoft パートナーまたは販売店で、Microsoft アドバイザーへのサインアップが完了している場合、管理センター内でカスタルトのテナントを管理するアクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-106">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="b4bbc-107">これを代理管理といいます。組織内の管理者と同じ場合のように Microsoft 365 テナント (EOP 設定を含む) を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-107">This is known as delegated administration, and it allows you to manage their Microsoft 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="b4bbc-108">代理管理を実行するための手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-108">The steps for performing delegated administration are as follows:</span></span>

1. <span data-ttu-id="b4bbc-109">[Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-109">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="b4bbc-110">代理管理用にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-110">Sign up for delegated administration.</span></span> <span data-ttu-id="b4bbc-111">カスタマーのアカウント管理を開始する前に、顧客が代理管理者として承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-111">Before you can start administering a customer's account, they must authorize you as a delegated administrator.</span></span> <span data-ttu-id="b4bbc-112">承認を入手するには、最初に代 [理管理のオファーを送信します](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-112">To obtain their approval, you first [send them an offer for delegated administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> <span data-ttu-id="b4bbc-113">(後でカスタマーに委任管理を提供することもできます)。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-113">(You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="b4bbc-114">サブスクリプション アドバイザー パートナーの追加、 [変更、または削除を行う手順を使用して、代理管理者アカウントを作成します](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-114">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).</span></span>

<span data-ttu-id="b4bbc-115">アクセスを [許可する: 代理管理のセットアップ方法について詳しくは](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) 、ビジネスを構築してパートナーサブスクリプションを管理する。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-115">Visit [Partners: Build your business and administer partner subscription](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up delegated administration.</span></span>

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a><span data-ttu-id="b4bbc-116">再販業者ででない顧客です。どのようにすれば、自分のサブ テナントの代理管理者をセットアップできますか?</span><span class="sxs-lookup"><span data-stu-id="b4bbc-116">I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?</span></span>

<span data-ttu-id="b4bbc-117">現時点で、代理管理が行えるのはリセラーとパートナーのみです。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-117">Delegated administration is only available for resellers and partners at this time.</span></span> <span data-ttu-id="b4bbc-118">しかし、サブ テナント (企業) に適用するのに役立つ Windows PowerShell のサンプル スクリプトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-118">However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies).</span></span> <span data-ttu-id="b4bbc-119">詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-119">For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a><span data-ttu-id="b4bbc-120">サブ テナント管理者がわたしのポリシーを変更できないようにすることができますか？</span><span class="sxs-lookup"><span data-stu-id="b4bbc-120">Can I prevent my sub-tenant admin from modifying my policy?</span></span>

<span data-ttu-id="b4bbc-121">現在、Microsoft 365 にはその機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-121">Microsoft 365 does not currently have this capability.</span></span>

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a><span data-ttu-id="b4bbc-122">自分のすべてのサブ テナントを統合したレポートを取得できますか？</span><span class="sxs-lookup"><span data-stu-id="b4bbc-122">Can I get consolidated reporting across all of my sub-tenants?</span></span>

<span data-ttu-id="b4bbc-123">現時点では、Microsoft 365 管理センターのレポートで、管理する企業を統合したレポートを利用できません。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-123">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="b4bbc-124">ただし、これは Microsoft Graph を使用して [実行できます](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="b4bbc-124">However, you can do this by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
