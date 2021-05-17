---
title: MachineAction オブジェクト API の取得
description: Get MachineAction API を使用して、Microsoft Defender for Endpoint の ID で特定の Machine Action を取得する方法について説明します。
keywords: apis、graph api、サポートされている api、machineaction オブジェクト
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 180179d5b1362ad4952618148b11007aa9efe91c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200067"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="19be0-104">Get machineAction API</span><span class="sxs-lookup"><span data-stu-id="19be0-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19be0-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="19be0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="19be0-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="19be0-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19be0-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="19be0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="19be0-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="19be0-108">API description</span></span>
<span data-ttu-id="19be0-109">ID によって特定 [の Machine Action](machineaction.md) を取得します。</span><span class="sxs-lookup"><span data-stu-id="19be0-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="19be0-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="19be0-110">Limitations</span></span>
1. <span data-ttu-id="19be0-111">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="19be0-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="19be0-112">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="19be0-112">Permissions</span></span>
<span data-ttu-id="19be0-113">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="19be0-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="19be0-114">アクセス許可の選択方法などの詳細については [、「Use Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="19be0-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="19be0-115">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="19be0-115">Permission type</span></span> |   <span data-ttu-id="19be0-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="19be0-116">Permission</span></span>  |   <span data-ttu-id="19be0-117">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="19be0-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="19be0-118">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="19be0-118">Application</span></span> |   <span data-ttu-id="19be0-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="19be0-119">Machine.Read.All</span></span> |  <span data-ttu-id="19be0-120">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="19be0-120">'Read all machine profiles'</span></span>
<span data-ttu-id="19be0-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="19be0-121">Application</span></span> |   <span data-ttu-id="19be0-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="19be0-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="19be0-123">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="19be0-123">'Read and write all machine information'</span></span>
<span data-ttu-id="19be0-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="19be0-124">Delegated (work or school account)</span></span> | <span data-ttu-id="19be0-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="19be0-125">Machine.Read</span></span> | <span data-ttu-id="19be0-126">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="19be0-126">'Read machine information'</span></span>
<span data-ttu-id="19be0-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="19be0-127">Delegated (work or school account)</span></span> | <span data-ttu-id="19be0-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="19be0-128">Machine.ReadWrite</span></span> | <span data-ttu-id="19be0-129">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="19be0-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="19be0-130">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="19be0-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="19be0-131">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="19be0-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="19be0-132">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="19be0-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="19be0-133">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="19be0-133">Request headers</span></span>

<span data-ttu-id="19be0-134">名前</span><span class="sxs-lookup"><span data-stu-id="19be0-134">Name</span></span> | <span data-ttu-id="19be0-135">型</span><span class="sxs-lookup"><span data-stu-id="19be0-135">Type</span></span> | <span data-ttu-id="19be0-136">説明</span><span class="sxs-lookup"><span data-stu-id="19be0-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="19be0-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="19be0-137">Authorization</span></span> | <span data-ttu-id="19be0-138">String</span><span class="sxs-lookup"><span data-stu-id="19be0-138">String</span></span> | <span data-ttu-id="19be0-139">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="19be0-139">Bearer {token}.</span></span> <span data-ttu-id="19be0-140">**必須**</span><span class="sxs-lookup"><span data-stu-id="19be0-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="19be0-141">要求本文</span><span class="sxs-lookup"><span data-stu-id="19be0-141">Request body</span></span>
<span data-ttu-id="19be0-142">Empty</span><span class="sxs-lookup"><span data-stu-id="19be0-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="19be0-143">応答</span><span class="sxs-lookup"><span data-stu-id="19be0-143">Response</span></span>
<span data-ttu-id="19be0-144">成功した場合、このメソッドは Machine Action エンティティを持つ 200 Ok 応答 [コードを返](machineaction.md) します。</span><span class="sxs-lookup"><span data-stu-id="19be0-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="19be0-145">指定した ID を持つコンピューター アクション エンティティが見つからなかった場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="19be0-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="19be0-146">例</span><span class="sxs-lookup"><span data-stu-id="19be0-146">Example</span></span>

<span data-ttu-id="19be0-147">**要求**</span><span class="sxs-lookup"><span data-stu-id="19be0-147">**Request**</span></span>

<span data-ttu-id="19be0-148">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="19be0-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="19be0-149">**応答**</span><span class="sxs-lookup"><span data-stu-id="19be0-149">**Response**</span></span>

<span data-ttu-id="19be0-150">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="19be0-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
