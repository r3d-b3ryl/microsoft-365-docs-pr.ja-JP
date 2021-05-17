---
title: 調査パッケージ API の収集
description: この API を使用して、デバイスからの調査パッケージの収集に関連する呼び出しを作成します。
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
ms.openlocfilehash: 1e24236aae1922705c1711042f0426251a979ede
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167080"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="c8bd2-104">調査パッケージ API の収集</span><span class="sxs-lookup"><span data-stu-id="c8bd2-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8bd2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c8bd2-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8bd2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c8bd2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8bd2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8bd2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="c8bd2-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="c8bd2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c8bd2-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c8bd2-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="c8bd2-110">API description</span></span>
<span data-ttu-id="c8bd2-111">デバイスから調査パッケージを収集します。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="c8bd2-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="c8bd2-112">Limitations</span></span>
1. <span data-ttu-id="c8bd2-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c8bd2-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c8bd2-114">Permissions</span></span>
<span data-ttu-id="c8bd2-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c8bd2-116">アクセス許可の選択方法などの詳細については [、「Use Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c8bd2-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c8bd2-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="c8bd2-117">Permission type</span></span> |   <span data-ttu-id="c8bd2-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c8bd2-118">Permission</span></span>  |   <span data-ttu-id="c8bd2-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="c8bd2-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c8bd2-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8bd2-120">Application</span></span> |   <span data-ttu-id="c8bd2-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="c8bd2-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="c8bd2-122">'collect forensics'</span><span class="sxs-lookup"><span data-stu-id="c8bd2-122">'Collect forensics'</span></span>
<span data-ttu-id="c8bd2-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="c8bd2-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="c8bd2-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="c8bd2-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="c8bd2-125">'collect forensics'</span><span class="sxs-lookup"><span data-stu-id="c8bd2-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="c8bd2-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="c8bd2-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c8bd2-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Alerts Investigation' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="c8bd2-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c8bd2-128">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="c8bd2-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c8bd2-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="c8bd2-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="c8bd2-130">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="c8bd2-130">Request headers</span></span>

<span data-ttu-id="c8bd2-131">名前</span><span class="sxs-lookup"><span data-stu-id="c8bd2-131">Name</span></span> | <span data-ttu-id="c8bd2-132">型</span><span class="sxs-lookup"><span data-stu-id="c8bd2-132">Type</span></span> | <span data-ttu-id="c8bd2-133">説明</span><span class="sxs-lookup"><span data-stu-id="c8bd2-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="c8bd2-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="c8bd2-134">Authorization</span></span> | <span data-ttu-id="c8bd2-135">String</span><span class="sxs-lookup"><span data-stu-id="c8bd2-135">String</span></span> | <span data-ttu-id="c8bd2-136">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-136">Bearer {token}.</span></span> <span data-ttu-id="c8bd2-137">**必須**</span><span class="sxs-lookup"><span data-stu-id="c8bd2-137">**Required**.</span></span>
<span data-ttu-id="c8bd2-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c8bd2-138">Content-Type</span></span> | <span data-ttu-id="c8bd2-139">string</span><span class="sxs-lookup"><span data-stu-id="c8bd2-139">string</span></span> | <span data-ttu-id="c8bd2-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="c8bd2-140">application/json.</span></span> <span data-ttu-id="c8bd2-141">**必須**</span><span class="sxs-lookup"><span data-stu-id="c8bd2-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c8bd2-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="c8bd2-142">Request body</span></span>
<span data-ttu-id="c8bd2-143">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c8bd2-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8bd2-144">Parameter</span></span> | <span data-ttu-id="c8bd2-145">型</span><span class="sxs-lookup"><span data-stu-id="c8bd2-145">Type</span></span>    | <span data-ttu-id="c8bd2-146">説明</span><span class="sxs-lookup"><span data-stu-id="c8bd2-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="c8bd2-147">コメント</span><span class="sxs-lookup"><span data-stu-id="c8bd2-147">Comment</span></span> |   <span data-ttu-id="c8bd2-148">文字列</span><span class="sxs-lookup"><span data-stu-id="c8bd2-148">String</span></span> |    <span data-ttu-id="c8bd2-149">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-149">Comment to associate with the action.</span></span> <span data-ttu-id="c8bd2-150">**必須**</span><span class="sxs-lookup"><span data-stu-id="c8bd2-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c8bd2-151">応答</span><span class="sxs-lookup"><span data-stu-id="c8bd2-151">Response</span></span>
<span data-ttu-id="c8bd2-152">成功した場合、このメソッドは応答本文に 201 - Created response code and [Machine Action](machineaction.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="c8bd2-153">例</span><span class="sxs-lookup"><span data-stu-id="c8bd2-153">Example</span></span>

<span data-ttu-id="c8bd2-154">**要求**</span><span class="sxs-lookup"><span data-stu-id="c8bd2-154">**Request**</span></span>

<span data-ttu-id="c8bd2-155">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="c8bd2-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
