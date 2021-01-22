---
title: Microsoft 365 Defender REST API の一般的なエラー コード
description: Microsoft 365 Defender REST API の一般的なエラー コードについて説明します。
keywords: api, エラー, コード, 一般的なエラー, mtp, api エラー コード
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928392"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="2a110-104">Microsoft 365 Defender REST API の一般的なエラー コード</span><span class="sxs-lookup"><span data-stu-id="2a110-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2a110-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2a110-105">**Applies to:**</span></span>

- <span data-ttu-id="2a110-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2a110-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a110-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="2a110-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2a110-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="2a110-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2a110-109">エラー コードは、Microsoft 365 Defender API の操作によって返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a110-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="2a110-110">すべてのエラー応答にはエラー メッセージが含まれるので、問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2a110-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="2a110-111">表セクションのエラー メッセージ列には、いくつかのサンプル メッセージが示されています。</span><span class="sxs-lookup"><span data-stu-id="2a110-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="2a110-112">実際のメッセージの内容は、応答をトリガーした要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2a110-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="2a110-113">可変コンテンツは、テーブル内で角かっこで示されています。</span><span class="sxs-lookup"><span data-stu-id="2a110-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="2a110-114">エラー コード</span><span class="sxs-lookup"><span data-stu-id="2a110-114">Error codes</span></span>

