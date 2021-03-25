---
title: バッチ更新アラート エンティティ API
description: この API を使用して、Microsoft Defender for Endpoint アラートをバッチで更新する方法について説明します。 状態、決定、分類、および assignedTo プロパティを更新できます。
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
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167091"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="39cf4-105">バッチ更新の通知</span><span class="sxs-lookup"><span data-stu-id="39cf4-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="39cf4-106">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="39cf4-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="39cf4-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="39cf4-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="39cf4-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="39cf4-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="39cf4-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="39cf4-109">API description</span></span>
<span data-ttu-id="39cf4-110">既存のアラートのバッチのプロパティを [更新します](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="39cf4-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="39cf4-111">コメントの **提出は** 、プロパティを更新する場合と更新しない場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="39cf4-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="39cf4-112">更新可能なプロパティは `status` `determination` 、、、、 `classification` です `assignedTo` 。</span><span class="sxs-lookup"><span data-stu-id="39cf4-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="39cf4-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="39cf4-113">Limitations</span></span>
1. <span data-ttu-id="39cf4-114">API で使用可能なアラートを更新できます。</span><span class="sxs-lookup"><span data-stu-id="39cf4-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="39cf4-115">詳細については [、「アラートの一](get-alerts.md) 覧」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39cf4-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="39cf4-116">この API のレート制限は、1 分あたり 10 回の呼び出しと 1 時間あたり 500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="39cf4-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="39cf4-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="39cf4-117">Permissions</span></span>
<span data-ttu-id="39cf4-118">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="39cf4-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="39cf4-119">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="39cf4-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="39cf4-120">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="39cf4-120">Permission type</span></span> |   <span data-ttu-id="39cf4-121">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="39cf4-121">Permission</span></span>  |   <span data-ttu-id="39cf4-122">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="39cf4-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="39cf4-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="39cf4-123">Application</span></span> |   <span data-ttu-id="39cf4-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="39cf4-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="39cf4-125">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="39cf4-125">'Read and write all alerts'</span></span>
<span data-ttu-id="39cf4-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="39cf4-126">Delegated (work or school account)</span></span> | <span data-ttu-id="39cf4-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="39cf4-127">Alert.ReadWrite</span></span> | <span data-ttu-id="39cf4-128">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="39cf4-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="39cf4-129">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="39cf4-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="39cf4-130">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'アラートの調査' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="39cf4-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="39cf4-131">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="39cf4-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="39cf4-132">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="39cf4-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="39cf4-133">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="39cf4-133">Request headers</span></span>

<span data-ttu-id="39cf4-134">名前</span><span class="sxs-lookup"><span data-stu-id="39cf4-134">Name</span></span> | <span data-ttu-id="39cf4-135">種類</span><span class="sxs-lookup"><span data-stu-id="39cf4-135">Type</span></span> | <span data-ttu-id="39cf4-136">説明</span><span class="sxs-lookup"><span data-stu-id="39cf4-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="39cf4-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="39cf4-137">Authorization</span></span> | <span data-ttu-id="39cf4-138">文字列</span><span class="sxs-lookup"><span data-stu-id="39cf4-138">String</span></span> | <span data-ttu-id="39cf4-139">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="39cf4-139">Bearer {token}.</span></span> <span data-ttu-id="39cf4-140">**必須**</span><span class="sxs-lookup"><span data-stu-id="39cf4-140">**Required**.</span></span>
<span data-ttu-id="39cf4-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="39cf4-141">Content-Type</span></span> | <span data-ttu-id="39cf4-142">文字列</span><span class="sxs-lookup"><span data-stu-id="39cf4-142">String</span></span> | <span data-ttu-id="39cf4-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="39cf4-143">application/json.</span></span> <span data-ttu-id="39cf4-144">**必須**</span><span class="sxs-lookup"><span data-stu-id="39cf4-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="39cf4-145">要求本文</span><span class="sxs-lookup"><span data-stu-id="39cf4-145">Request body</span></span>
<span data-ttu-id="39cf4-146">要求本文で、更新するアラートの ID と、これらのアラートに対して更新する関連フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="39cf4-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="39cf4-147">要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。</span><span class="sxs-lookup"><span data-stu-id="39cf4-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="39cf4-148">最適なパフォーマンスを得るためには、変更されていない既存の値を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="39cf4-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="39cf4-149">プロパティ</span><span class="sxs-lookup"><span data-stu-id="39cf4-149">Property</span></span> | <span data-ttu-id="39cf4-150">種類</span><span class="sxs-lookup"><span data-stu-id="39cf4-150">Type</span></span> | <span data-ttu-id="39cf4-151">説明</span><span class="sxs-lookup"><span data-stu-id="39cf4-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="39cf4-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="39cf4-152">alertIds</span></span> | <span data-ttu-id="39cf4-153">リスト &lt; 文字列&gt;</span><span class="sxs-lookup"><span data-stu-id="39cf4-153">List&lt;String&gt;</span></span>| <span data-ttu-id="39cf4-154">更新するアラートの一覧。</span><span class="sxs-lookup"><span data-stu-id="39cf4-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="39cf4-155">**必須**</span><span class="sxs-lookup"><span data-stu-id="39cf4-155">**Required**</span></span>
<span data-ttu-id="39cf4-156">status</span><span class="sxs-lookup"><span data-stu-id="39cf4-156">status</span></span> | <span data-ttu-id="39cf4-157">String</span><span class="sxs-lookup"><span data-stu-id="39cf4-157">String</span></span> | <span data-ttu-id="39cf4-158">指定したアラートの更新された状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="39cf4-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="39cf4-159">プロパティの値は、'New'、'InProgress'、および 'Resolved' です。</span><span class="sxs-lookup"><span data-stu-id="39cf4-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="39cf4-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="39cf4-160">assignedTo</span></span> | <span data-ttu-id="39cf4-161">String</span><span class="sxs-lookup"><span data-stu-id="39cf4-161">String</span></span> | <span data-ttu-id="39cf4-162">指定したアラートの所有者</span><span class="sxs-lookup"><span data-stu-id="39cf4-162">Owner of the specified alerts</span></span>
<span data-ttu-id="39cf4-163">classification</span><span class="sxs-lookup"><span data-stu-id="39cf4-163">classification</span></span> | <span data-ttu-id="39cf4-164">String</span><span class="sxs-lookup"><span data-stu-id="39cf4-164">String</span></span> | <span data-ttu-id="39cf4-165">指定したアラートの仕様を指定します。</span><span class="sxs-lookup"><span data-stu-id="39cf4-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="39cf4-166">プロパティの値は、'Unknown'、'FalsePositive'、'TruePositive'です。</span><span class="sxs-lookup"><span data-stu-id="39cf4-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="39cf4-167">決定</span><span class="sxs-lookup"><span data-stu-id="39cf4-167">determination</span></span> | <span data-ttu-id="39cf4-168">文字列</span><span class="sxs-lookup"><span data-stu-id="39cf4-168">String</span></span> | <span data-ttu-id="39cf4-169">指定したアラートの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="39cf4-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="39cf4-170">プロパティの値は、'NotAvailable'、'Apt'、'Malware'、'SecurityPersonnel'、'SecurityTesting'、'UnwantedSoftware'、'Other' です。</span><span class="sxs-lookup"><span data-stu-id="39cf4-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="39cf4-171">comment</span><span class="sxs-lookup"><span data-stu-id="39cf4-171">comment</span></span> | <span data-ttu-id="39cf4-172">String</span><span class="sxs-lookup"><span data-stu-id="39cf4-172">String</span></span> | <span data-ttu-id="39cf4-173">指定したアラートに追加するコメント。</span><span class="sxs-lookup"><span data-stu-id="39cf4-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="39cf4-174">応答</span><span class="sxs-lookup"><span data-stu-id="39cf4-174">Response</span></span>
<span data-ttu-id="39cf4-175">成功した場合、このメソッドは 200 OK を返し、空の応答本文を返します。</span><span class="sxs-lookup"><span data-stu-id="39cf4-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="39cf4-176">例</span><span class="sxs-lookup"><span data-stu-id="39cf4-176">Example</span></span>

<span data-ttu-id="39cf4-177">**要求**</span><span class="sxs-lookup"><span data-stu-id="39cf4-177">**Request**</span></span>

<span data-ttu-id="39cf4-178">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="39cf4-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
