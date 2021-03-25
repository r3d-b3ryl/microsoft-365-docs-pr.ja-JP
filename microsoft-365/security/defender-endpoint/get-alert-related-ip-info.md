---
title: アラート関連の AP 情報を取得する
description: Microsoft Defender for Endpoint を使用して、特定のアラートに関連するすべての AP を取得します。
keywords: apis、graph api、サポートされている API、アラート情報の取得、アラート情報、関連 IP
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
ms.openlocfilehash: 970f82038bd7feb4f0c568ed13b285f75bf1ab19
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167056"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="3af02-104">アラート関連の AP 情報 API を取得する</span><span class="sxs-lookup"><span data-stu-id="3af02-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3af02-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3af02-105">**Applies to:**</span></span>
- [<span data-ttu-id="3af02-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3af02-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3af02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3af02-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3af02-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="3af02-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3af02-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="3af02-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3af02-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="3af02-110">API description</span></span>
<span data-ttu-id="3af02-111">特定のアラートに関連するすべての IPs を取得します。</span><span class="sxs-lookup"><span data-stu-id="3af02-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="3af02-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="3af02-112">Limitations</span></span>
1. <span data-ttu-id="3af02-113">構成済みの保持期間に従って、最後に更新されたアラートに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3af02-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3af02-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="3af02-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3af02-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3af02-115">Permissions</span></span>
<span data-ttu-id="3af02-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="3af02-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3af02-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3af02-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3af02-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="3af02-118">Permission type</span></span> |   <span data-ttu-id="3af02-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3af02-119">Permission</span></span>  |   <span data-ttu-id="3af02-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="3af02-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3af02-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3af02-121">Application</span></span> |   <span data-ttu-id="3af02-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="3af02-122">Ip.Read.All</span></span> |   <span data-ttu-id="3af02-123">'IP アドレス プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="3af02-123">'Read IP address profiles'</span></span>
<span data-ttu-id="3af02-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="3af02-124">Delegated (work or school account)</span></span> | <span data-ttu-id="3af02-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="3af02-125">Ip.Read.All</span></span> |  <span data-ttu-id="3af02-126">'IP アドレス プロファイルの読み取り'</span><span class="sxs-lookup"><span data-stu-id="3af02-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="3af02-127">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="3af02-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3af02-128">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="3af02-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3af02-129">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="3af02-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3af02-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3af02-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="3af02-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3af02-131">Request headers</span></span>

<span data-ttu-id="3af02-132">名前</span><span class="sxs-lookup"><span data-stu-id="3af02-132">Name</span></span> | <span data-ttu-id="3af02-133">種類</span><span class="sxs-lookup"><span data-stu-id="3af02-133">Type</span></span> | <span data-ttu-id="3af02-134">説明</span><span class="sxs-lookup"><span data-stu-id="3af02-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="3af02-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="3af02-135">Authorization</span></span> | <span data-ttu-id="3af02-136">文字列</span><span class="sxs-lookup"><span data-stu-id="3af02-136">String</span></span> | <span data-ttu-id="3af02-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="3af02-137">Bearer {token}.</span></span> <span data-ttu-id="3af02-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="3af02-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3af02-139">要求本文</span><span class="sxs-lookup"><span data-stu-id="3af02-139">Request body</span></span>
<span data-ttu-id="3af02-140">Empty</span><span class="sxs-lookup"><span data-stu-id="3af02-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3af02-141">応答</span><span class="sxs-lookup"><span data-stu-id="3af02-141">Response</span></span>
<span data-ttu-id="3af02-142">成功し、アラートと IP が存在する場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="3af02-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="3af02-143">アラートが見つからない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="3af02-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3af02-144">例</span><span class="sxs-lookup"><span data-stu-id="3af02-144">Example</span></span>

<span data-ttu-id="3af02-145">**要求**</span><span class="sxs-lookup"><span data-stu-id="3af02-145">**Request**</span></span>

<span data-ttu-id="3af02-146">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="3af02-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="3af02-147">**応答**</span><span class="sxs-lookup"><span data-stu-id="3af02-147">**Response**</span></span>

<span data-ttu-id="3af02-148">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="3af02-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```