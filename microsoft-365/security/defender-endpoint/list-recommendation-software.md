---
title: 推奨されるソフトウェアを一覧表示する
description: 特定のソフトウェアに関連するセキュリティ推奨事項を取得します。
keywords: apis、graph api、サポートされている api、get、セキュリティ推奨事項、ソフトウェアのセキュリティ推奨事項、脅威と脆弱性の管理、脅威と脆弱性の管理 API
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
ms.openlocfilehash: 1d5ca404554d667ae9c36533fc1ad9cb866caff7
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302400"
---
# <a name="list-software-by-recommendation"></a>推奨されるソフトウェアを一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

特定のソフトウェアに関連するセキュリティ推奨事項を取得します。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Software.Read.All|'脅威と脆弱性管理ソフトウェア情報の読み取り'
委任 (職場または学校のアカウント)|SecurityRecommendation.Read|'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'

## <a name="http-request"></a>HTTP 要求

```http
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a>要求ヘッダー

名前|型|説明
:---|:---|:---
Authorization|String|ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは、本文のセキュリティ推奨事項に関連付けられたソフトウェアで 200 OK を返します。

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

### <a name="response-example"></a>応答の例

以下は、応答の例です。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a>関連トピック

- [リスクベースの脅威&の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [脅威&脆弱性のセキュリティに関する推奨事項](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
