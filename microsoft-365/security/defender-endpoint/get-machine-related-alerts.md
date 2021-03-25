---
title: コンピューター関連のアラート API を取得する
description: Get machine 関連のアラート API を使用して、Microsoft Defender for Endpoint の特定のデバイスに関連するすべてのアラートを取得する方法について説明します。
keywords: apis, graph api, サポートされている API, get, デバイス, 関連, アラート
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199253"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="6374f-104">コンピューター関連のアラート API を取得する</span><span class="sxs-lookup"><span data-stu-id="6374f-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6374f-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6374f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6374f-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6374f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6374f-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6374f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="6374f-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="6374f-108">API description</span></span>
<span data-ttu-id="6374f-109">特定のデバイスに [関連付](alerts.md) なすべてのアラートを取得します。</span><span class="sxs-lookup"><span data-stu-id="6374f-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="6374f-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="6374f-110">Limitations</span></span>
1. <span data-ttu-id="6374f-111">構成済みの保持期間に従って、最後に更新されたデバイスに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6374f-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="6374f-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="6374f-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="6374f-113">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="6374f-113">Permission type</span></span> |   <span data-ttu-id="6374f-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6374f-114">Permission</span></span>  |   <span data-ttu-id="6374f-115">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="6374f-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6374f-116">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6374f-116">Application</span></span> |   <span data-ttu-id="6374f-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="6374f-117">Alert.Read.All</span></span> |    <span data-ttu-id="6374f-118">'すべてのアラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="6374f-118">'Read all alerts'</span></span>
<span data-ttu-id="6374f-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6374f-119">Application</span></span> |   <span data-ttu-id="6374f-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6374f-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="6374f-121">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="6374f-121">'Read and write all alerts'</span></span>
<span data-ttu-id="6374f-122">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="6374f-122">Delegated (work or school account)</span></span> | <span data-ttu-id="6374f-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="6374f-123">Alert.Read</span></span> | <span data-ttu-id="6374f-124">'アラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="6374f-124">'Read alerts'</span></span>
<span data-ttu-id="6374f-125">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="6374f-125">Delegated (work or school account)</span></span> | <span data-ttu-id="6374f-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6374f-126">Alert.ReadWrite</span></span> | <span data-ttu-id="6374f-127">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="6374f-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="6374f-128">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="6374f-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6374f-129">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="6374f-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="6374f-130">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="6374f-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6374f-131">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="6374f-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="6374f-132">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6374f-132">Request headers</span></span>

<span data-ttu-id="6374f-133">名前</span><span class="sxs-lookup"><span data-stu-id="6374f-133">Name</span></span> | <span data-ttu-id="6374f-134">種類</span><span class="sxs-lookup"><span data-stu-id="6374f-134">Type</span></span> | <span data-ttu-id="6374f-135">説明</span><span class="sxs-lookup"><span data-stu-id="6374f-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="6374f-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="6374f-136">Authorization</span></span> | <span data-ttu-id="6374f-137">文字列</span><span class="sxs-lookup"><span data-stu-id="6374f-137">String</span></span> | <span data-ttu-id="6374f-138">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="6374f-138">Bearer {token}.</span></span> <span data-ttu-id="6374f-139">**必須**</span><span class="sxs-lookup"><span data-stu-id="6374f-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6374f-140">要求本文</span><span class="sxs-lookup"><span data-stu-id="6374f-140">Request body</span></span>
<span data-ttu-id="6374f-141">Empty</span><span class="sxs-lookup"><span data-stu-id="6374f-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6374f-142">応答</span><span class="sxs-lookup"><span data-stu-id="6374f-142">Response</span></span>
<span data-ttu-id="6374f-143">成功し、デバイスが存在する場合 - 本文のアラート[](alerts.md)エンティティの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="6374f-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="6374f-144">デバイスが見つからなかった場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="6374f-144">If device was not found - 404 Not Found.</span></span>
