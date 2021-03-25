---
title: 調査 API の開始
description: この API を使用して、デバイスの調査を開始します。
keywords: apis, graph api, サポートされている API, 調査
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
ms.openlocfilehash: 4bdbfbb20f3abb9829b2c8be83b9eaa6ec92cde7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187225"
---
# <a name="start-investigation-api"></a><span data-ttu-id="339d1-104">調査 API の開始</span><span class="sxs-lookup"><span data-stu-id="339d1-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="339d1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="339d1-105">**Applies to:**</span></span>
- [<span data-ttu-id="339d1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="339d1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="339d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="339d1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="339d1-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="339d1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="339d1-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="339d1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="339d1-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="339d1-110">API description</span></span>
<span data-ttu-id="339d1-111">デバイスで自動調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="339d1-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="339d1-112">詳細 [については、「自動調査の概要](automated-investigations.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="339d1-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="339d1-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="339d1-113">Limitations</span></span>
1. <span data-ttu-id="339d1-114">この API のレート制限は、1 時間あたり 50 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="339d1-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="339d1-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="339d1-115">Permissions</span></span>
<span data-ttu-id="339d1-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="339d1-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="339d1-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="339d1-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="339d1-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="339d1-118">Permission type</span></span> |   <span data-ttu-id="339d1-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="339d1-119">Permission</span></span>  |   <span data-ttu-id="339d1-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="339d1-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="339d1-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="339d1-121">Application</span></span> |   <span data-ttu-id="339d1-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="339d1-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="339d1-123">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="339d1-123">'Read and write all alerts'</span></span>
<span data-ttu-id="339d1-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="339d1-124">Delegated (work or school account)</span></span> | <span data-ttu-id="339d1-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="339d1-125">Alert.ReadWrite</span></span> | <span data-ttu-id="339d1-126">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="339d1-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="339d1-127">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="339d1-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="339d1-128">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)</span><span class="sxs-lookup"><span data-stu-id="339d1-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="339d1-129">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="339d1-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="339d1-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="339d1-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="339d1-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="339d1-131">Request headers</span></span>

<span data-ttu-id="339d1-132">名前</span><span class="sxs-lookup"><span data-stu-id="339d1-132">Name</span></span> | <span data-ttu-id="339d1-133">種類</span><span class="sxs-lookup"><span data-stu-id="339d1-133">Type</span></span> | <span data-ttu-id="339d1-134">説明</span><span class="sxs-lookup"><span data-stu-id="339d1-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="339d1-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="339d1-135">Authorization</span></span> | <span data-ttu-id="339d1-136">文字列</span><span class="sxs-lookup"><span data-stu-id="339d1-136">String</span></span> | <span data-ttu-id="339d1-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="339d1-137">Bearer {token}.</span></span> <span data-ttu-id="339d1-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="339d1-138">**Required**.</span></span>
<span data-ttu-id="339d1-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="339d1-139">Content-Type</span></span> | <span data-ttu-id="339d1-140">string</span><span class="sxs-lookup"><span data-stu-id="339d1-140">string</span></span> | <span data-ttu-id="339d1-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="339d1-141">application/json.</span></span> <span data-ttu-id="339d1-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="339d1-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="339d1-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="339d1-143">Request body</span></span>
<span data-ttu-id="339d1-144">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="339d1-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="339d1-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="339d1-145">Parameter</span></span> | <span data-ttu-id="339d1-146">種類</span><span class="sxs-lookup"><span data-stu-id="339d1-146">Type</span></span>    | <span data-ttu-id="339d1-147">説明</span><span class="sxs-lookup"><span data-stu-id="339d1-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="339d1-148">コメント</span><span class="sxs-lookup"><span data-stu-id="339d1-148">Comment</span></span> |   <span data-ttu-id="339d1-149">文字列</span><span class="sxs-lookup"><span data-stu-id="339d1-149">String</span></span> |    <span data-ttu-id="339d1-150">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="339d1-150">Comment to associate with the action.</span></span> <span data-ttu-id="339d1-151">**必須**</span><span class="sxs-lookup"><span data-stu-id="339d1-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="339d1-152">応答</span><span class="sxs-lookup"><span data-stu-id="339d1-152">Response</span></span>
<span data-ttu-id="339d1-153">成功した場合、このメソッドは 201 - 作成された応答コードと [応答本文の調査](investigation.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="339d1-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="339d1-154">例</span><span class="sxs-lookup"><span data-stu-id="339d1-154">Example</span></span>

<span data-ttu-id="339d1-155">**要求**</span><span class="sxs-lookup"><span data-stu-id="339d1-155">**Request**</span></span>

<span data-ttu-id="339d1-156">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="339d1-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
