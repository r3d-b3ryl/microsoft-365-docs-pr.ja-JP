---
title: インポート インジケーター API
description: Microsoft Defender for Endpoint でインジケーター API のインポート バッチを使用する方法について説明します。
keywords: apis, サポートされている api, submit, ti, indicator, update
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198247"
---
# <a name="import-indicators-api"></a><span data-ttu-id="129be-104">インポート インジケーター API</span><span class="sxs-lookup"><span data-stu-id="129be-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="129be-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="129be-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="129be-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="129be-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="129be-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="129be-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="129be-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="129be-108">API description</span></span>
<span data-ttu-id="129be-109">Indicator エンティティのバッチを [送信または](ti-indicator.md) 更新します。</span><span class="sxs-lookup"><span data-stu-id="129be-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="129be-110">IPs の CIDR 表記はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="129be-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="129be-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="129be-111">Limitations</span></span>
1. <span data-ttu-id="129be-112">この API のレート制限は、1 分あたり 30 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="129be-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="129be-113">テナントごとに 15,000 のアクティブ [なインジケーターの制限](ti-indicator.md) があります。</span><span class="sxs-lookup"><span data-stu-id="129be-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="129be-114">1 つの API 呼び出しの最大バッチ サイズは 500 です。</span><span class="sxs-lookup"><span data-stu-id="129be-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="129be-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="129be-115">Permissions</span></span>
<span data-ttu-id="129be-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="129be-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="129be-117">アクセス許可の選択方法などの詳細については、「開始する」 [を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="129be-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="129be-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="129be-118">Permission type</span></span> |   <span data-ttu-id="129be-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="129be-119">Permission</span></span>  |   <span data-ttu-id="129be-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="129be-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="129be-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="129be-121">Application</span></span> |   <span data-ttu-id="129be-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="129be-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="129be-123">'読み取りおよび書き込みインジケーター'</span><span class="sxs-lookup"><span data-stu-id="129be-123">'Read and write Indicators'</span></span>
<span data-ttu-id="129be-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="129be-124">Application</span></span> |   <span data-ttu-id="129be-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="129be-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="129be-126">'すべてのインジケーターの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="129be-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="129be-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="129be-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="129be-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="129be-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="129be-129">'読み取りおよび書き込みインジケーター'</span><span class="sxs-lookup"><span data-stu-id="129be-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="129be-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="129be-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="129be-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="129be-131">Request headers</span></span>

<span data-ttu-id="129be-132">名前</span><span class="sxs-lookup"><span data-stu-id="129be-132">Name</span></span> | <span data-ttu-id="129be-133">種類</span><span class="sxs-lookup"><span data-stu-id="129be-133">Type</span></span> | <span data-ttu-id="129be-134">説明</span><span class="sxs-lookup"><span data-stu-id="129be-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="129be-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="129be-135">Authorization</span></span> | <span data-ttu-id="129be-136">文字列</span><span class="sxs-lookup"><span data-stu-id="129be-136">String</span></span> | <span data-ttu-id="129be-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="129be-137">Bearer {token}.</span></span> <span data-ttu-id="129be-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="129be-138">**Required**.</span></span>
<span data-ttu-id="129be-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="129be-139">Content-Type</span></span> | <span data-ttu-id="129be-140">string</span><span class="sxs-lookup"><span data-stu-id="129be-140">string</span></span> | <span data-ttu-id="129be-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="129be-141">application/json.</span></span> <span data-ttu-id="129be-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="129be-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="129be-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="129be-143">Request body</span></span>
<span data-ttu-id="129be-144">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="129be-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="129be-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="129be-145">Parameter</span></span> | <span data-ttu-id="129be-146">種類</span><span class="sxs-lookup"><span data-stu-id="129be-146">Type</span></span>    | <span data-ttu-id="129be-147">説明</span><span class="sxs-lookup"><span data-stu-id="129be-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="129be-148">インジケーター</span><span class="sxs-lookup"><span data-stu-id="129be-148">Indicators</span></span> | <span data-ttu-id="129be-149">リスト<[インジケーター](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="129be-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="129be-150">インジケーターの [一覧](ti-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="129be-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="129be-151">**必須**</span><span class="sxs-lookup"><span data-stu-id="129be-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="129be-152">応答</span><span class="sxs-lookup"><span data-stu-id="129be-152">Response</span></span>
- <span data-ttu-id="129be-153">成功した場合、このメソッドは、インジケーターごとのインポート結果の一覧を含む 200 - OK 応答コードを返します。以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="129be-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="129be-154">成功しない場合: このメソッドは 400 - Bad Request を返します。</span><span class="sxs-lookup"><span data-stu-id="129be-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="129be-155">通常、不適切な要求は、不適切な本文を示します。</span><span class="sxs-lookup"><span data-stu-id="129be-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="129be-156">例</span><span class="sxs-lookup"><span data-stu-id="129be-156">Example</span></span>

<span data-ttu-id="129be-157">**要求**</span><span class="sxs-lookup"><span data-stu-id="129be-157">**Request**</span></span>

<span data-ttu-id="129be-158">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="129be-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="129be-159">**応答**</span><span class="sxs-lookup"><span data-stu-id="129be-159">**Response**</span></span>

<span data-ttu-id="129be-160">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="129be-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="129be-161">関連トピック</span><span class="sxs-lookup"><span data-stu-id="129be-161">Related topic</span></span>
- [<span data-ttu-id="129be-162">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="129be-162">Manage indicators</span></span>](manage-indicators.md)
