---
title: Batch Update アラート エンティティ API
description: この API を使用してMicrosoft Defender for Endpointアラートをバッチで更新する方法について説明します。 状態、決定、分類、および assignedTo プロパティを更新できます。
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 7bda1310178759def39b6ba9baedb25de875fb11
ms.sourcegitcommit: e4882e3c66166ea7b834ad2e8fafeab42293e07d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67099153"
---
# <a name="batch-update-alerts"></a>アラートのバッチ更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API の説明

既存のアラートのバッチのプロパティを更新[します](alerts.md)。

**コメント** の送信は、プロパティの更新の有無にかかわらず使用できます。

更新可能なプロパティは、次 `classification` `determination``assignedTo`のとおりです。 `status`

## <a name="limitations"></a>制限事項

1. API で使用可能なアラートを更新できます。 詳細については、「 [アラートの一覧表示](get-alerts.md) 」を参照してください。
2. この API のレート制限は、1 分あたり 10 回、1 時間あたり 500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
:---|:---|:---
アプリケーション | Alert.ReadWrite.All | 'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント) | Alert.ReadWrite | 'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"アラート調査" (詳細については、 [ロールの作成と管理](user-roles.md) に関するページを参照してください)
> - ユーザーは、デバイス グループの設定に基づいて、アラートに関連付けられているデバイスにアクセスできる必要があります (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照)

## <a name="http-request"></a>HTTP 要求

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**。
Content-Type | 文字列 | application/json. **必須**。

## <a name="request-body"></a>要求本文

要求本文で、更新するアラートの ID と、これらのアラートに対して更新する関連フィールドの値を指定します。

要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。

最適なパフォーマンスを得るためには、変更されていない既存の値を含めないでください。

プロパティ | 型 | 説明
:---|:---|:---
alertIds | リスト&lt;文字列&gt;| 更新するアラートの ID の一覧。 **必須**
status | String | 指定したアラートの更新された状態を指定します。 プロパティの値は、"新規"、"InProgress"、"Resolved" です。
assignedTo | String | 指定したアラートの所有者
classification | String | 指定したアラートの仕様を指定します。 プロパティの値は、"True positive"、"Informational、expected activity"、"False positive" です。
決定 | String | 指定したアラートの決定を指定します。 プロパティの値は、'NotAvailable'、'Apt'、'Malware'、'SecurityPersonnel'、'SecurityTesting'、'UnwantedSoftware'、'Other' です。
comment | String | 指定したアラートに追加するコメント。

>[!NOTE]
>2022 年 8 月 29 日頃、以前にサポートされていたアラート決定値 ('Apt' と 'SecurityPersonnel') は非推奨になり、API 経由では使用できなくなります。

## <a name="response"></a>応答

成功した場合、このメソッドは空の応答本文で 200 OK を返します。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
