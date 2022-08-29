---
title: インジケーター API を削除します。
description: インジケーターの削除 API を使用して、Microsoft Defender for Endpointの ID でインジケーター エンティティを削除する方法について説明します。
keywords: apis, public api, サポートされている API, delete, ti indicator, entity, id
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 1bfb5955a14f8f520ce66139b708f82d27e1f724
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326125"
---
# <a name="delete-indicator-api"></a>インジケーター API の削除

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API の説明

[ID でインジケーター](ti-indicator.md) エンティティを削除します。

## <a name="limitations"></a>制限事項

この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[作業の開始」](apis-intro.md)を参照してください。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
:---|:---|:---
アプリケーション | Ti.ReadWrite | 'TI インジケーターの読み取りと書き込み'
アプリケーション | Ti.ReadWrite.All | 'インジケーターの読み取りと書き込み'

## <a name="http-request"></a>HTTP 要求

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

インジケーターが存在し、正常に削除された場合 - 204 OK (コンテンツなし)

指定した ID を持つインジケーターが見つからなかった場合 - 404 Not Found

## <a name="example"></a>例

### <a name="request"></a>要求

要求の例を次に示します。

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
