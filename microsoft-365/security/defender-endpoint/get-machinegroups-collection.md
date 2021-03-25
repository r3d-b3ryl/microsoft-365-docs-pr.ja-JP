---
title: RBAC マシン グループ コレクション API の取得
description: Get KB コレクション API を使用して、Microsoft Defender Advanced Threat Protection の RBAC デバイス グループのコレクションを取得する方法について説明します。
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
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167020"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="82458-104">KB コレクション API の取得</span><span class="sxs-lookup"><span data-stu-id="82458-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="82458-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="82458-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="82458-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="82458-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="82458-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="82458-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="82458-108">RBAC デバイス グループのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="82458-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="82458-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="82458-109">Permissions</span></span>
<span data-ttu-id="82458-110">ユーザーには読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="82458-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="82458-111">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="82458-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="82458-112">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="82458-112">Request headers</span></span>

<span data-ttu-id="82458-113">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="82458-113">Header</span></span> | <span data-ttu-id="82458-114">値</span><span class="sxs-lookup"><span data-stu-id="82458-114">Value</span></span> 
:---|:---
<span data-ttu-id="82458-115">Authorization</span><span class="sxs-lookup"><span data-stu-id="82458-115">Authorization</span></span> | <span data-ttu-id="82458-116">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="82458-116">Bearer {token}.</span></span> <span data-ttu-id="82458-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="82458-117">**Required**.</span></span>
<span data-ttu-id="82458-118">コンテンツ タイプ</span><span class="sxs-lookup"><span data-stu-id="82458-118">Content type</span></span> | <span data-ttu-id="82458-119">application/json</span><span class="sxs-lookup"><span data-stu-id="82458-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="82458-120">要求本文</span><span class="sxs-lookup"><span data-stu-id="82458-120">Request body</span></span>
<span data-ttu-id="82458-121">Empty</span><span class="sxs-lookup"><span data-stu-id="82458-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="82458-122">応答</span><span class="sxs-lookup"><span data-stu-id="82458-122">Response</span></span>
<span data-ttu-id="82458-123">成功した場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="82458-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="82458-124">例</span><span class="sxs-lookup"><span data-stu-id="82458-124">Example</span></span>

<span data-ttu-id="82458-125">**要求**</span><span class="sxs-lookup"><span data-stu-id="82458-125">**Request**</span></span>

<span data-ttu-id="82458-126">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="82458-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="82458-127">**応答**</span><span class="sxs-lookup"><span data-stu-id="82458-127">**Response**</span></span>

<span data-ttu-id="82458-128">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="82458-128">Here is an example of the response.</span></span>
<span data-ttu-id="82458-129">フィールド ID には、デバイス グループ **ID とデバイス** 情報の **フィールド rbacGroupId** が含まれる。</span><span class="sxs-lookup"><span data-stu-id="82458-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="82458-130">グループ **化されていないフィールドは** 、グループに割り当てられていないすべてのデバイスに対して 1 つのグループに対してだけ true です。</span><span class="sxs-lookup"><span data-stu-id="82458-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="82458-131">通常どおり、このグループの名前は "UnassignedGroup" です。</span><span class="sxs-lookup"><span data-stu-id="82458-131">This group as usual has name "UnassignedGroup".</span></span>

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
