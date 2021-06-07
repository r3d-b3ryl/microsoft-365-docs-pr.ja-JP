---
title: ID API によるアラート情報の取得
description: ID API によるアラート情報の取得を使用して、Microsoft Defender for Endpoint の ID で特定のアラートを取得する方法について説明します。
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
ms.openlocfilehash: b9de7645abc59849b3ca28f64904b0ba49d4eef5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771899"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="5556c-104">ID API によるアラート情報の取得</span><span class="sxs-lookup"><span data-stu-id="5556c-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5556c-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5556c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="5556c-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="5556c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5556c-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="5556c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5556c-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="5556c-108">API description</span></span>
<span data-ttu-id="5556c-109">ID によって特定 [のアラート](alerts.md) を取得します。</span><span class="sxs-lookup"><span data-stu-id="5556c-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="5556c-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="5556c-110">Limitations</span></span>
1. <span data-ttu-id="5556c-111">構成済みの保持期間に従って、最後に更新されたアラートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="5556c-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="5556c-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="5556c-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5556c-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5556c-113">Permissions</span></span>
<span data-ttu-id="5556c-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="5556c-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5556c-115">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5556c-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5556c-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="5556c-116">Permission type</span></span> |   <span data-ttu-id="5556c-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5556c-117">Permission</span></span>  |   <span data-ttu-id="5556c-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="5556c-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5556c-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5556c-119">Application</span></span> |   <span data-ttu-id="5556c-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="5556c-120">Alert.Read.All</span></span> |    <span data-ttu-id="5556c-121">'すべてのアラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="5556c-121">'Read all alerts'</span></span>
<span data-ttu-id="5556c-122">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5556c-122">Application</span></span> |   <span data-ttu-id="5556c-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5556c-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="5556c-124">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="5556c-124">'Read and write all alerts'</span></span>
<span data-ttu-id="5556c-125">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="5556c-125">Delegated (work or school account)</span></span> | <span data-ttu-id="5556c-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="5556c-126">Alert.Read</span></span> | <span data-ttu-id="5556c-127">'アラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="5556c-127">'Read alerts'</span></span>
<span data-ttu-id="5556c-128">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="5556c-128">Delegated (work or school account)</span></span> | <span data-ttu-id="5556c-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5556c-129">Alert.ReadWrite</span></span> | <span data-ttu-id="5556c-130">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="5556c-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="5556c-131">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="5556c-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5556c-132">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="5556c-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5556c-133">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="5556c-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5556c-134">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="5556c-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="5556c-135">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="5556c-135">Request headers</span></span>

<span data-ttu-id="5556c-136">名前</span><span class="sxs-lookup"><span data-stu-id="5556c-136">Name</span></span> | <span data-ttu-id="5556c-137">種類</span><span class="sxs-lookup"><span data-stu-id="5556c-137">Type</span></span> | <span data-ttu-id="5556c-138">説明</span><span class="sxs-lookup"><span data-stu-id="5556c-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="5556c-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="5556c-139">Authorization</span></span> | <span data-ttu-id="5556c-140">String</span><span class="sxs-lookup"><span data-stu-id="5556c-140">String</span></span> | <span data-ttu-id="5556c-141">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="5556c-141">Bearer {token}.</span></span> <span data-ttu-id="5556c-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="5556c-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5556c-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="5556c-143">Request body</span></span>
<span data-ttu-id="5556c-144">Empty</span><span class="sxs-lookup"><span data-stu-id="5556c-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5556c-145">応答</span><span class="sxs-lookup"><span data-stu-id="5556c-145">Response</span></span>
<span data-ttu-id="5556c-146">成功した場合、このメソッドは 200 OK を返し、応答本文の [アラート](alerts.md) エンティティを返します。</span><span class="sxs-lookup"><span data-stu-id="5556c-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="5556c-147">指定された ID を持つアラートが見つからなかった場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="5556c-147">If alert with the specified id was not found - 404 Not Found.</span></span>
