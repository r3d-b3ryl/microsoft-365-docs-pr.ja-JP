---
title: すべての推奨事項を一覧表示する
description: 組織に影響を与えるすべてのセキュリティに関する推奨事項の一覧を取得します。
keywords: apis, graph api, サポートされている api, get, security recommendations, Microsoft Defender for Endpoint tvm api, 脅威と脆弱性の管理, 脅威と脆弱性の管理 api, mdvm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c420d73326cc9965f0b4a5d57af5adba83c30f1d
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67343089"
---
# <a name="list-all-recommendations"></a>すべての推奨事項を一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

組織に影響を与えるすべてのセキュリティに関する推奨事項の一覧を取得します。


## <a name="api-description"></a>API の説明

組織に影響を与えるすべてのセキュリティに関する推奨事項に関する情報を返します。

*Url：* GET:/api/recommendations
<br>[OData V4 クエリ](https://www.odata.org/documentation/)をサポートします。
<br>OData でサポートされている演算子:
<br>```$filter```on: ```id```, , ```productName```, ```vendor```, ```recommendedVersion```, ```subCategory``````recommendationCategory```, ```severityScore```, ```remediationType```, ```recommendedProgram```, ```recommendedVendor```, および```status```プロパティ。
<br>```$top``` 最大値が 10,000 です。
<br>```$skip```.
<br>[Microsoft Defender for Endpointを使用した OData クエリの](exposed-apis-odata-samples.md)例を参照してください。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[エンドポイント API に Microsoft Defender を使用する](apis-intro.md)」を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|SecurityRecommendation.Read.All|'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'
委任 (職場または学校のアカウント)|SecurityRecommendation.Read |'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/recommendations
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは本文のセキュリティに関する推奨事項の一覧を含む 200 OK を返します。

## <a name="example"></a>例

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

### <a name="response"></a>応答

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10" "va-_-microsoft-_-windows_11",
            "productName": "windows_10" "Windows_11",
            "recommendationName": "Update Windows 10" "Update Windows 11",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10" "Windows 11"
        }
        ...
     ]
}
```

## <a name="see-also"></a>関連項目

- [Microsoft Defender 脆弱性の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [脆弱性管理のセキュリティに関する推奨事項](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
