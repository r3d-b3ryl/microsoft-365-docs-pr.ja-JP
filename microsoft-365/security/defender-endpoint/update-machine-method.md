---
title: コンピューター エンティティ API の更新
description: この API を使用してコンピューター タグを更新する方法について説明します。 タグと devicevalue プロパティを更新できます。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985751"
---
# <a name="update-machine"></a><span data-ttu-id="8c46f-105">コンピューターの更新</span><span class="sxs-lookup"><span data-stu-id="8c46f-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c46f-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8c46f-106">**Applies to:**</span></span>
- [<span data-ttu-id="8c46f-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8c46f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8c46f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c46f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8c46f-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="8c46f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c46f-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8c46f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8c46f-111">API の説明</span><span class="sxs-lookup"><span data-stu-id="8c46f-111">API description</span></span>
<span data-ttu-id="8c46f-112">既存の Machine のプロパティを更新 [します](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="8c46f-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="8c46f-113">更新可能なプロパティは次 ```machineTags``` のとおりです ```deviceValue``` 。</span><span class="sxs-lookup"><span data-stu-id="8c46f-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="8c46f-114">制限事項</span><span class="sxs-lookup"><span data-stu-id="8c46f-114">Limitations</span></span>
1. <span data-ttu-id="8c46f-115">API で使用できるコンピューターを更新できます。</span><span class="sxs-lookup"><span data-stu-id="8c46f-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="8c46f-116">コンピューターを更新すると、タグ コレクションにタグが追加されます。</span><span class="sxs-lookup"><span data-stu-id="8c46f-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="8c46f-117">タグが存在する場合は、本文の tags コレクションにタグを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c46f-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="8c46f-118">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="8c46f-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="8c46f-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8c46f-119">Permissions</span></span>
<span data-ttu-id="8c46f-120">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8c46f-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8c46f-121">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8c46f-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8c46f-122">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="8c46f-122">Permission type</span></span> |   <span data-ttu-id="8c46f-123">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8c46f-123">Permission</span></span>  |   <span data-ttu-id="8c46f-124">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="8c46f-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8c46f-125">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8c46f-125">Application</span></span> |   <span data-ttu-id="8c46f-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8c46f-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="8c46f-127">'すべてのコンピューターのコンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="8c46f-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="8c46f-128">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="8c46f-128">Delegated (work or school account)</span></span> | <span data-ttu-id="8c46f-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8c46f-129">Machine.ReadWrite</span></span> | <span data-ttu-id="8c46f-130">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="8c46f-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="8c46f-131">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="8c46f-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8c46f-132">ユーザーには、少なくとも次の役割のアクセス許可が必要です。"アラートの調査" です。</span><span class="sxs-lookup"><span data-stu-id="8c46f-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="8c46f-133">詳細については、「役割の作成 [と管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8c46f-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="8c46f-134">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c46f-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="8c46f-135">詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="8c46f-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="8c46f-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="8c46f-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="8c46f-137">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8c46f-137">Request headers</span></span>

<span data-ttu-id="8c46f-138">名前</span><span class="sxs-lookup"><span data-stu-id="8c46f-138">Name</span></span> | <span data-ttu-id="8c46f-139">種類</span><span class="sxs-lookup"><span data-stu-id="8c46f-139">Type</span></span> | <span data-ttu-id="8c46f-140">説明</span><span class="sxs-lookup"><span data-stu-id="8c46f-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="8c46f-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="8c46f-141">Authorization</span></span> | <span data-ttu-id="8c46f-142">String</span><span class="sxs-lookup"><span data-stu-id="8c46f-142">String</span></span> | <span data-ttu-id="8c46f-143">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="8c46f-143">Bearer {token}.</span></span> <span data-ttu-id="8c46f-144">**必須**</span><span class="sxs-lookup"><span data-stu-id="8c46f-144">**Required**.</span></span>
<span data-ttu-id="8c46f-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8c46f-145">Content-Type</span></span> | <span data-ttu-id="8c46f-146">文字列</span><span class="sxs-lookup"><span data-stu-id="8c46f-146">String</span></span> | <span data-ttu-id="8c46f-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="8c46f-147">application/json.</span></span> <span data-ttu-id="8c46f-148">**必須**</span><span class="sxs-lookup"><span data-stu-id="8c46f-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8c46f-149">要求本文</span><span class="sxs-lookup"><span data-stu-id="8c46f-149">Request body</span></span>
<span data-ttu-id="8c46f-150">要求本文で、更新する必要がある関連フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c46f-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="8c46f-151">要求本文に含まれない既存のプロパティは、以前の値のままになるか、他のプロパティ値の変化に基づいて再計算されます。</span><span class="sxs-lookup"><span data-stu-id="8c46f-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="8c46f-152">最適なパフォーマンスを得る場合は、変更していない既存の値を含めてはならない。</span><span class="sxs-lookup"><span data-stu-id="8c46f-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="8c46f-153">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8c46f-153">Property</span></span> | <span data-ttu-id="8c46f-154">種類</span><span class="sxs-lookup"><span data-stu-id="8c46f-154">Type</span></span> | <span data-ttu-id="8c46f-155">説明</span><span class="sxs-lookup"><span data-stu-id="8c46f-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="8c46f-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="8c46f-156">machineTags</span></span> | <span data-ttu-id="8c46f-157">String コレクション</span><span class="sxs-lookup"><span data-stu-id="8c46f-157">String collection</span></span> | <span data-ttu-id="8c46f-158">コンピューター タグ [の](machine.md) セット。</span><span class="sxs-lookup"><span data-stu-id="8c46f-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="8c46f-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="8c46f-159">deviceValue</span></span> | <span data-ttu-id="8c46f-160">Null 許容列挙</span><span class="sxs-lookup"><span data-stu-id="8c46f-160">Nullable Enum</span></span> | <span data-ttu-id="8c46f-161">デバイス [の値](tvm-assign-device-value.md)です。</span><span class="sxs-lookup"><span data-stu-id="8c46f-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="8c46f-162">指定できる値は、'Normal'、'Low'、および 'High' です。</span><span class="sxs-lookup"><span data-stu-id="8c46f-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="8c46f-163">応答</span><span class="sxs-lookup"><span data-stu-id="8c46f-163">Response</span></span>
<span data-ttu-id="8c46f-164">成功した場合、このメソッドは 200 OK[](machine.md)を返し、更新されたプロパティを持つ応答本文の machine エンティティを返します。</span><span class="sxs-lookup"><span data-stu-id="8c46f-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="8c46f-165">本文の machine tags コレクションに既存のコンピューター タグが含まれている場合 - 400 無効な入力と、見つからないタグ/s を通知するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8c46f-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="8c46f-166">指定した ID を持つコンピューターが見つからない場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="8c46f-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="8c46f-167">例</span><span class="sxs-lookup"><span data-stu-id="8c46f-167">Example</span></span>

<span data-ttu-id="8c46f-168">**要求**</span><span class="sxs-lookup"><span data-stu-id="8c46f-168">**Request**</span></span>

<span data-ttu-id="8c46f-169">要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8c46f-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
