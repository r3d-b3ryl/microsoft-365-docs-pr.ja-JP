---
title: PowerShell を使用して Microsoft 365 のレポートを作成する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: '概要: microsoft 365 の PowerShell を使用して、Microsoft 365 管理センターでは作成できないレポートを作成します。'
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753980"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="38555-103">PowerShell を使用して Microsoft 365 のレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="38555-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="38555-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="38555-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="38555-105">Microsoft 365 管理センターでは、さまざまなレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="38555-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="38555-106">ただし、これらのレポートで提供される情報は非常に多く、場合によってはさらに必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="38555-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="38555-107">これは、Microsoft 365 に PowerShell が必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="38555-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="38555-108">これらの記事では、microsoft 365 の PowerShell を使用して Microsoft 365 テナントから情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38555-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="38555-109">Microsoft 365 の PowerShell を使用したレポート作成の概要:</span><span class="sxs-lookup"><span data-stu-id="38555-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="38555-110">Microsoft 365 で PowerShell を使用する理由</span><span class="sxs-lookup"><span data-stu-id="38555-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="38555-111">ユーザー アカウントおよびライセンスのレポート:</span><span class="sxs-lookup"><span data-stu-id="38555-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="38555-112">PowerShell を使用して Microsoft 365 ライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="38555-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="38555-113">PowerShell を使用して Microsoft 365 ライセンスおよびライセンスのないユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="38555-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="38555-114">PowerShell を使用して Microsoft 365 アカウントのライセンスとサービスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="38555-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="38555-115">PowerShell を使用して Microsoft 365 ユーザーアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="38555-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="38555-116">SharePoint Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="38555-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="38555-117">SharePoint Online 管理シェルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="38555-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="38555-118">Remove-spositegroup-指定したサイトコレクションのすべてのグループを取得します。</span><span class="sxs-lookup"><span data-stu-id="38555-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="38555-119">Exchange Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="38555-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="38555-120">Exchange Online PowerShell を使用してメールボックスを表示する</span><span class="sxs-lookup"><span data-stu-id="38555-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="38555-121">関連 articlesl</span><span class="sxs-lookup"><span data-stu-id="38555-121">Related articlesl</span></span>

[<span data-ttu-id="38555-122">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="38555-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="38555-123">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="38555-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="38555-124">PowerShell を使用して SharePoint を管理する</span><span class="sxs-lookup"><span data-stu-id="38555-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="38555-125">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="38555-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  