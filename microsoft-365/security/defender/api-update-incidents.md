---
title: インシデント API の更新
description: API を使用してインシデントを更新するMicrosoft 365 Defenderする
keywords: update, api, Incident
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
ms.openlocfilehash: 4a083f4d891ef51b3156c2ad407a55de597cd6a754fa77d9d96fe5d6e3cffe4d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863237"
---
# <a name="update-incidents-api"></a>インシデント API の更新

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="api-description"></a>API の説明

既存のインシデントのプロパティを更新します。 更新可能なプロパティは `status` `determination` `classification` 、、、、、、 `assignedTo` `tags` です `comments` 。

### <a name="quotas-resource-allocation-and-other-constraints"></a>クォータ、リソース割り当て、その他の制約

1. 調整のしきい値に達する前に、1 分あたり最大 50 回の通話または 1 時間あたり 1500 回の通話を行います。
2. プロパティを設定できるのは `determination` `classification` 、TruePositive に設定されている場合のみです。

要求が調整されている場合は、応答コードが `429` 返されます。 応答本文には、新しい呼び出しを開始できる時刻が示されます。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法などの詳細については、「Access [the Microsoft 365 Defender API」を参照してください](api-access.md)。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Incident.ReadWrite.All|すべてのインシデントの読み取りおよび書き込み
委任 (職場または学校のアカウント)|Incident.ReadWrite|インシデントの読み取りおよび書き込み

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合、ユーザーはポータルでインシデントを更新するアクセス許可を持っている必要があります。

## <a name="http-request"></a>HTTP 要求

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
---|---|---
Authorization|String|ベアラー {token}。 **必須**
Content-Type|文字列|application/json. **必須**

## <a name="request-body"></a>要求本文

要求本文で、更新するフィールドの値を指定します。 要求本文に含まれていない既存のプロパティは、関連する値の変更のために再計算する必要がない限り、値を維持します。 最適なパフォーマンスを得る場合は、変更していない既存の値を省略する必要があります。

プロパティ|種類|説明
---|---|---
status|列挙|インシデントの現在の状態を指定します。 使用できる値は `Active` `Resolved` 、、、および `Redirected` です。
assignedTo|string|インシデントの所有者。
classification|列挙|インシデントの仕様。 可能な値は、`Unknown`、`FalsePositive`、`TruePositive` です。
決定|列挙|インシデントの決定を指定します。 可能な値は、`NotAvailable`、`Apt`、`Malware`、`SecurityPersonnel`、`SecurityTesting`、`UnwantedSoftware`、`Other` です。
tags|string List|インシデント タグの一覧。
comment|string|インシデントに追加するコメント。

## <a name="response"></a>応答

成功した場合、このメソッドはを返します `200 OK` 。 応答本文には、更新されたプロパティを持つインシデント エンティティが含まれる。 指定した ID を持つインシデントが見つからなかった場合、メソッドはを返します `404 Not Found` 。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

要求の例を次に示します。

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

### <a name="response-example"></a>応答の例

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

- [API にMicrosoft 365 Defenderする](api-access.md)
- [API の制限とライセンスの詳細](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [インシデント API](api-incident.md)
- [インシデントをリストする](api-list-incidents.md)
- [インシデントの概要](incidents-overview.md)
