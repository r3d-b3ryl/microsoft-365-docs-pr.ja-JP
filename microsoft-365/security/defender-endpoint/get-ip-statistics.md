---
title: IP 統計 API の取得
description: Microsoft Defender for Endpoint を使用して、IP の最新の統計情報を取得します。
keywords: apis, graph api, supported apis, get, ip, statistics, prevalence
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
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998730"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="c9c5f-104">IP 統計 API の取得</span><span class="sxs-lookup"><span data-stu-id="c9c5f-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c9c5f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c9c5f-105">**Applies to:**</span></span>
- [<span data-ttu-id="c9c5f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c9c5f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c9c5f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9c5f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c9c5f-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c9c5f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c9c5f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="c9c5f-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="c9c5f-110">API description</span></span>
<span data-ttu-id="c9c5f-111">指定した IP の統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="c9c5f-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="c9c5f-112">Limitations</span></span>
1. <span data-ttu-id="c9c5f-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="c9c5f-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c9c5f-114">Permissions</span></span>
<span data-ttu-id="c9c5f-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c9c5f-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c9c5f-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c9c5f-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="c9c5f-117">Permission type</span></span> |   <span data-ttu-id="c9c5f-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c9c5f-118">Permission</span></span>  |   <span data-ttu-id="c9c5f-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="c9c5f-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c9c5f-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c9c5f-120">Application</span></span> |   <span data-ttu-id="c9c5f-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="c9c5f-121">Ip.Read.All</span></span> |   <span data-ttu-id="c9c5f-122">'IP アドレス プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="c9c5f-122">'Read IP address profiles'</span></span>
<span data-ttu-id="c9c5f-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="c9c5f-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c9c5f-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="c9c5f-124">Ip.Read.All</span></span> |  <span data-ttu-id="c9c5f-125">'IP アドレス プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="c9c5f-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="c9c5f-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="c9c5f-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c9c5f-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="c9c5f-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c9c5f-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="c9c5f-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="c9c5f-129">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="c9c5f-129">Request headers</span></span>

<span data-ttu-id="c9c5f-130">名前</span><span class="sxs-lookup"><span data-stu-id="c9c5f-130">Name</span></span> | <span data-ttu-id="c9c5f-131">種類</span><span class="sxs-lookup"><span data-stu-id="c9c5f-131">Type</span></span> | <span data-ttu-id="c9c5f-132">説明</span><span class="sxs-lookup"><span data-stu-id="c9c5f-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="c9c5f-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="c9c5f-133">Authorization</span></span> | <span data-ttu-id="c9c5f-134">String</span><span class="sxs-lookup"><span data-stu-id="c9c5f-134">String</span></span> | <span data-ttu-id="c9c5f-135">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-135">Bearer {token}.</span></span> <span data-ttu-id="c9c5f-136">**必須**</span><span class="sxs-lookup"><span data-stu-id="c9c5f-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="c9c5f-137">要求 URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9c5f-137">Request URI parameters</span></span>

<span data-ttu-id="c9c5f-138">名前</span><span class="sxs-lookup"><span data-stu-id="c9c5f-138">Name</span></span> | <span data-ttu-id="c9c5f-139">種類</span><span class="sxs-lookup"><span data-stu-id="c9c5f-139">Type</span></span> | <span data-ttu-id="c9c5f-140">説明</span><span class="sxs-lookup"><span data-stu-id="c9c5f-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="c9c5f-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="c9c5f-141">lookBackHours</span></span> | <span data-ttu-id="c9c5f-142">Int32</span><span class="sxs-lookup"><span data-stu-id="c9c5f-142">Int32</span></span> | <span data-ttu-id="c9c5f-143">統計を取得するために検索する時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="c9c5f-144">既定値は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-144">Defaults to 30 days.</span></span> <span data-ttu-id="c9c5f-145">**オプション**。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c9c5f-146">要求本文</span><span class="sxs-lookup"><span data-stu-id="c9c5f-146">Request body</span></span>
<span data-ttu-id="c9c5f-147">Empty</span><span class="sxs-lookup"><span data-stu-id="c9c5f-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c9c5f-148">応答</span><span class="sxs-lookup"><span data-stu-id="c9c5f-148">Response</span></span>
<span data-ttu-id="c9c5f-149">成功した場合と ip が存在する場合 - 200 OK 本文の統計データを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="c9c5f-150">IP が存在しない - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="c9c5f-151">例</span><span class="sxs-lookup"><span data-stu-id="c9c5f-151">Example</span></span>

<span data-ttu-id="c9c5f-152">**要求**</span><span class="sxs-lookup"><span data-stu-id="c9c5f-152">**Request**</span></span>

<span data-ttu-id="c9c5f-153">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="c9c5f-154">**応答**</span><span class="sxs-lookup"><span data-stu-id="c9c5f-154">**Response**</span></span>

<span data-ttu-id="c9c5f-155">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="c9c5f-156">名前</span><span class="sxs-lookup"><span data-stu-id="c9c5f-156">Name</span></span> | <span data-ttu-id="c9c5f-157">説明</span><span class="sxs-lookup"><span data-stu-id="c9c5f-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="c9c5f-158">組織の普及率</span><span class="sxs-lookup"><span data-stu-id="c9c5f-158">Organization prevalence</span></span> | <span data-ttu-id="c9c5f-159">この IP へのネットワーク接続を開いたデバイスの個別の数。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="c9c5f-160">組織が最初に見られた</span><span class="sxs-lookup"><span data-stu-id="c9c5f-160">Org first seen</span></span> | <span data-ttu-id="c9c5f-161">組織内のこの IP の最初の接続。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="c9c5f-162">組織が最後に見た</span><span class="sxs-lookup"><span data-stu-id="c9c5f-162">Org last seen</span></span>  | <span data-ttu-id="c9c5f-163">組織内のこの IP の最後の接続。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="c9c5f-164">この統計情報は、過去 30 日間のデータに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="c9c5f-164">This statistic information is based on data from the past 30 days.</span></span> 
