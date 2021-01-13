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
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799664"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="34c8c-103">コア電子情報開示の制限</span><span class="sxs-lookup"><span data-stu-id="34c8c-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="34c8c-104">次の表に、コア電子情報開示ケースと、コア電子情報開示ケースに関連付けられている保留リストの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="34c8c-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="34c8c-105">コア電子情報開示の詳細については、「コア電子情報開示の概要 [」を参照してください](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="34c8c-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="34c8c-106">制限の説明</span><span class="sxs-lookup"><span data-stu-id="34c8c-106">Description of limit</span></span> | <span data-ttu-id="34c8c-107">極限</span><span class="sxs-lookup"><span data-stu-id="34c8c-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="34c8c-108">組織のケースの最大数</span><span class="sxs-lookup"><span data-stu-id="34c8c-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="34c8c-109">制限なし</span><span class="sxs-lookup"><span data-stu-id="34c8c-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="34c8c-110">組織のケース保留の最大数</span><span class="sxs-lookup"><span data-stu-id="34c8c-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="34c8c-111">10,000</span><span class="sxs-lookup"><span data-stu-id="34c8c-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="34c8c-112">1 つのケース保留のメールボックスの最大数</span><span class="sxs-lookup"><span data-stu-id="34c8c-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="34c8c-113">1,000</span><span class="sxs-lookup"><span data-stu-id="34c8c-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="34c8c-114">1 つのケース保留の SharePoint および OneDrive for Business サイトの最大数</span><span class="sxs-lookup"><span data-stu-id="34c8c-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="34c8c-115">100</span><span class="sxs-lookup"><span data-stu-id="34c8c-115">100</span></span>  <br/> |
  |<span data-ttu-id="34c8c-116">コア電子情報開示ホーム ページに表示されるケースの最大数と、ケース内の [保留リスト]、[検索]、および [エクスポート] タブに表示されるアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="34c8c-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="34c8c-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="34c8c-117"><sup>1</sup></span></span> |<span data-ttu-id="34c8c-118">1,000</span><span class="sxs-lookup"><span data-stu-id="34c8c-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="34c8c-119"><sup>1</sup> 1,000 件を超えるケース、保留、検索、またはエクスポートの一覧を表示するには、対応する Office 365 Security & Compliance PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34c8c-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="34c8c-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="34c8c-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="34c8c-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="34c8c-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="34c8c-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="34c8c-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="34c8c-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="34c8c-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="34c8c-124">コア電子情報開示ケースに関連するコンテンツ検索とエクスポートに関連する制限の詳細については、「コンテンツ検索とコア電子情報開示の制限」を参照 [してください](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="34c8c-124">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>