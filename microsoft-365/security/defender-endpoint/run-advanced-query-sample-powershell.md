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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 24e143eae463d376275242ebf35abd78888de052
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165980"
---
# <a name="advanced-hunting-using-powershell"></a>PowerShell を使用した高度な追求

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

PowerShell を使用して高度なクエリを実行する方法については [、「Advanced Hunting API」を参照してください](run-advanced-query-api.md)。

このセクションでは、PowerShell サンプルを共有してトークンを取得し、それを使用してクエリを実行します。

## <a name="before-you-begin"></a>はじめに
最初にアプリを [作成する必要があります](apis-intro.md)。

## <a name="preparation-instructions"></a>準備手順

- PowerShell のウィンドウを開きます。
- ポリシーで PowerShell コマンドを実行できない場合は、次のコマンドを実行できます。
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>詳細については [、「PowerShell のドキュメント」を参照してください。](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>トークンの取得

- 次のコマンドを実行します。

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

どこ
- $tenantId: クエリを実行するテナントの ID (つまり、このテナントのデータに対してクエリが実行されます)
- $appId: アプリの ID (アプリAzure AD Defender for Endpoint への 「高度なクエリの実行」 アクセス許可が必要です)
- $appSecret: アプリの秘密Azure AD

## <a name="run-query"></a>クエリの実行

次のクエリを実行します。

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

- $resultsクエリの結果を含む
- $schemaクエリの結果のスキーマが含まれている場合

### <a name="complex-queries"></a>複雑なクエリ

複雑なクエリ (または複数行クエリ) を実行する場合は、クエリをファイルに保存し、上記のサンプルの最初の行ではなく、次のコマンドを実行します。

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>クエリ結果を操作する

これで、クエリ結果を使用できます。

クエリの結果を CSV 形式でファイル形式で出力するにはfile1.csvを実行します。

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

file1.json で JSON 形式でクエリの結果を出力するには、次の操作を行います。

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>関連トピック
- [エンドポイント API 用 Microsoft Defender](apis-intro.md)
- [高度な追求 API](run-advanced-query-api.md)
- [Python を使用した高度な追求](run-advanced-query-sample-python.md)
