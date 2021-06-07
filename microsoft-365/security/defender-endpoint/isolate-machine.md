---
title: コンピューター API の分離
description: 分離マシン API を使用して、Microsoft Defender for Endpoint の外部ネットワークへのアクセスからデバイスを分離する方法について説明します。
keywords: apis、graph api、サポートされている API、デバイスの分離
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
ms.openlocfilehash: 9f3313a08b072f4fb2f699148ab801207e56fc09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772115"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="8ea4b-104">コンピューター API の分離</span><span class="sxs-lookup"><span data-stu-id="8ea4b-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8ea4b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8ea4b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ea4b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ea4b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8ea4b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ea4b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="8ea4b-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8ea4b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8ea4b-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8ea4b-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="8ea4b-110">API description</span></span>
<span data-ttu-id="8ea4b-111">デバイスが外部ネットワークにアクセスするのを分離します。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="8ea4b-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="8ea4b-112">Limitations</span></span>
1. <span data-ttu-id="8ea4b-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="8ea4b-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8ea4b-114">Permissions</span></span>
<span data-ttu-id="8ea4b-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8ea4b-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8ea4b-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="8ea4b-117">Permission type</span></span> |   <span data-ttu-id="8ea4b-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8ea4b-118">Permission</span></span>  |   <span data-ttu-id="8ea4b-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="8ea4b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8ea4b-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8ea4b-120">Application</span></span> |   <span data-ttu-id="8ea4b-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="8ea4b-121">Machine.Isolate</span></span> |   <span data-ttu-id="8ea4b-122">'分離マシン'</span><span class="sxs-lookup"><span data-stu-id="8ea4b-122">'Isolate machine'</span></span>
<span data-ttu-id="8ea4b-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-123">Delegated (work or school account)</span></span> | <span data-ttu-id="8ea4b-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="8ea4b-124">Machine.Isolate</span></span> |  <span data-ttu-id="8ea4b-125">'分離マシン'</span><span class="sxs-lookup"><span data-stu-id="8ea4b-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="8ea4b-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="8ea4b-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8ea4b-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="8ea4b-128">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="8ea4b-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="8ea4b-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="8ea4b-130">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8ea4b-130">Request headers</span></span>

<span data-ttu-id="8ea4b-131">名前</span><span class="sxs-lookup"><span data-stu-id="8ea4b-131">Name</span></span> | <span data-ttu-id="8ea4b-132">種類</span><span class="sxs-lookup"><span data-stu-id="8ea4b-132">Type</span></span> | <span data-ttu-id="8ea4b-133">説明</span><span class="sxs-lookup"><span data-stu-id="8ea4b-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="8ea4b-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="8ea4b-134">Authorization</span></span> | <span data-ttu-id="8ea4b-135">String</span><span class="sxs-lookup"><span data-stu-id="8ea4b-135">String</span></span> | <span data-ttu-id="8ea4b-136">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-136">Bearer {token}.</span></span> <span data-ttu-id="8ea4b-137">**必須**</span><span class="sxs-lookup"><span data-stu-id="8ea4b-137">**Required**.</span></span>
<span data-ttu-id="8ea4b-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8ea4b-138">Content-Type</span></span> | <span data-ttu-id="8ea4b-139">string</span><span class="sxs-lookup"><span data-stu-id="8ea4b-139">string</span></span> | <span data-ttu-id="8ea4b-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="8ea4b-140">application/json.</span></span> <span data-ttu-id="8ea4b-141">**必須**</span><span class="sxs-lookup"><span data-stu-id="8ea4b-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8ea4b-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="8ea4b-142">Request body</span></span>
<span data-ttu-id="8ea4b-143">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="8ea4b-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ea4b-144">Parameter</span></span> | <span data-ttu-id="8ea4b-145">種類</span><span class="sxs-lookup"><span data-stu-id="8ea4b-145">Type</span></span>    | <span data-ttu-id="8ea4b-146">説明</span><span class="sxs-lookup"><span data-stu-id="8ea4b-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="8ea4b-147">コメント</span><span class="sxs-lookup"><span data-stu-id="8ea4b-147">Comment</span></span> |   <span data-ttu-id="8ea4b-148">文字列</span><span class="sxs-lookup"><span data-stu-id="8ea4b-148">String</span></span> |    <span data-ttu-id="8ea4b-149">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-149">Comment to associate with the action.</span></span> <span data-ttu-id="8ea4b-150">**必須**</span><span class="sxs-lookup"><span data-stu-id="8ea4b-150">**Required**.</span></span>
<span data-ttu-id="8ea4b-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="8ea4b-151">IsolationType</span></span>   | <span data-ttu-id="8ea4b-152">String</span><span class="sxs-lookup"><span data-stu-id="8ea4b-152">String</span></span> |  <span data-ttu-id="8ea4b-153">分離の種類。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-153">Type of the isolation.</span></span> <span data-ttu-id="8ea4b-154">使用できる値は、'Full' または '選択的' です。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="8ea4b-155">**IsolationType** は、実行する分離の種類を制御し、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="8ea4b-156">完全 – 完全分離</span><span class="sxs-lookup"><span data-stu-id="8ea4b-156">Full – Full isolation</span></span>
- <span data-ttu-id="8ea4b-157">選択的 – 制限された一連のアプリケーションだけがネットワークにアクセスを制限します (詳細については、「 [デバイス](respond-machine-alerts.md#isolate-devices-from-the-network) をネットワークから分離する」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="8ea4b-158">応答</span><span class="sxs-lookup"><span data-stu-id="8ea4b-158">Response</span></span>
<span data-ttu-id="8ea4b-159">成功した場合、このメソッドは応答本文に 201 - Created response code and [Machine Action](machineaction.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="8ea4b-160">例</span><span class="sxs-lookup"><span data-stu-id="8ea4b-160">Example</span></span>

<span data-ttu-id="8ea4b-161">**要求**</span><span class="sxs-lookup"><span data-stu-id="8ea4b-161">**Request**</span></span>

<span data-ttu-id="8ea4b-162">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="8ea4b-163">デバイスを分離から解放するには、「デバイスを分離 [から解放する」を参照してください](unisolate-machine.md)。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
