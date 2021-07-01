---
title: ユーザー関連のコンピューター API を取得する
description: ユーザー関連コンピューターの取得 API を使用して、Microsoft Defender for Endpoint のユーザー ID に関連するデバイスのコレクションを取得する方法について説明します。
keywords: apis, graph api, サポートされている API, get, user, user related alerts
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
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229457"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="7da7c-104">ユーザー関連のコンピューター API を取得する</span><span class="sxs-lookup"><span data-stu-id="7da7c-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7da7c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7da7c-105">**Applies to:**</span></span>
- [<span data-ttu-id="7da7c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7da7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7da7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7da7c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7da7c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7da7c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7da7c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7da7c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="7da7c-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="7da7c-110">API description</span></span>
<span data-ttu-id="7da7c-111">特定のユーザー ID に関連するデバイスのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="7da7c-111">Retrieves a collection of devices related to a given user ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="7da7c-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="7da7c-112">Limitations</span></span>

<span data-ttu-id="7da7c-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="7da7c-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="7da7c-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7da7c-114">Permissions</span></span>

<span data-ttu-id="7da7c-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7da7c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7da7c-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7da7c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7da7c-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="7da7c-117">Permission type</span></span> |<span data-ttu-id="7da7c-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7da7c-118">Permission</span></span>|<span data-ttu-id="7da7c-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="7da7c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7da7c-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7da7c-120">Application</span></span> |<span data-ttu-id="7da7c-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="7da7c-121">Machine.Read.All</span></span>|<span data-ttu-id="7da7c-122">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="7da7c-122">'Read all machine profiles'</span></span>
<span data-ttu-id="7da7c-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7da7c-123">Application</span></span> |<span data-ttu-id="7da7c-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="7da7c-124">Machine.ReadWrite.All</span></span> |<span data-ttu-id="7da7c-125">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="7da7c-125">'Read and write all machine information'</span></span>
<span data-ttu-id="7da7c-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="7da7c-126">Delegated (work or school account)</span></span> | <span data-ttu-id="7da7c-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="7da7c-127">Machine.Read</span></span> | <span data-ttu-id="7da7c-128">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="7da7c-128">'Read machine information'</span></span>
<span data-ttu-id="7da7c-129">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="7da7c-129">Delegated (work or school account)</span></span> | <span data-ttu-id="7da7c-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="7da7c-130">Machine.ReadWrite</span></span> | <span data-ttu-id="7da7c-131">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="7da7c-131">'Read and write machine information'</span></span>

> [!NOTE]
> <span data-ttu-id="7da7c-132">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="7da7c-132">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="7da7c-133">ユーザーには、少なくとも次の役割のアクセス許可が必要です。'データの表示' 。</span><span class="sxs-lookup"><span data-stu-id="7da7c-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="7da7c-134">詳細については、「役割の作成 [と管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="7da7c-134">For more information, see [Create and manage roles](user-roles.md))</span></span>
> - <span data-ttu-id="7da7c-135">応答には、デバイス グループの設定に基づいて、ユーザーがアクセスできるデバイスだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7da7c-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="7da7c-136">詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="7da7c-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="7da7c-137">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="7da7c-137">HTTP request</span></span>

```http
GET /api/users/{id}/machines
```

<span data-ttu-id="7da7c-138">**ID は完全な UPN ではなく、ユーザー名のみです。(たとえば、使用するコンピューターを取得 user1@contoso.com/api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="7da7c-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="7da7c-139">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="7da7c-139">Request headers</span></span>

<span data-ttu-id="7da7c-140">名前</span><span class="sxs-lookup"><span data-stu-id="7da7c-140">Name</span></span> | <span data-ttu-id="7da7c-141">種類</span><span class="sxs-lookup"><span data-stu-id="7da7c-141">Type</span></span> | <span data-ttu-id="7da7c-142">説明</span><span class="sxs-lookup"><span data-stu-id="7da7c-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="7da7c-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="7da7c-143">Authorization</span></span> | <span data-ttu-id="7da7c-144">String</span><span class="sxs-lookup"><span data-stu-id="7da7c-144">String</span></span> | <span data-ttu-id="7da7c-145">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="7da7c-145">Bearer {token}.</span></span> <span data-ttu-id="7da7c-146">**必須**</span><span class="sxs-lookup"><span data-stu-id="7da7c-146">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7da7c-147">要求本文</span><span class="sxs-lookup"><span data-stu-id="7da7c-147">Request body</span></span>

<span data-ttu-id="7da7c-148">Empty</span><span class="sxs-lookup"><span data-stu-id="7da7c-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7da7c-149">応答</span><span class="sxs-lookup"><span data-stu-id="7da7c-149">Response</span></span>

<span data-ttu-id="7da7c-150">成功し、ユーザーが存在する場合 - 本文のコンピューター[](machine.md)エンティティの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="7da7c-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="7da7c-151">ユーザーが存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="7da7c-151">If user does not exist - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="7da7c-152">例</span><span class="sxs-lookup"><span data-stu-id="7da7c-152">Example</span></span>

### <a name="request"></a><span data-ttu-id="7da7c-153">要求</span><span class="sxs-lookup"><span data-stu-id="7da7c-153">Request</span></span>

<span data-ttu-id="7da7c-154">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="7da7c-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
