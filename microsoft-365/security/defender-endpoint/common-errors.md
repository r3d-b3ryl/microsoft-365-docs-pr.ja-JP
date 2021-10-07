---
title: エンドポイント API エラーの一般的な Microsoft Defender
description: 説明付きエンドポイント API エラーの一般的な Microsoft Defender の一覧。
keywords: API、Microsoft Defender for Endpoint API、エラー、トラブルシューティング
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 065a82521e8dad8ea4594ba6b3364471b99927ae
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178493"
---
# <a name="common-rest-api-error-codes"></a>一般的な REST API エラー コード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* 次の表に示すエラー コードは、Microsoft Defender for Endpoint API の操作によって返される場合があります。
* エラー コードに加えて、すべてのエラー応答にエラー メッセージが含まれているので、問題の解決に役立ちます。
* メッセージは、変更できるフリー テキストです。
* ページの下部には、応答の例があります。

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

エラー コード|HTTP ステータス コード|メッセージ
---|---|---
BadRequest|BadRequest (400)|一般的な不良要求エラー メッセージ。
ODataError|BadRequest (400)|無効な OData URI クエリ (特定のエラーが指定されています)。
InvalidInput|BadRequest (400)|無効な入力 {無効な入力}
InvalidRequestBody|BadRequest (400)|要求本文が無効です。
InvalidHashValue|BadRequest (400)|ハッシュ値 {無効なハッシュ} が無効です。
InvalidDomainName|BadRequest (400)|ドメイン名 {無効なドメイン} が無効です。
InvalidIpAddress|BadRequest (400)|IP アドレス {無効な IP} が無効です。
InvalidUrl|BadRequest (400)|URL {無効な URL} が無効です。
MaximumBatchSizeExceeded|BadRequest (400)|最大バッチ サイズを超えました。 Received: {batch size received}, allowed: {batch size allowed}.
MissingRequiredParameter|BadRequest (400)|パラメーター {不足しているパラメーター} がありません。
OsPlatformNotSupported|BadRequest (400)|OS プラットフォーム {クライアント OS プラットフォーム} は、このアクションではサポートされていません。
ClientVersionNotSupported|BadRequest (400)|{要求されたアクション} は、クライアント バージョン {サポートされているクライアント バージョン} 以上でサポートされています。
権限がありません (Unauthorized)|承認されていない (401)|承認されていない (無効または期限切れの承認ヘッダー)。
禁止されています|禁止 (403)|禁止 (有効なトークンですが、アクションに対するアクセス許可が不十分)。
DisabledFeature|禁止 (403)|テナント機能が有効になっていません。
DisallowedOperation|禁止 (403)|{禁止された操作と理由}。
NotFound|見つかりません (404)|一般的なエラー メッセージが見つかりません。
ResourceNotFound|見つかりません (404)|リソース {要求されたリソース} が見つかりませんでした。
InternalServerError|内部サーバー エラー (500)|(エラー メッセージなし、操作を再試行)
TooManyRequests|要求が多すぎます (429)|応答は、要求数または CPU のいずれかによって、クォータ制限に達する値を表します。

## <a name="body-parameters-are-case-sensitive"></a>本文パラメーターでは大文字と小文字が区別されます

送信された本文パラメーターでは、現在大文字と小文字が区別されます。

**InvalidRequestBody** エラーまたは **MissingRequiredParameter** エラーが発生した場合、誤ったパラメーター大文字または小文字が原因である可能性があります。

[API ドキュメント] ページを確認し、送信されたパラメーターが関連する例と一致する点を確認します。

## <a name="correlation-request-id"></a>相関要求 ID

各エラー応答には、追跡用の一意の ID パラメーターが含まれる。

このパラメーターのプロパティ名は "target" です。

エラーについてお問い合わせの際に、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。

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
