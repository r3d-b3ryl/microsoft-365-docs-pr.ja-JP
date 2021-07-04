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
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288649"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="5dff3-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="5dff3-103">UpdateModelSettings</span></span>

<span data-ttu-id="5dff3-104">SharePoint Syntex 文書理解モデルの使用可能なモデル設定 (関連する保持ラベルとモデルの説明) を更新します (の[例](rest-updatemodelsettings-method.md#examples)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5dff3-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="5dff3-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="5dff3-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="5dff3-106">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="5dff3-106">URI parameters</span></span>

|<span data-ttu-id="5dff3-107">名前</span><span class="sxs-lookup"><span data-stu-id="5dff3-107">Name</span></span> |<span data-ttu-id="5dff3-108">In</span><span class="sxs-lookup"><span data-stu-id="5dff3-108">In</span></span> |<span data-ttu-id="5dff3-109">必須</span><span class="sxs-lookup"><span data-stu-id="5dff3-109">Required</span></span>|<span data-ttu-id="5dff3-110">型</span><span class="sxs-lookup"><span data-stu-id="5dff3-110">Type</span></span>|<span data-ttu-id="5dff3-111">説明</span><span class="sxs-lookup"><span data-stu-id="5dff3-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="5dff3-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="5dff3-112">modelFileName</span></span>|<span data-ttu-id="5dff3-113">query</span><span class="sxs-lookup"><span data-stu-id="5dff3-113">query</span></span>|<span data-ttu-id="5dff3-114">はい</span><span class="sxs-lookup"><span data-stu-id="5dff3-114">True</span></span>|<span data-ttu-id="5dff3-115">string</span><span class="sxs-lookup"><span data-stu-id="5dff3-115">string</span></span>|<span data-ttu-id="5dff3-116">Syntex モデル ファイル名です。</span><span class="sxs-lookup"><span data-stu-id="5dff3-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="5dff3-117">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="5dff3-117">Request headers</span></span>

| <span data-ttu-id="5dff3-118">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="5dff3-118">Header</span></span> | <span data-ttu-id="5dff3-119">値</span><span class="sxs-lookup"><span data-stu-id="5dff3-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="5dff3-120">Accept</span><span class="sxs-lookup"><span data-stu-id="5dff3-120">Accept</span></span>|<span data-ttu-id="5dff3-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="5dff3-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="5dff3-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5dff3-122">Content-Type</span></span>|<span data-ttu-id="5dff3-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="5dff3-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="5dff3-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="5dff3-124">x-requestdigest</span></span>|<span data-ttu-id="5dff3-125">現在のサイトの適切なダイジェストです。</span><span class="sxs-lookup"><span data-stu-id="5dff3-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="5dff3-126">要求本文</span><span class="sxs-lookup"><span data-stu-id="5dff3-126">Request body</span></span>

|<span data-ttu-id="5dff3-127">名前</span><span class="sxs-lookup"><span data-stu-id="5dff3-127">Name</span></span>    |<span data-ttu-id="5dff3-128">種類</span><span class="sxs-lookup"><span data-stu-id="5dff3-128">Type</span></span>   |<span data-ttu-id="5dff3-129">説明</span><span class="sxs-lookup"><span data-stu-id="5dff3-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="5dff3-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="5dff3-130">ModelSettings</span></span>|<span data-ttu-id="5dff3-131">文字列</span><span class="sxs-lookup"><span data-stu-id="5dff3-131">string</span></span>|<span data-ttu-id="5dff3-132">モデル設定の JSON。</span><span class="sxs-lookup"><span data-stu-id="5dff3-132">JSON of model settings.</span></span>|
|<span data-ttu-id="5dff3-133">説明</span><span class="sxs-lookup"><span data-stu-id="5dff3-133">Description</span></span>|<span data-ttu-id="5dff3-134">string</span><span class="sxs-lookup"><span data-stu-id="5dff3-134">string</span></span>|<span data-ttu-id="5dff3-135">モデルの説明。</span><span class="sxs-lookup"><span data-stu-id="5dff3-135">The model description.</span></span>|
|<span data-ttu-id="5dff3-136">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="5dff3-136">RetentionLabel</span></span>| |<span data-ttu-id="5dff3-137">関連付けられているラベルの情報 (ラベル ID と名前)。</span><span class="sxs-lookup"><span data-stu-id="5dff3-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="5dff3-138">応答</span><span class="sxs-lookup"><span data-stu-id="5dff3-138">Responses</span></span>

| <span data-ttu-id="5dff3-139">名前</span><span class="sxs-lookup"><span data-stu-id="5dff3-139">Name</span></span>   | <span data-ttu-id="5dff3-140">種類</span><span class="sxs-lookup"><span data-stu-id="5dff3-140">Type</span></span>  | <span data-ttu-id="5dff3-141">説明</span><span class="sxs-lookup"><span data-stu-id="5dff3-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="5dff3-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="5dff3-142">200 OK</span></span>| |<span data-ttu-id="5dff3-143">成功</span><span class="sxs-lookup"><span data-stu-id="5dff3-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="5dff3-144">例</span><span class="sxs-lookup"><span data-stu-id="5dff3-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="5dff3-145">Contoso 契約のモデル設定を更新する</span><span class="sxs-lookup"><span data-stu-id="5dff3-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="5dff3-146">この例では、モデルの説明と "Standard Hold" 保持ラベルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="5dff3-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="5dff3-147">保持ラベルの　ID は `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6` です。</span><span class="sxs-lookup"><span data-stu-id="5dff3-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="5dff3-148">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="5dff3-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="5dff3-149">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="5dff3-149">Sample response</span></span>

<span data-ttu-id="5dff3-150">**Status code:** 200</span><span class="sxs-lookup"><span data-stu-id="5dff3-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="5dff3-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dff3-151">See also</span></span>

[<span data-ttu-id="5dff3-152">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="5dff3-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
