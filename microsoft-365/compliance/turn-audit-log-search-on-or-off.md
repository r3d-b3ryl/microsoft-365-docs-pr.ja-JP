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
description: セキュリティ & コンプライアンスセンターで監査ログ検索機能をオンまたはオフにして、管理者が監査ログを検索する機能を有効または無効にします。
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819137"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="906eb-103">監査ログ検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="906eb-103">Turn audit log search on or off</span></span>

<span data-ttu-id="906eb-104">監査ログの検索を開始する前に、自分 (または別の管理者) が監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-104">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="906eb-105">セキュリティ & コンプライアンスセンターで監査ログの検索が有効になっている場合は、組織のユーザーおよび管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられているライセンスに応じて、90日間、および最大1年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="906eb-105">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="906eb-106">ただし、監査ログデータを記録して保持しない理由が組織にある場合があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="906eb-107">そのような場合は、グローバル管理者が Microsoft 365 の監査を無効にすることを決定することがあります。</span><span class="sxs-lookup"><span data-stu-id="906eb-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="906eb-108">Microsoft 365 で監査ログの検索を無効にした場合、Office 365 Management Activity API または Azure Sentinel を使用して組織の監査データにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="906eb-108">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="906eb-109">この記事の手順に従って監査ログの検索を無効にすると、セキュリティ & コンプライアンスセンターを使用して監査ログを検索したとき、または Exchange Online PowerShell で**search-unifiedauditlog**コマンドレットを実行したときに結果が返されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="906eb-109">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="906eb-110">これは、Office 365 Management Activity API または Azure Sentinel を介して監査ログを利用できないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="906eb-110">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="906eb-111">監査ログ検索をオンまたはオフにする前に</span><span class="sxs-lookup"><span data-stu-id="906eb-111">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="906eb-112">Microsoft 365 組織で監査ログの検索をオンまたはオフにするには、Exchange Online の Audit Logs 役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="906eb-113">既定では、この役割は、Exchange 管理センターの [**アクセス許可**] ページで、コンプライアンス管理および組織の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="906eb-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="906eb-114">Microsoft 365 のグローバル管理者は、Exchange Online の Organization Management 役割グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="906eb-114">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="906eb-115">監査ログの検索を有効または無効にするには、Exchange Online のアクセス許可をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="906eb-116">セキュリティ & コンプライアンスセンターの [**アクセス許可**] ページで監査ログの役割をユーザーに割り当てると、監査ログの検索をオンまたはオフにすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="906eb-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="906eb-117">これは、基礎となるコマンドレットが Exchange Online のコマンドレットであるためです。</span><span class="sxs-lookup"><span data-stu-id="906eb-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="906eb-118">監査ログの検索の詳細な手順については、「[セキュリティ & のコンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="906eb-118">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="906eb-119">Microsoft 365 Management Activity API の詳細については、「 [microsoft 365 管理 api の使用を開始](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="906eb-119">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="906eb-120">監査ログ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="906eb-120">Turn on audit log search</span></span>

<span data-ttu-id="906eb-121">セキュリティ & コンプライアンスセンターまたは PowerShell を使用して、Microsoft 365 で監査ログの検索を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="906eb-121">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="906eb-122">監査ログの検索を有効にすると、監査ログの検索時に結果を返す前に、数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-122">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="906eb-123">監査ログ検索を有効にするには、Exchange Online で Audit Logs 役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-123">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="906eb-124">セキュリティ & コンプライアンスセンターを使用して監査ログの検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="906eb-124">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="906eb-125">[[セキュリティ & コンプライアンスセンター] に移動](https://protection.office.com)して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="906eb-125">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="906eb-126">[セキュリティ & コンプライアンスセンター] で、[**検索** \> **監査ログの検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="906eb-126">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="906eb-127">ユーザーおよび管理者のアクティビティを記録するために、監査を有効にする必要があるというバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="906eb-127">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="906eb-128">[**監査を有効にする] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="906eb-128">Click **Turn on auditing**.</span></span>

    ![[監査を有効にする] をクリックします。](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="906eb-130">バナーが更新され、監査ログの準備が完了し、ユーザーと管理者のアクティビティを数時間で検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="906eb-130">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="906eb-131">PowerShell を使用して監査ログの検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="906eb-131">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="906eb-132">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="906eb-132">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="906eb-133">Office 365 で監査ログの検索を有効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="906eb-133">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="906eb-134">変更が有効になるまでに最大60分かかる可能性があることを伝えるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="906eb-134">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="906eb-135">監査ログの検索を無効にする</span><span class="sxs-lookup"><span data-stu-id="906eb-135">Turn off audit log search</span></span>

<span data-ttu-id="906eb-136">監査ログの検索を無効にするには、Exchange Online 組織に接続されたリモート PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-136">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="906eb-137">監査ログ検索を有効にするのと同様に、監査ログ検索を無効にするには、Exchange Online の Audit Logs 役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-137">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="906eb-138">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="906eb-138">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="906eb-139">Office 365 で監査ログの検索を無効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="906eb-139">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="906eb-140">しばらくした後、監査ログの検索がオフ (無効) になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="906eb-140">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="906eb-141">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="906eb-141">There are two ways to do this:</span></span>

    - <span data-ttu-id="906eb-142">PowerShell で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="906eb-142">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="906eb-143">UnifiedAuditLogIngestionEnabled プロパティのの値は、 `False` 監査ログの検索がオフになっていることを示します。 _UnifiedAuditLogIngestionEnabled_</span><span class="sxs-lookup"><span data-stu-id="906eb-143">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="906eb-144">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**検索** \> **監査ログの検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="906eb-144">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="906eb-145">ユーザーおよび管理者のアクティビティを記録するために、監査を有効にする必要があるというバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="906eb-145">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>