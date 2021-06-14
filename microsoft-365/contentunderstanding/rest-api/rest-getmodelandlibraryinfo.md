---
title: モデルとライブラリの情報を取得する
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
description: REST API を使用して、モデルとそれが適用されているライブラリに関する情報を取得します。
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904302"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="8d72b-103">モデルとライブラリの情報を取得する</span><span class="sxs-lookup"><span data-stu-id="8d72b-103">Get model and library information</span></span>

<span data-ttu-id="8d72b-104">モデルと、モデルが適用されているライブラリに関する情報を取得します ([例](rest-getmodelandlibraryinfo.md#examples)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8d72b-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="8d72b-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="8d72b-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="8d72b-106">URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d72b-106">URI parameters</span></span>

| <span data-ttu-id="8d72b-107">名前</span><span class="sxs-lookup"><span data-stu-id="8d72b-107">Name</span></span> | <span data-ttu-id="8d72b-108">In</span><span class="sxs-lookup"><span data-stu-id="8d72b-108">In</span></span> | <span data-ttu-id="8d72b-109">必須</span><span class="sxs-lookup"><span data-stu-id="8d72b-109">Required</span></span> | <span data-ttu-id="8d72b-110">型</span><span class="sxs-lookup"><span data-stu-id="8d72b-110">Type</span></span> | <span data-ttu-id="8d72b-111">説明</span><span class="sxs-lookup"><span data-stu-id="8d72b-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="8d72b-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="8d72b-112">ModelUniqueId</span></span>|<span data-ttu-id="8d72b-113">query</span><span class="sxs-lookup"><span data-stu-id="8d72b-113">query</span></span>|<span data-ttu-id="8d72b-114">はい</span><span class="sxs-lookup"><span data-stu-id="8d72b-114">True</span></span>|<span data-ttu-id="8d72b-115">GUID</span><span class="sxs-lookup"><span data-stu-id="8d72b-115">GUID</span></span>|<span data-ttu-id="8d72b-116">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="8d72b-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="8d72b-117">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8d72b-117">Request headers</span></span>

| <span data-ttu-id="8d72b-118">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8d72b-118">Header</span></span> | <span data-ttu-id="8d72b-119">値</span><span class="sxs-lookup"><span data-stu-id="8d72b-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="8d72b-120">Accept</span><span class="sxs-lookup"><span data-stu-id="8d72b-120">Accept</span></span>|<span data-ttu-id="8d72b-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="8d72b-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="8d72b-122">要求本文</span><span class="sxs-lookup"><span data-stu-id="8d72b-122">Request body</span></span>

| <span data-ttu-id="8d72b-123">名前</span><span class="sxs-lookup"><span data-stu-id="8d72b-123">Name</span></span> | <span data-ttu-id="8d72b-124">必須</span><span class="sxs-lookup"><span data-stu-id="8d72b-124">Required</span></span> | <span data-ttu-id="8d72b-125">型</span><span class="sxs-lookup"><span data-stu-id="8d72b-125">Type</span></span> | <span data-ttu-id="8d72b-126">説明</span><span class="sxs-lookup"><span data-stu-id="8d72b-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="8d72b-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="8d72b-127">ModelUniqueId</span></span>|<span data-ttu-id="8d72b-128">○</span><span class="sxs-lookup"><span data-stu-id="8d72b-128">yes</span></span>|<span data-ttu-id="8d72b-129">文字列</span><span class="sxs-lookup"><span data-stu-id="8d72b-129">string</span></span>|<span data-ttu-id="8d72b-130">モデル ファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="8d72b-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="8d72b-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="8d72b-131">TargetSiteUrl</span></span>|<span data-ttu-id="8d72b-132">○</span><span class="sxs-lookup"><span data-stu-id="8d72b-132">yes</span></span>|<span data-ttu-id="8d72b-133">文字列</span><span class="sxs-lookup"><span data-stu-id="8d72b-133">string</span></span>|<span data-ttu-id="8d72b-134">ターゲット ライブラリ サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="8d72b-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="8d72b-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="8d72b-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="8d72b-136">○</span><span class="sxs-lookup"><span data-stu-id="8d72b-136">yes</span></span>|<span data-ttu-id="8d72b-137">文字列</span><span class="sxs-lookup"><span data-stu-id="8d72b-137">string</span></span>|<span data-ttu-id="8d72b-138">ターゲット ライブラリの Web のサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="8d72b-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="8d72b-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="8d72b-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="8d72b-140">○</span><span class="sxs-lookup"><span data-stu-id="8d72b-140">yes</span></span>|<span data-ttu-id="8d72b-141">文字列</span><span class="sxs-lookup"><span data-stu-id="8d72b-141">string</span></span>|<span data-ttu-id="8d72b-142">ターゲット ライブラリのサーバー相対 URL。</span><span class="sxs-lookup"><span data-stu-id="8d72b-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="8d72b-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="8d72b-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="8d72b-144">○</span><span class="sxs-lookup"><span data-stu-id="8d72b-144">yes</span></span>|<span data-ttu-id="8d72b-145">int</span><span class="sxs-lookup"><span data-stu-id="8d72b-145">int</span></span>|<span data-ttu-id="8d72b-146">ターゲット ライブラリが削除されたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="8d72b-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="8d72b-147">応答</span><span class="sxs-lookup"><span data-stu-id="8d72b-147">Response</span></span>

| <span data-ttu-id="8d72b-148">名前</span><span class="sxs-lookup"><span data-stu-id="8d72b-148">Name</span></span>   | <span data-ttu-id="8d72b-149">型</span><span class="sxs-lookup"><span data-stu-id="8d72b-149">Type</span></span>  | <span data-ttu-id="8d72b-150">説明</span><span class="sxs-lookup"><span data-stu-id="8d72b-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8d72b-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="8d72b-151">200 OK</span></span>| |<span data-ttu-id="8d72b-152">成功</span><span class="sxs-lookup"><span data-stu-id="8d72b-152">Success</span></span>|
|<span data-ttu-id="8d72b-153">201 Created</span><span class="sxs-lookup"><span data-stu-id="8d72b-153">201 Created</span></span>| |<span data-ttu-id="8d72b-154">この API では複数のライブラリへのモデルの適用がサポートされているため、いずれかのライブラリにモデルを適用する際にエラーが発生した場合でも、201 が返される可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8d72b-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="8d72b-155">応答本文を調べて、モデルが指定されたすべてのライブラリに正常に適用されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d72b-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="8d72b-156">詳細については [要求本文](rest-getmodelandlibraryinfo.md#request-body) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d72b-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="8d72b-157">例</span><span class="sxs-lookup"><span data-stu-id="8d72b-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="8d72b-158">リポジトリ サイトの契約モデルと主要ドキュメント ライブラリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="8d72b-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="8d72b-159">このサンプルでは、Contoso 契約書文書理解モデルの ID は `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`です。</span><span class="sxs-lookup"><span data-stu-id="8d72b-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="8d72b-160">要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="8d72b-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="8d72b-161">応答のサンプル</span><span class="sxs-lookup"><span data-stu-id="8d72b-161">Sample response</span></span>

<span data-ttu-id="8d72b-162">**Status code:** 200</span><span class="sxs-lookup"><span data-stu-id="8d72b-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="8d72b-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d72b-163">See also</span></span>

[<span data-ttu-id="8d72b-164">Syntex 文書理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="8d72b-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