<span data-ttu-id="2a110-115">エラー コード</span><span class="sxs-lookup"><span data-stu-id="2a110-115">Error code</span></span> | <span data-ttu-id="2a110-116">HTTP ステータス コード</span><span class="sxs-lookup"><span data-stu-id="2a110-116">HTTP status code</span></span> | <span data-ttu-id="2a110-117">メッセージ</span><span class="sxs-lookup"><span data-stu-id="2a110-117">Message</span></span>
-|-|-
<span data-ttu-id="2a110-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="2a110-118">BadRequest</span></span> | <span data-ttu-id="2a110-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-119">BadRequest (400)</span></span> | <span data-ttu-id="2a110-120">General Bad Request エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2a110-120">General Bad Request error message.</span></span>
<span data-ttu-id="2a110-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="2a110-121">ODataError</span></span> | <span data-ttu-id="2a110-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-122">BadRequest (400)</span></span> | <span data-ttu-id="2a110-123">無効な OData URI クエリ \<the specific error is specified\> です。</span><span class="sxs-lookup"><span data-stu-id="2a110-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="2a110-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="2a110-124">InvalidInput</span></span> | <span data-ttu-id="2a110-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-125">BadRequest (400)</span></span> | <span data-ttu-id="2a110-126">無効な入力 \<the invalid input\> です。</span><span class="sxs-lookup"><span data-stu-id="2a110-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="2a110-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="2a110-127">InvalidRequestBody</span></span> | <span data-ttu-id="2a110-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-128">BadRequest (400)</span></span> | <span data-ttu-id="2a110-129">要求本文が無効です。</span><span class="sxs-lookup"><span data-stu-id="2a110-129">Invalid request body.</span></span>
<span data-ttu-id="2a110-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="2a110-130">InvalidHashValue</span></span> | <span data-ttu-id="2a110-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-131">BadRequest (400)</span></span> | <span data-ttu-id="2a110-132">ハッシュ値 \<the invalid hash\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="2a110-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="2a110-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="2a110-133">InvalidDomainName</span></span> | <span data-ttu-id="2a110-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-134">BadRequest (400)</span></span> | <span data-ttu-id="2a110-135">ドメイン名 \<the invalid domain\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="2a110-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="2a110-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="2a110-136">InvalidIpAddress</span></span> | <span data-ttu-id="2a110-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-137">BadRequest (400)</span></span> | <span data-ttu-id="2a110-138">IP アドレス \<the invalid IP\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="2a110-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="2a110-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="2a110-139">InvalidUrl</span></span> | <span data-ttu-id="2a110-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-140">BadRequest (400)</span></span> | <span data-ttu-id="2a110-141">URL \<the invalid URL\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="2a110-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="2a110-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="2a110-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="2a110-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-143">BadRequest (400)</span></span> | <span data-ttu-id="2a110-144">最大バッチ サイズを超えました。</span><span class="sxs-lookup"><span data-stu-id="2a110-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="2a110-145">Received: \<batch size received\> , allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="2a110-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="2a110-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="2a110-146">MissingRequiredParameter</span></span> | <span data-ttu-id="2a110-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-147">BadRequest (400)</span></span> | <span data-ttu-id="2a110-148">パラメーター \<the missing parameter\> がありません。</span><span class="sxs-lookup"><span data-stu-id="2a110-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="2a110-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="2a110-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="2a110-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-150">BadRequest (400)</span></span> | <span data-ttu-id="2a110-151">このアクション \<the client OS Platform\> では、OS プラットフォームはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2a110-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="2a110-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="2a110-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="2a110-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2a110-153">BadRequest (400)</span></span> | <span data-ttu-id="2a110-154">\<The requested action\> はクライアント バージョン以上 \<supported client version\> でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2a110-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="2a110-155">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="2a110-155">Unauthorized</span></span> | <span data-ttu-id="2a110-156">Unauthorized (401)</span><span class="sxs-lookup"><span data-stu-id="2a110-156">Unauthorized (401)</span></span> | <span data-ttu-id="2a110-157">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="2a110-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="2a110-158">*注: 通常、無効または期限切れの承認ヘッダーが原因です。*</span><span class="sxs-lookup"><span data-stu-id="2a110-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="2a110-159">禁止されています</span><span class="sxs-lookup"><span data-stu-id="2a110-159">Forbidden</span></span> | <span data-ttu-id="2a110-160">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="2a110-160">Forbidden (403)</span></span> | <span data-ttu-id="2a110-161">禁止されています</span><span class="sxs-lookup"><span data-stu-id="2a110-161">Forbidden</span></span> <br /><br /><span data-ttu-id="2a110-162">*注: 有効なトークンですが、アクションのアクセス許可が不十分です*。</span><span class="sxs-lookup"><span data-stu-id="2a110-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="2a110-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="2a110-163">DisabledFeature</span></span> | <span data-ttu-id="2a110-164">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="2a110-164">Forbidden (403)</span></span> | <span data-ttu-id="2a110-165">テナント機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2a110-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="2a110-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="2a110-166">DisallowedOperation</span></span> | <span data-ttu-id="2a110-167">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="2a110-167">Forbidden (403)</span></span> | <span data-ttu-id="2a110-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="2a110-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="2a110-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="2a110-169">NotFound</span></span> | <span data-ttu-id="2a110-170">Not Found (404)</span><span class="sxs-lookup"><span data-stu-id="2a110-170">Not Found (404)</span></span> | <span data-ttu-id="2a110-171">General Not Found エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2a110-171">General Not Found error message.</span></span>
<span data-ttu-id="2a110-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="2a110-172">ResourceNotFound</span></span> | <span data-ttu-id="2a110-173">Not Found (404)</span><span class="sxs-lookup"><span data-stu-id="2a110-173">Not Found (404)</span></span> | <span data-ttu-id="2a110-174">リソース \<the requested resource\> が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="2a110-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="2a110-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="2a110-175">InternalServerError</span></span> | <span data-ttu-id="2a110-176">内部サーバー エラー (500)</span><span class="sxs-lookup"><span data-stu-id="2a110-176">Internal Server Error (500)</span></span> | <span data-ttu-id="2a110-177">*注: エラー メッセージが表示されない場合は、操作を再試行するか、解決されない場合は Microsoft にお問い合わせください。*</span><span class="sxs-lookup"><span data-stu-id="2a110-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="2a110-178">例</span><span class="sxs-lookup"><span data-stu-id="2a110-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="2a110-179">本文パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a110-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a110-180">本文パラメーターでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2a110-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="2a110-181">*InvalidRequestBody エラー* または *MissingRequiredParameter* エラーが発生した場合は、入力ミスが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a110-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="2a110-182">API ドキュメントを確認し、送信されたパラメーターが関連する例と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a110-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="2a110-183">追跡 ID</span><span class="sxs-lookup"><span data-stu-id="2a110-183">Tracking ID</span></span>

<span data-ttu-id="2a110-184">各エラー応答には、追跡用の一意の ID パラメーターが含まれている。</span><span class="sxs-lookup"><span data-stu-id="2a110-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="2a110-185">このパラメーターのプロパティ名はターゲット *です*。</span><span class="sxs-lookup"><span data-stu-id="2a110-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="2a110-186">エラーについてお問い合わせの場合、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2a110-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2a110-187">関連記事</span><span class="sxs-lookup"><span data-stu-id="2a110-187">Related articles</span></span>

- [<span data-ttu-id="2a110-188">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="2a110-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2a110-189">サポートされている Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="2a110-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="2a110-190">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="2a110-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2a110-191">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="2a110-191">Learn about API limits and licensing</span></span>](api-terms.md)
