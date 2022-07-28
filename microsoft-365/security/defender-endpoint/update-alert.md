---
title: アラート エンティティ API を更新する
description: この API を使用してMicrosoft Defender for Endpointアラートを更新する方法について説明します。 状態、決定、分類、および assignedTo プロパティを更新できます。
keywords: apis, graph api, サポートされている API, get, alert, information, id
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
ms.openlocfilehash: 141f57f50b8400c0fdf2b40e9d8190be96b0fe1b
ms.sourcegitcommit: 1e53bf8208c30d7b60685896207cc1142bebf34a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "67059823"
---
# <a name="update-alert"></a>アラートを更新する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明
既存の[アラート](alerts.md)のプロパティを更新します。

**コメント** の送信は、プロパティの更新の有無にかかわらず使用できます。

更新可能なプロパティは、次のとおりです。 `status``determination``classification``assignedTo`

## <a name="limitations"></a>制限事項

1. API で使用可能なアラートを更新できます。 詳細については、「 [リスト アラート](get-alerts.md)」を参照してください。
2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Alerts.ReadWrite.All|'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント)|Alert.ReadWrite|'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です。"アラート調査" (詳細については、 [ロールの作成と管理](user-roles.md) に関するページを参照してください)
> - ユーザーは、デバイス グループの設定に基づいて、アラートに関連付けられているデバイスにアクセスできる必要があります (詳細については、「[デバイス グループの作成と管理](machine-groups.md)」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。
Content-Type|文字列|application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、更新する必要がある関連フィールドの値を指定します。

要求本文に含まれていない既存のプロパティは、以前の値を保持するか、他のプロパティ値の変更に基づいて再計算されます。

パフォーマンスを最大限に高めるには、変更されていない既存の値を含めてはなりません。

プロパティ|型|説明
:---|:---|:---
状態|String|アラートの現在の状態を指定します。 プロパティの値は、"新規"、"InProgress"、"Resolved" です。
assignedTo|String|アラートの所有者
分類|String|アラートの仕様を指定します。 プロパティの値は、'Unknown'、'FalsePositive'、'TruePositive' です。
決定|String|アラートの決定を指定します。 プロパティの値は、'NotAvailable'、'Apt'、'Malware'、'SecurityPersonnel'、'SecurityTesting'、'UnwantedSoftware'、'Other' です。
コメント|文字列|アラートに追加するコメント。

>[!NOTE]
>2022 年 8 月 29 日頃、以前にサポートされていたアラート決定値 ('Apt' と 'SecurityPersonnel') は非推奨になり、API 経由では使用できなくなります。

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、更新されたプロパティを持つ応答本文の [アラート](alerts.md) エンティティを返します。 指定した ID のアラートが見つからなかった場合は 404 Not Found。

## <a name="example"></a>例

### <a name="request"></a>要求

要求の例を次に示します。

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
