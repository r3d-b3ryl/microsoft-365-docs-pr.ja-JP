---
title: インシデント API の更新
description: Microsoft 脅威保護 API を使用してインシデントを更新する方法について説明します。
keywords: update、api、incident
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650394"
---
# <a name="update-incidents-api"></a>インシデント API の更新

**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>API の説明
既存のインシデントのプロパティを更新します。
<br>更新可能なプロパティは、、、 ```status``` ```determination``` ```classification``` 、 ```assignedTo``` ```tags``` です。


## <a name="limitations"></a>制限事項
1. この API の速度制限は、1分あたり50通話、1時間あたり1500通話です。
2. ```determination```分類が TruePositive に設定されている場合にのみ、を設定できます。


## <a name="permissions"></a>アクセス許可
この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法を含む詳細については、「 [Microsoft の脅威保護 api にアクセス](api-access.md)する」を参照してください。

アクセス許可の種類 |   アクセス許可  |   アクセス許可の表示名
:---|:---|:---
アプリケーション |   インシデント。すべて |    ' すべてのインシデントの読み取りと書き込み '
委任 (職場または学校のアカウント) | 障害/書き込み | ' 読み取りおよび書き込みのインシデント '

>[!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>- ユーザーはポータルでインシデントを更新する権限を持っている必要があります。


## <a name="http-request"></a>HTTP 要求

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前 | 種類 | 説明
:---|:---|:---
Authorization | 文字列 | ベアラー {token}。 **必須**。
Content-Type | 文字列 | application/json. **必須**。


## <a name="request-body"></a>要求本文
要求本文で、更新する必要のある関連フィールドの値を指定します。
<br>要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。 
<br>最適なパフォーマンスを得るために、変更されていない既存の値を含めないでください。

プロパティ | 種類 | 説明
:---|:---|:---
status | 列挙 | 通知の現在の状態を指定します。 可能な値は ```Active``` 、、、 ```Resolved``` ```Redirected``` です。
assignedTo | string | インシデントの所有者。
classification | 列挙 | 通知の仕様。 可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。
決定 | 列挙 | 通知の決定を指定します。 可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。
tags | 文字列リスト | インシデントタグのリスト。



## <a name="response"></a>応答
成功した場合、このメソッドは 200 OK と、応答本文で、更新されたプロパティを持つ incident エンティティを返します。 指定した id の incident が見つからない場合は、404が見つかりません。


## <a name="example"></a>例

**要求**

以下は、要求の例です。

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>関連トピック
- [インシデント Api](api-incident.md)
- [インシデントを一覧表示する](api-list-incidents.md)