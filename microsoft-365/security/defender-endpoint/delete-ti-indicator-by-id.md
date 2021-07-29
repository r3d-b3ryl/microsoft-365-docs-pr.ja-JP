---
title: インジケーター API を削除します。
description: Delete Indicator API を使用して、Microsoft Defender for Endpoint の ID でインジケーター エンティティを削除する方法について説明します。
keywords: apis, public api, supported apis, delete, ti indicator, entity, id
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
ms.openlocfilehash: 9e2a674f156b5300fac22673e33c07c9b5532b42
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2021
ms.locfileid: "53595668"
---
# <a name="delete-indicator-api"></a>インジケーター API の削除

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API の説明

ID で [Indicator エンティティ](ti-indicator.md) を削除します。

## <a name="limitations"></a>制限事項

この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法などの詳細については、「開始する」 [を参照してください。](apis-intro.md)

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
:---|:---|:---
アプリケーション | Ti.ReadWrite | 'TI インジケーターの読み取りおよび書き込み'
アプリケーション | Ti.ReadWrite.All | '読み取りおよび書き込みインジケーター'

## <a name="http-request"></a>HTTP 要求

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

Indicator が存在し、正常に削除された場合 - コンテンツなしで 204 OK。

指定した ID を持つインジケーターが見つからなかった場合 - 404 Not Found。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
