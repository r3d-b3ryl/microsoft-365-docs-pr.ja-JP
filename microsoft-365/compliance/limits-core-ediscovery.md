---
title: コア電子情報開示ケースの制限
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: この記事では、Microsoft 365 のコア電子情報開示ケースの制限について説明します。
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423448"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="aca49-103">コア電子情報開示の制限</span><span class="sxs-lookup"><span data-stu-id="aca49-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="aca49-104">次の表に、コアの電子情報開示ケースと、コア電子情報開示ケースに関連付けられているホールドの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="aca49-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="aca49-105">Core eDiscovery の詳細については、「Overview [of Core eDiscovery」を参照してください](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="aca49-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="aca49-106">制限の説明</span><span class="sxs-lookup"><span data-stu-id="aca49-106">Description of limit</span></span> | <span data-ttu-id="aca49-107">制限</span><span class="sxs-lookup"><span data-stu-id="aca49-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="aca49-108">組織のケースの最大数。</span><span class="sxs-lookup"><span data-stu-id="aca49-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="aca49-109">制限なし</span><span class="sxs-lookup"><span data-stu-id="aca49-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="aca49-110">組織のケースホールドの最大数。</span><span class="sxs-lookup"><span data-stu-id="aca49-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="aca49-111">10,000</span><span class="sxs-lookup"><span data-stu-id="aca49-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="aca49-112">1 つのケースホールド内のメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="aca49-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="aca49-113">この制限には、ユーザー メールボックスの合計と、Microsoft 365 グループ、Microsoft Teams、およびグループグループに関連付けられたメールボックスYammer含まれます。</span><span class="sxs-lookup"><span data-stu-id="aca49-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="aca49-114">1,000</span><span class="sxs-lookup"><span data-stu-id="aca49-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="aca49-115">1 つのケースホールド内のサイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="aca49-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="aca49-116">この制限には、OneDrive for Business サイト、SharePoint サイト、および Microsoft 365 グループ、Microsoft Teams、および Yammer グループに関連付けられたサイトの合計が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aca49-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="aca49-117">100</span><span class="sxs-lookup"><span data-stu-id="aca49-117">100</span></span>  <br/> |
  |<span data-ttu-id="aca49-118">コアの電子情報開示ホーム ページに表示されるケースの最大数と、ケース内の [保持] タブ、[検索] タブ、および [エクスポート] タブに表示されるアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="aca49-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="aca49-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="aca49-119"><sup>1</sup></span></span> |<span data-ttu-id="aca49-120">1,000</span><span class="sxs-lookup"><span data-stu-id="aca49-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="aca49-121"><sup>1</sup> 1,000 を超えるケース、ホールド、検索、またはエクスポートのリストを表示するには、対応する Office 365 Security & Compliance PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aca49-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="aca49-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="aca49-122">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="aca49-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="aca49-123">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="aca49-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="aca49-124">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="aca49-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="aca49-125">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="aca49-126">Core eDiscovery ケースに関連付けられたコンテンツ検索とエクスポートに関連する制限の詳細については、「Limits for Content [Search and Core eDiscovery」を参照してください](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="aca49-126">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>