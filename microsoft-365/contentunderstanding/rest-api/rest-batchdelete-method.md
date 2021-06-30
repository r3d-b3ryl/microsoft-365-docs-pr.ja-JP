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
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177239"
---
# <a name="batchdelete"></a><span data-ttu-id="17cd6-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="17cd6-103">BatchDelete</span></span>

<span data-ttu-id="17cd6-104">適用された文書理解モデルを 1 つ以上のライブラリから削除します。</span><span class="sxs-lookup"><span data-stu-id="17cd6-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="17cd6-105">モデルを削除する前に、すべてのライブラリからそのモデルを削除する必要があることに注意してください ([例](rest-batchdelete-method.md#examples)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="17cd6-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="17cd6-106">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="17cd6-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="17cd6-107">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="17cd6-107">URI parameters</span></span>

<span data-ttu-id="17cd6-108">なし</span><span class="sxs-lookup"><span data-stu-id="17cd6-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="17cd6-109">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="17cd6-109">Request headers</span></span>

| <span data-ttu-id="17cd6-110">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="17cd6-110">Header</span></span> | <span data-ttu-id="17cd6-111">値</span><span class="sxs-lookup"><span data-stu-id="17cd6-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="17cd6-112">Accept</span><span class="sxs-lookup"><span data-stu-id="17cd6-112">Accept</span></span>|<span data-ttu-id="17cd6-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="17cd6-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="17cd6-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="17cd6-114">Content-Type</span></span>|<span data-ttu-id="17cd6-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="17cd6-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="17cd6-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="17cd6-116">x-requestdigest</span></span>|<span data-ttu-id="17cd6-117">現在のサイトの適切なダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="17cd6-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="17cd6-118">要求本文</span><span class="sxs-lookup"><span data-stu-id="17cd6-118">Request body</span></span>

| <span data-ttu-id="17cd6-119">名前</span><span class="sxs-lookup"><span data-stu-id="17cd6-119">Name</span></span> | <span data-ttu-id="17cd6-120">必須</span><span class="sxs-lookup"><span data-stu-id="17cd6-120">Required</span></span> | <span data-ttu-id="17cd6-121">型</span><span class="sxs-lookup"><span data-stu-id="17cd6-121">Type</span></span> | <span data-ttu-id="17cd6-122">説明</span><span class="sxs-lookup"><span data-stu-id="17cd6-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="17cd6-123">発行元</span><span class="sxs-lookup"><span data-stu-id="17cd6-123">Publications</span></span>|<span data-ttu-id="17cd6-124">○</span><span class="sxs-lookup"><span data-stu-id="17cd6-124">yes</span></span>|<span data-ttu-id="17cd6-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="17cd6-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="17cd6-126">それぞれがモデルとターゲット ドキュメント ライブラリを指定する MachineLearningPublicationEntityData のコレクション。</span><span class="sxs-lookup"><span data-stu-id="17cd6-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="17cd6-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="17cd6-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="17cd6-128">名前</span><span class="sxs-lookup"><span data-stu-id="17cd6-128">Name</span></span> | <span data-ttu-id="17cd6-129">必須</span><span class="sxs-lookup"><span data-stu-id="17cd6-129">Required</span></span> | <span data-ttu-id="17cd6-130">型</span><span class="sxs-lookup"><span data-stu-id="17cd6-130">Type</span></span> | <span data-ttu-id="17cd6-131">説明</span><span class="sxs-lookup"><span data-stu-id="17cd6-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="17cd6-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="17cd6-132">ModelUniqueId</span></span>|<span data-ttu-id="17cd6-133">○</span><span class="sxs-lookup"><span data-stu-id="17cd6-133">yes</span></span>|<span data-ttu-id="17cd6-134">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-134">string</span></span>|<span data-ttu-id="17cd6-135">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="17cd6-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="17cd6-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="17cd6-136">TargetSiteUrl</span></span>|<span data-ttu-id="17cd6-137">○</span><span class="sxs-lookup"><span data-stu-id="17cd6-137">yes</span></span>|<span data-ttu-id="17cd6-138">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-138">string</span></span>|<span data-ttu-id="17cd6-139">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="17cd6-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="17cd6-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="17cd6-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="17cd6-141">○</span><span class="sxs-lookup"><span data-stu-id="17cd6-141">yes</span></span>|<span data-ttu-id="17cd6-142">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-142">string</span></span>|<span data-ttu-id="17cd6-143">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="17cd6-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="17cd6-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="17cd6-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="17cd6-145">○</span><span class="sxs-lookup"><span data-stu-id="17cd6-145">yes</span></span>|<span data-ttu-id="17cd6-146">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-146">string</span></span>|<span data-ttu-id="17cd6-147">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="17cd6-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="17cd6-148">応答</span><span class="sxs-lookup"><span data-stu-id="17cd6-148">Response</span></span>

