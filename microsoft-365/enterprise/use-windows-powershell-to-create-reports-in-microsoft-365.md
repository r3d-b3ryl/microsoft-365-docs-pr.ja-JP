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
description: '概要: PowerShell を使用Microsoft 365管理センターで作成できないレポートを作成Microsoft 365します。'
ms.openlocfilehash: dc183ae8a315bf788befc85474d0647802ac91ee
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222781"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="10236-103">PowerShell を使用して Microsoft 365 のレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="10236-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="10236-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="10236-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="10236-105">管理センターでは、さまざまなレポートMicrosoft 365利用できます。</span><span class="sxs-lookup"><span data-stu-id="10236-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="10236-106">しかし、これらのレポートは非常に多くの情報しか提供しないので、より多くの情報が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="10236-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="10236-107">この場合は、PowerShell が必要Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="10236-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="10236-108">これらの記事では、PowerShell を使用してテナントMicrosoft 365情報を取得する方法Microsoft 365説明します。</span><span class="sxs-lookup"><span data-stu-id="10236-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="10236-109">PowerShell を使用したレポート作成のMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="10236-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="10236-110">Microsoft 365 で PowerShell を使用する理由</span><span class="sxs-lookup"><span data-stu-id="10236-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="10236-111">ユーザー アカウントおよびライセンスのレポート:</span><span class="sxs-lookup"><span data-stu-id="10236-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="10236-112">PowerShell Microsoft 365ライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="10236-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="10236-113">PowerShell Microsoft 365ライセンスユーザーとライセンスのないユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="10236-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="10236-114">PowerShell Microsoft 365アカウント のライセンスとサービスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="10236-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="10236-115">PowerShell Microsoft 365ユーザー アカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="10236-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="10236-116">SharePoint Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="10236-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="10236-117">SharePoint Online 管理シェルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="10236-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="10236-118">Get-SPOSiteGroup - 指定したサイト コレクション上のすべてのグループを取得します。</span><span class="sxs-lookup"><span data-stu-id="10236-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="10236-119">Exchange Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="10236-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="10236-120">PowerShell Exchange Onlineを使用してメールボックスを表示する</span><span class="sxs-lookup"><span data-stu-id="10236-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="10236-121">関連記事</span><span class="sxs-lookup"><span data-stu-id="10236-121">Related articlesl</span></span>

[<span data-ttu-id="10236-122">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="10236-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="10236-123">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="10236-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="10236-124">PowerShell SharePointを管理する</span><span class="sxs-lookup"><span data-stu-id="10236-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="10236-125">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="10236-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
