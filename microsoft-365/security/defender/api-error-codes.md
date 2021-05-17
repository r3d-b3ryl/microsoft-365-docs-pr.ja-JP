---
title: Defender REST API Microsoft 365コードの一般的な説明
description: Defender REST API エラー コードMicrosoft 365一般的な方法について説明します。
keywords: api、 error, codes, common error, Microsoft 365 Defender, API エラー コード
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932883"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="8e7a6-104">Defender REST API Microsoft 365コードの一般的な説明</span><span class="sxs-lookup"><span data-stu-id="8e7a6-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8e7a6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8e7a6-105">**Applies to:**</span></span>

- <span data-ttu-id="8e7a6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e7a6-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e7a6-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8e7a6-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8e7a6-109">エラー コードは、任意の Defender API 上の操作Microsoft 365返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="8e7a6-110">すべてのエラー応答にエラー メッセージが含まれるので、問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="8e7a6-111">テーブル セクションのエラー メッセージ列には、いくつかのサンプル メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="8e7a6-112">実際のメッセージの内容は、応答をトリガーした要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="8e7a6-113">変数の内容は、表に角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="8e7a6-114">エラー コード</span><span class="sxs-lookup"><span data-stu-id="8e7a6-114">Error codes</span></span>

<span data-ttu-id="8e7a6-115">エラー コード</span><span class="sxs-lookup"><span data-stu-id="8e7a6-115">Error code</span></span> | <span data-ttu-id="8e7a6-116">HTTP ステータス コード</span><span class="sxs-lookup"><span data-stu-id="8e7a6-116">HTTP status code</span></span> | <span data-ttu-id="8e7a6-117">メッセージ</span><span class="sxs-lookup"><span data-stu-id="8e7a6-117">Message</span></span>
-|-|-
<span data-ttu-id="8e7a6-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="8e7a6-118">BadRequest</span></span> | <span data-ttu-id="8e7a6-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-119">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-120">一般的な不良要求エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-120">General Bad Request error message.</span></span>
<span data-ttu-id="8e7a6-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="8e7a6-121">ODataError</span></span> | <span data-ttu-id="8e7a6-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-122">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-123">OData URI クエリが無効です \<the specific error is specified\> 。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="8e7a6-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="8e7a6-124">InvalidInput</span></span> | <span data-ttu-id="8e7a6-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-125">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-126">入力が無効です \<the invalid input\> 。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="8e7a6-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="8e7a6-127">InvalidRequestBody</span></span> | <span data-ttu-id="8e7a6-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-128">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-129">要求本文が無効です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-129">Invalid request body.</span></span>
<span data-ttu-id="8e7a6-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="8e7a6-130">InvalidHashValue</span></span> | <span data-ttu-id="8e7a6-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-131">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-132">ハッシュ値 \<the invalid hash\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="8e7a6-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="8e7a6-133">InvalidDomainName</span></span> | <span data-ttu-id="8e7a6-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-134">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-135">ドメイン名 \<the invalid domain\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="8e7a6-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="8e7a6-136">InvalidIpAddress</span></span> | <span data-ttu-id="8e7a6-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-137">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-138">IP アドレス \<the invalid IP\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="8e7a6-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="8e7a6-139">InvalidUrl</span></span> | <span data-ttu-id="8e7a6-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-140">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-141">URL \<the invalid URL\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="8e7a6-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="8e7a6-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="8e7a6-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-143">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-144">最大バッチ サイズを超えました。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="8e7a6-145">受信: \<batch size received\> 、許可: {batch size allowed}。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="8e7a6-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="8e7a6-146">MissingRequiredParameter</span></span> | <span data-ttu-id="8e7a6-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-147">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-148">パラメーター \<the missing parameter\> がありません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="8e7a6-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="8e7a6-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="8e7a6-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-150">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-151">OS プラットフォーム \<the client OS Platform\> は、このアクションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="8e7a6-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="8e7a6-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="8e7a6-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-153">BadRequest (400)</span></span> | <span data-ttu-id="8e7a6-154">\<The requested action\> はクライアント バージョン以上 \<supported client version\> でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="8e7a6-155">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-155">Unauthorized</span></span> | <span data-ttu-id="8e7a6-156">承認されていない (401)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-156">Unauthorized (401)</span></span> | <span data-ttu-id="8e7a6-157">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="8e7a6-158">*注: 通常、無効または期限切れの承認ヘッダーが原因です。*</span><span class="sxs-lookup"><span data-stu-id="8e7a6-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="8e7a6-159">禁止されています</span><span class="sxs-lookup"><span data-stu-id="8e7a6-159">Forbidden</span></span> | <span data-ttu-id="8e7a6-160">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-160">Forbidden (403)</span></span> | <span data-ttu-id="8e7a6-161">禁止されています</span><span class="sxs-lookup"><span data-stu-id="8e7a6-161">Forbidden</span></span> <br /><br /><span data-ttu-id="8e7a6-162">*注: 有効なトークンですが、アクションに対するアクセス許可が不十分です*。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="8e7a6-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="8e7a6-163">DisabledFeature</span></span> | <span data-ttu-id="8e7a6-164">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-164">Forbidden (403)</span></span> | <span data-ttu-id="8e7a6-165">テナント機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="8e7a6-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="8e7a6-166">DisallowedOperation</span></span> | <span data-ttu-id="8e7a6-167">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-167">Forbidden (403)</span></span> | <span data-ttu-id="8e7a6-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="8e7a6-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="8e7a6-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="8e7a6-169">NotFound</span></span> | <span data-ttu-id="8e7a6-170">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-170">Not Found (404)</span></span> | <span data-ttu-id="8e7a6-171">一般的なエラー メッセージが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-171">General Not Found error message.</span></span>
<span data-ttu-id="8e7a6-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="8e7a6-172">ResourceNotFound</span></span> | <span data-ttu-id="8e7a6-173">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-173">Not Found (404)</span></span> | <span data-ttu-id="8e7a6-174">リソース \<the requested resource\> が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="8e7a6-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="8e7a6-175">InternalServerError</span></span> | <span data-ttu-id="8e7a6-176">内部サーバー エラー (500)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-176">Internal Server Error (500)</span></span> | <span data-ttu-id="8e7a6-177">*注: エラー メッセージが表示されない場合は、操作を再試行するか、解決されない場合は Microsoft にお問い合わせください。*</span><span class="sxs-lookup"><span data-stu-id="8e7a6-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="8e7a6-178">例</span><span class="sxs-lookup"><span data-stu-id="8e7a6-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="8e7a6-179">本文パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e7a6-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e7a6-180">本文パラメーターでは、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="8e7a6-181">*InvalidRequestBody エラーまたは* *MissingRequiredParameter* エラーが発生した場合は、入力ミスが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="8e7a6-182">API のドキュメントを確認し、送信されたパラメーターが関連する例と一致する点を確認します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="8e7a6-183">追跡 ID</span><span class="sxs-lookup"><span data-stu-id="8e7a6-183">Tracking ID</span></span>

<span data-ttu-id="8e7a6-184">各エラー応答には、追跡用の一意の ID パラメーターが含まれる。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="8e7a6-185">このパラメーターのプロパティ名は target *です*。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="8e7a6-186">エラーについてお問い合わせの際に、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8e7a6-187">関連記事</span><span class="sxs-lookup"><span data-stu-id="8e7a6-187">Related articles</span></span>

- [<span data-ttu-id="8e7a6-188">Microsoft 365Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="8e7a6-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="8e7a6-189">サポートされている Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="8e7a6-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="8e7a6-190">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="8e7a6-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8e7a6-191">API の制限とライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="8e7a6-191">Learn about API limits and licensing</span></span>](api-terms.md)
