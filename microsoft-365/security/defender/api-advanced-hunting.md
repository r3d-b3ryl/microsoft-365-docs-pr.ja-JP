---
title: 高度なハンティング API Microsoft 365 Defender
description: Microsoft 365 Defenderの高度なハンティング API を使用して高度なハンティング クエリを実行する方法について説明します
keywords: 高度なハンティング、API、API、M365 Defender、Microsoft 365 Defender
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
ms.openlocfilehash: d01cdacc40b58eb940b2773606221b4fdbe18728
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823192"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender 高度なハンティング API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

[高度なハンティング](advanced-hunting-overview.md)は、[特別に構築されたクエリ](advanced-hunting-query-language.md)を使用して、Microsoft 365 Defenderの過去 30 日間のイベント データを調べる脅威検出ツールです。 高度なハンティング クエリを使用して、異常なアクティビティを検査し、潜在的な脅威を検出し、攻撃に対応することもできます。 高度なハンティング API を使用すると、プログラムによってイベント データにクエリを実行できます。

## <a name="quotas-and-resource-allocation"></a>クォータとリソースの割り当て

次の条件は、すべてのクエリに関連します。

1. クエリは、過去 30 日間のデータを調査して返します。
2. 結果は最大 100,000 行を返すことができます。
3. テナントごとに 1 分あたり最大 45 回の呼び出しを行うことができます。
4. テナントが 100% に達した場合、次の 15 分のサイクル終了までクエリはブロックされます。
5. 1 つの要求が 10 分を超えて実行されると、タイムアウトしてエラーが返されます。
6. HTTP 応答コードは `429` 、送信された要求の数または割り当てられた実行時間によって、クォータに達したことを示します。 応答本文を読み、上限に達したことを理解します。 

> [!NOTE]
> 上記のすべてのクォータ (たとえば、1 分あたり 15 回の呼び出し) は、テナント サイズごとです。 これらのクォータは最小です。

## <a name="permissions"></a>アクセス許可

高度なハンティング API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft 365 Defender Protection API にアクセスする」を](api-access.md)参照してください。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
-|-|-
アプリケーション | AdvancedHunting.Read.All| 高度なクエリを実行する
委任 (職場または学校のアカウント) | AdvancedHunting.Read | 高度なクエリを実行する

>[!Note]
> ユーザー資格情報を使用してトークンを取得する場合:
>
>- ユーザーが "データの表示" AD ロールを持っている必要がある
>- ユーザーは、デバイス グループの設定に基づいて、デバイスにアクセスできる必要があります。

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

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター | 型 | 説明
-|-|-
Query | テキスト | 実行するクエリ。 **注: 必須**

## <a name="response"></a>応答

成功した場合、このメソッドは応答本文に _QueryResponse_ オブジェクトを返`200 OK`します。

応答オブジェクトには、次の 3 つの最上位レベルのプロパティが含まれています。

1. 統計 - クエリパフォーマンス統計のディクショナリ。
2. スキーマ - 応答のスキーマ、各列のName-Typeペアの一覧。
3. 結果 - 高度なハンティング イベントの一覧。

## <a name="example"></a>例

次の例では、ユーザーは以下のクエリを送信し、次の値を含む API 応答オブジェクトを`Stats``Schema`受信します`Results`。

### <a name="query"></a>Query

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>応答オブジェクト

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

- [Microsoft 365 Defender API にアクセスする](api-access.md)
- [API の制限とライセンスについて学習する](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [高度な追求の概要](advanced-hunting-overview.md)
