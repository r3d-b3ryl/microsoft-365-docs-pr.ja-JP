---
title: RBAC マシン グループ コレクション API の取得
description: Get KB コレクション API を使用して、Microsoft Defender Advanced Threat Protection の RBAC デバイス グループのコレクションを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, RBAC, group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167020"
---
# <a name="get-kb-collection-api"></a>KB コレクション API の取得

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


RBAC デバイス グループのコレクションを取得します。

## <a name="permissions"></a>アクセス許可
ユーザーには読み取りアクセス許可が必要です。

## <a name="http-request"></a>HTTP 要求
```
GET /testwdatppreview/machinegroups
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

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**応答**

以下は、応答の例です。
フィールド ID には、デバイス グループ **ID とデバイス** 情報の **フィールド rbacGroupId** が含まれる。 グループ **化されていないフィールドは** 、グループに割り当てられていないすべてのデバイスに対して 1 つのグループに対してだけ true です。 通常どおり、このグループの名前は "UnassignedGroup" です。

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
