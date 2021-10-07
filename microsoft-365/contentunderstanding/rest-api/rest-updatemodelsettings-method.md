---
title: UpdateModelSettings
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
description: REST API を使用して、SharePoint Syntex 文書理解モデルに関する利用可能なモデル設定を更新します。
ms.openlocfilehash: f6489208b292237936776a2cfa98a5c1c42e64a9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168652"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

SharePoint Syntex 文書理解モデルの使用可能なモデル設定 (関連する保持ラベルとモデルの説明) を更新します (の[例](rest-updatemodelsettings-method.md#examples)を参照してください)。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>URI パラメーター

|名前 |In |必須|型|説明|
|-----|---|--------|----|-----------|
|modelFileName|query|はい|string|Syntex モデル ファイル名です。|

## <a name="request-headers"></a>要求ヘッダー

| ヘッダー | 値 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|現在のサイトの適切なダイジェストです。|

## <a name="request-body"></a>要求本文

|名前    |型   |説明 |
|--------|-------|-------|
|ModelSettings|文字列|モデル設定の JSON。|
|説明|string|モデルの説明。|
|保持ラベル| |関連付けられているラベルの情報 (ラベル ID と名前)。|

## <a name="responses"></a>応答

| 名前   | 型  | 説明|
|--------|-------|------------|
|200 OK| |成功|

## <a name="examples"></a>例

### <a name="update-model-settings-for-contoso-contract"></a>Contoso 契約のモデル設定を更新する

この例では、モデルの説明と "Standard Hold" 保持ラベルが更新されます。 保持ラベルの　ID は `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6` です。

#### <a name="sample-request"></a>要求のサンプル

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>応答のサンプル

**Status code:** 200

## <a name="see-also"></a>関連項目

[Syntex 文書理解モデル REST API](syntex-model-rest-api.md)
