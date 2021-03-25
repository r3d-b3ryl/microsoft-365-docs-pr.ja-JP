---
title: コンピューターのセキュリティ状態コレクション API を取得する
description: Microsoft Defender for Endpoint を使用してデバイスのセキュリティ状態のコレクションを取得します。
keywords: apis, graph api, supported apis, get, device, security, state
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200367"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="ad1a1-104">Get Machines セキュリティ状態コレクション API</span><span class="sxs-lookup"><span data-stu-id="ad1a1-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ad1a1-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ad1a1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ad1a1-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ad1a1-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad1a1-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ad1a1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="ad1a1-108">デバイスのセキュリティ状態のコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad1a1-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="ad1a1-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ad1a1-109">Permissions</span></span>
<span data-ttu-id="ad1a1-110">ユーザーには読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ad1a1-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="ad1a1-111">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="ad1a1-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="ad1a1-112">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="ad1a1-112">Request headers</span></span>

<span data-ttu-id="ad1a1-113">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="ad1a1-113">Header</span></span> | <span data-ttu-id="ad1a1-114">値</span><span class="sxs-lookup"><span data-stu-id="ad1a1-114">Value</span></span> 
:---|:---
<span data-ttu-id="ad1a1-115">Authorization</span><span class="sxs-lookup"><span data-stu-id="ad1a1-115">Authorization</span></span> | <span data-ttu-id="ad1a1-116">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="ad1a1-116">Bearer {token}.</span></span> <span data-ttu-id="ad1a1-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="ad1a1-117">**Required**.</span></span>
<span data-ttu-id="ad1a1-118">コンテンツ タイプ</span><span class="sxs-lookup"><span data-stu-id="ad1a1-118">Content type</span></span> | <span data-ttu-id="ad1a1-119">application/json</span><span class="sxs-lookup"><span data-stu-id="ad1a1-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="ad1a1-120">要求本文</span><span class="sxs-lookup"><span data-stu-id="ad1a1-120">Request body</span></span>
<span data-ttu-id="ad1a1-121">Empty</span><span class="sxs-lookup"><span data-stu-id="ad1a1-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ad1a1-122">応答</span><span class="sxs-lookup"><span data-stu-id="ad1a1-122">Response</span></span>
<span data-ttu-id="ad1a1-123">成功した場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="ad1a1-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="ad1a1-124">例</span><span class="sxs-lookup"><span data-stu-id="ad1a1-124">Example</span></span>

<span data-ttu-id="ad1a1-125">**要求**</span><span class="sxs-lookup"><span data-stu-id="ad1a1-125">**Request**</span></span>

<span data-ttu-id="ad1a1-126">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="ad1a1-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="ad1a1-127">**応答**</span><span class="sxs-lookup"><span data-stu-id="ad1a1-127">**Response**</span></span>

<span data-ttu-id="ad1a1-128">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="ad1a1-128">Here is an example of the response.</span></span>
<span data-ttu-id="ad1a1-129">フィールド *ID には* デバイス ID が含まれるので、デバイス情報のフィールド *ID*\* と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="ad1a1-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
