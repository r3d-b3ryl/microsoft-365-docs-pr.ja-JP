---
title: バッチ適用モデル
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
description: REST API を使用して、ドキュメント理解モデルを 1 つ以上のライブラリに適用します。
ms.openlocfilehash: 24ea9a480bc3ce5a7745857de17a6fab6ed97685
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177263"
---
# <a name="batch-apply-model"></a><span data-ttu-id="424f7-103">バッチ適用モデル</span><span class="sxs-lookup"><span data-stu-id="424f7-103">Batch Apply model</span></span>

<span data-ttu-id="424f7-104">トレーニング済みのドキュメント理解モデルを 1 つ以上のライブラリに適用 (または同期) します ( [例](rest-applymodel-method.md#examples)を参照)。</span><span class="sxs-lookup"><span data-stu-id="424f7-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="424f7-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="424f7-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="424f7-106">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="424f7-106">URI parameters</span></span>

<span data-ttu-id="424f7-107">なし</span><span class="sxs-lookup"><span data-stu-id="424f7-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="424f7-108">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="424f7-108">Request headers</span></span>

| <span data-ttu-id="424f7-109">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="424f7-109">Header</span></span> | <span data-ttu-id="424f7-110">値</span><span class="sxs-lookup"><span data-stu-id="424f7-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="424f7-111">Accept</span><span class="sxs-lookup"><span data-stu-id="424f7-111">Accept</span></span>|<span data-ttu-id="424f7-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="424f7-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="424f7-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="424f7-113">Content-Type</span></span>|<span data-ttu-id="424f7-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="424f7-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="424f7-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="424f7-115">x-requestdigest</span></span>|<span data-ttu-id="424f7-116">現在のサイトの適切なダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="424f7-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="424f7-117">要求本文</span><span class="sxs-lookup"><span data-stu-id="424f7-117">Request body</span></span>

| <span data-ttu-id="424f7-118">名前</span><span class="sxs-lookup"><span data-stu-id="424f7-118">Name</span></span> | <span data-ttu-id="424f7-119">必須</span><span class="sxs-lookup"><span data-stu-id="424f7-119">Required</span></span> | <span data-ttu-id="424f7-120">型</span><span class="sxs-lookup"><span data-stu-id="424f7-120">Type</span></span> | <span data-ttu-id="424f7-121">説明</span><span class="sxs-lookup"><span data-stu-id="424f7-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="424f7-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="424f7-122">__metadata</span></span>|<span data-ttu-id="424f7-123">○</span><span class="sxs-lookup"><span data-stu-id="424f7-123">yes</span></span>|<span data-ttu-id="424f7-124">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-124">string</span></span>|<span data-ttu-id="424f7-125">SPO でオブジェクト メタを設定します。</span><span class="sxs-lookup"><span data-stu-id="424f7-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="424f7-126">常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"} を使用します。</span><span class="sxs-lookup"><span data-stu-id="424f7-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="424f7-127">発行元</span><span class="sxs-lookup"><span data-stu-id="424f7-127">Publications</span></span>|<span data-ttu-id="424f7-128">○</span><span class="sxs-lookup"><span data-stu-id="424f7-128">yes</span></span>|<span data-ttu-id="424f7-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="424f7-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="424f7-130">それぞれがモデルとターゲット ドキュメント ライブラリを指定する MachineLearningPublicationEntityData のコレクション。</span><span class="sxs-lookup"><span data-stu-id="424f7-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="424f7-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="424f7-131">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="424f7-132">名前</span><span class="sxs-lookup"><span data-stu-id="424f7-132">Name</span></span> | <span data-ttu-id="424f7-133">必須</span><span class="sxs-lookup"><span data-stu-id="424f7-133">Required</span></span> | <span data-ttu-id="424f7-134">型</span><span class="sxs-lookup"><span data-stu-id="424f7-134">Type</span></span> | <span data-ttu-id="424f7-135">説明</span><span class="sxs-lookup"><span data-stu-id="424f7-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="424f7-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="424f7-136">ModelUniqueId</span></span>|<span data-ttu-id="424f7-137">○</span><span class="sxs-lookup"><span data-stu-id="424f7-137">yes</span></span>|<span data-ttu-id="424f7-138">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-138">string</span></span>|<span data-ttu-id="424f7-139">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="424f7-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="424f7-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="424f7-140">TargetSiteUrl</span></span>|<span data-ttu-id="424f7-141">○</span><span class="sxs-lookup"><span data-stu-id="424f7-141">yes</span></span>|<span data-ttu-id="424f7-142">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-142">string</span></span>|<span data-ttu-id="424f7-143">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="424f7-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="424f7-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="424f7-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="424f7-145">○</span><span class="sxs-lookup"><span data-stu-id="424f7-145">yes</span></span>|<span data-ttu-id="424f7-146">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-146">string</span></span>|<span data-ttu-id="424f7-147">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="424f7-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="424f7-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="424f7-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="424f7-149">○</span><span class="sxs-lookup"><span data-stu-id="424f7-149">yes</span></span>|<span data-ttu-id="424f7-150">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-150">string</span></span>|<span data-ttu-id="424f7-151">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="424f7-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="424f7-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="424f7-152">ViewOption</span></span>|<span data-ttu-id="424f7-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="424f7-153">no</span></span>|<span data-ttu-id="424f7-154">string</span><span class="sxs-lookup"><span data-stu-id="424f7-154">string</span></span>|<span data-ttu-id="424f7-155">新しいモデル ビューをライブラリの既定値として設定するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="424f7-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="424f7-156">応答</span><span class="sxs-lookup"><span data-stu-id="424f7-156">Response</span></span>

| <span data-ttu-id="424f7-157">名前</span><span class="sxs-lookup"><span data-stu-id="424f7-157">Name</span></span>   | <span data-ttu-id="424f7-158">種類</span><span class="sxs-lookup"><span data-stu-id="424f7-158">Type</span></span>  | <span data-ttu-id="424f7-159">説明</span><span class="sxs-lookup"><span data-stu-id="424f7-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="424f7-160">201 Created</span><span class="sxs-lookup"><span data-stu-id="424f7-160">201 Created</span></span>||<span data-ttu-id="424f7-161">これは、複数のドキュメント ライブラリへのモデルの適用をサポートするためにカスタマイズされた API です。</span><span class="sxs-lookup"><span data-stu-id="424f7-161">This is a customized API to support applying a model to multi document libraries.</span></span> <span data-ttu-id="424f7-162">部分的に成功した場合でも、作成された 201 が返される可能性があり、呼び出し元は応答本文を調べて、モデルがドキュメント ライブラリに正常に適用されたかどうかを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="424f7-162">In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="424f7-163">応答本文</span><span class="sxs-lookup"><span data-stu-id="424f7-163">Response Body</span></span>
| <span data-ttu-id="424f7-164">名前</span><span class="sxs-lookup"><span data-stu-id="424f7-164">Name</span></span>   | <span data-ttu-id="424f7-165">種類</span><span class="sxs-lookup"><span data-stu-id="424f7-165">Type</span></span>  | <span data-ttu-id="424f7-166">説明</span><span class="sxs-lookup"><span data-stu-id="424f7-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="424f7-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="424f7-167">TotalSuccesses</span></span>|<span data-ttu-id="424f7-168">整数</span><span class="sxs-lookup"><span data-stu-id="424f7-168">int</span></span>|<span data-ttu-id="424f7-169">ドキュメント ライブラリに正常に適用されたモデルの総数。</span><span class="sxs-lookup"><span data-stu-id="424f7-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="424f7-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="424f7-170">TotalFailures</span></span>|<span data-ttu-id="424f7-171">整数</span><span class="sxs-lookup"><span data-stu-id="424f7-171">int</span></span>|<span data-ttu-id="424f7-172">ドキュメント ライブラリへの適用に失敗したモデルの総数。</span><span class="sxs-lookup"><span data-stu-id="424f7-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="424f7-173">詳細</span><span class="sxs-lookup"><span data-stu-id="424f7-173">Details</span></span>|<span data-ttu-id="424f7-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="424f7-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="424f7-175">MachineLearningPublicationResult のコレクション。それぞれが、ドキュメント ライブラリにモデルを適用した詳細な結果を指定します。</span><span class="sxs-lookup"><span data-stu-id="424f7-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="424f7-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="424f7-176">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="424f7-177">名前</span><span class="sxs-lookup"><span data-stu-id="424f7-177">Name</span></span>   | <span data-ttu-id="424f7-178">種類</span><span class="sxs-lookup"><span data-stu-id="424f7-178">Type</span></span>  | <span data-ttu-id="424f7-179">説明</span><span class="sxs-lookup"><span data-stu-id="424f7-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="424f7-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="424f7-180">StatusCode</span></span>|<span data-ttu-id="424f7-181">整数</span><span class="sxs-lookup"><span data-stu-id="424f7-181">int</span></span>|<span data-ttu-id="424f7-182">HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="424f7-182">The HTTP status code.</span></span>|
|<span data-ttu-id="424f7-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="424f7-183">ErrorMessage</span></span>|<span data-ttu-id="424f7-184">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-184">string</span></span>|<span data-ttu-id="424f7-185">モデルをドキュメント ライブラリに適用するときに何が問題になっているのかを示すエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="424f7-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="424f7-186">発行元</span><span class="sxs-lookup"><span data-stu-id="424f7-186">Publication</span></span>|<span data-ttu-id="424f7-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="424f7-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="424f7-188">モデル情報とターゲット ドキュメント ライブラリを指定します。</span><span class="sxs-lookup"><span data-stu-id="424f7-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="424f7-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="424f7-189">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="424f7-190">名前</span><span class="sxs-lookup"><span data-stu-id="424f7-190">Name</span></span> | <span data-ttu-id="424f7-191">種類</span><span class="sxs-lookup"><span data-stu-id="424f7-191">Type</span></span> | <span data-ttu-id="424f7-192">説明</span><span class="sxs-lookup"><span data-stu-id="424f7-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="424f7-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="424f7-193">ModelUniqueId</span></span>|<span data-ttu-id="424f7-194">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-194">string</span></span>|<span data-ttu-id="424f7-195">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="424f7-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="424f7-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="424f7-196">TargetSiteUrl</span></span>|<span data-ttu-id="424f7-197">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-197">string</span></span>|<span data-ttu-id="424f7-198">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="424f7-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="424f7-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="424f7-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="424f7-200">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-200">string</span></span>|<span data-ttu-id="424f7-201">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="424f7-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="424f7-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="424f7-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="424f7-203">文字列</span><span class="sxs-lookup"><span data-stu-id="424f7-203">string</span></span>|<span data-ttu-id="424f7-204">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="424f7-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="424f7-205">例</span><span class="sxs-lookup"><span data-stu-id="424f7-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="424f7-206">リポジトリ サイトの契約書ドキュメント ライブラリにモデルを適用する</span><span class="sxs-lookup"><span data-stu-id="424f7-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="424f7-207">このサンプルでは、Contoso 契約書ドキュメント理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。</span><span class="sxs-lookup"><span data-stu-id="424f7-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="424f7-208">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="424f7-208">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="424f7-209">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="424f7-209">Sample response</span></span>

<span data-ttu-id="424f7-210">応答では、TotalFailures と TotalSuccinstalls は、指定されたライブラリに適用されるモデルの失敗と成功の数を示します。</span><span class="sxs-lookup"><span data-stu-id="424f7-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="424f7-211">**状態コード :** 201</span><span class="sxs-lookup"><span data-stu-id="424f7-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="424f7-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="424f7-212">See also</span></span>

[<span data-ttu-id="424f7-213">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="424f7-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
