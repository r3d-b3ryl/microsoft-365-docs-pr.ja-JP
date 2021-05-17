---
title: KB コレクション API の取得
description: Microsoft Defender for Endpoint を使用して、ナレッジ ベース (KB) と KB の詳細のコレクションを取得します。
keywords: apis, graph api, supported apis, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167176"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="beb6d-104">KB コレクション API の取得</span><span class="sxs-lookup"><span data-stu-id="beb6d-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="beb6d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="beb6d-105">**Applies to:**</span></span>
- [<span data-ttu-id="beb6d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="beb6d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="beb6d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="beb6d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="beb6d-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="beb6d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="beb6d-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="beb6d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="beb6d-110">KB と KB の詳細のコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="beb6d-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="beb6d-111">権限</span><span class="sxs-lookup"><span data-stu-id="beb6d-111">Permissions</span></span>
<span data-ttu-id="beb6d-112">ユーザーには読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="beb6d-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="beb6d-113">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="beb6d-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="beb6d-114">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="beb6d-114">Request headers</span></span>

<span data-ttu-id="beb6d-115">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="beb6d-115">Header</span></span> | <span data-ttu-id="beb6d-116">値</span><span class="sxs-lookup"><span data-stu-id="beb6d-116">Value</span></span> 
:---|:---
<span data-ttu-id="beb6d-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="beb6d-117">Authorization</span></span> | <span data-ttu-id="beb6d-118">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="beb6d-118">Bearer {token}.</span></span> <span data-ttu-id="beb6d-119">**必須**</span><span class="sxs-lookup"><span data-stu-id="beb6d-119">**Required**.</span></span>
<span data-ttu-id="beb6d-120">コンテンツ タイプ</span><span class="sxs-lookup"><span data-stu-id="beb6d-120">Content type</span></span> | <span data-ttu-id="beb6d-121">application/json</span><span class="sxs-lookup"><span data-stu-id="beb6d-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="beb6d-122">要求本文</span><span class="sxs-lookup"><span data-stu-id="beb6d-122">Request body</span></span>
<span data-ttu-id="beb6d-123">Empty</span><span class="sxs-lookup"><span data-stu-id="beb6d-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="beb6d-124">応答</span><span class="sxs-lookup"><span data-stu-id="beb6d-124">Response</span></span>
<span data-ttu-id="beb6d-125">成功した場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="beb6d-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="beb6d-126">例</span><span class="sxs-lookup"><span data-stu-id="beb6d-126">Example</span></span>

<span data-ttu-id="beb6d-127">**要求**</span><span class="sxs-lookup"><span data-stu-id="beb6d-127">**Request**</span></span>

<span data-ttu-id="beb6d-128">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="beb6d-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="beb6d-129">**応答**</span><span class="sxs-lookup"><span data-stu-id="beb6d-129">**Response**</span></span>

<span data-ttu-id="beb6d-130">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="beb6d-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
