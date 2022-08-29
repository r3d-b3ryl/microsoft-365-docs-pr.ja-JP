---
title: List Investigations API
description: この API を使用して、Investigations コレクションの取得に関連する呼び出しを作成します。
keywords: apis、graph api、サポートされている API、Investigations コレクション
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
ms.openlocfilehash: 746cf78bce54651cc24dd07a90c5fc11772903d2
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67325993"
---
# <a name="list-investigations-api"></a>List Investigations API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

調査のコレクションを取得 [します](investigation.md)。

[OData V4 クエリ](https://www.odata.org/documentation/)をサポートします。

OData の`$filter`クエリは、次の`triggeringAlertId``startTime``id``state``machineId`プロパティでサポートされます。
<br>```$stop``` 最大値が 10,000 の場合
<br>```$skip```

[Microsoft Defender for Endpointを使用した OData クエリの例を](exposed-apis-odata-samples.md)参照してください

## <a name="limitations"></a>制限事項

1. 最大ページ サイズは 10,000 です。
2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Alert.Read.All|'すべてのアラートを読み取る'
アプリケーション|Alert.ReadWrite.All|'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント)|Alert.Read|'アラートの読み取り'
委任 (職場または学校のアカウント)|Alert.ReadWrite|'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"データの表示" (詳細については、「 [ロールの作成と管理](user-roles.md) 」を参照)

## <a name="http-request"></a>HTTP 要求

```http
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは、 [Investigations](investigation.md) エンティティのコレクションを含む 200 OK 応答コードを返します。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

すべての調査を取得する要求の例を次に示します。

```http
GET https://api.securitycenter.microsoft.com/api/investigations
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
