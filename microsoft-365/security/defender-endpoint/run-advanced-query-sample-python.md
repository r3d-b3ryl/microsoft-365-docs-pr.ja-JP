---
title: Python API ガイドを使用した高度なハンティング
ms.reviewer: ''
description: 例を使用して、Python を使用して Microsoft Defender for Endpoint API を使用してクエリを実行する方法について説明します。
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
ms.openlocfilehash: 260e191a2948544ee98223c8b7f1563719693c9c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154736"
---
# <a name="advanced-hunting-using-python"></a>Python を使用した高度な追求

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Python を使用して高度なクエリを実行するには [、「Advanced Hunting API」を参照してください](run-advanced-query-api.md)。

このセクションでは、Python サンプルを共有してトークンを取得し、それを使用してクエリを実行します。

> **前提条件**: 最初にアプリを [作成する必要があります](apis-intro.md)。

## <a name="get-token"></a>トークンの取得

- 次のコマンドを実行します。

```python
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

どこ

- tenantId: クエリを実行するテナントの ID (つまり、このテナントのデータに対してクエリが実行されます)
- appId: Azure AD アプリの ID (アプリには、Microsoft Defender for Endpoint への 「高度なクエリの実行」 アクセス許可が必要です)
- appSecret: Azure アプリAD秘密

## <a name="run-query"></a>クエリの実行

 次のクエリを実行します。

```python
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]
```

- schema には、クエリの結果のスキーマが含まれている
- 結果にはクエリの結果が含まれる

### <a name="complex-queries"></a>複雑なクエリ

複雑なクエリ (または複数行クエリ) を実行する場合は、クエリをファイルに保存し、上記のサンプルの最初の行ではなく、次のコマンドを実行します。

```python
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>クエリ結果を操作する

これで、クエリ結果を使用できます。

結果を反復処理するには、次の操作を実行します。

```python
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result
```

クエリの結果を CSV 形式でファイル形式で出力するにはfile1.csvを実行します。

```python
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

file1.json で JSON 形式でクエリの結果を出力するには、次の操作を行います。

```python
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```

## <a name="related-topic"></a>関連トピック

- [エンドポイント API 用 Microsoft Defender](apis-intro.md)
- [高度な追求 API](run-advanced-query-api.md)
- [PowerShell を使用した高度な追求](run-advanced-query-sample-powershell.md)
