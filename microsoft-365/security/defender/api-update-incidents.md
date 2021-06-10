---
title: インシデント API の更新
description: Defender API を使用してインシデントを更新Microsoft 365する方法
keywords: update, api, Incident
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
ms.openlocfilehash: b50fe4672dd4cd721464c7414297efcc4a4921b7
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861505"
---
# <a name="update-incidents-api"></a><span data-ttu-id="a4a50-104">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="a4a50-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a4a50-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a4a50-105">**Applies to:**</span></span>

- [<span data-ttu-id="a4a50-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4a50-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="a4a50-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="a4a50-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a4a50-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="a4a50-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="a4a50-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="a4a50-109">API description</span></span>

<span data-ttu-id="a4a50-110">既存のインシデントのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="a4a50-110">Updates properties of existing incident.</span></span> <span data-ttu-id="a4a50-111">更新可能なプロパティは ```status``` ```determination``` ```classification``` 、、、、、、 ```assignedTo``` ```tags``` です ```comments``` 。</span><span class="sxs-lookup"><span data-stu-id="a4a50-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="a4a50-112">クォータ、リソース割り当て、その他の制約</span><span class="sxs-lookup"><span data-stu-id="a4a50-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="a4a50-113">調整のしきい値に達する前に、1 分あたり最大 50 回の通話または 1 時間あたり 1500 回の通話を行います。</span><span class="sxs-lookup"><span data-stu-id="a4a50-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="a4a50-114">プロパティを設定できるのは `determination` `classification` 、TruePositive に設定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="a4a50-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="a4a50-115">要求が調整されている場合は、応答コードが `429` 返されます。</span><span class="sxs-lookup"><span data-stu-id="a4a50-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="a4a50-116">応答本文には、新しい呼び出しを開始できる時刻が示されます。</span><span class="sxs-lookup"><span data-stu-id="a4a50-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="a4a50-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a4a50-117">Permissions</span></span>

<span data-ttu-id="a4a50-118">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a4a50-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a4a50-119">アクセス許可の選択方法など、詳細については[、「Access the Defender API Microsoft 365参照してください](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a50-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="a4a50-120">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="a4a50-120">Permission type</span></span> | <span data-ttu-id="a4a50-121">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a4a50-121">Permission</span></span> | <span data-ttu-id="a4a50-122">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="a4a50-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="a4a50-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a4a50-123">Application</span></span> | <span data-ttu-id="a4a50-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="a4a50-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="a4a50-125">すべてのインシデントの読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="a4a50-125">Read and write all incidents</span></span>
<span data-ttu-id="a4a50-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="a4a50-126">Delegated (work or school account)</span></span> | <span data-ttu-id="a4a50-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a4a50-127">Incident.ReadWrite</span></span> | <span data-ttu-id="a4a50-128">インシデントの読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="a4a50-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="a4a50-129">ユーザー資格情報を使用してトークンを取得する場合、ユーザーはポータルでインシデントを更新するアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a50-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="a4a50-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="a4a50-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="a4a50-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a4a50-131">Request headers</span></span>

<span data-ttu-id="a4a50-132">名前</span><span class="sxs-lookup"><span data-stu-id="a4a50-132">Name</span></span> | <span data-ttu-id="a4a50-133">種類</span><span class="sxs-lookup"><span data-stu-id="a4a50-133">Type</span></span> | <span data-ttu-id="a4a50-134">説明</span><span class="sxs-lookup"><span data-stu-id="a4a50-134">Description</span></span>
-|-|-
<span data-ttu-id="a4a50-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="a4a50-135">Authorization</span></span> | <span data-ttu-id="a4a50-136">String</span><span class="sxs-lookup"><span data-stu-id="a4a50-136">String</span></span> | <span data-ttu-id="a4a50-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="a4a50-137">Bearer {token}.</span></span> <span data-ttu-id="a4a50-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="a4a50-138">**Required**.</span></span>
<span data-ttu-id="a4a50-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a4a50-139">Content-Type</span></span> | <span data-ttu-id="a4a50-140">文字列</span><span class="sxs-lookup"><span data-stu-id="a4a50-140">String</span></span> | <span data-ttu-id="a4a50-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="a4a50-141">application/json.</span></span> <span data-ttu-id="a4a50-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="a4a50-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a4a50-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="a4a50-143">Request body</span></span>

<span data-ttu-id="a4a50-144">要求本文で、更新するフィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4a50-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="a4a50-145">要求本文に含まれていない既存のプロパティは、関連する値の変更のために再計算する必要がない限り、値を維持します。</span><span class="sxs-lookup"><span data-stu-id="a4a50-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="a4a50-146">最適なパフォーマンスを得る場合は、変更していない既存の値を省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a50-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="a4a50-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a4a50-147">Property</span></span> | <span data-ttu-id="a4a50-148">種類</span><span class="sxs-lookup"><span data-stu-id="a4a50-148">Type</span></span> | <span data-ttu-id="a4a50-149">説明</span><span class="sxs-lookup"><span data-stu-id="a4a50-149">Description</span></span>
-|-|-
<span data-ttu-id="a4a50-150">status</span><span class="sxs-lookup"><span data-stu-id="a4a50-150">status</span></span> | <span data-ttu-id="a4a50-151">列挙</span><span class="sxs-lookup"><span data-stu-id="a4a50-151">Enum</span></span> | <span data-ttu-id="a4a50-152">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4a50-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="a4a50-153">使用できる値は ```Active``` ```Resolved``` 、、、および ```Redirected``` です。</span><span class="sxs-lookup"><span data-stu-id="a4a50-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="a4a50-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a4a50-154">assignedTo</span></span> | <span data-ttu-id="a4a50-155">string</span><span class="sxs-lookup"><span data-stu-id="a4a50-155">string</span></span> | <span data-ttu-id="a4a50-156">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="a4a50-156">Owner of the incident.</span></span>
<span data-ttu-id="a4a50-157">classification</span><span class="sxs-lookup"><span data-stu-id="a4a50-157">classification</span></span> | <span data-ttu-id="a4a50-158">列挙</span><span class="sxs-lookup"><span data-stu-id="a4a50-158">Enum</span></span> | <span data-ttu-id="a4a50-159">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="a4a50-159">Specification of the incident.</span></span> <span data-ttu-id="a4a50-160">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="a4a50-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="a4a50-161">決定</span><span class="sxs-lookup"><span data-stu-id="a4a50-161">determination</span></span> | <span data-ttu-id="a4a50-162">列挙</span><span class="sxs-lookup"><span data-stu-id="a4a50-162">Enum</span></span> | <span data-ttu-id="a4a50-163">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4a50-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="a4a50-164">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="a4a50-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="a4a50-165">tags</span><span class="sxs-lookup"><span data-stu-id="a4a50-165">tags</span></span> | <span data-ttu-id="a4a50-166">string List</span><span class="sxs-lookup"><span data-stu-id="a4a50-166">string List</span></span> | <span data-ttu-id="a4a50-167">インシデント タグの一覧。</span><span class="sxs-lookup"><span data-stu-id="a4a50-167">List of Incident tags.</span></span>
<span data-ttu-id="a4a50-168">comment</span><span class="sxs-lookup"><span data-stu-id="a4a50-168">comment</span></span> | <span data-ttu-id="a4a50-169">string</span><span class="sxs-lookup"><span data-stu-id="a4a50-169">string</span></span> | <span data-ttu-id="a4a50-170">インシデントに追加するコメント。</span><span class="sxs-lookup"><span data-stu-id="a4a50-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="a4a50-171">応答</span><span class="sxs-lookup"><span data-stu-id="a4a50-171">Response</span></span>

<span data-ttu-id="a4a50-172">成功した場合、このメソッドはを返します `200 OK` 。</span><span class="sxs-lookup"><span data-stu-id="a4a50-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="a4a50-173">応答本文には、更新されたプロパティを持つインシデント エンティティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="a4a50-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="a4a50-174">指定した ID を持つインシデントが見つからなかった場合、メソッドはを返します `404 Not Found` 。</span><span class="sxs-lookup"><span data-stu-id="a4a50-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="a4a50-175">例</span><span class="sxs-lookup"><span data-stu-id="a4a50-175">Example</span></span>

<span data-ttu-id="a4a50-176">**要求**</span><span class="sxs-lookup"><span data-stu-id="a4a50-176">**Request**</span></span>

<span data-ttu-id="a4a50-177">要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a4a50-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="a4a50-178">**応答**</span><span class="sxs-lookup"><span data-stu-id="a4a50-178">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="a4a50-179">関連資料</span><span class="sxs-lookup"><span data-stu-id="a4a50-179">Related articles</span></span>

- [<span data-ttu-id="a4a50-180">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="a4a50-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a4a50-181">API の制限とライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="a4a50-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="a4a50-182">エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="a4a50-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="a4a50-183">インシデント API</span><span class="sxs-lookup"><span data-stu-id="a4a50-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="a4a50-184">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="a4a50-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="a4a50-185">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="a4a50-185">Incidents overview</span></span>](incidents-overview.md)
