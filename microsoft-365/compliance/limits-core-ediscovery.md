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
description: この記事では、電子情報開示のコア ケースの制限について説明Microsoft 365。
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311426"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="6e34e-103">コア電子情報開示の制限</span><span class="sxs-lookup"><span data-stu-id="6e34e-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="6e34e-104">次の表に、コアの電子情報開示ケースと、コア電子情報開示ケースに関連付けられているホールドの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="6e34e-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="6e34e-105">Core eDiscovery の詳細については、「Overview [of Core eDiscovery」を参照してください](./get-started-core-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="6e34e-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="6e34e-106">制限の説明</span><span class="sxs-lookup"><span data-stu-id="6e34e-106">Description of limit</span></span> | <span data-ttu-id="6e34e-107">制限</span><span class="sxs-lookup"><span data-stu-id="6e34e-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="6e34e-108">組織のケースの最大数。</span><span class="sxs-lookup"><span data-stu-id="6e34e-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="6e34e-109">制限なし</span><span class="sxs-lookup"><span data-stu-id="6e34e-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="6e34e-110">組織のケースホールドの最大数。</span><span class="sxs-lookup"><span data-stu-id="6e34e-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="6e34e-111">10,000</span><span class="sxs-lookup"><span data-stu-id="6e34e-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="6e34e-112">1 つのケースホールド内のメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="6e34e-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="6e34e-113">この制限には、ユーザー メールボックスの合計と、グループ、グループ、およびグループに関連Microsoft 365メールボックスMicrosoft TeamsがYammerされます。</span><span class="sxs-lookup"><span data-stu-id="6e34e-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="6e34e-114">1,000</span><span class="sxs-lookup"><span data-stu-id="6e34e-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="6e34e-115">1 つのケースホールド内のサイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="6e34e-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="6e34e-116">この制限には、OneDrive for Business サイト、SharePoint サイト、および Microsoft 365 グループ、Microsoft Teams、および Yammer グループに関連付けられたサイトの合計が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e34e-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="6e34e-117">100</span><span class="sxs-lookup"><span data-stu-id="6e34e-117">100</span></span>  <br/> |
  |<span data-ttu-id="6e34e-118">コアの電子情報開示ホーム ページに表示されるケースの最大数と、ケース内の [保持] タブ、[検索] タブ、および [エクスポート] タブに表示されるアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="6e34e-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="6e34e-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6e34e-119"><sup>1</sup></span></span> |<span data-ttu-id="6e34e-120">1,000</span><span class="sxs-lookup"><span data-stu-id="6e34e-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="6e34e-121"><sup>1</sup> 1,000 を超えるケース、ホールド、検索、またはエクスポートのリストを表示するには、対応する Office 365 Security & Compliance PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e34e-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="6e34e-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="6e34e-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="6e34e-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="6e34e-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="6e34e-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="6e34e-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="6e34e-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="6e34e-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="6e34e-126">Core 電子情報開示ケースに関連付けられた検索とエクスポートに関連する制限の詳細については、「コンテンツ検索の制限」および [「Core eDiscovery」を参照してください](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="6e34e-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>