---
title: インジケーター API の送信または更新
description: Submit または Update Indicator API を使用して、Microsoft Defender for Endpoint の新しい Indicator エンティティを送信または更新する方法について説明します。
keywords: apis, graph api, supported apis, submit, ti, indicator, update
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187257"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="eb789-104">インジケーター API の送信または更新</span><span class="sxs-lookup"><span data-stu-id="eb789-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eb789-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="eb789-105">**Applies to:**</span></span>
- [<span data-ttu-id="eb789-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb789-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eb789-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb789-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eb789-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="eb789-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eb789-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="eb789-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="eb789-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="eb789-110">API description</span></span>
<span data-ttu-id="eb789-111">新しい Indicator エンティティを [送信または更新](ti-indicator.md) します。</span><span class="sxs-lookup"><span data-stu-id="eb789-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="eb789-112">IPs の CIDR 表記はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eb789-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="eb789-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="eb789-113">Limitations</span></span>
1. <span data-ttu-id="eb789-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="eb789-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="eb789-115">テナントごとに 15,000 のアクティブインジケーターの制限があります。</span><span class="sxs-lookup"><span data-stu-id="eb789-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="eb789-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb789-116">Permissions</span></span>
<span data-ttu-id="eb789-117">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="eb789-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eb789-118">アクセス許可の選択方法などの詳細については、「開始する」 [を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="eb789-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="eb789-119">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="eb789-119">Permission type</span></span> |   <span data-ttu-id="eb789-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb789-120">Permission</span></span>  |   <span data-ttu-id="eb789-121">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="eb789-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="eb789-122">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="eb789-122">Application</span></span> |   <span data-ttu-id="eb789-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="eb789-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="eb789-124">'読み取りおよび書き込みインジケーター'</span><span class="sxs-lookup"><span data-stu-id="eb789-124">'Read and write Indicators'</span></span>
<span data-ttu-id="eb789-125">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="eb789-125">Application</span></span> |   <span data-ttu-id="eb789-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="eb789-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="eb789-127">'すべてのインジケーターの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="eb789-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="eb789-128">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="eb789-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="eb789-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="eb789-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="eb789-130">'読み取りおよび書き込みインジケーター'</span><span class="sxs-lookup"><span data-stu-id="eb789-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="eb789-131">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="eb789-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="eb789-132">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="eb789-132">Request headers</span></span>

<span data-ttu-id="eb789-133">名前</span><span class="sxs-lookup"><span data-stu-id="eb789-133">Name</span></span> | <span data-ttu-id="eb789-134">型</span><span class="sxs-lookup"><span data-stu-id="eb789-134">Type</span></span> | <span data-ttu-id="eb789-135">説明</span><span class="sxs-lookup"><span data-stu-id="eb789-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="eb789-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="eb789-136">Authorization</span></span> | <span data-ttu-id="eb789-137">String</span><span class="sxs-lookup"><span data-stu-id="eb789-137">String</span></span> | <span data-ttu-id="eb789-138">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="eb789-138">Bearer {token}.</span></span> <span data-ttu-id="eb789-139">**必須**</span><span class="sxs-lookup"><span data-stu-id="eb789-139">**Required**.</span></span>
<span data-ttu-id="eb789-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="eb789-140">Content-Type</span></span> | <span data-ttu-id="eb789-141">string</span><span class="sxs-lookup"><span data-stu-id="eb789-141">string</span></span> | <span data-ttu-id="eb789-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="eb789-142">application/json.</span></span> <span data-ttu-id="eb789-143">**必須**</span><span class="sxs-lookup"><span data-stu-id="eb789-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="eb789-144">要求本文</span><span class="sxs-lookup"><span data-stu-id="eb789-144">Request body</span></span>
<span data-ttu-id="eb789-145">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb789-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="eb789-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb789-146">Parameter</span></span> | <span data-ttu-id="eb789-147">型</span><span class="sxs-lookup"><span data-stu-id="eb789-147">Type</span></span>    | <span data-ttu-id="eb789-148">説明</span><span class="sxs-lookup"><span data-stu-id="eb789-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="eb789-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="eb789-149">indicatorValue</span></span> | <span data-ttu-id="eb789-150">String</span><span class="sxs-lookup"><span data-stu-id="eb789-150">String</span></span> | <span data-ttu-id="eb789-151">Indicator エンティティ [の](ti-indicator.md) ID。</span><span class="sxs-lookup"><span data-stu-id="eb789-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="eb789-152">**Required**</span><span class="sxs-lookup"><span data-stu-id="eb789-152">**Required**</span></span>
<span data-ttu-id="eb789-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="eb789-153">indicatorType</span></span> | <span data-ttu-id="eb789-154">列挙</span><span class="sxs-lookup"><span data-stu-id="eb789-154">Enum</span></span> | <span data-ttu-id="eb789-155">インジケーターの種類。</span><span class="sxs-lookup"><span data-stu-id="eb789-155">Type of the indicator.</span></span> <span data-ttu-id="eb789-156">指定できる値は、"FileSha1"、"FileSha256"、"IpAddress"、"DomainName" および "Url" です。</span><span class="sxs-lookup"><span data-stu-id="eb789-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="eb789-157">**Required**</span><span class="sxs-lookup"><span data-stu-id="eb789-157">**Required**</span></span>
<span data-ttu-id="eb789-158">action</span><span class="sxs-lookup"><span data-stu-id="eb789-158">action</span></span> | <span data-ttu-id="eb789-159">列挙</span><span class="sxs-lookup"><span data-stu-id="eb789-159">Enum</span></span> | <span data-ttu-id="eb789-160">インジケーターが組織内で検出される場合に実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="eb789-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="eb789-161">指定できる値は、"Alert"、"AlertAndBlock"、"Allowed" です。</span><span class="sxs-lookup"><span data-stu-id="eb789-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="eb789-162">**Required**</span><span class="sxs-lookup"><span data-stu-id="eb789-162">**Required**</span></span>
<span data-ttu-id="eb789-163">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="eb789-163">application</span></span> | <span data-ttu-id="eb789-164">String</span><span class="sxs-lookup"><span data-stu-id="eb789-164">String</span></span> | <span data-ttu-id="eb789-165">インジケーターに関連付けられているアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="eb789-165">The application associated with the indicator.</span></span> <span data-ttu-id="eb789-166">**Optional**</span><span class="sxs-lookup"><span data-stu-id="eb789-166">**Optional**</span></span>
<span data-ttu-id="eb789-167">title</span><span class="sxs-lookup"><span data-stu-id="eb789-167">title</span></span> | <span data-ttu-id="eb789-168">String</span><span class="sxs-lookup"><span data-stu-id="eb789-168">String</span></span> | <span data-ttu-id="eb789-169">インジケーターアラートのタイトル。</span><span class="sxs-lookup"><span data-stu-id="eb789-169">Indicator alert title.</span></span> <span data-ttu-id="eb789-170">**Required**</span><span class="sxs-lookup"><span data-stu-id="eb789-170">**Required**</span></span>
<span data-ttu-id="eb789-171">説明</span><span class="sxs-lookup"><span data-stu-id="eb789-171">description</span></span> | <span data-ttu-id="eb789-172">String</span><span class="sxs-lookup"><span data-stu-id="eb789-172">String</span></span> | <span data-ttu-id="eb789-173">インジケーターの説明。</span><span class="sxs-lookup"><span data-stu-id="eb789-173">Description of the indicator.</span></span> <span data-ttu-id="eb789-174">**Required**</span><span class="sxs-lookup"><span data-stu-id="eb789-174">**Required**</span></span>
<span data-ttu-id="eb789-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="eb789-175">expirationTime</span></span> | <span data-ttu-id="eb789-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="eb789-176">DateTimeOffset</span></span> | <span data-ttu-id="eb789-177">インジケーターの有効期限。</span><span class="sxs-lookup"><span data-stu-id="eb789-177">The expiration time of the indicator.</span></span> <span data-ttu-id="eb789-178">**Optional**</span><span class="sxs-lookup"><span data-stu-id="eb789-178">**Optional**</span></span>
<span data-ttu-id="eb789-179">severity</span><span class="sxs-lookup"><span data-stu-id="eb789-179">severity</span></span> | <span data-ttu-id="eb789-180">列挙</span><span class="sxs-lookup"><span data-stu-id="eb789-180">Enum</span></span> | <span data-ttu-id="eb789-181">インジケーターの重大度。</span><span class="sxs-lookup"><span data-stu-id="eb789-181">The severity of the indicator.</span></span> <span data-ttu-id="eb789-182">指定できる値は、"Informational"、"Low"、"Medium"、"High" です。</span><span class="sxs-lookup"><span data-stu-id="eb789-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="eb789-183">**Optional**</span><span class="sxs-lookup"><span data-stu-id="eb789-183">**Optional**</span></span>
<span data-ttu-id="eb789-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="eb789-184">recommendedActions</span></span> | <span data-ttu-id="eb789-185">String</span><span class="sxs-lookup"><span data-stu-id="eb789-185">String</span></span> | <span data-ttu-id="eb789-186">TI インジケーターアラート推奨アクション。</span><span class="sxs-lookup"><span data-stu-id="eb789-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="eb789-187">**Optional**</span><span class="sxs-lookup"><span data-stu-id="eb789-187">**Optional**</span></span>
<span data-ttu-id="eb789-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="eb789-188">rbacGroupNames</span></span> | <span data-ttu-id="eb789-189">String</span><span class="sxs-lookup"><span data-stu-id="eb789-189">String</span></span> | <span data-ttu-id="eb789-190">インジケーターが適用される RBAC グループ名のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="eb789-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="eb789-191">**Optional**</span><span class="sxs-lookup"><span data-stu-id="eb789-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="eb789-192">応答</span><span class="sxs-lookup"><span data-stu-id="eb789-192">Response</span></span>
- <span data-ttu-id="eb789-193">成功した場合、このメソッドは 200 - OK 応答コードと、応答本文で作成/更新 [された Indicator](ti-indicator.md) エンティティを返します。</span><span class="sxs-lookup"><span data-stu-id="eb789-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="eb789-194">成功しない場合: このメソッドは 400 - Bad Request を返します。</span><span class="sxs-lookup"><span data-stu-id="eb789-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="eb789-195">通常、不適切な要求は、不適切な本文を示します。</span><span class="sxs-lookup"><span data-stu-id="eb789-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="eb789-196">例</span><span class="sxs-lookup"><span data-stu-id="eb789-196">Example</span></span>

<span data-ttu-id="eb789-197">**要求**</span><span class="sxs-lookup"><span data-stu-id="eb789-197">**Request**</span></span>

<span data-ttu-id="eb789-198">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="eb789-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="eb789-199">関連トピック</span><span class="sxs-lookup"><span data-stu-id="eb789-199">Related topic</span></span>
- [<span data-ttu-id="eb789-200">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="eb789-200">Manage indicators</span></span>](manage-indicators.md)
