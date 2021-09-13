---
title: アラート エンティティ API の更新
description: この API を使用して Microsoft Defender for Endpoint アラートを更新する方法について説明します。 状態、決定、分類、および assignedTo プロパティを更新できます。
keywords: apis, graph api, supported apis, get, alert, information, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 00c02bad3f95d2bd8def69d5dd6ad8e1c2e857df
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213364"
---
# <a name="update-alert"></a>アラートを更新する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明
既存の Alert のプロパティを [更新します](alerts.md)。

コメントの **提出は** 、プロパティを更新する場合と更新しない場合に使用できます。

更新可能なプロパティは `status` `determination` 、、、、 `classification` です `assignedTo` 。

## <a name="limitations"></a>制限事項

1. API で使用可能なアラートを更新できます。 詳細については [、「アラートの一](get-alerts.md) 覧」を参照してください。
2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Alerts.ReadWrite.All|'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント)|Alert.ReadWrite|'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'アラートの調査' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)
> - ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**
Content-Type|文字列|application/json. **必須**

## <a name="request-body"></a>要求本文

要求本文で、更新する必要がある関連フィールドの値を指定します。

要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。

最適なパフォーマンスを得る場合は、変更していない既存の値を含めてはならない。

プロパティ|型|説明
:---|:---|:---
status|String|アラートの現在の状態を指定します。 プロパティの値は、'New'、'InProgress'、および 'Resolved' です。
assignedTo|String|アラートの所有者
classification|String|アラートの仕様を指定します。 プロパティの値は、'Unknown'、'FalsePositive'、'TruePositive'です。
決定|String|アラートの決定を指定します。 プロパティの値は、'NotAvailable'、'Apt'、'Malware'、'SecurityPersonnel'、'SecurityTesting'、'UnwantedSoftware'、'Other' です。
comment|String|警告に追加するコメント。

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK[](alerts.md)を返し、更新されたプロパティを持つ応答本文のアラート エンティティを返します。 指定された ID を持つアラートが見つからなかった場合 - 404 Not Found。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
