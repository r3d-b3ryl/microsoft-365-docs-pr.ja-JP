---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
ms.localizationpriority: high
description: REST API を使用して、適用された文書理解モデルを 1 つ以上のライブラリから削除します。
ms.openlocfilehash: 52154c5f963ddb466b1544925ffe225fd6b8ff67
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60187055"
---
# <a name="batchdelete"></a>BatchDelete

適用された文書理解モデルを 1 つ以上のライブラリから削除します。 モデルを削除する前に、すべてのライブラリからそのモデルを削除する必要があることに注意してください ([例](rest-batchdelete-method.md#examples)を参照してください)。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
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
|発行元|○|MachineLearningPublicationEntityData[]|それぞれがモデルとターゲット ドキュメント ライブラリを指定する MachineLearningPublicationEntityData のコレクション。|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 名前 | 必須 | 型 | 説明 |
|--------|-------|--------|------------|
|ModelUniqueId|○|文字列|モデル ファイルの一意の ID。|
|TargetSiteUrl|○|文字列|ターゲット ライブラリ サイトの完全な URL。|
|TargetWebServerRelativeUrl|○|文字列|ターゲット ライブラリの Web のサーバー相対 URL。|
|TargetLibraryServerRelativeUrl|○|文字列|ターゲット ライブラリのサーバー相対 URL。|

## <a name="response"></a>応答

| 名前   | 型  | 説明|
|--------|-------|------------|
|200 OK||これは、複数ドキュメント ライブラリからのモデルの削除をサポートするためのカスタマイズされた API です。部分的に成功した場合でも 200 OK が返される可能性があり、呼び出し元は応答本文を調べて、モデルがドキュメント ライブラリから正常に削除されたかどうかを把握する必要があります。|

## <a name="response-body"></a>応答本文

| 名前   | 型  | 説明|
|--------|-------|------------|
|TotalSuccesses|整数|ドキュメント ライブラリから正常に削除されたモデルの総数。|
|TotalFailures|整数|ドキュメント ライブラリからの削除に失敗したモデルの総数。|
|詳細|MachineLearningPublicationResult[]|MachineLearningPublicationResult のコレクション。それぞれが、ドキュメント ライブラリからモデルを削除した詳細な結果を指定します。|

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

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>リポジトリ サイトの契約書ドキュメント ライブラリからモデルを削除する

このサンプルでは、Contoso 契約書文書理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。

#### <a name="sample-request"></a>要求のサンプル

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```

#### <a name="sample-response"></a>応答のサンプル

応答では、TotalFailures と TotalSuccesses は、指定されたライブラリから削除されるモデルの失敗と成功の数を示します。

**Status code:** 200

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
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>関連項目

[Syntex 文書理解モデル REST API](syntex-model-rest-api.md)
