---
title: 監査ログ検索を有効または無効にする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: セキュリティ & コンプライアンス センターで監査ログ検索機能を有効または無効にして、管理者が監査ログを検索する機能を有効または無効にする方法について。
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976330"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="b6f56-103">監査ログ検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b6f56-103">Turn audit log search on or off</span></span>

<span data-ttu-id="b6f56-104">監査ログは、Microsoft 365 および 365 エンタープライズOffice既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b6f56-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="b6f56-105">これには、E3/G3 または E5/G5 サブスクリプションを持つ組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="b6f56-106">コンプライアンス センターで監査ログ検索を有効にすると、組織のユーザーと管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられたライセンスに応じて 90 日間、最大 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="b6f56-107">ただし、組織には監査ログ データを記録して保持したくない理由がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6f56-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="b6f56-108">このような場合、グローバル管理者は Microsoft 365 で監査をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6f56-109">Microsoft 365 で監査ログ検索をオフにした場合、Office 365 マネージメント アクティビティ API または Azure Sentinel を使用して組織の監査データにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b6f56-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="b6f56-110">この記事の手順に従って監査ログ検索をオフにした場合、セキュリティ & コンプライアンス センターを使用して監査ログを検索したり、Exchange Online PowerShell で **Search-UnifiedAuditLog** コマンドレットを実行したりすると、結果は返されません。</span><span class="sxs-lookup"><span data-stu-id="b6f56-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="b6f56-111">つまり、監査ログは、Office 365 マネージメント アクティビティ API または Azure Sentinel を通じて利用できません。</span><span class="sxs-lookup"><span data-stu-id="b6f56-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="b6f56-112">監査ログ検索を有効またはオフにする前に</span><span class="sxs-lookup"><span data-stu-id="b6f56-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="b6f56-113">Microsoft 365 組織で監査ログ検索を有効またはオフに切り替えするには、Exchange Online の監査ログの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6f56-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="b6f56-114">既定では、この役割は Exchange 管理センターの [アクセス許可]ページの [コンプライアンス管理] 役割グループと [組織の管理] 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="b6f56-115">Microsoft 365 のグローバル管理者は、Exchange Online の Organization Management 役割グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="b6f56-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b6f56-116">監査ログ検索を有効またはオフに切り替えするには、Exchange Online でユーザーにアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6f56-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="b6f56-117">セキュリティ & コンプライアンス センターの [アクセス許可] ページでユーザーに監査ログの役割を割り当てると、監査ログの検索を有効またはオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b6f56-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="b6f56-118">これは、基になるコマンドレットが Exchange Online PowerShell コマンドレットだからです。</span><span class="sxs-lookup"><span data-stu-id="b6f56-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="b6f56-119">監査ログの検索に関する詳しい手順については、セキュリティ/コンプライアンス センターの「監査ログを& [参照してください](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="b6f56-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="b6f56-120">Microsoft 365 マネージメント アクティビティ API の詳細については [、「Microsoft 365 Management](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)API の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6f56-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="b6f56-121">監査ログの検索が有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6f56-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="b6f56-122">`True` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査ログ検索が有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b6f56-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="b6f56-123">監査ログ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="b6f56-123">Turn on audit log search</span></span>

<span data-ttu-id="b6f56-124">組織で監査ログの検索が有効ではない場合は、コンプライアンス センターで有効にするか、Exchange Online PowerShell を使用して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="b6f56-125">監査ログの検索を有効にしてから、監査ログの検索時に結果を返すまで数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6f56-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="b6f56-126">コンプライアンス センターを使用して監査ログ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="b6f56-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="b6f56-127">[コンプライアンス センターに移動し、](https://protection.office.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="b6f56-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="b6f56-128">コンプライアンス センターで、検索監査ログ **の検索**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b6f56-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="b6f56-129">組織の監査ログ検索が有効ではない場合は、ユーザーと管理者のアクティビティを記録するために監査を有効にする必要があるというバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="b6f56-130">[ **監査を有効にする] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b6f56-130">Click **Turn on auditing**.</span></span>

    ![[監査を有効にする] をクリックします。](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="b6f56-132">バナーが更新され、監査ログが準備中であり、数時間後にユーザーと管理者のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="b6f56-133">PowerShell を使用して監査ログ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="b6f56-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="b6f56-134">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="b6f56-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="b6f56-135">次の PowerShell コマンドを実行して、365 で監査ログOfficeします。</span><span class="sxs-lookup"><span data-stu-id="b6f56-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="b6f56-136">変更が有効にな最大 60 分かかる可能性があるというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="b6f56-137">監査ログ検索をオフにする</span><span class="sxs-lookup"><span data-stu-id="b6f56-137">Turn off audit log search</span></span>

<span data-ttu-id="b6f56-138">Exchange Online PowerShell を使用して監査ログ検索をオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6f56-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="b6f56-139">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="b6f56-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="b6f56-140">次の PowerShell コマンドを実行して監査ログ検索をオフにします。</span><span class="sxs-lookup"><span data-stu-id="b6f56-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="b6f56-141">しばらくすると、監査ログ検索がオフ (無効) になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6f56-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="b6f56-142">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b6f56-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="b6f56-143">Exchange Online PowerShell で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6f56-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="b6f56-144">`False` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査ログ検索が無効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b6f56-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="b6f56-145">コンプライアンス センター [で、検索](https://protection.office.com)監査ログ **の検索** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b6f56-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="b6f56-146">ユーザーと管理者のアクティビティを記録するには、監査を有効にする必要があるというバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6f56-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>
