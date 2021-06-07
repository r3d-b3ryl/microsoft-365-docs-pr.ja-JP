---
title: 内部 IP API でデバイスを検索する
description: 指定されたタイムスタンプの 15 分前および後の時間範囲で、要求された内部 IP で見られるデバイスを検索する
keywords: apis, graph api, supported apis, get, device, IP, find, find device, by ip, ip
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
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769439"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="7f597-104">内部 IP API でデバイスを検索する</span><span class="sxs-lookup"><span data-stu-id="7f597-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7f597-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7f597-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="7f597-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="7f597-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7f597-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7f597-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="7f597-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="7f597-108">API description</span></span>
<span data-ttu-id="7f597-109">指定 [されたタイムスタンプ](machine.md) の 15 分前と後の時間範囲で、要求された内部 IP で表示されるコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="7f597-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="7f597-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="7f597-110">Limitations</span></span>
1. <span data-ttu-id="7f597-111">指定されたタイムスタンプは、過去 30 日間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f597-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="7f597-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="7f597-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="7f597-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7f597-113">Permissions</span></span>
<span data-ttu-id="7f597-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f597-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7f597-115">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7f597-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7f597-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="7f597-116">Permission type</span></span> |   <span data-ttu-id="7f597-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7f597-117">Permission</span></span>  |   <span data-ttu-id="7f597-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="7f597-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7f597-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7f597-119">Application</span></span> |   <span data-ttu-id="7f597-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="7f597-120">Machine.Read.All</span></span> |  <span data-ttu-id="7f597-121">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="7f597-121">'Read all machine profiles'</span></span>
<span data-ttu-id="7f597-122">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7f597-122">Application</span></span> |   <span data-ttu-id="7f597-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="7f597-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="7f597-124">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="7f597-124">'Read and write all machine information'</span></span>
<span data-ttu-id="7f597-125">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="7f597-125">Delegated (work or school account)</span></span> | <span data-ttu-id="7f597-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="7f597-126">Machine.Read</span></span> | <span data-ttu-id="7f597-127">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="7f597-127">'Read machine information'</span></span>
<span data-ttu-id="7f597-128">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="7f597-128">Delegated (work or school account)</span></span> | <span data-ttu-id="7f597-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="7f597-129">Machine.ReadWrite</span></span> | <span data-ttu-id="7f597-130">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="7f597-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="7f597-131">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="7f597-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="7f597-132">応答には、ユーザーがデバイス グループ設定に基づいてアクセスできるデバイスだけが含まれます (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="7f597-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="7f597-133">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="7f597-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="7f597-134">応答には、ユーザーがデバイス グループ設定に基づいてアクセスできるデバイスだけが含まれます (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="7f597-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7f597-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="7f597-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="7f597-136">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="7f597-136">Request headers</span></span>

<span data-ttu-id="7f597-137">名前</span><span class="sxs-lookup"><span data-stu-id="7f597-137">Name</span></span> | <span data-ttu-id="7f597-138">種類</span><span class="sxs-lookup"><span data-stu-id="7f597-138">Type</span></span> | <span data-ttu-id="7f597-139">説明</span><span class="sxs-lookup"><span data-stu-id="7f597-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="7f597-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="7f597-140">Authorization</span></span> | <span data-ttu-id="7f597-141">String</span><span class="sxs-lookup"><span data-stu-id="7f597-141">String</span></span> | <span data-ttu-id="7f597-142">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="7f597-142">Bearer {token}.</span></span> <span data-ttu-id="7f597-143">**必須**</span><span class="sxs-lookup"><span data-stu-id="7f597-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7f597-144">要求本文</span><span class="sxs-lookup"><span data-stu-id="7f597-144">Request body</span></span>
<span data-ttu-id="7f597-145">Empty</span><span class="sxs-lookup"><span data-stu-id="7f597-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7f597-146">応答</span><span class="sxs-lookup"><span data-stu-id="7f597-146">Response</span></span>
<span data-ttu-id="7f597-147">成功した場合 - 応答本文のコンピューターの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="7f597-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="7f597-148">タイムスタンプが過去 30 日間 ( 400 Bad Request) ではない場合。</span><span class="sxs-lookup"><span data-stu-id="7f597-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="7f597-149">例</span><span class="sxs-lookup"><span data-stu-id="7f597-149">Example</span></span>

<span data-ttu-id="7f597-150">**要求**</span><span class="sxs-lookup"><span data-stu-id="7f597-150">**Request**</span></span>

<span data-ttu-id="7f597-151">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="7f597-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
