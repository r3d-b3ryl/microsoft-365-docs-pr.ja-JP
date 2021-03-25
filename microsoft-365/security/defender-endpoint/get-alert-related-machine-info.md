---
title: アラート関連のコンピューター情報を取得する
description: Microsoft Defender for Endpoint を使用して、特定のアラートに関連するすべてのデバイスを取得します。
keywords: apis、graph api、サポートされている API、アラート情報の取得、アラート情報、関連デバイス
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
ms.openlocfilehash: 70ce6adce3e14be7ee440b96587b8f9402c0b99f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166984"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="9468c-104">アラート関連のコンピューター情報 API を取得する</span><span class="sxs-lookup"><span data-stu-id="9468c-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9468c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9468c-105">**Applies to:**</span></span>
- [<span data-ttu-id="9468c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9468c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9468c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9468c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="9468c-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="9468c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9468c-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="9468c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9468c-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="9468c-110">API description</span></span>
<span data-ttu-id="9468c-111">特定の [アラートに関連](machine.md) するデバイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9468c-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="9468c-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="9468c-112">Limitations</span></span>
1. <span data-ttu-id="9468c-113">構成済みの保持期間に従って、最後に更新されたアラートに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9468c-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="9468c-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="9468c-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9468c-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9468c-115">Permissions</span></span>
<span data-ttu-id="9468c-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="9468c-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9468c-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9468c-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9468c-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="9468c-118">Permission type</span></span> |   <span data-ttu-id="9468c-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9468c-119">Permission</span></span>  |   <span data-ttu-id="9468c-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="9468c-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9468c-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9468c-121">Application</span></span> |   <span data-ttu-id="9468c-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="9468c-122">Machine.Read.All</span></span> |  <span data-ttu-id="9468c-123">'すべてのコンピューター情報を読み取る'</span><span class="sxs-lookup"><span data-stu-id="9468c-123">'Read all machine information'</span></span>
<span data-ttu-id="9468c-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9468c-124">Application</span></span> |   <span data-ttu-id="9468c-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9468c-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="9468c-126">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="9468c-126">'Read and write all machine information'</span></span>
<span data-ttu-id="9468c-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="9468c-127">Delegated (work or school account)</span></span> | <span data-ttu-id="9468c-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="9468c-128">Machine.Read</span></span> | <span data-ttu-id="9468c-129">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="9468c-129">'Read machine information'</span></span>
<span data-ttu-id="9468c-130">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="9468c-130">Delegated (work or school account)</span></span> | <span data-ttu-id="9468c-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9468c-131">Machine.ReadWrite</span></span> | <span data-ttu-id="9468c-132">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="9468c-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="9468c-133">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="9468c-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9468c-134">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="9468c-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9468c-135">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="9468c-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9468c-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="9468c-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="9468c-137">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="9468c-137">Request headers</span></span>

<span data-ttu-id="9468c-138">名前</span><span class="sxs-lookup"><span data-stu-id="9468c-138">Name</span></span> | <span data-ttu-id="9468c-139">種類</span><span class="sxs-lookup"><span data-stu-id="9468c-139">Type</span></span> | <span data-ttu-id="9468c-140">説明</span><span class="sxs-lookup"><span data-stu-id="9468c-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="9468c-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="9468c-141">Authorization</span></span> | <span data-ttu-id="9468c-142">文字列</span><span class="sxs-lookup"><span data-stu-id="9468c-142">String</span></span> | <span data-ttu-id="9468c-143">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="9468c-143">Bearer {token}.</span></span> <span data-ttu-id="9468c-144">**必須**</span><span class="sxs-lookup"><span data-stu-id="9468c-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9468c-145">要求本文</span><span class="sxs-lookup"><span data-stu-id="9468c-145">Request body</span></span>
<span data-ttu-id="9468c-146">Empty</span><span class="sxs-lookup"><span data-stu-id="9468c-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9468c-147">応答</span><span class="sxs-lookup"><span data-stu-id="9468c-147">Response</span></span>
<span data-ttu-id="9468c-148">成功し、アラートとデバイスが存在する場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="9468c-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="9468c-149">アラートが見つからない場合、またはデバイスが見つからない場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="9468c-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="9468c-150">例</span><span class="sxs-lookup"><span data-stu-id="9468c-150">Example</span></span>

<span data-ttu-id="9468c-151">**要求**</span><span class="sxs-lookup"><span data-stu-id="9468c-151">**Request**</span></span>

<span data-ttu-id="9468c-152">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="9468c-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="9468c-153">**応答**</span><span class="sxs-lookup"><span data-stu-id="9468c-153">**Response**</span></span>

<span data-ttu-id="9468c-154">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="9468c-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
