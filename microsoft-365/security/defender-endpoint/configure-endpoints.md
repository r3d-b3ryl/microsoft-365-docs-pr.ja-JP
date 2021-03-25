---
title: Windows 10 デバイスのオンボード ツールと各種方法
description: センサー データを Microsoft Defender ATP センサーに送信できるよう、Windows 10 デバイスをオンボードする
keywords: オンボード Windows 10 デバイス、グループ ポリシー、エンドポイント構成マネージャー、モバイル デバイス管理、ローカル スクリプト、gp、sccm、mdm、intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165539"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="bc5d3-104">Windows 10 デバイスのオンボード ツールと各種方法</span><span class="sxs-lookup"><span data-stu-id="bc5d3-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc5d3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bc5d3-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc5d3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bc5d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc5d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc5d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="bc5d3-108">Microsoft 365 Endpoint データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="bc5d3-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="bc5d3-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bc5d3-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bc5d3-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="bc5d3-111">Defender for Endpoint サービスがセンサー データを取得できるよう、組織内のデバイスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="bc5d3-112">組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="bc5d3-113">次の展開ツールとメソッドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="bc5d3-114">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="bc5d3-114">Group Policy</span></span>
- <span data-ttu-id="bc5d3-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bc5d3-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="bc5d3-116">モバイル デバイスの管理 (Microsoft Intune を含む)</span><span class="sxs-lookup"><span data-stu-id="bc5d3-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="bc5d3-117">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="bc5d3-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bc5d3-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bc5d3-118">In this section</span></span>
<span data-ttu-id="bc5d3-119">トピック</span><span class="sxs-lookup"><span data-stu-id="bc5d3-119">Topic</span></span> | <span data-ttu-id="bc5d3-120">説明</span><span class="sxs-lookup"><span data-stu-id="bc5d3-120">Description</span></span>
:---|:---
[<span data-ttu-id="bc5d3-121">グループ ポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc5d3-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="bc5d3-122">グループ ポリシーを使用して、構成パッケージをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="bc5d3-123">Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc5d3-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="bc5d3-124">デバイスに構成パッケージを展開するには、Microsoft Endpoint Manager (現在のブランチ) バージョン 1606 または Microsoft Endpoint Manager (現在のブランチ) バージョン 1602 以前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="bc5d3-125">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc5d3-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="bc5d3-126">デバイスに構成パッケージを展開するには、モバイル デバイス管理ツールまたは Microsoft Intune を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="bc5d3-127">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc5d3-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="bc5d3-128">ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="bc5d3-129">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc5d3-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="bc5d3-130">構成パッケージを使用して VDI デバイスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="bc5d3-131">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bc5d3-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bc5d3-132">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="bc5d3-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
