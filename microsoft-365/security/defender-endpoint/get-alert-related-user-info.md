---
title: アラート関連のユーザー情報を取得する
description: Get alert related user information API を使用して、Microsoft Defender for Endpoint の特定のアラートに関連するユーザーを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, alert, information, related, user
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
ms.openlocfilehash: aee3c6fb381341c6823fbcb6766c0b761cb3413d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166983"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="3db06-104">アラート関連のユーザー情報 API を取得する</span><span class="sxs-lookup"><span data-stu-id="3db06-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3db06-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3db06-105">**Applies to:**</span></span>
- [<span data-ttu-id="3db06-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3db06-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3db06-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3db06-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="3db06-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="3db06-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3db06-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="3db06-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3db06-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="3db06-110">API description</span></span>
<span data-ttu-id="3db06-111">特定のアラートに関連するユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="3db06-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="3db06-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="3db06-112">Limitations</span></span>
1. <span data-ttu-id="3db06-113">構成済みの保持期間に従って、最後に更新されたアラートに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3db06-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3db06-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="3db06-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3db06-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3db06-115">Permissions</span></span>
<span data-ttu-id="3db06-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="3db06-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3db06-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3db06-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3db06-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="3db06-118">Permission type</span></span> |   <span data-ttu-id="3db06-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3db06-119">Permission</span></span>  |   <span data-ttu-id="3db06-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="3db06-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3db06-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3db06-121">Application</span></span> |   <span data-ttu-id="3db06-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="3db06-122">User.Read.All</span></span> | <span data-ttu-id="3db06-123">'ユーザー プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="3db06-123">'Read user profiles'</span></span>
<span data-ttu-id="3db06-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="3db06-124">Delegated (work or school account)</span></span> | <span data-ttu-id="3db06-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="3db06-125">User.Read.All</span></span> | <span data-ttu-id="3db06-126">'ユーザー プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="3db06-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="3db06-127">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="3db06-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3db06-128">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="3db06-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3db06-129">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="3db06-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3db06-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3db06-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="3db06-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3db06-131">Request headers</span></span>

<span data-ttu-id="3db06-132">名前</span><span class="sxs-lookup"><span data-stu-id="3db06-132">Name</span></span> | <span data-ttu-id="3db06-133">種類</span><span class="sxs-lookup"><span data-stu-id="3db06-133">Type</span></span> | <span data-ttu-id="3db06-134">説明</span><span class="sxs-lookup"><span data-stu-id="3db06-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="3db06-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="3db06-135">Authorization</span></span> | <span data-ttu-id="3db06-136">文字列</span><span class="sxs-lookup"><span data-stu-id="3db06-136">String</span></span> | <span data-ttu-id="3db06-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="3db06-137">Bearer {token}.</span></span> <span data-ttu-id="3db06-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="3db06-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3db06-139">要求本文</span><span class="sxs-lookup"><span data-stu-id="3db06-139">Request body</span></span>
<span data-ttu-id="3db06-140">Empty</span><span class="sxs-lookup"><span data-stu-id="3db06-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3db06-141">応答</span><span class="sxs-lookup"><span data-stu-id="3db06-141">Response</span></span>
<span data-ttu-id="3db06-142">成功し、警告し、ユーザーが存在する場合 - 200 OK を本文のユーザーとします。</span><span class="sxs-lookup"><span data-stu-id="3db06-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="3db06-143">アラートまたはユーザーが見つからない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="3db06-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3db06-144">例</span><span class="sxs-lookup"><span data-stu-id="3db06-144">Example</span></span>

<span data-ttu-id="3db06-145">**要求**</span><span class="sxs-lookup"><span data-stu-id="3db06-145">**Request**</span></span>

<span data-ttu-id="3db06-146">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="3db06-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="3db06-147">**応答**</span><span class="sxs-lookup"><span data-stu-id="3db06-147">**Response**</span></span>

<span data-ttu-id="3db06-148">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="3db06-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```
