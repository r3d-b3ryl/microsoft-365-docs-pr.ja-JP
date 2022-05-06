---
title: インシデント API を取得する
description: インシデントの取得 API を使用して、Microsoft 365 Defenderで 1 つのインシデントを取得する方法について説明します。
keywords: apis, graph api, サポートされている API, get, file, hash
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 8861dc3752d2c4cc798bc83475f6a51f8245191a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159056"
---
# <a name="get-incident-information-api"></a>インシデント情報 API を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

ID で特定のインシデントを取得します。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Incident.Read.All|'すべてのインシデントを読み取る'
アプリケーション|Incident.ReadWrite.All|'すべてのインシデントの読み取りと書き込み'
委任 (職場または学校のアカウント)|Incident.Read|'インシデントの読み取り'
委任 (職場または学校のアカウント)|Incident.ReadWrite|'インシデントの読み取りと書き込み'

> [!NOTE]
>
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です。"データの表示"
> - 応答には、ユーザーが公開されているインシデントのみが含まれます。

## <a name="http-request"></a>HTTP 要求

```console
GET .../api/incidents/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
---|---|---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、応答本文のインシデント エンティティを返します。
指定した ID を持つインシデントが見つからなかった場合は 、404 が見つかりません。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
