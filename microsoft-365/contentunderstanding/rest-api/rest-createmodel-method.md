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
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904293"
---
# <a name="create-model"></a><span data-ttu-id="9dd58-103">モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="9dd58-103">Create model</span></span>

<span data-ttu-id="9dd58-104">モデルとそれに関連付けられたコンテンツ タイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="9dd58-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="9dd58-105">これにより、モデルのみが作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9dd58-105">Note that this only creates the model.</span></span> <span data-ttu-id="9dd58-106">引き続きコンテンツ センターでトレーニングする必要があります ([例](rest-createmodel-method.md#examples)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9dd58-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="9dd58-107">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="9dd58-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="9dd58-108">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="9dd58-108">URI Parameters</span></span>

<span data-ttu-id="9dd58-109">なし</span><span class="sxs-lookup"><span data-stu-id="9dd58-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="9dd58-110">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="9dd58-110">Request headers</span></span>

| <span data-ttu-id="9dd58-111">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="9dd58-111">Header</span></span> | <span data-ttu-id="9dd58-112">値</span><span class="sxs-lookup"><span data-stu-id="9dd58-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="9dd58-113">Accept</span><span class="sxs-lookup"><span data-stu-id="9dd58-113">Accept</span></span>|<span data-ttu-id="9dd58-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="9dd58-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="9dd58-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9dd58-115">Content-Type</span></span>|<span data-ttu-id="9dd58-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="9dd58-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="9dd58-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="9dd58-117">x-requestdigest</span></span>|<span data-ttu-id="9dd58-118">現在のサイトの適切なダイジェスト</span><span class="sxs-lookup"><span data-stu-id="9dd58-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="9dd58-119">要求本文</span><span class="sxs-lookup"><span data-stu-id="9dd58-119">Request body</span></span>

|<span data-ttu-id="9dd58-120">名前</span><span class="sxs-lookup"><span data-stu-id="9dd58-120">Name</span></span>    |<span data-ttu-id="9dd58-121">型</span><span class="sxs-lookup"><span data-stu-id="9dd58-121">Type</span></span>   |<span data-ttu-id="9dd58-122">説明</span><span class="sxs-lookup"><span data-stu-id="9dd58-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="9dd58-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="9dd58-123">_metadata</span></span>|  |<span data-ttu-id="9dd58-124">SPO でオブジェクト メタを設定します。</span><span class="sxs-lookup"><span data-stu-id="9dd58-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="9dd58-125">常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"} を使用します。</span><span class="sxs-lookup"><span data-stu-id="9dd58-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="9dd58-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="9dd58-126">ContentTypeGroup</span></span>|<span data-ttu-id="9dd58-127">文字列</span><span class="sxs-lookup"><span data-stu-id="9dd58-127">string</span></span>|<span data-ttu-id="9dd58-128">モデルに関連付けられている関連付けられた関連コンテンツ タイプ グループ。</span><span class="sxs-lookup"><span data-stu-id="9dd58-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="9dd58-129">既定では、"インテリジェント ドキュメント コンテンツ タイプ" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9dd58-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="9dd58-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="9dd58-130">ContentTypeName</span></span>|<span data-ttu-id="9dd58-131">文字列</span><span class="sxs-lookup"><span data-stu-id="9dd58-131">string</span></span>|<span data-ttu-id="9dd58-132">関連付けられているコンテンツ タイプ名。</span><span class="sxs-lookup"><span data-stu-id="9dd58-132">The associated content type name.</span></span> <span data-ttu-id="9dd58-133">作成されたモデル ファイルは同じ名前です。</span><span class="sxs-lookup"><span data-stu-id="9dd58-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="9dd58-134">応答</span><span class="sxs-lookup"><span data-stu-id="9dd58-134">Responses</span></span>

| <span data-ttu-id="9dd58-135">名前</span><span class="sxs-lookup"><span data-stu-id="9dd58-135">Name</span></span>   | <span data-ttu-id="9dd58-136">型</span><span class="sxs-lookup"><span data-stu-id="9dd58-136">Type</span></span>  | <span data-ttu-id="9dd58-137">説明</span><span class="sxs-lookup"><span data-stu-id="9dd58-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="9dd58-138">201 Created</span><span class="sxs-lookup"><span data-stu-id="9dd58-138">201 Created</span></span>| |<span data-ttu-id="9dd58-139">成功</span><span class="sxs-lookup"><span data-stu-id="9dd58-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="9dd58-140">例</span><span class="sxs-lookup"><span data-stu-id="9dd58-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="9dd58-141">"Contoso 契約" という名前の新しい文書理解モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="9dd58-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="9dd58-142">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="9dd58-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a><span data-ttu-id="9dd58-143">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="9dd58-143">Sample response</span></span>

<span data-ttu-id="9dd58-144">**状態コード :** 201</span><span class="sxs-lookup"><span data-stu-id="9dd58-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="9dd58-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="9dd58-145">See also</span></span>

[<span data-ttu-id="9dd58-146">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="9dd58-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
