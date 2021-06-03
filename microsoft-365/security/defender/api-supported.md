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
ms.openlocfilehash: c10b2863503a5bda829cbf67379a606b687ac2e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730944"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="011ff-104">サポートされている Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="011ff-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="011ff-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="011ff-105">**Applies to:**</span></span>
- <span data-ttu-id="011ff-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="011ff-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="011ff-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="011ff-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="011ff-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="011ff-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="011ff-109">使用可能な API の一覧</span><span class="sxs-lookup"><span data-stu-id="011ff-109">List of available APIs</span></span>

<span data-ttu-id="011ff-110">記事</span><span class="sxs-lookup"><span data-stu-id="011ff-110">Article</span></span> | <span data-ttu-id="011ff-111">説明</span><span class="sxs-lookup"><span data-stu-id="011ff-111">Description</span></span>
-|-
[<span data-ttu-id="011ff-112">高度な追及 API</span><span class="sxs-lookup"><span data-stu-id="011ff-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="011ff-113">高度な検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="011ff-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="011ff-114">インシデント API</span><span class="sxs-lookup"><span data-stu-id="011ff-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="011ff-115">他の実用的なタスクと共に、インシデントを一覧表示および更新します。</span><span class="sxs-lookup"><span data-stu-id="011ff-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="011ff-116">[ストリーミング API](../defender-endpoint/raw-data-export.md) (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="011ff-116">[Streaming API](../defender-endpoint/raw-data-export.md) (Preview)</span></span> | <span data-ttu-id="011ff-117">1 つのデータ ストリームで発生するリアルタイム イベントとアラートを出荷します。</span><span class="sxs-lookup"><span data-stu-id="011ff-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="011ff-118">エンドポイント URI</span><span class="sxs-lookup"><span data-stu-id="011ff-118">Endpoint URIs</span></span>

<span data-ttu-id="011ff-119">両方のメイン API の基本 URI は次の値です https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="011ff-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="011ff-120">パフォーマンスを向上するには、位置情報に近いサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="011ff-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="011ff-121">米国: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="011ff-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="011ff-122">ヨーロッパ: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="011ff-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="011ff-123">英国: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="011ff-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="011ff-124">トークンは、アクセスすることで取得できます https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="011ff-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="011ff-125">パスに沿ったすべての `/api` API は [、OData プロトコル](/odata/overview) を使用します。たとえば、 https://api.security.microsoft.com/api/incidents です。</span><span class="sxs-lookup"><span data-stu-id="011ff-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="011ff-126">関連資料</span><span class="sxs-lookup"><span data-stu-id="011ff-126">Related articles</span></span>

- [<span data-ttu-id="011ff-127">Microsoft 365Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="011ff-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="011ff-128">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="011ff-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="011ff-129">ストリーミング API</span><span class="sxs-lookup"><span data-stu-id="011ff-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="011ff-130">API の制限とライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="011ff-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="011ff-131">エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="011ff-131">Understand error codes</span></span>](api-error-codes.md)
