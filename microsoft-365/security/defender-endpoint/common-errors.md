---
title: 一般的なMicrosoft Defender for Endpoint API エラー
description: 説明を含む一般的なMicrosoft Defender for Endpoint API エラーの一覧。
keywords: API、Microsoft Defender for Endpoint API、エラー、トラブルシューティング
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: dbbfd44f573e216015bfe586d5c309cc3ba12f5e
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326147"
---
# <a name="common-rest-api-error-codes"></a>一般的な REST API エラー コード



[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* 次の表に示すエラー コードは、Microsoft Defender for Endpoint API の操作によって返される場合があります。
* エラー コードに加えて、すべてのエラー応答にエラー メッセージが含まれているので、問題の解決に役立ちます。
* メッセージは自由に変更できるテキストです。
* ページの下部には、応答の例があります。

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

エラー コード|HTTP ステータス コード|メッセージ
---|---|---
BadRequest|BadRequest (400)|一般的な不適切な要求エラー メッセージ。
ODataError|BadRequest (400)|OData URI クエリが無効です (特定のエラーが指定されています)。
InvalidInput|BadRequest (400)|無効な入力 {無効な入力}。
InvalidRequestBody|BadRequest (400)|要求本文が無効です。
InvalidHashValue|BadRequest (400)|ハッシュ値 {無効なハッシュ} が無効です。
InvalidDomainName|BadRequest (400)|ドメイン名 {無効なドメイン} が無効です。
InvalidIpAddress|BadRequest (400)|IP アドレス {無効な IP} が無効です。
InvalidUrl|BadRequest (400)|URL {無効な URL} が無効です。
MaximumBatchSizeExceeded|BadRequest (400)|最大バッチ サイズを超えました。 受信済み: {batch size received}, allowed: {batch size allowed}.
MissingRequiredParameter|BadRequest (400)|パラメーター {不足しているパラメーター} が見つかりません。
OsPlatformNotSupported|BadRequest (400)|このアクションでは、OS プラットフォーム {クライアント OS プラットフォーム} はサポートされていません。
ClientVersionNotSupported|BadRequest (400)|{要求されたアクション} は、クライアント バージョン {サポートされているクライアント バージョン} 以降でサポートされています。
権限がありません (Unauthorized)|承認されていない (401)|承認されていない (無効または期限切れの承認ヘッダー)。
禁止されています|禁止 (403)|許可されていません (有効なトークンですが、アクションのアクセス許可が不十分です)。
DisabledFeature|禁止 (403)|テナント機能が有効になっていません。
DisallowedOperation|禁止 (403)|{許可されていない操作と理由}。
NotFound|見つかりません (404)|一般的な見つからないエラー メッセージ。
ResourceNotFound|見つかりません (404)|リソース {要求されたリソース} が見つかりませんでした。
InternalServerError|内部サーバー エラー (500)|(エラー メッセージなし、操作を再試行してください)
TooManyRequests|要求が多すぎます (429)|応答は、要求の数または CPU によってクォータ制限に達することを表します。

## <a name="body-parameters-are-case-sensitive"></a>本文パラメーターでは大文字と小文字が区別されます

送信された本文パラメーターは現在、大文字と小文字が区別されます。

**InvalidRequestBody** または **MissingRequiredParameter エラーが発生した** 場合は、間違ったパラメーターの大文字または小文字が原因である可能性があります。

API ドキュメント ページを確認し、送信されたパラメーターが関連する例と一致することを確認します。

## <a name="correlation-request-id"></a>関連付け要求 ID

各エラー応答には、追跡用の一意の ID パラメーターが含まれています。

このパラメーターのプロパティ名は "target" です。

エラーについて問い合わせる場合は、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。

## <a name="examples"></a>例

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```
