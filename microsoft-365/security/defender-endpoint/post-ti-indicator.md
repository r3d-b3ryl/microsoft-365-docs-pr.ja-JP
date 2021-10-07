---
title: インジケーター API の送信または更新
description: Submit または Update Indicator API を使用して、Microsoft Defender for Endpoint の新しい Indicator エンティティを送信または更新する方法について説明します。
keywords: apis, graph api, supported apis, submit, ti, indicator, update
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
ms.openlocfilehash: 299a6fff547c921dfdc02d4c23bfd8947b878875
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157880"
---
# <a name="submit-or-update-indicator-api"></a>インジケーター API の送信または更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

新しい Indicator エンティティを [送信または更新](ti-indicator.md) します。

IPs の CIDR 表記はサポートされていません。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。
2. テナントごとに 15,000 のアクティブインジケーターの制限があります。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法などの詳細については、「開始する」 [を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Ti.ReadWrite|'読み取りおよび書き込みインジケーター'
アプリケーション|Ti.ReadWrite.All|'すべてのインジケーターの読み取りと書き込み'
委任 (職場または学校のアカウント)|Ti.ReadWrite|'読み取りおよび書き込みインジケーター'

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**
Content-Type|string|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、JSON オブジェクトに次のパラメーターを指定します。

パラメーター|型|説明
:---|:---|:---
indicatorValue|String|Indicator エンティティ [の](ti-indicator.md) ID。 **必須**
indicatorType|列挙|インジケーターの種類。 指定できる値は、"FileSha1"、"FileMd5"、"CertificateThumbprint"、"FileSha256"、"IpAddress"、"DomainName"、"Url" です。 **必須**
action|列挙|インジケーターが組織内で検出される場合に実行されるアクション。 指定できる値は、"Alert"、"Warn"、"Block"、"Audit"、"BlockAndRemediate"、"AlertAndBlock"、"Allowed" です。 **必須**
アプリケーション|String|インジケーターに関連付けられているアプリケーション。 このフィールドは、新しいインジケーターでのみ機能します。 既存のインジケーターの値は更新されない。 **Optional**
title|String|インジケーターアラートのタイトル。 **必須**
description|String|インジケーターの説明。 **必須**
expirationTime|DateTimeOffset|インジケーターの有効期限。 **Optional**
severity|列挙|インジケーターの重大度。 指定できる値は、"Informational"、"Low"、"Medium"、"High" です。 **Optional**
recommendedActions|String|TI インジケーターアラート推奨アクション。 **Optional**
rbacGroupNames|String|インジケーターが適用される RBAC グループ名のコンマ区切りのリスト。 **Optional**

## <a name="response"></a>応答

- 成功した場合、このメソッドは 200 - OK 応答コードと、応答本文で作成/更新 [された Indicator](ti-indicator.md) エンティティを返します。
- 成功しない場合: このメソッドは 400 - Bad Request を返します。 通常、不適切な要求は、不適切な本文を示します。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>関連トピック

- [インジケーターの管理](manage-indicators.md)
