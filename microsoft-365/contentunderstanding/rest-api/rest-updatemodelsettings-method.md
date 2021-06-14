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
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904303"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="b28fc-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="b28fc-103">UpdateModelSettings</span></span>

<span data-ttu-id="b28fc-104">SharePoint Syntex 文書理解モデルの使用可能なモデル設定 (関連する保持ラベルとモデルの説明) を更新します (の[例](rest-updatemodelsettings-method.md#examples)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b28fc-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="b28fc-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b28fc-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="b28fc-106">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="b28fc-106">URI parameters</span></span>

<span data-ttu-id="b28fc-107">なし</span><span class="sxs-lookup"><span data-stu-id="b28fc-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="b28fc-108">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b28fc-108">Request headers</span></span>

| <span data-ttu-id="b28fc-109">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b28fc-109">Header</span></span> | <span data-ttu-id="b28fc-110">値</span><span class="sxs-lookup"><span data-stu-id="b28fc-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="b28fc-111">Accept</span><span class="sxs-lookup"><span data-stu-id="b28fc-111">Accept</span></span>|<span data-ttu-id="b28fc-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="b28fc-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="b28fc-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b28fc-113">Content-Type</span></span>|<span data-ttu-id="b28fc-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="b28fc-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="b28fc-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="b28fc-115">x-requestdigest</span></span>|<span data-ttu-id="b28fc-116">現在のサイトの適切なダイジェストです。</span><span class="sxs-lookup"><span data-stu-id="b28fc-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="b28fc-117">要求本文</span><span class="sxs-lookup"><span data-stu-id="b28fc-117">Request body</span></span>

|<span data-ttu-id="b28fc-118">名前</span><span class="sxs-lookup"><span data-stu-id="b28fc-118">Name</span></span>    |<span data-ttu-id="b28fc-119">型</span><span class="sxs-lookup"><span data-stu-id="b28fc-119">Type</span></span>   |<span data-ttu-id="b28fc-120">説明</span><span class="sxs-lookup"><span data-stu-id="b28fc-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="b28fc-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="b28fc-121">ModelSettings</span></span>|<span data-ttu-id="b28fc-122">文字列</span><span class="sxs-lookup"><span data-stu-id="b28fc-122">string</span></span>|<span data-ttu-id="b28fc-123">モデル設定の JSON。</span><span class="sxs-lookup"><span data-stu-id="b28fc-123">JSON of model settings.</span></span>|
|<span data-ttu-id="b28fc-124">説明</span><span class="sxs-lookup"><span data-stu-id="b28fc-124">Description</span></span>|<span data-ttu-id="b28fc-125">string</span><span class="sxs-lookup"><span data-stu-id="b28fc-125">string</span></span>|<span data-ttu-id="b28fc-126">モデルの説明。</span><span class="sxs-lookup"><span data-stu-id="b28fc-126">The model description.</span></span>|
|<span data-ttu-id="b28fc-127">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="b28fc-127">RetentionLabel</span></span>| |<span data-ttu-id="b28fc-128">関連付けられているラベルの情報 (ラベル ID と名前)。</span><span class="sxs-lookup"><span data-stu-id="b28fc-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="b28fc-129">応答</span><span class="sxs-lookup"><span data-stu-id="b28fc-129">Responses</span></span>

| <span data-ttu-id="b28fc-130">名前</span><span class="sxs-lookup"><span data-stu-id="b28fc-130">Name</span></span>   | <span data-ttu-id="b28fc-131">型</span><span class="sxs-lookup"><span data-stu-id="b28fc-131">Type</span></span>  | <span data-ttu-id="b28fc-132">説明</span><span class="sxs-lookup"><span data-stu-id="b28fc-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="b28fc-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="b28fc-133">200 OK</span></span>| |<span data-ttu-id="b28fc-134">成功</span><span class="sxs-lookup"><span data-stu-id="b28fc-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="b28fc-135">例</span><span class="sxs-lookup"><span data-stu-id="b28fc-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="b28fc-136">Contoso 契約のモデル設定を更新する</span><span class="sxs-lookup"><span data-stu-id="b28fc-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="b28fc-137">この例では、モデルの説明と "Standard Hold" 保持ラベルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="b28fc-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="b28fc-138">保持ラベルの　ID は `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6` です。</span><span class="sxs-lookup"><span data-stu-id="b28fc-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="b28fc-139">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="b28fc-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="b28fc-140">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="b28fc-140">Sample response</span></span>

<span data-ttu-id="b28fc-141">**Status code:** 200</span><span class="sxs-lookup"><span data-stu-id="b28fc-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="b28fc-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="b28fc-142">See also</span></span>

[<span data-ttu-id="b28fc-143">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="b28fc-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
