---
title: スコアのメソッドとプロパティ
description: 組織の露出スコア、デバイスのセキュリティで保護されたスコア、およびデバイス グループ別の露出スコアを取得します。
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200163"
---
# <a name="score-resource-type"></a><span data-ttu-id="edeea-104">スコア リソースの種類</span><span class="sxs-lookup"><span data-stu-id="edeea-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="edeea-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="edeea-105">**Applies to:**</span></span>
- [<span data-ttu-id="edeea-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="edeea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="edeea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="edeea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="edeea-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="edeea-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="edeea-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="edeea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="edeea-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="edeea-110">Methods</span></span>

<span data-ttu-id="edeea-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="edeea-111">Method</span></span> |<span data-ttu-id="edeea-112">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="edeea-112">Return Type</span></span> |<span data-ttu-id="edeea-113">説明</span><span class="sxs-lookup"><span data-stu-id="edeea-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="edeea-114">露出スコアの取得</span><span class="sxs-lookup"><span data-stu-id="edeea-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="edeea-115">スコア</span><span class="sxs-lookup"><span data-stu-id="edeea-115">Score</span></span>](score.md) | <span data-ttu-id="edeea-116">組織の露出スコアを取得します。</span><span class="sxs-lookup"><span data-stu-id="edeea-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="edeea-117">デバイスのセキュリティで保護されたスコアを取得する</span><span class="sxs-lookup"><span data-stu-id="edeea-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="edeea-118">スコア</span><span class="sxs-lookup"><span data-stu-id="edeea-118">Score</span></span>](score.md) | <span data-ttu-id="edeea-119">組織デバイスのセキュリティで保護されたスコアを取得します。</span><span class="sxs-lookup"><span data-stu-id="edeea-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="edeea-120">デバイス グループ別の露出スコアの一覧表示</span><span class="sxs-lookup"><span data-stu-id="edeea-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="edeea-121">スコア</span><span class="sxs-lookup"><span data-stu-id="edeea-121">Score</span></span>](score.md) | <span data-ttu-id="edeea-122">デバイス グループ別にスコアを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="edeea-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="edeea-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="edeea-123">Properties</span></span>

<span data-ttu-id="edeea-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="edeea-124">Property</span></span> |  <span data-ttu-id="edeea-125">種類</span><span class="sxs-lookup"><span data-stu-id="edeea-125">Type</span></span>    |   <span data-ttu-id="edeea-126">説明</span><span class="sxs-lookup"><span data-stu-id="edeea-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="edeea-127">スコア</span><span class="sxs-lookup"><span data-stu-id="edeea-127">Score</span></span> | <span data-ttu-id="edeea-128">Double</span><span class="sxs-lookup"><span data-stu-id="edeea-128">Double</span></span> | <span data-ttu-id="edeea-129">現在のスコア。</span><span class="sxs-lookup"><span data-stu-id="edeea-129">The current score.</span></span>
<span data-ttu-id="edeea-130">時間</span><span class="sxs-lookup"><span data-stu-id="edeea-130">Time</span></span> | <span data-ttu-id="edeea-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="edeea-131">DateTime</span></span> | <span data-ttu-id="edeea-132">この API の呼び出しが行われた日時。</span><span class="sxs-lookup"><span data-stu-id="edeea-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="edeea-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="edeea-133">RbacGroupName</span></span> | <span data-ttu-id="edeea-134">文字列</span><span class="sxs-lookup"><span data-stu-id="edeea-134">String</span></span> | <span data-ttu-id="edeea-135">デバイス グループ名。</span><span class="sxs-lookup"><span data-stu-id="edeea-135">The device group name.</span></span>
