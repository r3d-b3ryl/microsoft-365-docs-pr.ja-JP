---
title: サポートされている Microsoft 365 Defender API
description: サポートされている Microsoft 365 Defender API
keywords: Microsoft 365Defender、API、API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935727"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="5f3c4-104">サポートされている Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="5f3c4-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5f3c4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5f3c4-105">**Applies to:**</span></span>
- <span data-ttu-id="5f3c4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f3c4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f3c4-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="5f3c4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5f3c4-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="5f3c4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="5f3c4-109">使用可能な API の一覧</span><span class="sxs-lookup"><span data-stu-id="5f3c4-109">List of available APIs</span></span>

<span data-ttu-id="5f3c4-110">記事</span><span class="sxs-lookup"><span data-stu-id="5f3c4-110">Article</span></span> | <span data-ttu-id="5f3c4-111">説明</span><span class="sxs-lookup"><span data-stu-id="5f3c4-111">Description</span></span>
-|-
[<span data-ttu-id="5f3c4-112">高度な追及 API</span><span class="sxs-lookup"><span data-stu-id="5f3c4-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="5f3c4-113">高度な検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f3c4-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="5f3c4-114">インシデント API</span><span class="sxs-lookup"><span data-stu-id="5f3c4-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="5f3c4-115">他の実用的なタスクと共に、インシデントを一覧表示および更新します。</span><span class="sxs-lookup"><span data-stu-id="5f3c4-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="5f3c4-116">エンドポイント URI</span><span class="sxs-lookup"><span data-stu-id="5f3c4-116">Endpoint URIs</span></span>

<span data-ttu-id="5f3c4-117">両方のメイン API の基本 URI は次の値です https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="5f3c4-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="5f3c4-118">パフォーマンスを向上するには、位置情報に近いサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f3c4-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="5f3c4-119">米国: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5f3c4-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="5f3c4-120">ヨーロッパ: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5f3c4-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="5f3c4-121">英国: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5f3c4-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="5f3c4-122">トークンは、アクセスすることで取得できます https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="5f3c4-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="5f3c4-123">パスに沿ったすべての `/api` API は [、OData プロトコル](/odata/overview) を使用します。たとえば、 https://api.security.microsoft.com/api/incidents です。</span><span class="sxs-lookup"><span data-stu-id="5f3c4-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5f3c4-124">関連記事</span><span class="sxs-lookup"><span data-stu-id="5f3c4-124">Related articles</span></span>

- [<span data-ttu-id="5f3c4-125">Microsoft 365Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="5f3c4-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="5f3c4-126">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="5f3c4-126">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="5f3c4-127">API の制限とライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="5f3c4-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="5f3c4-128">エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="5f3c4-128">Understand error codes</span></span>](api-error-codes.md)