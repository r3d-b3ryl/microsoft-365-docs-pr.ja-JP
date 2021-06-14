---
title: モデルを適用
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
description: REST APIを使用して、ドキュメント理解モデルを 1 つ以上のライブラリに適用します。
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904353"
---
# <a name="apply-model"></a>モデルを適用

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
|ModelUniqueId|○|文字列|モデル ファイルの一意の ID。|
TargetSiteUrl|○|文字列|ターゲット ライブラリ サイトの完全な URL。|
TargetWebServerRelativeUrl|○|文字列|ターゲット ライブラリの Web のサーバー相対 URL。|
TargetLibraryServerRelativeUrl|○|文字列|ターゲット ライブラリのサーバー相対 URL。|
ViewOption|いいえ|string|新しいモデル ビューをライブラリの既定値として設定するかどうかを指定します。|

## <a name="response"></a>応答

| 名前   | 型  | 説明|
|--------|-------|------------|
|200 OK| |成功|
|201 Created| |この API では複数のライブラリへのモデルの適用がサポートされているため、いずれかのライブラリにモデルを適用する際にエラーが発生した場合でも、201 が返される可能性があることに注意してください。 <br>応答本文を調べて、モデルが指定されたすべてのライブラリに正常に適用されたかどうかを確認します。 詳細については [要求本文](rest-applymodel-method.md#request-body) を参照してください。|

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

[Syntex ドキュメント理解モデル REST API](syntex-model-rest-api.md)
