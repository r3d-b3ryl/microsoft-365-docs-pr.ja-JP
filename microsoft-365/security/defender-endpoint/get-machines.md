---
title: マシン API の一覧
description: リスト コンピューター API を使用して、Microsoft Defender ATP クラウドと通信したコンピューターのコレクションを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, devices
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
ms.openlocfilehash: 23997cf4997ccfea8ee89a9b9ec5cc991dfa1ed0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200379"
---
# <a name="list-machines-api"></a><span data-ttu-id="b3c16-104">マシン API の一覧</span><span class="sxs-lookup"><span data-stu-id="b3c16-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b3c16-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b3c16-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b3c16-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b3c16-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3c16-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b3c16-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b3c16-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="b3c16-108">API description</span></span>
<span data-ttu-id="b3c16-109">Microsoft Defender for Endpoint クラウド [と](machine.md) 通信したコンピューターのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3c16-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="b3c16-110">[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="b3c16-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="b3c16-111">OData のクエリは `$filter` 、で `computerDnsName` `lastSeen` `healthStatus` `osPlatform` `riskScore` サポートされています `rbacGroupId` 。</span><span class="sxs-lookup"><span data-stu-id="b3c16-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="b3c16-112">Defender for Endpoint を使用した [OData クエリの例を参照してください。](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="b3c16-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="b3c16-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="b3c16-113">Limitations</span></span>
1. <span data-ttu-id="b3c16-114">構成済みの保持期間に従って最後に表示されたデバイスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="b3c16-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="b3c16-115">最大ページ サイズは 10,000 です。</span><span class="sxs-lookup"><span data-stu-id="b3c16-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="b3c16-116">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="b3c16-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="b3c16-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b3c16-117">Permissions</span></span>

<span data-ttu-id="b3c16-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="b3c16-118">Permission type</span></span> |   <span data-ttu-id="b3c16-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b3c16-119">Permission</span></span>  |   <span data-ttu-id="b3c16-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="b3c16-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b3c16-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b3c16-121">Application</span></span> |   <span data-ttu-id="b3c16-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="b3c16-122">Machine.Read.All</span></span> |  <span data-ttu-id="b3c16-123">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="b3c16-123">'Read all machine profiles'</span></span>
<span data-ttu-id="b3c16-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b3c16-124">Application</span></span> |   <span data-ttu-id="b3c16-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b3c16-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="b3c16-126">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="b3c16-126">'Read and write all machine information'</span></span>
<span data-ttu-id="b3c16-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b3c16-127">Delegated (work or school account)</span></span> | <span data-ttu-id="b3c16-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="b3c16-128">Machine.Read</span></span> | <span data-ttu-id="b3c16-129">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="b3c16-129">'Read machine information'</span></span>
<span data-ttu-id="b3c16-130">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b3c16-130">Delegated (work or school account)</span></span> | <span data-ttu-id="b3c16-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b3c16-131">Machine.ReadWrite</span></span> | <span data-ttu-id="b3c16-132">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="b3c16-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="b3c16-133">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="b3c16-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b3c16-134">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="b3c16-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b3c16-135">応答には、デバイス グループの設定に基づいて、ユーザーがアクセスできるデバイスだけが含まれます[](machine-groups.md)(詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="b3c16-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b3c16-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b3c16-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="b3c16-137">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b3c16-137">Request headers</span></span>

<span data-ttu-id="b3c16-138">名前</span><span class="sxs-lookup"><span data-stu-id="b3c16-138">Name</span></span> | <span data-ttu-id="b3c16-139">種類</span><span class="sxs-lookup"><span data-stu-id="b3c16-139">Type</span></span> | <span data-ttu-id="b3c16-140">説明</span><span class="sxs-lookup"><span data-stu-id="b3c16-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="b3c16-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="b3c16-141">Authorization</span></span> | <span data-ttu-id="b3c16-142">文字列</span><span class="sxs-lookup"><span data-stu-id="b3c16-142">String</span></span> | <span data-ttu-id="b3c16-143">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="b3c16-143">Bearer {token}.</span></span> <span data-ttu-id="b3c16-144">**必須**</span><span class="sxs-lookup"><span data-stu-id="b3c16-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b3c16-145">要求本文</span><span class="sxs-lookup"><span data-stu-id="b3c16-145">Request body</span></span>
<span data-ttu-id="b3c16-146">Empty</span><span class="sxs-lookup"><span data-stu-id="b3c16-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b3c16-147">応答</span><span class="sxs-lookup"><span data-stu-id="b3c16-147">Response</span></span>
<span data-ttu-id="b3c16-148">成功し、コンピューターが存在する場合 - 本文のコンピューター[](machine.md)エンティティの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="b3c16-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="b3c16-149">最新のコンピューターがない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="b3c16-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b3c16-150">例</span><span class="sxs-lookup"><span data-stu-id="b3c16-150">Example</span></span>

<span data-ttu-id="b3c16-151">**要求**</span><span class="sxs-lookup"><span data-stu-id="b3c16-151">**Request**</span></span>

<span data-ttu-id="b3c16-152">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="b3c16-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="b3c16-153">**応答**</span><span class="sxs-lookup"><span data-stu-id="b3c16-153">**Response**</span></span>

<span data-ttu-id="b3c16-154">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="b3c16-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
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
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b3c16-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3c16-155">Related topics</span></span>
- [<span data-ttu-id="b3c16-156">エンドポイント用 Microsoft Defender を使用した OData クエリ</span><span class="sxs-lookup"><span data-stu-id="b3c16-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
