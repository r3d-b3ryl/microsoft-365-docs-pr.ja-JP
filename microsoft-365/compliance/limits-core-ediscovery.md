---
title: コア電子情報開示ケースの制限
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551447"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="fff81-103">コア電子情報開示の制限</span><span class="sxs-lookup"><span data-stu-id="fff81-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="fff81-104">次の表に、主要な電子情報開示ケースの制限と、コア電子情報開示ケースに関連付けられている保留リストを示します。</span><span class="sxs-lookup"><span data-stu-id="fff81-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="fff81-105">コア電子情報開示の詳細については、「[コア電子情報開示の概要](ediscovery-cases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fff81-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="fff81-106">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="fff81-106">**Description of limit**</span></span>|<span data-ttu-id="fff81-107">**制限**</span><span class="sxs-lookup"><span data-stu-id="fff81-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="fff81-108">組織のケースの最大数</span><span class="sxs-lookup"><span data-stu-id="fff81-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="fff81-109">制限なし</span><span class="sxs-lookup"><span data-stu-id="fff81-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="fff81-110">組織のケース保留の最大数</span><span class="sxs-lookup"><span data-stu-id="fff81-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="fff81-111">10,000</span><span class="sxs-lookup"><span data-stu-id="fff81-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="fff81-112">1 つのケース保留のメールボックスの最大数</span><span class="sxs-lookup"><span data-stu-id="fff81-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="fff81-113">1,000</span><span class="sxs-lookup"><span data-stu-id="fff81-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="fff81-114">1 つのケース保留の SharePoint および OneDrive for Business サイトの最大数</span><span class="sxs-lookup"><span data-stu-id="fff81-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="fff81-115">100</span><span class="sxs-lookup"><span data-stu-id="fff81-115">100</span></span>  <br/> |
  |<span data-ttu-id="fff81-116">コア電子情報開示のホームページに表示されるケースの最大数と、ケース内で保持、検索、およびエクスポートタブに表示されるアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="fff81-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="fff81-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fff81-117"><sup>1</sup></span></span> |<span data-ttu-id="fff81-118">1,000</span><span class="sxs-lookup"><span data-stu-id="fff81-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="fff81-119"><sup>1</sup> 1000 ケース、ホールド、検索、またはエクスポートの一覧を表示するには、対応する Office 365 Security & コンプライアンス PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fff81-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="fff81-120">Get-compliancecase</span><span class="sxs-lookup"><span data-stu-id="fff81-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [<span data-ttu-id="fff81-121">CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="fff81-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [<span data-ttu-id="fff81-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="fff81-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [<span data-ttu-id="fff81-123">New-compliancesearchaction</span><span class="sxs-lookup"><span data-stu-id="fff81-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
