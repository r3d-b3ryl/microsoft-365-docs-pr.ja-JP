---
title: ライブ応答ライブラリからファイルを削除する
description: ライブ応答ライブラリからファイルを削除する方法について学習します。
keywords: apis、graph api、サポートされている API、ライブラリからの削除
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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bd5c77911c889bb52e04981c96be239ff17575f2
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331000"
---
#  <a name="delete-a-file-from-the-live-response-library"></a>ライブ応答ライブラリからファイルを削除する  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

ライブ応答ライブラリからファイルを削除します。

## <a name="limitations"></a>制限事項

1.  この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「開始する」 [を参照してください](apis-intro.md)。

| アクセス許可の種類                    | アクセス許可     | アクセス許可の表示名        |
|------------------------------------|----------------|--------------------------------|
| アプリケーション                        | Library.Manage | ライブ応答ライブラリの管理 |
| 委任 (職場または学校のアカウント) | Library.Manage | ライブ応答ライブラリの管理 |

## <a name="http-request"></a>HTTP 要求

DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/{fileName}

## <a name="request-headers"></a>要求ヘッダー

| 名前            | 型   | 説明               |
|-----------------|--------|---------------------------|
| Authorization   | String | ベアラー\<token>\. 必須です。 |

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

-   ライブラリにファイルが存在し、正常に削除された場合 204 No Content.

-   指定したファイル名が見つからなかった場合は、404 が見つかりません。

## <a name="example"></a>例

要求

以下は、要求の例です。

```HTTP
DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/script1.ps1
```

## <a name="related-topic"></a>関連トピック
- [ライブ応答を実行する](run-live-response.md) 