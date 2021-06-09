---
title: ソフトウェアの一覧表示
description: ソフトウェア インベントリの一覧を取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, software inventory, threat & 脆弱性の管理 api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 2b7375f04094cdb56b0801adf2c1c0b7a8ab3098
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844276"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="f3140-104">ソフトウェア インベントリ API の一覧表示</span><span class="sxs-lookup"><span data-stu-id="f3140-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3140-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f3140-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f3140-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="f3140-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f3140-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f3140-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f3140-108">組織のソフトウェア インベントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3140-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="f3140-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f3140-109">Permissions</span></span>
<span data-ttu-id="f3140-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f3140-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f3140-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3140-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f3140-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="f3140-112">Permission type</span></span> |   <span data-ttu-id="f3140-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f3140-113">Permission</span></span>  |   <span data-ttu-id="f3140-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="f3140-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f3140-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f3140-115">Application</span></span> |<span data-ttu-id="f3140-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="f3140-116">Software.Read.All</span></span> |    <span data-ttu-id="f3140-117">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="f3140-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="f3140-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="f3140-118">Delegated (work or school account)</span></span> | <span data-ttu-id="f3140-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="f3140-119">Software.Read</span></span> |    <span data-ttu-id="f3140-120">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="f3140-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f3140-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="f3140-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="f3140-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f3140-122">Request headers</span></span>

<span data-ttu-id="f3140-123">名前</span><span class="sxs-lookup"><span data-stu-id="f3140-123">Name</span></span> | <span data-ttu-id="f3140-124">種類</span><span class="sxs-lookup"><span data-stu-id="f3140-124">Type</span></span> | <span data-ttu-id="f3140-125">説明</span><span class="sxs-lookup"><span data-stu-id="f3140-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="f3140-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="f3140-126">Authorization</span></span> | <span data-ttu-id="f3140-127">String</span><span class="sxs-lookup"><span data-stu-id="f3140-127">String</span></span> | <span data-ttu-id="f3140-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="f3140-128">Bearer {token}.</span></span> <span data-ttu-id="f3140-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="f3140-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f3140-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="f3140-130">Request body</span></span>
<span data-ttu-id="f3140-131">Empty</span><span class="sxs-lookup"><span data-stu-id="f3140-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f3140-132">応答</span><span class="sxs-lookup"><span data-stu-id="f3140-132">Response</span></span>
<span data-ttu-id="f3140-133">成功した場合、このメソッドは、本文のソフトウェア インベントリで 200 OK を返します。</span><span class="sxs-lookup"><span data-stu-id="f3140-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="f3140-134">例</span><span class="sxs-lookup"><span data-stu-id="f3140-134">Example</span></span>

<span data-ttu-id="f3140-135">**要求**</span><span class="sxs-lookup"><span data-stu-id="f3140-135">**Request**</span></span>

<span data-ttu-id="f3140-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="f3140-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="f3140-137">**応答**</span><span class="sxs-lookup"><span data-stu-id="f3140-137">**Response**</span></span>

<span data-ttu-id="f3140-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="f3140-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="f3140-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3140-139">Related topics</span></span>
- [<span data-ttu-id="f3140-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="f3140-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f3140-141">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="f3140-141">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
