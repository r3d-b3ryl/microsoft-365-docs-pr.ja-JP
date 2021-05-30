---
title: アイテム保持ポリシーとアイテム保持ラベルの制限
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: アイテム保持ポリシーおよび保持ラベル ポリシーのポリシーおよびポリシーごとの項目の最大数を把握する
ms.openlocfilehash: 1ee2d07a42aaf4dff45ae22e9dfc005b3c4593d9
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698966"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="6fbbf-103">アイテム保持ポリシーとアイテム保持ラベルの制限</span><span class="sxs-lookup"><span data-stu-id="6fbbf-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="6fbbf-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="6fbbf-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="6fbbf-105">[アイテム保持ポリシーと保持ラベル ポリシー](retention.md#retention-policies-and-retention-labels)を使用して、組織のデータを自動的に保持または削除する場合、注意すべき最大数がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="6fbbf-106">テナントごとのポリシーの最大数</span><span class="sxs-lookup"><span data-stu-id="6fbbf-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="6fbbf-107">1 つのテナントに最大 10,000 のポリシー (任意の構成) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="6fbbf-108">この最大値はデータ保持のため複数の異なるポリシーを包含します。またコンプライアンスのための他のポリシー、例えばDLP、情報バリア、電子情報開示、機密度ラベル等も同様です。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="6fbbf-109">この ポリシー 10,000個の制限内では、ワークロード毎のデータ保持ポリシーの最大数にもいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="6fbbf-110">Exchange Online (任意の構成): 1,800</span><span class="sxs-lookup"><span data-stu-id="6fbbf-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="6fbbf-111">SharePoint または OneDrive: (自動的に含まれるすべてのサイト): 13</span><span class="sxs-lookup"><span data-stu-id="6fbbf-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="6fbbf-112">SharePoint または OneDrive (含まれるまたは除外される特定の場所): 2,600</span><span class="sxs-lookup"><span data-stu-id="6fbbf-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="6fbbf-113">Microsoft Teams と Yammer のデータ保持ポリシーでは、データ保持目的でメールボックスを使用しますが、Exchange Online のポリシーの最大数は、Teams と Yammer のデータ保持ポリシーを含みません。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="6fbbf-114">ポリシーごとのアイテムの最大数</span><span class="sxs-lookup"><span data-stu-id="6fbbf-114">Maximum number of items per policy</span></span>

<span data-ttu-id="6fbbf-115">省略可能な構成を使用して、特定のユーザー、特定の Microsoft 365 グループ、特定のサイトに保持設定を適用する場合に、ポリシーごとに注意すべき制限事項がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="6fbbf-116">保持するポリシーごとのアイテムの最大数:</span><span class="sxs-lookup"><span data-stu-id="6fbbf-116">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="6fbbf-117">1,000 メールボックス (ユーザー メールボックスまたはグループ メールボックス)</span><span class="sxs-lookup"><span data-stu-id="6fbbf-117">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="6fbbf-118">1,000 個の Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="6fbbf-118">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="6fbbf-119">Teams のプライベート チャットのユーザー 1,000 人</span><span class="sxs-lookup"><span data-stu-id="6fbbf-119">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="6fbbf-120">100 個のサイト (OneDrive または SharePoint)</span><span class="sxs-lookup"><span data-stu-id="6fbbf-120">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="6fbbf-121">ポリシーごとにこれらの制限があるので、これらの数を超える結果となる特定の対象または除外を使用する必要がある場合は、同じ保持設定を持つ追加の保持ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-121">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="6fbbf-122">このために複数の保持ポリシーを使用するいくつかの[シナリオ例とソリューション](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-122">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="6fbbf-123">ただし、複数の保持ポリシーを所有すると管理費が高くなるので、本当に対象や除外が必要かどうかを常に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-123">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="6fbbf-124">場所全体に適用される既定値の構成には制限がなく、この構成の選択は、複数のポリシーを作成して維持するよりも良い解決策になるかもしれないことに留意してください。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-124">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="6fbbf-125">このシナリオで複数のポリシーを作成して維持する必要がある場合は、[PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) を使用してより効率的な構成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-125">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="6fbbf-126">最大数を超えないようにするために複数のポリシーを使用する例</span><span class="sxs-lookup"><span data-stu-id="6fbbf-126">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="6fbbf-127">以下の例では、保持ポリシーの場所だけを指定できず、前のセクションで説明した最大数を考慮しなければならない場合の設計ソリューションをいくつか提供しています。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-127">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="6fbbf-128">交換例は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-128">Exchange example:</span></span>

- <span data-ttu-id="6fbbf-129">**要件**: 40,000 以上のユーザー メールボックスがある組織では、ほとんどのユーザーは 7 年間メールを保持する必要がありますが、特定のユーザーのサブセット (425) は 5 年間だけメールを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-129">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="6fbbf-130">**ソリューション**: Exchange メールの保持期間が 7 年のアイテム保持ポリシーを 1 つ作成し、ユーザーのサブセットを除外します。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-130">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="6fbbf-131">次に、Exchange メールの第 2 のアイテム保持ポリシーを作成し、保持期間を 5 年として、ユーザーのサブセットを含めます。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-131">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="6fbbf-132">どちらの場合も、対象となる数と除外される数が 1 つのポリシーの指定メールボックスの最大数を下回っており、ユーザーのサブセットは、第二のポリシーよりも[保持期間](retention.md#the-principles-of-retention-or-what-takes-precedence)が長いため、最初のポリシーから明示的に除外されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-132">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="6fbbf-133">ユーザーのサブセットが保存期間のより長いアイテム保持ポリシーを必要とする場合は、最初のポリシーから除外する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-133">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="6fbbf-134">このソリューションでは、新規に組織に加入したユーザーがいる場合は、そのユーザーのメールボックスは自動的に 7 年間最初のポリシーに含まれ、サポートされている最大数に影響はありません。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-134">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="6fbbf-135">しかし、5 年間の保持期間を必要とする新規ユーザーは、対象数と除外数に追加され、この制限は最大 1,000 です。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-135">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="6fbbf-136">SharePoint の例は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-136">SharePoint example:</span></span>

- <span data-ttu-id="6fbbf-137">**要件**: ある組織では、数千の SharePoint サイトがありますが、10 年の保持期間が必要なのは 2,000 サイトのみで、8,000 サイトでは 4 年の保持期間が必要です。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-137">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="6fbbf-138">**ソリューション**: 特定の 100 サイトを含む保持期間 10 年の SharePoint 用アイテム保持ポリシーを 20 個作成し、特定の 100 サイトを含む保持期間 4 年の SharePoint 用アイテム保持ポリシーを 80 個作成します。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-138">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="6fbbf-139">すべての SharePoint サイトを保持する必要はなく、特定のサイトを指定したアイテム保持ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-139">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="6fbbf-140">アイテム保持ポリシーは指定した 100 サイト以上には対応していないため、2 つの保持期間に対応したポリシーを複数作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-140">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="6fbbf-141">これらのアイテム保持ポリシーには、含まれるサイトの最大数が含まれているため、次に保持が必要な新しいサイトは、保持期間に関係なく、新しいアイテム保持ポリシーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="6fbbf-141">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>