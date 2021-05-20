---
title: インシデント API の更新
description: Microsoft 365 Defender API を使用してインシデントを更新する方法を確認する
keywords: 更新,API,インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571783"
---
# <a name="update-incident-api"></a><span data-ttu-id="402d0-104">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="402d0-104">Update incident API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="402d0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="402d0-105">**Applies to:**</span></span>

- <span data-ttu-id="402d0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="402d0-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="402d0-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="402d0-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="402d0-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="402d0-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="402d0-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="402d0-109">API description</span></span>

<span data-ttu-id="402d0-110">既存のインシデントのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="402d0-110">Updates properties of existing incident.</span></span> <span data-ttu-id="402d0-111">更新可能プロパティは、 ```status``` ```determination``` 、 、 、 、 、 、 、 ```classification``` ```assignedTo``` ```tags``` ```comments``` です。</span><span class="sxs-lookup"><span data-stu-id="402d0-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="402d0-112">クォータ、リソース割り当て、およびその他の制約</span><span class="sxs-lookup"><span data-stu-id="402d0-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="402d0-113">調整しきい値に達する前に、1 分間に最大 50 回、または 1 時間あたり 1500 件のコールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="402d0-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="402d0-114">プロパティを設定できるのは `determination` `classification` 、TruePositive に設定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="402d0-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="402d0-115">要求が調整されると、応答コードが返されます `429` 。</span><span class="sxs-lookup"><span data-stu-id="402d0-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="402d0-116">応答本文は、新しい呼び出しを開始できる時間を示します。</span><span class="sxs-lookup"><span data-stu-id="402d0-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="402d0-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="402d0-117">Permissions</span></span>

<span data-ttu-id="402d0-118">この API を呼び出すためには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="402d0-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="402d0-119">アクセス許可の選択方法を含む詳細については[、「Microsoft 365 Defender API へのアクセス](api-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="402d0-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="402d0-120">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="402d0-120">Permission type</span></span> | <span data-ttu-id="402d0-121">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="402d0-121">Permission</span></span> | <span data-ttu-id="402d0-122">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="402d0-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="402d0-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="402d0-123">Application</span></span> | <span data-ttu-id="402d0-124">インシデント.読み書き.すべて</span><span class="sxs-lookup"><span data-stu-id="402d0-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="402d0-125">すべてのインシデントの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="402d0-125">Read and write all incidents</span></span>
<span data-ttu-id="402d0-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="402d0-126">Delegated (work or school account)</span></span> | <span data-ttu-id="402d0-127">インシデント.読み取り書き込み</span><span class="sxs-lookup"><span data-stu-id="402d0-127">Incident.ReadWrite</span></span> | <span data-ttu-id="402d0-128">インシデントの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="402d0-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="402d0-129">ユーザーの資格情報を使用してトークンを取得する場合、ユーザーはポータルでインシデントを更新する権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="402d0-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="402d0-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="402d0-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="402d0-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="402d0-131">Request headers</span></span>

<span data-ttu-id="402d0-132">名前</span><span class="sxs-lookup"><span data-stu-id="402d0-132">Name</span></span> | <span data-ttu-id="402d0-133">型</span><span class="sxs-lookup"><span data-stu-id="402d0-133">Type</span></span> | <span data-ttu-id="402d0-134">説明</span><span class="sxs-lookup"><span data-stu-id="402d0-134">Description</span></span>
-|-|-
<span data-ttu-id="402d0-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="402d0-135">Authorization</span></span> | <span data-ttu-id="402d0-136">String</span><span class="sxs-lookup"><span data-stu-id="402d0-136">String</span></span> | <span data-ttu-id="402d0-137">ベアラー {トークン}</span><span class="sxs-lookup"><span data-stu-id="402d0-137">Bearer {token}.</span></span> <span data-ttu-id="402d0-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="402d0-138">**Required**.</span></span>
<span data-ttu-id="402d0-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="402d0-139">Content-Type</span></span> | <span data-ttu-id="402d0-140">文字列</span><span class="sxs-lookup"><span data-stu-id="402d0-140">String</span></span> | <span data-ttu-id="402d0-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="402d0-141">application/json.</span></span> <span data-ttu-id="402d0-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="402d0-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="402d0-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="402d0-143">Request body</span></span>

