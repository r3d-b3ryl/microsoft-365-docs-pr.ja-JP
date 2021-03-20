---
title: デバイスの一覧の CSV ファイル
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Microsoft 365 for business で AutoPilot 用の CSV ファイルを作成する方法について説明します。
ms.openlocfilehash: 78a9012bac054329bdb87b02757f49f30dd44f65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914740"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="8c037-103">デバイスの一覧の CSV ファイル</span><span class="sxs-lookup"><span data-stu-id="8c037-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="8c037-104">デバイスの一覧 (CSV ファイル形式)</span><span class="sxs-lookup"><span data-stu-id="8c037-104">Device list .csv file format</span></span>

<span data-ttu-id="8c037-105">Windows Autopilot を使用してデバイスを管理および展開するには、デバイスに関する特定の情報を含む CSV ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="8c037-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="8c037-106">デバイスの一覧のファイルの列には、次のヘッダーが指定された順に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c037-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="8c037-107">列 A:デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="8c037-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="8c037-108">列 B: 空白のままにする</span><span class="sxs-lookup"><span data-stu-id="8c037-108">Column B: leave blank</span></span>

- <span data-ttu-id="8c037-109">列 C:ハードウェア ハッシュ</span><span class="sxs-lookup"><span data-stu-id="8c037-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="8c037-110">この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。</span><span class="sxs-lookup"><span data-stu-id="8c037-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="8c037-p101">デバイスを追加すると、プロファイルにも追加する必要があります。プロファイルは、デバイスまたはデバイスのグループに AutoPilot 展開プロファイルを適用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c037-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="8c037-113">関連記事</span><span class="sxs-lookup"><span data-stu-id="8c037-113">Related articles</span></span>

[<span data-ttu-id="8c037-114">Microsoft 365 for business のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="8c037-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="8c037-115">Microsoft 365 for business の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="8c037-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="8c037-116">ビジネス向け Microsoft 365 の管理</span><span class="sxs-lookup"><span data-stu-id="8c037-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
