---
title: Microsoft の脅威保護での高度な検索の制限
description: 高度な検索サービスの応答性を維持するさまざまなサービス制限を理解する
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aaba01f5970c9abf55f5fae760d1ba1fed8ba914
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199879"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="1d2ba-104">高度な検索サービスの制限</span><span class="sxs-lookup"><span data-stu-id="1d2ba-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1d2ba-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1d2ba-105">**Applies to:**</span></span>
- <span data-ttu-id="1d2ba-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1d2ba-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1d2ba-107">サービスのパフォーマンスと応答性を向上させるために、高度な検索は、クエリのさまざまな制限を手動で実行し、 [カスタムの検出ルール](custom-detection-rules.md)を設定します。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="1d2ba-108">これらの制限事項については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="1d2ba-109">極限</span><span class="sxs-lookup"><span data-stu-id="1d2ba-109">Limit</span></span> | <span data-ttu-id="1d2ba-110">Size</span><span class="sxs-lookup"><span data-stu-id="1d2ba-110">Size</span></span> | <span data-ttu-id="1d2ba-111">更新サイクル</span><span class="sxs-lookup"><span data-stu-id="1d2ba-111">Refresh cycle</span></span> | <span data-ttu-id="1d2ba-112">説明</span><span class="sxs-lookup"><span data-stu-id="1d2ba-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="1d2ba-113">データ範囲</span><span class="sxs-lookup"><span data-stu-id="1d2ba-113">Data range</span></span> | <span data-ttu-id="1d2ba-114">30 日間</span><span class="sxs-lookup"><span data-stu-id="1d2ba-114">30 days</span></span> | <span data-ttu-id="1d2ba-115">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="1d2ba-115">Every query</span></span> | <span data-ttu-id="1d2ba-116">各クエリは、過去30日間のデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="1d2ba-117">結果セット</span><span class="sxs-lookup"><span data-stu-id="1d2ba-117">Result set</span></span> | <span data-ttu-id="1d2ba-118">1万行</span><span class="sxs-lookup"><span data-stu-id="1d2ba-118">10,000 rows</span></span> | <span data-ttu-id="1d2ba-119">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="1d2ba-119">Every query</span></span> | <span data-ttu-id="1d2ba-120">各クエリは最大1万レコードを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="1d2ba-121">Timeout</span><span class="sxs-lookup"><span data-stu-id="1d2ba-121">Timeout</span></span> | <span data-ttu-id="1d2ba-122">10 分</span><span class="sxs-lookup"><span data-stu-id="1d2ba-122">10 minutes</span></span> | <span data-ttu-id="1d2ba-123">すべてのクエリ</span><span class="sxs-lookup"><span data-stu-id="1d2ba-123">Every query</span></span> | <span data-ttu-id="1d2ba-124">各クエリは、最大10分間実行できます。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="1d2ba-125">10分以内に完了しない場合、サービスはエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="1d2ba-126">CPU リソース</span><span class="sxs-lookup"><span data-stu-id="1d2ba-126">CPU resources</span></span> | <span data-ttu-id="1d2ba-127">テナントのサイズに基づく</span><span class="sxs-lookup"><span data-stu-id="1d2ba-127">Based on tenant size</span></span> | <span data-ttu-id="1d2ba-128">-毎時、15分ごと</span><span class="sxs-lookup"><span data-stu-id="1d2ba-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="1d2ba-129">-毎日午前12時</span><span class="sxs-lookup"><span data-stu-id="1d2ba-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="1d2ba-130">サービスによって、毎日および15分の制限が個別に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="1d2ba-131">各制限について、クエリが実行され、テナントが割り当てられたリソースの10% を超えた場合に、 [ポータルにエラーが表示され](advanced-hunting-errors.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="1d2ba-132">テナントが次の毎日または15分のサイクルの後に100% に達した場合、クエリはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="1d2ba-133">別の制限のセットは、API で実行される高度な検索クエリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="1d2ba-134">高度な検索 Api について確認する</span><span class="sxs-lookup"><span data-stu-id="1d2ba-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="1d2ba-135">複数のクエリを定期的に実行する場合は、使用量を追跡し、 [最適化のベストプラクティスを適用](advanced-hunting-best-practices.md) して、これらの制限を超えたことによる影響を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="1d2ba-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d2ba-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d2ba-136">Related topics</span></span>

- [<span data-ttu-id="1d2ba-137">高度な検索のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="1d2ba-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1d2ba-138">詳細な検索エラーを処理する</span><span class="sxs-lookup"><span data-stu-id="1d2ba-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="1d2ba-139">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="1d2ba-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1d2ba-140">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="1d2ba-140">Custom detections overview</span></span>](custom-detections-overview.md)
