---
title: Microsoft 365 Defender 高度なハンティング API
description: Microsoft 365 Defender の高度な検索 API を使用して高度な検索クエリを実行する方法について説明します。
keywords: 高度な検索、API、api、MTP、M365 Defender、Microsoft 365 Defender
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
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988118"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender 高度なハンティング API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft Threat Protection

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

[高度な検索](advanced-hunting-overview.md)は、特別に構築されたクエリ[](advanced-hunting-query-language.md)を使用して、Microsoft 365 Defender の過去 30 日間のイベント データを調べる脅威検索ツールです。 高度な検索クエリを使用すると、異常なアクティビティの検査、脅威の検出、攻撃への対応を行います。 高度なハンティング API を使用すると、プログラムでイベント データをクエリできます。

## <a name="quotas-and-resource-allocation"></a>クォータとリソース割り当て

次の条件は、すべてのクエリに関連します。

1. クエリは、過去 30 日間のデータを探索して返します。
2. 結果は最大 100,000 行を返します。
3. テナントごとに 1 分あたり最大 15 回の呼び出しを行います。
4. テナントごとに 1 時間あたり 10 分の実行時間があります。
5. テナントごとに 1 日あたり 4 時間の合計実行時間があります。
6. 1 つの要求が 10 分以上実行される場合は、タイム アウトしてエラーを返します。
7. HTTP 応答コードは、送信された要求の数または割り当てられた実行時間によってクォータに達 `429` したかどうかを示します。 応答本文を読んで、達した制限を理解します。 

> [!NOTE]
> 上記のすべてのクォータ (たとえば、1 分あたり 15 回の呼び出し) はテナントのサイズごとに行います。 これらのクォータは最小です。

## <a name="permissions"></a>アクセス許可

高度な検索 API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については[、「Microsoft 365 Defender Protection API](api-access.md)へのアクセス」を参照してください。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
-|-|-
アプリケーション | AdvancedHunting.Read.All | 高度なクエリを実行する
委任 (職場または学校アカウント) | AdvancedHunting.Read | 高度なクエリを実行する

>[!Note]
> ユーザー資格情報を使用してトークンを取得する場合:
>
>- ユーザーは"データの表示" 役割を持ADがあります。
>- ユーザーは、デバイス グループの設定に基づいて、デバイスにアクセスできる必要があります。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>要求ヘッダー

ヘッダー | 値
-|-
Authorization | Bearer {token} **注: 必須**
Content-Type | application/json

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター | 種類 | 説明
-|-|-
クエリ | テキスト | 実行するクエリ。 **注: 必須**

## <a name="response"></a>応答

成功した場合、このメソッドは応答本文で `200 OK` _QueryResponse_ オブジェクトを返します。

応答オブジェクトには、次の 3 つのトップ レベル プロパティが含まれる。

1. 統計 : クエリ パフォーマンス統計のディクショナリです。
2. スキーマ : 応答のスキーマ、各列のName-Typeのリスト。
3. 結果 - 高度な検索イベントの一覧。

## <a name="example"></a>例

次の例では、ユーザーは以下のクエリを送信し、, を含む API 応答 `Stats` オブジェクト `Schema` を受け取ります `Results` 。

### <a name="query"></a>クエリ

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Response オブジェクト

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API へのアクセス](api-access.md)
- [API の制限とライセンスについて](api-terms.md)
- [エラー コードを理解する](api-error-codes.md)
- [高度な検出の概要](advanced-hunting-overview.md)
