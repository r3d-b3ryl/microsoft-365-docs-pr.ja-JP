---
title: ユーザー関連の通知 API を取得する
description: Microsoft Defender for Endpoint を使用して、特定のユーザー ID に関連するアラートのコレクションを取得します。
keywords: apis, graph api, supported apis, get, user, related, alerts
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
ms.openlocfilehash: cff4530cfa4ecd6b0d918a9112e7be3c0f30209c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166799"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="15567-104">ユーザー関連の通知 API を取得する</span><span class="sxs-lookup"><span data-stu-id="15567-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="15567-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="15567-105">**Applies to:**</span></span>
- [<span data-ttu-id="15567-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="15567-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="15567-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15567-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="15567-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="15567-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="15567-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="15567-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="15567-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="15567-110">API description</span></span>
<span data-ttu-id="15567-111">特定のユーザー ID に関連するアラートのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="15567-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="15567-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="15567-112">Limitations</span></span>
1. <span data-ttu-id="15567-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="15567-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="15567-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="15567-114">Permissions</span></span>
<span data-ttu-id="15567-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="15567-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="15567-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="15567-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="15567-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="15567-117">Permission type</span></span> |   <span data-ttu-id="15567-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="15567-118">Permission</span></span>  |   <span data-ttu-id="15567-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="15567-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="15567-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="15567-120">Application</span></span> |   <span data-ttu-id="15567-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="15567-121">Alert.Read.All</span></span> |    <span data-ttu-id="15567-122">'すべてのアラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="15567-122">'Read all alerts'</span></span>
<span data-ttu-id="15567-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="15567-123">Application</span></span> |   <span data-ttu-id="15567-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="15567-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="15567-125">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="15567-125">'Read and write all alerts'</span></span>
<span data-ttu-id="15567-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="15567-126">Delegated (work or school account)</span></span> | <span data-ttu-id="15567-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="15567-127">Alert.Read</span></span> | <span data-ttu-id="15567-128">'アラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="15567-128">'Read alerts'</span></span>
<span data-ttu-id="15567-129">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="15567-129">Delegated (work or school account)</span></span> | <span data-ttu-id="15567-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="15567-130">Alert.ReadWrite</span></span> | <span data-ttu-id="15567-131">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="15567-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="15567-132">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="15567-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="15567-133">ユーザーには、少なくとも次の役割のアクセス許可が必要です。'データの表示' 。</span><span class="sxs-lookup"><span data-stu-id="15567-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="15567-134">詳細については、「役割の作成 [と管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="15567-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="15567-135">応答には、デバイス グループ設定に基づいて、ユーザーがアクセスできるデバイスに関連付けられたアラートだけが含まれます[](machine-groups.md)(詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="15567-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="15567-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="15567-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="15567-137">**ID は完全な UPN ではなく、ユーザー名のみです。(たとえば、/api/users/user1/alerts を使用 user1@contoso.com アラートを取得するには)**</span><span class="sxs-lookup"><span data-stu-id="15567-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="15567-138">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="15567-138">Request headers</span></span>

<span data-ttu-id="15567-139">名前</span><span class="sxs-lookup"><span data-stu-id="15567-139">Name</span></span> | <span data-ttu-id="15567-140">型</span><span class="sxs-lookup"><span data-stu-id="15567-140">Type</span></span> | <span data-ttu-id="15567-141">説明</span><span class="sxs-lookup"><span data-stu-id="15567-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="15567-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="15567-142">Authorization</span></span> | <span data-ttu-id="15567-143">String</span><span class="sxs-lookup"><span data-stu-id="15567-143">String</span></span> | <span data-ttu-id="15567-144">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="15567-144">Bearer {token}.</span></span> <span data-ttu-id="15567-145">**必須**</span><span class="sxs-lookup"><span data-stu-id="15567-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="15567-146">要求本文</span><span class="sxs-lookup"><span data-stu-id="15567-146">Request body</span></span>
<span data-ttu-id="15567-147">Empty</span><span class="sxs-lookup"><span data-stu-id="15567-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="15567-148">応答</span><span class="sxs-lookup"><span data-stu-id="15567-148">Response</span></span>
<span data-ttu-id="15567-149">成功し、ユーザーが存在する場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="15567-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="15567-150">ユーザーが存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="15567-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="15567-151">例</span><span class="sxs-lookup"><span data-stu-id="15567-151">Example</span></span>

<span data-ttu-id="15567-152">**要求**</span><span class="sxs-lookup"><span data-stu-id="15567-152">**Request**</span></span>

<span data-ttu-id="15567-153">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="15567-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
