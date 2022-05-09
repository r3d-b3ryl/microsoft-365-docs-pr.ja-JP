---
title: ソフトウェアの一覧表示
description: ソフトウェア インベントリの一覧を取得します
keywords: apis, graph api, サポートされている API, get, list, file, information, software inventory, threat & 脆弱性の管理 api, Microsoft Defender for Endpoint tvm api
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0f2db10e24212808253e197c562468c03f3ae293
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300900"
---
# <a name="list-software-inventory-api"></a>ソフトウェア インベントリ API の一覧表示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

組織のソフトウェア インベントリを取得します。
<br>[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。
<br>OData でサポートされている演算子:
<br>```$filter``` on:  ```id```、、 ```name```および ```vendor``` プロパティ。
<br>```$top``` 最大値が 10,000 です。
<br>```$skip```.
<br>[Microsoft Defender for Endpointを使用した OData クエリの](exposed-apis-odata-samples.md)例を参照してください。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用](apis-intro.md)する」を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Software.Read.All|'脅威と脆弱性管理ソフトウェアの情報の読み取り'
委任 (職場または学校のアカウント)|Software.Read|'脅威と脆弱性管理ソフトウェアの情報の読み取り'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/Software
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは本体のソフトウェア インベントリで 200 OK を返します。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/Software
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a>関連項目

- [リスクベースの脅威&脆弱性管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [脅威&脆弱性ソフトウェア インベントリ](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
