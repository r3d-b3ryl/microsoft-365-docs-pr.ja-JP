---
title: Microsoft 365 グループを作成するときに使用するドメインを選択する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'PowerShell を使用して電子メールアドレスポリシーを構成することによって、Microsoft 365 グループを作成するときに使用するドメインを選択する方法について説明します。 '
ms.openlocfilehash: 19caa4f4dfdef4895fa58f8bf5c198269844044f
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597379"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="7f40c-103">Microsoft 365 グループを作成するときに使用するドメインを選択する</span><span class="sxs-lookup"><span data-stu-id="7f40c-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

 <span data-ttu-id="7f40c-104">一部の組織では、独立した複数のメール ドメインを使用して、ビジネスのさまざまな部分をセグメント化しています。</span><span class="sxs-lookup"><span data-stu-id="7f40c-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="7f40c-105">ユーザーが Microsoft 365 グループを作成するときに使用するドメインを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="7f40c-106">ユーザーが会社の既定の承認済みドメイン以外のドメインにグループを作成する必要がある場合、PowerShell を使ってメール アドレス ポリシー (EAP) を構成することでこれを許可できます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="7f40c-107">PowerShell コマンドレットを実行する前に、組織に説明できるモジュールをダウンロードしてインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="7f40c-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="7f40c-108">詳細については、「[リモート PowerShell による Exchange への接続](https://go.microsoft.com/fwlink/p/?LinkId=785881)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f40c-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="7f40c-109">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="7f40c-109">Example scenarios</span></span>

<span data-ttu-id="7f40c-110">ビジネスのメインドメインが Contoso.com であるとします。</span><span class="sxs-lookup"><span data-stu-id="7f40c-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="7f40c-111">しかし、組織の既定の承認済みドメインは service.contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="7f40c-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="7f40c-112">これは、グループが service.contoso.com に作成されることを意味します (たとえば、jimsteam@service.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="7f40c-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="7f40c-113">組織にサブドメインが構成されているとします。</span><span class="sxs-lookup"><span data-stu-id="7f40c-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="7f40c-114">これらのドメインにグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f40c-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="7f40c-115">学生用の students.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f40c-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="7f40c-116">教職員メンバー用の faculty.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f40c-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="7f40c-117">次の 2 つのシナリオで、その実行方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f40c-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f40c-118">複数の EAPs がある場合は、優先度の順に評価されます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="7f40c-119">値が1の場合は、最も高い優先度を表します。</span><span class="sxs-lookup"><span data-stu-id="7f40c-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="7f40c-120">EAP が一致すると、それ以降の EAP は評価されず、グループにスタンプされたアドレスは一致した EAP によって取得されます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="7f40c-121">> 指定された条件に一致する EAPs がない場合、グループは組織の既定の承認済みドメインでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="7f40c-122">承認済みドメインを追加する方法については、「 [Exchange Online で承認済みドメインを管理する」](https://go.microsoft.com/fwlink/p/?LinkId=785428)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f40c-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="7f40c-123">シナリオ 1</span><span class="sxs-lookup"><span data-stu-id="7f40c-123">Scenario 1</span></span>

<span data-ttu-id="7f40c-124">次の例は、groups.contoso.com ドメイン内の組織内のすべての Microsoft 365 グループをプロビジョニングする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f40c-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="7f40c-125">シナリオ 2</span><span class="sxs-lookup"><span data-stu-id="7f40c-125">Scenario 2</span></span>

<span data-ttu-id="7f40c-126">どのサブドメインの Microsoft 365 グループを作成するかを制御する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="7f40c-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="7f40c-127">あなたの希望です：</span><span class="sxs-lookup"><span data-stu-id="7f40c-127">You want:</span></span>
  
- <span data-ttu-id="7f40c-128">Students.groups.contoso.com ドメインで、学生 ( **Department**が**学生**に設定されているユーザー) によって作成されたグループ。</span><span class="sxs-lookup"><span data-stu-id="7f40c-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="7f40c-129">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f40c-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="7f40c-130">教職員メンバーによって作成されたグループ (**学科**に [**教職員] または [電子メールアドレスが含まれ**ているユーザー]) が faculty.groups.contoso.com ドメインにある。</span><span class="sxs-lookup"><span data-stu-id="7f40c-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="7f40c-131">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f40c-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="7f40c-132">他のすべてのユーザーを groups.contoso.com ドメインに入れる。</span><span class="sxs-lookup"><span data-stu-id="7f40c-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="7f40c-133">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f40c-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="7f40c-134">メール アドレス ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="7f40c-134">Change email address policies</span></span>

<span data-ttu-id="7f40c-135">既存の EAP の優先順位またはメール アドレス テンプレートを変更するには、Set-EmailAddressPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f40c-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="7f40c-136">EAP を変更しても、プロビジョニング済みのグループには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="7f40c-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="7f40c-137">メール アドレス ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="7f40c-137">Delete email address policies</span></span>

<span data-ttu-id="7f40c-138">EAP を削除するには、Remove-EmailAddressPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f40c-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="7f40c-139">EAP を変更しても、プロビジョニング済みのグループには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="7f40c-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="7f40c-140">ハイブリッド要件</span><span class="sxs-lookup"><span data-stu-id="7f40c-140">Hybrid requirements</span></span>

<span data-ttu-id="7f40c-141">組織がハイブリッドシナリオで構成されている場合は、「 [microsoft 365 グループをオンプレミスの Exchange ハイブリッドで構成](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)する」を参照して、組織が microsoft 365 グループを作成するための要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7f40c-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="7f40c-142">電子メールアドレスポリシーグループの使用に関するその他の情報:</span><span class="sxs-lookup"><span data-stu-id="7f40c-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="7f40c-143">以下のいくつかの点を把握しておく必要あります。</span><span class="sxs-lookup"><span data-stu-id="7f40c-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="7f40c-144">グループ作成の速度は、組織に構成されている EAP の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7f40c-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="7f40c-145">管理者とユーザーは、グループを作成するときにドメインを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="7f40c-146">ユーザーのグループは、既に用意されている標準クエリ (ユーザーのプロパティ) を使用して決定されます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="7f40c-147">サポートされているフィルター可能なプロパティについて[は、-受信者フィルターパラメーターのフィルター処理されたプロパティを](https://go.microsoft.com/fwlink/p/?LinkId=785918)確認してください。</span><span class="sxs-lookup"><span data-stu-id="7f40c-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="7f40c-148">グループに EAP を構成しないと、グループの作成で既定の承認済みドメインが選択されます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="7f40c-149">承認済みドメインを削除する場合は、最初に、EAP を更新する必要があります。そうしないと、グループのプロビジョニングが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="7f40c-150">1 つの組織につき最大で 100 のメール アドレス ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7f40c-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="7f40c-151">関連記事</span><span class="sxs-lookup"><span data-stu-id="7f40c-151">Related articles</span></span>

[<span data-ttu-id="7f40c-152">管理センターで Microsoft 365 グループを作成する</span><span class="sxs-lookup"><span data-stu-id="7f40c-152">Create an Microsoft 365 group in the admin center</span></span>](create-groups.md)
