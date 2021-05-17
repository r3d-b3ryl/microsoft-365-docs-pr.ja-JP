---
title: 内部 IP API によるデバイス情報の検索
description: この API を使用して、内部 IP による特定のタイムスタンプの周りのデバイス エントリの検索に関連する呼び出しを作成します。
keywords: ip、apis、graph api、サポートされている API、デバイス、デバイス情報の検索
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167140"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="3a631-104">内部 IP API によるデバイス情報の検索</span><span class="sxs-lookup"><span data-stu-id="3a631-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3a631-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3a631-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="3a631-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3a631-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3a631-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3a631-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="3a631-108">内部 IP でデバイスを検索します。</span><span class="sxs-lookup"><span data-stu-id="3a631-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="3a631-109">タイムスタンプは、過去 30 日以内である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a631-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="3a631-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3a631-110">Permissions</span></span>
<span data-ttu-id="3a631-111">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="3a631-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3a631-112">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3a631-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3a631-113">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="3a631-113">Permission type</span></span> | <span data-ttu-id="3a631-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="3a631-114">Permission</span></span> | <span data-ttu-id="3a631-115">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="3a631-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3a631-116">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3a631-116">Application</span></span> | <span data-ttu-id="3a631-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="3a631-117">Machine.Read.All</span></span> | <span data-ttu-id="3a631-118">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="3a631-118">'Read all machine profiles'</span></span>
<span data-ttu-id="3a631-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3a631-119">Application</span></span> | <span data-ttu-id="3a631-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3a631-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="3a631-121">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="3a631-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="3a631-122">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3a631-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="3a631-123">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3a631-123">Request headers</span></span>

<span data-ttu-id="3a631-124">名前</span><span class="sxs-lookup"><span data-stu-id="3a631-124">Name</span></span> | <span data-ttu-id="3a631-125">型</span><span class="sxs-lookup"><span data-stu-id="3a631-125">Type</span></span> | <span data-ttu-id="3a631-126">説明</span><span class="sxs-lookup"><span data-stu-id="3a631-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="3a631-127">Authorization</span><span class="sxs-lookup"><span data-stu-id="3a631-127">Authorization</span></span> | <span data-ttu-id="3a631-128">String</span><span class="sxs-lookup"><span data-stu-id="3a631-128">String</span></span> | <span data-ttu-id="3a631-129">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="3a631-129">Bearer {token}.</span></span> <span data-ttu-id="3a631-130">**必須**</span><span class="sxs-lookup"><span data-stu-id="3a631-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3a631-131">要求本文</span><span class="sxs-lookup"><span data-stu-id="3a631-131">Request body</span></span>
<span data-ttu-id="3a631-132">Empty</span><span class="sxs-lookup"><span data-stu-id="3a631-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3a631-133">応答</span><span class="sxs-lookup"><span data-stu-id="3a631-133">Response</span></span>
<span data-ttu-id="3a631-134">成功し、コンピューターが存在する場合 - 200 OK。</span><span class="sxs-lookup"><span data-stu-id="3a631-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="3a631-135">コンピューターが見つからない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="3a631-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3a631-136">例</span><span class="sxs-lookup"><span data-stu-id="3a631-136">Example</span></span>

<span data-ttu-id="3a631-137">**要求**</span><span class="sxs-lookup"><span data-stu-id="3a631-137">**Request**</span></span>

<span data-ttu-id="3a631-138">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="3a631-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="3a631-139">**応答**</span><span class="sxs-lookup"><span data-stu-id="3a631-139">**Response**</span></span>

<span data-ttu-id="3a631-140">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="3a631-140">Here is an example of the response.</span></span>

<span data-ttu-id="3a631-141">この応答は、タイムスタンプの 16 分前および後にこの IP アドレスを報告したすべてのデバイスの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="3a631-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
