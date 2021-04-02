---
title: Microsoft Defender ATP の高度な狩猟制限
description: 高度なハンティング サービスの応答性を維持するさまざまなサービス制限を理解する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp、検索、クエリ、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499535"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="b11f6-104">高度なハンティング サービスの制限</span><span class="sxs-lookup"><span data-stu-id="b11f6-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b11f6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b11f6-105">**Applies to:**</span></span>
- [<span data-ttu-id="b11f6-106">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b11f6-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="b11f6-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b11f6-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b11f6-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b11f6-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="b11f6-109">サービスのパフォーマンスと応答性を維持するために、高度な検索では、クエリを手動で、カスタム検出ルールによって実行するためのさまざまな [制限を設定します](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="b11f6-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="b11f6-110">これらの制限を理解するには、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b11f6-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="b11f6-111">制限</span><span class="sxs-lookup"><span data-stu-id="b11f6-111">Limit</span></span> | <span data-ttu-id="b11f6-112">Size</span><span class="sxs-lookup"><span data-stu-id="b11f6-112">Size</span></span> | <span data-ttu-id="b11f6-113">更新サイクル</span><span class="sxs-lookup"><span data-stu-id="b11f6-113">Refresh cycle</span></span> | <span data-ttu-id="b11f6-114">説明</span><span class="sxs-lookup"><span data-stu-id="b11f6-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="b11f6-115">データ範囲</span><span class="sxs-lookup"><span data-stu-id="b11f6-115">Data range</span></span> | <span data-ttu-id="b11f6-116">30 日間</span><span class="sxs-lookup"><span data-stu-id="b11f6-116">30 days</span></span> | <span data-ttu-id="b11f6-117">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="b11f6-117">Every query</span></span> | <span data-ttu-id="b11f6-118">各クエリは、過去 30 日間までのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b11f6-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="b11f6-119">結果セット</span><span class="sxs-lookup"><span data-stu-id="b11f6-119">Result set</span></span> | <span data-ttu-id="b11f6-120">10,000 行</span><span class="sxs-lookup"><span data-stu-id="b11f6-120">10,000 rows</span></span> | <span data-ttu-id="b11f6-121">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="b11f6-121">Every query</span></span> | <span data-ttu-id="b11f6-122">各クエリは、最大 10,000 レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="b11f6-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="b11f6-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="b11f6-123">Timeout</span></span> | <span data-ttu-id="b11f6-124">10 分</span><span class="sxs-lookup"><span data-stu-id="b11f6-124">10 minutes</span></span> | <span data-ttu-id="b11f6-125">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="b11f6-125">Every query</span></span> | <span data-ttu-id="b11f6-126">各クエリは最大 10 分間実行できます。</span><span class="sxs-lookup"><span data-stu-id="b11f6-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="b11f6-127">10 分以内に完了しない場合、サービスはエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="b11f6-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="b11f6-128">CPU リソース</span><span class="sxs-lookup"><span data-stu-id="b11f6-128">CPU resources</span></span> | <span data-ttu-id="b11f6-129">テナントのサイズに基づく</span><span class="sxs-lookup"><span data-stu-id="b11f6-129">Based on tenant size</span></span> | <span data-ttu-id="b11f6-130">- 1 時間に 15 分ごとに</span><span class="sxs-lookup"><span data-stu-id="b11f6-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="b11f6-131">- 毎日午前 12 時</span><span class="sxs-lookup"><span data-stu-id="b11f6-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="b11f6-132">サービスは、日次制限と 15 分の制限を個別に適用します。</span><span class="sxs-lookup"><span data-stu-id="b11f6-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="b11f6-133">制限ごとに [、クエリが](advanced-hunting-errors.md) 実行され、テナントが割り当てられたリソースの 10% 以上を消費するたびに、ポータルにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b11f6-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="b11f6-134">テナントが次の 1 日または 15 分のサイクルの後まで 100% に達した場合、クエリはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b11f6-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="b11f6-135">API を介して実行される高度な検索クエリには、個別の制限セットが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11f6-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="b11f6-136">高度な狩猟 API について読む</span><span class="sxs-lookup"><span data-stu-id="b11f6-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="b11f6-137">複数のクエリを定期的に実行しているお客様は[](advanced-hunting-best-practices.md)、消費を追跡し、最適化のベスト プラクティスを適用して、これらの制限を超えた結果の中断を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="b11f6-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b11f6-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="b11f6-138">Related topics</span></span>

- [<span data-ttu-id="b11f6-139">高度な狩猟のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="b11f6-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b11f6-140">高度なハンティング エラーの処理</span><span class="sxs-lookup"><span data-stu-id="b11f6-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="b11f6-141">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="b11f6-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b11f6-142">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="b11f6-142">Custom detections rules</span></span>](custom-detection-rules.md)
