---
title: Get domain related machines API
description: Get domain related machines API を使用して、Microsoft Defender for Endpoint のドメインと通信するコンピューターを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, domain, related, devices
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
ms.openlocfilehash: 3fffb87c486e8b6b89b5e868b96d02dfae496e0b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166876"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="af86f-104">Get domain related machines API</span><span class="sxs-lookup"><span data-stu-id="af86f-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af86f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="af86f-105">**Applies to:**</span></span>
- [<span data-ttu-id="af86f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af86f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="af86f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af86f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="af86f-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="af86f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af86f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="af86f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="af86f-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="af86f-110">API description</span></span>
<span data-ttu-id="af86f-111">特定のドメイン アドレスと通信した [コンピューター](machine.md) のコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="af86f-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="af86f-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="af86f-112">Limitations</span></span>
1. <span data-ttu-id="af86f-113">構成済みの保持期間に従って、最後に更新されたデバイスに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="af86f-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="af86f-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="af86f-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="af86f-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="af86f-115">Permissions</span></span>
<span data-ttu-id="af86f-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="af86f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="af86f-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="af86f-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="af86f-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="af86f-118">Permission type</span></span> |   <span data-ttu-id="af86f-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="af86f-119">Permission</span></span>  |   <span data-ttu-id="af86f-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="af86f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="af86f-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="af86f-121">Application</span></span> |   <span data-ttu-id="af86f-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="af86f-122">Machine.Read.All</span></span> |  <span data-ttu-id="af86f-123">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="af86f-123">'Read all machine profiles'</span></span>
<span data-ttu-id="af86f-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="af86f-124">Application</span></span> |   <span data-ttu-id="af86f-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="af86f-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="af86f-126">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="af86f-126">'Read and write all machine information'</span></span>
<span data-ttu-id="af86f-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="af86f-127">Delegated (work or school account)</span></span> | <span data-ttu-id="af86f-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="af86f-128">Machine.Read</span></span> | <span data-ttu-id="af86f-129">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="af86f-129">'Read machine information'</span></span>
<span data-ttu-id="af86f-130">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="af86f-130">Delegated (work or school account)</span></span> | <span data-ttu-id="af86f-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="af86f-131">Machine.ReadWrite</span></span> | <span data-ttu-id="af86f-132">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="af86f-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="af86f-133">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="af86f-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="af86f-134">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="af86f-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="af86f-135">応答には、デバイス グループの設定に基づいて、ユーザーがアクセスできるデバイスだけが含まれます (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="af86f-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="af86f-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="af86f-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="af86f-137">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="af86f-137">Request headers</span></span>

<span data-ttu-id="af86f-138">名前</span><span class="sxs-lookup"><span data-stu-id="af86f-138">Name</span></span> | <span data-ttu-id="af86f-139">型</span><span class="sxs-lookup"><span data-stu-id="af86f-139">Type</span></span> | <span data-ttu-id="af86f-140">説明</span><span class="sxs-lookup"><span data-stu-id="af86f-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="af86f-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="af86f-141">Authorization</span></span> | <span data-ttu-id="af86f-142">String</span><span class="sxs-lookup"><span data-stu-id="af86f-142">String</span></span> | <span data-ttu-id="af86f-143">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="af86f-143">Bearer {token}.</span></span> <span data-ttu-id="af86f-144">**必須**</span><span class="sxs-lookup"><span data-stu-id="af86f-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="af86f-145">要求本文</span><span class="sxs-lookup"><span data-stu-id="af86f-145">Request body</span></span>
<span data-ttu-id="af86f-146">Empty</span><span class="sxs-lookup"><span data-stu-id="af86f-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="af86f-147">応答</span><span class="sxs-lookup"><span data-stu-id="af86f-147">Response</span></span>
<span data-ttu-id="af86f-148">成功した場合とドメインが存在する場合 - コンピューター[](machine.md)エンティティの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="af86f-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="af86f-149">ドメインが存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="af86f-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="af86f-150">例</span><span class="sxs-lookup"><span data-stu-id="af86f-150">Example</span></span>

<span data-ttu-id="af86f-151">**要求**</span><span class="sxs-lookup"><span data-stu-id="af86f-151">**Request**</span></span>

<span data-ttu-id="af86f-152">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="af86f-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
