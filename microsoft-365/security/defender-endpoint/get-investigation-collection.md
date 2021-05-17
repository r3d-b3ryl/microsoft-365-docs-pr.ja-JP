---
title: リスト調査 API
description: この API を使用して、Investigations コレクションの取得に関連する呼び出しを作成する
keywords: apis、graph api、サポートされている API、Investigations コレクション
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 9ad1216a05846b48bff4186c7e6f39e9da3623b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167116"
---
# <a name="list-investigations-api"></a><span data-ttu-id="b7067-104">リスト調査 API</span><span class="sxs-lookup"><span data-stu-id="b7067-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7067-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b7067-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7067-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b7067-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7067-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7067-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b7067-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="b7067-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b7067-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b7067-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b7067-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="b7067-110">API description</span></span>
<span data-ttu-id="b7067-111">調査のコレクション [を取得します](investigation.md)。</span><span class="sxs-lookup"><span data-stu-id="b7067-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="b7067-112">[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="b7067-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="b7067-113">OData のクエリは ```$filter``` 、次のプロパティ ```startTime``` ```state``` で ```machineId``` サポート ```triggeringAlertId``` されています。</span><span class="sxs-lookup"><span data-stu-id="b7067-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="b7067-114">Microsoft Defender [for Endpoint を使用した OData クエリの例を参照してください。](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="b7067-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="b7067-115">制限事項</span><span class="sxs-lookup"><span data-stu-id="b7067-115">Limitations</span></span>
1. <span data-ttu-id="b7067-116">最大ページ サイズは 10,000 です。</span><span class="sxs-lookup"><span data-stu-id="b7067-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="b7067-117">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="b7067-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="b7067-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b7067-118">Permissions</span></span>
<span data-ttu-id="b7067-119">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="b7067-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b7067-120">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b7067-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b7067-121">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="b7067-121">Permission type</span></span> |   <span data-ttu-id="b7067-122">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b7067-122">Permission</span></span>  |   <span data-ttu-id="b7067-123">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="b7067-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b7067-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b7067-124">Application</span></span> |   <span data-ttu-id="b7067-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="b7067-125">Alert.Read.All</span></span> |    <span data-ttu-id="b7067-126">'すべてのアラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="b7067-126">'Read all alerts'</span></span>
<span data-ttu-id="b7067-127">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b7067-127">Application</span></span> |   <span data-ttu-id="b7067-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b7067-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="b7067-129">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="b7067-129">'Read and write all alerts'</span></span>
<span data-ttu-id="b7067-130">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b7067-130">Delegated (work or school account)</span></span> | <span data-ttu-id="b7067-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="b7067-131">Alert.Read</span></span> | <span data-ttu-id="b7067-132">'アラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="b7067-132">'Read alerts'</span></span>
<span data-ttu-id="b7067-133">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b7067-133">Delegated (work or school account)</span></span> | <span data-ttu-id="b7067-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b7067-134">Alert.ReadWrite</span></span> | <span data-ttu-id="b7067-135">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="b7067-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="b7067-136">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="b7067-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b7067-137">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="b7067-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b7067-138">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b7067-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="b7067-139">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b7067-139">Request headers</span></span>

<span data-ttu-id="b7067-140">名前</span><span class="sxs-lookup"><span data-stu-id="b7067-140">Name</span></span> | <span data-ttu-id="b7067-141">型</span><span class="sxs-lookup"><span data-stu-id="b7067-141">Type</span></span> | <span data-ttu-id="b7067-142">説明</span><span class="sxs-lookup"><span data-stu-id="b7067-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="b7067-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="b7067-143">Authorization</span></span> | <span data-ttu-id="b7067-144">String</span><span class="sxs-lookup"><span data-stu-id="b7067-144">String</span></span> | <span data-ttu-id="b7067-145">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="b7067-145">Bearer {token}.</span></span> <span data-ttu-id="b7067-146">**必須**</span><span class="sxs-lookup"><span data-stu-id="b7067-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b7067-147">要求本文</span><span class="sxs-lookup"><span data-stu-id="b7067-147">Request body</span></span>
<span data-ttu-id="b7067-148">Empty</span><span class="sxs-lookup"><span data-stu-id="b7067-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b7067-149">応答</span><span class="sxs-lookup"><span data-stu-id="b7067-149">Response</span></span>
<span data-ttu-id="b7067-150">成功した場合、このメソッドは 200 の Ok 応答コードを [、Investigations](investigation.md) エンティティのコレクションと一緒に返します。</span><span class="sxs-lookup"><span data-stu-id="b7067-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="b7067-151">例</span><span class="sxs-lookup"><span data-stu-id="b7067-151">Example</span></span>

<span data-ttu-id="b7067-152">**要求**</span><span class="sxs-lookup"><span data-stu-id="b7067-152">**Request**</span></span>

<span data-ttu-id="b7067-153">すべての調査を取得する要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b7067-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="b7067-154">**応答**</span><span class="sxs-lookup"><span data-stu-id="b7067-154">**Response**</span></span>

<span data-ttu-id="b7067-155">応答の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b7067-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
