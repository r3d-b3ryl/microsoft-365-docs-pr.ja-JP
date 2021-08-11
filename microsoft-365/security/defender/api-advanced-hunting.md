---
title: Microsoft 365 Defender高度なハンティング API
description: 高度な検索 API を使用して高度なMicrosoft 365 Defenderを実行する方法について説明します。
keywords: Advanced Hunting, API, api, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: 4064a2d4469fb842a6446c1a869de44a48f2b627cdb25ae4f7999a255c3d04f2
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53792916"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender高度なハンティング API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

[高度な検索](advanced-hunting-overview.md)は、特別に構築されたクエリ[](advanced-hunting-query-language.md)を使用して、過去 30 日間のイベント データを調査する脅威Microsoft 365 Defender。 高度な検索クエリを使用して、異常なアクティビティを検査し、可能な脅威を検出し、攻撃にも対応できます。 高度な検索 API を使用すると、イベント データをプログラムでクエリできます。

## <a name="quotas-and-resource-allocation"></a>クォータとリソース割り当て

次の条件は、すべてのクエリに関連します。

1. クエリは、過去 30 日間のデータを探索して返します。
2. 結果は、最大 100,000 行を返す場合があります。
3. テナントごとに 1 分あたり最大 15 回の呼び出しを行います。
4. テナントが次の 15 分のサイクルの後まで 100% に達した場合、クエリはブロックされます。
5. 1 つの要求が 10 分以上実行された場合、その要求はタイム アウトし、エラーを返します。
6. HTTP 応答コードは、送信された要求の数または割り当てられた実行時間のいずれかによって、クォータに達 `429` したかどうかを示します。 応答本文を読んで、到達した制限を理解します。 

> [!NOTE]
> 上記のすべてのクォータ (たとえば、1 分あたり 15 回の呼び出し) はテナント サイズごとに設定されます。 これらのクォータは最小です。

## <a name="permissions"></a>アクセス許可

高度な検索 API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については[、「Access the Microsoft 365 Defender保護 API」を参照してください。](api-access.md)

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
-|-|-
アプリケーション | AdvancedHunting.Read.All | 高度なクエリを実行する
委任 (職場または学校のアカウント) | AdvancedHunting.Read | 高度なクエリを実行する

>[!Note]
> ユーザー資格情報を使用してトークンを取得する場合:
>
>- ユーザーは、"データの表示" ロールを持AD必要があります
>- ユーザーは、デバイス グループの設定に基づいて、デバイスにアクセスする必要があります。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>要求ヘッダー

ヘッダー | 値
-|-
Authorization | ベアラー {token} **注: 必須**
Content-Type | application/json

## <a name="request-body"></a>要求本文

要求本文で、JSON オブジェクトに次のパラメーターを指定します。

パラメーター | 種類 | 説明
-|-|-
Query | テキスト | 実行するクエリ。 **注: 必須**

## <a name="response"></a>応答

成功した場合、このメソッドは `200 OK` 応答本文の _QueryResponse_ オブジェクトを返します。

応答オブジェクトには、次の 3 つのトップ レベル プロパティが含まれる。

1. 統計 - クエリパフォーマンス統計の辞書。
2. Schema - 応答のスキーマ、各列のName-Typeの一覧。
3. 結果 - 高度な狩猟イベントの一覧。

## <a name="example"></a>例

次の例では、ユーザーが以下のクエリを送信し、、 、および を含む API 応答オブジェクト `Stats` `Schema` を受け取ります `Results` 。

### <a name="query"></a>Query

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

- [API にMicrosoft 365 Defenderする](api-access.md)
- [API の制限とライセンスの詳細](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [高度な追求の概要](advanced-hunting-overview.md)
