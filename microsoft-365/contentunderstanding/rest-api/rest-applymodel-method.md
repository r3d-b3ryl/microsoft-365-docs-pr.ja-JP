---
title: バッチ適用モデル
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: REST API を使用して、ドキュメント理解モデルを 1 つ以上のライブラリに適用します。
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221081"
---
# <a name="batch-apply-model"></a>バッチ適用モデル

トレーニング済みのドキュメント理解モデルを 1 つ以上のライブラリに適用 (または同期) します ( [例](rest-applymodel-method.md#examples)を参照)。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a>URI パラメーター

なし

## <a name="request-headers"></a>要求ヘッダー

| ヘッダー | 値 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|現在のサイトの適切なダイジェスト。|

## <a name="request-body"></a>要求本文

| 名前 | 必須 | 型 | 説明 |
|--------|-------|--------|------------|
|__metadata|○|文字列|SPO でオブジェクト メタを設定します。 常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"} を使用します。|
|発行元|○|MachineLearningPublicationEntityData[]|それぞれがモデルとターゲット ドキュメント ライブラリを指定する MachineLearningPublicationEntityData のコレクション。|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 名前 | 必須 | 型 | 説明 |
|--------|-------|--------|------------|
|ModelUniqueId|○|文字列|モデル ファイルの一意の ID。|
|TargetSiteUrl|○|文字列|ターゲット ライブラリ サイトの完全な URL。|
|TargetWebServerRelativeUrl|○|文字列|ターゲット ライブラリの Web のサーバー相対 URL。|
|TargetLibraryServerRelativeUrl|○|文字列|ターゲット ライブラリのサーバー相対 URL。|
|ViewOption|いいえ|string|新しいモデル ビューをライブラリの既定値として設定するかどうかを指定します。|

## <a name="response"></a>応答

| 名前   | 型  | 説明|
|--------|-------|------------|
|201 Created||これは、複数のドキュメント ライブラリへのモデルの適用をサポートするためにカスタマイズされた API です。部分的に成功した場合でも、作成された 201 が返される可能性があり、呼び出し元は応答本文を調べて、モデルがドキュメント ライブラリに正常に適用されたかどうかを理解する必要があります。|

## <a name="response-body"></a>応答本文

| 名前   | 型  | 説明|
|--------|-------|------------|
|TotalSuccesses|整数|ドキュメント ライブラリに正常に適用されたモデルの総数。|
|TotalFailures|整数|ドキュメント ライブラリへの適用に失敗したモデルの総数。|
|詳細|MachineLearningPublicationResult[]|MachineLearningPublicationResult のコレクション。それぞれが、ドキュメント ライブラリにモデルを適用した詳細な結果を指定します。|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult

| 名前   | 型  | 説明|
|--------|-------|------------|
|StatusCode|整数|HTTP 状態コード。|
|ErrorMessage|文字列|モデルをドキュメント ライブラリに適用するときに何が問題になっているのかを示すエラー メッセージ。|
|発行元|MachineLearningPublicationEntityData|モデル情報とターゲット ドキュメント ライブラリを指定します。| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 名前 | 型 | 説明 |
|--------|--------|------------|
|ModelUniqueId|文字列|モデル ファイルの一意の ID。|
|TargetSiteUrl|文字列|ターゲット ライブラリ サイトの完全な URL。|
|TargetWebServerRelativeUrl|文字列|ターゲット ライブラリの Web のサーバー相対 URL。|
|TargetLibraryServerRelativeUrl|文字列|ターゲット ライブラリのサーバー相対 URL。|

## <a name="examples"></a>例

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>リポジトリ サイトの契約書ドキュメント ライブラリにモデルを適用する

このサンプルでは、Contoso 契約書ドキュメント理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。

#### <a name="sample-request"></a>要求のサンプル

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>応答のサンプル

応答では、TotalFailures と TotalSuccinstalls は、指定されたライブラリに適用されるモデルの失敗と成功の数を示します。

**状態コード :** 201

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>関連項目

[Syntex 文書理解モデル REST API](syntex-model-rest-api.md)
