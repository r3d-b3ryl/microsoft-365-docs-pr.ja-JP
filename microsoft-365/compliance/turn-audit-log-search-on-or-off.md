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
description: セキュリティ & コンプライアンスセンターでは、監査ログ検索機能を有効にすることができます。 変更した場合は、いつでもオフにすることができます。 監査ログの検索がオフになっている場合、管理者は、組織内のユーザーおよび管理者のアクティビティについて Microsoft 365 の監査ログを検索することはできません。
ms.openlocfilehash: f3d88f62f466d9c868dfc6addb5865e144f5223b
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330791"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="e8534-105">監査ログ検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e8534-105">Turn audit log search on or off</span></span>

<span data-ttu-id="e8534-106">監査ログの検索を開始する前に、自分 (または別の管理者) が監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-106">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="e8534-107">セキュリティ & コンプライアンスセンターで監査ログの検索が有効になっている場合は、組織のユーザーおよび管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられているライセンスに応じて、90日間、および最大1年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="e8534-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="e8534-108">ただし、監査ログデータを記録して保持しない理由が組織にある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-108">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="e8534-109">そのような場合は、グローバル管理者が Microsoft 365 の監査を無効にすることを決定することがあります。</span><span class="sxs-lookup"><span data-stu-id="e8534-109">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8534-110">Microsoft 365 で監査ログの検索を無効にした場合、Office 365 Management Activity API または Azure Sentinel を使用して組織の監査データにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e8534-110">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="e8534-111">この記事の手順に従って監査ログの検索を無効にすると、セキュリティ & コンプライアンスセンターを使用して監査ログを検索したとき、または Exchange Online PowerShell で**search-unifiedauditlog**コマンドレットを実行したときに結果が返されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e8534-111">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="e8534-112">これは、Office 365 Management Activity API または Azure Sentinel を介して監査ログを利用できないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="e8534-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e8534-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="e8534-113">Before you begin</span></span>

- <span data-ttu-id="e8534-114">Microsoft 365 組織で監査ログの検索をオンまたはオフにするには、Exchange Online の Audit Logs 役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-114">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="e8534-115">既定では、この役割は、Exchange 管理センターの [**アクセス許可**] ページで、コンプライアンス管理および組織の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e8534-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="e8534-116">Microsoft 365 のグローバル管理者は、Exchange Online の Organization Management 役割グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="e8534-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e8534-117">監査ログの検索を有効または無効にするには、Exchange Online のアクセス許可をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-117">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="e8534-118">セキュリティ & コンプライアンスセンターの [**アクセス許可**] ページで監査ログの役割をユーザーに割り当てると、監査ログの検索をオンまたはオフにすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="e8534-118">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="e8534-119">これは、基礎となるコマンドレットが Exchange Online のコマンドレットであるためです。</span><span class="sxs-lookup"><span data-stu-id="e8534-119">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="e8534-120">監査ログの検索の詳細な手順については、「[セキュリティ & のコンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8534-120">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="e8534-121">Microsoft 365 Management Activity API の詳細については、「 [microsoft 365 管理 api の使用を開始](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8534-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="e8534-122">監査ログ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="e8534-122">Turn on audit log search</span></span>

<span data-ttu-id="e8534-123">セキュリティ & コンプライアンスセンターまたは PowerShell を使用して、Microsoft 365 で監査ログの検索を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8534-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="e8534-124">監査ログの検索を有効にすると、監査ログの検索時に結果を返す前に、数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="e8534-125">監査ログ検索を有効にするには、Exchange Online で Audit Logs 役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="e8534-126">セキュリティ & コンプライアンスセンターを使用して監査ログの検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="e8534-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="e8534-127">[[セキュリティ & コンプライアンスセンター] に移動](https://protection.office.com)して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e8534-127">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="e8534-128">[セキュリティ & コンプライアンスセンター] で、[**検索** \> **監査ログの検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8534-128">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="e8534-129">ユーザーおよび管理者のアクティビティを記録するために、監査を有効にする必要があるというバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8534-129">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="e8534-130">[**監査を有効にする] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="e8534-130">Click **Turn on auditing**.</span></span>

    ![[監査を有効にする] をクリックします。](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="e8534-132">バナーが更新され、監査ログの準備が完了し、ユーザーと管理者のアクティビティを数時間で検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e8534-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="e8534-133">PowerShell を使用して監査ログの検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="e8534-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="e8534-134">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="e8534-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="e8534-135">Office 365 で監査ログの検索を有効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8534-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="e8534-136">変更が有効になるまでに最大60分かかる可能性があることを伝えるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8534-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="e8534-137">監査ログの検索を無効にする</span><span class="sxs-lookup"><span data-stu-id="e8534-137">Turn off audit log search</span></span>

<span data-ttu-id="e8534-138">監査ログの検索を無効にするには、Exchange Online 組織に接続されたリモート PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="e8534-139">監査ログ検索を有効にするのと同様に、監査ログ検索を無効にするには、Exchange Online の Audit Logs 役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="e8534-140">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="e8534-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="e8534-141">Office 365 で監査ログの検索を無効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8534-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="e8534-142">しばらくした後、監査ログの検索がオフ (無効) になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8534-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="e8534-143">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e8534-143">There are two ways to do this:</span></span>

    - <span data-ttu-id="e8534-144">PowerShell で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8534-144">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="e8534-145">UnifiedAuditLogIngestionEnabled プロパティのの値は、 `False` 監査ログの検索がオフになっていることを示します。 _UnifiedAuditLogIngestionEnabled_</span><span class="sxs-lookup"><span data-stu-id="e8534-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="e8534-146">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**検索** \> **監査ログの検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8534-146">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="e8534-147">ユーザーおよび管理者のアクティビティを記録するために、監査を有効にする必要があるというバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8534-147">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>