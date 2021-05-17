---
title: セキュリティ上の推奨事項を取得する
description: 特定のデバイス ID に関連するセキュリティ推奨事項のコレクションを取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, security recommendation per device, threat & 脆弱性の管理 api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: bc209687d51b3e05bfcfd6028042ba5912b877f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935307"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="e16e0-104">セキュリティ上の推奨事項を取得する</span><span class="sxs-lookup"><span data-stu-id="e16e0-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e16e0-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e16e0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="e16e0-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e16e0-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e16e0-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e16e0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e16e0-108">特定のデバイス ID に関連するセキュリティ推奨事項のコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="e16e0-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="e16e0-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e16e0-109">Permissions</span></span>
<span data-ttu-id="e16e0-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e16e0-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e16e0-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e16e0-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e16e0-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="e16e0-112">Permission type</span></span> |   <span data-ttu-id="e16e0-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e16e0-113">Permission</span></span>  |   <span data-ttu-id="e16e0-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="e16e0-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e16e0-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e16e0-115">Application</span></span> | <span data-ttu-id="e16e0-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="e16e0-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="e16e0-117">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="e16e0-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="e16e0-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="e16e0-118">Delegated (work or school account)</span></span> | <span data-ttu-id="e16e0-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="e16e0-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="e16e0-120">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="e16e0-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="e16e0-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="e16e0-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="e16e0-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e16e0-122">Request headers</span></span>

<span data-ttu-id="e16e0-123">名前</span><span class="sxs-lookup"><span data-stu-id="e16e0-123">Name</span></span> | <span data-ttu-id="e16e0-124">型</span><span class="sxs-lookup"><span data-stu-id="e16e0-124">Type</span></span> | <span data-ttu-id="e16e0-125">説明</span><span class="sxs-lookup"><span data-stu-id="e16e0-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="e16e0-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="e16e0-126">Authorization</span></span> | <span data-ttu-id="e16e0-127">String</span><span class="sxs-lookup"><span data-stu-id="e16e0-127">String</span></span> | <span data-ttu-id="e16e0-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="e16e0-128">Bearer {token}.</span></span> <span data-ttu-id="e16e0-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="e16e0-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e16e0-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="e16e0-130">Request body</span></span>
<span data-ttu-id="e16e0-131">Empty</span><span class="sxs-lookup"><span data-stu-id="e16e0-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e16e0-132">応答</span><span class="sxs-lookup"><span data-stu-id="e16e0-132">Response</span></span>
<span data-ttu-id="e16e0-133">成功した場合、このメソッドは 200 OK を返し、本文のセキュリティに関する推奨事項を返します。</span><span class="sxs-lookup"><span data-stu-id="e16e0-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="e16e0-134">例</span><span class="sxs-lookup"><span data-stu-id="e16e0-134">Example</span></span>

<span data-ttu-id="e16e0-135">**要求**</span><span class="sxs-lookup"><span data-stu-id="e16e0-135">**Request**</span></span>

<span data-ttu-id="e16e0-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="e16e0-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="e16e0-137">**応答**</span><span class="sxs-lookup"><span data-stu-id="e16e0-137">**Response**</span></span>

<span data-ttu-id="e16e0-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="e16e0-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="e16e0-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e16e0-139">Related topics</span></span>
- [<span data-ttu-id="e16e0-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="e16e0-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e16e0-141">脅威&脆弱性のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="e16e0-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
