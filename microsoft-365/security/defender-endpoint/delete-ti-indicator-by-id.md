---
title: インジケーター API を削除します。
description: Delete Indicator API を使用して、Microsoft Defender for Endpoint の ID でインジケーター エンティティを削除する方法について説明します。
keywords: apis, public api, supported apis, delete, ti indicator, entity, id
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
ms.openlocfilehash: 1305be897dff6932713cf294eb4e5cd53692681c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167104"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="42c37-104">インジケーター API の削除</span><span class="sxs-lookup"><span data-stu-id="42c37-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="42c37-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="42c37-105">**Applies to:**</span></span>
- [<span data-ttu-id="42c37-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42c37-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="42c37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42c37-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="42c37-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="42c37-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="42c37-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="42c37-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="42c37-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="42c37-110">API description</span></span>
<span data-ttu-id="42c37-111">ID で [Indicator エンティティ](ti-indicator.md) を削除します。</span><span class="sxs-lookup"><span data-stu-id="42c37-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="42c37-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="42c37-112">Limitations</span></span>
1. <span data-ttu-id="42c37-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="42c37-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="42c37-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="42c37-114">Permissions</span></span>
<span data-ttu-id="42c37-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="42c37-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="42c37-116">アクセス許可の選択方法などの詳細については、「開始する」 [を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="42c37-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="42c37-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="42c37-117">Permission type</span></span> |   <span data-ttu-id="42c37-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="42c37-118">Permission</span></span>  |   <span data-ttu-id="42c37-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="42c37-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="42c37-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="42c37-120">Application</span></span> |   <span data-ttu-id="42c37-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="42c37-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="42c37-122">'TI インジケーターの読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="42c37-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="42c37-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="42c37-123">Application</span></span> |   <span data-ttu-id="42c37-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="42c37-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="42c37-125">'読み取りおよび書き込みインジケーター'</span><span class="sxs-lookup"><span data-stu-id="42c37-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="42c37-126">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="42c37-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="42c37-127">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="42c37-127">Request headers</span></span>

<span data-ttu-id="42c37-128">名前</span><span class="sxs-lookup"><span data-stu-id="42c37-128">Name</span></span> | <span data-ttu-id="42c37-129">種類</span><span class="sxs-lookup"><span data-stu-id="42c37-129">Type</span></span> | <span data-ttu-id="42c37-130">説明</span><span class="sxs-lookup"><span data-stu-id="42c37-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="42c37-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="42c37-131">Authorization</span></span> | <span data-ttu-id="42c37-132">文字列</span><span class="sxs-lookup"><span data-stu-id="42c37-132">String</span></span> | <span data-ttu-id="42c37-133">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="42c37-133">Bearer {token}.</span></span> <span data-ttu-id="42c37-134">**必須**</span><span class="sxs-lookup"><span data-stu-id="42c37-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="42c37-135">要求本文</span><span class="sxs-lookup"><span data-stu-id="42c37-135">Request body</span></span>
<span data-ttu-id="42c37-136">Empty</span><span class="sxs-lookup"><span data-stu-id="42c37-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="42c37-137">応答</span><span class="sxs-lookup"><span data-stu-id="42c37-137">Response</span></span>
<span data-ttu-id="42c37-138">Indicator が存在し、正常に削除された場合 - コンテンツなしで 204 OK。</span><span class="sxs-lookup"><span data-stu-id="42c37-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="42c37-139">指定した ID を持つインジケーターが見つからなかった場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="42c37-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="42c37-140">例</span><span class="sxs-lookup"><span data-stu-id="42c37-140">Example</span></span>

<span data-ttu-id="42c37-141">**要求**</span><span class="sxs-lookup"><span data-stu-id="42c37-141">**Request**</span></span>

<span data-ttu-id="42c37-142">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="42c37-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
