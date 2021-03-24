---
title: Microsoft Defender ATP API の一般的なエラー
description: 説明付き Microsoft Defender ATP API の一般的なエラーの一覧。
keywords: apis、mdatp api、エラー、トラブルシューティング
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
ms.openlocfilehash: ddbbe07bc477ae3a5016feb795b5bad5ed82a30a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064379"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="d354f-104">一般的な REST API エラー コード</span><span class="sxs-lookup"><span data-stu-id="d354f-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="d354f-105">次の表に示すエラー コードは、Microsoft Defender for Endpoint API の操作によって返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d354f-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="d354f-106">エラー コードに加えて、すべてのエラー応答にエラー メッセージが含まれているので、問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d354f-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="d354f-107">メッセージは、変更できるフリー テキストです。</span><span class="sxs-lookup"><span data-stu-id="d354f-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="d354f-108">ページの下部には、応答の例があります。</span><span class="sxs-lookup"><span data-stu-id="d354f-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="d354f-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d354f-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d354f-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d354f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d354f-111">エラー コード</span><span class="sxs-lookup"><span data-stu-id="d354f-111">Error code</span></span> |<span data-ttu-id="d354f-112">HTTP ステータス コード</span><span class="sxs-lookup"><span data-stu-id="d354f-112">HTTP status code</span></span> |<span data-ttu-id="d354f-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d354f-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="d354f-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="d354f-114">BadRequest</span></span> | <span data-ttu-id="d354f-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-115">BadRequest (400)</span></span> | <span data-ttu-id="d354f-116">一般的な不良要求エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d354f-116">General Bad Request error message.</span></span>
<span data-ttu-id="d354f-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="d354f-117">ODataError</span></span> | <span data-ttu-id="d354f-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-118">BadRequest (400)</span></span> | <span data-ttu-id="d354f-119">無効な OData URI クエリ (特定のエラーが指定されています)。</span><span class="sxs-lookup"><span data-stu-id="d354f-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="d354f-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="d354f-120">InvalidInput</span></span> | <span data-ttu-id="d354f-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-121">BadRequest (400)</span></span> | <span data-ttu-id="d354f-122">無効な入力 {無効な入力}</span><span class="sxs-lookup"><span data-stu-id="d354f-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="d354f-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="d354f-123">InvalidRequestBody</span></span> | <span data-ttu-id="d354f-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-124">BadRequest (400)</span></span> | <span data-ttu-id="d354f-125">要求本文が無効です。</span><span class="sxs-lookup"><span data-stu-id="d354f-125">Invalid request body.</span></span>
<span data-ttu-id="d354f-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="d354f-126">InvalidHashValue</span></span> | <span data-ttu-id="d354f-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-127">BadRequest (400)</span></span> | <span data-ttu-id="d354f-128">ハッシュ値 {無効なハッシュ} が無効です。</span><span class="sxs-lookup"><span data-stu-id="d354f-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="d354f-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="d354f-129">InvalidDomainName</span></span> | <span data-ttu-id="d354f-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-130">BadRequest (400)</span></span> | <span data-ttu-id="d354f-131">ドメイン名 {無効なドメイン} が無効です。</span><span class="sxs-lookup"><span data-stu-id="d354f-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="d354f-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="d354f-132">InvalidIpAddress</span></span> | <span data-ttu-id="d354f-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-133">BadRequest (400)</span></span> | <span data-ttu-id="d354f-134">IP アドレス {無効な IP} が無効です。</span><span class="sxs-lookup"><span data-stu-id="d354f-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="d354f-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="d354f-135">InvalidUrl</span></span> | <span data-ttu-id="d354f-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-136">BadRequest (400)</span></span> | <span data-ttu-id="d354f-137">URL {無効な URL} が無効です。</span><span class="sxs-lookup"><span data-stu-id="d354f-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="d354f-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="d354f-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="d354f-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-139">BadRequest (400)</span></span> | <span data-ttu-id="d354f-140">最大バッチ サイズを超えました。</span><span class="sxs-lookup"><span data-stu-id="d354f-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="d354f-141">Received: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="d354f-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="d354f-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="d354f-142">MissingRequiredParameter</span></span> | <span data-ttu-id="d354f-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-143">BadRequest (400)</span></span> | <span data-ttu-id="d354f-144">パラメーター {不足しているパラメーター} がありません。</span><span class="sxs-lookup"><span data-stu-id="d354f-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="d354f-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="d354f-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="d354f-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-146">BadRequest (400)</span></span> | <span data-ttu-id="d354f-147">OS プラットフォーム {クライアント OS プラットフォーム} は、このアクションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d354f-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="d354f-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="d354f-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="d354f-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d354f-149">BadRequest (400)</span></span> | <span data-ttu-id="d354f-150">{要求されたアクション} は、クライアント バージョン {サポートされているクライアント バージョン} 以上でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d354f-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="d354f-151">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="d354f-151">Unauthorized</span></span> | <span data-ttu-id="d354f-152">承認されていない (401)</span><span class="sxs-lookup"><span data-stu-id="d354f-152">Unauthorized (401)</span></span> | <span data-ttu-id="d354f-153">承認されていない (無効または期限切れの承認ヘッダー)。</span><span class="sxs-lookup"><span data-stu-id="d354f-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="d354f-154">禁止されています</span><span class="sxs-lookup"><span data-stu-id="d354f-154">Forbidden</span></span> | <span data-ttu-id="d354f-155">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="d354f-155">Forbidden (403)</span></span> | <span data-ttu-id="d354f-156">禁止 (有効なトークンですが、アクションに対するアクセス許可が不十分)。</span><span class="sxs-lookup"><span data-stu-id="d354f-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="d354f-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="d354f-157">DisabledFeature</span></span> | <span data-ttu-id="d354f-158">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="d354f-158">Forbidden (403)</span></span> | <span data-ttu-id="d354f-159">テナント機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="d354f-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="d354f-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="d354f-160">DisallowedOperation</span></span> | <span data-ttu-id="d354f-161">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="d354f-161">Forbidden (403)</span></span> | <span data-ttu-id="d354f-162">{禁止された操作と理由}。</span><span class="sxs-lookup"><span data-stu-id="d354f-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="d354f-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="d354f-163">NotFound</span></span> | <span data-ttu-id="d354f-164">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="d354f-164">Not Found (404)</span></span> | <span data-ttu-id="d354f-165">一般的なエラー メッセージが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="d354f-165">General Not Found error message.</span></span>
<span data-ttu-id="d354f-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="d354f-166">ResourceNotFound</span></span> | <span data-ttu-id="d354f-167">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="d354f-167">Not Found (404)</span></span> | <span data-ttu-id="d354f-168">リソース {要求されたリソース} が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="d354f-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="d354f-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="d354f-169">InternalServerError</span></span> | <span data-ttu-id="d354f-170">内部サーバー エラー (500)</span><span class="sxs-lookup"><span data-stu-id="d354f-170">Internal Server Error (500)</span></span> | <span data-ttu-id="d354f-171">(エラー メッセージなし、操作を再試行)</span><span class="sxs-lookup"><span data-stu-id="d354f-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="d354f-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="d354f-172">TooManyRequests</span></span> | <span data-ttu-id="d354f-173">要求が多すぎます (429)</span><span class="sxs-lookup"><span data-stu-id="d354f-173">Too Many Requests (429)</span></span> | <span data-ttu-id="d354f-174">応答は、要求数または CPU のいずれかによって、クォータ制限に達する値を表します。</span><span class="sxs-lookup"><span data-stu-id="d354f-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="d354f-175">本文パラメーターでは大文字と小文字が区別されます</span><span class="sxs-lookup"><span data-stu-id="d354f-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="d354f-176">送信された本文パラメーターでは、現在大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="d354f-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="d354f-177">**InvalidRequestBody** エラーまたは **MissingRequiredParameter** エラーが発生した場合、誤ったパラメーター大文字または小文字が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d354f-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="d354f-178">[API ドキュメント] ページを確認し、送信されたパラメーターが関連する例と一致する点を確認します。</span><span class="sxs-lookup"><span data-stu-id="d354f-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="d354f-179">相関要求 ID</span><span class="sxs-lookup"><span data-stu-id="d354f-179">Correlation request ID</span></span>

<span data-ttu-id="d354f-180">各エラー応答には、追跡用の一意の ID パラメーターが含まれる。</span><span class="sxs-lookup"><span data-stu-id="d354f-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="d354f-181">このパラメーターのプロパティ名は "target" です。</span><span class="sxs-lookup"><span data-stu-id="d354f-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="d354f-182">エラーについてお問い合わせの際に、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d354f-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="d354f-183">例</span><span class="sxs-lookup"><span data-stu-id="d354f-183">Examples</span></span>

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
