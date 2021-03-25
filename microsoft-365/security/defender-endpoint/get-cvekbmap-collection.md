---
title: CVE-KB マップ API の取得
description: Get CVE-KB マップ API を使用して、Microsoft Defender for Endpoint の KB および CVE の詳細に対する CVE のマップを取得する方法について説明します。
keywords: apis, graph api, サポートされている api, get, cve, kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166888"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="04896-104">CVE-KB マップ API の取得</span><span class="sxs-lookup"><span data-stu-id="04896-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04896-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="04896-105">**Applies to:**</span></span>
- [<span data-ttu-id="04896-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="04896-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="04896-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04896-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="04896-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="04896-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="04896-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="04896-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="04896-110">KB および CVE の詳細に対する CVE のマップを取得します。</span><span class="sxs-lookup"><span data-stu-id="04896-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="04896-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="04896-111">Permissions</span></span>
<span data-ttu-id="04896-112">ユーザーには読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="04896-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="04896-113">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="04896-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="04896-114">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="04896-114">Request headers</span></span>

<span data-ttu-id="04896-115">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="04896-115">Header</span></span> | <span data-ttu-id="04896-116">値</span><span class="sxs-lookup"><span data-stu-id="04896-116">Value</span></span> 
:---|:---
<span data-ttu-id="04896-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="04896-117">Authorization</span></span> | <span data-ttu-id="04896-118">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="04896-118">Bearer {token}.</span></span> <span data-ttu-id="04896-119">**必須**</span><span class="sxs-lookup"><span data-stu-id="04896-119">**Required**.</span></span>
<span data-ttu-id="04896-120">コンテンツ タイプ</span><span class="sxs-lookup"><span data-stu-id="04896-120">Content type</span></span> | <span data-ttu-id="04896-121">application/json</span><span class="sxs-lookup"><span data-stu-id="04896-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="04896-122">要求本文</span><span class="sxs-lookup"><span data-stu-id="04896-122">Request body</span></span>
<span data-ttu-id="04896-123">Empty</span><span class="sxs-lookup"><span data-stu-id="04896-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="04896-124">応答</span><span class="sxs-lookup"><span data-stu-id="04896-124">Response</span></span>
<span data-ttu-id="04896-125">成功し、マップが存在する場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="04896-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="04896-126">例</span><span class="sxs-lookup"><span data-stu-id="04896-126">Example</span></span>

<span data-ttu-id="04896-127">**要求**</span><span class="sxs-lookup"><span data-stu-id="04896-127">**Request**</span></span>

<span data-ttu-id="04896-128">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="04896-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="04896-129">**応答**</span><span class="sxs-lookup"><span data-stu-id="04896-129">**Response**</span></span>

<span data-ttu-id="04896-130">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="04896-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