| <span data-ttu-id="17cd6-149">名前</span><span class="sxs-lookup"><span data-stu-id="17cd6-149">Name</span></span>   | <span data-ttu-id="17cd6-150">種類</span><span class="sxs-lookup"><span data-stu-id="17cd6-150">Type</span></span>  | <span data-ttu-id="17cd6-151">説明</span><span class="sxs-lookup"><span data-stu-id="17cd6-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="17cd6-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="17cd6-152">200 OK</span></span>||<span data-ttu-id="17cd6-153">これは、複数のドキュメント ライブラリからのモデルの削除をサポートするためにカスタマイズされた API です。</span><span class="sxs-lookup"><span data-stu-id="17cd6-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="17cd6-154">部分的に成功した場合でも、200 OK が返される可能性があり、呼び出し元は応答本文を調べて、モデルがドキュメント ライブラリから正常に削除されたかどうかを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17cd6-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="17cd6-155">応答本文</span><span class="sxs-lookup"><span data-stu-id="17cd6-155">Response Body</span></span>
| <span data-ttu-id="17cd6-156">名前</span><span class="sxs-lookup"><span data-stu-id="17cd6-156">Name</span></span>   | <span data-ttu-id="17cd6-157">種類</span><span class="sxs-lookup"><span data-stu-id="17cd6-157">Type</span></span>  | <span data-ttu-id="17cd6-158">説明</span><span class="sxs-lookup"><span data-stu-id="17cd6-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="17cd6-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="17cd6-159">TotalSuccesses</span></span>|<span data-ttu-id="17cd6-160">整数</span><span class="sxs-lookup"><span data-stu-id="17cd6-160">int</span></span>|<span data-ttu-id="17cd6-161">ドキュメント ライブラリから正常に削除されたモデルの総数。</span><span class="sxs-lookup"><span data-stu-id="17cd6-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="17cd6-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="17cd6-162">TotalFailures</span></span>|<span data-ttu-id="17cd6-163">整数</span><span class="sxs-lookup"><span data-stu-id="17cd6-163">int</span></span>|<span data-ttu-id="17cd6-164">ドキュメント ライブラリからの削除に失敗したモデルの総数。</span><span class="sxs-lookup"><span data-stu-id="17cd6-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="17cd6-165">詳細</span><span class="sxs-lookup"><span data-stu-id="17cd6-165">Details</span></span>|<span data-ttu-id="17cd6-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="17cd6-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="17cd6-167">MachineLearningPublicationResult のコレクション。それぞれが、ドキュメント ライブラリからモデルを削除した詳細な結果を指定します。</span><span class="sxs-lookup"><span data-stu-id="17cd6-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="17cd6-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="17cd6-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="17cd6-169">名前</span><span class="sxs-lookup"><span data-stu-id="17cd6-169">Name</span></span>   | <span data-ttu-id="17cd6-170">種類</span><span class="sxs-lookup"><span data-stu-id="17cd6-170">Type</span></span>  | <span data-ttu-id="17cd6-171">説明</span><span class="sxs-lookup"><span data-stu-id="17cd6-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="17cd6-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="17cd6-172">StatusCode</span></span>|<span data-ttu-id="17cd6-173">整数</span><span class="sxs-lookup"><span data-stu-id="17cd6-173">int</span></span>|<span data-ttu-id="17cd6-174">HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="17cd6-174">The HTTP status code.</span></span>|
|<span data-ttu-id="17cd6-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="17cd6-175">ErrorMessage</span></span>|<span data-ttu-id="17cd6-176">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-176">string</span></span>|<span data-ttu-id="17cd6-177">モデルをドキュメント ライブラリに適用するときに何が問題になっているのかを示すエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="17cd6-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="17cd6-178">発行元</span><span class="sxs-lookup"><span data-stu-id="17cd6-178">Publication</span></span>|<span data-ttu-id="17cd6-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="17cd6-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="17cd6-180">モデル情報とターゲット ドキュメント ライブラリを指定します。</span><span class="sxs-lookup"><span data-stu-id="17cd6-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="17cd6-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="17cd6-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="17cd6-182">名前</span><span class="sxs-lookup"><span data-stu-id="17cd6-182">Name</span></span> | <span data-ttu-id="17cd6-183">種類</span><span class="sxs-lookup"><span data-stu-id="17cd6-183">Type</span></span> | <span data-ttu-id="17cd6-184">説明</span><span class="sxs-lookup"><span data-stu-id="17cd6-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="17cd6-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="17cd6-185">ModelUniqueId</span></span>|<span data-ttu-id="17cd6-186">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-186">string</span></span>|<span data-ttu-id="17cd6-187">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="17cd6-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="17cd6-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="17cd6-188">TargetSiteUrl</span></span>|<span data-ttu-id="17cd6-189">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-189">string</span></span>|<span data-ttu-id="17cd6-190">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="17cd6-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="17cd6-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="17cd6-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="17cd6-192">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-192">string</span></span>|<span data-ttu-id="17cd6-193">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="17cd6-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="17cd6-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="17cd6-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="17cd6-195">文字列</span><span class="sxs-lookup"><span data-stu-id="17cd6-195">string</span></span>|<span data-ttu-id="17cd6-196">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="17cd6-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="17cd6-197">例</span><span class="sxs-lookup"><span data-stu-id="17cd6-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="17cd6-198">リポジトリ サイトの契約書ドキュメント ライブラリからモデルを削除する</span><span class="sxs-lookup"><span data-stu-id="17cd6-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="17cd6-199">このサンプルでは、Contoso 契約書文書理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。</span><span class="sxs-lookup"><span data-stu-id="17cd6-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="17cd6-200">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="17cd6-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a><span data-ttu-id="17cd6-201">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="17cd6-201">Sample response</span></span>

<span data-ttu-id="17cd6-202">応答では、TotalFailures と TotalSuccesses は、指定されたライブラリから削除されるモデルの失敗と成功の数を示します。</span><span class="sxs-lookup"><span data-stu-id="17cd6-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="17cd6-203">**Status code:** 200</span><span class="sxs-lookup"><span data-stu-id="17cd6-203">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="17cd6-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="17cd6-204">See also</span></span>

[<span data-ttu-id="17cd6-205">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="17cd6-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
