---
title: モデルを作成する
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
description: REST API を使用して、モデルとそれに関連付けられているコンテンツ タイプを作成します。
ms.openlocfilehash: ac5a48f92352c2c286323b8a679a975e0dbdca80703f9f727d16a4999b4a2f65
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53899813"
---
# <a name="create-model"></a>モデルを作成する

モデルとそれに関連付けられたコンテンツ タイプを作成します。 これにより、モデルのみが作成されることに注意してください。 引き続きコンテンツ センターでトレーニングする必要があります ([例](rest-createmodel-method.md#examples)を参照してください)。

## <a name="http-request"></a>HTTP 要求

```http
POST /_api/machinelearning/models HTTP/1.1
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

|名前    |種類   |説明 |
|--------|-------|------------|
|_metadata|  |SPO でオブジェクト メタを設定します。 常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"} を使用します。 |
|ContentTypeGroup|文字列|モデルに関連付けられている関連付けられた関連コンテンツ タイプ グループ。 既定では、"インテリジェント ドキュメント コンテンツ タイプ" に設定されます。|
|ContentTypeName|文字列|関連付けられているコンテンツ タイプ名。 作成されたモデル ファイルは同じ名前です。|

## <a name="responses"></a>応答

| 名前   | 種類  | 説明|
|--------|-------|------------|
|201 Created| |成功|

## <a name="examples"></a>例

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>"Contoso 契約" という名前の新しい文書理解モデルを作成する

#### <a name="sample-request"></a>要求のサンプル

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a>応答のサンプル

**状態コード :** 201

## <a name="see-also"></a>関連項目

[Syntex 文書理解モデル REST API](syntex-model-rest-api.md)
