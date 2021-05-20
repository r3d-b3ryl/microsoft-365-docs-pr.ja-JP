---
title: インシデント API の更新
description: Microsoft 365 Defender API を使用してインシデントを更新する方法を確認する
keywords: 更新,API,インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571783"
---
# <a name="update-incident-api"></a>インシデント API の更新

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="api-description"></a>API の説明

既存のインシデントのプロパティを更新します。 更新可能プロパティは、 ```status``` ```determination``` 、 、 、 、 、 、 、 ```classification``` ```assignedTo``` ```tags``` ```comments``` です。

### <a name="quotas-resource-allocation-and-other-constraints"></a>クォータ、リソース割り当て、およびその他の制約

1. 調整しきい値に達する前に、1 分間に最大 50 回、または 1 時間あたり 1500 件のコールを作成できます。
2. プロパティを設定できるのは `determination` `classification` 、TruePositive に設定されている場合のみです。

要求が調整されると、応答コードが返されます `429` 。 応答本文は、新しい呼び出しを開始できる時間を示します。

## <a name="permissions"></a>アクセス許可

この API を呼び出すためには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法を含む詳細については[、「Microsoft 365 Defender API へのアクセス](api-access.md)」を参照してください。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
-|-|-
アプリケーション | インシデント.読み書き.すべて | すべてのインシデントの読み取りと書き込み
委任 (職場または学校のアカウント) | インシデント.読み取り書き込み | インシデントの読み取りと書き込み

> [!NOTE]
> ユーザーの資格情報を使用してトークンを取得する場合、ユーザーはポータルでインシデントを更新する権限を持っている必要があります。

## <a name="http-request"></a>HTTP 要求

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前 | 型 | 説明
-|-|-
Authorization | String | ベアラー {トークン} **必須**
Content-Type | 文字列 | application/json. **必須**

## <a name="request-body"></a>要求本文

要求本文で、更新するフィールドの値を指定します。 関連する値の変更によって再計算する必要がない限り、要求本文に含まれていない既存のプロパティは値を保持します。 最適なパフォーマンスを得る場合は、変更されていない既存の値を省略してください。

プロパティ | 型 | 説明
-|-|-
status | 列挙 | インシデントの現在の状態を指定します。 使用できる値は ```Active``` 、 ```Resolved``` 、 、 、 です ```Redirected``` 。
assignedTo | string | インシデントの所有者。
classification | 列挙 | インシデントの仕様。 可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。
決定 | 列挙 | インシデントの決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | 文字列リスト | インシデント タグのリスト。
comment | string | インシデントに追加するコメント。

## <a name="response"></a>応答

成功した場合、このメソッドは `200 OK` を返します。 応答本文には、更新されたプロパティを持つインシデント エンティティが含まれます。 指定された ID のインシデントが見つからなかった場合、メソッドは `404 Not Found` を返します。

## <a name="example"></a>例

**要求**

要求の例を次に示します。

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**応答**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>関連記事

- [Microsoft 365ディフェンダー API へのアクセス](api-access.md)
- [API の制限とライセンスについて](api-terms.md)
- [エラー コードを理解する](api-error-codes.md)
- [インシデント API](api-incident.md)
- [インシデントを一覧表示する](api-list-incidents.md)
- [インシデントの概要](incidents-overview.md)
