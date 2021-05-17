---
title: オフボード マシン API
description: API を使用して Microsoft Defender for Endpoint からデバイスをオフボードする方法について説明します。
keywords: apis、graph api、サポートされている API、調査パッケージの収集
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
ms.openlocfilehash: 03a1ef11224021703a6f33f82fa2c4f135a317a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934179"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="544b0-104">オフボード マシン API</span><span class="sxs-lookup"><span data-stu-id="544b0-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="544b0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="544b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="544b0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="544b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="544b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="544b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="544b0-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="544b0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="544b0-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="544b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="544b0-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="544b0-110">API description</span></span>
<span data-ttu-id="544b0-111">Defender for Endpoint からのオフボード デバイス。</span><span class="sxs-lookup"><span data-stu-id="544b0-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="544b0-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="544b0-112">Limitations</span></span>
 - <span data-ttu-id="544b0-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="544b0-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="544b0-114">この API は、Windows 10バージョン 1703 以降、またはサーバー 2019 以降Windowsサポートされています。</span><span class="sxs-lookup"><span data-stu-id="544b0-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="544b0-115">この API は、MacOS デバイスまたは Linux デバイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="544b0-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="544b0-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="544b0-116">Permissions</span></span>
<span data-ttu-id="544b0-117">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="544b0-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="544b0-118">アクセス許可の選択方法などの詳細については [、「Use Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="544b0-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="544b0-119">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="544b0-119">Permission type</span></span> |   <span data-ttu-id="544b0-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="544b0-120">Permission</span></span>  |   <span data-ttu-id="544b0-121">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="544b0-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="544b0-122">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="544b0-122">Application</span></span> |   <span data-ttu-id="544b0-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="544b0-123">Machine.Offboard</span></span> |  <span data-ttu-id="544b0-124">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="544b0-124">'Offboard machine'</span></span>
<span data-ttu-id="544b0-125">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="544b0-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="544b0-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="544b0-126">Machine.Offboard</span></span> |  <span data-ttu-id="544b0-127">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="544b0-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="544b0-128">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="544b0-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="544b0-129">ユーザーが役割を 「グローバル管理者」 ADする必要がある</span><span class="sxs-lookup"><span data-stu-id="544b0-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="544b0-130">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="544b0-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="544b0-131">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="544b0-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="544b0-132">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="544b0-132">Request headers</span></span>

<span data-ttu-id="544b0-133">名前</span><span class="sxs-lookup"><span data-stu-id="544b0-133">Name</span></span> | <span data-ttu-id="544b0-134">型</span><span class="sxs-lookup"><span data-stu-id="544b0-134">Type</span></span> | <span data-ttu-id="544b0-135">説明</span><span class="sxs-lookup"><span data-stu-id="544b0-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="544b0-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="544b0-136">Authorization</span></span> | <span data-ttu-id="544b0-137">String</span><span class="sxs-lookup"><span data-stu-id="544b0-137">String</span></span> | <span data-ttu-id="544b0-138">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="544b0-138">Bearer {token}.</span></span> <span data-ttu-id="544b0-139">**必須**</span><span class="sxs-lookup"><span data-stu-id="544b0-139">**Required**.</span></span>
<span data-ttu-id="544b0-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="544b0-140">Content-Type</span></span> | <span data-ttu-id="544b0-141">string</span><span class="sxs-lookup"><span data-stu-id="544b0-141">string</span></span> | <span data-ttu-id="544b0-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="544b0-142">application/json.</span></span> <span data-ttu-id="544b0-143">**必須**</span><span class="sxs-lookup"><span data-stu-id="544b0-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="544b0-144">要求本文</span><span class="sxs-lookup"><span data-stu-id="544b0-144">Request body</span></span>
<span data-ttu-id="544b0-145">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="544b0-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="544b0-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="544b0-146">Parameter</span></span> | <span data-ttu-id="544b0-147">型</span><span class="sxs-lookup"><span data-stu-id="544b0-147">Type</span></span>    | <span data-ttu-id="544b0-148">説明</span><span class="sxs-lookup"><span data-stu-id="544b0-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="544b0-149">コメント</span><span class="sxs-lookup"><span data-stu-id="544b0-149">Comment</span></span> |   <span data-ttu-id="544b0-150">文字列</span><span class="sxs-lookup"><span data-stu-id="544b0-150">String</span></span> |    <span data-ttu-id="544b0-151">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="544b0-151">Comment to associate with the action.</span></span> <span data-ttu-id="544b0-152">**必須**</span><span class="sxs-lookup"><span data-stu-id="544b0-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="544b0-153">応答</span><span class="sxs-lookup"><span data-stu-id="544b0-153">Response</span></span>
<span data-ttu-id="544b0-154">成功した場合、このメソッドは応答本文に 201 - Created response code and [Machine Action](machineaction.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="544b0-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="544b0-155">例</span><span class="sxs-lookup"><span data-stu-id="544b0-155">Example</span></span>

<span data-ttu-id="544b0-156">**要求**</span><span class="sxs-lookup"><span data-stu-id="544b0-156">**Request**</span></span>

<span data-ttu-id="544b0-157">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="544b0-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
