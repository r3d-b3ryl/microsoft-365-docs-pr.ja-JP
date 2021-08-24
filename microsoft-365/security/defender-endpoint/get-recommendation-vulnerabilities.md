---
title: 推奨事項による脆弱性の一覧表示
description: セキュリティ推奨事項に関連付けられている脆弱性の一覧を取得します。
keywords: apis、graph api、サポートされている api、get、脆弱性のリスト、セキュリティの推奨事項、脆弱性に関するセキュリティ推奨事項、脅威と脆弱性の管理、脅威と脆弱性の管理 api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8325f848281a37099e7a89eeda05d738c686b011
ms.sourcegitcommit: 4582873483bd52bc790bf75b838cc505dc4bbeb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58502737"
---
# <a name="list-vulnerabilities-by-recommendation"></a>推奨事項による脆弱性の一覧表示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

セキュリティ推奨事項に関連付けられている脆弱性の一覧を取得します。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Vulnerability.Read.All  |'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'
委任 (職場または学校のアカウント)|脆弱性。読み取り|'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、セキュリティの推奨事項に関連付けられている脆弱性の一覧を返します。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a>関連項目

- [リスクベースの脅威&の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [脅威&脆弱性のセキュリティに関する推奨事項](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
