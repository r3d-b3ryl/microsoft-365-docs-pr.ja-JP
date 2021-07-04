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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289921"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="02e03-104">インジケーター API の削除</span><span class="sxs-lookup"><span data-stu-id="02e03-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02e03-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="02e03-105">**Applies to:**</span></span>
- [<span data-ttu-id="02e03-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="02e03-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02e03-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02e03-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="02e03-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="02e03-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="02e03-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="02e03-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="02e03-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="02e03-110">API description</span></span>

<span data-ttu-id="02e03-111">ID で [Indicator エンティティ](ti-indicator.md) を削除します。</span><span class="sxs-lookup"><span data-stu-id="02e03-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="02e03-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="02e03-112">Limitations</span></span>

<span data-ttu-id="02e03-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="02e03-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="02e03-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="02e03-114">Permissions</span></span>

<span data-ttu-id="02e03-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="02e03-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="02e03-116">アクセス許可の選択方法などの詳細については、「開始する」 [を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="02e03-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="02e03-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="02e03-117">Permission type</span></span> | <span data-ttu-id="02e03-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="02e03-118">Permission</span></span> | <span data-ttu-id="02e03-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="02e03-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="02e03-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="02e03-120">Application</span></span> | <span data-ttu-id="02e03-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="02e03-121">Ti.ReadWrite</span></span> | <span data-ttu-id="02e03-122">'TI インジケーターの読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="02e03-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="02e03-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="02e03-123">Application</span></span> | <span data-ttu-id="02e03-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="02e03-124">Ti.ReadWrite.All</span></span> | <span data-ttu-id="02e03-125">'読み取りおよび書き込みインジケーター'</span><span class="sxs-lookup"><span data-stu-id="02e03-125">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="02e03-126">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="02e03-126">HTTP request</span></span>

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="02e03-127">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="02e03-127">Request headers</span></span>

<span data-ttu-id="02e03-128">名前</span><span class="sxs-lookup"><span data-stu-id="02e03-128">Name</span></span> | <span data-ttu-id="02e03-129">種類</span><span class="sxs-lookup"><span data-stu-id="02e03-129">Type</span></span> | <span data-ttu-id="02e03-130">説明</span><span class="sxs-lookup"><span data-stu-id="02e03-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="02e03-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="02e03-131">Authorization</span></span> | <span data-ttu-id="02e03-132">String</span><span class="sxs-lookup"><span data-stu-id="02e03-132">String</span></span> | <span data-ttu-id="02e03-133">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="02e03-133">Bearer {token}.</span></span> <span data-ttu-id="02e03-134">**必須**</span><span class="sxs-lookup"><span data-stu-id="02e03-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="02e03-135">要求本文</span><span class="sxs-lookup"><span data-stu-id="02e03-135">Request body</span></span>

<span data-ttu-id="02e03-136">Empty</span><span class="sxs-lookup"><span data-stu-id="02e03-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="02e03-137">応答</span><span class="sxs-lookup"><span data-stu-id="02e03-137">Response</span></span>

<span data-ttu-id="02e03-138">Indicator が存在し、正常に削除された場合 - コンテンツなしで 204 OK。</span><span class="sxs-lookup"><span data-stu-id="02e03-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>

<span data-ttu-id="02e03-139">指定した ID を持つインジケーターが見つからなかった場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="02e03-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="02e03-140">例</span><span class="sxs-lookup"><span data-stu-id="02e03-140">Example</span></span>

### <a name="request"></a><span data-ttu-id="02e03-141">要求</span><span class="sxs-lookup"><span data-stu-id="02e03-141">Request</span></span>

<span data-ttu-id="02e03-142">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="02e03-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
