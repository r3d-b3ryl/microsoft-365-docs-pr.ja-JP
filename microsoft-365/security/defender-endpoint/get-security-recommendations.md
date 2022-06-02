---
title: セキュリティ上の推奨事項を取得する
description: 特定のデバイス ID に関連するセキュリティに関する推奨事項のコレクションを取得します。
keywords: apis, graph api, サポートされている API, get, list, file, information, security recommendation per device, threat & 脆弱性の管理 api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: ebe07abd4e7f87e7abfe4d4a8ccd131e20dc4958
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65839714"
---
# <a name="get-security-recommendations"></a>セキュリティ上の推奨事項を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

特定のデバイス ID に関連するセキュリティに関する推奨事項のコレクションを取得します。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API の使用」を](apis-intro.md)参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|SecurityRecommendation.Read.All|'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'
委任 (職場または学校のアカウント)|SecurityRecommendation.Read|'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは本文のセキュリティに関する推奨事項を含む 200 OK を返します。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
...
}
```

## <a name="related-topics"></a>関連項目

- [リスクベースの脅威&脆弱性管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [脅威&脆弱性のセキュリティに関する推奨事項](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
