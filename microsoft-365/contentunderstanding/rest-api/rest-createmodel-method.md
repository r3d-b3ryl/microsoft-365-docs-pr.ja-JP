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
ms.openlocfilehash: 1c5bd84c777774edc1aa0c2419181f7b84aa4707
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287247"
---
# <a name="create-model"></a><span data-ttu-id="18823-103">モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="18823-103">Create model</span></span>

<span data-ttu-id="18823-104">モデルとそれに関連付けられたコンテンツ タイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="18823-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="18823-105">これにより、モデルのみが作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="18823-105">Note that this only creates the model.</span></span> <span data-ttu-id="18823-106">引き続きコンテンツ センターでトレーニングする必要があります ([例](rest-createmodel-method.md#examples)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="18823-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="18823-107">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="18823-107">HTTP request</span></span>

```http
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="18823-108">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="18823-108">URI Parameters</span></span>

<span data-ttu-id="18823-109">なし</span><span class="sxs-lookup"><span data-stu-id="18823-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="18823-110">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="18823-110">Request headers</span></span>

| <span data-ttu-id="18823-111">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="18823-111">Header</span></span> | <span data-ttu-id="18823-112">値</span><span class="sxs-lookup"><span data-stu-id="18823-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="18823-113">Accept</span><span class="sxs-lookup"><span data-stu-id="18823-113">Accept</span></span>|<span data-ttu-id="18823-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="18823-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="18823-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="18823-115">Content-Type</span></span>|<span data-ttu-id="18823-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="18823-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="18823-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="18823-117">x-requestdigest</span></span>|<span data-ttu-id="18823-118">現在のサイトの適切なダイジェスト</span><span class="sxs-lookup"><span data-stu-id="18823-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="18823-119">要求本文</span><span class="sxs-lookup"><span data-stu-id="18823-119">Request body</span></span>

|<span data-ttu-id="18823-120">名前</span><span class="sxs-lookup"><span data-stu-id="18823-120">Name</span></span>    |<span data-ttu-id="18823-121">種類</span><span class="sxs-lookup"><span data-stu-id="18823-121">Type</span></span>   |<span data-ttu-id="18823-122">説明</span><span class="sxs-lookup"><span data-stu-id="18823-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="18823-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="18823-123">_metadata</span></span>|  |<span data-ttu-id="18823-124">SPO でオブジェクト メタを設定します。</span><span class="sxs-lookup"><span data-stu-id="18823-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="18823-125">常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"} を使用します。</span><span class="sxs-lookup"><span data-stu-id="18823-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="18823-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="18823-126">ContentTypeGroup</span></span>|<span data-ttu-id="18823-127">文字列</span><span class="sxs-lookup"><span data-stu-id="18823-127">string</span></span>|<span data-ttu-id="18823-128">モデルに関連付けられている関連付けられた関連コンテンツ タイプ グループ。</span><span class="sxs-lookup"><span data-stu-id="18823-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="18823-129">既定では、"インテリジェント ドキュメント コンテンツ タイプ" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="18823-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="18823-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="18823-130">ContentTypeName</span></span>|<span data-ttu-id="18823-131">文字列</span><span class="sxs-lookup"><span data-stu-id="18823-131">string</span></span>|<span data-ttu-id="18823-132">関連付けられているコンテンツ タイプ名。</span><span class="sxs-lookup"><span data-stu-id="18823-132">The associated content type name.</span></span> <span data-ttu-id="18823-133">作成されたモデル ファイルは同じ名前です。</span><span class="sxs-lookup"><span data-stu-id="18823-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="18823-134">応答</span><span class="sxs-lookup"><span data-stu-id="18823-134">Responses</span></span>

| <span data-ttu-id="18823-135">名前</span><span class="sxs-lookup"><span data-stu-id="18823-135">Name</span></span>   | <span data-ttu-id="18823-136">種類</span><span class="sxs-lookup"><span data-stu-id="18823-136">Type</span></span>  | <span data-ttu-id="18823-137">説明</span><span class="sxs-lookup"><span data-stu-id="18823-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="18823-138">201 Created</span><span class="sxs-lookup"><span data-stu-id="18823-138">201 Created</span></span>| |<span data-ttu-id="18823-139">成功</span><span class="sxs-lookup"><span data-stu-id="18823-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="18823-140">例</span><span class="sxs-lookup"><span data-stu-id="18823-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="18823-141">"Contoso 契約" という名前の新しい文書理解モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="18823-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="18823-142">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="18823-142">Sample request</span></span>

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="18823-143">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="18823-143">Sample response</span></span>

<span data-ttu-id="18823-144">**状態コード :** 201</span><span class="sxs-lookup"><span data-stu-id="18823-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="18823-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="18823-145">See also</span></span>

[<span data-ttu-id="18823-146">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="18823-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
