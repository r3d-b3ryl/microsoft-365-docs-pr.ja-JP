---
title: コンピューターとソフトウェアによってすべての脆弱性を取得する
description: コンピューターとソフトウェアによって組織に影響を与えるすべての脆弱性の一覧を取得します。
keywords: apis, graph api, supported api, get, vulnerability information, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: f4c50b9058510f07ef1e64bbfe2c01198a2cc78d02af1d4474e0cf1e6ba362c5
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53793876"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>マシンとソフトウェアによる脆弱性の一覧表示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

コンピューターとソフトウェアごとに組織に影響を与えるすべての脆弱性の一覧 [を](machine.md) 取得 [します](software.md)。

- 脆弱性に修正 KB がある場合は、応答に表示されます。
- [OData V4 クエリをサポートします](https://www.odata.org/documentation/)。
- OData ```$filter``` は、すべてのプロパティでサポートされています。

> [!TIP]
> これは、統合のための素晴らしい API [Power BIです](api-power-bi.md)。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Vulnerability.Read.All|'脅威と脆弱性管理の脆弱性情報の読み取り'
委任 (職場または学校のアカウント)|脆弱性。読み取り|'脅威と脆弱性管理の脆弱性情報の読み取り'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、本文の脆弱性の一覧を返します。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>関連項目

- [リスクベースの脅威と脆弱性の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [組織の脆弱性](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
