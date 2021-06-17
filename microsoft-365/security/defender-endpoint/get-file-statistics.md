---
title: ファイル統計 API の取得
description: Get file statistics API を使用して、Microsoft Defender for Endpoint で指定されたファイルの統計情報を取得する方法について説明します。
keywords: apis, graph api, supported apis, get, file, statistics
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
ms.openlocfilehash: 826b2ff25363f1d9a6276e1a42a10c1cf4995904
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998814"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="57761-104">ファイル統計 API の取得</span><span class="sxs-lookup"><span data-stu-id="57761-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="57761-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="57761-105">**Applies to:**</span></span>
- [<span data-ttu-id="57761-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="57761-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="57761-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57761-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="57761-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="57761-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="57761-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="57761-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="57761-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="57761-110">API description</span></span>
<span data-ttu-id="57761-111">指定したファイルの統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="57761-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="57761-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="57761-112">Limitations</span></span>
1. <span data-ttu-id="57761-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="57761-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="57761-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="57761-114">Permissions</span></span>
<span data-ttu-id="57761-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="57761-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="57761-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="57761-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="57761-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="57761-117">Permission type</span></span> |   <span data-ttu-id="57761-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="57761-118">Permission</span></span>  |   <span data-ttu-id="57761-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="57761-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="57761-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="57761-120">Application</span></span> |   <span data-ttu-id="57761-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="57761-121">File.Read.All</span></span> | <span data-ttu-id="57761-122">'ファイル プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="57761-122">'Read file profiles'</span></span>
<span data-ttu-id="57761-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="57761-123">Delegated (work or school account)</span></span> | <span data-ttu-id="57761-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="57761-124">File.Read.All</span></span> | <span data-ttu-id="57761-125">'ファイル プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="57761-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="57761-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="57761-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="57761-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="57761-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="57761-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="57761-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="57761-129">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="57761-129">Request headers</span></span>

<span data-ttu-id="57761-130">名前</span><span class="sxs-lookup"><span data-stu-id="57761-130">Name</span></span> | <span data-ttu-id="57761-131">種類</span><span class="sxs-lookup"><span data-stu-id="57761-131">Type</span></span> | <span data-ttu-id="57761-132">説明</span><span class="sxs-lookup"><span data-stu-id="57761-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="57761-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="57761-133">Authorization</span></span> | <span data-ttu-id="57761-134">String</span><span class="sxs-lookup"><span data-stu-id="57761-134">String</span></span> | <span data-ttu-id="57761-135">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="57761-135">Bearer {token}.</span></span> <span data-ttu-id="57761-136">**必須**</span><span class="sxs-lookup"><span data-stu-id="57761-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="57761-137">要求 URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="57761-137">Request URI parameters</span></span>

<span data-ttu-id="57761-138">名前</span><span class="sxs-lookup"><span data-stu-id="57761-138">Name</span></span> | <span data-ttu-id="57761-139">種類</span><span class="sxs-lookup"><span data-stu-id="57761-139">Type</span></span> | <span data-ttu-id="57761-140">説明</span><span class="sxs-lookup"><span data-stu-id="57761-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="57761-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="57761-141">lookBackHours</span></span> | <span data-ttu-id="57761-142">Int32</span><span class="sxs-lookup"><span data-stu-id="57761-142">Int32</span></span> | <span data-ttu-id="57761-143">統計を取得するために検索する時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="57761-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="57761-144">既定値は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="57761-144">Defaults to 30 days.</span></span> <span data-ttu-id="57761-145">**オプション**。</span><span class="sxs-lookup"><span data-stu-id="57761-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="57761-146">要求本文</span><span class="sxs-lookup"><span data-stu-id="57761-146">Request body</span></span>
<span data-ttu-id="57761-147">Empty</span><span class="sxs-lookup"><span data-stu-id="57761-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="57761-148">応答</span><span class="sxs-lookup"><span data-stu-id="57761-148">Response</span></span>
<span data-ttu-id="57761-149">成功し、ファイルが存在する場合 - 200 OK 本文の統計データ。</span><span class="sxs-lookup"><span data-stu-id="57761-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="57761-150">ファイルが存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="57761-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="57761-151">例</span><span class="sxs-lookup"><span data-stu-id="57761-151">Example</span></span>

<span data-ttu-id="57761-152">**要求**</span><span class="sxs-lookup"><span data-stu-id="57761-152">**Request**</span></span>

<span data-ttu-id="57761-153">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="57761-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="57761-154">**応答**</span><span class="sxs-lookup"><span data-stu-id="57761-154">**Response**</span></span>

<span data-ttu-id="57761-155">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="57761-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "organizationPrevalence": 14850,
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globallyPrevalence": 705012,
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
