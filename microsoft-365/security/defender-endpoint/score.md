---
title: スコア メソッドとプロパティ
description: 組織の露出スコア、デバイスのセキュリティで保護されたスコア、およびデバイス グループ別の露出スコアを取得します。
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771431"
---
# <a name="score-resource-type"></a><span data-ttu-id="67d9b-104">スコア リソースの種類</span><span class="sxs-lookup"><span data-stu-id="67d9b-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67d9b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="67d9b-105">**Applies to:**</span></span>
- [<span data-ttu-id="67d9b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="67d9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="67d9b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67d9b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67d9b-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="67d9b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67d9b-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="67d9b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="67d9b-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="67d9b-110">Methods</span></span>

<span data-ttu-id="67d9b-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="67d9b-111">Method</span></span> |<span data-ttu-id="67d9b-112">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="67d9b-112">Return Type</span></span> |<span data-ttu-id="67d9b-113">説明</span><span class="sxs-lookup"><span data-stu-id="67d9b-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="67d9b-114">暴露スコアを取得する</span><span class="sxs-lookup"><span data-stu-id="67d9b-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="67d9b-115">スコア</span><span class="sxs-lookup"><span data-stu-id="67d9b-115">Score</span></span>](score.md) | <span data-ttu-id="67d9b-116">組織の露出スコアを取得します。</span><span class="sxs-lookup"><span data-stu-id="67d9b-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="67d9b-117">デバイスのセキュア スコアを取得する</span><span class="sxs-lookup"><span data-stu-id="67d9b-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="67d9b-118">スコア</span><span class="sxs-lookup"><span data-stu-id="67d9b-118">Score</span></span>](score.md) | <span data-ttu-id="67d9b-119">組織デバイスのセキュリティで保護されたスコアを取得します。</span><span class="sxs-lookup"><span data-stu-id="67d9b-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="67d9b-120">デバイス グループ別の露出スコアの一覧表示</span><span class="sxs-lookup"><span data-stu-id="67d9b-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="67d9b-121">スコア</span><span class="sxs-lookup"><span data-stu-id="67d9b-121">Score</span></span>](score.md) | <span data-ttu-id="67d9b-122">デバイス グループ別にスコアを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="67d9b-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="67d9b-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="67d9b-123">Properties</span></span>

<span data-ttu-id="67d9b-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="67d9b-124">Property</span></span> |  <span data-ttu-id="67d9b-125">種類</span><span class="sxs-lookup"><span data-stu-id="67d9b-125">Type</span></span>    |   <span data-ttu-id="67d9b-126">説明</span><span class="sxs-lookup"><span data-stu-id="67d9b-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="67d9b-127">スコア</span><span class="sxs-lookup"><span data-stu-id="67d9b-127">Score</span></span> | <span data-ttu-id="67d9b-128">Double</span><span class="sxs-lookup"><span data-stu-id="67d9b-128">Double</span></span> | <span data-ttu-id="67d9b-129">現在のスコア。</span><span class="sxs-lookup"><span data-stu-id="67d9b-129">The current score.</span></span>
<span data-ttu-id="67d9b-130">Time</span><span class="sxs-lookup"><span data-stu-id="67d9b-130">Time</span></span> | <span data-ttu-id="67d9b-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="67d9b-131">DateTime</span></span> | <span data-ttu-id="67d9b-132">この API の呼び出しが行われた日時。</span><span class="sxs-lookup"><span data-stu-id="67d9b-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="67d9b-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="67d9b-133">RbacGroupName</span></span> | <span data-ttu-id="67d9b-134">String</span><span class="sxs-lookup"><span data-stu-id="67d9b-134">String</span></span> | <span data-ttu-id="67d9b-135">デバイス グループ名。</span><span class="sxs-lookup"><span data-stu-id="67d9b-135">The device group name.</span></span>
