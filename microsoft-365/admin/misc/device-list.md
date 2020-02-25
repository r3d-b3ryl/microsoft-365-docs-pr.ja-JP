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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: AutoPilo の CSV ファイルを Microsoft 365 Business に作成する方法について説明します。
ms.openlocfilehash: cd317bd5edaa3fdaea8a704f79a269387e8fe1c1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257354"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="3bc11-103">デバイスの一覧の CSV ファイル</span><span class="sxs-lookup"><span data-stu-id="3bc11-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="3bc11-104">デバイスの一覧 (CSV ファイル形式)</span><span class="sxs-lookup"><span data-stu-id="3bc11-104">Device list .csv file format</span></span>

<span data-ttu-id="3bc11-105">Windows Autopilot を使用してデバイスを管理および展開するには、デバイスに関する特定の情報を含む CSV ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="3bc11-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="3bc11-106">デバイスの一覧のファイルの列には、次のヘッダーが指定された順に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bc11-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="3bc11-107">列 A:デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="3bc11-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="3bc11-108">列 B: 空白のままにする</span><span class="sxs-lookup"><span data-stu-id="3bc11-108">Column B: leave blank</span></span>

- <span data-ttu-id="3bc11-109">列 C:ハードウェア ハッシュ</span><span class="sxs-lookup"><span data-stu-id="3bc11-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="3bc11-110">この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [G-et-WindowsAutoPilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使って、入手できます。</span><span class="sxs-lookup"><span data-stu-id="3bc11-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="3bc11-p101">デバイスを追加すると、プロファイルにも追加する必要があります。プロファイルは、デバイスまたはデバイスのグループに AutoPilot 展開プロファイルを適用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3bc11-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="3bc11-113">関連記事</span><span class="sxs-lookup"><span data-stu-id="3bc11-113">Related articles</span></span>

[<span data-ttu-id="3bc11-114">Microsoft 365 Business のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="3bc11-114">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="3bc11-115">Microsoft 365 Business を使い始める</span><span class="sxs-lookup"><span data-stu-id="3bc11-115">Get started with Microsoft 365 Business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="3bc11-116">Microsoft 365 Business の管理</span><span class="sxs-lookup"><span data-stu-id="3bc11-116">Manage Microsoft 365 Business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  