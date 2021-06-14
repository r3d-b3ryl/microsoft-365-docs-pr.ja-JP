---
title: モデルを適用
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
description: REST APIを使用して、ドキュメント理解モデルを 1 つ以上のライブラリに適用します。
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904353"
---
# <a name="apply-model"></a><span data-ttu-id="68482-103">モデルを適用</span><span class="sxs-lookup"><span data-stu-id="68482-103">Apply model</span></span>

<span data-ttu-id="68482-104">トレーニング済みのドキュメント理解モデルを 1 つ以上のライブラリに適用 (または同期) します ( [例](rest-applymodel-method.md#examples)を参照)。</span><span class="sxs-lookup"><span data-stu-id="68482-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="68482-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="68482-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="68482-106">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="68482-106">URI parameters</span></span>

<span data-ttu-id="68482-107">なし</span><span class="sxs-lookup"><span data-stu-id="68482-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="68482-108">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="68482-108">Request headers</span></span>

| <span data-ttu-id="68482-109">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="68482-109">Header</span></span> | <span data-ttu-id="68482-110">値</span><span class="sxs-lookup"><span data-stu-id="68482-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="68482-111">Accept</span><span class="sxs-lookup"><span data-stu-id="68482-111">Accept</span></span>|<span data-ttu-id="68482-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="68482-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="68482-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="68482-113">Content-Type</span></span>|<span data-ttu-id="68482-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="68482-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="68482-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="68482-115">x-requestdigest</span></span>|<span data-ttu-id="68482-116">現在のサイトの適切なダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="68482-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="68482-117">要求本文</span><span class="sxs-lookup"><span data-stu-id="68482-117">Request body</span></span>

| <span data-ttu-id="68482-118">名前</span><span class="sxs-lookup"><span data-stu-id="68482-118">Name</span></span> | <span data-ttu-id="68482-119">必須</span><span class="sxs-lookup"><span data-stu-id="68482-119">Required</span></span> | <span data-ttu-id="68482-120">型</span><span class="sxs-lookup"><span data-stu-id="68482-120">Type</span></span> | <span data-ttu-id="68482-121">説明</span><span class="sxs-lookup"><span data-stu-id="68482-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="68482-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="68482-122">ModelUniqueId</span></span>|<span data-ttu-id="68482-123">○</span><span class="sxs-lookup"><span data-stu-id="68482-123">yes</span></span>|<span data-ttu-id="68482-124">文字列</span><span class="sxs-lookup"><span data-stu-id="68482-124">string</span></span>|<span data-ttu-id="68482-125">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="68482-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="68482-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="68482-126">TargetSiteUrl</span></span>|<span data-ttu-id="68482-127">○</span><span class="sxs-lookup"><span data-stu-id="68482-127">yes</span></span>|<span data-ttu-id="68482-128">文字列</span><span class="sxs-lookup"><span data-stu-id="68482-128">string</span></span>|<span data-ttu-id="68482-129">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="68482-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="68482-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="68482-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="68482-131">○</span><span class="sxs-lookup"><span data-stu-id="68482-131">yes</span></span>|<span data-ttu-id="68482-132">文字列</span><span class="sxs-lookup"><span data-stu-id="68482-132">string</span></span>|<span data-ttu-id="68482-133">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="68482-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="68482-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="68482-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="68482-135">○</span><span class="sxs-lookup"><span data-stu-id="68482-135">yes</span></span>|<span data-ttu-id="68482-136">文字列</span><span class="sxs-lookup"><span data-stu-id="68482-136">string</span></span>|<span data-ttu-id="68482-137">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="68482-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="68482-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="68482-138">ViewOption</span></span>|<span data-ttu-id="68482-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="68482-139">no</span></span>|<span data-ttu-id="68482-140">string</span><span class="sxs-lookup"><span data-stu-id="68482-140">string</span></span>|<span data-ttu-id="68482-141">新しいモデル ビューをライブラリの既定値として設定するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="68482-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="68482-142">応答</span><span class="sxs-lookup"><span data-stu-id="68482-142">Response</span></span>

| <span data-ttu-id="68482-143">名前</span><span class="sxs-lookup"><span data-stu-id="68482-143">Name</span></span>   | <span data-ttu-id="68482-144">型</span><span class="sxs-lookup"><span data-stu-id="68482-144">Type</span></span>  | <span data-ttu-id="68482-145">説明</span><span class="sxs-lookup"><span data-stu-id="68482-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="68482-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="68482-146">200 OK</span></span>| |<span data-ttu-id="68482-147">成功</span><span class="sxs-lookup"><span data-stu-id="68482-147">Success</span></span>|
|<span data-ttu-id="68482-148">201 Created</span><span class="sxs-lookup"><span data-stu-id="68482-148">201 Created</span></span>| |<span data-ttu-id="68482-149">この API では複数のライブラリへのモデルの適用がサポートされているため、いずれかのライブラリにモデルを適用する際にエラーが発生した場合でも、201 が返される可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="68482-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="68482-150">応答本文を調べて、モデルが指定されたすべてのライブラリに正常に適用されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="68482-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="68482-151">詳細については [要求本文](rest-applymodel-method.md#request-body) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68482-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="68482-152">例</span><span class="sxs-lookup"><span data-stu-id="68482-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="68482-153">リポジトリ サイトの契約書ドキュメント ライブラリにモデルを適用する</span><span class="sxs-lookup"><span data-stu-id="68482-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="68482-154">このサンプルでは、Contoso 契約書ドキュメント理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。</span><span class="sxs-lookup"><span data-stu-id="68482-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="68482-155">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="68482-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="68482-156">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="68482-156">Sample response</span></span>

<span data-ttu-id="68482-157">応答では、TotalFailures と TotalSuccinstalls は、指定されたライブラリに適用されるモデルの失敗と成功の数を示します。</span><span class="sxs-lookup"><span data-stu-id="68482-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="68482-158">**Status code:** 200</span><span class="sxs-lookup"><span data-stu-id="68482-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="68482-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="68482-159">See also</span></span>

[<span data-ttu-id="68482-160">Syntex ドキュメント理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="68482-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
