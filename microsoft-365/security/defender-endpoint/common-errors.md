---
title: エンドポイント API エラーの一般的な Microsoft Defender
description: 説明付きエンドポイント API エラーの一般的な Microsoft Defender の一覧。
keywords: API、Microsoft Defender for Endpoint API、エラー、トラブルシューティング
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771011"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="fa1ac-104">一般的な REST API エラー コード</span><span class="sxs-lookup"><span data-stu-id="fa1ac-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="fa1ac-105">次の表に示すエラー コードは、Microsoft Defender for Endpoint API の操作によって返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="fa1ac-106">エラー コードに加えて、すべてのエラー応答にエラー メッセージが含まれているので、問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="fa1ac-107">メッセージは、変更できるフリー テキストです。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="fa1ac-108">ページの下部には、応答の例があります。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="fa1ac-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fa1ac-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fa1ac-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="fa1ac-111">エラー コード</span><span class="sxs-lookup"><span data-stu-id="fa1ac-111">Error code</span></span> |<span data-ttu-id="fa1ac-112">HTTP ステータス コード</span><span class="sxs-lookup"><span data-stu-id="fa1ac-112">HTTP status code</span></span> |<span data-ttu-id="fa1ac-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="fa1ac-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="fa1ac-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="fa1ac-114">BadRequest</span></span> | <span data-ttu-id="fa1ac-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-115">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-116">一般的な不良要求エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-116">General Bad Request error message.</span></span>
<span data-ttu-id="fa1ac-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="fa1ac-117">ODataError</span></span> | <span data-ttu-id="fa1ac-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-118">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-119">無効な OData URI クエリ (特定のエラーが指定されています)。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="fa1ac-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="fa1ac-120">InvalidInput</span></span> | <span data-ttu-id="fa1ac-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-121">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-122">無効な入力 {無効な入力}</span><span class="sxs-lookup"><span data-stu-id="fa1ac-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="fa1ac-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="fa1ac-123">InvalidRequestBody</span></span> | <span data-ttu-id="fa1ac-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-124">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-125">要求本文が無効です。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-125">Invalid request body.</span></span>
<span data-ttu-id="fa1ac-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="fa1ac-126">InvalidHashValue</span></span> | <span data-ttu-id="fa1ac-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-127">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-128">ハッシュ値 {無効なハッシュ} が無効です。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="fa1ac-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="fa1ac-129">InvalidDomainName</span></span> | <span data-ttu-id="fa1ac-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-130">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-131">ドメイン名 {無効なドメイン} が無効です。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="fa1ac-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="fa1ac-132">InvalidIpAddress</span></span> | <span data-ttu-id="fa1ac-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-133">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-134">IP アドレス {無効な IP} が無効です。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="fa1ac-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="fa1ac-135">InvalidUrl</span></span> | <span data-ttu-id="fa1ac-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-136">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-137">URL {無効な URL} が無効です。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="fa1ac-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="fa1ac-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="fa1ac-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-139">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-140">最大バッチ サイズを超えました。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="fa1ac-141">Received: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="fa1ac-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="fa1ac-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="fa1ac-142">MissingRequiredParameter</span></span> | <span data-ttu-id="fa1ac-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-143">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-144">パラメーター {不足しているパラメーター} がありません。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="fa1ac-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="fa1ac-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="fa1ac-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-146">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-147">OS プラットフォーム {クライアント OS プラットフォーム} は、このアクションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="fa1ac-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="fa1ac-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="fa1ac-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-149">BadRequest (400)</span></span> | <span data-ttu-id="fa1ac-150">{要求されたアクション} は、クライアント バージョン {サポートされているクライアント バージョン} 以上でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="fa1ac-151">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-151">Unauthorized</span></span> | <span data-ttu-id="fa1ac-152">承認されていない (401)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-152">Unauthorized (401)</span></span> | <span data-ttu-id="fa1ac-153">承認されていない (無効または期限切れの承認ヘッダー)。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="fa1ac-154">禁止されています</span><span class="sxs-lookup"><span data-stu-id="fa1ac-154">Forbidden</span></span> | <span data-ttu-id="fa1ac-155">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-155">Forbidden (403)</span></span> | <span data-ttu-id="fa1ac-156">禁止 (有効なトークンですが、アクションに対するアクセス許可が不十分)。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="fa1ac-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="fa1ac-157">DisabledFeature</span></span> | <span data-ttu-id="fa1ac-158">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-158">Forbidden (403)</span></span> | <span data-ttu-id="fa1ac-159">テナント機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="fa1ac-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="fa1ac-160">DisallowedOperation</span></span> | <span data-ttu-id="fa1ac-161">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-161">Forbidden (403)</span></span> | <span data-ttu-id="fa1ac-162">{禁止された操作と理由}。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="fa1ac-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="fa1ac-163">NotFound</span></span> | <span data-ttu-id="fa1ac-164">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-164">Not Found (404)</span></span> | <span data-ttu-id="fa1ac-165">一般的なエラー メッセージが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-165">General Not Found error message.</span></span>
<span data-ttu-id="fa1ac-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="fa1ac-166">ResourceNotFound</span></span> | <span data-ttu-id="fa1ac-167">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-167">Not Found (404)</span></span> | <span data-ttu-id="fa1ac-168">リソース {要求されたリソース} が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="fa1ac-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="fa1ac-169">InternalServerError</span></span> | <span data-ttu-id="fa1ac-170">内部サーバー エラー (500)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-170">Internal Server Error (500)</span></span> | <span data-ttu-id="fa1ac-171">(エラー メッセージなし、操作を再試行)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="fa1ac-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="fa1ac-172">TooManyRequests</span></span> | <span data-ttu-id="fa1ac-173">要求が多すぎます (429)</span><span class="sxs-lookup"><span data-stu-id="fa1ac-173">Too Many Requests (429)</span></span> | <span data-ttu-id="fa1ac-174">応答は、要求数または CPU のいずれかによって、クォータ制限に達する値を表します。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="fa1ac-175">本文パラメーターでは大文字と小文字が区別されます</span><span class="sxs-lookup"><span data-stu-id="fa1ac-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="fa1ac-176">送信された本文パラメーターでは、現在大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="fa1ac-177">**InvalidRequestBody** エラーまたは **MissingRequiredParameter** エラーが発生した場合、誤ったパラメーター大文字または小文字が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="fa1ac-178">[API ドキュメント] ページを確認し、送信されたパラメーターが関連する例と一致する点を確認します。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="fa1ac-179">相関要求 ID</span><span class="sxs-lookup"><span data-stu-id="fa1ac-179">Correlation request ID</span></span>

<span data-ttu-id="fa1ac-180">各エラー応答には、追跡用の一意の ID パラメーターが含まれる。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="fa1ac-181">このパラメーターのプロパティ名は "target" です。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="fa1ac-182">エラーについてお問い合わせの際に、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fa1ac-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="fa1ac-183">例</span><span class="sxs-lookup"><span data-stu-id="fa1ac-183">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```


```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```
