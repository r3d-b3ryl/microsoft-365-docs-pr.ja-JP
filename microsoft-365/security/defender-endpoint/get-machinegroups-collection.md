---
title: RBAC マシン グループ コレクション API の取得
description: Get KB コレクション API を使用して、Microsoft Defender for Endpoint の RBAC デバイス グループのコレクションを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, RBAC, group
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
ms.date: 10/07/2018
ms.openlocfilehash: 18566025d79f02281c1d2c1509dd98f1e57879c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932777"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="7b1b3-104">KB コレクション API の取得</span><span class="sxs-lookup"><span data-stu-id="7b1b3-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7b1b3-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7b1b3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="7b1b3-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="7b1b3-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7b1b3-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="7b1b3-108">RBAC デバイス グループのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="7b1b3-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7b1b3-109">Permissions</span></span>
<span data-ttu-id="7b1b3-110">ユーザーには読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="7b1b3-111">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="7b1b3-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="7b1b3-112">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="7b1b3-112">Request headers</span></span>

<span data-ttu-id="7b1b3-113">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="7b1b3-113">Header</span></span> | <span data-ttu-id="7b1b3-114">値</span><span class="sxs-lookup"><span data-stu-id="7b1b3-114">Value</span></span> 
:---|:---
<span data-ttu-id="7b1b3-115">Authorization</span><span class="sxs-lookup"><span data-stu-id="7b1b3-115">Authorization</span></span> | <span data-ttu-id="7b1b3-116">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-116">Bearer {token}.</span></span> <span data-ttu-id="7b1b3-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="7b1b3-117">**Required**.</span></span>
<span data-ttu-id="7b1b3-118">コンテンツ タイプ</span><span class="sxs-lookup"><span data-stu-id="7b1b3-118">Content type</span></span> | <span data-ttu-id="7b1b3-119">application/json</span><span class="sxs-lookup"><span data-stu-id="7b1b3-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="7b1b3-120">要求本文</span><span class="sxs-lookup"><span data-stu-id="7b1b3-120">Request body</span></span>
<span data-ttu-id="7b1b3-121">Empty</span><span class="sxs-lookup"><span data-stu-id="7b1b3-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7b1b3-122">応答</span><span class="sxs-lookup"><span data-stu-id="7b1b3-122">Response</span></span>
<span data-ttu-id="7b1b3-123">成功した場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="7b1b3-124">例</span><span class="sxs-lookup"><span data-stu-id="7b1b3-124">Example</span></span>

<span data-ttu-id="7b1b3-125">**要求**</span><span class="sxs-lookup"><span data-stu-id="7b1b3-125">**Request**</span></span>

<span data-ttu-id="7b1b3-126">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="7b1b3-127">**応答**</span><span class="sxs-lookup"><span data-stu-id="7b1b3-127">**Response**</span></span>

<span data-ttu-id="7b1b3-128">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-128">Here is an example of the response.</span></span>
<span data-ttu-id="7b1b3-129">フィールド ID には、デバイス グループ **ID とデバイス** 情報の **フィールド rbacGroupId** が含まれる。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="7b1b3-130">グループ **化されていないフィールドは** 、グループに割り当てられていないすべてのデバイスに対して 1 つのグループに対してだけ true です。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="7b1b3-131">通常どおり、このグループの名前は "UnassignedGroup" です。</span><span class="sxs-lookup"><span data-stu-id="7b1b3-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
