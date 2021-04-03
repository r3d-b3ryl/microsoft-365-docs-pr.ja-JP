---
title: デバイス値の割り当て - 脅威と脆弱性の管理
description: 低、通常、または高い値をデバイスに割り当て、資産の優先順位を区別する方法について学習します。
keywords: microsoft Defender atp デバイスの値、脅威と脆弱性管理デバイスの値、価値の高いデバイス、デバイス値の露出スコア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3cecee8b80f179f67cb48f62e1d9238a51825bfd
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500214"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="8fa0d-104">デバイス値の割り当て - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="8fa0d-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8fa0d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8fa0d-105">**Applies to:**</span></span>

- [<span data-ttu-id="8fa0d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8fa0d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8fa0d-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="8fa0d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8fa0d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fa0d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8fa0d-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8fa0d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8fa0d-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8fa0d-111">デバイスの値を定義すると、資産の優先順位を区別できます。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="8fa0d-112">デバイスの値は、個々の資産のリスクアペタイトを脅威と脆弱性管理の露出スコアの計算に組み込むのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="8fa0d-113">"高い値" として割り当てられたデバイスは、より多くの重みを受け取る。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="8fa0d-114">デバイス値の設定 [API を使用することもできます](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="8fa0d-115">デバイス値のオプション:</span><span class="sxs-lookup"><span data-stu-id="8fa0d-115">Device value options:</span></span>

- <span data-ttu-id="8fa0d-116">低</span><span class="sxs-lookup"><span data-stu-id="8fa0d-116">Low</span></span>
- <span data-ttu-id="8fa0d-117">標準 (既定値)</span><span class="sxs-lookup"><span data-stu-id="8fa0d-117">Normal (Default)</span></span>
- <span data-ttu-id="8fa0d-118">高</span><span class="sxs-lookup"><span data-stu-id="8fa0d-118">High</span></span>

<span data-ttu-id="8fa0d-119">高い値を割り当てる必要があるデバイスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="8fa0d-120">ドメイン コントローラー、Active Directory</span><span class="sxs-lookup"><span data-stu-id="8fa0d-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="8fa0d-121">インターネットに接続するデバイス</span><span class="sxs-lookup"><span data-stu-id="8fa0d-121">Internet facing devices</span></span>
- <span data-ttu-id="8fa0d-122">VIP デバイス</span><span class="sxs-lookup"><span data-stu-id="8fa0d-122">VIP devices</span></span>
- <span data-ttu-id="8fa0d-123">内部/外部の実稼働サービスをホストするデバイス</span><span class="sxs-lookup"><span data-stu-id="8fa0d-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="8fa0d-124">デバイスの値を選択する</span><span class="sxs-lookup"><span data-stu-id="8fa0d-124">Choose device value</span></span>

1. <span data-ttu-id="8fa0d-125">任意のデバイス ページに移動し、最も簡単な場所はデバイス インベントリから行います。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="8fa0d-126">ページ **の上部にある** アクション バーの横にある 3 つのドットから [デバイス値] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![デバイス値ドロップダウンの例。](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="8fa0d-128">現在のデバイス値とそれが何を意味するフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="8fa0d-129">デバイスの値を確認し、デバイスに最適な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="8fa0d-130">![デバイス値のフライアウトの例。](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="8fa0d-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="8fa0d-131">デバイスの値が露出スコアに与える影響</span><span class="sxs-lookup"><span data-stu-id="8fa0d-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="8fa0d-132">露出スコアは、すべてのデバイスの加重平均です。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="8fa0d-133">デバイス グループがある場合は、デバイス グループ別にスコアをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="8fa0d-134">通常のデバイスの重み 1</span><span class="sxs-lookup"><span data-stu-id="8fa0d-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="8fa0d-135">低い値のデバイスの重み 0.75</span><span class="sxs-lookup"><span data-stu-id="8fa0d-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="8fa0d-136">高い値のデバイスには、NumberOfAssets / 10 の重みがあります。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="8fa0d-137">デバイスが 100 台の場合、各高価値デバイスの重みは 10 (100/10) になります。</span><span class="sxs-lookup"><span data-stu-id="8fa0d-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="8fa0d-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fa0d-138">Related topics</span></span>

- [<span data-ttu-id="8fa0d-139">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="8fa0d-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="8fa0d-140">露出スコア</span><span class="sxs-lookup"><span data-stu-id="8fa0d-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="8fa0d-141">API</span><span class="sxs-lookup"><span data-stu-id="8fa0d-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)