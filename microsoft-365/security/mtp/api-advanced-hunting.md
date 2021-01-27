---
title: Microsoft 365 Defender 高度なハンティング API
description: Microsoft 365 Defender の高度な検索 API を使用して高度な検索クエリを実行する方法について説明します。
keywords: 高度な検索、API、api、MTP、M365 Defender、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988118"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="32f22-104">Microsoft 365 Defender 高度なハンティング API</span><span class="sxs-lookup"><span data-stu-id="32f22-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="32f22-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="32f22-105">**Applies to:**</span></span>

- <span data-ttu-id="32f22-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="32f22-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32f22-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="32f22-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="32f22-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="32f22-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="32f22-109">[高度な検索](advanced-hunting-overview.md)は、特別に構築されたクエリ[](advanced-hunting-query-language.md)を使用して、Microsoft 365 Defender の過去 30 日間のイベント データを調べる脅威検索ツールです。</span><span class="sxs-lookup"><span data-stu-id="32f22-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="32f22-110">高度な検索クエリを使用すると、異常なアクティビティの検査、脅威の検出、攻撃への対応を行います。</span><span class="sxs-lookup"><span data-stu-id="32f22-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="32f22-111">高度なハンティング API を使用すると、プログラムでイベント データをクエリできます。</span><span class="sxs-lookup"><span data-stu-id="32f22-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="32f22-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="32f22-112">Quotas and resource allocation</span></span>

<span data-ttu-id="32f22-113">次の条件は、すべてのクエリに関連します。</span><span class="sxs-lookup"><span data-stu-id="32f22-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="32f22-114">クエリは、過去 30 日間のデータを探索して返します。</span><span class="sxs-lookup"><span data-stu-id="32f22-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="32f22-115">結果は最大 100,000 行を返します。</span><span class="sxs-lookup"><span data-stu-id="32f22-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="32f22-116">テナントごとに 1 分あたり最大 15 回の呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="32f22-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="32f22-117">テナントごとに 1 時間あたり 10 分の実行時間があります。</span><span class="sxs-lookup"><span data-stu-id="32f22-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="32f22-118">テナントごとに 1 日あたり 4 時間の合計実行時間があります。</span><span class="sxs-lookup"><span data-stu-id="32f22-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="32f22-119">1 つの要求が 10 分以上実行される場合は、タイム アウトしてエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="32f22-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="32f22-120">HTTP 応答コードは、送信された要求の数または割り当てられた実行時間によってクォータに達 `429` したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="32f22-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="32f22-121">応答本文を読んで、達した制限を理解します。</span><span class="sxs-lookup"><span data-stu-id="32f22-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="32f22-122">上記のすべてのクォータ (たとえば、1 分あたり 15 回の呼び出し) はテナントのサイズごとに行います。</span><span class="sxs-lookup"><span data-stu-id="32f22-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="32f22-123">これらのクォータは最小です。</span><span class="sxs-lookup"><span data-stu-id="32f22-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="32f22-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="32f22-124">Permissions</span></span>

<span data-ttu-id="32f22-125">高度な検索 API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="32f22-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="32f22-126">アクセス許可の選択方法など、詳細については[、「Microsoft 365 Defender Protection API](api-access.md)へのアクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32f22-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="32f22-127">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="32f22-127">Permission type</span></span> | <span data-ttu-id="32f22-128">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="32f22-128">Permission</span></span> | <span data-ttu-id="32f22-129">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="32f22-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="32f22-130">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="32f22-130">Application</span></span> | <span data-ttu-id="32f22-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="32f22-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="32f22-132">高度なクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="32f22-132">Run advanced queries</span></span>
<span data-ttu-id="32f22-133">委任 (職場または学校アカウント)</span><span class="sxs-lookup"><span data-stu-id="32f22-133">Delegated (work or school account)</span></span> | <span data-ttu-id="32f22-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="32f22-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="32f22-135">高度なクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="32f22-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="32f22-136">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="32f22-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="32f22-137">ユーザーは"データの表示" 役割を持ADがあります。</span><span class="sxs-lookup"><span data-stu-id="32f22-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="32f22-138">ユーザーは、デバイス グループの設定に基づいて、デバイスにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="32f22-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="32f22-139">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="32f22-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="32f22-140">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="32f22-140">Request headers</span></span>

