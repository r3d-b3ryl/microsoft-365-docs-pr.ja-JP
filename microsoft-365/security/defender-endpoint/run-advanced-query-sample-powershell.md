---
title: PowerShell API Basics を使用した高度なハンティング
ms.reviewer: ''
description: PowerShell を使用した Microsoft Defender for Endpoint API のクエリの基本について説明します。
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
ms.openlocfilehash: 0d44f59f69c590ecd8d61207de8784af3e32197d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844888"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="f91be-104">PowerShell を使用した高度な追求</span><span class="sxs-lookup"><span data-stu-id="f91be-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f91be-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f91be-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="f91be-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="f91be-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f91be-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f91be-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f91be-108">PowerShell を使用して高度なクエリを実行する方法については [、「Advanced Hunting API」を参照してください](run-advanced-query-api.md)。</span><span class="sxs-lookup"><span data-stu-id="f91be-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="f91be-109">このセクションでは、PowerShell サンプルを共有してトークンを取得し、それを使用してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="f91be-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f91be-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="f91be-110">Before you begin</span></span>
<span data-ttu-id="f91be-111">最初にアプリを [作成する必要があります](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="f91be-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="f91be-112">準備手順</span><span class="sxs-lookup"><span data-stu-id="f91be-112">Preparation instructions</span></span>

- <span data-ttu-id="f91be-113">PowerShell のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="f91be-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="f91be-114">ポリシーで PowerShell コマンドを実行できない場合は、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f91be-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="f91be-115">詳細については [、「PowerShell のドキュメント」を参照してください。](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="f91be-115">For more information, see [PowerShell documentation](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="f91be-116">トークンの取得</span><span class="sxs-lookup"><span data-stu-id="f91be-116">Get token</span></span>

- <span data-ttu-id="f91be-117">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f91be-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="f91be-118">どこ</span><span class="sxs-lookup"><span data-stu-id="f91be-118">where</span></span>
- <span data-ttu-id="f91be-119">$tenantId: クエリを実行するテナントの ID (つまり、このテナントのデータに対してクエリが実行されます)</span><span class="sxs-lookup"><span data-stu-id="f91be-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="f91be-120">$appId: Azure AD アプリの ID (アプリに Defender for Endpoint への 「高度なクエリの実行」 アクセス許可が必要)</span><span class="sxs-lookup"><span data-stu-id="f91be-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="f91be-121">$appSecret: Azure AD アプリの秘密</span><span class="sxs-lookup"><span data-stu-id="f91be-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="f91be-122">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="f91be-122">Run query</span></span>

<span data-ttu-id="f91be-123">次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="f91be-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="f91be-124">$resultsクエリの結果を含む</span><span class="sxs-lookup"><span data-stu-id="f91be-124">$results contain the results of your query</span></span>
- <span data-ttu-id="f91be-125">$schemaクエリの結果のスキーマが含まれている場合</span><span class="sxs-lookup"><span data-stu-id="f91be-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="f91be-126">複雑なクエリ</span><span class="sxs-lookup"><span data-stu-id="f91be-126">Complex queries</span></span>

<span data-ttu-id="f91be-127">複雑なクエリ (または複数行クエリ) を実行する場合は、クエリをファイルに保存し、上記のサンプルの最初の行ではなく、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f91be-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="f91be-128">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="f91be-128">Work with query results</span></span>

<span data-ttu-id="f91be-129">これで、クエリ結果を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f91be-129">You can now use the query results.</span></span>

<span data-ttu-id="f91be-130">クエリの結果を CSV 形式でファイル形式で出力するにはfile1.csvを実行します。</span><span class="sxs-lookup"><span data-stu-id="f91be-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="f91be-131">クエリの結果を JSON 形式でファイル形式で出力するには、file1.jsを実行します。</span><span class="sxs-lookup"><span data-stu-id="f91be-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="f91be-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f91be-132">Related topic</span></span>
- [<span data-ttu-id="f91be-133">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f91be-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="f91be-134">高度な追及 API</span><span class="sxs-lookup"><span data-stu-id="f91be-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="f91be-135">Python を使用した高度な追求</span><span class="sxs-lookup"><span data-stu-id="f91be-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
