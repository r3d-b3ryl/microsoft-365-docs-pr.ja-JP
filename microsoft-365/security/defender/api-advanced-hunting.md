---
title: Microsoft 365Defender advanced hunting API
description: Defender の高度な狩猟 API を使用して高度なMicrosoft 365を実行する方法について説明します。
keywords: Advanced Hunting, API, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c988a609a329c8f7f8988314e56aae942beebac5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932895"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="a8e5c-104">Microsoft 365Defender Advanced hunting API</span><span class="sxs-lookup"><span data-stu-id="a8e5c-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a8e5c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a8e5c-105">**Applies to:**</span></span>

- <span data-ttu-id="a8e5c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8e5c-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8e5c-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a8e5c-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a8e5c-109">[高度な検索](advanced-hunting-overview.md)は、特別に構築されたクエリ[](advanced-hunting-query-language.md)を使用して、Defender の過去 30 日間のイベント データを調べる脅威Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="a8e5c-110">高度な検索クエリを使用して、異常なアクティビティを検査し、可能な脅威を検出し、攻撃にも対応できます。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="a8e5c-111">高度な検索 API を使用すると、イベント データをプログラムでクエリできます。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="a8e5c-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="a8e5c-112">Quotas and resource allocation</span></span>

<span data-ttu-id="a8e5c-113">次の条件は、すべてのクエリに関連します。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="a8e5c-114">クエリは、過去 30 日間のデータを探索して返します。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="a8e5c-115">結果は、最大 100,000 行を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="a8e5c-116">テナントごとに 1 分あたり最大 15 回の呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="a8e5c-117">テナントごとに 1 時間あたり 10 分の実行時間があります。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="a8e5c-118">テナントごとに 1 日に 4 時間の合計実行時間があります。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="a8e5c-119">1 つの要求が 10 分以上実行された場合、その要求はタイム アウトし、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="a8e5c-120">HTTP 応答コードは、送信された要求の数または割り当てられた実行時間のいずれかによって、クォータに達 `429` したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="a8e5c-121">応答本文を読んで、到達した制限を理解します。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="a8e5c-122">上記のすべてのクォータ (たとえば、1 分あたり 15 回の呼び出し) はテナント サイズごとに設定されます。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="a8e5c-123">これらのクォータは最小です。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="a8e5c-124">権限</span><span class="sxs-lookup"><span data-stu-id="a8e5c-124">Permissions</span></span>

<span data-ttu-id="a8e5c-125">高度な検索 API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="a8e5c-126">アクセス許可の選択方法など、詳細については[、「Access the Defender Protection API Microsoft 365」を参照してください。](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="a8e5c-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="a8e5c-127">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="a8e5c-127">Permission type</span></span> | <span data-ttu-id="a8e5c-128">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a8e5c-128">Permission</span></span> | <span data-ttu-id="a8e5c-129">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="a8e5c-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="a8e5c-130">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a8e5c-130">Application</span></span> | <span data-ttu-id="a8e5c-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="a8e5c-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="a8e5c-132">高度なクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="a8e5c-132">Run advanced queries</span></span>
<span data-ttu-id="a8e5c-133">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="a8e5c-133">Delegated (work or school account)</span></span> | <span data-ttu-id="a8e5c-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="a8e5c-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="a8e5c-135">高度なクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="a8e5c-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="a8e5c-136">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="a8e5c-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="a8e5c-137">ユーザーは、"データの表示" ロールを持AD必要があります</span><span class="sxs-lookup"><span data-stu-id="a8e5c-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="a8e5c-138">ユーザーは、デバイス グループの設定に基づいて、デバイスにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="a8e5c-139">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="a8e5c-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="a8e5c-140">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a8e5c-140">Request headers</span></span>

<span data-ttu-id="a8e5c-141">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a8e5c-141">Header</span></span> | <span data-ttu-id="a8e5c-142">値</span><span class="sxs-lookup"><span data-stu-id="a8e5c-142">Value</span></span>
-|-
<span data-ttu-id="a8e5c-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="a8e5c-143">Authorization</span></span> | <span data-ttu-id="a8e5c-144">ベアラー {token} **注: 必須**</span><span class="sxs-lookup"><span data-stu-id="a8e5c-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="a8e5c-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a8e5c-145">Content-Type</span></span> | <span data-ttu-id="a8e5c-146">application/json</span><span class="sxs-lookup"><span data-stu-id="a8e5c-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="a8e5c-147">要求本文</span><span class="sxs-lookup"><span data-stu-id="a8e5c-147">Request body</span></span>

<span data-ttu-id="a8e5c-148">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="a8e5c-149">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8e5c-149">Parameter</span></span> | <span data-ttu-id="a8e5c-150">型</span><span class="sxs-lookup"><span data-stu-id="a8e5c-150">Type</span></span> | <span data-ttu-id="a8e5c-151">説明</span><span class="sxs-lookup"><span data-stu-id="a8e5c-151">Description</span></span>
-|-|-
<span data-ttu-id="a8e5c-152">クエリ</span><span class="sxs-lookup"><span data-stu-id="a8e5c-152">Query</span></span> | <span data-ttu-id="a8e5c-153">テキスト</span><span class="sxs-lookup"><span data-stu-id="a8e5c-153">Text</span></span> | <span data-ttu-id="a8e5c-154">実行するクエリ。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-154">The query to run.</span></span> <span data-ttu-id="a8e5c-155">**注: 必須**</span><span class="sxs-lookup"><span data-stu-id="a8e5c-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="a8e5c-156">応答</span><span class="sxs-lookup"><span data-stu-id="a8e5c-156">Response</span></span>

<span data-ttu-id="a8e5c-157">成功した場合、このメソッドは `200 OK` 応答本文の _QueryResponse_ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="a8e5c-158">応答オブジェクトには、次の 3 つのトップ レベル プロパティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="a8e5c-159">統計 - クエリパフォーマンス統計の辞書。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="a8e5c-160">Schema - 応答のスキーマ、各列のName-Typeの一覧。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="a8e5c-161">結果 - 高度な狩猟イベントの一覧。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="a8e5c-162">例</span><span class="sxs-lookup"><span data-stu-id="a8e5c-162">Example</span></span>

<span data-ttu-id="a8e5c-163">次の例では、ユーザーが以下のクエリを送信し、、 、および を含む API 応答オブジェクト `Stats` `Schema` を受け取ります `Results` 。</span><span class="sxs-lookup"><span data-stu-id="a8e5c-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="a8e5c-164">クエリ</span><span class="sxs-lookup"><span data-stu-id="a8e5c-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="a8e5c-165">Response オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a8e5c-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="a8e5c-166">関連記事</span><span class="sxs-lookup"><span data-stu-id="a8e5c-166">Related articles</span></span>

- [<span data-ttu-id="a8e5c-167">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="a8e5c-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a8e5c-168">API の制限とライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="a8e5c-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="a8e5c-169">エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="a8e5c-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="a8e5c-170">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="a8e5c-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
