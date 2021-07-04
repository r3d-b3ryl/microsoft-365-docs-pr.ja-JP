---
title: インシデント API の取得
description: '[インシデントの取得] API を使用して、インシデントを 1 つのインシデントにMicrosoft 365 Defender。'
keywords: apis, graph api, supported apis, get, file, hash
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289609"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="de0b7-104">インシデント情報 API の取得</span><span class="sxs-lookup"><span data-stu-id="de0b7-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="de0b7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="de0b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="de0b7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de0b7-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="de0b7-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="de0b7-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="de0b7-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="de0b7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="de0b7-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="de0b7-109">API description</span></span>

<span data-ttu-id="de0b7-110">ID によって特定のインシデントを取得します。</span><span class="sxs-lookup"><span data-stu-id="de0b7-110">Retrieves a specific incident by its ID</span></span>

## <a name="limitations"></a><span data-ttu-id="de0b7-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="de0b7-111">Limitations</span></span>

1. <span data-ttu-id="de0b7-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="de0b7-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="de0b7-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="de0b7-113">Permissions</span></span>

<span data-ttu-id="de0b7-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="de0b7-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="de0b7-115">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="de0b7-115">Permission type</span></span> | <span data-ttu-id="de0b7-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="de0b7-116">Permission</span></span> | <span data-ttu-id="de0b7-117">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="de0b7-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="de0b7-118">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="de0b7-118">Application</span></span> | <span data-ttu-id="de0b7-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="de0b7-119">Incident.Read.All</span></span> | <span data-ttu-id="de0b7-120">'すべてのインシデントを読み取る'</span><span class="sxs-lookup"><span data-stu-id="de0b7-120">'Read all Incidents'</span></span>
<span data-ttu-id="de0b7-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="de0b7-121">Application</span></span> | <span data-ttu-id="de0b7-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="de0b7-122">Incident.ReadWrite.All</span></span> | <span data-ttu-id="de0b7-123">'すべてのインシデントの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="de0b7-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="de0b7-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="de0b7-124">Delegated (work or school account)</span></span> | <span data-ttu-id="de0b7-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="de0b7-125">Incident.Read</span></span> | <span data-ttu-id="de0b7-126">'インシデントの読み取り'</span><span class="sxs-lookup"><span data-stu-id="de0b7-126">'Read Incidents'</span></span>
<span data-ttu-id="de0b7-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="de0b7-127">Delegated (work or school account)</span></span> | <span data-ttu-id="de0b7-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="de0b7-128">Incident.ReadWrite</span></span> | <span data-ttu-id="de0b7-129">'インシデントの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="de0b7-129">'Read and write Incidents'</span></span>

> [!NOTE]
>
> <span data-ttu-id="de0b7-130">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="de0b7-130">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="de0b7-131">ユーザーには、少なくとも次の役割のアクセス許可が必要です。'データの表示'</span><span class="sxs-lookup"><span data-stu-id="de0b7-131">The user needs to have at least the following role permission: 'View Data'</span></span>
> - <span data-ttu-id="de0b7-132">応答には、ユーザーが公開されているインシデントだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de0b7-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="de0b7-133">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="de0b7-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="de0b7-134">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="de0b7-134">Request headers</span></span>

<span data-ttu-id="de0b7-135">名前</span><span class="sxs-lookup"><span data-stu-id="de0b7-135">Name</span></span> | <span data-ttu-id="de0b7-136">種類</span><span class="sxs-lookup"><span data-stu-id="de0b7-136">Type</span></span> | <span data-ttu-id="de0b7-137">説明</span><span class="sxs-lookup"><span data-stu-id="de0b7-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="de0b7-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="de0b7-138">Authorization</span></span> | <span data-ttu-id="de0b7-139">String</span><span class="sxs-lookup"><span data-stu-id="de0b7-139">String</span></span> | <span data-ttu-id="de0b7-140">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="de0b7-140">Bearer {token}.</span></span> <span data-ttu-id="de0b7-141">**必須**</span><span class="sxs-lookup"><span data-stu-id="de0b7-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="de0b7-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="de0b7-142">Request body</span></span>

<span data-ttu-id="de0b7-143">Empty</span><span class="sxs-lookup"><span data-stu-id="de0b7-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="de0b7-144">応答</span><span class="sxs-lookup"><span data-stu-id="de0b7-144">Response</span></span>

<span data-ttu-id="de0b7-145">成功した場合、このメソッドは 200 OK を返し、応答本文のインシデント エンティティを返します。</span><span class="sxs-lookup"><span data-stu-id="de0b7-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="de0b7-146">指定した ID を持つインシデントが見つからなかった場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="de0b7-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="de0b7-147">例</span><span class="sxs-lookup"><span data-stu-id="de0b7-147">Example</span></span>

<span data-ttu-id="de0b7-148">**要求**</span><span class="sxs-lookup"><span data-stu-id="de0b7-148">**Request**</span></span>

<span data-ttu-id="de0b7-149">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="de0b7-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
