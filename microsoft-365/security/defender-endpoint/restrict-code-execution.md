---
title: アプリの実行 API の制限
description: この API を使用して、アプリケーションの実行制限に関連する呼び出しを作成します。
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
ms.openlocfilehash: 149f3aefd963f15eafa15030a322ec588c0615ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186783"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="7a3c0-104">アプリの実行 API の制限</span><span class="sxs-lookup"><span data-stu-id="7a3c0-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7a3c0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7a3c0-105">**Applies to:**</span></span>
- [<span data-ttu-id="7a3c0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7a3c0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7a3c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a3c0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="7a3c0-108">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7a3c0-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7a3c0-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="7a3c0-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7a3c0-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="7a3c0-111">API の説明</span><span class="sxs-lookup"><span data-stu-id="7a3c0-111">API description</span></span>
<span data-ttu-id="7a3c0-112">定義済みのセットを除くデバイス上のすべてのアプリケーションの実行を制限します。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="7a3c0-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="7a3c0-113">Limitations</span></span>
1. <span data-ttu-id="7a3c0-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="7a3c0-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7a3c0-115">Permissions</span></span>
<span data-ttu-id="7a3c0-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7a3c0-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7a3c0-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7a3c0-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="7a3c0-118">Permission type</span></span> |   <span data-ttu-id="7a3c0-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7a3c0-119">Permission</span></span>  |   <span data-ttu-id="7a3c0-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="7a3c0-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7a3c0-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7a3c0-121">Application</span></span> |   <span data-ttu-id="7a3c0-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="7a3c0-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="7a3c0-123">'コードの実行を制限する'</span><span class="sxs-lookup"><span data-stu-id="7a3c0-123">'Restrict code execution'</span></span>
<span data-ttu-id="7a3c0-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="7a3c0-124">Delegated (work or school account)</span></span> | <span data-ttu-id="7a3c0-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="7a3c0-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="7a3c0-126">'コードの実行を制限する'</span><span class="sxs-lookup"><span data-stu-id="7a3c0-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="7a3c0-127">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="7a3c0-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7a3c0-128">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)</span><span class="sxs-lookup"><span data-stu-id="7a3c0-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="7a3c0-129">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="7a3c0-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7a3c0-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="7a3c0-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="7a3c0-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="7a3c0-131">Request headers</span></span>

<span data-ttu-id="7a3c0-132">名前</span><span class="sxs-lookup"><span data-stu-id="7a3c0-132">Name</span></span> | <span data-ttu-id="7a3c0-133">型</span><span class="sxs-lookup"><span data-stu-id="7a3c0-133">Type</span></span> | <span data-ttu-id="7a3c0-134">説明</span><span class="sxs-lookup"><span data-stu-id="7a3c0-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="7a3c0-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="7a3c0-135">Authorization</span></span> | <span data-ttu-id="7a3c0-136">String</span><span class="sxs-lookup"><span data-stu-id="7a3c0-136">String</span></span> | <span data-ttu-id="7a3c0-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-137">Bearer {token}.</span></span> <span data-ttu-id="7a3c0-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="7a3c0-138">**Required**.</span></span>
<span data-ttu-id="7a3c0-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="7a3c0-139">Content-Type</span></span> | <span data-ttu-id="7a3c0-140">string</span><span class="sxs-lookup"><span data-stu-id="7a3c0-140">string</span></span> | <span data-ttu-id="7a3c0-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="7a3c0-141">application/json.</span></span> <span data-ttu-id="7a3c0-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="7a3c0-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7a3c0-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="7a3c0-143">Request body</span></span>
<span data-ttu-id="7a3c0-144">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="7a3c0-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a3c0-145">Parameter</span></span> | <span data-ttu-id="7a3c0-146">型</span><span class="sxs-lookup"><span data-stu-id="7a3c0-146">Type</span></span>    | <span data-ttu-id="7a3c0-147">説明</span><span class="sxs-lookup"><span data-stu-id="7a3c0-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="7a3c0-148">コメント</span><span class="sxs-lookup"><span data-stu-id="7a3c0-148">Comment</span></span> |   <span data-ttu-id="7a3c0-149">文字列</span><span class="sxs-lookup"><span data-stu-id="7a3c0-149">String</span></span> |    <span data-ttu-id="7a3c0-150">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-150">Comment to associate with the action.</span></span> <span data-ttu-id="7a3c0-151">**必須**</span><span class="sxs-lookup"><span data-stu-id="7a3c0-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="7a3c0-152">応答</span><span class="sxs-lookup"><span data-stu-id="7a3c0-152">Response</span></span>
<span data-ttu-id="7a3c0-153">成功した場合、このメソッドは応答本文に 201 - Created response code and [Machine Action](machineaction.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="7a3c0-154">例</span><span class="sxs-lookup"><span data-stu-id="7a3c0-154">Example</span></span>

<span data-ttu-id="7a3c0-155">**要求**</span><span class="sxs-lookup"><span data-stu-id="7a3c0-155">**Request**</span></span>

<span data-ttu-id="7a3c0-156">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="7a3c0-157">デバイスからコード実行制限を削除するには、「アプリの制限を [削除する」を参照してください](unrestrict-code-execution.md)。</span><span class="sxs-lookup"><span data-stu-id="7a3c0-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
