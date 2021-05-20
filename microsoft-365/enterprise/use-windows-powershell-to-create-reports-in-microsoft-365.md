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
description: '概要: powerShell を Microsoft 365 に使用して、Microsoft 365管理センターで作成できないレポートを作成します。'
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572743"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="07e38-103">PowerShell を使用して Microsoft 365 のレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="07e38-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="07e38-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="07e38-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="07e38-105">Microsoft 365管理センターでは、さまざまなレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="07e38-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="07e38-106">しかし、これらのレポートは非常に多くの情報しか提供されず、より多くの情報が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="07e38-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="07e38-107">Microsoft 365用に PowerShell が必要なときです。</span><span class="sxs-lookup"><span data-stu-id="07e38-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="07e38-108">次の記事では、Microsoft 365テナントから情報を取得するMicrosoft 365に PowerShell を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e38-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="07e38-109">Microsoft 365用の PowerShell を使用したレポート作成の概要:</span><span class="sxs-lookup"><span data-stu-id="07e38-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="07e38-110">Microsoft 365 で PowerShell を使用する理由</span><span class="sxs-lookup"><span data-stu-id="07e38-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="07e38-111">ユーザー アカウントおよびライセンスのレポート:</span><span class="sxs-lookup"><span data-stu-id="07e38-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="07e38-112">PowerShell を使用してMicrosoft 365ライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="07e38-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="07e38-113">PowerShell を使用Microsoft 365ライセンスユーザーとライセンスされていないユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="07e38-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="07e38-114">PowerShell Microsoft 365アカウント ライセンスとサービスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="07e38-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="07e38-115">PowerShell を使用してMicrosoft 365ユーザー アカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="07e38-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="07e38-116">SharePoint Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="07e38-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="07e38-117">SharePoint Online 管理シェルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="07e38-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="07e38-118">Get-SPOSiteGroup - 指定されたサイト コレクションのすべてのグループを取得します。</span><span class="sxs-lookup"><span data-stu-id="07e38-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="07e38-119">Exchange Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="07e38-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="07e38-120">powerShell Exchange Online使用してメールボックスを表示する</span><span class="sxs-lookup"><span data-stu-id="07e38-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="07e38-121">関連記事</span><span class="sxs-lookup"><span data-stu-id="07e38-121">Related articles</span></span>

[<span data-ttu-id="07e38-122">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="07e38-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="07e38-123">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="07e38-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="07e38-124">SharePointを管理する</span><span class="sxs-lookup"><span data-stu-id="07e38-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="07e38-125">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="07e38-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
