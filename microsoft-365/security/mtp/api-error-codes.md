---
title: Microsoft 365 Defender REST API の一般的なエラー コード
description: Microsoft 365 Defender REST API の一般的なエラー コードについて説明します。
keywords: api, エラー, コード, 一般的なエラー, mtp, api エラー コード
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719216"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Microsoft 365 Defender REST API の一般的なエラー コード

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft Threat Protection

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

エラー コードは、Microsoft 365 Defender API の操作によって返される場合があります。 すべてのエラー応答にはエラー メッセージが含まれるので、問題の解決に役立ちます。 表セクションのエラー メッセージ列には、いくつかのサンプル メッセージが示されています。 実際のメッセージの内容は、応答をトリガーした要因によって異なります。 可変コンテンツは、テーブル内で角かっこで示されています。

## <a name="error-codes"></a>エラー コード

エラー コード | HTTP ステータス コード | メッセージ
-|-|-
BadRequest | BadRequest (400) | General Bad Request エラー メッセージ。
ODataError | BadRequest (400) | 無効な OData URI クエリ \<the specific error is specified\> です。
InvalidInput | BadRequest (400) | 無効な入力 \<the invalid input\> です。
InvalidRequestBody | BadRequest (400) | 要求本文が無効です。
InvalidHashValue | BadRequest (400) | ハッシュ値 \<the invalid hash\> が無効です。
InvalidDomainName | BadRequest (400) | ドメイン名 \<the invalid domain\> が無効です。
InvalidIpAddress | BadRequest (400) | IP アドレス \<the invalid IP\> が無効です。
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> が無効です。
MaximumBatchSizeExceeded | BadRequest (400) | 最大バッチ サイズを超えました。 Received: \<batch size received\> , allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | パラメーター \<the missing parameter\> がありません。
OsPlatformNotSupported | BadRequest (400) | このアクション \<the client OS Platform\> では、OS プラットフォームはサポートされていません。
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> はクライアント バージョン以上 \<supported client version\> でサポートされています。
権限がありません (Unauthorized) | Unauthorized (401) | 権限がありません (Unauthorized) <br /><br />*注: 通常、無効または期限切れの承認ヘッダーが原因です。*
禁止されています | Forbidden (403) | 禁止されています <br /><br />*注: 有効なトークンですが、アクションのアクセス許可が不十分です*。
DisabledFeature | Forbidden (403) | テナント機能が有効になっていません。
DisallowedOperation | Forbidden (403) | \<the disallowed operation and the reason\>.
NotFound | Not Found (404) | General Not Found エラー メッセージ。
ResourceNotFound | Not Found (404) | リソース \<the requested resource\> が見つかりませんでした。
InternalServerError | 内部サーバー エラー (500) | *注: エラー メッセージが表示されない場合は、操作を再試行するか、解決されない場合は Microsoft にお問い合わせください。*

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

## <a name="body-parameters"></a>本文パラメーター

> [!IMPORTANT]
> 本文パラメーターでは大文字と小文字が区別されます。

*InvalidRequestBody エラー* または *MissingRequiredParameter* エラーが発生した場合は、入力ミスが原因である可能性があります。 API ドキュメントを確認し、送信されたパラメーターが関連する例と一致する必要があります。

## <a name="tracking-id"></a>追跡 ID

各エラー応答には、追跡用の一意の ID パラメーターが含まれる。 このパラメーターのプロパティ名は target *です*。 エラーについてお問い合わせの場合、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [サポートされている Microsoft 365 Defender API](api-supported.md)
- [Microsoft 365 Defender API へのアクセス](api-access.md)
- [API の制限とライセンスについて](api-terms.md)
