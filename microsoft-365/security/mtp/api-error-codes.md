---
title: 一般的な Microsoft 365 Defender REST API のエラーコード
description: 一般的な Microsoft 365 Defender REST API のエラーコードについて
keywords: api、error、コード、一般的なエラー、mtp、api のエラーコード
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
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846010"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="6abda-104">一般的な Microsoft 365 Defender REST API のエラーコード</span><span class="sxs-lookup"><span data-stu-id="6abda-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6abda-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6abda-105">**Applies to:**</span></span>
- <span data-ttu-id="6abda-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6abda-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="6abda-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="6abda-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6abda-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6abda-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6abda-109">次の表に示すエラーコードは、Microsoft 365 Defender Api のいずれかの操作によって返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6abda-109">The error codes listed in the following table may be returned by an operation on any of Microsoft 365 Defender APIs.</span></span>

<span data-ttu-id="6abda-110">エラー応答ごとにエラーメッセージが含まれています。これは、この問題を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6abda-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="6abda-111">このメッセージは、変更できる無料のテキストです。</span><span class="sxs-lookup"><span data-stu-id="6abda-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="6abda-112">ページの下部に、応答の例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="6abda-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="6abda-113">エラー コード</span><span class="sxs-lookup"><span data-stu-id="6abda-113">Error code</span></span> |<span data-ttu-id="6abda-114">HTTP ステータス コード</span><span class="sxs-lookup"><span data-stu-id="6abda-114">HTTP status code</span></span> |<span data-ttu-id="6abda-115">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6abda-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="6abda-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="6abda-116">BadRequest</span></span> | <span data-ttu-id="6abda-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-117">BadRequest (400)</span></span> | <span data-ttu-id="6abda-118">通常の正しくない要求エラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="6abda-118">General Bad Request error message.</span></span>
<span data-ttu-id="6abda-119">/エラー</span><span class="sxs-lookup"><span data-stu-id="6abda-119">ODataError</span></span> | <span data-ttu-id="6abda-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-120">BadRequest (400)</span></span> | <span data-ttu-id="6abda-121">OData URI クエリが正しくありません (具体的なエラーが指定されています)。</span><span class="sxs-lookup"><span data-stu-id="6abda-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="6abda-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="6abda-122">InvalidInput</span></span> | <span data-ttu-id="6abda-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-123">BadRequest (400)</span></span> | <span data-ttu-id="6abda-124">無効な入力です {無効な入力} です。</span><span class="sxs-lookup"><span data-stu-id="6abda-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="6abda-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="6abda-125">InvalidRequestBody</span></span> | <span data-ttu-id="6abda-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-126">BadRequest (400)</span></span> | <span data-ttu-id="6abda-127">要求本文が無効です。</span><span class="sxs-lookup"><span data-stu-id="6abda-127">Invalid request body.</span></span>
<span data-ttu-id="6abda-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="6abda-128">InvalidHashValue</span></span> | <span data-ttu-id="6abda-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-129">BadRequest (400)</span></span> | <span data-ttu-id="6abda-130">ハッシュ値 {無効なハッシュ} が無効です。</span><span class="sxs-lookup"><span data-stu-id="6abda-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="6abda-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="6abda-131">InvalidDomainName</span></span> | <span data-ttu-id="6abda-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-132">BadRequest (400)</span></span> | <span data-ttu-id="6abda-133">ドメイン名 {無効なドメイン} が無効です。</span><span class="sxs-lookup"><span data-stu-id="6abda-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="6abda-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="6abda-134">InvalidIpAddress</span></span> | <span data-ttu-id="6abda-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-135">BadRequest (400)</span></span> | <span data-ttu-id="6abda-136">IP アドレス {無効な IP} が無効です。</span><span class="sxs-lookup"><span data-stu-id="6abda-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="6abda-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="6abda-137">InvalidUrl</span></span> | <span data-ttu-id="6abda-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-138">BadRequest (400)</span></span> | <span data-ttu-id="6abda-139">URL {無効な URL} が無効です。</span><span class="sxs-lookup"><span data-stu-id="6abda-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="6abda-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="6abda-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="6abda-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-141">BadRequest (400)</span></span> | <span data-ttu-id="6abda-142">最大バッチサイズを超えています。</span><span class="sxs-lookup"><span data-stu-id="6abda-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="6abda-143">Received: {batch size received in received}、allowed: {batch size allowed}。</span><span class="sxs-lookup"><span data-stu-id="6abda-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="6abda-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="6abda-144">MissingRequiredParameter</span></span> | <span data-ttu-id="6abda-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-145">BadRequest (400)</span></span> | <span data-ttu-id="6abda-146">パラメーター {不足しているパラメーター} がありません。</span><span class="sxs-lookup"><span data-stu-id="6abda-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="6abda-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="6abda-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="6abda-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-148">BadRequest (400)</span></span> | <span data-ttu-id="6abda-149">OS プラットフォーム {クライアント OS プラットフォーム} は、このアクションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6abda-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="6abda-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="6abda-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="6abda-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="6abda-151">BadRequest (400)</span></span> | <span data-ttu-id="6abda-152">{要求されたアクション} はクライアントバージョン {サポートされているクライアントバージョン} 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6abda-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="6abda-153">権限がありません (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="6abda-153">Unauthorized</span></span> | <span data-ttu-id="6abda-154">未承認 (401)</span><span class="sxs-lookup"><span data-stu-id="6abda-154">Unauthorized (401)</span></span> | <span data-ttu-id="6abda-155">承認されていない (通常は無効または期限切れの承認ヘッダー)。</span><span class="sxs-lookup"><span data-stu-id="6abda-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="6abda-156">禁止されています</span><span class="sxs-lookup"><span data-stu-id="6abda-156">Forbidden</span></span> | <span data-ttu-id="6abda-157">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="6abda-157">Forbidden (403)</span></span> | <span data-ttu-id="6abda-158">禁止 (有効なトークンですが、アクションに対して十分な権限がありません)。</span><span class="sxs-lookup"><span data-stu-id="6abda-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="6abda-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="6abda-159">DisabledFeature</span></span> | <span data-ttu-id="6abda-160">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="6abda-160">Forbidden (403)</span></span> | <span data-ttu-id="6abda-161">テナント機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="6abda-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="6abda-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="6abda-162">DisallowedOperation</span></span> | <span data-ttu-id="6abda-163">禁止 (403)</span><span class="sxs-lookup"><span data-stu-id="6abda-163">Forbidden (403)</span></span> | <span data-ttu-id="6abda-164">{許可されていない操作と理由}。</span><span class="sxs-lookup"><span data-stu-id="6abda-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="6abda-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="6abda-165">NotFound</span></span> | <span data-ttu-id="6abda-166">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="6abda-166">Not Found (404)</span></span> | <span data-ttu-id="6abda-167">一般的なエラーメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="6abda-167">General Not Found error message.</span></span>
<span data-ttu-id="6abda-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="6abda-168">ResourceNotFound</span></span> | <span data-ttu-id="6abda-169">見つかりません (404)</span><span class="sxs-lookup"><span data-stu-id="6abda-169">Not Found (404)</span></span> | <span data-ttu-id="6abda-170">リソース {要求されたリソース} が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="6abda-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="6abda-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="6abda-171">InternalServerError</span></span> | <span data-ttu-id="6abda-172">内部サーバーエラー (500)</span><span class="sxs-lookup"><span data-stu-id="6abda-172">Internal Server Error (500)</span></span> | <span data-ttu-id="6abda-173">(エラーメッセージが表示されない場合は、操作を再試行するか、お問い合わせください。解決しない場合)</span><span class="sxs-lookup"><span data-stu-id="6abda-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="6abda-174">本文のパラメーターでは大文字と小文字が区別される</span><span class="sxs-lookup"><span data-stu-id="6abda-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="6abda-175">送信される本文パラメーターは、現在、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6abda-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="6abda-176">**Invalidrequestbody** または **MissingRequiredParameter** のエラーが発生した場合は、パラメーターの大文字または小文字が正しくないことが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6abda-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="6abda-177">API ドキュメントページを参照して、送信されたパラメーターが関連する例と一致していることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6abda-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="6abda-178">関連付け要求 ID</span><span class="sxs-lookup"><span data-stu-id="6abda-178">Correlation request ID</span></span>

<span data-ttu-id="6abda-179">各エラー応答には、追跡用の一意の ID パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6abda-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="6abda-180">このパラメーターのプロパティ名は "target" です。</span><span class="sxs-lookup"><span data-stu-id="6abda-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="6abda-181">エラーについてお問い合わせの際には、この ID を添付することで問題の根本的な原因を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6abda-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="6abda-182">例</span><span class="sxs-lookup"><span data-stu-id="6abda-182">Examples</span></span>

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

