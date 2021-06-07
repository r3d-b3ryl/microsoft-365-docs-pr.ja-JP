---
title: リスト インジケーター API
description: リスト インジケーター API を使用して、Microsoft Defender for Endpoint のすべてのアクティブなインジケーターのコレクションを取得する方法について説明します。
keywords: apis, public api, supported apis, Indicators コレクション
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9ec8610957af0bc7741848e7c7bd4fe850f5e32
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770428"
---
# <a name="list-indicators-api"></a><span data-ttu-id="3a49d-104">リスト インジケーター API</span><span class="sxs-lookup"><span data-stu-id="3a49d-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3a49d-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3a49d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="3a49d-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3a49d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3a49d-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3a49d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3a49d-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="3a49d-108">API description</span></span>
<span data-ttu-id="3a49d-109">すべてのアクティブなインジケーターのコレクションを [取得します](ti-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="3a49d-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="3a49d-110">[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="3a49d-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="3a49d-111">OData のクエリは、およびプロパティ ```$filter``` ```indicatorValue``` ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` で ```action``` サポート ```severity``` されています。</span><span class="sxs-lookup"><span data-stu-id="3a49d-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="3a49d-112">Microsoft Defender [for Endpoint を使用した OData クエリの例を参照してください。](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="3a49d-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="3a49d-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="3a49d-113">Limitations</span></span>
1. <span data-ttu-id="3a49d-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="3a49d-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="3a49d-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3a49d-115">Permissions</span></span>
<span data-ttu-id="3a49d-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="3a49d-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3a49d-117">アクセス許可の選択方法などの詳細については、「開始する」 [を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3a49d-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="3a49d-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="3a49d-118">Permission type</span></span> |   <span data-ttu-id="3a49d-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3a49d-119">Permission</span></span>  |   <span data-ttu-id="3a49d-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="3a49d-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3a49d-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3a49d-121">Application</span></span> |   <span data-ttu-id="3a49d-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3a49d-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="3a49d-123">'読み取りおよび書き込みインジケーター'</span><span class="sxs-lookup"><span data-stu-id="3a49d-123">'Read and write Indicators'</span></span>
<span data-ttu-id="3a49d-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3a49d-124">Application</span></span> |   <span data-ttu-id="3a49d-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3a49d-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="3a49d-126">'すべてのインジケーターの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="3a49d-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="3a49d-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="3a49d-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="3a49d-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3a49d-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="3a49d-129">'読み取りおよび書き込みインジケーター'</span><span class="sxs-lookup"><span data-stu-id="3a49d-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="3a49d-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3a49d-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="3a49d-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3a49d-131">Request headers</span></span>

<span data-ttu-id="3a49d-132">名前</span><span class="sxs-lookup"><span data-stu-id="3a49d-132">Name</span></span> | <span data-ttu-id="3a49d-133">種類</span><span class="sxs-lookup"><span data-stu-id="3a49d-133">Type</span></span> | <span data-ttu-id="3a49d-134">説明</span><span class="sxs-lookup"><span data-stu-id="3a49d-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="3a49d-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="3a49d-135">Authorization</span></span> | <span data-ttu-id="3a49d-136">String</span><span class="sxs-lookup"><span data-stu-id="3a49d-136">String</span></span> | <span data-ttu-id="3a49d-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="3a49d-137">Bearer {token}.</span></span> <span data-ttu-id="3a49d-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="3a49d-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3a49d-139">要求本文</span><span class="sxs-lookup"><span data-stu-id="3a49d-139">Request body</span></span>
<span data-ttu-id="3a49d-140">Empty</span><span class="sxs-lookup"><span data-stu-id="3a49d-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3a49d-141">応答</span><span class="sxs-lookup"><span data-stu-id="3a49d-141">Response</span></span>
<span data-ttu-id="3a49d-142">成功した場合、このメソッドは、Indicator エンティティのコレクションを持つ 200 Ok 応答コード [を](ti-indicator.md) 返します。</span><span class="sxs-lookup"><span data-stu-id="3a49d-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="3a49d-143">アプリケーションに 'Ti.ReadWrite.All' アクセス許可がある場合は、すべてのインジケーターに公開されます。</span><span class="sxs-lookup"><span data-stu-id="3a49d-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="3a49d-144">それ以外の場合は、作成したインジケーターにのみ公開されます。</span><span class="sxs-lookup"><span data-stu-id="3a49d-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="3a49d-145">例 1:</span><span class="sxs-lookup"><span data-stu-id="3a49d-145">Example 1:</span></span>

<span data-ttu-id="3a49d-146">**要求**</span><span class="sxs-lookup"><span data-stu-id="3a49d-146">**Request**</span></span>

<span data-ttu-id="3a49d-147">すべてのインジケーターを取得する要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a49d-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="3a49d-148">**応答**</span><span class="sxs-lookup"><span data-stu-id="3a49d-148">**Response**</span></span>

<span data-ttu-id="3a49d-149">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="3a49d-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="3a49d-150">例 2:</span><span class="sxs-lookup"><span data-stu-id="3a49d-150">Example 2:</span></span>

<span data-ttu-id="3a49d-151">**要求**</span><span class="sxs-lookup"><span data-stu-id="3a49d-151">**Request**</span></span>

<span data-ttu-id="3a49d-152">'AlertAndBlock' アクションを持つすべてのインジケーターを取得する要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a49d-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="3a49d-153">**応答**</span><span class="sxs-lookup"><span data-stu-id="3a49d-153">**Response**</span></span>

<span data-ttu-id="3a49d-154">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="3a49d-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
