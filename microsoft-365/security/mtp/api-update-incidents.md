---
title: インシデント API の更新
description: Microsoft 365 Defender API を使用してインシデントを更新する方法について説明します。
keywords: 更新, api, インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719406"
---
# <a name="update-incidents-api"></a><span data-ttu-id="3940e-104">インシデント更新 API</span><span class="sxs-lookup"><span data-stu-id="3940e-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3940e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3940e-105">**Applies to:**</span></span>

- <span data-ttu-id="3940e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3940e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3940e-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="3940e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3940e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3940e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="3940e-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="3940e-109">API description</span></span>

<span data-ttu-id="3940e-110">既存のインシデントのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="3940e-110">Updates properties of existing incident.</span></span> <span data-ttu-id="3940e-111">更新可能なプロパティは、次 ```status``` ```determination``` ```classification``` ```assignedTo``` のとおりです ```tags``` 。</span><span class="sxs-lookup"><span data-stu-id="3940e-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="3940e-112">クォータ、リソース割り当て、その他の制約</span><span class="sxs-lookup"><span data-stu-id="3940e-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="3940e-113">調整しきい値に達する前に、1 分あたり最大 50 回、または 1 時間あたり 1500 回の通話を行います。</span><span class="sxs-lookup"><span data-stu-id="3940e-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="3940e-114">このプロパティは `determination` `classification` 、TruePositive に設定されている場合にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="3940e-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="3940e-115">要求が調整されている場合は、応答コードを `429` 返します。</span><span class="sxs-lookup"><span data-stu-id="3940e-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="3940e-116">応答本文には、新しい呼び出しを開始できる時刻が示されます。</span><span class="sxs-lookup"><span data-stu-id="3940e-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="3940e-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3940e-117">Permissions</span></span>

<span data-ttu-id="3940e-118">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="3940e-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3940e-119">アクセス許可の選択方法など、詳細については [、「Microsoft 365 Defender API](api-access.md)へのアクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3940e-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="3940e-120">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="3940e-120">Permission type</span></span> | <span data-ttu-id="3940e-121">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3940e-121">Permission</span></span> | <span data-ttu-id="3940e-122">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="3940e-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="3940e-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3940e-123">Application</span></span> | <span data-ttu-id="3940e-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3940e-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="3940e-125">すべてのインシデントの読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="3940e-125">Read and write all incidents</span></span>
<span data-ttu-id="3940e-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="3940e-126">Delegated (work or school account)</span></span> | <span data-ttu-id="3940e-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3940e-127">Incident.ReadWrite</span></span> | <span data-ttu-id="3940e-128">インシデントの読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="3940e-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="3940e-129">ユーザー資格情報を使用してトークンを取得する場合、ユーザーはポータルでインシデントを更新するアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3940e-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="3940e-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3940e-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="3940e-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3940e-131">Request headers</span></span>

<span data-ttu-id="3940e-132">名前</span><span class="sxs-lookup"><span data-stu-id="3940e-132">Name</span></span> | <span data-ttu-id="3940e-133">型</span><span class="sxs-lookup"><span data-stu-id="3940e-133">Type</span></span> | <span data-ttu-id="3940e-134">説明</span><span class="sxs-lookup"><span data-stu-id="3940e-134">Description</span></span>
-|-|-
<span data-ttu-id="3940e-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="3940e-135">Authorization</span></span> | <span data-ttu-id="3940e-136">String</span><span class="sxs-lookup"><span data-stu-id="3940e-136">String</span></span> | <span data-ttu-id="3940e-137">ベアラー {トークン}。</span><span class="sxs-lookup"><span data-stu-id="3940e-137">Bearer {token}.</span></span> <span data-ttu-id="3940e-138">**必須**。</span><span class="sxs-lookup"><span data-stu-id="3940e-138">**Required**.</span></span>
<span data-ttu-id="3940e-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3940e-139">Content-Type</span></span> | <span data-ttu-id="3940e-140">文字列</span><span class="sxs-lookup"><span data-stu-id="3940e-140">String</span></span> | <span data-ttu-id="3940e-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="3940e-141">application/json.</span></span> <span data-ttu-id="3940e-142">**必須**。</span><span class="sxs-lookup"><span data-stu-id="3940e-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3940e-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="3940e-143">Request body</span></span>

