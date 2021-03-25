---
title: KB コレクション API の取得
description: Microsoft Defender for Endpoint を使用して、ナレッジ ベース (KB) と KB の詳細のコレクションを取得します。
keywords: apis, graph api, supported apis, get, kb
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
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167176"
---
# <a name="get-kb-collection-api"></a>KB コレクション API の取得

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

KB と KB の詳細のコレクションを取得します。

## <a name="permissions"></a>アクセス許可
ユーザーには読み取りアクセス許可が必要です。

## <a name="http-request"></a>HTTP 要求
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a>要求ヘッダー

ヘッダー | 値 
:---|:---
Authorization | ベアラー {token}。 **必須**
コンテンツ タイプ | application/json

## <a name="request-body"></a>要求本文
Empty

## <a name="response"></a>応答
成功した場合 - 200 OK。

## <a name="example"></a>例

**要求**

以下は、要求の例です。

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

**応答**

以下は、応答の例です。

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
