---
title: ドメイン統計 API の取得
description: Get domain statistics API を使用して、Microsoft Defender for Endpoint の特定のドメインの統計情報を取得する方法について説明します。
keywords: apis、graph api、サポートされている API、get、ドメイン、ドメイン関連デバイス
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
ms.openlocfilehash: d2edc5d429d124412134b466753b65506d2dd7a9
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772187"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="3239c-104">ドメイン統計 API の取得</span><span class="sxs-lookup"><span data-stu-id="3239c-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3239c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3239c-105">**Applies to:**</span></span>
- [<span data-ttu-id="3239c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3239c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3239c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3239c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3239c-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3239c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3239c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3239c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3239c-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="3239c-110">API description</span></span>
<span data-ttu-id="3239c-111">指定したドメインの統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3239c-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="3239c-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="3239c-112">Limitations</span></span>
1. <span data-ttu-id="3239c-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="3239c-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3239c-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3239c-114">Permissions</span></span>
<span data-ttu-id="3239c-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="3239c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3239c-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3239c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3239c-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="3239c-117">Permission type</span></span> |   <span data-ttu-id="3239c-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3239c-118">Permission</span></span>  |   <span data-ttu-id="3239c-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="3239c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3239c-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3239c-120">Application</span></span> |   <span data-ttu-id="3239c-121">URL。Read.All</span><span class="sxs-lookup"><span data-stu-id="3239c-121">URL.Read.All</span></span> |  <span data-ttu-id="3239c-122">'URL の読み取り'</span><span class="sxs-lookup"><span data-stu-id="3239c-122">'Read URLs'</span></span>
<span data-ttu-id="3239c-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="3239c-123">Delegated (work or school account)</span></span> | <span data-ttu-id="3239c-124">URL。Read.All</span><span class="sxs-lookup"><span data-stu-id="3239c-124">URL.Read.All</span></span> | <span data-ttu-id="3239c-125">'URL の読み取り'</span><span class="sxs-lookup"><span data-stu-id="3239c-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="3239c-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="3239c-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3239c-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="3239c-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3239c-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3239c-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="3239c-129">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3239c-129">Request headers</span></span>

<span data-ttu-id="3239c-130">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3239c-130">Header</span></span> | <span data-ttu-id="3239c-131">値</span><span class="sxs-lookup"><span data-stu-id="3239c-131">Value</span></span> 
:---|:---
<span data-ttu-id="3239c-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="3239c-132">Authorization</span></span> | <span data-ttu-id="3239c-133">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="3239c-133">Bearer {token}.</span></span> <span data-ttu-id="3239c-134">**必須**</span><span class="sxs-lookup"><span data-stu-id="3239c-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="3239c-135">要求 URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="3239c-135">Request URI parameters</span></span>

<span data-ttu-id="3239c-136">名前</span><span class="sxs-lookup"><span data-stu-id="3239c-136">Name</span></span> | <span data-ttu-id="3239c-137">種類</span><span class="sxs-lookup"><span data-stu-id="3239c-137">Type</span></span> | <span data-ttu-id="3239c-138">説明</span><span class="sxs-lookup"><span data-stu-id="3239c-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="3239c-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="3239c-139">lookBackHours</span></span> | <span data-ttu-id="3239c-140">Int32</span><span class="sxs-lookup"><span data-stu-id="3239c-140">Int32</span></span> | <span data-ttu-id="3239c-141">統計を取得するために検索する時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="3239c-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="3239c-142">既定値は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="3239c-142">Defaults to 30 days.</span></span> <span data-ttu-id="3239c-143">**オプション**。</span><span class="sxs-lookup"><span data-stu-id="3239c-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3239c-144">要求本文</span><span class="sxs-lookup"><span data-stu-id="3239c-144">Request body</span></span>
<span data-ttu-id="3239c-145">Empty</span><span class="sxs-lookup"><span data-stu-id="3239c-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3239c-146">応答</span><span class="sxs-lookup"><span data-stu-id="3239c-146">Response</span></span>
<span data-ttu-id="3239c-147">成功し、ドメインが存在する場合 - 200 OK、応答本文に statistics オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3239c-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="3239c-148">ドメインが存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="3239c-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3239c-149">例</span><span class="sxs-lookup"><span data-stu-id="3239c-149">Example</span></span>

<span data-ttu-id="3239c-150">**要求**</span><span class="sxs-lookup"><span data-stu-id="3239c-150">**Request**</span></span>

<span data-ttu-id="3239c-151">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="3239c-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="3239c-152">**応答**</span><span class="sxs-lookup"><span data-stu-id="3239c-152">**Response**</span></span>

<span data-ttu-id="3239c-153">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="3239c-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
