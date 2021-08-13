---
title: 分類要求の作成
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
description: REST API を使い、トレーニング済みの文書理解モデルを使用して 1 つ以上のファイルを分類する要求を作成します。
ms.openlocfilehash: 99b4893ace64f802baf8642bf08f916c183e6a3844894561a9e756521599087c
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53891309"
---
# <a name="create-classification-request"></a>分類要求の作成

適用された文書理解モデルを使用して 1 つ以上のファイルを分類する要求を作成します ( [例](rest-createclassificationrequest.md#examples)参照)。

SharePoint Online (および SharePoint 2016 以降のオンプレミス) REST サービスでは、OData $batch クエリ オプションを使って、サービスに対する複数の要求の組み合わせがサポートされています。 要求は、OData $batch クエリ オプションを使用して、サービスへの 1 回の呼び出しに結合されます。 この方法を使用すると、一度に数百のドキュメントの分類作業項目をキューに入れられます。

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

|名前    |種類   |説明 |
|--------|-------|------------|
|_metadata|文字列 |SPO でオブジェクト メタを設定します。 常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"} を使用します。 |
|TargetSiteId|guid|分類するファイルが配置されているサイトの ID。|
|TargetWebId|guid|分類するファイルがある Web の ID。|
|TargetUniqueId|guid|更新するファイルの ID です。|

## <a name="responses"></a>応答

| 名前   | 種類  | 説明|
|--------|-------|------------|
|201 Created| |成功|

## <a name="examples"></a>例

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>ID "e6cff8b7-c90c-4564-b5b8-033449090932" のファイルを分類するための要求をキューに入れる

#### <a name="sample-request"></a>要求のサンプル

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a>応答のサンプル

**状態コード :** 201

## <a name="see-also"></a>関連項目

[Syntex 文書理解モデル REST API](syntex-model-rest-api.md)
