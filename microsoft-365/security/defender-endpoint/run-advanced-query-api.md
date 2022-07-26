---
title: 高度な追求 API
ms.reviewer: ''
description: 高度なハンティング API を使用して、Microsoft Defender for Endpointで高度なクエリを実行する方法について説明します。 制限事項について確認し、例を参照してください。
keywords: apis, サポートされている API, 高度な捜索, クエリ
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
ms.openlocfilehash: 9f361a404ec3f8893ff4573fdc4db29904a5e766
ms.sourcegitcommit: 6e570b79944862c86735db455349b685d5b903b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67020629"
---
# <a name="advanced-hunting-api"></a>高度なハンティング API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> [!NOTE]
> この API では、Microsoft Defender for Endpointに属するテーブルにのみクエリを実行できます。 他のMicrosoft 365 Defender サービスに属するテーブルでは、[Microsoft 365 Defender Advanced hunting API](/microsoft-365/security/defender/api-advanced-hunting) を使用する必要があります。

## <a name="limitations"></a>制限事項

1. 過去 30 日間のデータに対してのみクエリを実行できます。

2. 結果には最大 100,000 行が含まれます。

3. テナントごとに実行回数が制限されます。
   - API 呼び出し: 1 分あたり最大 45 回の呼び出し、1 時間あたり最大 1500 回の呼び出し。
   - 実行時間: 1 時間ごとに実行時間が 10 分、実行時間が 1 日に 3 時間です。

4. 1 つの要求の最大実行時間は 10 分です。

5. 429 応答は、要求の数または CPU によってクォータ制限に達することを表します。 応答本文を読み取って、どの制限に達したかを理解します。

6. 1 つの要求のクエリ結果の最大サイズは 124 MB を超えることはできません。 超過した場合は、"クエリの実行が許可された結果サイズを超えました。 結果の量を制限してクエリを最適化し、もう一度やり直してください"と表示されます。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|AdvancedQuery.Read.All|'高度なクエリを実行する'
委任 (職場または学校のアカウント)|AdvancedQuery.Read|'高度なクエリを実行する'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーが "データの表示" AD ロールを持っている必要がある
> - ユーザーは、デバイス グループの設定に基づいてデバイスにアクセスできる必要があります (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>要求ヘッダー

ヘッダー|値
:---|:---
Authorization|ベアラー {token}。 **必須**。
Content-Type|application/json

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含む JSON オブジェクトを指定します。

パラメーター|種類|説明
:---|:---|:---
Query|テキスト|実行するクエリ。 **必須**。

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、応答本文で _QueryResponse_ オブジェクトを返します。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents
|where InitiatingProcessFileName =~ 'powershell.exe'
|where ProcessCommandLine contains 'appdata'
|project Timestamp, FileName, InitiatingProcessFileName, DeviceId
|limit 2"
}
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

> [!NOTE]
> 簡潔にするために、ここに示す応答オブジェクトが切り捨てられる場合があります。 実際の呼び出しではすべてのプロパティが返されます。

```json
{
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
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint API の概要](apis-intro.md)
- [ポータルからの高度なハンティング](advanced-hunting-query-language.md)
- [PowerShell を使用した高度な追求](run-advanced-query-sample-powershell.md)
