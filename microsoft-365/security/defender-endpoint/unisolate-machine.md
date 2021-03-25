---
title: 分離 API からデバイスを解放する
description: この API を使用して、デバイスを分離から解放するために関連する呼び出しを作成します。
keywords: apis、graph api、サポートされている api、分離からデバイスを削除する
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
ms.openlocfilehash: 036eb6f589c13fb9232557c45619829149179148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199335"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="6a2b1-104">分離 API からデバイスを解放する</span><span class="sxs-lookup"><span data-stu-id="6a2b1-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a2b1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6a2b1-105">**Applies to:**</span></span> 
- [<span data-ttu-id="6a2b1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6a2b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6a2b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a2b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="6a2b1-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6a2b1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a2b1-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6a2b1-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="6a2b1-110">API description</span></span>
<span data-ttu-id="6a2b1-111">デバイスの分離を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="6a2b1-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="6a2b1-112">Limitations</span></span>
1. <span data-ttu-id="6a2b1-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="6a2b1-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6a2b1-114">Permissions</span></span>
<span data-ttu-id="6a2b1-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6a2b1-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6a2b1-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6a2b1-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="6a2b1-117">Permission type</span></span> |   <span data-ttu-id="6a2b1-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6a2b1-118">Permission</span></span>  |   <span data-ttu-id="6a2b1-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="6a2b1-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6a2b1-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6a2b1-120">Application</span></span> |   <span data-ttu-id="6a2b1-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="6a2b1-121">Machine.Isolate</span></span> |   <span data-ttu-id="6a2b1-122">'分離マシン'</span><span class="sxs-lookup"><span data-stu-id="6a2b1-122">'Isolate machine'</span></span>
<span data-ttu-id="6a2b1-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="6a2b1-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="6a2b1-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="6a2b1-124">Machine.Isolate</span></span> |   <span data-ttu-id="6a2b1-125">'分離マシン'</span><span class="sxs-lookup"><span data-stu-id="6a2b1-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="6a2b1-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="6a2b1-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6a2b1-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)</span><span class="sxs-lookup"><span data-stu-id="6a2b1-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="6a2b1-128">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="6a2b1-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6a2b1-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="6a2b1-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="6a2b1-130">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6a2b1-130">Request headers</span></span>

<span data-ttu-id="6a2b1-131">名前</span><span class="sxs-lookup"><span data-stu-id="6a2b1-131">Name</span></span> | <span data-ttu-id="6a2b1-132">種類</span><span class="sxs-lookup"><span data-stu-id="6a2b1-132">Type</span></span> | <span data-ttu-id="6a2b1-133">説明</span><span class="sxs-lookup"><span data-stu-id="6a2b1-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="6a2b1-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="6a2b1-134">Authorization</span></span> | <span data-ttu-id="6a2b1-135">文字列</span><span class="sxs-lookup"><span data-stu-id="6a2b1-135">String</span></span> | <span data-ttu-id="6a2b1-136">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-136">Bearer {token}.</span></span> <span data-ttu-id="6a2b1-137">**必須**</span><span class="sxs-lookup"><span data-stu-id="6a2b1-137">**Required**.</span></span>
<span data-ttu-id="6a2b1-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6a2b1-138">Content-Type</span></span> | <span data-ttu-id="6a2b1-139">string</span><span class="sxs-lookup"><span data-stu-id="6a2b1-139">string</span></span> | <span data-ttu-id="6a2b1-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="6a2b1-140">application/json.</span></span> <span data-ttu-id="6a2b1-141">**必須**</span><span class="sxs-lookup"><span data-stu-id="6a2b1-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6a2b1-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="6a2b1-142">Request body</span></span>
<span data-ttu-id="6a2b1-143">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="6a2b1-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a2b1-144">Parameter</span></span> | <span data-ttu-id="6a2b1-145">種類</span><span class="sxs-lookup"><span data-stu-id="6a2b1-145">Type</span></span>    | <span data-ttu-id="6a2b1-146">説明</span><span class="sxs-lookup"><span data-stu-id="6a2b1-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="6a2b1-147">コメント</span><span class="sxs-lookup"><span data-stu-id="6a2b1-147">Comment</span></span> |   <span data-ttu-id="6a2b1-148">文字列</span><span class="sxs-lookup"><span data-stu-id="6a2b1-148">String</span></span> |    <span data-ttu-id="6a2b1-149">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-149">Comment to associate with the action.</span></span> <span data-ttu-id="6a2b1-150">**必須**</span><span class="sxs-lookup"><span data-stu-id="6a2b1-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="6a2b1-151">応答</span><span class="sxs-lookup"><span data-stu-id="6a2b1-151">Response</span></span>
<span data-ttu-id="6a2b1-152">成功した場合、このメソッドは応答本文に 201 - Created response code and [Machine Action](machineaction.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="6a2b1-153">例</span><span class="sxs-lookup"><span data-stu-id="6a2b1-153">Example</span></span>

<span data-ttu-id="6a2b1-154">**要求**</span><span class="sxs-lookup"><span data-stu-id="6a2b1-154">**Request**</span></span>

<span data-ttu-id="6a2b1-155">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="6a2b1-156">デバイスを分離するには、「デバイスを分離 [する」を参照してください](isolate-machine.md)。</span><span class="sxs-lookup"><span data-stu-id="6a2b1-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

