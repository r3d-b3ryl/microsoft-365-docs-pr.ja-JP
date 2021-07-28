---
title: CVE-KB マップ API の取得
description: Get CVE-KB マップ API を使用して、Microsoft Defender for Endpoint の KB および CVE の詳細に対する CVE のマップを取得する方法について説明します。
keywords: apis, graph api, サポートされている api, get, cve, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: afb3e689c33b7d6d314bc23b19869824b3666c00
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623950"
---
# <a name="get-cve-kb-map-api"></a>CVE-KB マップ API の取得

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

KB および CVE の詳細に対する CVE のマップを取得します。

## <a name="permissions"></a>アクセス許可

ユーザーには読み取りアクセス許可が必要です。

## <a name="http-request"></a>HTTP 要求

```http
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>要求ヘッダー

ヘッダー|値
:---|:---
Authorization|ベアラー {token}。 **必須**
コンテンツ タイプ|application/json

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功し、マップが存在する場合 - 200 OK。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    ...
}
```
