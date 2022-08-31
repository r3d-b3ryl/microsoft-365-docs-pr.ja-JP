---
title: 一般的なMicrosoft 365 Defender REST API エラー コード
description: 一般的なMicrosoft 365 Defender REST API エラー コードについて説明します
keywords: api, error, codes, common errors, Microsoft 365 Defender, api error code
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.custom: api
ms.openlocfilehash: 6aeed1afa77779de5d21bb0ecbdd34d5a4c7e0e0
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482474"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>一般的なMicrosoft 365 Defender REST API エラー コード

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

エラー コードは、Microsoft 365 Defender API の操作によって返される場合があります。 すべてのエラー応答には、問題の解決に役立つエラー メッセージが含まれます。 テーブル セクションのエラー メッセージ列には、いくつかのサンプル メッセージが用意されています。 実際のメッセージの内容は、応答をトリガーした要因によって異なります。 変数の内容は、山かっこで表されます。

## <a name="error-codes"></a>エラー コード

エラー コード | HTTP ステータス コード | メッセージ
-|-|-
BadRequest | BadRequest (400) | 一般的な不適切な要求エラー メッセージ。
ODataError | BadRequest (400) | OData URI クエリ \<the specific error is specified\>が無効です。
InvalidInput | BadRequest (400) | 入力 \<the invalid input\>が無効です。
InvalidRequestBody | BadRequest (400) | 要求本文が無効です。
InvalidHashValue | BadRequest (400) | ハッシュ値 \<the invalid hash\> が無効です。
InvalidDomainName | BadRequest (400) | ドメイン名 \<the invalid domain\> が無効です。
InvalidIpAddress | BadRequest (400) | IP アドレス \<the invalid IP\> が無効です。
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> が無効です。
MaximumBatchSizeExceeded | BadRequest (400) | 最大バッチ サイズを超えました。 受信: \<batch size received\>、許可: {batch size allowed}。
MissingRequiredParameter | BadRequest (400) | パラメーター \<the missing parameter\> がありません。
OsPlatformNotSupported | BadRequest (400) | このアクションでは、OS プラットフォーム \<the client OS Platform\> はサポートされていません。
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> は、クライアント バージョン \<supported client version\> 以上でサポートされています。
権限がありません (Unauthorized) | 承認されていない (401) | 権限がありません (Unauthorized) <br /><br />*注: 通常、無効または期限切れの承認ヘッダーが原因です。*
禁止されています | 禁止 (403) | 禁止されています <br /><br />*注: 有効なトークンですが、アクションのアクセス許可が不十分です*。
DisabledFeature | 禁止 (403) | テナント機能が有効になっていません。
DisallowedOperation | 禁止 (403) | \<the disallowed operation and the reason\>.
NotFound | 見つかりません (404) | 一般的な見つからないエラー メッセージ。
ResourceNotFound | 見つかりません (404) | リソース \<the requested resource\> が見つかりませんでした。
InternalServerError | 内部サーバー エラー (500) | *注: エラー メッセージが表示されない場合は、操作を再試行するか、解決されない場合は [Microsoft にお問い合わせください](../../admin/get-help-support.md)*

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

*InvalidRequestBody* または *MissingRequiredParameter エラーが発生した* 場合は、入力ミスが原因である可能性があります。 API ドキュメントを確認し、送信されたパラメーターが関連する例と一致することを確認します。

## <a name="tracking-id"></a>追跡 ID

各エラー応答には、追跡用の一意の ID パラメーターが含まれています。 このパラメーターのプロパティ名は *ターゲット* です。 エラーについてお問い合わせいただくと、この ID を添付すると、問題の根本原因を見つけることができます。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [サポートされている Microsoft 365 Defender API](api-supported.md)
- [Microsoft 365 Defender API にアクセスする](api-access.md)
- [API の制限とライセンスについて学習する](api-terms.md)
