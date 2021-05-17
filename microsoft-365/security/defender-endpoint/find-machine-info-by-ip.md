---
title: 内部 IP API によるデバイス情報の検索
description: この API を使用して、内部 IP による特定のタイムスタンプの周りのデバイス エントリの検索に関連する呼び出しを作成します。
keywords: ip、apis、graph api、サポートされている API、デバイス、デバイス情報の検索
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167140"
---
# <a name="find-device-information-by-internal-ip-api"></a>内部 IP API によるデバイス情報の検索

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

内部 IP でデバイスを検索します。

>[!NOTE]
>タイムスタンプは、過去 30 日以内である必要があります。

## <a name="permissions"></a>アクセス許可
この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
:---|:---|:---
アプリケーション | Machine.Read.All | 'すべてのコンピューター プロファイルを読み取る'
アプリケーション | Machine.ReadWrite.All | 'すべてのコンピューター情報の読み取りと書き込み'

## <a name="http-request"></a>HTTP 要求
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a>要求ヘッダー

名前 | 型 | 説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**


## <a name="request-body"></a>要求本文
Empty

## <a name="response"></a>応答
成功し、コンピューターが存在する場合 - 200 OK。
コンピューターが見つからない場合 - 404 が見つかりません。


## <a name="example"></a>例

**要求**

以下は、要求の例です。

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

**応答**

以下は、応答の例です。

この応答は、タイムスタンプの 16 分前および後にこの IP アドレスを報告したすべてのデバイスの一覧を返します。 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
