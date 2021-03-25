---
title: ユーザー情報 API の取得
description: Microsoft Defender for Endpoint で、ユーザー情報の取得 API を使用してキーまたはユーザー名で User エンティティを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, user, user information
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198543"
---
# <a name="get-user-information-api"></a><span data-ttu-id="08ca8-104">ユーザー情報 API の取得</span><span class="sxs-lookup"><span data-stu-id="08ca8-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08ca8-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="08ca8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="08ca8-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="08ca8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="08ca8-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="08ca8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="08ca8-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="08ca8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="08ca8-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="08ca8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="08ca8-110">キー (ユーザー名) で User エンティティを取得します。</span><span class="sxs-lookup"><span data-stu-id="08ca8-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="08ca8-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="08ca8-111">Permissions</span></span>
<span data-ttu-id="08ca8-112">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="08ca8-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="08ca8-113">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="08ca8-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="08ca8-114">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="08ca8-114">Permission type</span></span> |   <span data-ttu-id="08ca8-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="08ca8-115">Permission</span></span>  |   <span data-ttu-id="08ca8-116">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="08ca8-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="08ca8-117">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="08ca8-117">Application</span></span> |   <span data-ttu-id="08ca8-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="08ca8-118">User.Read.All</span></span> | <span data-ttu-id="08ca8-119">'すべてのユーザー プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="08ca8-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="08ca8-120">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="08ca8-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="08ca8-121">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="08ca8-121">Request headers</span></span>

<span data-ttu-id="08ca8-122">名前</span><span class="sxs-lookup"><span data-stu-id="08ca8-122">Name</span></span> | <span data-ttu-id="08ca8-123">種類</span><span class="sxs-lookup"><span data-stu-id="08ca8-123">Type</span></span> | <span data-ttu-id="08ca8-124">説明</span><span class="sxs-lookup"><span data-stu-id="08ca8-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="08ca8-125">Authorization</span><span class="sxs-lookup"><span data-stu-id="08ca8-125">Authorization</span></span> | <span data-ttu-id="08ca8-126">文字列</span><span class="sxs-lookup"><span data-stu-id="08ca8-126">String</span></span> | <span data-ttu-id="08ca8-127">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="08ca8-127">Bearer {token}.</span></span> <span data-ttu-id="08ca8-128">**必須**</span><span class="sxs-lookup"><span data-stu-id="08ca8-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="08ca8-129">要求本文</span><span class="sxs-lookup"><span data-stu-id="08ca8-129">Request body</span></span>
<span data-ttu-id="08ca8-130">Empty</span><span class="sxs-lookup"><span data-stu-id="08ca8-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="08ca8-131">応答</span><span class="sxs-lookup"><span data-stu-id="08ca8-131">Response</span></span>
<span data-ttu-id="08ca8-132">成功し、ユーザーが存在する場合 - 本文[](user.md)にユーザー エンティティが 200 OK。</span><span class="sxs-lookup"><span data-stu-id="08ca8-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="08ca8-133">ユーザーが存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="08ca8-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="08ca8-134">例</span><span class="sxs-lookup"><span data-stu-id="08ca8-134">Example</span></span>

<span data-ttu-id="08ca8-135">**要求**</span><span class="sxs-lookup"><span data-stu-id="08ca8-135">**Request**</span></span>

<span data-ttu-id="08ca8-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="08ca8-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="08ca8-137">**応答**</span><span class="sxs-lookup"><span data-stu-id="08ca8-137">**Response**</span></span>

<span data-ttu-id="08ca8-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="08ca8-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
