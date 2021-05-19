---
title: グループの作成時に使用するドメインMicrosoft 365する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: PowerShell を使用して電子メール アドレス ポリシーを構成して、Microsoft 365グループを作成するときに使用するドメインを選択する方法について説明します。
ms.openlocfilehash: a0142ea5f5aa088c4be79fc8699a616d9cdd9390
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538221"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="43a63-103">グループの作成時に使用するドメインMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="43a63-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="43a63-104">一部の組織では、独立した複数のメール ドメインを使用して、ビジネスのさまざまな部分をセグメント化しています。</span><span class="sxs-lookup"><span data-stu-id="43a63-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="43a63-105">ユーザーがグループを作成するときに使用するドメインMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="43a63-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="43a63-106">ユーザーが会社の既定の承認済みドメイン以外のドメインにグループを作成する必要がある場合、PowerShell を使ってメール アドレス ポリシー (EAP) を構成することでこれを許可できます。</span><span class="sxs-lookup"><span data-stu-id="43a63-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="43a63-107">PowerShell コマンドレットを実行する前に、組織に相談できるモジュールをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="43a63-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="43a63-108">詳細については、「[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43a63-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="43a63-109">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="43a63-109">Example scenarios</span></span>

<span data-ttu-id="43a63-110">たとえば、ビジネスのメイン ドメインが Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="43a63-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="43a63-111">ただし、組織の既定で受け入れられるドメインは service.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="43a63-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="43a63-112">つまり、グループはグループ (たとえば、service.contoso.com) に作成 jimsteam@service.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="43a63-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="43a63-113">たとえば、組織でサブドメインも構成済みだとします。</span><span class="sxs-lookup"><span data-stu-id="43a63-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="43a63-114">これらのドメインにグループを作成する場合も、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43a63-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="43a63-115">学生用の students.contoso.com</span><span class="sxs-lookup"><span data-stu-id="43a63-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="43a63-116">教職員メンバー用の faculty.contoso.com</span><span class="sxs-lookup"><span data-stu-id="43a63-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="43a63-117">次の 2 つのシナリオで、その実行方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43a63-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="43a63-118">複数の EAP がある場合、優先度の順に評価されます。</span><span class="sxs-lookup"><span data-stu-id="43a63-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="43a63-119">値 1 は、優先度が最も高い値を意味します。</span><span class="sxs-lookup"><span data-stu-id="43a63-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="43a63-120">EAP が一致すると、それ以上の EAP は評価され、グループにスタンプされるアドレスは、一致した EAP に基いて行います。</span><span class="sxs-lookup"><span data-stu-id="43a63-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="43a63-121">> 指定した条件に一致する EAP がない場合、グループは組織の既定の受け入れドメインにプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="43a63-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="43a63-122">承認された[ドメインを追加する](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)方法の詳細については、「Exchange Onlineで受け入れドメインを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43a63-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="43a63-123">シナリオ 1</span><span class="sxs-lookup"><span data-stu-id="43a63-123">Scenario 1</span></span>

<span data-ttu-id="43a63-124">次の使用例は、組織のすべてのグループMicrosoft 365ドメインでプロビジョニングする groups.contoso.com します。</span><span class="sxs-lookup"><span data-stu-id="43a63-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="43a63-125">シナリオ 2</span><span class="sxs-lookup"><span data-stu-id="43a63-125">Scenario 2</span></span>

<span data-ttu-id="43a63-126">たとえば、グループが作成されるサブドメインMicrosoft 365制御するとします。</span><span class="sxs-lookup"><span data-stu-id="43a63-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="43a63-127">あなたの希望です：</span><span class="sxs-lookup"><span data-stu-id="43a63-127">You want:</span></span>
  
- <span data-ttu-id="43a63-128">学生 (部門が [学生] に設定されている **ユーザー)** によって作成されたグループは、students.groups.contoso.com されます。</span><span class="sxs-lookup"><span data-stu-id="43a63-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="43a63-129">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="43a63-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="43a63-130">教員が作成したグループ ([部署] が [教職員] または [電子メール アドレス] に設定されているユーザー **には、faculty.contoso.com)** が faculty.groups.contoso.com されます。</span><span class="sxs-lookup"><span data-stu-id="43a63-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="43a63-131">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="43a63-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="43a63-132">他のユーザーが作成したグループは、ドメイン内 groups.contoso.com されます。</span><span class="sxs-lookup"><span data-stu-id="43a63-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="43a63-133">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="43a63-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="43a63-134">メール アドレス ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="43a63-134">Change email address policies</span></span>

<span data-ttu-id="43a63-135">既存の EAP の優先順位またはメール アドレス テンプレートを変更するには、Set-EmailAddressPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="43a63-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="43a63-136">EAP を変更しても、プロビジョニング済みのグループには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="43a63-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="43a63-137">メール アドレス ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="43a63-137">Delete email address policies</span></span>

<span data-ttu-id="43a63-138">EAP を削除するには、Remove-EmailAddressPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="43a63-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="43a63-139">EAP を変更しても、プロビジョニング済みのグループには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="43a63-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="43a63-140">ハイブリッド要件</span><span class="sxs-lookup"><span data-stu-id="43a63-140">Hybrid requirements</span></span>

<span data-ttu-id="43a63-141">組織がハイブリッド シナリオで構成されている場合は、「Microsoft 365 グループをオンプレミス[Exchange](/exchange/hybrid-deployment/set-up-microsoft-365-groups)ハイブリッドで構成する」を参照して、組織が Microsoft 365 グループを作成するための要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="43a63-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="43a63-142">電子メール アドレス ポリシー グループの使用に関する追加情報:</span><span class="sxs-lookup"><span data-stu-id="43a63-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="43a63-143">以下のいくつかの点を把握しておく必要あります。</span><span class="sxs-lookup"><span data-stu-id="43a63-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="43a63-144">グループ作成の速度は、組織に構成されている EAP の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="43a63-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="43a63-145">管理者とユーザーは、グループを作成するときにドメインを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="43a63-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="43a63-146">ユーザーのグループは、既に用意されている標準クエリ (ユーザーのプロパティ) を使用して決定されます。</span><span class="sxs-lookup"><span data-stu-id="43a63-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="43a63-147">サポートされている [フィルター可能なプロパティについては、-RecipientFilter パラメーターの Filterable](/powershell/exchange/recipientfilter-properties) プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43a63-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="43a63-148">グループに EAP を構成しないと、グループの作成で既定の承認済みドメインが選択されます。</span><span class="sxs-lookup"><span data-stu-id="43a63-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="43a63-149">承認済みドメインを削除する場合は、最初に、EAP を更新する必要があります。そうしないと、グループのプロビジョニングが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="43a63-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="43a63-150">1 つの組織につき最大で 100 のメール アドレス ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="43a63-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="43a63-151">関連記事</span><span class="sxs-lookup"><span data-stu-id="43a63-151">Related articles</span></span>

[<span data-ttu-id="43a63-152">コラボレーション ガバナンス計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="43a63-152">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="43a63-153">コラボレーション ガバナンス 計画の作成</span><span class="sxs-lookup"><span data-stu-id="43a63-153">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="43a63-154">管理センター Microsoft 365グループを作成する</span><span class="sxs-lookup"><span data-stu-id="43a63-154">Create an Microsoft 365 group in the admin center</span></span>](../admin/create-groups/create-groups.md)