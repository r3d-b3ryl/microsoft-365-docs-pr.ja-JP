---
title: インシデント API の取得
description: '[インシデントの取得] API を使用して、インシデントを 1 つのインシデントにMicrosoft 365 Defender。'
keywords: apis, graph api, supported apis, get, file, hash
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6f1e59dd653ef0718797a4b71e67c3607b39824c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220053"
---
# <a name="get-incident-information-api"></a>インシデント情報 API の取得

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

ID によって特定のインシデントを取得します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Incident.Read.All|'すべてのインシデントを読み取る'
アプリケーション|Incident.ReadWrite.All|'すべてのインシデントの読み取りと書き込み'
委任 (職場または学校アカウント)|Incident.Read|'インシデントの読み取り'
委任 (職場または学校アカウント)|Incident.ReadWrite|'インシデントの読み取りと書き込み'

> [!NOTE]
>
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次の役割のアクセス許可が必要です。'データの表示'
> - 応答には、ユーザーが公開されているインシデントだけが含まれます。

## <a name="http-request"></a>HTTP 要求

```console
GET .../api/incidents/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
---|---|---
Authorization|文字列|ベアラー {token}。 **必須**

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、応答本文のインシデント エンティティを返します。
指定した ID を持つインシデントが見つからなかった場合 - 404 Not Found。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
