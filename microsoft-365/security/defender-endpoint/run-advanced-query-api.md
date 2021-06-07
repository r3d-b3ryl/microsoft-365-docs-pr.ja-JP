---
title: 高度な追及 API
ms.reviewer: ''
description: 高度なハンティング API を使用して、Microsoft Defender for Endpoint で高度なクエリを実行する方法について説明します。 制限について説明し、例を参照してください。
keywords: apis、サポートされている API、高度な検索、クエリ
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0173e271967a1b5b18d69713e9e6540e9cd11a87
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772403"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="9fed1-105">高度なハンティング API</span><span class="sxs-lookup"><span data-stu-id="9fed1-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9fed1-106">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9fed1-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9fed1-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="9fed1-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9fed1-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="9fed1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="9fed1-109">制限事項</span><span class="sxs-lookup"><span data-stu-id="9fed1-109">Limitations</span></span>

1. <span data-ttu-id="9fed1-110">クエリを実行できるのは、過去 30 日間のデータのみです。</span><span class="sxs-lookup"><span data-stu-id="9fed1-110">You can only run a query on data from the last 30 days.</span></span>

2. <span data-ttu-id="9fed1-111">結果には、最大 100,000 行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9fed1-111">The results will include a maximum of 100,000 rows.</span></span>

3. <span data-ttu-id="9fed1-112">実行の数はテナントごとに制限されます。</span><span class="sxs-lookup"><span data-stu-id="9fed1-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="9fed1-113">API 呼び出し: 1 分あたり最大 45 回の呼び出し、1 時間あたり最大 1500 回の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="9fed1-113">API calls: Up to 45 calls per minute, up to 1500 calls per hour.</span></span>
   - <span data-ttu-id="9fed1-114">実行時間: 1 時間ごとに 10 分、1 日に 3 時間の実行時間。</span><span class="sxs-lookup"><span data-stu-id="9fed1-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>

4. <span data-ttu-id="9fed1-115">1 つの要求の最大実行時間は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="9fed1-115">The maximal execution time of a single request is 10 minutes.</span></span>

5. <span data-ttu-id="9fed1-116">429 応答は、要求数または CPU によってクォータ制限に達した値を表します。</span><span class="sxs-lookup"><span data-stu-id="9fed1-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="9fed1-117">応答本文を読み取り、どの制限に達したのかを理解します。</span><span class="sxs-lookup"><span data-stu-id="9fed1-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="9fed1-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9fed1-118">Permissions</span></span>

<span data-ttu-id="9fed1-119">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="9fed1-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9fed1-120">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9fed1-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9fed1-121">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="9fed1-121">Permission type</span></span> |   <span data-ttu-id="9fed1-122">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9fed1-122">Permission</span></span>  |   <span data-ttu-id="9fed1-123">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="9fed1-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9fed1-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9fed1-124">Application</span></span> |   <span data-ttu-id="9fed1-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="9fed1-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="9fed1-126">'高度なクエリを実行する'</span><span class="sxs-lookup"><span data-stu-id="9fed1-126">'Run advanced queries'</span></span>
<span data-ttu-id="9fed1-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="9fed1-127">Delegated (work or school account)</span></span> | <span data-ttu-id="9fed1-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="9fed1-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="9fed1-129">'高度なクエリを実行する'</span><span class="sxs-lookup"><span data-stu-id="9fed1-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="9fed1-130">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="9fed1-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9fed1-131">ユーザーが 'View Data' ロールを持つAD</span><span class="sxs-lookup"><span data-stu-id="9fed1-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="9fed1-132">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="9fed1-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9fed1-133">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="9fed1-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="9fed1-134">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="9fed1-134">Request headers</span></span>

<span data-ttu-id="9fed1-135">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="9fed1-135">Header</span></span> | <span data-ttu-id="9fed1-136">値</span><span class="sxs-lookup"><span data-stu-id="9fed1-136">Value</span></span> 
:---|:---
<span data-ttu-id="9fed1-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="9fed1-137">Authorization</span></span> | <span data-ttu-id="9fed1-138">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="9fed1-138">Bearer {token}.</span></span> <span data-ttu-id="9fed1-139">**必須**</span><span class="sxs-lookup"><span data-stu-id="9fed1-139">**Required**.</span></span>
<span data-ttu-id="9fed1-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9fed1-140">Content-Type</span></span>    | <span data-ttu-id="9fed1-141">application/json</span><span class="sxs-lookup"><span data-stu-id="9fed1-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="9fed1-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="9fed1-142">Request body</span></span>

<span data-ttu-id="9fed1-143">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fed1-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="9fed1-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9fed1-144">Parameter</span></span> | <span data-ttu-id="9fed1-145">種類</span><span class="sxs-lookup"><span data-stu-id="9fed1-145">Type</span></span>    | <span data-ttu-id="9fed1-146">説明</span><span class="sxs-lookup"><span data-stu-id="9fed1-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="9fed1-147">クエリ</span><span class="sxs-lookup"><span data-stu-id="9fed1-147">Query</span></span> | <span data-ttu-id="9fed1-148">テキスト</span><span class="sxs-lookup"><span data-stu-id="9fed1-148">Text</span></span> |  <span data-ttu-id="9fed1-149">実行するクエリ。</span><span class="sxs-lookup"><span data-stu-id="9fed1-149">The query to run.</span></span> <span data-ttu-id="9fed1-150">**必須**</span><span class="sxs-lookup"><span data-stu-id="9fed1-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="9fed1-151">応答</span><span class="sxs-lookup"><span data-stu-id="9fed1-151">Response</span></span>

<span data-ttu-id="9fed1-152">成功した場合、このメソッドは 200 OK を返し、応答本文で _QueryResponse_ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9fed1-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="9fed1-153">例</span><span class="sxs-lookup"><span data-stu-id="9fed1-153">Example</span></span>

##### <a name="request"></a><span data-ttu-id="9fed1-154">要求</span><span class="sxs-lookup"><span data-stu-id="9fed1-154">Request</span></span>

<span data-ttu-id="9fed1-155">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="9fed1-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a><span data-ttu-id="9fed1-156">応答</span><span class="sxs-lookup"><span data-stu-id="9fed1-156">Response</span></span>

<span data-ttu-id="9fed1-157">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="9fed1-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="9fed1-158">ここに示す応答オブジェクトは、簡単に切り詰められることがあります。</span><span class="sxs-lookup"><span data-stu-id="9fed1-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="9fed1-159">実際の呼び出しではすべてのプロパティが返されます。</span><span class="sxs-lookup"><span data-stu-id="9fed1-159">All of the properties will be returned from an actual call.</span></span>

```json
{
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
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="9fed1-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fed1-160">Related topics</span></span>

- [<span data-ttu-id="9fed1-161">Microsoft Defender for Endpoint API の概要</span><span class="sxs-lookup"><span data-stu-id="9fed1-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="9fed1-162">ポータルからの高度な検索</span><span class="sxs-lookup"><span data-stu-id="9fed1-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9fed1-163">PowerShell を使用した高度な追求</span><span class="sxs-lookup"><span data-stu-id="9fed1-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
