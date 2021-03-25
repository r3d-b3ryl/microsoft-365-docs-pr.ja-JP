---
title: ファイル情報 API の取得
description: Get file information API を使用して、Microsoft Defender for Endpoint の Sha1、Sha256、または MD5 識別子でファイルを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, file, information, sha1, sha256, md5
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
ms.openlocfilehash: 181d808b465bfbf26eeff48a564e231b00a9a77f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166852"
---
# <a name="get-file-information-api"></a><span data-ttu-id="35d84-104">ファイル情報 API の取得</span><span class="sxs-lookup"><span data-stu-id="35d84-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35d84-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="35d84-105">**Applies to:**</span></span>
- [<span data-ttu-id="35d84-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35d84-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="35d84-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35d84-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="35d84-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="35d84-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35d84-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="35d84-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="35d84-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="35d84-110">API description</span></span>
<span data-ttu-id="35d84-111">識別子 Sha1 [または](files.md) Sha256 でファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="35d84-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="35d84-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="35d84-112">Limitations</span></span>
1. <span data-ttu-id="35d84-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="35d84-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="35d84-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="35d84-114">Permissions</span></span>
<span data-ttu-id="35d84-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="35d84-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="35d84-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="35d84-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="35d84-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="35d84-117">Permission type</span></span> |   <span data-ttu-id="35d84-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="35d84-118">Permission</span></span>  |   <span data-ttu-id="35d84-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="35d84-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="35d84-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="35d84-120">Application</span></span> |   <span data-ttu-id="35d84-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="35d84-121">File.Read.All</span></span> | <span data-ttu-id="35d84-122">'すべてのファイル プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="35d84-122">'Read all file profiles'</span></span>
<span data-ttu-id="35d84-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="35d84-123">Delegated (work or school account)</span></span> | <span data-ttu-id="35d84-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="35d84-124">File.Read.All</span></span> |    <span data-ttu-id="35d84-125">'すべてのファイル プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="35d84-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="35d84-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="35d84-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="35d84-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="35d84-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="35d84-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="35d84-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="35d84-129">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="35d84-129">Request headers</span></span>

<span data-ttu-id="35d84-130">名前</span><span class="sxs-lookup"><span data-stu-id="35d84-130">Name</span></span> | <span data-ttu-id="35d84-131">種類</span><span class="sxs-lookup"><span data-stu-id="35d84-131">Type</span></span> | <span data-ttu-id="35d84-132">説明</span><span class="sxs-lookup"><span data-stu-id="35d84-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="35d84-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="35d84-133">Authorization</span></span> | <span data-ttu-id="35d84-134">文字列</span><span class="sxs-lookup"><span data-stu-id="35d84-134">String</span></span> | <span data-ttu-id="35d84-135">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="35d84-135">Bearer {token}.</span></span> <span data-ttu-id="35d84-136">**必須**</span><span class="sxs-lookup"><span data-stu-id="35d84-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="35d84-137">要求本文</span><span class="sxs-lookup"><span data-stu-id="35d84-137">Request body</span></span>
<span data-ttu-id="35d84-138">Empty</span><span class="sxs-lookup"><span data-stu-id="35d84-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="35d84-139">応答</span><span class="sxs-lookup"><span data-stu-id="35d84-139">Response</span></span>
<span data-ttu-id="35d84-140">正常に実行され、ファイルが存在する場合は、本文に [ファイル](files.md) エンティティが 200 OK です。</span><span class="sxs-lookup"><span data-stu-id="35d84-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="35d84-141">ファイルが存在しない場合 - 404 が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="35d84-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="35d84-142">例</span><span class="sxs-lookup"><span data-stu-id="35d84-142">Example</span></span>

<span data-ttu-id="35d84-143">**要求**</span><span class="sxs-lookup"><span data-stu-id="35d84-143">**Request**</span></span>

<span data-ttu-id="35d84-144">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="35d84-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="35d84-145">**応答**</span><span class="sxs-lookup"><span data-stu-id="35d84-145">**Response**</span></span>

<span data-ttu-id="35d84-146">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="35d84-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
