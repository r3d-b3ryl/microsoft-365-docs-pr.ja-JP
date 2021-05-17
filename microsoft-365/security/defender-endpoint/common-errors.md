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
ms.technology: mde
ms.openlocfilehash: 54ae77c28523d3be6092e1567424d2d87a5f2927
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934791"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="8feba-104">一般的な REST API エラー コード</span><span class="sxs-lookup"><span data-stu-id="8feba-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="8feba-105">次の表に示すエラー コードは、Microsoft Defender for Endpoint API の操作によって返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8feba-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="8feba-106">エラー コードに加えて、すべてのエラー応答にエラー メッセージが含まれているので、問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8feba-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="8feba-107">メッセージは、変更できるフリー テキストです。</span><span class="sxs-lookup"><span data-stu-id="8feba-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="8feba-108">ページの下部には、応答の例があります。</span><span class="sxs-lookup"><span data-stu-id="8feba-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="8feba-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8feba-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8feba-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8feba-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8feba-111">エラー コード</span><span class="sxs-lookup"><span data-stu-id="8feba-111">Error code</span></span> |<span data-ttu-id="8feba-112">HTTP ステータス コード</span><span class="sxs-lookup"><span data-stu-id="8feba-112">HTTP status code</span></span> |<span data-ttu-id="8feba-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="8feba-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="8feba-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="8feba-114">BadRequest</span></span> | <span data-ttu-id="8feba-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-115">BadRequest (400)</span></span> | <span data-ttu-id="8feba-116">一般的な不良要求エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="8feba-116">General Bad Request error message.</span></span>
<span data-ttu-id="8feba-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="8feba-117">ODataError</span></span> | <span data-ttu-id="8feba-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-118">BadRequest (400)</span></span> | <span data-ttu-id="8feba-119">無効な OData URI クエリ (特定のエラーが指定されています)。</span><span class="sxs-lookup"><span data-stu-id="8feba-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="8feba-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="8feba-120">InvalidInput</span></span> | <span data-ttu-id="8feba-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-121">BadRequest (400)</span></span> | <span data-ttu-id="8feba-122">無効な入力 {無効な入力}</span><span class="sxs-lookup"><span data-stu-id="8feba-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="8feba-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="8feba-123">InvalidRequestBody</span></span> | <span data-ttu-id="8feba-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-124">BadRequest (400)</span></span> | <span data-ttu-id="8feba-125">要求本文が無効です。</span><span class="sxs-lookup"><span data-stu-id="8feba-125">Invalid request body.</span></span>
<span data-ttu-id="8feba-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="8feba-126">InvalidHashValue</span></span> | <span data-ttu-id="8feba-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-127">BadRequest (400)</span></span> | <span data-ttu-id="8feba-128">ハッシュ値 {無効なハッシュ} が無効です。</span><span class="sxs-lookup"><span data-stu-id="8feba-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="8feba-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="8feba-129">InvalidDomainName</span></span> | <span data-ttu-id="8feba-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-130">BadRequest (400)</span></span> | <span data-ttu-id="8feba-131">ドメイン名 {無効なドメイン} が無効です。</span><span class="sxs-lookup"><span data-stu-id="8feba-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="8feba-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="8feba-132">InvalidIpAddress</span></span> | <span data-ttu-id="8feba-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-133">BadRequest (400)</span></span> | <span data-ttu-id="8feba-134">IP アドレス {無効な IP} が無効です。</span><span class="sxs-lookup"><span data-stu-id="8feba-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="8feba-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="8feba-135">InvalidUrl</span></span> | <span data-ttu-id="8feba-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-136">BadRequest (400)</span></span> | <span data-ttu-id="8feba-137">URL {無効な URL} が無効です。</span><span class="sxs-lookup"><span data-stu-id="8feba-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="8feba-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="8feba-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="8feba-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-139">BadRequest (400)</span></span> | <span data-ttu-id="8feba-140">最大バッチ サイズを超えました。</span><span class="sxs-lookup"><span data-stu-id="8feba-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="8feba-141">Received: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="8feba-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="8feba-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="8feba-142">MissingRequiredParameter</span></span> | <span data-ttu-id="8feba-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-143">BadRequest (400)</span></span> | <span data-ttu-id="8feba-144">パラメーター {不足しているパラメーター} がありません。</span><span class="sxs-lookup"><span data-stu-id="8feba-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="8feba-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="8feba-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="8feba-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-146">BadRequest (400)</span></span> | <span data-ttu-id="8feba-147">OS プラットフォーム {クライアント OS プラットフォーム} は、このアクションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8feba-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="8feba-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="8feba-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="8feba-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8feba-149">BadRequest (400)</span></span> | <span data-ttu-id="8feba-150">{要求されたアクション} は、クライアント バージョン {サポートされているクライアント バージョン} 以上でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8feba-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="8feba-151">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="8feba-151">Unauthorized</span></span> | <span data-ttu-id="8feba-152">承認されていない (401)</span><span class="sxs-lookup"><span data-stu-id="8feba-152">Unauthorized (401)</span></span> | <span data-ttu-id="8feba-153">承認されていない (無効または期限切れの承認ヘッダー)。</span><span class="sxs-lookup"><span data-stu-id="8feba-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="8feba-154">禁止されています</span><span class="sxs-lookup"><span data-stu-id="8feba-154">Forbidden</span></span> | <span data-ttu-id="8feba-155">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="8feba-155">Forbidden (403)</span></span> | <span data-ttu-id="8feba-156">禁止 (有効なトークンですが、アクションに対するアクセス許可が不十分)。</span><span class="sxs-lookup"><span data-stu-id="8feba-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="8feba-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="8feba-157">DisabledFeature</span></span> | <span data-ttu-id="8feba-158">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="8feba-158">Forbidden (403)</span></span> | <span data-ttu-id="8feba-159">テナント機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="8feba-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="8feba-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="8feba-160">DisallowedOperation</span></span> | <span data-ttu-id="8feba-161">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="8feba-161">Forbidden (403)</span></span> | <span data-ttu-id="8feba-162">{禁止された操作と理由}。</span><span class="sxs-lookup"><span data-stu-id="8feba-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="8feba-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="8feba-163">NotFound</span></span> | <span data-ttu-id="8feba-164">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="8feba-164">Not Found (404)</span></span> | <span data-ttu-id="8feba-165">一般的なエラー メッセージが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="8feba-165">General Not Found error message.</span></span>
<span data-ttu-id="8feba-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="8feba-166">ResourceNotFound</span></span> | <span data-ttu-id="8feba-167">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="8feba-167">Not Found (404)</span></span> | <span data-ttu-id="8feba-168">リソース {要求されたリソース} が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8feba-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="8feba-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="8feba-169">InternalServerError</span></span> | <span data-ttu-id="8feba-170">内部サーバー エラー (500)</span><span class="sxs-lookup"><span data-stu-id="8feba-170">Internal Server Error (500)</span></span> | <span data-ttu-id="8feba-171">(エラー メッセージなし、操作を再試行)</span><span class="sxs-lookup"><span data-stu-id="8feba-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="8feba-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="8feba-172">TooManyRequests</span></span> | <span data-ttu-id="8feba-173">要求が多すぎます (429)</span><span class="sxs-lookup"><span data-stu-id="8feba-173">Too Many Requests (429)</span></span> | <span data-ttu-id="8feba-174">応答は、要求数または CPU のいずれかによって、クォータ制限に達する値を表します。</span><span class="sxs-lookup"><span data-stu-id="8feba-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="8feba-175">本文パラメーターでは大文字と小文字が区別されます</span><span class="sxs-lookup"><span data-stu-id="8feba-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="8feba-176">送信された本文パラメーターでは、現在大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="8feba-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="8feba-177">**InvalidRequestBody** エラーまたは **MissingRequiredParameter** エラーが発生した場合、誤ったパラメーター大文字または小文字が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8feba-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="8feba-178">[API ドキュメント] ページを確認し、送信されたパラメーターが関連する例と一致する点を確認します。</span><span class="sxs-lookup"><span data-stu-id="8feba-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="8feba-179">相関要求 ID</span><span class="sxs-lookup"><span data-stu-id="8feba-179">Correlation request ID</span></span>

<span data-ttu-id="8feba-180">各エラー応答には、追跡用の一意の ID パラメーターが含まれる。</span><span class="sxs-lookup"><span data-stu-id="8feba-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="8feba-181">このパラメーターのプロパティ名は "target" です。</span><span class="sxs-lookup"><span data-stu-id="8feba-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="8feba-182">エラーについてお問い合わせの際に、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8feba-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="8feba-183">例</span><span class="sxs-lookup"><span data-stu-id="8feba-183">Examples</span></span>

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
