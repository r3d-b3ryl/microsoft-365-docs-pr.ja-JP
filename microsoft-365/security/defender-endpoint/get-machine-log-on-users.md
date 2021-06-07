---
title: コンピューター ログオン ユーザー API の取得
description: コンピューター ログオン ユーザーの取得 API を使用して、Microsoft Defender for Endpoint のデバイスでログオンしているユーザーのコレクションを取得する方法について説明します。
keywords: apis, graph api, サポートされている api, get, device, log on, users
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
ms.openlocfilehash: 1c81d2978677b751a8085f88b5c4732fd4a5a247
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770051"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="29f45-104">コンピューター ログオン ユーザー API の取得</span><span class="sxs-lookup"><span data-stu-id="29f45-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="29f45-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="29f45-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="29f45-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="29f45-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="29f45-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="29f45-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="29f45-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="29f45-108">API description</span></span>
<span data-ttu-id="29f45-109">特定のデバイスでログオンしているユーザーのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="29f45-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="29f45-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="29f45-110">Limitations</span></span>
1. <span data-ttu-id="29f45-111">構成済みの保持期間に従って、最後に更新されたアラートに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="29f45-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="29f45-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="29f45-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="29f45-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="29f45-113">Permissions</span></span>
<span data-ttu-id="29f45-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="29f45-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="29f45-115">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="29f45-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="29f45-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="29f45-116">Permission type</span></span> |   <span data-ttu-id="29f45-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="29f45-117">Permission</span></span>  |   <span data-ttu-id="29f45-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="29f45-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="29f45-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="29f45-119">Application</span></span> |   <span data-ttu-id="29f45-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="29f45-120">User.Read.All</span></span> | <span data-ttu-id="29f45-121">'ユーザー プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="29f45-121">'Read user profiles'</span></span>
<span data-ttu-id="29f45-122">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="29f45-122">Delegated (work or school account)</span></span> | <span data-ttu-id="29f45-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="29f45-123">User.Read.All</span></span> | <span data-ttu-id="29f45-124">'ユーザー プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="29f45-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="29f45-125">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="29f45-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="29f45-126">ユーザーには、少なくとも次の役割のアクセス許可が必要です。'データの表示' 。</span><span class="sxs-lookup"><span data-stu-id="29f45-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="29f45-127">詳細については、「役割の作成 [と管理」を参照してください](user-roles.md) 。</span><span class="sxs-lookup"><span data-stu-id="29f45-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="29f45-128">応答には、デバイス グループの設定に基づいて、デバイスがユーザーに表示されている場合にのみ、ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="29f45-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="29f45-129">詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="29f45-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="29f45-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="29f45-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="29f45-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="29f45-131">Request headers</span></span>

<span data-ttu-id="29f45-132">名前</span><span class="sxs-lookup"><span data-stu-id="29f45-132">Name</span></span> | <span data-ttu-id="29f45-133">種類</span><span class="sxs-lookup"><span data-stu-id="29f45-133">Type</span></span> | <span data-ttu-id="29f45-134">説明</span><span class="sxs-lookup"><span data-stu-id="29f45-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="29f45-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="29f45-135">Authorization</span></span> | <span data-ttu-id="29f45-136">String</span><span class="sxs-lookup"><span data-stu-id="29f45-136">String</span></span> | <span data-ttu-id="29f45-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="29f45-137">Bearer {token}.</span></span> <span data-ttu-id="29f45-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="29f45-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="29f45-139">要求本文</span><span class="sxs-lookup"><span data-stu-id="29f45-139">Request body</span></span>
<span data-ttu-id="29f45-140">Empty</span><span class="sxs-lookup"><span data-stu-id="29f45-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="29f45-141">応答</span><span class="sxs-lookup"><span data-stu-id="29f45-141">Response</span></span>
<span data-ttu-id="29f45-142">成功し、デバイスが存在する場合 - 本文のユーザー[](user.md)エンティティの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="29f45-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="29f45-143">デバイスが見つからなかった場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="29f45-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="29f45-144">例</span><span class="sxs-lookup"><span data-stu-id="29f45-144">Example</span></span>

<span data-ttu-id="29f45-145">**要求**</span><span class="sxs-lookup"><span data-stu-id="29f45-145">**Request**</span></span>

<span data-ttu-id="29f45-146">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="29f45-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="29f45-147">**応答**</span><span class="sxs-lookup"><span data-stu-id="29f45-147">**Response**</span></span>

<span data-ttu-id="29f45-148">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="29f45-148">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
