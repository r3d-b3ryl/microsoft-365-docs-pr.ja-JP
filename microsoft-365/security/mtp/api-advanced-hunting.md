---
title: 高度な検索 Api
description: Microsoft の脅威保護 API を使用して高度な検索クエリを実行する方法について説明します。
keywords: 高度な検索、Api、api、MTP
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
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650426"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="e49e8-104">高度な検索 Api</span><span class="sxs-lookup"><span data-stu-id="e49e8-104">Advanced hunting APIs</span></span>

<span data-ttu-id="e49e8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e49e8-105">**Applies to:**</span></span>
- <span data-ttu-id="e49e8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e49e8-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="e49e8-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="e49e8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e49e8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e49e8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="e49e8-109">制限事項</span><span class="sxs-lookup"><span data-stu-id="e49e8-109">Limitations</span></span>
1. <span data-ttu-id="e49e8-110">クエリは、過去30日間のデータに対してのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="e49e8-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="e49e8-111">結果には最大10万行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e49e8-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="e49e8-112">実行回数は、テナントごとに制限されます。1分あたり最大15件の通話、稼働時間は1時間ごとに15分、稼働時間は1日に4時間。</span><span class="sxs-lookup"><span data-stu-id="e49e8-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="e49e8-113">1回の要求の最大実行時間は10分です。</span><span class="sxs-lookup"><span data-stu-id="e49e8-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="e49e8-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e49e8-114">Permissions</span></span>
<span data-ttu-id="e49e8-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e49e8-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e49e8-116">アクセス許可の選択方法を含む詳細については、「 [Microsoft の脅威保護 api にアクセス](api-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e49e8-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="e49e8-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="e49e8-117">Permission type</span></span> |   <span data-ttu-id="e49e8-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e49e8-118">Permission</span></span>  |   <span data-ttu-id="e49e8-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="e49e8-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e49e8-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e49e8-120">Application</span></span> |   <span data-ttu-id="e49e8-121">AdvancedHunting</span><span class="sxs-lookup"><span data-stu-id="e49e8-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="e49e8-122">[高度なクエリを実行する]</span><span class="sxs-lookup"><span data-stu-id="e49e8-122">'Run advanced queries'</span></span>
<span data-ttu-id="e49e8-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="e49e8-123">Delegated (work or school account)</span></span> | <span data-ttu-id="e49e8-124">AdvancedHunting</span><span class="sxs-lookup"><span data-stu-id="e49e8-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="e49e8-125">[高度なクエリを実行する]</span><span class="sxs-lookup"><span data-stu-id="e49e8-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="e49e8-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="e49e8-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e49e8-127">ユーザーは ' View Data ' AD の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49e8-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="e49e8-128">ユーザーはデバイスグループの設定に基づいて、デバイスへのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49e8-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="e49e8-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="e49e8-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="e49e8-130">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e49e8-130">Request headers</span></span>

<span data-ttu-id="e49e8-131">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e49e8-131">Header</span></span> | <span data-ttu-id="e49e8-132">値</span><span class="sxs-lookup"><span data-stu-id="e49e8-132">Value</span></span> 
:---|:---
<span data-ttu-id="e49e8-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="e49e8-133">Authorization</span></span> | <span data-ttu-id="e49e8-134">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="e49e8-134">Bearer {token}.</span></span> <span data-ttu-id="e49e8-135">**必須**。</span><span class="sxs-lookup"><span data-stu-id="e49e8-135">**Required**.</span></span>
<span data-ttu-id="e49e8-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e49e8-136">Content-Type</span></span>    | <span data-ttu-id="e49e8-137">application/json</span><span class="sxs-lookup"><span data-stu-id="e49e8-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="e49e8-138">要求本文</span><span class="sxs-lookup"><span data-stu-id="e49e8-138">Request body</span></span>
<span data-ttu-id="e49e8-139">要求本文で、次のパラメーターを使用して JSON オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e49e8-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="e49e8-140">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e49e8-140">Parameter</span></span> | <span data-ttu-id="e49e8-141">種類</span><span class="sxs-lookup"><span data-stu-id="e49e8-141">Type</span></span>    | <span data-ttu-id="e49e8-142">説明</span><span class="sxs-lookup"><span data-stu-id="e49e8-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="e49e8-143">クエリ</span><span class="sxs-lookup"><span data-stu-id="e49e8-143">Query</span></span> | <span data-ttu-id="e49e8-144">テキスト</span><span class="sxs-lookup"><span data-stu-id="e49e8-144">Text</span></span> |  <span data-ttu-id="e49e8-145">実行するクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="e49e8-145">The query to run.</span></span> <span data-ttu-id="e49e8-146">**必須**。</span><span class="sxs-lookup"><span data-stu-id="e49e8-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="e49e8-147">応答</span><span class="sxs-lookup"><span data-stu-id="e49e8-147">Response</span></span>
<span data-ttu-id="e49e8-148">成功した場合、このメソッドは 200 OK を返し、応答本文で _Queryresponse_ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e49e8-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="e49e8-149">Response オブジェクトは3つの部分 (プロパティ) に分かれています。</span><span class="sxs-lookup"><span data-stu-id="e49e8-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="e49e8-150">```Stats``` -クエリパフォーマンス統計。</span><span class="sxs-lookup"><span data-stu-id="e49e8-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="e49e8-151">```Schema``` -応答のスキーマ。各列の名前の種類のペアのリスト。</span><span class="sxs-lookup"><span data-stu-id="e49e8-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="e49e8-152">```Results``` -高度な検索イベントのリスト。</span><span class="sxs-lookup"><span data-stu-id="e49e8-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="e49e8-153">例</span><span class="sxs-lookup"><span data-stu-id="e49e8-153">Example</span></span>

<span data-ttu-id="e49e8-154">要求</span><span class="sxs-lookup"><span data-stu-id="e49e8-154">Request</span></span>

<span data-ttu-id="e49e8-155">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="e49e8-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="e49e8-156">応答</span><span class="sxs-lookup"><span data-stu-id="e49e8-156">Response</span></span>

<span data-ttu-id="e49e8-157">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="e49e8-157">Here is an example of the response.</span></span>


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a><span data-ttu-id="e49e8-158">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e49e8-158">Related topic</span></span>
- [<span data-ttu-id="e49e8-159">Microsoft の脅威保護 Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="e49e8-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
