---
title: インシデント API の更新
description: Microsoft 脅威保護 API を使用してインシデントを更新する方法について説明します。
keywords: update、api、incident
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
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650394"
---
# <a name="update-incidents-api"></a><span data-ttu-id="e57ba-104">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="e57ba-104">Update incidents API</span></span>

<span data-ttu-id="e57ba-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e57ba-105">**Applies to:**</span></span>
- <span data-ttu-id="e57ba-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e57ba-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="e57ba-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="e57ba-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e57ba-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e57ba-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="e57ba-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="e57ba-109">API description</span></span>
<span data-ttu-id="e57ba-110">既存のインシデントのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="e57ba-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="e57ba-111">更新可能なプロパティは、、、 ```status``` ```determination``` ```classification``` 、 ```assignedTo``` ```tags``` です。</span><span class="sxs-lookup"><span data-stu-id="e57ba-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="e57ba-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="e57ba-112">Limitations</span></span>
1. <span data-ttu-id="e57ba-113">この API の速度制限は、1分あたり50通話、1時間あたり1500通話です。</span><span class="sxs-lookup"><span data-stu-id="e57ba-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="e57ba-114">```determination```分類が TruePositive に設定されている場合にのみ、を設定できます。</span><span class="sxs-lookup"><span data-stu-id="e57ba-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="e57ba-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e57ba-115">Permissions</span></span>
<span data-ttu-id="e57ba-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e57ba-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e57ba-117">アクセス許可の選択方法を含む詳細については、「 [Microsoft の脅威保護 api にアクセス](api-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e57ba-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="e57ba-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="e57ba-118">Permission type</span></span> |   <span data-ttu-id="e57ba-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e57ba-119">Permission</span></span>  |   <span data-ttu-id="e57ba-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="e57ba-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e57ba-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e57ba-121">Application</span></span> |   <span data-ttu-id="e57ba-122">インシデント。すべて</span><span class="sxs-lookup"><span data-stu-id="e57ba-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="e57ba-123">' すべてのインシデントの読み取りと書き込み '</span><span class="sxs-lookup"><span data-stu-id="e57ba-123">'Read and write all incidents'</span></span>
<span data-ttu-id="e57ba-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="e57ba-124">Delegated (work or school account)</span></span> | <span data-ttu-id="e57ba-125">障害/書き込み</span><span class="sxs-lookup"><span data-stu-id="e57ba-125">Incident.ReadWrite</span></span> | <span data-ttu-id="e57ba-126">' 読み取りおよび書き込みのインシデント '</span><span class="sxs-lookup"><span data-stu-id="e57ba-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="e57ba-127">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="e57ba-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e57ba-128">ユーザーはポータルでインシデントを更新する権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e57ba-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="e57ba-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="e57ba-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="e57ba-130">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e57ba-130">Request headers</span></span>

<span data-ttu-id="e57ba-131">名前</span><span class="sxs-lookup"><span data-stu-id="e57ba-131">Name</span></span> | <span data-ttu-id="e57ba-132">種類</span><span class="sxs-lookup"><span data-stu-id="e57ba-132">Type</span></span> | <span data-ttu-id="e57ba-133">説明</span><span class="sxs-lookup"><span data-stu-id="e57ba-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="e57ba-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="e57ba-134">Authorization</span></span> | <span data-ttu-id="e57ba-135">文字列</span><span class="sxs-lookup"><span data-stu-id="e57ba-135">String</span></span> | <span data-ttu-id="e57ba-136">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="e57ba-136">Bearer {token}.</span></span> <span data-ttu-id="e57ba-137">**必須**。</span><span class="sxs-lookup"><span data-stu-id="e57ba-137">**Required**.</span></span>
<span data-ttu-id="e57ba-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e57ba-138">Content-Type</span></span> | <span data-ttu-id="e57ba-139">文字列</span><span class="sxs-lookup"><span data-stu-id="e57ba-139">String</span></span> | <span data-ttu-id="e57ba-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="e57ba-140">application/json.</span></span> <span data-ttu-id="e57ba-141">**必須**。</span><span class="sxs-lookup"><span data-stu-id="e57ba-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e57ba-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="e57ba-142">Request body</span></span>
<span data-ttu-id="e57ba-143">要求本文で、更新する必要のある関連フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e57ba-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="e57ba-144">要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。</span><span class="sxs-lookup"><span data-stu-id="e57ba-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="e57ba-145">最適なパフォーマンスを得るために、変更されていない既存の値を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="e57ba-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="e57ba-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e57ba-146">Property</span></span> | <span data-ttu-id="e57ba-147">種類</span><span class="sxs-lookup"><span data-stu-id="e57ba-147">Type</span></span> | <span data-ttu-id="e57ba-148">説明</span><span class="sxs-lookup"><span data-stu-id="e57ba-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="e57ba-149">status</span><span class="sxs-lookup"><span data-stu-id="e57ba-149">status</span></span> | <span data-ttu-id="e57ba-150">列挙</span><span class="sxs-lookup"><span data-stu-id="e57ba-150">Enum</span></span> | <span data-ttu-id="e57ba-151">通知の現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="e57ba-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="e57ba-152">可能な値は ```Active``` 、、、 ```Resolved``` ```Redirected``` です。</span><span class="sxs-lookup"><span data-stu-id="e57ba-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="e57ba-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="e57ba-153">assignedTo</span></span> | <span data-ttu-id="e57ba-154">string</span><span class="sxs-lookup"><span data-stu-id="e57ba-154">string</span></span> | <span data-ttu-id="e57ba-155">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="e57ba-155">Owner of the incident.</span></span>
<span data-ttu-id="e57ba-156">classification</span><span class="sxs-lookup"><span data-stu-id="e57ba-156">classification</span></span> | <span data-ttu-id="e57ba-157">列挙</span><span class="sxs-lookup"><span data-stu-id="e57ba-157">Enum</span></span> | <span data-ttu-id="e57ba-158">通知の仕様。</span><span class="sxs-lookup"><span data-stu-id="e57ba-158">Specification of the alert.</span></span> <span data-ttu-id="e57ba-159">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="e57ba-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="e57ba-160">決定</span><span class="sxs-lookup"><span data-stu-id="e57ba-160">determination</span></span> | <span data-ttu-id="e57ba-161">列挙</span><span class="sxs-lookup"><span data-stu-id="e57ba-161">Enum</span></span> | <span data-ttu-id="e57ba-162">通知の決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e57ba-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="e57ba-163">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="e57ba-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="e57ba-164">tags</span><span class="sxs-lookup"><span data-stu-id="e57ba-164">tags</span></span> | <span data-ttu-id="e57ba-165">文字列リスト</span><span class="sxs-lookup"><span data-stu-id="e57ba-165">string List</span></span> | <span data-ttu-id="e57ba-166">インシデントタグのリスト。</span><span class="sxs-lookup"><span data-stu-id="e57ba-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="e57ba-167">応答</span><span class="sxs-lookup"><span data-stu-id="e57ba-167">Response</span></span>
<span data-ttu-id="e57ba-168">成功した場合、このメソッドは 200 OK と、応答本文で、更新されたプロパティを持つ incident エンティティを返します。</span><span class="sxs-lookup"><span data-stu-id="e57ba-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="e57ba-169">指定した id の incident が見つからない場合は、404が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="e57ba-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="e57ba-170">例</span><span class="sxs-lookup"><span data-stu-id="e57ba-170">Example</span></span>

<span data-ttu-id="e57ba-171">**要求**</span><span class="sxs-lookup"><span data-stu-id="e57ba-171">**Request**</span></span>

<span data-ttu-id="e57ba-172">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="e57ba-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="e57ba-173">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e57ba-173">Related topic</span></span>
- [<span data-ttu-id="e57ba-174">インシデント Api</span><span class="sxs-lookup"><span data-stu-id="e57ba-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="e57ba-175">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="e57ba-175">List incidents</span></span>](api-list-incidents.md)