<span data-ttu-id="402d0-144">要求本文で、更新するフィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="402d0-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="402d0-145">関連する値の変更によって再計算する必要がない限り、要求本文に含まれていない既存のプロパティは値を保持します。</span><span class="sxs-lookup"><span data-stu-id="402d0-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="402d0-146">最適なパフォーマンスを得る場合は、変更されていない既存の値を省略してください。</span><span class="sxs-lookup"><span data-stu-id="402d0-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="402d0-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="402d0-147">Property</span></span> | <span data-ttu-id="402d0-148">型</span><span class="sxs-lookup"><span data-stu-id="402d0-148">Type</span></span> | <span data-ttu-id="402d0-149">説明</span><span class="sxs-lookup"><span data-stu-id="402d0-149">Description</span></span>
-|-|-
<span data-ttu-id="402d0-150">status</span><span class="sxs-lookup"><span data-stu-id="402d0-150">status</span></span> | <span data-ttu-id="402d0-151">列挙</span><span class="sxs-lookup"><span data-stu-id="402d0-151">Enum</span></span> | <span data-ttu-id="402d0-152">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="402d0-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="402d0-153">使用できる値は ```Active``` 、 ```Resolved``` 、 、 、 です ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="402d0-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="402d0-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="402d0-154">assignedTo</span></span> | <span data-ttu-id="402d0-155">string</span><span class="sxs-lookup"><span data-stu-id="402d0-155">string</span></span> | <span data-ttu-id="402d0-156">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="402d0-156">Owner of the incident.</span></span>
<span data-ttu-id="402d0-157">classification</span><span class="sxs-lookup"><span data-stu-id="402d0-157">classification</span></span> | <span data-ttu-id="402d0-158">列挙</span><span class="sxs-lookup"><span data-stu-id="402d0-158">Enum</span></span> | <span data-ttu-id="402d0-159">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="402d0-159">Specification of the incident.</span></span> <span data-ttu-id="402d0-160">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="402d0-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="402d0-161">決定</span><span class="sxs-lookup"><span data-stu-id="402d0-161">determination</span></span> | <span data-ttu-id="402d0-162">列挙</span><span class="sxs-lookup"><span data-stu-id="402d0-162">Enum</span></span> | <span data-ttu-id="402d0-163">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="402d0-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="402d0-164">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="402d0-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="402d0-165">tags</span><span class="sxs-lookup"><span data-stu-id="402d0-165">tags</span></span> | <span data-ttu-id="402d0-166">文字列リスト</span><span class="sxs-lookup"><span data-stu-id="402d0-166">string List</span></span> | <span data-ttu-id="402d0-167">インシデント タグのリスト。</span><span class="sxs-lookup"><span data-stu-id="402d0-167">List of Incident tags.</span></span>
<span data-ttu-id="402d0-168">comment</span><span class="sxs-lookup"><span data-stu-id="402d0-168">comment</span></span> | <span data-ttu-id="402d0-169">string</span><span class="sxs-lookup"><span data-stu-id="402d0-169">string</span></span> | <span data-ttu-id="402d0-170">インシデントに追加するコメント。</span><span class="sxs-lookup"><span data-stu-id="402d0-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="402d0-171">応答</span><span class="sxs-lookup"><span data-stu-id="402d0-171">Response</span></span>

<span data-ttu-id="402d0-172">成功した場合、このメソッドは `200 OK` を返します。</span><span class="sxs-lookup"><span data-stu-id="402d0-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="402d0-173">応答本文には、更新されたプロパティを持つインシデント エンティティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="402d0-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="402d0-174">指定された ID のインシデントが見つからなかった場合、メソッドは `404 Not Found` を返します。</span><span class="sxs-lookup"><span data-stu-id="402d0-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="402d0-175">例</span><span class="sxs-lookup"><span data-stu-id="402d0-175">Example</span></span>

<span data-ttu-id="402d0-176">**要求**</span><span class="sxs-lookup"><span data-stu-id="402d0-176">**Request**</span></span>

<span data-ttu-id="402d0-177">要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="402d0-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="402d0-178">**応答**</span><span class="sxs-lookup"><span data-stu-id="402d0-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="402d0-179">関連記事</span><span class="sxs-lookup"><span data-stu-id="402d0-179">Related articles</span></span>

- [<span data-ttu-id="402d0-180">Microsoft 365ディフェンダー API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="402d0-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="402d0-181">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="402d0-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="402d0-182">エラー コードを理解する</span><span class="sxs-lookup"><span data-stu-id="402d0-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="402d0-183">インシデント API</span><span class="sxs-lookup"><span data-stu-id="402d0-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="402d0-184">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="402d0-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="402d0-185">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="402d0-185">Incidents overview</span></span>](incidents-overview.md)
