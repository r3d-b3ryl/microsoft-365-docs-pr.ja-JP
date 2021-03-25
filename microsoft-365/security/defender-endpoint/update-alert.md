---
title: アラート エンティティ API の更新
description: この API を使用して Microsoft Defender ATP アラートを更新する方法について説明します。 状態、決定、分類、および assignedTo プロパティを更新できます。
keywords: apis, graph api, supported apis, get, alert, information, id
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
ms.openlocfilehash: 7dd3ab3da34efa6cb954db2a596d7a1e48efedf1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199311"
---
# <a name="update-alert"></a><span data-ttu-id="15903-105">アラートを更新する</span><span class="sxs-lookup"><span data-stu-id="15903-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="15903-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="15903-106">**Applies to:**</span></span>
- [<span data-ttu-id="15903-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="15903-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="15903-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15903-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="15903-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="15903-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="15903-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="15903-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="15903-111">API の説明</span><span class="sxs-lookup"><span data-stu-id="15903-111">API description</span></span>
<span data-ttu-id="15903-112">既存の Alert のプロパティを [更新します](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="15903-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="15903-113">コメントの **提出は** 、プロパティを更新する場合と更新しない場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="15903-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="15903-114">更新可能なプロパティは ```status``` ```determination``` 、、、、 ```classification``` です ```assignedTo``` 。</span><span class="sxs-lookup"><span data-stu-id="15903-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="15903-115">制限事項</span><span class="sxs-lookup"><span data-stu-id="15903-115">Limitations</span></span>
1. <span data-ttu-id="15903-116">API で使用可能なアラートを更新できます。</span><span class="sxs-lookup"><span data-stu-id="15903-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="15903-117">詳細については [、「アラートの一](get-alerts.md) 覧」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15903-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="15903-118">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="15903-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="15903-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="15903-119">Permissions</span></span>
<span data-ttu-id="15903-120">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="15903-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="15903-121">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="15903-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="15903-122">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="15903-122">Permission type</span></span> |   <span data-ttu-id="15903-123">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="15903-123">Permission</span></span>  |   <span data-ttu-id="15903-124">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="15903-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="15903-125">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="15903-125">Application</span></span> |   <span data-ttu-id="15903-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="15903-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="15903-127">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="15903-127">'Read and write all alerts'</span></span>
<span data-ttu-id="15903-128">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="15903-128">Delegated (work or school account)</span></span> | <span data-ttu-id="15903-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="15903-129">Alert.ReadWrite</span></span> | <span data-ttu-id="15903-130">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="15903-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="15903-131">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="15903-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="15903-132">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'アラートの調査' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="15903-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="15903-133">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="15903-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="15903-134">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="15903-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="15903-135">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="15903-135">Request headers</span></span>

<span data-ttu-id="15903-136">名前</span><span class="sxs-lookup"><span data-stu-id="15903-136">Name</span></span> | <span data-ttu-id="15903-137">種類</span><span class="sxs-lookup"><span data-stu-id="15903-137">Type</span></span> | <span data-ttu-id="15903-138">説明</span><span class="sxs-lookup"><span data-stu-id="15903-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="15903-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="15903-139">Authorization</span></span> | <span data-ttu-id="15903-140">文字列</span><span class="sxs-lookup"><span data-stu-id="15903-140">String</span></span> | <span data-ttu-id="15903-141">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="15903-141">Bearer {token}.</span></span> <span data-ttu-id="15903-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="15903-142">**Required**.</span></span>
<span data-ttu-id="15903-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="15903-143">Content-Type</span></span> | <span data-ttu-id="15903-144">文字列</span><span class="sxs-lookup"><span data-stu-id="15903-144">String</span></span> | <span data-ttu-id="15903-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="15903-145">application/json.</span></span> <span data-ttu-id="15903-146">**必須**</span><span class="sxs-lookup"><span data-stu-id="15903-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="15903-147">要求本文</span><span class="sxs-lookup"><span data-stu-id="15903-147">Request body</span></span>
<span data-ttu-id="15903-148">要求本文で、更新する必要がある関連フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="15903-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="15903-149">要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。</span><span class="sxs-lookup"><span data-stu-id="15903-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="15903-150">最適なパフォーマンスを得る場合は、変更していない既存の値を含めてはならない。</span><span class="sxs-lookup"><span data-stu-id="15903-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="15903-151">プロパティ</span><span class="sxs-lookup"><span data-stu-id="15903-151">Property</span></span> | <span data-ttu-id="15903-152">種類</span><span class="sxs-lookup"><span data-stu-id="15903-152">Type</span></span> | <span data-ttu-id="15903-153">説明</span><span class="sxs-lookup"><span data-stu-id="15903-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="15903-154">status</span><span class="sxs-lookup"><span data-stu-id="15903-154">status</span></span> | <span data-ttu-id="15903-155">String</span><span class="sxs-lookup"><span data-stu-id="15903-155">String</span></span> | <span data-ttu-id="15903-156">アラートの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="15903-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="15903-157">プロパティの値は、'New'、'InProgress'、および 'Resolved' です。</span><span class="sxs-lookup"><span data-stu-id="15903-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="15903-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="15903-158">assignedTo</span></span> | <span data-ttu-id="15903-159">String</span><span class="sxs-lookup"><span data-stu-id="15903-159">String</span></span> | <span data-ttu-id="15903-160">アラートの所有者</span><span class="sxs-lookup"><span data-stu-id="15903-160">Owner of the alert</span></span>
<span data-ttu-id="15903-161">classification</span><span class="sxs-lookup"><span data-stu-id="15903-161">classification</span></span> | <span data-ttu-id="15903-162">String</span><span class="sxs-lookup"><span data-stu-id="15903-162">String</span></span> | <span data-ttu-id="15903-163">アラートの仕様を指定します。</span><span class="sxs-lookup"><span data-stu-id="15903-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="15903-164">プロパティの値は、'Unknown'、'FalsePositive'、'TruePositive'です。</span><span class="sxs-lookup"><span data-stu-id="15903-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="15903-165">決定</span><span class="sxs-lookup"><span data-stu-id="15903-165">determination</span></span> | <span data-ttu-id="15903-166">文字列</span><span class="sxs-lookup"><span data-stu-id="15903-166">String</span></span> | <span data-ttu-id="15903-167">アラートの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="15903-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="15903-168">プロパティの値は、'NotAvailable'、'Apt'、'Malware'、'SecurityPersonnel'、'SecurityTesting'、'UnwantedSoftware'、'Other' です。</span><span class="sxs-lookup"><span data-stu-id="15903-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="15903-169">comment</span><span class="sxs-lookup"><span data-stu-id="15903-169">comment</span></span> | <span data-ttu-id="15903-170">String</span><span class="sxs-lookup"><span data-stu-id="15903-170">String</span></span> | <span data-ttu-id="15903-171">警告に追加するコメント。</span><span class="sxs-lookup"><span data-stu-id="15903-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="15903-172">応答</span><span class="sxs-lookup"><span data-stu-id="15903-172">Response</span></span>
<span data-ttu-id="15903-173">成功した場合、このメソッドは 200 OK[](alerts.md)を返し、更新されたプロパティを持つ応答本文のアラート エンティティを返します。</span><span class="sxs-lookup"><span data-stu-id="15903-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="15903-174">指定された ID を持つアラートが見つからなかった場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="15903-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="15903-175">例</span><span class="sxs-lookup"><span data-stu-id="15903-175">Example</span></span>

<span data-ttu-id="15903-176">**要求**</span><span class="sxs-lookup"><span data-stu-id="15903-176">**Request**</span></span>

<span data-ttu-id="15903-177">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="15903-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
