---
title: IP 統計 API の取得
description: Microsoft Defender for Endpoint を使用して、IP の最新の統計情報を取得します。
keywords: apis, graph api, supported apis, get, ip, statistics, prevalence
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
ms.openlocfilehash: 673f6f92b96cb1cbe42c2fa513aa3c57713be88f
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622942"
---
# <a name="get-ip-statistics-api"></a>IP 統計 API の取得

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明
指定した IP の統計情報を取得します。

## <a name="limitations"></a>制限事項
1. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Ip.Read.All|'IP アドレス プロファイルの読み取り'
委任 (職場または学校のアカウント)|Ip.Read.All|'IP アドレス プロファイルの読み取り'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
> - ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**

## <a name="request-uri-parameters"></a>要求 URI パラメーター

名前|種類|説明
:---|:---|:---
lookBackHours|Int32|統計を取得するために検索する時間を定義します。 既定値は 30 日です。 **オプション**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合と ip が存在する場合 - 200 OK 本文の統計データを使用します。 IP が存在しない - 404 が見つかりません。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```

|名前|説明|
|---|---|
|組織の普及率|この IP へのネットワーク接続を開いたデバイスの個別の数。|
|組織が最初に見られた|組織内のこの IP の最初の接続。|
|組織が最後に見た|組織内のこの IP の最後の接続。|

> [!NOTE]
> この統計情報は、過去 30 日間のデータに基づいて行われます。
