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
ms.openlocfilehash: 99aa86b1b58b15c63803e1b71d071cbde5c38492
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691946"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="acd98-103">PowerShell を使用して Microsoft 365 のレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="acd98-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="acd98-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="acd98-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="acd98-105">Microsoft 365 管理者センターでは、数多くのさまざまなレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="acd98-105">There are many different reports available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="acd98-106">ただし、これらのレポートは大量の情報を提供するだけで、さらに詳細が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="acd98-106">However, these reports only provide so much information and sometimes you need more.</span></span> <span data-ttu-id="acd98-107">これは、Microsoft 365 に PowerShell が必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="acd98-107">That's when you need PowerShell for Microsoft 365</span></span>
  
<span data-ttu-id="acd98-108">次の記事では、microsoft 365 の PowerShell を使用して Microsoft 365 テナントから情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="acd98-108">These articles that describe how to use PowerShell for Microsoft 365 to obtain information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="acd98-109">Microsoft 365 の PowerShell を使用したレポート作成の概要:</span><span class="sxs-lookup"><span data-stu-id="acd98-109">Getting started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="acd98-110">Microsoft 365 の PowerShell では、管理センターでは表示できない追加情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="acd98-110">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Admin center</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
  - [<span data-ttu-id="acd98-111">Microsoft 365 の PowerShell は、データのフィルター処理に適しています。</span><span class="sxs-lookup"><span data-stu-id="acd98-111">PowerShell for Microsoft 365 is great at filtering data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#filter)
    
  - [<span data-ttu-id="acd98-112">Microsoft 365 の PowerShell を使用すると、データの印刷や保存が容易になります。</span><span class="sxs-lookup"><span data-stu-id="acd98-112">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#printsave)
    
- <span data-ttu-id="acd98-113">ユーザー アカウントおよびライセンスのレポート:</span><span class="sxs-lookup"><span data-stu-id="acd98-113">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="acd98-114">PowerShell を使用して Microsoft 365 ライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="acd98-114">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="acd98-115">PowerShell を使用して Microsoft 365 ライセンスおよびライセンスのないユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="acd98-115">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="acd98-116">PowerShell を使用して Microsoft 365 アカウントのライセンスとサービスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="acd98-116">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="acd98-117">PowerShell を使用して Microsoft 365 ユーザーアカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="acd98-117">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="acd98-118">SharePoint Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="acd98-118">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="acd98-119">SharePoint Online 管理シェルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="acd98-119">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="acd98-120">PowerShell を使用して SharePoint Online サイト グループを管理する</span><span class="sxs-lookup"><span data-stu-id="acd98-120">Manage SharePoint Online site groups with PowerShell</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="acd98-121">Exchange Online のレポート:</span><span class="sxs-lookup"><span data-stu-id="acd98-121">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="acd98-122">PowerShell を使用して Exchange Online メールボックス情報を表示する</span><span class="sxs-lookup"><span data-stu-id="acd98-122">Display Exchange Online mailbox information with PowerShell</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
  - [<span data-ttu-id="acd98-123">PowerShell で Exchange Online レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="acd98-123">Display Exchange Online reports with PowerShell</span></span>](https://technet.microsoft.com/library/4873a063-9fc4-4ed9-826a-6e935fef61d4.aspx)
    
## <a name="related-topics"></a><span data-ttu-id="acd98-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="acd98-124">Related topics</span></span>

[<span data-ttu-id="acd98-125">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="acd98-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="acd98-126">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="acd98-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="acd98-127">PowerShell を使用して SharePoint Online を管理する</span><span class="sxs-lookup"><span data-stu-id="acd98-127">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="acd98-128">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="acd98-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
