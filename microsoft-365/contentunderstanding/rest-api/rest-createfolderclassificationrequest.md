---
title: フォルダー分類要求の作成
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
description: REST API を使い、トレーニング済みの文書理解モデルを使用してフォルダー全体を分類する要求を作成します。
ms.openlocfilehash: 44e1969628fb61b797f59a7378b95403c94dda8a
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59777133"
---
# <a name="create-folder-classification-request"></a>フォルダー分類要求の作成

適用されたドキュメント理解モデルを使用して、オフピーク時にフォルダー全体を分類する要求を作成します。 (詳細については、[例](rest-createfolderclassificationrequest.md#examples)を参照してください。)この API を使用すると、ルート フォルダーの作業項目を作成してドキュメント ライブラリ全体を分類できます。

## <a name="http-request"></a>HTTP 要求

```http
POST /_api/machinelearning/workItems HTTP/1.1
```

## <a name="uri-parameters"></a>URI パラメーター

なし

## <a name="request-headers"></a>要求ヘッダー

| ヘッダー | 値 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|現在のサイトの適切なダイジェスト|

## <a name="request-body"></a>要求本文

|名前    |型   |説明 |
|--------|-------|------------|
|_metadata|文字列 |SPO でオブジェクト メタを設定します。 常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"} を使用します。 |
|TargetSiteId|guid|分類するファイルが配置されているサイトの ID。 これは、TargetSiteUrl に値がある場合は省略できます。 |
|TargetSiteUrl|文字列|分類するフォルダが配置されているサイトの完全なURL。 TargeSiteId に値がある場合、これは省略できます。|
|TargetWebId|guid|分類するフォルダーが配置されている Web の ID。 TargetWebServerRelativeUrl に値がある場合は、これを省略できます。 |
|TargetWebServerRelativeUrl|文字列|分類するフォルダーが配置されている Web のサーバー相対 URL。 TargetWebId に値がある場合は、これを省略できます。  |
|TargetUniqueId|guid|分類するフォルダーの ID。 TargetServerRelativeUrl に値がある場合は、これを省略できます。 |
|TargetServerRelativeUrl|string|分類するフォルダのサーバー相対 URL があります。 TargetUniqueId に値がある場合は、これを省略できます。|
|IsFolder|ブール値|分類されるアイテムがフォルダーかどうかを示すフラグ。 フォルダー分類作業項目を作成する場合は、常にこれを true に設定します。 |


## <a name="responses"></a>応答

| 名前   | 型  | 説明|
|--------|-------|------------|
|201 Created| |応答はカスタマイズされます。 エラーが発生した場合でも、201 Created を返す可能性があります。 呼び出し元は、応答本文をさらに調べ、正確な結果を判断する必要があります。|

## <a name="response-body"></a>応答本文

| 名前   | 型  | 説明|
|--------|-------|------------|
|StatusCode |整数 |HTTP 状態コード。 200 または 201 でない場合、API は失敗しているはずです。|
|ErrorMessage |文字列 |モデルをドキュメント ライブラリに適用するときに何が問題になっているのかを示すエラー メッセージ。|

## <a name="examples"></a>例

### <a name="enqueue-a-request-to-classify-a-whole-folder-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>ID "e6cff8b7-c90c-4564-b5b8-033449090932" のフォルダー全体を分類する要求をキューに入れる


#### <a name="sample-request"></a>要求の例

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932",
    "IsFolder": true 
}
```

#### <a name="sample-response"></a>応答のサンプル

**状態コード :** 201

```JSON
{
    "ErrorMessage":  null,
    "StatusCode":  201
}
```

## <a name="see-also"></a>関連項目

[Syntex 文書理解モデル REST API](syntex-model-rest-api.md)
