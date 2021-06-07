---
title: ID API でコンピューターを取得する
description: Id によるコンピューターの取得 API を使用して、Microsoft Defender for Endpoint のデバイス ID またはコンピューター名でコンピューターを取得する方法について説明します。
keywords: apis、graph api、サポートされている API、get、デバイス、エンティティ、ID
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e4ed5a68b0f4c5e9472702d3cc2798a810e4f84e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769475"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="b0592-104">ID API でコンピューターを取得する</span><span class="sxs-lookup"><span data-stu-id="b0592-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0592-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b0592-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="b0592-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b0592-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b0592-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b0592-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b0592-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="b0592-108">API description</span></span>
<span data-ttu-id="b0592-109">デバイス ID または [コンピューター名によって](machine.md) 特定のコンピューターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b0592-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="b0592-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="b0592-110">Limitations</span></span>
1. <span data-ttu-id="b0592-111">構成済みのアイテム保持ポリシーに従ってデバイスを最後に表示できます。</span><span class="sxs-lookup"><span data-stu-id="b0592-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="b0592-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="b0592-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b0592-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b0592-113">Permissions</span></span>
<span data-ttu-id="b0592-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0592-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b0592-115">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b0592-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b0592-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="b0592-116">Permission type</span></span> |   <span data-ttu-id="b0592-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b0592-117">Permission</span></span>  |   <span data-ttu-id="b0592-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="b0592-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b0592-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b0592-119">Application</span></span> |   <span data-ttu-id="b0592-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="b0592-120">Machine.Read.All</span></span> |  <span data-ttu-id="b0592-121">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="b0592-121">'Read all machine profiles'</span></span>
<span data-ttu-id="b0592-122">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b0592-122">Application</span></span> |   <span data-ttu-id="b0592-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b0592-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="b0592-124">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="b0592-124">'Read and write all machine information'</span></span>
<span data-ttu-id="b0592-125">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b0592-125">Delegated (work or school account)</span></span> | <span data-ttu-id="b0592-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="b0592-126">Machine.Read</span></span> | <span data-ttu-id="b0592-127">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="b0592-127">'Read machine information'</span></span>
<span data-ttu-id="b0592-128">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b0592-128">Delegated (work or school account)</span></span> | <span data-ttu-id="b0592-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b0592-129">Machine.ReadWrite</span></span> | <span data-ttu-id="b0592-130">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="b0592-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="b0592-131">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="b0592-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b0592-132">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="b0592-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b0592-133">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="b0592-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="b0592-134">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b0592-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="b0592-135">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b0592-135">Request headers</span></span>

<span data-ttu-id="b0592-136">名前</span><span class="sxs-lookup"><span data-stu-id="b0592-136">Name</span></span> | <span data-ttu-id="b0592-137">種類</span><span class="sxs-lookup"><span data-stu-id="b0592-137">Type</span></span> | <span data-ttu-id="b0592-138">説明</span><span class="sxs-lookup"><span data-stu-id="b0592-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="b0592-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="b0592-139">Authorization</span></span> | <span data-ttu-id="b0592-140">String</span><span class="sxs-lookup"><span data-stu-id="b0592-140">String</span></span> | <span data-ttu-id="b0592-141">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="b0592-141">Bearer {token}.</span></span> <span data-ttu-id="b0592-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="b0592-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b0592-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="b0592-143">Request body</span></span>
<span data-ttu-id="b0592-144">Empty</span><span class="sxs-lookup"><span data-stu-id="b0592-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b0592-145">応答</span><span class="sxs-lookup"><span data-stu-id="b0592-145">Response</span></span>
<span data-ttu-id="b0592-146">成功し、デバイスが存在する場合 - 本体の[](machine.md)コンピューター エンティティで 200 OK。</span><span class="sxs-lookup"><span data-stu-id="b0592-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="b0592-147">指定した ID を持つコンピューターが見つからない場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="b0592-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b0592-148">例</span><span class="sxs-lookup"><span data-stu-id="b0592-148">Example</span></span>

<span data-ttu-id="b0592-149">**要求**</span><span class="sxs-lookup"><span data-stu-id="b0592-149">**Request**</span></span>

<span data-ttu-id="b0592-150">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="b0592-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="b0592-151">**応答**</span><span class="sxs-lookup"><span data-stu-id="b0592-151">**Response**</span></span>

<span data-ttu-id="b0592-152">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="b0592-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2018-08-02T14:55:03.7791856Z",
    "osPlatform": "Windows10",
    "version": "1709",
    "osProcessor": "x64",
    "lastIpAddress": "172.17.230.209",
    "lastExternalIpAddress": "167.220.196.71",
    "osBuild": 18209,
    "healthStatus": "Active",
    "rbacGroupId": 140,
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Medium",
    "isAadJoined": true,
    "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
    "machineTags": [ "test tag 1", "test tag 2" ]
}

```
