---
title: ソフトウェアによる脆弱性の一覧表示
description: インストールされているソフトウェアの脆弱性の一覧を取得します。
keywords: apis, graph api, supported api, get, vulnerabilities list, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 9f70cba0d749238b9602f88b27d96aec87a5139b
ms.sourcegitcommit: 4582873483bd52bc790bf75b838cc505dc4bbeb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58502845"
---
# <a name="list-vulnerabilities-by-software"></a>ソフトウェアによる脆弱性の一覧表示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

インストールされているソフトウェアの脆弱性の一覧を取得します。 

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Vulnerability.Read.All|'脅威と脆弱性管理ソフトウェア情報の読み取り'
委任 (職場または学校のアカウント)|脆弱性。読み取り|'脅威と脆弱性管理ソフトウェア情報の読み取り'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a>要求ヘッダー

|名前|型|説明
|---|---|---|
|Authorization|String|ベアラー {token}。**必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、指定したソフトウェアによって公開される脆弱性の一覧を返します。 

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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
