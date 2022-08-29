---
title: Python API ガイドを使用した高度なハンティング
ms.reviewer: ''
description: 例を使用して、Microsoft Defender for Endpoint API を使用して Python を使用してクエリを実行する方法について説明します。
keywords: apis, サポートされている API, 高度な捜索, クエリ
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6751098c58e53c06cf9b62f7b93cd48aa35f5374
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331381"
---
# <a name="advanced-hunting-using-python"></a>Python を使用した高度な追求

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Python を使用して高度なクエリを実行する方法については、「 [Advanced Hunting API](run-advanced-query-api.md)」を参照してください。

このセクションでは、Python サンプルを共有してトークンを取得し、それを使用してクエリを実行します。

> **前提条件**: 最初に [アプリを作成する必要があります](apis-intro.md)。

## <a name="get-token"></a>トークンを取得する

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

- tenantId: クエリを実行するテナントの ID (つまり、このテナントのデータでクエリが実行されます)
- appId: Azure AD アプリの ID (アプリには、Microsoft Defender for Endpointに対する "高度なクエリの実行" アクセス許可が必要です)
- appSecret: Azure AD アプリのシークレット

## <a name="run-query"></a>クエリを実行する

 次のクエリを実行します。

```python
query = 'DeviceRegistryEvents | limit 10' # Paste your own query here

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

- schema には、クエリの結果のスキーマが含まれています
- 結果にはクエリの結果が含まれます

### <a name="complex-queries"></a>複雑なクエリ

複雑なクエリ (または複数行のクエリ) を実行する場合は、クエリをファイルに保存し、上記のサンプルの最初の行の代わりに、次のコマンドを実行します。

```python
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>クエリ結果を操作する

これで、クエリ結果を使用できるようになりました。

結果を反復処理するには、次の操作を行います。

```python
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result
```

クエリの結果を CSV 形式でファイルに出力するにはfile1.csv次の手順に従います。

```python
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

ファイル file1.json で JSON 形式でクエリの結果を出力するには、次の手順を実行します。

```python
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Endpoint API](apis-intro.md)
- [高度な追求 API](run-advanced-query-api.md)
- [PowerShell を使用した高度な追求](run-advanced-query-sample-powershell.md)
