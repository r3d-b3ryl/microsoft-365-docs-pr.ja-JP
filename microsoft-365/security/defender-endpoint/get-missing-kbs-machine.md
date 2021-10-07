---
title: デバイス ID で不足している KB を取得する
description: デバイス ID によって不足しているセキュリティ更新プログラムを取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, device id, threat & 脆弱性の管理 api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: fd8bb1d004259a3c3f8595b4686e5c78266495c2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152252"
---
# <a name="get-missing-kbs-by-device-id"></a>デバイス ID で不足している KB を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

デバイス ID によって不足している KB (セキュリティ更新プログラム) を取得します。

## <a name="http-request"></a>HTTP 要求

```http
GET /api/machines/{machineId}/getmissingkbs
```
## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください](apis-intro.md)。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
:---|:---|:---
アプリケーション | Software.Read.All | '脅威と脆弱性管理ソフトウェア情報の読み取り'

## <a name="request-header"></a>要求ヘッダー

名前|型|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、指定したデバイスには本文に kb データがありません。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
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
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        }
        ]
}
```

## <a name="related-topics"></a>関連トピック

- [リスクベースの脅威&の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [脅威&ソフトウェア インベントリ](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
