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
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286539"
---
# <a name="batch-apply-model"></a><span data-ttu-id="98eee-103">バッチ適用モデル</span><span class="sxs-lookup"><span data-stu-id="98eee-103">Batch Apply model</span></span>

<span data-ttu-id="98eee-104">トレーニング済みのドキュメント理解モデルを 1 つ以上のライブラリに適用 (または同期) します ( [例](rest-applymodel-method.md#examples)を参照)。</span><span class="sxs-lookup"><span data-stu-id="98eee-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="98eee-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="98eee-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="98eee-106">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="98eee-106">URI parameters</span></span>

<span data-ttu-id="98eee-107">なし</span><span class="sxs-lookup"><span data-stu-id="98eee-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="98eee-108">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="98eee-108">Request headers</span></span>

| <span data-ttu-id="98eee-109">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="98eee-109">Header</span></span> | <span data-ttu-id="98eee-110">値</span><span class="sxs-lookup"><span data-stu-id="98eee-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="98eee-111">Accept</span><span class="sxs-lookup"><span data-stu-id="98eee-111">Accept</span></span>|<span data-ttu-id="98eee-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="98eee-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="98eee-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="98eee-113">Content-Type</span></span>|<span data-ttu-id="98eee-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="98eee-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="98eee-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="98eee-115">x-requestdigest</span></span>|<span data-ttu-id="98eee-116">現在のサイトの適切なダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="98eee-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="98eee-117">要求本文</span><span class="sxs-lookup"><span data-stu-id="98eee-117">Request body</span></span>

| <span data-ttu-id="98eee-118">名前</span><span class="sxs-lookup"><span data-stu-id="98eee-118">Name</span></span> | <span data-ttu-id="98eee-119">必須</span><span class="sxs-lookup"><span data-stu-id="98eee-119">Required</span></span> | <span data-ttu-id="98eee-120">型</span><span class="sxs-lookup"><span data-stu-id="98eee-120">Type</span></span> | <span data-ttu-id="98eee-121">説明</span><span class="sxs-lookup"><span data-stu-id="98eee-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="98eee-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="98eee-122">__metadata</span></span>|<span data-ttu-id="98eee-123">○</span><span class="sxs-lookup"><span data-stu-id="98eee-123">yes</span></span>|<span data-ttu-id="98eee-124">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-124">string</span></span>|<span data-ttu-id="98eee-125">SPO でオブジェクト メタを設定します。</span><span class="sxs-lookup"><span data-stu-id="98eee-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="98eee-126">常に値 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"} を使用します。</span><span class="sxs-lookup"><span data-stu-id="98eee-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="98eee-127">発行元</span><span class="sxs-lookup"><span data-stu-id="98eee-127">Publications</span></span>|<span data-ttu-id="98eee-128">○</span><span class="sxs-lookup"><span data-stu-id="98eee-128">yes</span></span>|<span data-ttu-id="98eee-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="98eee-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="98eee-130">それぞれがモデルとターゲット ドキュメント ライブラリを指定する MachineLearningPublicationEntityData のコレクション。</span><span class="sxs-lookup"><span data-stu-id="98eee-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="98eee-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="98eee-131">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="98eee-132">名前</span><span class="sxs-lookup"><span data-stu-id="98eee-132">Name</span></span> | <span data-ttu-id="98eee-133">必須</span><span class="sxs-lookup"><span data-stu-id="98eee-133">Required</span></span> | <span data-ttu-id="98eee-134">型</span><span class="sxs-lookup"><span data-stu-id="98eee-134">Type</span></span> | <span data-ttu-id="98eee-135">説明</span><span class="sxs-lookup"><span data-stu-id="98eee-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="98eee-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="98eee-136">ModelUniqueId</span></span>|<span data-ttu-id="98eee-137">○</span><span class="sxs-lookup"><span data-stu-id="98eee-137">yes</span></span>|<span data-ttu-id="98eee-138">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-138">string</span></span>|<span data-ttu-id="98eee-139">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="98eee-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="98eee-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="98eee-140">TargetSiteUrl</span></span>|<span data-ttu-id="98eee-141">○</span><span class="sxs-lookup"><span data-stu-id="98eee-141">yes</span></span>|<span data-ttu-id="98eee-142">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-142">string</span></span>|<span data-ttu-id="98eee-143">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="98eee-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="98eee-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="98eee-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="98eee-145">○</span><span class="sxs-lookup"><span data-stu-id="98eee-145">yes</span></span>|<span data-ttu-id="98eee-146">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-146">string</span></span>|<span data-ttu-id="98eee-147">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="98eee-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="98eee-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="98eee-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="98eee-149">○</span><span class="sxs-lookup"><span data-stu-id="98eee-149">yes</span></span>|<span data-ttu-id="98eee-150">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-150">string</span></span>|<span data-ttu-id="98eee-151">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="98eee-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="98eee-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="98eee-152">ViewOption</span></span>|<span data-ttu-id="98eee-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="98eee-153">no</span></span>|<span data-ttu-id="98eee-154">string</span><span class="sxs-lookup"><span data-stu-id="98eee-154">string</span></span>|<span data-ttu-id="98eee-155">新しいモデル ビューをライブラリの既定値として設定するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="98eee-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="98eee-156">応答</span><span class="sxs-lookup"><span data-stu-id="98eee-156">Response</span></span>

| <span data-ttu-id="98eee-157">名前</span><span class="sxs-lookup"><span data-stu-id="98eee-157">Name</span></span>   | <span data-ttu-id="98eee-158">種類</span><span class="sxs-lookup"><span data-stu-id="98eee-158">Type</span></span>  | <span data-ttu-id="98eee-159">説明</span><span class="sxs-lookup"><span data-stu-id="98eee-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="98eee-160">201 Created</span><span class="sxs-lookup"><span data-stu-id="98eee-160">201 Created</span></span>||<span data-ttu-id="98eee-p102">これは、複数のドキュメント ライブラリへのモデルの適用をサポートするためにカスタマイズされた API です。部分的に成功した場合でも、作成された 201 が返される可能性があり、呼び出し元は応答本文を調べて、モデルがドキュメント ライブラリに正常に適用されたかどうかを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eee-p102">This is a customized API to support applying a model to multi document libraries. In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="98eee-163">応答本文</span><span class="sxs-lookup"><span data-stu-id="98eee-163">Response Body</span></span>

| <span data-ttu-id="98eee-164">名前</span><span class="sxs-lookup"><span data-stu-id="98eee-164">Name</span></span>   | <span data-ttu-id="98eee-165">種類</span><span class="sxs-lookup"><span data-stu-id="98eee-165">Type</span></span>  | <span data-ttu-id="98eee-166">説明</span><span class="sxs-lookup"><span data-stu-id="98eee-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="98eee-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="98eee-167">TotalSuccesses</span></span>|<span data-ttu-id="98eee-168">整数</span><span class="sxs-lookup"><span data-stu-id="98eee-168">int</span></span>|<span data-ttu-id="98eee-169">ドキュメント ライブラリに正常に適用されたモデルの総数。</span><span class="sxs-lookup"><span data-stu-id="98eee-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="98eee-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="98eee-170">TotalFailures</span></span>|<span data-ttu-id="98eee-171">整数</span><span class="sxs-lookup"><span data-stu-id="98eee-171">int</span></span>|<span data-ttu-id="98eee-172">ドキュメント ライブラリへの適用に失敗したモデルの総数。</span><span class="sxs-lookup"><span data-stu-id="98eee-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="98eee-173">詳細</span><span class="sxs-lookup"><span data-stu-id="98eee-173">Details</span></span>|<span data-ttu-id="98eee-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="98eee-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="98eee-175">MachineLearningPublicationResult のコレクション。それぞれが、ドキュメント ライブラリにモデルを適用した詳細な結果を指定します。</span><span class="sxs-lookup"><span data-stu-id="98eee-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="98eee-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="98eee-176">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="98eee-177">名前</span><span class="sxs-lookup"><span data-stu-id="98eee-177">Name</span></span>   | <span data-ttu-id="98eee-178">種類</span><span class="sxs-lookup"><span data-stu-id="98eee-178">Type</span></span>  | <span data-ttu-id="98eee-179">説明</span><span class="sxs-lookup"><span data-stu-id="98eee-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="98eee-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="98eee-180">StatusCode</span></span>|<span data-ttu-id="98eee-181">整数</span><span class="sxs-lookup"><span data-stu-id="98eee-181">int</span></span>|<span data-ttu-id="98eee-182">HTTP 状態コード。</span><span class="sxs-lookup"><span data-stu-id="98eee-182">The HTTP status code.</span></span>|
|<span data-ttu-id="98eee-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="98eee-183">ErrorMessage</span></span>|<span data-ttu-id="98eee-184">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-184">string</span></span>|<span data-ttu-id="98eee-185">モデルをドキュメント ライブラリに適用するときに何が問題になっているのかを示すエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="98eee-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="98eee-186">発行元</span><span class="sxs-lookup"><span data-stu-id="98eee-186">Publication</span></span>|<span data-ttu-id="98eee-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="98eee-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="98eee-188">モデル情報とターゲット ドキュメント ライブラリを指定します。</span><span class="sxs-lookup"><span data-stu-id="98eee-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="98eee-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="98eee-189">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="98eee-190">名前</span><span class="sxs-lookup"><span data-stu-id="98eee-190">Name</span></span> | <span data-ttu-id="98eee-191">種類</span><span class="sxs-lookup"><span data-stu-id="98eee-191">Type</span></span> | <span data-ttu-id="98eee-192">説明</span><span class="sxs-lookup"><span data-stu-id="98eee-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="98eee-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="98eee-193">ModelUniqueId</span></span>|<span data-ttu-id="98eee-194">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-194">string</span></span>|<span data-ttu-id="98eee-195">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="98eee-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="98eee-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="98eee-196">TargetSiteUrl</span></span>|<span data-ttu-id="98eee-197">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-197">string</span></span>|<span data-ttu-id="98eee-198">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="98eee-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="98eee-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="98eee-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="98eee-200">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-200">string</span></span>|<span data-ttu-id="98eee-201">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="98eee-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="98eee-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="98eee-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="98eee-203">文字列</span><span class="sxs-lookup"><span data-stu-id="98eee-203">string</span></span>|<span data-ttu-id="98eee-204">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="98eee-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="98eee-205">例</span><span class="sxs-lookup"><span data-stu-id="98eee-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="98eee-206">リポジトリ サイトの契約書ドキュメント ライブラリにモデルを適用する</span><span class="sxs-lookup"><span data-stu-id="98eee-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="98eee-207">このサンプルでは、Contoso 契約書ドキュメント理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。</span><span class="sxs-lookup"><span data-stu-id="98eee-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="98eee-208">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="98eee-208">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="98eee-209">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="98eee-209">Sample response</span></span>

<span data-ttu-id="98eee-210">応答では、TotalFailures と TotalSuccinstalls は、指定されたライブラリに適用されるモデルの失敗と成功の数を示します。</span><span class="sxs-lookup"><span data-stu-id="98eee-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="98eee-211">**状態コード :** 201</span><span class="sxs-lookup"><span data-stu-id="98eee-211">**Status code:** 201</span></span>

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

## <a name="see-also"></a><span data-ttu-id="98eee-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="98eee-212">See also</span></span>

[<span data-ttu-id="98eee-213">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="98eee-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
