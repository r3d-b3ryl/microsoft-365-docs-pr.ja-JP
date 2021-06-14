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
ms.openlocfilehash: 6a218db181368c2837d570062b6101bc3bacfb05
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904282"
---
# <a name="create-classification-request"></a><span data-ttu-id="2fe72-103">分類要求の作成</span><span class="sxs-lookup"><span data-stu-id="2fe72-103">Create classification request</span></span>

<span data-ttu-id="2fe72-104">適用された文書理解モデルを使用して 1 つ以上のファイルを分類する要求を作成します ( [例](rest-createclassificationrequest.md#examples)参照)。</span><span class="sxs-lookup"><span data-stu-id="2fe72-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="2fe72-105">SharePoint Online (および SharePoint 2016 以降のオンプレミス) REST サービスでは、OData $batch クエリ オプションを使って、サービスに対する複数の要求の組み合わせがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fe72-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="2fe72-106">要求は、OData $batch クエリ オプションを使用して、サービスへの 1 回の呼び出しに結合されます。</span><span class="sxs-lookup"><span data-stu-id="2fe72-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="2fe72-107">この方法を使用すると、一度に数百のドキュメントの分類作業項目をキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="2fe72-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="2fe72-108">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="2fe72-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="2fe72-109">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fe72-109">URI Parameters</span></span>

<span data-ttu-id="2fe72-110">なし</span><span class="sxs-lookup"><span data-stu-id="2fe72-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="2fe72-111">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="2fe72-111">Request headers</span></span>

| <span data-ttu-id="2fe72-112">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="2fe72-112">Header</span></span> | <span data-ttu-id="2fe72-113">値</span><span class="sxs-lookup"><span data-stu-id="2fe72-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="2fe72-114">Accept</span><span class="sxs-lookup"><span data-stu-id="2fe72-114">Accept</span></span>|<span data-ttu-id="2fe72-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="2fe72-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="2fe72-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2fe72-116">Content-Type</span></span>|<span data-ttu-id="2fe72-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="2fe72-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="2fe72-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="2fe72-118">x-requestdigest</span></span>|<span data-ttu-id="2fe72-119">現在のサイトの適切なダイジェスト</span><span class="sxs-lookup"><span data-stu-id="2fe72-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="2fe72-120">要求本文</span><span class="sxs-lookup"><span data-stu-id="2fe72-120">Request body</span></span>

|<span data-ttu-id="2fe72-121">名前</span><span class="sxs-lookup"><span data-stu-id="2fe72-121">Name</span></span>    |<span data-ttu-id="2fe72-122">型</span><span class="sxs-lookup"><span data-stu-id="2fe72-122">Type</span></span>   |<span data-ttu-id="2fe72-123">説明</span><span class="sxs-lookup"><span data-stu-id="2fe72-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="2fe72-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="2fe72-124">_metadata</span></span>|<span data-ttu-id="2fe72-125">文字列</span><span class="sxs-lookup"><span data-stu-id="2fe72-125">string</span></span> |<span data-ttu-id="2fe72-126">SPO でオブジェクト メタを設定します。</span><span class="sxs-lookup"><span data-stu-id="2fe72-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="2fe72-127">常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"} を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe72-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="2fe72-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="2fe72-128">TargetSiteId</span></span>|<span data-ttu-id="2fe72-129">guid</span><span class="sxs-lookup"><span data-stu-id="2fe72-129">guid</span></span>|<span data-ttu-id="2fe72-130">分類するファイルが配置されているサイトの ID。</span><span class="sxs-lookup"><span data-stu-id="2fe72-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="2fe72-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="2fe72-131">TargetWebId</span></span>|<span data-ttu-id="2fe72-132">guid</span><span class="sxs-lookup"><span data-stu-id="2fe72-132">guid</span></span>|<span data-ttu-id="2fe72-133">分類するファイルがある Web の ID。</span><span class="sxs-lookup"><span data-stu-id="2fe72-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="2fe72-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="2fe72-134">TargetUniqueId</span></span>|<span data-ttu-id="2fe72-135">guid</span><span class="sxs-lookup"><span data-stu-id="2fe72-135">guid</span></span>|<span data-ttu-id="2fe72-136">更新するファイルの ID です。</span><span class="sxs-lookup"><span data-stu-id="2fe72-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="2fe72-137">応答</span><span class="sxs-lookup"><span data-stu-id="2fe72-137">Responses</span></span>

| <span data-ttu-id="2fe72-138">名前</span><span class="sxs-lookup"><span data-stu-id="2fe72-138">Name</span></span>   | <span data-ttu-id="2fe72-139">型</span><span class="sxs-lookup"><span data-stu-id="2fe72-139">Type</span></span>  | <span data-ttu-id="2fe72-140">説明</span><span class="sxs-lookup"><span data-stu-id="2fe72-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="2fe72-141">201 Created</span><span class="sxs-lookup"><span data-stu-id="2fe72-141">201 Created</span></span>| |<span data-ttu-id="2fe72-142">成功</span><span class="sxs-lookup"><span data-stu-id="2fe72-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="2fe72-143">例</span><span class="sxs-lookup"><span data-stu-id="2fe72-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="2fe72-144">ID "e6cff8b7-c90c-4564-b5b8-033449090932" のファイルを分類するための要求をキューに入れる</span><span class="sxs-lookup"><span data-stu-id="2fe72-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="2fe72-145">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="2fe72-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="2fe72-146">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="2fe72-146">Sample response</span></span>

<span data-ttu-id="2fe72-147">**状態コード :** 201</span><span class="sxs-lookup"><span data-stu-id="2fe72-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="2fe72-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fe72-148">See also</span></span>

[<span data-ttu-id="2fe72-149">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="2fe72-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
