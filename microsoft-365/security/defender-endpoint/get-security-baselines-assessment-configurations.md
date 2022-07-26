---
title: セキュリティ ベースラインの評価構成
description: "\"脅威と脆弱性の管理\" データをプルするセキュリティ ベースライン評価構成に関する情報を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。"
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device Vulnerability Assessment, device vulnerability report, secure configuration Assessment, secure configuration report, secure configuration report, software Vulnerabilities assessment, software Vulnerability report, software vulnerability report, vulnerability report by machine,
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 4b6360fd62eab766614ae9e0d2da76042cab6df6
ms.sourcegitcommit: 6e570b79944862c86735db455349b685d5b903b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67020497"
---
# <a name="list-security-baselines-assessment-configurations"></a>セキュリティ ベースライン評価構成を一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender 脆弱性の管理を体験しますか? [Microsoft Defender 脆弱性の管理パブリック プレビュー試用版](../defender-vulnerability-management/get-defender-vulnerability-management.md)にサインアップする方法の詳細については、こちらを参照してください。

## <a name="1-get-all-security-baselines-assessment-configurations"></a>1. すべてのセキュリティ ベースライン評価構成を取得する

この API は、使用可能なすべてのベンチマークについて、考えられるすべてのセキュリティ ベースライン評価構成と設定の一覧を取得します。

### <a name="11-parameters"></a>1.1 パラメーター

- OData V4 クエリをサポートしています
- OData でサポートされている演算子:
  - `$filter`on: `id`, , `name``category``CCE`
  - `$top` 最大値が 10,000 の場合
  - `$skip`

### <a name="12-http-request"></a>1.2 HTTP 要求

```http
GET /api/baselineConfigurations 
```

### <a name="13-request-headers"></a>1.3 要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

### <a name="14-response"></a>1.4 応答

成功した場合、このメソッドは本文内のベースライン構成の一覧で 200 OK を返します。

### <a name="15-properties"></a>1.5 プロパティ

|プロパティ | 種類 | 説明 |
|:---|:---|:---|
|Id | String | ベースライン ベンチマーク内の特定の構成の一意の識別子。
|name | String | その構成名がベンチマークに表示されます。
|description | String | ベンチマークに表示される構成の説明。
|category | String | ベンチマークに表示される構成カテゴリ。
|complianceLevel|String|この構成が表示されるベンチマークのコンプライアンス レベル。
|`cce`|Int|ベンチマークに表示されるこの構成の CCE。
|根拠 |String|ベンチマークに表示されるこの構成の根拠。 STIG ベンチマークの場合、この構成では指定されません。

## <a name="16-example"></a>1.6 例

### <a name="151-request-example"></a>1.5.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/baselineConfigurations
```

### <a name="162-response-example"></a>1.6.2 応答の例

```json
{
    "@odata.context": " https://api-df.securitycenter.microsoft.com/api/$metadata#BaselineConfigurations ", 
    "value": [
        {
            "id": "1.1.8", 
            "name": "(L1) Ensure 'Allow importing of payment info' is set to 'Disabled'",
            "description": "<p xmlns:xhtml=\"http://www.w3.org/1999/xhtml\">This policy setting controls whether users are able to import payment information from another browser into Microsoft Edge as well as whether payment information is imported on first use.</p>",
            "category": "Microsoft Edge",
            "complianceLevels": [
                "Level 1 (L1) - Corporate/Enterprise Environment (general use)",
                "Level 2 (L2) - High Security/Sensitive Data Environment (limited functionality)"
            ],
            "cce": "",
            "rationale": "<p xmlns:xhtml=\"http://www.w3.org/1999/xhtml\">Having payment information automatically imported or allowing users to import payment data from another browser into Microsoft Edge could allow for sensitive data to be imported into Edge.</p>",
            "remediation": "<div xmlns:xhtml=\"http://www.w3.org/1999/xhtml\">\r\n  <p>\r\n    <p>\r\nTo establish the recommended configuration via GP, set the following UI path to                 <span class=\"inline_block\">Disabled</span></p>\r\n    <code class=\"code_block\">Computer Configuration\\Policies\\Administrative Templates\\Microsoft Edge\\Allow importing of payment info\r\n</code>\r\n    <p>\r\n      <strong>Note:</strong>\r\n This Group Policy path may not exist by default. It is provided by the Group Policy template                 <span class=\"inline_block\">MSEdge.admx/adml</span>\r\n that can be downloaded from Microsoft                 <a href=\"https://www.microsoft.com/en-us/edge/business/download\">here</a>\r\n.              </p>\r\n    <p class=\"bold\">Impact:</p>\r\n    <p>\r\n      <p>Users will be unable to perform a payment information import from other browsers into Microsoft Edge.</p>\r\n    </p>\r\n  </p>\r\n</div>",
            "benchmarkName": "CIS"
"recommendedValue": [ 
                "Equals '0'" 
            ], 
            "source": [ 
                "hkey_local_machine\\software\\policies\\microsoft\\windows\\eventlog\\security\\retention" 
            ]
        }, 
    ] 
} 
```

## <a name="see-also"></a>関連項目

- [セキュリティ ベースライン評価のエクスポート](export-security-baseline-assessment.md)
- [セキュリティ ベースライン評価プロファイルを取得する](get-security-baselines-assessment-profiles.md)
