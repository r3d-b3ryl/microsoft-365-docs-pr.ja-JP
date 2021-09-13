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
localization_priority: Priority
description: REST API を使用して、SharePoint Syntex 文書理解モデルに関する利用可能なモデル設定を更新します。
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59163879"
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
