---
title: Id による推奨事項の取得
description: セキュリティの推奨事項を ID で取得します。
keywords: apis、graph api、サポートされている API、get、セキュリティ推奨事項、ID によるセキュリティの推奨事項、脅威と脆弱性の管理、脅威と脆弱性管理 API
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
ms.openlocfilehash: 45a151fc5855a4a2b1ba63a50b54737c90e6bdd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199515"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="f3652-104">ID による推奨事項の取得</span><span class="sxs-lookup"><span data-stu-id="f3652-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3652-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f3652-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f3652-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f3652-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f3652-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f3652-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f3652-108">セキュリティの推奨事項を ID で取得します。</span><span class="sxs-lookup"><span data-stu-id="f3652-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="f3652-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f3652-109">Permissions</span></span>
<span data-ttu-id="f3652-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f3652-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f3652-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3652-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f3652-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="f3652-112">Permission type</span></span> |   <span data-ttu-id="f3652-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f3652-113">Permission</span></span>  |   <span data-ttu-id="f3652-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="f3652-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f3652-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f3652-115">Application</span></span> |   <span data-ttu-id="f3652-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="f3652-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="f3652-117">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="f3652-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="f3652-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="f3652-118">Delegated (work or school account)</span></span> | <span data-ttu-id="f3652-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="f3652-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="f3652-120">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="f3652-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f3652-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="f3652-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="f3652-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f3652-122">Request headers</span></span>

<span data-ttu-id="f3652-123">名前</span><span class="sxs-lookup"><span data-stu-id="f3652-123">Name</span></span> | <span data-ttu-id="f3652-124">種類</span><span class="sxs-lookup"><span data-stu-id="f3652-124">Type</span></span> | <span data-ttu-id="f3652-125">説明</span><span class="sxs-lookup"><span data-stu-id="f3652-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="f3652-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="f3652-126">Authorization</span></span> | <span data-ttu-id="f3652-127">文字列</span><span class="sxs-lookup"><span data-stu-id="f3652-127">String</span></span> | <span data-ttu-id="f3652-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="f3652-128">Bearer {token}.</span></span> <span data-ttu-id="f3652-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="f3652-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f3652-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="f3652-130">Request body</span></span>
<span data-ttu-id="f3652-131">Empty</span><span class="sxs-lookup"><span data-stu-id="f3652-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f3652-132">応答</span><span class="sxs-lookup"><span data-stu-id="f3652-132">Response</span></span>
<span data-ttu-id="f3652-133">成功した場合、このメソッドは 200 OK を返し、本文のセキュリティに関する推奨事項を返します。</span><span class="sxs-lookup"><span data-stu-id="f3652-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="f3652-134">例</span><span class="sxs-lookup"><span data-stu-id="f3652-134">Example</span></span>

<span data-ttu-id="f3652-135">**要求**</span><span class="sxs-lookup"><span data-stu-id="f3652-135">**Request**</span></span>

<span data-ttu-id="f3652-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="f3652-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="f3652-137">**応答**</span><span class="sxs-lookup"><span data-stu-id="f3652-137">**Response**</span></span>

<span data-ttu-id="f3652-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="f3652-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="f3652-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3652-139">Related topics</span></span>
- [<span data-ttu-id="f3652-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="f3652-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f3652-141">脅威&脆弱性のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="f3652-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
