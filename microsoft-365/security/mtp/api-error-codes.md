---
title: Microsoft 365 Defender REST API の一般的なエラー コード
description: Microsoft 365 Defender REST API の一般的なエラー コードについて説明します。
keywords: api, エラー, コード, 一般的なエラー, mtp, api エラー コード
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719216"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="5b987-104">Microsoft 365 Defender REST API の一般的なエラー コード</span><span class="sxs-lookup"><span data-stu-id="5b987-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5b987-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5b987-105">**Applies to:**</span></span>

- <span data-ttu-id="5b987-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5b987-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b987-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="5b987-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5b987-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="5b987-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5b987-109">エラー コードは、Microsoft 365 Defender API の操作によって返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b987-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="5b987-110">すべてのエラー応答にはエラー メッセージが含まれるので、問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5b987-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="5b987-111">表セクションのエラー メッセージ列には、いくつかのサンプル メッセージが示されています。</span><span class="sxs-lookup"><span data-stu-id="5b987-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="5b987-112">実際のメッセージの内容は、応答をトリガーした要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5b987-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="5b987-113">可変コンテンツは、テーブル内で角かっこで示されています。</span><span class="sxs-lookup"><span data-stu-id="5b987-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="5b987-114">エラー コード</span><span class="sxs-lookup"><span data-stu-id="5b987-114">Error codes</span></span>

