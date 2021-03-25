---
title: アラート関連のドメイン情報を取得する
description: Microsoft Defender for Endpoint を使用して、特定のアラートに関連するすべてのドメインを取得します。
keywords: apis、graph api、サポートされている API、アラート情報の取得、アラート情報、関連ドメイン
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
ms.openlocfilehash: 0cb09b23df8243d970069d087976ddc79394b67d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200415"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="915e5-104">アラート関連のドメイン情報 API を取得する</span><span class="sxs-lookup"><span data-stu-id="915e5-104">Get alert related domain information API</span></span>

<span data-ttu-id="915e5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="915e5-105">**Applies to:**</span></span> 
- [<span data-ttu-id="915e5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="915e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="915e5-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="915e5-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="915e5-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="915e5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="915e5-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="915e5-109">API description</span></span>
<span data-ttu-id="915e5-110">特定のアラートに関連するすべてのドメインを取得します。</span><span class="sxs-lookup"><span data-stu-id="915e5-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="915e5-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="915e5-111">Limitations</span></span>
1. <span data-ttu-id="915e5-112">構成済みの保持期間に従って、最後に更新されたアラートに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="915e5-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="915e5-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="915e5-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="915e5-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="915e5-114">Permissions</span></span>
<span data-ttu-id="915e5-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="915e5-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="915e5-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="915e5-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="915e5-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="915e5-117">Permission type</span></span> | <span data-ttu-id="915e5-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="915e5-118">Permission</span></span> | <span data-ttu-id="915e5-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="915e5-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="915e5-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="915e5-120">Application</span></span> | <span data-ttu-id="915e5-121">URL。Read.All</span><span class="sxs-lookup"><span data-stu-id="915e5-121">URL.Read.All</span></span> | <span data-ttu-id="915e5-122">'URL の読み取り'</span><span class="sxs-lookup"><span data-stu-id="915e5-122">'Read URLs'</span></span>
<span data-ttu-id="915e5-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="915e5-123">Delegated (work or school account)</span></span> | <span data-ttu-id="915e5-124">URL。Read.All</span><span class="sxs-lookup"><span data-stu-id="915e5-124">URL.Read.All</span></span> | <span data-ttu-id="915e5-125">'URL の読み取り'</span><span class="sxs-lookup"><span data-stu-id="915e5-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="915e5-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="915e5-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="915e5-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="915e5-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="915e5-128">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="915e5-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="915e5-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="915e5-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="915e5-130">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="915e5-130">Request headers</span></span>

<span data-ttu-id="915e5-131">名前</span><span class="sxs-lookup"><span data-stu-id="915e5-131">Name</span></span> | <span data-ttu-id="915e5-132">種類</span><span class="sxs-lookup"><span data-stu-id="915e5-132">Type</span></span> | <span data-ttu-id="915e5-133">説明</span><span class="sxs-lookup"><span data-stu-id="915e5-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="915e5-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="915e5-134">Authorization</span></span> | <span data-ttu-id="915e5-135">文字列</span><span class="sxs-lookup"><span data-stu-id="915e5-135">String</span></span> | <span data-ttu-id="915e5-136">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="915e5-136">Bearer {token}.</span></span> <span data-ttu-id="915e5-137">**必須**</span><span class="sxs-lookup"><span data-stu-id="915e5-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="915e5-138">要求本文</span><span class="sxs-lookup"><span data-stu-id="915e5-138">Request body</span></span>
<span data-ttu-id="915e5-139">Empty</span><span class="sxs-lookup"><span data-stu-id="915e5-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="915e5-140">応答</span><span class="sxs-lookup"><span data-stu-id="915e5-140">Response</span></span>
<span data-ttu-id="915e5-141">成功し、アラートとドメインが存在する場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="915e5-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="915e5-142">アラートが見つからない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="915e5-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="915e5-143">例</span><span class="sxs-lookup"><span data-stu-id="915e5-143">Example</span></span>

<span data-ttu-id="915e5-144">**要求**</span><span class="sxs-lookup"><span data-stu-id="915e5-144">**Request**</span></span>

<span data-ttu-id="915e5-145">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="915e5-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="915e5-146">**応答**</span><span class="sxs-lookup"><span data-stu-id="915e5-146">**Response**</span></span>

<span data-ttu-id="915e5-147">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="915e5-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
