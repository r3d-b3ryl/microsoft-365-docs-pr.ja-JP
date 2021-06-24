---
title: 監査のオンとオフを切り替える
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
description: 管理者が監査ログを検索する機能を有効または無効にするには、Microsoft 365 コンプライアンス センターの監査ログ検索機能を有効または無効にする方法を示します。
ms.openlocfilehash: 7c55443eda9a99ff4ef153d8564fd9ac43fcc549
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105310"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="1bc47-103">監査のオンとオフを切り替える</span><span class="sxs-lookup"><span data-stu-id="1bc47-103">Turn auditing on or off</span></span>

<span data-ttu-id="1bc47-104">Microsoft 365 および Office 365 Enterprise 組織では、監査ログは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="1bc47-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="1bc47-105">これには、E3/G3 または E5/G5 サブスクリプションを持つ組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1bc47-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="1bc47-106">コンプライアンス センターで監査を有効にすると、組織のユーザーと管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられたライセンスに応じて 90 日間、最大 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="1bc47-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="1bc47-107">ただし、監査ログ データを記録および保持しない理由が組織にある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1bc47-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="1bc47-108">このような場合、グローバル管理者は、管理者が監査をオフにMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="1bc47-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bc47-109">Microsoft 365 で監査をオフにした場合、Office 365 管理アクティビティ API または Azure Sentinel を使用して組織の監査データにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1bc47-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="1bc47-110">この記事の手順に従って監査をオフにした場合、セキュリティ & コンプライアンス センターを使用して監査ログを検索したり、Exchange Online PowerShell で **Search-UnifiedAuditLog** コマンドレットを実行したりすると、結果は返されません。</span><span class="sxs-lookup"><span data-stu-id="1bc47-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="1bc47-111">つまり、監査ログは、管理アクティビティ API または Azure Sentinel Office 365使用できません。</span><span class="sxs-lookup"><span data-stu-id="1bc47-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="1bc47-112">監査を有効またはオフにする前に</span><span class="sxs-lookup"><span data-stu-id="1bc47-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="1bc47-113">組織で監査を有効またはExchange Onlineするには、監査ログの役割を割りMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="1bc47-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="1bc47-114">既定では、この役割は、管理センターの [アクセス許可] ページの[コンプライアンス管理] および [組織の管理Exchange割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1bc47-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="1bc47-115">グループ内のグローバルMicrosoft 365は、組織の管理役割グループのメンバー Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1bc47-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="1bc47-116">監査を有効またはオフに切り替Exchange Onlineユーザーにアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bc47-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="1bc47-117">セキュリティ & コンプライアンス センターの [アクセス許可] ページでユーザーに監査ログの役割を割り当てると、監査をオンまたはオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1bc47-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="1bc47-118">これは、基になるコマンドレットが PowerShell コマンドレットExchange Onlineです。</span><span class="sxs-lookup"><span data-stu-id="1bc47-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span>

- <span data-ttu-id="1bc47-119">監査ログの検索に関する詳細な手順については、「セキュリティ コンプライアンス センターで監査ログを検索する」 [を&してください](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc47-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="1bc47-120">管理アクティビティ API の詳細Microsoft 365、「管理 API の概要」を参照Microsoft 365[してください](/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="1bc47-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="1bc47-121">監査が有効になっていることを確認するには、PowerShell で次のコマンドExchange Onlineできます。</span><span class="sxs-lookup"><span data-stu-id="1bc47-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="1bc47-122">`True` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査が有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="1bc47-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="1bc47-123">監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="1bc47-123">Turn on auditing</span></span>

<span data-ttu-id="1bc47-124">組織で監査を有効にしていない場合は、コンプライアンス センターで有効にするか、PowerShell を使用Exchange Onlineできます。</span><span class="sxs-lookup"><span data-stu-id="1bc47-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="1bc47-125">監査ログを検索するときに結果を返す前に、監査を有効にしてから数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1bc47-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="1bc47-126">コンプライアンス センターを使用して監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="1bc47-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="1bc47-127"><https://compliance.microsoft.com> に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="1bc47-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="1bc47-128">左側のナビゲーション ウィンドウで、[すべて表示Microsoft 365 コンプライアンス センター **をクリックし**、[監査] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1bc47-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="1bc47-129">組織の監査が有効ではない場合は、ユーザーと管理アクティビティの記録を開始するように求めるバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bc47-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![[監査] ページのバナー](../media/AuditingBanner.png)

3. <span data-ttu-id="1bc47-131">[ユーザーと **管理アクティビティの記録を開始する] バナーをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="1bc47-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="1bc47-132">変更を有効にするには、最大 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1bc47-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="1bc47-133">PowerShell を使用して監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="1bc47-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="1bc47-134">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="1bc47-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="1bc47-135">次の PowerShell コマンドを実行して、監査を有効にOffice 365。</span><span class="sxs-lookup"><span data-stu-id="1bc47-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="1bc47-136">変更を有効にするには、最大 60 分かかる可能性があるというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bc47-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="1bc47-137">監査をオフにする</span><span class="sxs-lookup"><span data-stu-id="1bc47-137">Turn off auditing</span></span>

<span data-ttu-id="1bc47-138">監査をオフExchange Online PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bc47-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="1bc47-139">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="1bc47-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="1bc47-140">次の PowerShell コマンドを実行して監査をオフにします。</span><span class="sxs-lookup"><span data-stu-id="1bc47-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="1bc47-141">しばらくすると、監査が無効 (無効) になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1bc47-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="1bc47-142">これを行うには次に示す 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="1bc47-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="1bc47-143">PowerShell Exchange Onlineで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1bc47-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="1bc47-144">`False` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査がオフになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="1bc47-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="1bc47-145">[監査]**ページの**[監査] Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="1bc47-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="1bc47-146">組織の監査が有効ではない場合は、ユーザーと管理アクティビティの記録を開始するように求めるバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bc47-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
