---
title: コンピューターのセキュリティ状態コレクション API を取得する
description: Microsoft Defender for Endpoint を使用してデバイスのセキュリティ状態のコレクションを取得します。
keywords: apis, graph api, supported apis, get, device, security, state
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: api
ms.openlocfilehash: af3881a5215871b0405f2f6b42b73c248af0c00c
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586875"
---
# <a name="get-machines-security-states-collection-api"></a>Get Machines セキュリティ状態コレクション API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

デバイスのセキュリティ状態のコレクションを取得します。

## <a name="permissions"></a>アクセス許可

ユーザーには読み取りアクセス許可が必要です。

## <a name="http-request"></a>HTTP 要求

```http
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a>要求ヘッダー

ヘッダー|値
:---|:---
Authorization|ベアラー {token}。 **必須**
コンテンツ タイプ|application/json

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合 - 200 OK。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

要求の例を次に示します。

```http
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

### <a name="response-example"></a>応答の例

応答の例を下に示します。

フィールド *ID には* デバイス ID が含まれるので、デバイス情報のフィールド *ID** と等しくなります。

```json
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        ...
    ]
}
```
