---
title: Microsoft 365 Defender の高度な検索クォータと使用法のパラメーター
description: 高度な検索サービスの応答性を維持するさまざまなクォータおよび使用法のパラメーター (サービス制限) について理解します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果、クォータ、パラメーター、割り当て
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847370"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="dd21f-104">高度な検索クォータと使用法のパラメーター</span><span class="sxs-lookup"><span data-stu-id="dd21f-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dd21f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dd21f-105">**Applies to:**</span></span>
- <span data-ttu-id="dd21f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd21f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="dd21f-107">サービスのパフォーマンスと応答性を向上させるために、高度な検索はさまざまなクォータと使用状況パラメーター ("サービス制限" とも呼ばれます) を設定します。</span><span class="sxs-lookup"><span data-stu-id="dd21f-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="dd21f-108">これらのクォータとパラメーターは、手動で実行されるクエリ、および [カスタムの検出ルール](custom-detection-rules.md)に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dd21f-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="dd21f-109">複数のクエリを定期的に実行する場合は、使用量を追跡し、 [最適化のベストプラクティスを適用](advanced-hunting-best-practices.md) して、中断を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd21f-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="dd21f-110">既存のクォータと使用法のパラメーターについては、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd21f-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="dd21f-111">Quota または parameter</span><span class="sxs-lookup"><span data-stu-id="dd21f-111">Quota or parameter</span></span> | <span data-ttu-id="dd21f-112">Size</span><span class="sxs-lookup"><span data-stu-id="dd21f-112">Size</span></span> | <span data-ttu-id="dd21f-113">更新サイクル</span><span class="sxs-lookup"><span data-stu-id="dd21f-113">Refresh cycle</span></span> | <span data-ttu-id="dd21f-114">説明</span><span class="sxs-lookup"><span data-stu-id="dd21f-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="dd21f-115">データ範囲</span><span class="sxs-lookup"><span data-stu-id="dd21f-115">Data range</span></span> | <span data-ttu-id="dd21f-116">30 日間</span><span class="sxs-lookup"><span data-stu-id="dd21f-116">30 days</span></span> | <span data-ttu-id="dd21f-117">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="dd21f-117">Every query</span></span> | <span data-ttu-id="dd21f-118">各クエリは、過去30日間のデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="dd21f-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="dd21f-119">結果セット</span><span class="sxs-lookup"><span data-stu-id="dd21f-119">Result set</span></span> | <span data-ttu-id="dd21f-120">1万行</span><span class="sxs-lookup"><span data-stu-id="dd21f-120">10,000 rows</span></span> | <span data-ttu-id="dd21f-121">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="dd21f-121">Every query</span></span> | <span data-ttu-id="dd21f-122">各クエリは最大1万レコードを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="dd21f-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="dd21f-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="dd21f-123">Timeout</span></span> | <span data-ttu-id="dd21f-124">10 分</span><span class="sxs-lookup"><span data-stu-id="dd21f-124">10 minutes</span></span> | <span data-ttu-id="dd21f-125">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="dd21f-125">Every query</span></span> | <span data-ttu-id="dd21f-126">各クエリは、最大10分間実行できます。</span><span class="sxs-lookup"><span data-stu-id="dd21f-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="dd21f-127">10分以内に完了しない場合、サービスはエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="dd21f-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="dd21f-128">CPU リソース</span><span class="sxs-lookup"><span data-stu-id="dd21f-128">CPU resources</span></span> | <span data-ttu-id="dd21f-129">テナントのサイズに基づく</span><span class="sxs-lookup"><span data-stu-id="dd21f-129">Based on tenant size</span></span> | <span data-ttu-id="dd21f-130">-毎時、15分ごと</span><span class="sxs-lookup"><span data-stu-id="dd21f-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="dd21f-131">-毎日午前12時</span><span class="sxs-lookup"><span data-stu-id="dd21f-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="dd21f-132">サービスは、毎日および15分のクォータを個別に適用します。</span><span class="sxs-lookup"><span data-stu-id="dd21f-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="dd21f-133">クォータごとに、クエリが実行され、テナントが割り当てられたリソースの10% 以上を消費した場合は常に [エラーが表示され](advanced-hunting-errors.md) ます。</span><span class="sxs-lookup"><span data-stu-id="dd21f-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="dd21f-134">テナントが次の毎日または15分のサイクルの後に100% に達した場合、クエリはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="dd21f-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="dd21f-135">クォータとパラメーターの別のセットは、API を通じて実行される高度な検索クエリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="dd21f-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="dd21f-136">高度な検索 Api について確認する</span><span class="sxs-lookup"><span data-stu-id="dd21f-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="dd21f-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd21f-137">Related topics</span></span>

- [<span data-ttu-id="dd21f-138">高度な検索のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="dd21f-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="dd21f-139">詳細な検索エラーを処理する</span><span class="sxs-lookup"><span data-stu-id="dd21f-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="dd21f-140">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="dd21f-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dd21f-141">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="dd21f-141">Custom detections overview</span></span>](custom-detections-overview.md)