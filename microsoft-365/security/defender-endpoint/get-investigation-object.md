---
title: 調査オブジェクト API の取得
description: この API を使用して、Investigation オブジェクトの取得に関連する呼び出しを作成する
keywords: apis, graph api, supported apis, Investigation オブジェクト
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770135"
---
# <a name="get-investigation-api"></a><span data-ttu-id="5ba4e-104">調査 API の取得</span><span class="sxs-lookup"><span data-stu-id="5ba4e-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ba4e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5ba4e-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ba4e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5ba4e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ba4e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ba4e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5ba4e-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="5ba4e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5ba4e-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="5ba4e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5ba4e-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="5ba4e-110">API description</span></span>
<span data-ttu-id="5ba4e-111">ID によって特定 [の調査](investigation.md) を取得します。</span><span class="sxs-lookup"><span data-stu-id="5ba4e-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="5ba4e-112">ID には、調査 ID またはアラート ID をトリガーする調査を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5ba4e-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="5ba4e-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="5ba4e-113">Limitations</span></span>
1. <span data-ttu-id="5ba4e-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="5ba4e-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5ba4e-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5ba4e-115">Permissions</span></span>
<span data-ttu-id="5ba4e-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ba4e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5ba4e-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5ba4e-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5ba4e-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="5ba4e-118">Permission type</span></span> |   <span data-ttu-id="5ba4e-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5ba4e-119">Permission</span></span>  |   <span data-ttu-id="5ba4e-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="5ba4e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5ba4e-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5ba4e-121">Application</span></span> |   <span data-ttu-id="5ba4e-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="5ba4e-122">Alert.Read.All</span></span> |    <span data-ttu-id="5ba4e-123">'すべてのアラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="5ba4e-123">'Read all alerts'</span></span>
<span data-ttu-id="5ba4e-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5ba4e-124">Application</span></span> |   <span data-ttu-id="5ba4e-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5ba4e-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="5ba4e-126">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="5ba4e-126">'Read and write all alerts'</span></span>
<span data-ttu-id="5ba4e-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="5ba4e-127">Delegated (work or school account)</span></span> | <span data-ttu-id="5ba4e-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="5ba4e-128">Alert.Read</span></span> | <span data-ttu-id="5ba4e-129">'アラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="5ba4e-129">'Read alerts'</span></span>
<span data-ttu-id="5ba4e-130">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="5ba4e-130">Delegated (work or school account)</span></span> | <span data-ttu-id="5ba4e-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5ba4e-131">Alert.ReadWrite</span></span> | <span data-ttu-id="5ba4e-132">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="5ba4e-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="5ba4e-133">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="5ba4e-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5ba4e-134">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="5ba4e-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5ba4e-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="5ba4e-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="5ba4e-136">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="5ba4e-136">Request headers</span></span>

<span data-ttu-id="5ba4e-137">名前</span><span class="sxs-lookup"><span data-stu-id="5ba4e-137">Name</span></span> | <span data-ttu-id="5ba4e-138">種類</span><span class="sxs-lookup"><span data-stu-id="5ba4e-138">Type</span></span> | <span data-ttu-id="5ba4e-139">説明</span><span class="sxs-lookup"><span data-stu-id="5ba4e-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="5ba4e-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="5ba4e-140">Authorization</span></span> | <span data-ttu-id="5ba4e-141">String</span><span class="sxs-lookup"><span data-stu-id="5ba4e-141">String</span></span> | <span data-ttu-id="5ba4e-142">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="5ba4e-142">Bearer {token}.</span></span> <span data-ttu-id="5ba4e-143">**必須**</span><span class="sxs-lookup"><span data-stu-id="5ba4e-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5ba4e-144">要求本文</span><span class="sxs-lookup"><span data-stu-id="5ba4e-144">Request body</span></span>
<span data-ttu-id="5ba4e-145">Empty</span><span class="sxs-lookup"><span data-stu-id="5ba4e-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5ba4e-146">応答</span><span class="sxs-lookup"><span data-stu-id="5ba4e-146">Response</span></span>
<span data-ttu-id="5ba4e-147">成功した場合、このメソッドは 200 Ok 応答コードを [Investigations エンティティと一緒に返](investigation.md) します。</span><span class="sxs-lookup"><span data-stu-id="5ba4e-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