<span data-ttu-id="5b987-115">エラー コード</span><span class="sxs-lookup"><span data-stu-id="5b987-115">Error code</span></span> | <span data-ttu-id="5b987-116">HTTP ステータス コード</span><span class="sxs-lookup"><span data-stu-id="5b987-116">HTTP status code</span></span> | <span data-ttu-id="5b987-117">メッセージ</span><span class="sxs-lookup"><span data-stu-id="5b987-117">Message</span></span>
-|-|-
<span data-ttu-id="5b987-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="5b987-118">BadRequest</span></span> | <span data-ttu-id="5b987-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-119">BadRequest (400)</span></span> | <span data-ttu-id="5b987-120">General Bad Request エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5b987-120">General Bad Request error message.</span></span>
<span data-ttu-id="5b987-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="5b987-121">ODataError</span></span> | <span data-ttu-id="5b987-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-122">BadRequest (400)</span></span> | <span data-ttu-id="5b987-123">無効な OData URI クエリ \<the specific error is specified\> です。</span><span class="sxs-lookup"><span data-stu-id="5b987-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="5b987-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="5b987-124">InvalidInput</span></span> | <span data-ttu-id="5b987-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-125">BadRequest (400)</span></span> | <span data-ttu-id="5b987-126">無効な入力 \<the invalid input\> です。</span><span class="sxs-lookup"><span data-stu-id="5b987-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="5b987-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="5b987-127">InvalidRequestBody</span></span> | <span data-ttu-id="5b987-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-128">BadRequest (400)</span></span> | <span data-ttu-id="5b987-129">要求本文が無効です。</span><span class="sxs-lookup"><span data-stu-id="5b987-129">Invalid request body.</span></span>
<span data-ttu-id="5b987-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="5b987-130">InvalidHashValue</span></span> | <span data-ttu-id="5b987-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-131">BadRequest (400)</span></span> | <span data-ttu-id="5b987-132">ハッシュ値 \<the invalid hash\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="5b987-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="5b987-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="5b987-133">InvalidDomainName</span></span> | <span data-ttu-id="5b987-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-134">BadRequest (400)</span></span> | <span data-ttu-id="5b987-135">ドメイン名 \<the invalid domain\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="5b987-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="5b987-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="5b987-136">InvalidIpAddress</span></span> | <span data-ttu-id="5b987-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-137">BadRequest (400)</span></span> | <span data-ttu-id="5b987-138">IP アドレス \<the invalid IP\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="5b987-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="5b987-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="5b987-139">InvalidUrl</span></span> | <span data-ttu-id="5b987-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-140">BadRequest (400)</span></span> | <span data-ttu-id="5b987-141">URL \<the invalid URL\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="5b987-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="5b987-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="5b987-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="5b987-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-143">BadRequest (400)</span></span> | <span data-ttu-id="5b987-144">最大バッチ サイズを超えました。</span><span class="sxs-lookup"><span data-stu-id="5b987-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="5b987-145">Received: \<batch size received\> , allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="5b987-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="5b987-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="5b987-146">MissingRequiredParameter</span></span> | <span data-ttu-id="5b987-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-147">BadRequest (400)</span></span> | <span data-ttu-id="5b987-148">パラメーター \<the missing parameter\> がありません。</span><span class="sxs-lookup"><span data-stu-id="5b987-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="5b987-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="5b987-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="5b987-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-150">BadRequest (400)</span></span> | <span data-ttu-id="5b987-151">このアクション \<the client OS Platform\> では、OS プラットフォームはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5b987-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="5b987-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="5b987-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="5b987-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5b987-153">BadRequest (400)</span></span> | <span data-ttu-id="5b987-154">\<The requested action\> はクライアント バージョン以上 \<supported client version\> でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5b987-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="5b987-155">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="5b987-155">Unauthorized</span></span> | <span data-ttu-id="5b987-156">Unauthorized (401)</span><span class="sxs-lookup"><span data-stu-id="5b987-156">Unauthorized (401)</span></span> | <span data-ttu-id="5b987-157">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="5b987-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="5b987-158">*注: 通常、無効または期限切れの承認ヘッダーが原因です。*</span><span class="sxs-lookup"><span data-stu-id="5b987-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="5b987-159">禁止されています</span><span class="sxs-lookup"><span data-stu-id="5b987-159">Forbidden</span></span> | <span data-ttu-id="5b987-160">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="5b987-160">Forbidden (403)</span></span> | <span data-ttu-id="5b987-161">禁止されています</span><span class="sxs-lookup"><span data-stu-id="5b987-161">Forbidden</span></span> <br /><br /><span data-ttu-id="5b987-162">*注: 有効なトークンですが、アクションのアクセス許可が不十分です*。</span><span class="sxs-lookup"><span data-stu-id="5b987-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="5b987-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="5b987-163">DisabledFeature</span></span> | <span data-ttu-id="5b987-164">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="5b987-164">Forbidden (403)</span></span> | <span data-ttu-id="5b987-165">テナント機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="5b987-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="5b987-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="5b987-166">DisallowedOperation</span></span> | <span data-ttu-id="5b987-167">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="5b987-167">Forbidden (403)</span></span> | <span data-ttu-id="5b987-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="5b987-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="5b987-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="5b987-169">NotFound</span></span> | <span data-ttu-id="5b987-170">Not Found (404)</span><span class="sxs-lookup"><span data-stu-id="5b987-170">Not Found (404)</span></span> | <span data-ttu-id="5b987-171">General Not Found エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5b987-171">General Not Found error message.</span></span>
<span data-ttu-id="5b987-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="5b987-172">ResourceNotFound</span></span> | <span data-ttu-id="5b987-173">Not Found (404)</span><span class="sxs-lookup"><span data-stu-id="5b987-173">Not Found (404)</span></span> | <span data-ttu-id="5b987-174">リソース \<the requested resource\> が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="5b987-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="5b987-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="5b987-175">InternalServerError</span></span> | <span data-ttu-id="5b987-176">内部サーバー エラー (500)</span><span class="sxs-lookup"><span data-stu-id="5b987-176">Internal Server Error (500)</span></span> | <span data-ttu-id="5b987-177">*注: エラー メッセージが表示されない場合は、操作を再試行するか、解決されない場合は Microsoft にお問い合わせください。*</span><span class="sxs-lookup"><span data-stu-id="5b987-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="5b987-178">例</span><span class="sxs-lookup"><span data-stu-id="5b987-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="5b987-179">本文パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b987-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b987-180">本文パラメーターでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5b987-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="5b987-181">*InvalidRequestBody エラー* または *MissingRequiredParameter* エラーが発生した場合は、入力ミスが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5b987-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="5b987-182">API ドキュメントを確認し、送信されたパラメーターが関連する例と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b987-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="5b987-183">追跡 ID</span><span class="sxs-lookup"><span data-stu-id="5b987-183">Tracking ID</span></span>

<span data-ttu-id="5b987-184">各エラー応答には、追跡用の一意の ID パラメーターが含まれる。</span><span class="sxs-lookup"><span data-stu-id="5b987-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="5b987-185">このパラメーターのプロパティ名は target *です*。</span><span class="sxs-lookup"><span data-stu-id="5b987-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="5b987-186">エラーについてお問い合わせの場合、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5b987-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5b987-187">関連記事</span><span class="sxs-lookup"><span data-stu-id="5b987-187">Related articles</span></span>

- [<span data-ttu-id="5b987-188">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="5b987-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="5b987-189">サポートされている Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="5b987-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="5b987-190">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="5b987-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="5b987-191">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="5b987-191">Learn about API limits and licensing</span></span>](api-terms.md)
