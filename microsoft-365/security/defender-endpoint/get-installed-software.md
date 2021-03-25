---
title: インストールされているソフトウェアを取得する
description: 特定のデバイス ID に関連するインストール済みソフトウェアのコレクションを取得します。
keywords: apis、 graph api、 supported apis, get, list, file, information, software inventory, installed software per device, threat & vulnerability management api, mdatp tvm api
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
ms.technology: mde
ms.openlocfilehash: 6164020ef05561563fe0434bd2edac8c7b3e689a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166810"
---
# <a name="get-installed-software"></a>インストールされているソフトウェアを取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

特定のデバイス ID に関連するインストール済みソフトウェアのコレクションを取得します。

## <a name="permissions"></a>アクセス許可
この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類 |   アクセス許可  |   アクセス許可の表示名
:---|:---|:---
アプリケーション |Software.Read.All |    '脅威と脆弱性管理ソフトウェア情報の読み取り'
委任 (職場または学校のアカウント) | Software.Read |    '脅威と脆弱性管理ソフトウェア情報の読み取り'

## <a name="http-request"></a>HTTP 要求
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a>要求ヘッダー

名前 | 種類 | 説明
:---|:---|:---
Authorization | 文字列 | ベアラー {token}。 **必須**


## <a name="request-body"></a>要求本文
Empty

## <a name="response"></a>応答
成功した場合、このメソッドは、本文にインストールされているソフトウェア情報を含む 200 OK を返します。


## <a name="example"></a>例

**要求**

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

**応答**

以下は、応答の例です。


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a>関連項目

- [リスクベースの脅威&の管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [脅威&ソフトウェア インベントリ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
