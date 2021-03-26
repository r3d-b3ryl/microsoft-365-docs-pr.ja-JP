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
description: '概要: PowerShell for Microsoft 365 を使用して、Microsoft 365 管理センターで作成できないレポートを作成します。'
ms.openlocfilehash: dc183ae8a315bf788befc85474d0647802ac91ee
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222781"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="7c108-103">PowerShell を使用して Microsoft 365 のレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="7c108-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="7c108-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7c108-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7c108-105">Microsoft 365 管理センターでは、さまざまなレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7c108-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7c108-106">しかし、これらのレポートは非常に多くの情報しか提供しないので、より多くの情報が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c108-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="7c108-107">これは、Microsoft 365 用の PowerShell が必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="7c108-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="7c108-108">次の記事では、Microsoft 365 の PowerShell を使用して Microsoft 365 テナントから情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c108-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="7c108-109">PowerShell for Microsoft 365 を使用したレポート作成の開始:</span><span class="sxs-lookup"><span data-stu-id="7c108-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="7c108-110">Microsoft 365 で PowerShell を使用する理由</span><span class="sxs-lookup"><span data-stu-id="7c108-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="7c108-111">ユーザー アカウントおよびライセンスのレポート:</span><span class="sxs-lookup"><span data-stu-id="7c108-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="7c108-112">PowerShell で Microsoft 365 ライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="7c108-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="7c108-113">PowerShell で Microsoft 365 のライセンスユーザーとライセンスのないユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="7c108-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="7c108-114">PowerShell で Microsoft 365 アカウント のライセンスとサービスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="7c108-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="7c108-115">PowerShell で Microsoft 365 ユーザー アカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="7c108-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="7c108-116">SharePoint Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="7c108-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="7c108-117">SharePoint Online 管理シェルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="7c108-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="7c108-118">Get-SPOSiteGroup - 指定したサイト コレクション上のすべてのグループを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c108-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="7c108-119">Exchange Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="7c108-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="7c108-120">Exchange Online PowerShell を使用してメールボックスを表示する</span><span class="sxs-lookup"><span data-stu-id="7c108-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="7c108-121">関連記事</span><span class="sxs-lookup"><span data-stu-id="7c108-121">Related articlesl</span></span>

[<span data-ttu-id="7c108-122">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="7c108-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7c108-123">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="7c108-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7c108-124">PowerShell を使用して SharePoint を管理する</span><span class="sxs-lookup"><span data-stu-id="7c108-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7c108-125">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="7c108-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
