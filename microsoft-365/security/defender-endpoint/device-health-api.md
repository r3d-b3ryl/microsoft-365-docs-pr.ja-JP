---
title: Microsoft Defender ウイルス対策デバイスの正常性の詳細 API
description: Microsoft Defender ウイルス対策デバイスの正常性の詳細のリストを取得します。
keywords: API, グラフ API, サポートされている API, GET, デバイス正常性 API, Microsoft Defender for Endpoint レポート API Microsoft Defender レポート API, Microsoft Defender for Endpoint レポート API, Windows Defender レポート API, Defender for Endpoint レポート API, Windows Defender レポート API
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
ms.date: 08/08/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 11276ce633a0259b04ee0ea7a984fc9b9c8eeb8c
ms.sourcegitcommit: 402e0b2095b6cb141b8525a53194d47357bcd612
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2022
ms.locfileid: "67285226"
---
# <a name="microsoft-defender-antivirus-device-health-details-api"></a>Microsoft Defender ウイルス対策デバイスの正常性の詳細 API

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>API の説明

Microsoft Defender ウイルス対策デバイスの正常性の詳細のリストを取得します。
URL: GET: /api/public/avdeviceshealth
<br>[OData V4 クエリ](https://www.odata.org/documentation/)をサポートします。
<br>OData でサポートされている演算子:
<br>```$filter``` on: ```machineId```, ```computerDnsName```, ```osKind```, ```osPlatform```, ```osVersion```, a```vMode```, ```avSignatureVersion```, ```avEngineVersion```, ```avPlatformVersion```, ```quickScanResult```, ```quickScanError```, ```fullScanResult```, ```fullScanError```, ```avIsSignatureUpToDate```, ```avIsEngineUpToDate```, ```vIsPlatformUpToDate```, ```rbacGroupId```
<br>```$top``` 最大値が 10,000 です。
<br>```$skip```.
<br>[Microsoft Defender for Endpoint を使用した OData クエリ](exposed-apis-odata-samples.md] の例を参照してください

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[エンドポイント API に Microsoft Defender を使用する](apis-intro.md)」を参照してください。

| アクセス許可の種類 | アクセス許可 | アクセス許可の表示名 |
|:----|:----|:----|
| アプリケーション | Machine.Read.All | 'すべてのマシン プロファイルを読み取る' |
| アプリケーション | Machine.ReadWrite.All | 'すべてのマシン情報の読み取りと書き込み' |
| 委任 (職場または学校のアカウント) | Machine.Read | 'マシン情報の読み取り' |
| 委任 (職場または学校のアカウント) | Macine.ReadWrite | 'マシン情報の読み取りと書き込み' |

## <a name="http-request"></a>HTTP 要求

```http
GET /api/public/avdeviceshealth
```

## <a name="request-headers"></a>要求ヘッダー

| 名前 | 種類 | 説明 |
|:----|:----|:----|
| Authorization | String | ベアラー {token}。 **必須** |

## <a name="request-body"></a>要求本文

_空_

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK をデバイスの正常性の詳細のリストと共に返します。

## <a name="example"></a>例

### <a name="example-request"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/public/avdeviceshealth 
```

### <a name="example-response"></a>応答の例

以下は、応答の例です。

```json
{ 

    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#avdeviceshealth", 

    "value": [ 

        { 

           "id": "sampleId", 

           "machineId": "sampleMachineId", 

           "computerDnsName": "sampleDnsName", 

           "osKind": "mac", 

           "osPlatform": "macOS", 

           "osVersion": "11.6.5.0", 

           "avMode": "0", 

           "avSignatureVersion": "87523", 

           "avEngineVersion": "3.0", 

           "avPlatformVersion": "101.61.69", 

           "lastSeenTime": "2022-04-02T06:12:07+00:00", 

           "quickScanResult": "-", 

           "quickScanError": "-", 

           "fullScanResult": "-", 

           "fullScanError": "-", 

           "dataRefreshTimestamp": "2022-04-06T21:50:48+00:00", 

           "avSignatureUpdateTime": "2022-04-01T01:31:58+00:00", 

           "avIsSignatureUpToDate": "Unknown", 

           "avIsEngineUpToDate": "Unknown", 

           "avIsPlatformUpToDate": "Unknown", 

           "rbacGroupId": 86 

        }, 

        ... 

     ] 

}  
```

## <a name="see-also"></a>関連項目

[Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート](machine-reports.md)
