---
title: ライブ応答ライブラリにファイルをアップロードする
description: ライブ応答ライブラリにファイルをアップロードする方法について説明します。
keywords: apis、graph api、サポートされている API、ライブラリへのアップロード
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8e0bc9ca78a7e0baad7c07e73790215618aff9ab
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65873741"
---
#  <a name="upload-files-to-the-live-response-library"></a>ライブ応答ライブラリにファイルをアップロードする  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

[!include[Prerelease information](../../includes/prerelease.md)]

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

ファイルをライブ応答ライブラリにアップロードします。

## <a name="limitations"></a>制限事項

1.  ファイルの最大サイズ制限は 20 MB です。

2.  この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[概要](apis-intro.md)」を参照してください。


| アクセス許可の種類                    | アクセス許可     | アクセス許可の表示名        |
|------------------------------------|----------------|--------------------------------|
| アプリケーション                        | Library.Manage | ライブ応答ライブラリを管理する |
| 委任 (職場または学校のアカウント) | Library.Manage | ライブ応答ライブラリを管理する |

## <a name="http-request"></a>HTTP 要求

アップロード

```HTTP
POST https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="request-headers"></a>要求ヘッダー

|  名前   |    型    |       説明                         |
|-----------------|--------|--------------------------------|
| Authorization   | String | ベアラー\<token>。 必須です。      |
| Content-Type    | string | multipart/form-data。 必須です。 |

## <a name="request-body"></a>要求本文

要求本文で、次のパラメーターを含むフォーム データ オブジェクトを指定します。

| パラメーター         |     型         |       説明                                        |
|-----------------------|--------------|------------------------------------------------------------|
| ファイル                  | ファイルの内容 | ライブ応答ライブラリにアップロードするファイル。必須 |
| 説明           | String       | ファイルの説明。                                  |
| ParametersDescription | String       | (省略可能)スクリプトを実行するために必要なパラメーター。 既定値は空の文字列です。                |
| OverrideIfExists      | Boolean      | (省略可能)ファイルが既に存在する場合は、ファイルをオーバーライドするかどうかを指定します。 既定値は空の文字列です。          |



## <a name="response"></a>応答

-   成功した場合、このメソッドは 200 - OK 応答コードと、応答本文にアップロードされたライブ応答ライブラリ エンティティを返します。

-   成功しない場合:このメソッドは 400 - 無効な要求を返します。  
    通常、不適切な要求は本文が正しくないためです。

## <a name="example"></a>例

要求

curl を使用した要求の例を次に示します。

```CURL
curl -X POST https://api.securitycenter.microsoft.com/api/libraryfiles -H
"Authorization: Bearer \$token" -F "file=\@mdatp1.png" -F
"ParametersDescription=test"  
-F "HasParameters=true" -F "OverrideIfExists=true" -F "Description=test
description"
```

## <a name="related-topic"></a>関連トピック

-  [ライブ応答を実行する](run-live-response.md) 