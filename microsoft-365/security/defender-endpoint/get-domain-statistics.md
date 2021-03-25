---
title: ドメイン統計 API の取得
description: Get domain statistics API を使用して、Microsoft Defender for Endpoint の特定のドメインの統計情報を取得する方法について説明します。
keywords: apis、graph api、サポートされている API、get、ドメイン、ドメイン関連デバイス
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
ms.technology: mde
ms.openlocfilehash: eef06657d7f691a89e5985640431c2cc706557b4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167139"
---
# <a name="get-domain-statistics-api"></a>ドメイン統計 API の取得

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API の説明
指定したドメインの統計情報を取得します。


## <a name="limitations"></a>制限事項
1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。


## <a name="permissions"></a>アクセス許可
この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類 |   アクセス許可  |   アクセス許可の表示名
:---|:---|:---
アプリケーション |   URL。Read.All |  'URL の読み取り'
委任 (職場または学校のアカウント) | URL。Read.All | 'URL の読み取り'

>[!Note]
> ユーザー資格情報を使用してトークンを取得する場合:
>- ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>要求ヘッダー

ヘッダー | 値 
:---|:---
Authorization | ベアラー {token}。 **必須**

## <a name="request-uri-parameters"></a>要求 URI パラメーター

Name | 種類 | 説明
:---|:---|:---
lookBackHours | Int32 | 統計を取得するために検索する時間を定義します。 既定値は 30 日です。 **オプション**。

## <a name="request-body"></a>要求本文
Empty

## <a name="response"></a>応答
成功し、ドメインが存在する場合 - 200 OK、応答本文に statistics オブジェクト。 ドメインが存在しない場合 - 404 が見つかりません。


## <a name="example"></a>例

**要求**

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

**応答**

以下は、応答の例です。


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
