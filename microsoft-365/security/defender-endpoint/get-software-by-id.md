---
title: Id でソフトウェアを取得する
description: デバイス グループ別の露出スコアの一覧を取得します。
keywords: apis, graph api, supported api, get, software, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9a7d97cea96f919f1ec7cd1e37e7a8f27042c79
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845092"
---
# <a name="get-software-by-id"></a><span data-ttu-id="fac01-104">Id でソフトウェアを取得する</span><span class="sxs-lookup"><span data-stu-id="fac01-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fac01-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="fac01-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="fac01-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="fac01-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fac01-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="fac01-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="fac01-108">ソフトウェアの詳細を ID で取得します。</span><span class="sxs-lookup"><span data-stu-id="fac01-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="fac01-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="fac01-109">Permissions</span></span>
<span data-ttu-id="fac01-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="fac01-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fac01-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fac01-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="fac01-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="fac01-112">Permission type</span></span> |   <span data-ttu-id="fac01-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="fac01-113">Permission</span></span>  |   <span data-ttu-id="fac01-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="fac01-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fac01-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="fac01-115">Application</span></span> | <span data-ttu-id="fac01-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="fac01-116">Software.Read.All</span></span> | <span data-ttu-id="fac01-117">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="fac01-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="fac01-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="fac01-118">Delegated (work or school account)</span></span> | <span data-ttu-id="fac01-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="fac01-119">Software.Read</span></span> | <span data-ttu-id="fac01-120">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="fac01-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="fac01-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="fac01-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="fac01-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="fac01-122">Request headers</span></span>

| <span data-ttu-id="fac01-123">名前</span><span class="sxs-lookup"><span data-stu-id="fac01-123">Name</span></span>        | <span data-ttu-id="fac01-124">型</span><span class="sxs-lookup"><span data-stu-id="fac01-124">Type</span></span> | <span data-ttu-id="fac01-125">説明</span><span class="sxs-lookup"><span data-stu-id="fac01-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="fac01-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="fac01-126">Authorization</span></span> | <span data-ttu-id="fac01-127">String</span><span class="sxs-lookup"><span data-stu-id="fac01-127">String</span></span> | <span data-ttu-id="fac01-128">ベアラー {token}。**必須**。</span><span class="sxs-lookup"><span data-stu-id="fac01-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="fac01-129">要求本文</span><span class="sxs-lookup"><span data-stu-id="fac01-129">Request body</span></span>
<span data-ttu-id="fac01-130">Empty</span><span class="sxs-lookup"><span data-stu-id="fac01-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="fac01-131">応答</span><span class="sxs-lookup"><span data-stu-id="fac01-131">Response</span></span>
<span data-ttu-id="fac01-132">成功した場合、このメソッドは 200 OK を返し、本文に指定されたソフトウェア データを返します。</span><span class="sxs-lookup"><span data-stu-id="fac01-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="fac01-133">例</span><span class="sxs-lookup"><span data-stu-id="fac01-133">Example</span></span>

<span data-ttu-id="fac01-134">**要求**</span><span class="sxs-lookup"><span data-stu-id="fac01-134">**Request**</span></span>

<span data-ttu-id="fac01-135">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="fac01-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="fac01-136">**応答**</span><span class="sxs-lookup"><span data-stu-id="fac01-136">**Response**</span></span>

<span data-ttu-id="fac01-137">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="fac01-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="fac01-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="fac01-138">Related topics</span></span>
- [<span data-ttu-id="fac01-139">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="fac01-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="fac01-140">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="fac01-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
