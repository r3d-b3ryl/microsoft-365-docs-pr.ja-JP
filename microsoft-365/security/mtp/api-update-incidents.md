---
title: インシデント API の更新
description: Microsoft 365 Defender API を使用してインシデントを更新する方法について説明します。
keywords: 更新, api, インシデント
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
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929072"
---
# <a name="update-incidents-api"></a>インシデント API の更新

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>API の説明

既存のインシデントのプロパティを更新します。 更新可能なプロパティは、次 ```status``` ```determination``` ```classification``` ```assignedTo``` のとおりです ```tags``` 。

### <a name="quotas-resource-allocation-and-other-constraints"></a>クォータ、リソース割り当て、その他の制約

1. 調整しきい値に達する前に、1 分あたり最大 50 回、または 1 時間あたり 1500 回の通話を行います。
2. このプロパティは `determination` `classification` 、TruePositive に設定されている場合にのみ設定できます。

要求が調整されている場合は、応答コードを `429` 返します。 応答本文には、新しい呼び出しを開始できる時刻が示されます。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Microsoft 365 Defender API](api-access.md)へのアクセス」を参照してください。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
-|-|-
アプリケーション | Incident.ReadWrite.All | すべてのインシデントの読み取りおよび書き込み
委任 (職場または学校のアカウント) | Incident.ReadWrite | インシデントの読み取りおよび書き込み

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合、ユーザーはポータルでインシデントを更新するアクセス許可を持っている必要があります。

## <a name="http-request"></a>HTTP 要求

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前 | 種類 | 説明
-|-|-
Authorization | String | ベアラー {トークン}。 **必須**。
Content-Type | 文字列 | application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、更新するフィールドの値を指定します。 要求本文に含まれていない既存のプロパティは、関連する値の変更のために再計算する必要がない限り、値を保持します。 最適なパフォーマンスを得る場合は、変更していない既存の値を省略する必要があります。

プロパティ | 種類 | 説明
-|-|-
status | 列挙 | 通知の現在の状態を指定します。 使用できる値は ```Active``` 、次 ```Resolved``` のとおりです ```Redirected``` 。
assignedTo | string | インシデントの所有者。
classification | 列挙 | アラートの仕様。 可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。
判断 | 列挙 | 通知の判定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | string List | インシデント タグのリスト。

## <a name="response"></a>応答

成功した場合、このメソッドは返します `200 OK` 。 応答本文には、更新されたプロパティを持つインシデント エンティティが含まれる。 指定された ID のインシデントが見つからなかった場合、メソッドは返します `404 Not Found` 。

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
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API へのアクセス](api-access.md)
- [API の制限とライセンスについて](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [インシデント API](api-incident.md)
- [インシデントを一覧表示する](api-list-incidents.md)
- [インシデントの概要](incidents-overview.md)
