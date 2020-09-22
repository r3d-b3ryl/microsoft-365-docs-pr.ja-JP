---
title: 一般的な Microsoft Threat Protection REST API のエラーコード
description: 一般的な Microsoft Threat Protection REST API エラーコードについて
keywords: api、error、コード、一般的なエラー、mtp、api のエラーコード
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
ms.openlocfilehash: 81375b919b52ff895e5ec7014feb747b1a0eae65
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201341"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a>一般的な Microsoft Threat Protection REST API のエラーコード

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

次の表に記載されているエラーコードは、Microsoft の脅威保護 Api のいずれかの操作によって返される場合があります。

エラー応答ごとにエラーメッセージが含まれています。これは、この問題を解決するのに役立ちます。

このメッセージは、変更できる無料のテキストです。

ページの下部に、応答の例が記載されています。

エラー コード |HTTP ステータス コード |メッセージ 
:---|:---|:---
BadRequest | BadRequest (400) | 通常の正しくない要求エラーメッセージ。
/エラー | BadRequest (400) | OData URI クエリが正しくありません (具体的なエラーが指定されています)。
InvalidInput | BadRequest (400) | 無効な入力です {無効な入力} です。
InvalidRequestBody | BadRequest (400) | 要求本文が無効です。
InvalidHashValue | BadRequest (400) | ハッシュ値 {無効なハッシュ} が無効です。
InvalidDomainName | BadRequest (400) | ドメイン名 {無効なドメイン} が無効です。
InvalidIpAddress | BadRequest (400) | IP アドレス {無効な IP} が無効です。
InvalidUrl | BadRequest (400) | URL {無効な URL} が無効です。
MaximumBatchSizeExceeded | BadRequest (400) | 最大バッチサイズを超えています。 Received: {batch size received in received}、allowed: {batch size allowed}。
MissingRequiredParameter | BadRequest (400) | パラメーター {不足しているパラメーター} がありません。
OsPlatformNotSupported | BadRequest (400) | OS プラットフォーム {クライアント OS プラットフォーム} は、このアクションではサポートされていません。
ClientVersionNotSupported | BadRequest (400) | {要求されたアクション} はクライアントバージョン {サポートされているクライアントバージョン} 以降でサポートされています。
権限がありません (Unauthorized) | 未承認 (401) | 承認されていない (通常は無効または期限切れの承認ヘッダー)。
禁止されています | 禁止 (403) | 禁止 (有効なトークンですが、アクションに対して十分な権限がありません)。
DisabledFeature | 禁止 (403) | テナント機能が有効になっていません。
DisallowedOperation | 禁止 (403) | {許可されていない操作と理由}。
NotFound | 見つかりません (404) | 一般的なエラーメッセージが表示されません。
ResourceNotFound | 見つかりません (404) | リソース {要求されたリソース} が見つかりませんでした。
InternalServerError | 内部サーバーエラー (500) | (エラーメッセージが表示されない場合は、操作を再試行するか、お問い合わせください。解決しない場合)

## <a name="body-parameters-are-case-sensitive"></a>本文のパラメーターでは大文字と小文字が区別される

送信される本文パラメーターは、現在、大文字と小文字が区別されます。
<br>**Invalidrequestbody**または**MissingRequiredParameter**のエラーが発生した場合は、パラメーターの大文字または小文字が正しくないことが原因である可能性があります。
<br>API ドキュメントページを参照して、送信されたパラメーターが関連する例と一致していることを確認することをお勧めします。

## <a name="correlation-request-id"></a>関連付け要求 ID

各エラー応答には、追跡用の一意の ID パラメーターが含まれています。
<br>このパラメーターのプロパティ名は "target" です。
<br>エラーについてお問い合わせの際には、この ID を添付することで問題の根本的な原因を見つけることができます。

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

