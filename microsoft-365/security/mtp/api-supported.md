---
title: サポートされている Microsoft 365 Defender Api
description: サポートされている Microsoft 365 Defender Api
keywords: MTP、Api、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844962"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="77b28-104">サポートされている Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="77b28-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="77b28-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="77b28-105">**Applies to:**</span></span>
- <span data-ttu-id="77b28-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77b28-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="77b28-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="77b28-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="77b28-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="77b28-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="77b28-109">エンドポイント Uri:</span><span class="sxs-lookup"><span data-stu-id="77b28-109">End Point URIs:</span></span>

- <span data-ttu-id="77b28-110">サービスベース URI は次のとおりです。 https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77b28-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="77b28-111">パフォーマンスを向上させるには、次のようにサーバーを地域の場所に近づけることができます。</span><span class="sxs-lookup"><span data-stu-id="77b28-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="77b28-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77b28-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="77b28-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77b28-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="77b28-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77b28-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="77b28-115">トークンを取得するためのリソースは次のようになります。 https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77b28-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="77b28-116">Path の下にあるすべての Api ```/api``` は OData api です。</span><span class="sxs-lookup"><span data-stu-id="77b28-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="77b28-117">(. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="77b28-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="77b28-118">利用可能な Api のリスト:</span><span class="sxs-lookup"><span data-stu-id="77b28-118">List of available APIs:</span></span>

<span data-ttu-id="77b28-119">トピック</span><span class="sxs-lookup"><span data-stu-id="77b28-119">Topic</span></span> | <span data-ttu-id="77b28-120">説明</span><span class="sxs-lookup"><span data-stu-id="77b28-120">Description</span></span>
:---|:---
[<span data-ttu-id="77b28-121">高度な追及 API</span><span class="sxs-lookup"><span data-stu-id="77b28-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="77b28-122">API から高度な検索クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="77b28-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="77b28-123">インシデント API</span><span class="sxs-lookup"><span data-stu-id="77b28-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="77b28-124">インシデント関連の API 呼び出しを実行します。インシデントの一覧表示、インシデントの更新など。</span><span class="sxs-lookup"><span data-stu-id="77b28-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
