---
title: ライブ応答ライブラリからファイルを削除する
description: ライブ応答ライブラリからファイルを削除する方法について説明します。
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 23625c8b7160d604df5f3a8b1b1387fc31027acf
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526816"
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

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[概要](apis-intro.md)」を参照してください。

| アクセス許可の種類                    | アクセス許可     | アクセス許可の表示名        |
|------------------------------------|----------------|--------------------------------|
| アプリケーション                        | Library.Manage | ライブ応答ライブラリを管理する |
| 委任 (職場または学校のアカウント) | Library.Manage | ライブ応答ライブラリを管理する |

## <a name="http-request"></a>HTTP 要求

DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/{fileName}

## <a name="request-headers"></a>要求ヘッダー

| 名前            | 種類   | 説明               |
|-----------------|--------|---------------------------|
| Authorization   | String | 無記名\<token>\. 必須です。 |

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

-   ファイルがライブラリに存在し、正常に削除された場合 204 コンテンツなし。

-   指定したファイル名が見つからない場合は 404 [見つかりません]。

## <a name="example"></a>例

要求

以下は、要求の例です。

```HTTP
DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/script1.ps1
```

## <a name="related-topic"></a>関連トピック
- [ライブ応答を実行する](run-live-response.md) 