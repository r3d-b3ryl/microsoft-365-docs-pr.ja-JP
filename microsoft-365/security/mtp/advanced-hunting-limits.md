---
title: Microsoft 365 Defender の高度な検索クォータと使用パラメーター
description: 高度な検索サービスの応答性を維持するさまざまなクォータと使用パラメーター (サービス制限) を理解する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果、クォータ、パラメーター、割り当て
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929792"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="836ea-104">高度な検索クォータと使用パラメーター</span><span class="sxs-lookup"><span data-stu-id="836ea-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="836ea-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="836ea-105">**Applies to:**</span></span>
- <span data-ttu-id="836ea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="836ea-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="836ea-107">サービスのパフォーマンスと応答性を維持するために、高度な検索では、さまざまなクォータと使用パラメーター ("サービス制限" とも呼ばれる) が設定されます。</span><span class="sxs-lookup"><span data-stu-id="836ea-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="836ea-108">これらのクォータとパラメーターは、クエリが手動で実行され、カスタム検出ルール [によって実行される場合に適用されます](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="836ea-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="836ea-109">複数のクエリを定期的に実行する顧客は、[](advanced-hunting-best-practices.md)消費を追跡し、最適化のベスト プラクティスを適用して、中断を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="836ea-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="836ea-110">既存のクォータと使用パラメーターを理解するには、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="836ea-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="836ea-111">クォータまたはパラメーター</span><span class="sxs-lookup"><span data-stu-id="836ea-111">Quota or parameter</span></span> | <span data-ttu-id="836ea-112">Size</span><span class="sxs-lookup"><span data-stu-id="836ea-112">Size</span></span> | <span data-ttu-id="836ea-113">更新サイクル</span><span class="sxs-lookup"><span data-stu-id="836ea-113">Refresh cycle</span></span> | <span data-ttu-id="836ea-114">説明</span><span class="sxs-lookup"><span data-stu-id="836ea-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="836ea-115">データ範囲</span><span class="sxs-lookup"><span data-stu-id="836ea-115">Data range</span></span> | <span data-ttu-id="836ea-116">30 日間</span><span class="sxs-lookup"><span data-stu-id="836ea-116">30 days</span></span> | <span data-ttu-id="836ea-117">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="836ea-117">Every query</span></span> | <span data-ttu-id="836ea-118">各クエリは、最大 30 日間のデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="836ea-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="836ea-119">結果セット</span><span class="sxs-lookup"><span data-stu-id="836ea-119">Result set</span></span> | <span data-ttu-id="836ea-120">10,000 行</span><span class="sxs-lookup"><span data-stu-id="836ea-120">10,000 rows</span></span> | <span data-ttu-id="836ea-121">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="836ea-121">Every query</span></span> | <span data-ttu-id="836ea-122">各クエリは最大 10,000 レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="836ea-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="836ea-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="836ea-123">Timeout</span></span> | <span data-ttu-id="836ea-124">10 分</span><span class="sxs-lookup"><span data-stu-id="836ea-124">10 minutes</span></span> | <span data-ttu-id="836ea-125">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="836ea-125">Every query</span></span> | <span data-ttu-id="836ea-126">各クエリは最大 10 分間実行できます。</span><span class="sxs-lookup"><span data-stu-id="836ea-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="836ea-127">10 分以内に完了しない場合、サービスはエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="836ea-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="836ea-128">CPU リソース</span><span class="sxs-lookup"><span data-stu-id="836ea-128">CPU resources</span></span> | <span data-ttu-id="836ea-129">テナントサイズに基づく</span><span class="sxs-lookup"><span data-stu-id="836ea-129">Based on tenant size</span></span> | <span data-ttu-id="836ea-130">- 1 時間後 15 分ごとに</span><span class="sxs-lookup"><span data-stu-id="836ea-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="836ea-131">- 毎日午前 0 時 12 分</span><span class="sxs-lookup"><span data-stu-id="836ea-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="836ea-132">サービスは、日次クォータと 15 分のクォータを個別に適用します。</span><span class="sxs-lookup"><span data-stu-id="836ea-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="836ea-133">クォータごとに、クエリが[](advanced-hunting-errors.md)実行され、テナントが割り当てられたリソースの 10% 以上を消費するたびに、ポータルにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="836ea-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="836ea-134">テナントが 1 日または 15 分のサイクル後まで 100% に達した場合、クエリはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="836ea-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="836ea-135">別のクォータとパラメーターのセットは、API を介して実行される高度な検索クエリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="836ea-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="836ea-136">高度なハンティング API について読む</span><span class="sxs-lookup"><span data-stu-id="836ea-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="836ea-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="836ea-137">Related topics</span></span>

- [<span data-ttu-id="836ea-138">高度な検索のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="836ea-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="836ea-139">高度なハンティング エラーの処理</span><span class="sxs-lookup"><span data-stu-id="836ea-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="836ea-140">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="836ea-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="836ea-141">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="836ea-141">Custom detections overview</span></span>](custom-detections-overview.md)