---
title: Id でソフトウェアを取得する
description: デバイス グループ別の露出スコアの一覧を取得します。
keywords: apis, graph api, supported apis, get, software, mdatp tvm api
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
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198591"
---
# <a name="get-software-by-id"></a>Id でソフトウェアを取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

ソフトウェアの詳細を ID で取得します。

## <a name="permissions"></a>アクセス許可
この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。

アクセス許可の種類 |   アクセス許可  |   アクセス許可の表示名
:---|:---|:---
アプリケーション | Software.Read.All | '脅威と脆弱性管理ソフトウェア情報の読み取り'
委任 (職場または学校のアカウント) | Software.Read | '脅威と脆弱性管理ソフトウェア情報の読み取り'

## <a name="http-request"></a>HTTP 要求
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a>要求ヘッダー

| 名前        | 種類 | 説明
|:--------------|:-------|:--------------|
| Authorization | 文字列 | ベアラー {token}。**必須**。

## <a name="request-body"></a>要求本文
Empty

## <a name="response"></a>応答
成功した場合、このメソッドは 200 OK を返し、本文に指定されたソフトウェア データを返します。 


## <a name="example"></a>例

**要求**

以下は、要求の例です。

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

**応答**

以下は、応答の例です。

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a>関連項目
- [リスクベースの脅威&の管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [脅威&ソフトウェア インベントリ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
