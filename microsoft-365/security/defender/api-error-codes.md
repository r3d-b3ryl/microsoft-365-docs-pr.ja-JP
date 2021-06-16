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
ms.openlocfilehash: de24856e8ea7555a96de18cabca5ccadfe71b431
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930273"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="ec5b5-104">Defender REST API Microsoft 365コードの一般的な説明</span><span class="sxs-lookup"><span data-stu-id="ec5b5-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ec5b5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ec5b5-105">**Applies to:**</span></span>

- <span data-ttu-id="ec5b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec5b5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec5b5-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ec5b5-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ec5b5-109">エラー コードは、任意の Defender API 上の操作Microsoft 365返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="ec5b5-110">すべてのエラー応答にエラー メッセージが含まれるので、問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="ec5b5-111">テーブル セクションのエラー メッセージ列には、いくつかのサンプル メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="ec5b5-112">実際のメッセージの内容は、応答をトリガーした要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="ec5b5-113">変数の内容は、表に角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="ec5b5-114">エラー コード</span><span class="sxs-lookup"><span data-stu-id="ec5b5-114">Error codes</span></span>

<span data-ttu-id="ec5b5-115">エラー コード</span><span class="sxs-lookup"><span data-stu-id="ec5b5-115">Error code</span></span> | <span data-ttu-id="ec5b5-116">HTTP ステータス コード</span><span class="sxs-lookup"><span data-stu-id="ec5b5-116">HTTP status code</span></span> | <span data-ttu-id="ec5b5-117">メッセージ</span><span class="sxs-lookup"><span data-stu-id="ec5b5-117">Message</span></span>
-|-|-
<span data-ttu-id="ec5b5-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="ec5b5-118">BadRequest</span></span> | <span data-ttu-id="ec5b5-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-119">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-120">一般的な不良要求エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-120">General Bad Request error message.</span></span>
<span data-ttu-id="ec5b5-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="ec5b5-121">ODataError</span></span> | <span data-ttu-id="ec5b5-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-122">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-123">OData URI クエリが無効です \<the specific error is specified\> 。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="ec5b5-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="ec5b5-124">InvalidInput</span></span> | <span data-ttu-id="ec5b5-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-125">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-126">入力が無効です \<the invalid input\> 。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="ec5b5-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="ec5b5-127">InvalidRequestBody</span></span> | <span data-ttu-id="ec5b5-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-128">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-129">要求本文が無効です。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-129">Invalid request body.</span></span>
<span data-ttu-id="ec5b5-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="ec5b5-130">InvalidHashValue</span></span> | <span data-ttu-id="ec5b5-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-131">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-132">ハッシュ値 \<the invalid hash\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="ec5b5-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="ec5b5-133">InvalidDomainName</span></span> | <span data-ttu-id="ec5b5-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-134">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-135">ドメイン名 \<the invalid domain\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="ec5b5-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="ec5b5-136">InvalidIpAddress</span></span> | <span data-ttu-id="ec5b5-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-137">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-138">IP アドレス \<the invalid IP\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="ec5b5-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="ec5b5-139">InvalidUrl</span></span> | <span data-ttu-id="ec5b5-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-140">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-141">URL \<the invalid URL\> が無効です。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="ec5b5-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="ec5b5-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="ec5b5-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-143">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-144">最大バッチ サイズを超えました。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="ec5b5-145">受信: \<batch size received\> 、許可: {batch size allowed}。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="ec5b5-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="ec5b5-146">MissingRequiredParameter</span></span> | <span data-ttu-id="ec5b5-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-147">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-148">パラメーター \<the missing parameter\> がありません。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="ec5b5-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="ec5b5-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="ec5b5-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-150">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-151">OS プラットフォーム \<the client OS Platform\> は、このアクションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="ec5b5-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="ec5b5-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="ec5b5-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-153">BadRequest (400)</span></span> | <span data-ttu-id="ec5b5-154">\<The requested action\> はクライアント バージョン以上 \<supported client version\> でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="ec5b5-155">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-155">Unauthorized</span></span> | <span data-ttu-id="ec5b5-156">承認されていない (401)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-156">Unauthorized (401)</span></span> | <span data-ttu-id="ec5b5-157">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="ec5b5-158">*注: 通常、無効または期限切れの承認ヘッダーが原因です。*</span><span class="sxs-lookup"><span data-stu-id="ec5b5-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="ec5b5-159">禁止されています</span><span class="sxs-lookup"><span data-stu-id="ec5b5-159">Forbidden</span></span> | <span data-ttu-id="ec5b5-160">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-160">Forbidden (403)</span></span> | <span data-ttu-id="ec5b5-161">禁止されています</span><span class="sxs-lookup"><span data-stu-id="ec5b5-161">Forbidden</span></span> <br /><br /><span data-ttu-id="ec5b5-162">*注: 有効なトークンですが、アクションに対するアクセス許可が不十分です*。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="ec5b5-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="ec5b5-163">DisabledFeature</span></span> | <span data-ttu-id="ec5b5-164">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-164">Forbidden (403)</span></span> | <span data-ttu-id="ec5b5-165">テナント機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="ec5b5-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="ec5b5-166">DisallowedOperation</span></span> | <span data-ttu-id="ec5b5-167">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-167">Forbidden (403)</span></span> | <span data-ttu-id="ec5b5-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="ec5b5-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="ec5b5-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="ec5b5-169">NotFound</span></span> | <span data-ttu-id="ec5b5-170">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-170">Not Found (404)</span></span> | <span data-ttu-id="ec5b5-171">一般的なエラー メッセージが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-171">General Not Found error message.</span></span>
<span data-ttu-id="ec5b5-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="ec5b5-172">ResourceNotFound</span></span> | <span data-ttu-id="ec5b5-173">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-173">Not Found (404)</span></span> | <span data-ttu-id="ec5b5-174">リソース \<the requested resource\> が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="ec5b5-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="ec5b5-175">InternalServerError</span></span> | <span data-ttu-id="ec5b5-176">内部サーバー エラー (500)</span><span class="sxs-lookup"><span data-stu-id="ec5b5-176">Internal Server Error (500)</span></span> | <span data-ttu-id="ec5b5-177">*注: エラー メッセージが表示されない場合は、操作を再試行するか、解決されない場合は [Microsoft](/microsoft-365/business-video/get-help-support) にお問い合わせください。*</span><span class="sxs-lookup"><span data-stu-id="ec5b5-177">*Note: No error message,  retry the operation or [contact Microsoft](/microsoft-365/business-video/get-help-support) if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="ec5b5-178">例</span><span class="sxs-lookup"><span data-stu-id="ec5b5-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="ec5b5-179">本文パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec5b5-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec5b5-180">本文パラメーターでは、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="ec5b5-181">*InvalidRequestBody エラーまたは* *MissingRequiredParameter* エラーが発生した場合は、入力ミスが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="ec5b5-182">API のドキュメントを確認し、送信されたパラメーターが関連する例と一致する点を確認します。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="ec5b5-183">追跡 ID</span><span class="sxs-lookup"><span data-stu-id="ec5b5-183">Tracking ID</span></span>

<span data-ttu-id="ec5b5-184">各エラー応答には、追跡用の一意の ID パラメーターが含まれる。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="ec5b5-185">このパラメーターのプロパティ名は target *です*。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="ec5b5-186">エラーについてお問い合わせの際に、この ID を添付すると、問題の根本原因を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ec5b5-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ec5b5-187">関連資料</span><span class="sxs-lookup"><span data-stu-id="ec5b5-187">Related articles</span></span>

- [<span data-ttu-id="ec5b5-188">Microsoft 365Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="ec5b5-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="ec5b5-189">サポートされている Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="ec5b5-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="ec5b5-190">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="ec5b5-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="ec5b5-191">API の制限とライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="ec5b5-191">Learn about API limits and licensing</span></span>](api-terms.md)
