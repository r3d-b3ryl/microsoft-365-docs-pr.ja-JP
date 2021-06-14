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
localization_priority: Priority
description: REST API を使用して、適用された文書理解モデルを 1 つ以上のライブラリから削除します。
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904273"
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
|ModelUniqueId|○|文字列|モデル ファイルの一意の ID。|
TargetSiteUrl|○|文字列|ターゲット ライブラリ サイトの完全な URL。|
TargetWebServerRelativeUrl|○|文字列|ターゲット ライブラリの Web のサーバー相対 URL。|
TargetLibraryServerRelativeUrl|○|文字列|ターゲット ライブラリのサーバー相対 URL。|
ViewOption|いいえ|string|新しいモデル ビューをライブラリの既定値として設定するかどうかを指定します。|

## <a name="response"></a>応答

| 名前   | 型  | 説明|
|--------|-------|------------|
|200 OK| |成功|


## <a name="examples"></a>例

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>リポジトリ サイトの契約書ドキュメント ライブラリからモデルを削除する

このサンプルでは、Contoso 契約書文書理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。

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

応答では、TotalFailures と TotalSuccesses は、指定されたライブラリに適用されるモデルの失敗と成功の数を示します。

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
