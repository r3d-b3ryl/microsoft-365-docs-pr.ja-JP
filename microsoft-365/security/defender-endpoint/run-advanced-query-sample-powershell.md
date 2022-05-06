---
title: PowerShell API の基本を使用した高度なハンティング
ms.reviewer: ''
description: PowerShell を使用したMicrosoft Defender for Endpoint API のクエリの基本について説明します。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: fc0cae0ff8c45f4c32213130773e3c118d779ed6
ms.sourcegitcommit: 292de1a7e5ecc2e9e6187126aebba6d3b9416dff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2022
ms.locfileid: "65243142"
---
# <a name="advanced-hunting-using-powershell"></a>PowerShell を使用した高度な追求

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

PowerShell を使用して高度なクエリを実行する方法については、「 [Advanced Hunting API](run-advanced-query-api.md)」を参照してください。

このセクションでは、PowerShell サンプルを共有してトークンを取得し、それを使用してクエリを実行します。

## <a name="before-you-begin"></a>はじめに
最初に [アプリを作成する必要があります](apis-intro.md)。

## <a name="preparation-instructions"></a>準備手順

- PowerShell のウィンドウを開きます。

- ポリシーで PowerShell コマンドを実行できない場合は、次のコマンドを実行できます。

  ```powershell
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

詳細については、 [PowerShell のドキュメントを参照してください](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>トークンを取得する

- 次のコマンドを実行します。

```powershell
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
- $appId: Azure AD アプリの ID (アプリには Defender for Endpoint に対する "高度なクエリの実行" アクセス許可が必要です)
- $appSecret: Azure AD アプリのシークレット

## <a name="run-query"></a>クエリを実行する

次のクエリを実行します。

```powershell
$query = 'DeviceRegistryEvents | limit 10' # Paste your own query here

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

- クエリの結果を含む$results
- クエリの結果のスキーマが含まれている$schema

### <a name="complex-queries"></a>複雑なクエリ

複雑なクエリ (または複数行のクエリ) を実行する場合は、クエリをファイルに保存し、上記のサンプルの最初の行ではなく、次のコマンドを実行します。

```powershell
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>クエリ結果を操作する

これで、クエリ結果を使用できるようになりました。

ファイル file1.csvでクエリの結果を CSV 形式で出力するには、次のコマンドを実行します。

```powershell
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

クエリの結果をファイル file1.json で JSON 形式で出力するには、次のコマンドを実行します。

```powershell
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>関連トピック
- [Microsoft Defender for Endpoint API](apis-intro.md)
- [高度な追求 API](run-advanced-query-api.md)
- [Python を使用した高度な追求](run-advanced-query-sample-python.md)
