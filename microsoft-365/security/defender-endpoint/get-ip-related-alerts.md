---
title: IP 関連のアラート API を取得する
description: エンドポイント用 Microsoft Defender を使用して、特定の IP アドレスに関連するアラートのコレクションを取得する
keywords: apis, graph api, supported apis, get, ip, related, alerts
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
ms.openlocfilehash: dbcde70b32f9a10280dd43e98c5a237a0027a33c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167188"
---
# <a name="get-ip-related-alerts-api"></a><span data-ttu-id="1187c-104">IP 関連のアラート API を取得する</span><span class="sxs-lookup"><span data-stu-id="1187c-104">Get IP related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1187c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1187c-105">**Applies to:**</span></span>
- [<span data-ttu-id="1187c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1187c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1187c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1187c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1187c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1187c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1187c-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="1187c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1187c-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="1187c-110">API description</span></span>
<span data-ttu-id="1187c-111">特定の IP アドレスに関連するアラートのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="1187c-111">Retrieves a collection of alerts related to a given IP address.</span></span>


## <a name="limitations"></a><span data-ttu-id="1187c-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="1187c-112">Limitations</span></span>
1. <span data-ttu-id="1187c-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="1187c-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1187c-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1187c-114">Permissions</span></span>
<span data-ttu-id="1187c-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="1187c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1187c-116">アクセス許可の選択方法などの詳細については [、「Use Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1187c-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1187c-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="1187c-117">Permission type</span></span> |   <span data-ttu-id="1187c-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1187c-118">Permission</span></span>  |   <span data-ttu-id="1187c-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="1187c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1187c-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1187c-120">Application</span></span> |   <span data-ttu-id="1187c-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="1187c-121">Alert.Read.All</span></span> |    <span data-ttu-id="1187c-122">'すべてのアラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="1187c-122">'Read all alerts'</span></span>
<span data-ttu-id="1187c-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1187c-123">Application</span></span> |   <span data-ttu-id="1187c-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1187c-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="1187c-125">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="1187c-125">'Read and write all alerts'</span></span>
<span data-ttu-id="1187c-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="1187c-126">Delegated (work or school account)</span></span> | <span data-ttu-id="1187c-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="1187c-127">Alert.Read</span></span> | <span data-ttu-id="1187c-128">'アラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="1187c-128">'Read alerts'</span></span>
<span data-ttu-id="1187c-129">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="1187c-129">Delegated (work or school account)</span></span> | <span data-ttu-id="1187c-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1187c-130">Alert.ReadWrite</span></span> | <span data-ttu-id="1187c-131">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="1187c-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="1187c-132">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="1187c-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1187c-133">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="1187c-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="1187c-134">応答には、デバイス グループ設定に基づいて、ユーザーがアクセスできるデバイスに関連付けられたアラートだけが含まれます[](machine-groups.md)(詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="1187c-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1187c-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="1187c-135">HTTP request</span></span>
```
GET /api/ips/{ip}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="1187c-136">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1187c-136">Request headers</span></span>

<span data-ttu-id="1187c-137">名前</span><span class="sxs-lookup"><span data-stu-id="1187c-137">Name</span></span> | <span data-ttu-id="1187c-138">種類</span><span class="sxs-lookup"><span data-stu-id="1187c-138">Type</span></span> | <span data-ttu-id="1187c-139">説明</span><span class="sxs-lookup"><span data-stu-id="1187c-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="1187c-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="1187c-140">Authorization</span></span> | <span data-ttu-id="1187c-141">文字列</span><span class="sxs-lookup"><span data-stu-id="1187c-141">String</span></span> | <span data-ttu-id="1187c-142">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="1187c-142">Bearer {token}.</span></span> <span data-ttu-id="1187c-143">**必須**</span><span class="sxs-lookup"><span data-stu-id="1187c-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1187c-144">要求本文</span><span class="sxs-lookup"><span data-stu-id="1187c-144">Request body</span></span>
<span data-ttu-id="1187c-145">Empty</span><span class="sxs-lookup"><span data-stu-id="1187c-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1187c-146">応答</span><span class="sxs-lookup"><span data-stu-id="1187c-146">Response</span></span>
<span data-ttu-id="1187c-147">成功した場合と IP が存在する場合 -[](alerts.md)本文のアラート エンティティの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="1187c-147">If successful and IP exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="1187c-148">IP が存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="1187c-148">If IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="1187c-149">例</span><span class="sxs-lookup"><span data-stu-id="1187c-149">Example</span></span>

<span data-ttu-id="1187c-150">**要求**</span><span class="sxs-lookup"><span data-stu-id="1187c-150">**Request**</span></span>

<span data-ttu-id="1187c-151">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="1187c-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/alerts
```
