---
title: ソフトウェア ID で不足している KB を取得する
description: ソフトウェア ID で不足しているセキュリティ更新プログラムを取得します
keywords: apis, graph api, サポートされている API, get, list, file, information, software id, threat & Vulnerability management api, Microsoft Defender for Endpoint tvm api, mdvm, Microsoft Defender 脆弱性の管理
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: d587951bd201e921f48244a823a11747ceed776a
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67342891"
---
# <a name="get-missing-kbs-by-software-id"></a>ソフトウェア ID で不足している KB を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

ソフトウェア ID で見つからない KB (セキュリティ更新プログラム) を取得します

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[エンドポイント API に Microsoft Defender を使用する](apis-intro.md)」を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Software.Read.All|'脅威と脆弱性管理ソフトウェアの情報の読み取り'
委任 (職場または学校のアカウント)|Software.Read|'脅威と脆弱性管理ソフトウェアの情報の読み取り'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返します。指定されたソフトウェアは本文に KB データがありません。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a>応答

以下は、応答の例です。


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a>関連項目

- [Microsoft Defender 脆弱性の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Defender の脆弱性管理ソフトウェア インベントリ](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
