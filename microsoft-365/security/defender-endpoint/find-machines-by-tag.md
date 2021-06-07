---
title: タグ API でデバイスを検索する
description: specifc タグを含むすべてのデバイスを検索する
keywords: apis, サポートされている api, get, device, find, find device, by tag, tag
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
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771167"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="5bb86-104">タグ API でデバイスを検索する</span><span class="sxs-lookup"><span data-stu-id="5bb86-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5bb86-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5bb86-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5bb86-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="5bb86-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5bb86-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="5bb86-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5bb86-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="5bb86-108">API description</span></span>
<span data-ttu-id="5bb86-109">タグ[でコンピューターを](machine.md)[検索します](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="5bb86-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="5bb86-110">```startswith``` クエリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5bb86-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="5bb86-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="5bb86-111">Limitations</span></span>
1. <span data-ttu-id="5bb86-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="5bb86-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5bb86-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5bb86-113">Permissions</span></span>
<span data-ttu-id="5bb86-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="5bb86-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5bb86-115">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5bb86-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5bb86-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="5bb86-116">Permission type</span></span> |   <span data-ttu-id="5bb86-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5bb86-117">Permission</span></span>  |   <span data-ttu-id="5bb86-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="5bb86-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5bb86-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5bb86-119">Application</span></span> |   <span data-ttu-id="5bb86-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="5bb86-120">Machine.Read.All</span></span> |  <span data-ttu-id="5bb86-121">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="5bb86-121">'Read all machine profiles'</span></span>
<span data-ttu-id="5bb86-122">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5bb86-122">Application</span></span> |   <span data-ttu-id="5bb86-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5bb86-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="5bb86-124">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="5bb86-124">'Read and write all machine information'</span></span>
<span data-ttu-id="5bb86-125">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="5bb86-125">Delegated (work or school account)</span></span> | <span data-ttu-id="5bb86-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="5bb86-126">Machine.Read</span></span> | <span data-ttu-id="5bb86-127">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="5bb86-127">'Read machine information'</span></span>
<span data-ttu-id="5bb86-128">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="5bb86-128">Delegated (work or school account)</span></span> | <span data-ttu-id="5bb86-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5bb86-129">Machine.ReadWrite</span></span> | <span data-ttu-id="5bb86-130">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="5bb86-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="5bb86-131">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="5bb86-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="5bb86-132">応答には、ユーザーがデバイス グループ設定に基づいてアクセスできるデバイスだけが含まれます (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="5bb86-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="5bb86-133">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="5bb86-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="5bb86-134">応答には、ユーザーがデバイス グループ設定に基づいてアクセスできるデバイスだけが含まれます (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="5bb86-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5bb86-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="5bb86-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="5bb86-136">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="5bb86-136">Request headers</span></span>

<span data-ttu-id="5bb86-137">名前</span><span class="sxs-lookup"><span data-stu-id="5bb86-137">Name</span></span> | <span data-ttu-id="5bb86-138">種類</span><span class="sxs-lookup"><span data-stu-id="5bb86-138">Type</span></span> | <span data-ttu-id="5bb86-139">説明</span><span class="sxs-lookup"><span data-stu-id="5bb86-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="5bb86-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="5bb86-140">Authorization</span></span> | <span data-ttu-id="5bb86-141">String</span><span class="sxs-lookup"><span data-stu-id="5bb86-141">String</span></span> | <span data-ttu-id="5bb86-142">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="5bb86-142">Bearer {token}.</span></span> <span data-ttu-id="5bb86-143">**必須**</span><span class="sxs-lookup"><span data-stu-id="5bb86-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="5bb86-144">要求 URI パラメーター</span><span class="sxs-lookup"><span data-stu-id="5bb86-144">Request URI parameters</span></span>

<span data-ttu-id="5bb86-145">名前</span><span class="sxs-lookup"><span data-stu-id="5bb86-145">Name</span></span> | <span data-ttu-id="5bb86-146">種類</span><span class="sxs-lookup"><span data-stu-id="5bb86-146">Type</span></span> | <span data-ttu-id="5bb86-147">説明</span><span class="sxs-lookup"><span data-stu-id="5bb86-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="5bb86-148">tag</span><span class="sxs-lookup"><span data-stu-id="5bb86-148">tag</span></span> | <span data-ttu-id="5bb86-149">String</span><span class="sxs-lookup"><span data-stu-id="5bb86-149">String</span></span> | <span data-ttu-id="5bb86-150">タグ名。</span><span class="sxs-lookup"><span data-stu-id="5bb86-150">The tag name.</span></span> <span data-ttu-id="5bb86-151">**必須**</span><span class="sxs-lookup"><span data-stu-id="5bb86-151">**Required**.</span></span>
<span data-ttu-id="5bb86-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="5bb86-152">useStartsWithFilter</span></span> | <span data-ttu-id="5bb86-153">Boolean</span><span class="sxs-lookup"><span data-stu-id="5bb86-153">Boolean</span></span> | <span data-ttu-id="5bb86-154">true に設定すると、クエリ内の指定されたタグで始まるタグ名を持つすべてのデバイスが検索されます。</span><span class="sxs-lookup"><span data-stu-id="5bb86-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="5bb86-155">既定は false です。</span><span class="sxs-lookup"><span data-stu-id="5bb86-155">Defaults to false.</span></span> <span data-ttu-id="5bb86-156">**オプション**。</span><span class="sxs-lookup"><span data-stu-id="5bb86-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5bb86-157">要求本文</span><span class="sxs-lookup"><span data-stu-id="5bb86-157">Request body</span></span>
<span data-ttu-id="5bb86-158">Empty</span><span class="sxs-lookup"><span data-stu-id="5bb86-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5bb86-159">応答</span><span class="sxs-lookup"><span data-stu-id="5bb86-159">Response</span></span>
<span data-ttu-id="5bb86-160">成功した場合 - 応答本文のコンピューターの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="5bb86-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="5bb86-161">例</span><span class="sxs-lookup"><span data-stu-id="5bb86-161">Example</span></span>

<span data-ttu-id="5bb86-162">**要求**</span><span class="sxs-lookup"><span data-stu-id="5bb86-162">**Request**</span></span>

<span data-ttu-id="5bb86-163">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="5bb86-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```