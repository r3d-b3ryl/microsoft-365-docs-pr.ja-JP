---
title: 特定の PDL を使用して Microsoft 365 グループを作成する
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: 複数地域環境で指定された優先データの場所を持つ Microsoft 365 グループを作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f02a5eb6d8b30e8381c65d4735812675d35af2b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923746"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a><span data-ttu-id="bb741-103">特定の PDL を使用して Microsoft 365 グループを作成する</span><span class="sxs-lookup"><span data-stu-id="bb741-103">Create a Microsoft 365 Group with a specific PDL</span></span>

<span data-ttu-id="bb741-104">複数地域環境のユーザーが Microsoft 365 グループを作成すると、グループ優先データの場所はユーザーの優先データの場所に自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb741-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="bb741-105">グローバル管理者、SharePoint 管理者、Exchange 管理者は、選択した任意の地域にグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb741-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="bb741-106">特定の PDL でグループを作成する必要がある場合は、SharePoint 管理センターから、または Exchange Online New-unifiedgroup Microsoft PowerShell コマンドレットを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb741-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="bb741-107">これを実行すると、グループ メールボックスとグループに関連付けられている SharePoint サイトは両方とも、指定した PDL でプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="bb741-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="bb741-108">指定した PDL を使用して Microsoft 365 グループを作成するには、グループ サイトを作成する地域の場所にある SharePoint 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="bb741-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="bb741-109">例:</span><span class="sxs-lookup"><span data-stu-id="bb741-109">For example:</span></span>

<span data-ttu-id="bb741-110">オーストラリアの場所でグループ サイトを作成する場合は、https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement に移動します</span><span class="sxs-lookup"><span data-stu-id="bb741-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="bb741-111">**[+ 作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb741-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="bb741-112">プロセスに従って、グループ サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb741-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="bb741-113">グループ サイトは、サイト作成要求を開始した SharePoint 管理センターに対応する地域の場所にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="bb741-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="bb741-114">Exchange PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="bb741-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="bb741-115">Exchange Online PowerShell に接続して、パラメーター *-MailBoxRegion* を地域の場所コードとともに渡します。</span><span class="sxs-lookup"><span data-stu-id="bb741-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="bb741-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bb741-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![構文を使用した New-UnifiedGroup PowerShell コマンドレットのスクリーンショット](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="bb741-118">SharePoint グループのサイト プロビジョニングがオンデマンドであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bb741-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="bb741-119">サイトは、グループの所有者またはメンバーが初めてアクセスを試みたときにプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="bb741-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="bb741-120">地域の場所コード</span><span class="sxs-lookup"><span data-stu-id="bb741-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="bb741-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb741-121">Related topics</span></span>

[<span data-ttu-id="bb741-122">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="bb741-122">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)