---
title: ドメイン関連のアラート API を取得する
description: Get domain related alerts API を使用して、Microsoft Defender for Endpoint の特定のドメイン アドレスに関連するアラートを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, domain, related, alerts
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772259"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="f4456-104">ドメイン関連のアラート API を取得する</span><span class="sxs-lookup"><span data-stu-id="f4456-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4456-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f4456-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4456-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4456-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4456-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4456-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f4456-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="f4456-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4456-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f4456-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f4456-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="f4456-110">API description</span></span>
<span data-ttu-id="f4456-111">特定のドメイン アドレスに関連 [するアラート](alerts.md) のコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="f4456-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="f4456-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="f4456-112">Limitations</span></span>
1. <span data-ttu-id="f4456-113">構成済みの保持期間に従って、最後に更新されたアラートに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f4456-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="f4456-114">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="f4456-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f4456-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4456-115">Permissions</span></span>
<span data-ttu-id="f4456-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4456-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f4456-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f4456-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f4456-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="f4456-118">Permission type</span></span> |   <span data-ttu-id="f4456-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4456-119">Permission</span></span>  |   <span data-ttu-id="f4456-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="f4456-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f4456-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f4456-121">Application</span></span> |   <span data-ttu-id="f4456-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="f4456-122">Alert.Read.All</span></span> |    <span data-ttu-id="f4456-123">'すべてのアラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="f4456-123">'Read all alerts'</span></span>
<span data-ttu-id="f4456-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f4456-124">Application</span></span> |   <span data-ttu-id="f4456-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4456-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="f4456-126">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="f4456-126">'Read and write all alerts'</span></span>
<span data-ttu-id="f4456-127">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="f4456-127">Delegated (work or school account)</span></span> | <span data-ttu-id="f4456-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="f4456-128">Alert.Read</span></span> | <span data-ttu-id="f4456-129">'アラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="f4456-129">'Read alerts'</span></span>
<span data-ttu-id="f4456-130">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="f4456-130">Delegated (work or school account)</span></span> | <span data-ttu-id="f4456-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f4456-131">Alert.ReadWrite</span></span> | <span data-ttu-id="f4456-132">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="f4456-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="f4456-133">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="f4456-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f4456-134">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="f4456-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f4456-135">応答には、デバイス グループ設定に基づいて、ユーザーがアクセスできるデバイスに関連付けられたアラートだけが含まれます[](machine-groups.md)(詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="f4456-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f4456-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="f4456-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="f4456-137">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f4456-137">Request headers</span></span>

| <span data-ttu-id="f4456-138">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f4456-138">Header</span></span>        | <span data-ttu-id="f4456-139">値</span><span class="sxs-lookup"><span data-stu-id="f4456-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="f4456-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="f4456-140">Authorization</span></span> | <span data-ttu-id="f4456-141">String</span><span class="sxs-lookup"><span data-stu-id="f4456-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="f4456-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="f4456-142">Request body</span></span>
<span data-ttu-id="f4456-143">Empty</span><span class="sxs-lookup"><span data-stu-id="f4456-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f4456-144">応答</span><span class="sxs-lookup"><span data-stu-id="f4456-144">Response</span></span>
<span data-ttu-id="f4456-145">成功した場合とドメインが存在する場合 - アラート[](alerts.md)エンティティの一覧で 200 OK。</span><span class="sxs-lookup"><span data-stu-id="f4456-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="f4456-146">ドメインが存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="f4456-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f4456-147">例</span><span class="sxs-lookup"><span data-stu-id="f4456-147">Example</span></span>

<span data-ttu-id="f4456-148">**要求**</span><span class="sxs-lookup"><span data-stu-id="f4456-148">**Request**</span></span>

<span data-ttu-id="f4456-149">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="f4456-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