<span data-ttu-id="3940e-144">要求本文で、更新するフィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3940e-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="3940e-145">要求本文に含まれていない既存のプロパティは、関連する値の変更のために再計算する必要がない限り、値を保持します。</span><span class="sxs-lookup"><span data-stu-id="3940e-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="3940e-146">最適なパフォーマンスを得る場合は、変更していない既存の値を省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3940e-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="3940e-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3940e-147">Property</span></span> | <span data-ttu-id="3940e-148">型</span><span class="sxs-lookup"><span data-stu-id="3940e-148">Type</span></span> | <span data-ttu-id="3940e-149">説明</span><span class="sxs-lookup"><span data-stu-id="3940e-149">Description</span></span>
-|-|-
<span data-ttu-id="3940e-150">status</span><span class="sxs-lookup"><span data-stu-id="3940e-150">status</span></span> | <span data-ttu-id="3940e-151">列挙</span><span class="sxs-lookup"><span data-stu-id="3940e-151">Enum</span></span> | <span data-ttu-id="3940e-152">通知の現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="3940e-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="3940e-153">使用できる値は ```Active``` 、次 ```Resolved``` のとおりです ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="3940e-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="3940e-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="3940e-154">assignedTo</span></span> | <span data-ttu-id="3940e-155">string</span><span class="sxs-lookup"><span data-stu-id="3940e-155">string</span></span> | <span data-ttu-id="3940e-156">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="3940e-156">Owner of the incident.</span></span>
<span data-ttu-id="3940e-157">classification</span><span class="sxs-lookup"><span data-stu-id="3940e-157">classification</span></span> | <span data-ttu-id="3940e-158">列挙</span><span class="sxs-lookup"><span data-stu-id="3940e-158">Enum</span></span> | <span data-ttu-id="3940e-159">アラートの仕様。</span><span class="sxs-lookup"><span data-stu-id="3940e-159">Specification of the alert.</span></span> <span data-ttu-id="3940e-160">可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="3940e-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="3940e-161">判断</span><span class="sxs-lookup"><span data-stu-id="3940e-161">determination</span></span> | <span data-ttu-id="3940e-162">列挙</span><span class="sxs-lookup"><span data-stu-id="3940e-162">Enum</span></span> | <span data-ttu-id="3940e-163">通知の判定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3940e-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="3940e-164">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="3940e-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="3940e-165">tags</span><span class="sxs-lookup"><span data-stu-id="3940e-165">tags</span></span> | <span data-ttu-id="3940e-166">string List</span><span class="sxs-lookup"><span data-stu-id="3940e-166">string List</span></span> | <span data-ttu-id="3940e-167">インシデント タグのリスト。</span><span class="sxs-lookup"><span data-stu-id="3940e-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="3940e-168">応答</span><span class="sxs-lookup"><span data-stu-id="3940e-168">Response</span></span>

<span data-ttu-id="3940e-169">成功した場合、このメソッドは返します `200 OK` 。</span><span class="sxs-lookup"><span data-stu-id="3940e-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="3940e-170">応答本文には、更新されたプロパティを持つインシデント エンティティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="3940e-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="3940e-171">指定された ID のインシデントが見つからなかった場合、メソッドは返します `404 Not Found` 。</span><span class="sxs-lookup"><span data-stu-id="3940e-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="3940e-172">例</span><span class="sxs-lookup"><span data-stu-id="3940e-172">Example</span></span>

<span data-ttu-id="3940e-173">**要求**</span><span class="sxs-lookup"><span data-stu-id="3940e-173">**Request**</span></span>

<span data-ttu-id="3940e-174">要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3940e-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="3940e-175">**応答**</span><span class="sxs-lookup"><span data-stu-id="3940e-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="3940e-176">関連記事</span><span class="sxs-lookup"><span data-stu-id="3940e-176">Related articles</span></span>

- [<span data-ttu-id="3940e-177">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="3940e-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="3940e-178">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="3940e-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="3940e-179">エラー コードを理解する</span><span class="sxs-lookup"><span data-stu-id="3940e-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="3940e-180">インシデント API</span><span class="sxs-lookup"><span data-stu-id="3940e-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="3940e-181">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="3940e-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="3940e-182">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="3940e-182">Incidents overview</span></span>](incidents-overview.md)
