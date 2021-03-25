---
title: デバイス値 API の設定
description: Microsoft Defender for Endpoint API を使用してデバイスの値を指定する方法について説明します。
keywords: apis、graph api、サポートされている API、タグ、マシン タグ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33692ddf62153c0a6aa8f84568d69803af113bc6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185565"
---
# <a name="set-device-value-api"></a><span data-ttu-id="1d3d4-104">デバイス値 API の設定</span><span class="sxs-lookup"><span data-stu-id="1d3d4-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d3d4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1d3d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d3d4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d3d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d3d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d3d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1d3d4-108">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1d3d4-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1d3d4-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1d3d4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d3d4-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1d3d4-111">API の説明</span><span class="sxs-lookup"><span data-stu-id="1d3d4-111">API description</span></span>

<span data-ttu-id="1d3d4-112">特定のコンピューターのデバイス値を設定 [します](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="1d3d4-113">詳細については [、「デバイス値の割り当て](tvm-assign-device-value.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="1d3d4-114">制限事項</span><span class="sxs-lookup"><span data-stu-id="1d3d4-114">Limitations</span></span>

1. <span data-ttu-id="1d3d4-115">構成済みの保持期間に従って最後に表示されたデバイスに投稿できます。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="1d3d4-116">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1d3d4-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1d3d4-117">Permissions</span></span>

<span data-ttu-id="1d3d4-118">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d3d4-119">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1d3d4-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1d3d4-120">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="1d3d4-120">Permission type</span></span> |    <span data-ttu-id="1d3d4-121">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1d3d4-121">Permission</span></span>    |    <span data-ttu-id="1d3d4-122">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="1d3d4-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1d3d4-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1d3d4-123">Application</span></span> |    <span data-ttu-id="1d3d4-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1d3d4-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="1d3d4-125">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="1d3d4-125">'Read and write all machine information'</span></span>
<span data-ttu-id="1d3d4-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="1d3d4-126">Delegated (work or school account)</span></span> | <span data-ttu-id="1d3d4-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1d3d4-127">Machine.ReadWrite</span></span> | <span data-ttu-id="1d3d4-128">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="1d3d4-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="1d3d4-129">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="1d3d4-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="1d3d4-130">ユーザーには、少なくとも次の役割のアクセス許可が必要です。'セキュリティ設定の管理' 。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="1d3d4-131">詳細については、「役割の [作成と管理」を](user-roles.md) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="1d3d4-132">ユーザーは、コンピューター グループの設定に基づいてコンピューターにアクセスする必要があります (詳細については、「 [コンピューター](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="1d3d4-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1d3d4-133">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="1d3d4-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="1d3d4-134">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1d3d4-134">Request headers</span></span>

<span data-ttu-id="1d3d4-135">名前</span><span class="sxs-lookup"><span data-stu-id="1d3d4-135">Name</span></span> | <span data-ttu-id="1d3d4-136">種類</span><span class="sxs-lookup"><span data-stu-id="1d3d4-136">Type</span></span> | <span data-ttu-id="1d3d4-137">説明</span><span class="sxs-lookup"><span data-stu-id="1d3d4-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="1d3d4-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="1d3d4-138">Authorization</span></span> | <span data-ttu-id="1d3d4-139">文字列</span><span class="sxs-lookup"><span data-stu-id="1d3d4-139">String</span></span> | <span data-ttu-id="1d3d4-140">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-140">Bearer {token}.</span></span> <span data-ttu-id="1d3d4-141">**必須**</span><span class="sxs-lookup"><span data-stu-id="1d3d4-141">**Required**.</span></span>
<span data-ttu-id="1d3d4-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1d3d4-142">Content-Type</span></span> | <span data-ttu-id="1d3d4-143">string</span><span class="sxs-lookup"><span data-stu-id="1d3d4-143">string</span></span> | <span data-ttu-id="1d3d4-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="1d3d4-144">application/json.</span></span> <span data-ttu-id="1d3d4-145">**必須**</span><span class="sxs-lookup"><span data-stu-id="1d3d4-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1d3d4-146">要求本文</span><span class="sxs-lookup"><span data-stu-id="1d3d4-146">Request body</span></span>

<span data-ttu-id="1d3d4-147">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="1d3d4-148">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1d3d4-148">Parameter</span></span> |    <span data-ttu-id="1d3d4-149">種類</span><span class="sxs-lookup"><span data-stu-id="1d3d4-149">Type</span></span>    | <span data-ttu-id="1d3d4-150">説明</span><span class="sxs-lookup"><span data-stu-id="1d3d4-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="1d3d4-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="1d3d4-151">DeviceValue</span></span> |    <span data-ttu-id="1d3d4-152">列挙</span><span class="sxs-lookup"><span data-stu-id="1d3d4-152">Enum</span></span> |    <span data-ttu-id="1d3d4-153">デバイスの値。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-153">Device value.</span></span> <span data-ttu-id="1d3d4-154">使用できる値は、'Normal'、'Low'、および 'High' です。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="1d3d4-155">**必須**</span><span class="sxs-lookup"><span data-stu-id="1d3d4-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="1d3d4-156">応答</span><span class="sxs-lookup"><span data-stu-id="1d3d4-156">Response</span></span>

<span data-ttu-id="1d3d4-157">成功した場合、このメソッドは 200 - OK 応答コードと更新された Machine を応答本文で返します。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="1d3d4-158">例</span><span class="sxs-lookup"><span data-stu-id="1d3d4-158">Example</span></span>

<span data-ttu-id="1d3d4-159">**要求**</span><span class="sxs-lookup"><span data-stu-id="1d3d4-159">**Request**</span></span>

<span data-ttu-id="1d3d4-160">コンピューター タグを追加する要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1d3d4-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```