<span data-ttu-id="32f22-141">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="32f22-141">Header</span></span> | <span data-ttu-id="32f22-142">値</span><span class="sxs-lookup"><span data-stu-id="32f22-142">Value</span></span>
-|-
<span data-ttu-id="32f22-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="32f22-143">Authorization</span></span> | <span data-ttu-id="32f22-144">Bearer {token} **注: 必須**</span><span class="sxs-lookup"><span data-stu-id="32f22-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="32f22-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="32f22-145">Content-Type</span></span> | <span data-ttu-id="32f22-146">application/json</span><span class="sxs-lookup"><span data-stu-id="32f22-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="32f22-147">要求本文</span><span class="sxs-lookup"><span data-stu-id="32f22-147">Request body</span></span>

<span data-ttu-id="32f22-148">要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="32f22-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="32f22-149">パラメーター</span><span class="sxs-lookup"><span data-stu-id="32f22-149">Parameter</span></span> | <span data-ttu-id="32f22-150">種類</span><span class="sxs-lookup"><span data-stu-id="32f22-150">Type</span></span> | <span data-ttu-id="32f22-151">説明</span><span class="sxs-lookup"><span data-stu-id="32f22-151">Description</span></span>
-|-|-
<span data-ttu-id="32f22-152">クエリ</span><span class="sxs-lookup"><span data-stu-id="32f22-152">Query</span></span> | <span data-ttu-id="32f22-153">テキスト</span><span class="sxs-lookup"><span data-stu-id="32f22-153">Text</span></span> | <span data-ttu-id="32f22-154">実行するクエリ。</span><span class="sxs-lookup"><span data-stu-id="32f22-154">The query to run.</span></span> <span data-ttu-id="32f22-155">**注: 必須**</span><span class="sxs-lookup"><span data-stu-id="32f22-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="32f22-156">応答</span><span class="sxs-lookup"><span data-stu-id="32f22-156">Response</span></span>

<span data-ttu-id="32f22-157">成功した場合、このメソッドは応答本文で `200 OK` _QueryResponse_ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="32f22-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="32f22-158">応答オブジェクトには、次の 3 つのトップ レベル プロパティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="32f22-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="32f22-159">統計 : クエリ パフォーマンス統計のディクショナリです。</span><span class="sxs-lookup"><span data-stu-id="32f22-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="32f22-160">スキーマ : 応答のスキーマ、各列のName-Typeのリスト。</span><span class="sxs-lookup"><span data-stu-id="32f22-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="32f22-161">結果 - 高度な検索イベントの一覧。</span><span class="sxs-lookup"><span data-stu-id="32f22-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="32f22-162">例</span><span class="sxs-lookup"><span data-stu-id="32f22-162">Example</span></span>

<span data-ttu-id="32f22-163">次の例では、ユーザーは以下のクエリを送信し、, を含む API 応答 `Stats` オブジェクト `Schema` を受け取ります `Results` 。</span><span class="sxs-lookup"><span data-stu-id="32f22-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="32f22-164">クエリ</span><span class="sxs-lookup"><span data-stu-id="32f22-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="32f22-165">Response オブジェクト</span><span class="sxs-lookup"><span data-stu-id="32f22-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="32f22-166">関連記事</span><span class="sxs-lookup"><span data-stu-id="32f22-166">Related articles</span></span>

- [<span data-ttu-id="32f22-167">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="32f22-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="32f22-168">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="32f22-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="32f22-169">エラー コードを理解する</span><span class="sxs-lookup"><span data-stu-id="32f22-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="32f22-170">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="32f22-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
