---
title: セキュリティ ベースライン評価プロファイル
description: "\"Microsoft Defender 脆弱性の管理\" データをプルするセキュリティ ベースライン評価プロファイル API に関する情報を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。"
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
ms.openlocfilehash: f619efaa3ef258405a45bd747fa2f3e2850d0a21
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67345039"
---
# <a name="list-all-security-baselines-assessment-profiles"></a>すべてのセキュリティ ベースライン評価プロファイルを一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender 脆弱性の管理を体験するには [Microsoft Defender 脆弱性の管理パブリック プレビュー試用版](../defender-vulnerability-management/get-defender-vulnerability-management.md)にサインアップする方法について説明します。

## <a name="1-get-security-baselines-assessment-profiles"></a>1. セキュリティ ベースライン評価プロファイルを取得する

この API は、組織によって作成されたすべてのセキュリティ ベースライン評価プロファイルの一覧を取得します。

### <a name="11-parameters"></a>1.1 パラメーター

- OData V4 クエリをサポートします。
- OData でサポートされている演算子:
  - $filter on: id,name, operatingSystem, operatingSystemVersion, status, settingsNumber, passedDevices, totalDevices
  - 最大値が 10,000 の$top。
  - $skip。

### <a name="12-http-request"></a>1.2 HTTP 要求

```http
GET:/api/baselineProfiles
```

### <a name="13-request-headers"></a>1.3 要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

### <a name="14-properties"></a>1.4 プロパティ

|プロパティ | 種類 | 説明 |
|:---|:---|:---|
|ID | String | 特定のベースライン プロファイルの一意の識別子。
|name | String | プロファイル名。
|説明 | String | プロファイルの説明。
|ベンチマーク | 文字列 | プロファイル ベンチマーク。
|version | String | プロファイルのバージョン。
|operatingSystem|String|適用可能なオペレーティング システムのプロファイル。
|operatingSystemVersion|String|該当するオペレーティング システムのバージョンのプロファイル。
|status|ブール型|プロファイルがアクティブかどうかを示します
|complianceLevel|文字列|プロファイルに対して選択されたコンプライアンス レベル。
|settingsNumber|Int|プロファイルで選択された構成の数。
|createdBy|String|このプロファイルを作成したユーザー。
|lastUpdatedBy|DateTime|このプロファイルを変更する最後のユーザー。
|createdOnTimeOffset|DateTime|プロファイルが作成された日時。
|lastUpdateTimeOffset|DateTime|プロファイルが最後に更新された日時。
|passedDevices|Int|すべてのプロファイル構成に準拠するこのプロファイルに適用できるデバイスの数。
|totalDevices|Int|このプロファイルに適用できるデバイスの数。

## <a name="15-example"></a>1.5 例

### <a name="151-request-example"></a>1.5.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/baselineProfiles
```

### <a name="162-response-example"></a>1.6.2 応答の例

```json
{
    "@odata.context": "https:// api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicBaselineProfileDto)",
    "value":
    [
        {
            "id": "02bcbb9d-d197-479e-811e-1cd5a6f9f8fa",
            "name": "Windows 10 build 1909 CIS profile",
            "description": "important",
            "benchmark": "CIS",
            "version": "1.0.0",
            "operatingSystem": "Windows 10",
            "operatingSystemVersion": "1909",
            "status": true,
            "complianceLevel": "Level 1 (L1) - Corporate/Enterprise Environment (general use)",
            "settingsNumber": 51,
            "createdBy": "user@org.net",
            "lastUpdatedBy": null,
            "createdOnTimestampUTC": "0001-01-01T00:00:00Z",
            "lastUpdateTimestampUTC": "0001-01-01T00:00:00Z",
            "passedDevices": 0,
            "totalDevices": 10
        }
     ]
}
```

## <a name="see-also"></a>関連項目

- [セキュリティ ベースライン評価のエクスポート](export-security-baseline-assessment.md)
- [セキュリティ ベースライン評価構成を取得する](get-security-baselines-assessment-configurations.md)
