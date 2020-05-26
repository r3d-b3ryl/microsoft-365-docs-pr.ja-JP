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
ms.openlocfilehash: 00df8cff683701ce5ee38dca12b6f7af5b31c8b0
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351898"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="88052-103">コア電子情報開示の制限</span><span class="sxs-lookup"><span data-stu-id="88052-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="88052-104">次の表に、主要な電子情報開示ケースの制限と、コア電子情報開示ケースに関連付けられている保留リストを示します。</span><span class="sxs-lookup"><span data-stu-id="88052-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="88052-105">コア電子情報開示の詳細については、「[コア電子情報開示の概要](ediscovery-cases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88052-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="88052-106">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="88052-106">**Description of limit**</span></span>|<span data-ttu-id="88052-107">**制限**</span><span class="sxs-lookup"><span data-stu-id="88052-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="88052-108">組織のケースの最大数</span><span class="sxs-lookup"><span data-stu-id="88052-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="88052-109">制限なし</span><span class="sxs-lookup"><span data-stu-id="88052-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="88052-110">組織のケース保留の最大数</span><span class="sxs-lookup"><span data-stu-id="88052-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="88052-111">10,000</span><span class="sxs-lookup"><span data-stu-id="88052-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="88052-112">1 つのケース保留のメールボックスの最大数</span><span class="sxs-lookup"><span data-stu-id="88052-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="88052-113">1,000</span><span class="sxs-lookup"><span data-stu-id="88052-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="88052-114">1 つのケース保留の SharePoint および OneDrive for Business サイトの最大数</span><span class="sxs-lookup"><span data-stu-id="88052-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="88052-115">100</span><span class="sxs-lookup"><span data-stu-id="88052-115">100</span></span>  <br/> |
  |<span data-ttu-id="88052-116">コア電子情報開示のホームページに表示されるケースの最大数と、ケース内で保持、検索、およびエクスポートタブに表示されるアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="88052-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="88052-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88052-117"><sup>1</sup></span></span> |<span data-ttu-id="88052-118">1,000</span><span class="sxs-lookup"><span data-stu-id="88052-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="88052-119"><sup>1</sup> 1000 ケース、ホールド、検索、またはエクスポートの一覧を表示するには、対応する Office 365 Security & コンプライアンス PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="88052-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="88052-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="88052-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [<span data-ttu-id="88052-121">CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="88052-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [<span data-ttu-id="88052-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="88052-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [<span data-ttu-id="88052-123">New-compliancesearchaction</span><span class="sxs-lookup"><span data-stu-id="88052-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
