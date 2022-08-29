---
title: デバイスのセキュア スコアを取得する
description: 組織のデバイスのセキュリティスコアを取得します。
keywords: apis, graph api, サポートされている API, get, alerts, recent
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 07651ed756d8229e6f0f4712b230875c11bf8007
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327687"
---
# <a name="get-device-secure-score"></a>デバイスのセキュア スコアを取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[デバイスの Microsoft セキュリティ スコアを取得します](tvm-microsoft-secure-score-devices.md)。 デバイスの Microsoft セキュア スコアが高いということは、エンドポイントがサイバー セキュリティの脅威攻撃に対してより回復力があることを意味します。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[エンドポイント API に Microsoft Defender を使用する](apis-intro.md)」を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Score.Read.All|'Read Threat and Vulnerability Management score'
委任 (職場または学校のアカウント)|Score.Read|'Read Threat and Vulnerability Management score'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/configurationScore
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、デバイスのセキュリティで保護されたスコア データを応答本文に格納します。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

> [!NOTE]
> 簡潔にするために、ここに示す応答の一覧が切り捨てられる場合があります。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpointを使用した OData クエリ](exposed-apis-odata-samples.md)
