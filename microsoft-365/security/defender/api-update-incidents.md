---
title: インシデント API を更新する
description: Microsoft 365 Defender API を使用してインシデントを更新する方法について説明します
keywords: update, api, incident
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: f0d8ec43cc67ab07b2c69104e79730ab522118ad
ms.sourcegitcommit: e4882e3c66166ea7b834ad2e8fafeab42293e07d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67100055"
---
# <a name="update-incidents-api"></a>インシデント API を更新する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="api-description"></a>API の説明

既存のインシデントのプロパティを更新します。 更新可能なプロパティは、次`classification``comments``tags``assignedTo``determination`のとおりです。 `status`

### <a name="quotas-resource-allocation-and-other-constraints"></a>クォータ、リソース割り当て、およびその他の制約

1. 調整しきい値に達する前に、1 分あたり最大 50 回、1 時間あたり 1500 回の呼び出しを行うことができます。
2. このプロパティは `determination` 、TruePositive に設定されている場合 `classification` にのみ設定できます。

要求が調整されると、応答コードが `429` 返されます。 応答本文には、新しい呼び出しを開始できる時刻が示されます。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft 365 Defender API にアクセス](api-access.md)する」を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Incident.ReadWrite.All|すべてのインシデントの読み取りと書き込み
委任 (職場または学校のアカウント)|Incident.ReadWrite|インシデントの読み取りと書き込み

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合、ユーザーはポータルでインシデントを更新するアクセス許可を持っている必要があります。

## <a name="http-request"></a>HTTP 要求

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
---|---|---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|文字列|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、更新する必要があるフィールドの値を指定します。 要求本文に含まれていない既存のプロパティは、関連する値の変更が原因で再計算する必要がない限り、その値を保持します。 パフォーマンスを最大限に高めるには、変更されていない既存の値を省略する必要があります。

プロパティ|型|説明
---|---|---
status|列挙|インシデントの現在の状態を指定します。 指定できる値は、次`Resolved``Redirected`のとおりです。 `Active`
assignedTo|string|インシデントの所有者。
classification|列挙|インシデントの仕様。 可能な値は `Unknown`、`FalsePositive`、`TruePositive` です。
決定|列挙|インシデントの決定を指定します。 可能な値は、`NotAvailable`、`Apt`、`Malware`、`SecurityPersonnel`、`SecurityTesting`、`UnwantedSoftware`、`Other` です。
tags|string List|インシデント タグの一覧。
comment|string|インシデントに追加するコメント。

>[!NOTE]
>2022 年 8 月 29 日頃、以前にサポートされていたアラート決定値 ('Apt' と 'SecurityPersonnel') は非推奨になり、API 経由では使用できなくなります。

## <a name="response"></a>応答

成功した場合、このメソッドは `200 OK`. 応答本文には、更新されたプロパティを持つインシデント エンティティが含まれます。 指定した ID を持つインシデントが見つからない場合、メソッドは .`404 Not Found`

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

## <a name="related-articles"></a>関連資料

- [Microsoft 365 Defender API にアクセスする](api-access.md)
- [API の制限とライセンスについて学習する](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [インシデント API](api-incident.md)
- [インシデントをリストする](api-list-incidents.md)
- [インシデントの概要](incidents-overview.md)
