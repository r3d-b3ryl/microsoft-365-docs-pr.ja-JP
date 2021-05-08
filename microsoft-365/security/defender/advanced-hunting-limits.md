---
title: Defender の高度な検索クォータとMicrosoft 365パラメーター
description: 高度なハンティング サービスの応答性を維持するさまざまなクォータと使用状況パラメーター (サービス制限) を理解する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果、クォータ、パラメーター、割り当て
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245602"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="b1fe3-104">高度な検索クォータと使用状況パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1fe3-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b1fe3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b1fe3-105">**Applies to:**</span></span>
- <span data-ttu-id="b1fe3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1fe3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b1fe3-107">サービスのパフォーマンスと応答性を維持するために、高度なハンティングによってさまざまなクォータと使用状況パラメーター ("サービス制限" とも呼ばれる) が設定されます。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="b1fe3-108">これらのクォータとパラメーターは、手動で実行されるクエリと、カスタム検出ルールを使用して実行されるクエリに [個別に適用されます](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="b1fe3-109">複数のクエリを定期的に実行する顧客は、これらの制限に気を付け、最適化のベスト プラクティスを [適用](advanced-hunting-best-practices.md) して中断を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="b1fe3-110">既存のクォータと使用状況パラメーターを理解するには、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="b1fe3-111">クォータまたはパラメーター</span><span class="sxs-lookup"><span data-stu-id="b1fe3-111">Quota or parameter</span></span> | <span data-ttu-id="b1fe3-112">Size</span><span class="sxs-lookup"><span data-stu-id="b1fe3-112">Size</span></span> | <span data-ttu-id="b1fe3-113">更新サイクル</span><span class="sxs-lookup"><span data-stu-id="b1fe3-113">Refresh cycle</span></span> | <span data-ttu-id="b1fe3-114">説明</span><span class="sxs-lookup"><span data-stu-id="b1fe3-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="b1fe3-115">データ範囲</span><span class="sxs-lookup"><span data-stu-id="b1fe3-115">Data range</span></span> | <span data-ttu-id="b1fe3-116">30 日間</span><span class="sxs-lookup"><span data-stu-id="b1fe3-116">30 days</span></span> | <span data-ttu-id="b1fe3-117">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="b1fe3-117">Every query</span></span> | <span data-ttu-id="b1fe3-118">各クエリは、過去 30 日間までのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="b1fe3-119">結果セット</span><span class="sxs-lookup"><span data-stu-id="b1fe3-119">Result set</span></span> | <span data-ttu-id="b1fe3-120">10,000 行</span><span class="sxs-lookup"><span data-stu-id="b1fe3-120">10,000 rows</span></span> | <span data-ttu-id="b1fe3-121">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="b1fe3-121">Every query</span></span> | <span data-ttu-id="b1fe3-122">各クエリは、最大 10,000 レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="b1fe3-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="b1fe3-123">Timeout</span></span> | <span data-ttu-id="b1fe3-124">10 分</span><span class="sxs-lookup"><span data-stu-id="b1fe3-124">10 minutes</span></span> | <span data-ttu-id="b1fe3-125">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="b1fe3-125">Every query</span></span> | <span data-ttu-id="b1fe3-126">各クエリは最大 10 分間実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="b1fe3-127">10 分以内に完了しない場合、サービスはエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="b1fe3-128">CPU リソース</span><span class="sxs-lookup"><span data-stu-id="b1fe3-128">CPU resources</span></span> | <span data-ttu-id="b1fe3-129">テナントのサイズに基づく</span><span class="sxs-lookup"><span data-stu-id="b1fe3-129">Based on tenant size</span></span> | <span data-ttu-id="b1fe3-130">15 分ごと</span><span class="sxs-lookup"><span data-stu-id="b1fe3-130">Every 15 minutes</span></span> | <span data-ttu-id="b1fe3-131">ポータル [は、クエリが実行](advanced-hunting-errors.md) され、テナントが割り当てられたリソースの 10% 以上を消費するたびにエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="b1fe3-132">テナントが次の 15 分のサイクルの後まで 100% に達した場合、クエリはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="b1fe3-133">API を介して実行される高度な検索クエリには、個別のクォータとパラメーターのセットが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="b1fe3-134">高度な狩猟 API について読む</span><span class="sxs-lookup"><span data-stu-id="b1fe3-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="b1fe3-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1fe3-135">Related topics</span></span>

- [<span data-ttu-id="b1fe3-136">高度な狩猟のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="b1fe3-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b1fe3-137">高度なハンティング エラーの処理</span><span class="sxs-lookup"><span data-stu-id="b1fe3-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="b1fe3-138">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="b1fe3-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b1fe3-139">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="b1fe3-139">Custom detections overview</span></span>](custom-detections-overview.md)