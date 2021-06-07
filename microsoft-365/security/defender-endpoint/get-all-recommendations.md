---
title: すべての推奨事項を一覧表示する
description: 組織に影響を与えるすべてのセキュリティ推奨事項の一覧を取得します。
keywords: apis、 graph api, supported api, get, security recommendations, Microsoft Defender for Endpoint tvm api, 脅威と脆弱性の管理, 脅威と脆弱性の管理 api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 0a58287a9bd48a4d19144a40674e1d3ad3bd256a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768932"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="d8dea-104">すべての推奨事項を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="d8dea-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d8dea-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d8dea-105">**Applies to:**</span></span>
- [<span data-ttu-id="d8dea-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d8dea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8dea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8dea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="d8dea-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="d8dea-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d8dea-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d8dea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d8dea-110">組織に影響を与えるすべてのセキュリティ推奨事項の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d8dea-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="d8dea-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d8dea-111">Permissions</span></span>
<span data-ttu-id="d8dea-112">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8dea-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d8dea-113">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8dea-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="d8dea-114">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="d8dea-114">Permission type</span></span> |   <span data-ttu-id="d8dea-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d8dea-115">Permission</span></span>  |   <span data-ttu-id="d8dea-116">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="d8dea-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d8dea-117">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d8dea-117">Application</span></span> |   <span data-ttu-id="d8dea-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="d8dea-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="d8dea-119">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="d8dea-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="d8dea-120">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="d8dea-120">Delegated (work or school account)</span></span> | <span data-ttu-id="d8dea-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="d8dea-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="d8dea-122">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="d8dea-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="d8dea-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="d8dea-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="d8dea-124">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="d8dea-124">Request headers</span></span>

<span data-ttu-id="d8dea-125">名前</span><span class="sxs-lookup"><span data-stu-id="d8dea-125">Name</span></span> | <span data-ttu-id="d8dea-126">種類</span><span class="sxs-lookup"><span data-stu-id="d8dea-126">Type</span></span> | <span data-ttu-id="d8dea-127">説明</span><span class="sxs-lookup"><span data-stu-id="d8dea-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="d8dea-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="d8dea-128">Authorization</span></span> | <span data-ttu-id="d8dea-129">String</span><span class="sxs-lookup"><span data-stu-id="d8dea-129">String</span></span> | <span data-ttu-id="d8dea-130">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="d8dea-130">Bearer {token}.</span></span> <span data-ttu-id="d8dea-131">**必須**</span><span class="sxs-lookup"><span data-stu-id="d8dea-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d8dea-132">要求本文</span><span class="sxs-lookup"><span data-stu-id="d8dea-132">Request body</span></span>
<span data-ttu-id="d8dea-133">Empty</span><span class="sxs-lookup"><span data-stu-id="d8dea-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d8dea-134">応答</span><span class="sxs-lookup"><span data-stu-id="d8dea-134">Response</span></span>
<span data-ttu-id="d8dea-135">成功した場合、このメソッドは 200 OK を返し、本文のセキュリティ推奨事項の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="d8dea-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="d8dea-136">例</span><span class="sxs-lookup"><span data-stu-id="d8dea-136">Example</span></span>

<span data-ttu-id="d8dea-137">**要求**</span><span class="sxs-lookup"><span data-stu-id="d8dea-137">**Request**</span></span>

<span data-ttu-id="d8dea-138">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="d8dea-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="d8dea-139">**応答**</span><span class="sxs-lookup"><span data-stu-id="d8dea-139">**Response**</span></span>

<span data-ttu-id="d8dea-140">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="d8dea-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="d8dea-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8dea-141">See also</span></span>
- [<span data-ttu-id="d8dea-142">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="d8dea-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="d8dea-143">脅威&脆弱性のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="d8dea-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

