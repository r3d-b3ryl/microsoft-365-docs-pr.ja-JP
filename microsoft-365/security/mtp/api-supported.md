---
title: サポートされている Microsoft 365 Defender API
description: サポートされている Microsoft 365 Defender API
keywords: MTP、API、api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926200"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="dbe41-104">サポートされている Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="dbe41-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="dbe41-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dbe41-105">**Applies to:**</span></span>
- <span data-ttu-id="dbe41-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbe41-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbe41-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="dbe41-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dbe41-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="dbe41-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="dbe41-109">使用可能な API の一覧</span><span class="sxs-lookup"><span data-stu-id="dbe41-109">List of available APIs</span></span>

<span data-ttu-id="dbe41-110">記事</span><span class="sxs-lookup"><span data-stu-id="dbe41-110">Article</span></span> | <span data-ttu-id="dbe41-111">説明</span><span class="sxs-lookup"><span data-stu-id="dbe41-111">Description</span></span>
-|-
[<span data-ttu-id="dbe41-112">高度な追及 API</span><span class="sxs-lookup"><span data-stu-id="dbe41-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="dbe41-113">高度な検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbe41-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="dbe41-114">インシデント API</span><span class="sxs-lookup"><span data-stu-id="dbe41-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="dbe41-115">インシデントのリストと更新、および他の実用的なタスク。</span><span class="sxs-lookup"><span data-stu-id="dbe41-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="dbe41-116">エンドポイント URI</span><span class="sxs-lookup"><span data-stu-id="dbe41-116">Endpoint URIs</span></span>

<span data-ttu-id="dbe41-117">両方のメイン API のベース URI は次の値です https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="dbe41-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="dbe41-118">パフォーマンスを向上するには、位置情報に近いサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbe41-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="dbe41-119">米国: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dbe41-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="dbe41-120">ヨーロッパ: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dbe41-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="dbe41-121">英国: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dbe41-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="dbe41-122">トークンは、アクセスすることで取得できます https://api.security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="dbe41-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="dbe41-123">パス上のすべての API `/api` は [、OData](https://docs.microsoft.com/odata/overview) プロトコルを使用します。たとえば https://api.security.microsoft.com/api/incidents 、 .</span><span class="sxs-lookup"><span data-stu-id="dbe41-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dbe41-124">関連記事</span><span class="sxs-lookup"><span data-stu-id="dbe41-124">Related articles</span></span>

- [<span data-ttu-id="dbe41-125">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="dbe41-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="dbe41-126">Microsoft Threat Protection API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="dbe41-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="dbe41-127">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="dbe41-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="dbe41-128">エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="dbe41-128">Understand error codes</span></span>](api-error-codes.md)
