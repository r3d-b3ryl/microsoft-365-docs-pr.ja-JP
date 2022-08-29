---
title: Indicator API を送信または更新する
description: Submit または Update Indicator API を使用して、Microsoft Defender for Endpointで新しい Indicator エンティティを送信または更新する方法について説明します。
keywords: apis, graph api, サポートされている API, submit, ti, indicator, update
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
ms.openlocfilehash: c683937eb1336077c8b94f229f3c14ac36303a36
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387289"
---
# <a name="submit-or-update-indicator-api"></a>Indicator API を送信または更新する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

新しい [Indicator](ti-indicator.md) エンティティを送信または更新します。

IP の CIDR 表記はサポートされていません。

## <a name="limitations"></a>制限事項

1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。
2. テナントあたり 15,000 アクティブ インジケーターの制限があります。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[作業の開始」](apis-intro.md)を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Ti.ReadWrite|'インジケーターの読み取りと書き込み'
アプリケーション|Ti.ReadWrite.All|'すべてのインジケーターの読み取りと書き込み'
委任 (職場または学校のアカウント)|Ti.ReadWrite|'インジケーターの読み取りと書き込み'

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|string|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター|種類|説明
:---|:---|:---
indicatorValue|文字列|[インジケーター](ti-indicator.md) エンティティの ID。 **必須**
indicatorType|列挙|インジケーターの種類。 指定できる値は、"FileSha1"、"FileMd5"、"CertificateThumbprint"、"FileSha256"、"IpAddress"、"DomainName"、"Url" です。 **必須**
action|列挙|インジケーターが組織内で検出された場合に実行されるアクション。 指定できる値は、"アラート"、"警告"、"ブロック"、"監査、"BlockAndRemediate"、"AlertAndBlock"、"許可" です。 **必須**。 "Audit" を使用してアクションを作成するときは、"GenerateAlert" パラメーターを "TRUE" に設定する必要があります。
アプリケーション|文字列|インジケーターに関連付けられているアプリケーション。 このフィールドは、新しいインジケーターでのみ機能します。 既存のインジケーターの値は更新されません。 **Optional**
title|String|インジケーター アラートのタイトル。 **必須**
説明|String|インジケーターの説明。 **必須**
expirationTime|DateTimeOffset|インジケーターの有効期限。 **Optional**
severity|列挙|インジケーターの重大度。 指定できる値は、"Informational"、"Low"、"Medium"、"High" です。 **Optional**
recommendedActions|文字列|TI インジケーター アラート推奨アクション。 **Optional**
rbacGroupNames|文字列|インジケーターが適用される RBAC グループ名のコンマ区切りリスト。 **Optional**
educateUrl|文字列|カスタム通知/サポート URL。 URL インジケーターのブロックアクションと警告アクションの種類でサポートされています。 **Optional**
generateAlert|列挙|**True アラート** 生成が必要な場合は False、このインジケーターでアラートを生成しない場合は **False** 。
## <a name="response"></a>応答

- 成功した場合、このメソッドは 200 - OK 応答コードと、応答本文で作成/更新された [Indicator](ti-indicator.md) エンティティを返します。
- 成功しない場合:このメソッドは 400 - 無効な要求を返します。 通常、不適切な要求は本文が正しくないためです。

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
