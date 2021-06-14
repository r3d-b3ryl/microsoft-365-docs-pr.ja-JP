---
title: BatchDelete
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
description: REST API を使用して、適用された文書理解モデルを 1 つ以上のライブラリから削除します。
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904273"
---
# <a name="batchdelete"></a><span data-ttu-id="b805f-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="b805f-103">BatchDelete</span></span>

<span data-ttu-id="b805f-104">適用された文書理解モデルを 1 つ以上のライブラリから削除します。</span><span class="sxs-lookup"><span data-stu-id="b805f-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="b805f-105">モデルを削除する前に、すべてのライブラリからそのモデルを削除する必要があることに注意してください ([例](rest-batchdelete-method.md#examples)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b805f-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="b805f-106">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b805f-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="b805f-107">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="b805f-107">URI parameters</span></span>

<span data-ttu-id="b805f-108">なし</span><span class="sxs-lookup"><span data-stu-id="b805f-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="b805f-109">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b805f-109">Request headers</span></span>

| <span data-ttu-id="b805f-110">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b805f-110">Header</span></span> | <span data-ttu-id="b805f-111">値</span><span class="sxs-lookup"><span data-stu-id="b805f-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="b805f-112">Accept</span><span class="sxs-lookup"><span data-stu-id="b805f-112">Accept</span></span>|<span data-ttu-id="b805f-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="b805f-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="b805f-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b805f-114">Content-Type</span></span>|<span data-ttu-id="b805f-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="b805f-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="b805f-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="b805f-116">x-requestdigest</span></span>|<span data-ttu-id="b805f-117">現在のサイトの適切なダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="b805f-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="b805f-118">要求本文</span><span class="sxs-lookup"><span data-stu-id="b805f-118">Request body</span></span>

| <span data-ttu-id="b805f-119">名前</span><span class="sxs-lookup"><span data-stu-id="b805f-119">Name</span></span> | <span data-ttu-id="b805f-120">必須</span><span class="sxs-lookup"><span data-stu-id="b805f-120">Required</span></span> | <span data-ttu-id="b805f-121">型</span><span class="sxs-lookup"><span data-stu-id="b805f-121">Type</span></span> | <span data-ttu-id="b805f-122">説明</span><span class="sxs-lookup"><span data-stu-id="b805f-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="b805f-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="b805f-123">ModelUniqueId</span></span>|<span data-ttu-id="b805f-124">○</span><span class="sxs-lookup"><span data-stu-id="b805f-124">yes</span></span>|<span data-ttu-id="b805f-125">文字列</span><span class="sxs-lookup"><span data-stu-id="b805f-125">string</span></span>|<span data-ttu-id="b805f-126">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="b805f-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="b805f-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="b805f-127">TargetSiteUrl</span></span>|<span data-ttu-id="b805f-128">○</span><span class="sxs-lookup"><span data-stu-id="b805f-128">yes</span></span>|<span data-ttu-id="b805f-129">文字列</span><span class="sxs-lookup"><span data-stu-id="b805f-129">string</span></span>|<span data-ttu-id="b805f-130">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="b805f-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="b805f-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="b805f-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="b805f-132">○</span><span class="sxs-lookup"><span data-stu-id="b805f-132">yes</span></span>|<span data-ttu-id="b805f-133">文字列</span><span class="sxs-lookup"><span data-stu-id="b805f-133">string</span></span>|<span data-ttu-id="b805f-134">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="b805f-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="b805f-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="b805f-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="b805f-136">○</span><span class="sxs-lookup"><span data-stu-id="b805f-136">yes</span></span>|<span data-ttu-id="b805f-137">文字列</span><span class="sxs-lookup"><span data-stu-id="b805f-137">string</span></span>|<span data-ttu-id="b805f-138">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="b805f-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="b805f-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="b805f-139">ViewOption</span></span>|<span data-ttu-id="b805f-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="b805f-140">no</span></span>|<span data-ttu-id="b805f-141">string</span><span class="sxs-lookup"><span data-stu-id="b805f-141">string</span></span>|<span data-ttu-id="b805f-142">新しいモデル ビューをライブラリの既定値として設定するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b805f-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="b805f-143">応答</span><span class="sxs-lookup"><span data-stu-id="b805f-143">Response</span></span>

| <span data-ttu-id="b805f-144">名前</span><span class="sxs-lookup"><span data-stu-id="b805f-144">Name</span></span>   | <span data-ttu-id="b805f-145">型</span><span class="sxs-lookup"><span data-stu-id="b805f-145">Type</span></span>  | <span data-ttu-id="b805f-146">説明</span><span class="sxs-lookup"><span data-stu-id="b805f-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="b805f-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="b805f-147">200 OK</span></span>| |<span data-ttu-id="b805f-148">成功</span><span class="sxs-lookup"><span data-stu-id="b805f-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="b805f-149">例</span><span class="sxs-lookup"><span data-stu-id="b805f-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="b805f-150">リポジトリ サイトの契約書ドキュメント ライブラリからモデルを削除する</span><span class="sxs-lookup"><span data-stu-id="b805f-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="b805f-151">このサンプルでは、Contoso 契約書文書理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。</span><span class="sxs-lookup"><span data-stu-id="b805f-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="b805f-152">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="b805f-152">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="b805f-153">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="b805f-153">Sample response</span></span>

<span data-ttu-id="b805f-154">応答では、TotalFailures と TotalSuccesses は、指定されたライブラリに適用されるモデルの失敗と成功の数を示します。</span><span class="sxs-lookup"><span data-stu-id="b805f-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="b805f-155">**Status code:** 200</span><span class="sxs-lookup"><span data-stu-id="b805f-155">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="b805f-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="b805f-156">See also</span></span>

[<span data-ttu-id="b805f-157">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="b805f-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
