---
title: マシンの一覧表示 API
description: List machines API を使用して、クラウドと通信したマシンのコレクションMicrosoft Defender for Endpoint取得する方法について説明します。
keywords: apis, graph api, サポートされている API, get, devices
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection: M365-security-compliance
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6e522f2baac234097ed75d26eb1427719211a7de
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284651"
---
# <a name="list-machines-api"></a>マシンの一覧表示 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

Microsoft Defender for Endpoint クラウドと通信した [Machines](machine.md) のコレクションを取得します。

[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。

OData の`$filter`クエリは、次`riskScore``exposureLevel``lastSeen``onboardingStatus``machineTags``lastIpAddress``aadDeviceId``rbacGroupId``id``osPlatform``version``healthStatus``deviceValue`のようにサポートされています。 `computerDnsName`
<br>```$stop``` 最大値が 10,000 の場合
<br>```$skip```[Defender for Endpoint を使用した OData クエリの例を](exposed-apis-odata-samples.md)参照してください

## <a name="limitations"></a>制限事項

1. 構成された保有期間に従って、最後に表示されたデバイスを取得できます。
2. 最大ページ サイズは 10,000 です。
3. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。 

## <a name="permissions"></a>アクセス許可

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Machine.Read.All|'すべてのマシン プロファイルを読み取る'
アプリケーション|Machine.ReadWrite.All|'すべてのマシン情報の読み取りと書き込み'
委任 (職場または学校のアカウント)|Machine.Read|'マシン情報の読み取り'
委任 (職場または学校のアカウント)|Machine.ReadWrite|'マシン情報の読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロールアクセス許可が必要です:"データの表示" (詳細については、「 [ロールの作成と管理](user-roles.md) 」を参照)
> - 応答には、デバイス グループの設定に基づいて、ユーザーがアクセスできるデバイスのみが含まれます (詳細については、「 [デバイス グループの作成と管理](machine-groups.md) 」を参照)

## <a name="http-request"></a>HTTP 要求

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功し、マシンが存在する場合は、本文内の [マシン](machine.md) エンティティの一覧を含む 200 OK です。 最近使用したマシンがない場合は、404 が見つかりません。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10" "Windows11",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpointを使用した OData クエリ](exposed-apis-odata-samples.md)
