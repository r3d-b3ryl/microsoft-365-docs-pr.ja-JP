---
title: 推奨事項によって脆弱性を一覧表示する
description: セキュリティ推奨事項に関連付けられている脆弱性の一覧を取得します。
keywords: apis、graph api、サポートされている API、get、脆弱性のリスト、セキュリティの推奨事項、脆弱性に関するセキュリティ推奨事項、脅威と脆弱性の管理、脅威と脆弱性管理 API
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
ms.openlocfilehash: b41ee2886d758ab0ab70b78ee6d6d863d0d482a7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198603"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="7ee42-104">推奨事項によって脆弱性を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="7ee42-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ee42-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7ee42-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="7ee42-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7ee42-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7ee42-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="7ee42-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="7ee42-108">セキュリティ推奨事項に関連付けられている脆弱性の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ee42-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="7ee42-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ee42-109">Permissions</span></span>
<span data-ttu-id="7ee42-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7ee42-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7ee42-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ee42-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="7ee42-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="7ee42-112">Permission type</span></span> |   <span data-ttu-id="7ee42-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7ee42-113">Permission</span></span>  |   <span data-ttu-id="7ee42-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="7ee42-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7ee42-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7ee42-115">Application</span></span> |   <span data-ttu-id="7ee42-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="7ee42-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="7ee42-117">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="7ee42-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="7ee42-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="7ee42-118">Delegated (work or school account)</span></span> | <span data-ttu-id="7ee42-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="7ee42-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="7ee42-120">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="7ee42-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="7ee42-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="7ee42-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="7ee42-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="7ee42-122">Request headers</span></span>

<span data-ttu-id="7ee42-123">名前</span><span class="sxs-lookup"><span data-stu-id="7ee42-123">Name</span></span> | <span data-ttu-id="7ee42-124">種類</span><span class="sxs-lookup"><span data-stu-id="7ee42-124">Type</span></span> | <span data-ttu-id="7ee42-125">説明</span><span class="sxs-lookup"><span data-stu-id="7ee42-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="7ee42-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="7ee42-126">Authorization</span></span> | <span data-ttu-id="7ee42-127">文字列</span><span class="sxs-lookup"><span data-stu-id="7ee42-127">String</span></span> | <span data-ttu-id="7ee42-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="7ee42-128">Bearer {token}.</span></span> <span data-ttu-id="7ee42-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="7ee42-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="7ee42-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="7ee42-130">Request body</span></span>
<span data-ttu-id="7ee42-131">Empty</span><span class="sxs-lookup"><span data-stu-id="7ee42-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7ee42-132">応答</span><span class="sxs-lookup"><span data-stu-id="7ee42-132">Response</span></span>
<span data-ttu-id="7ee42-133">成功した場合、このメソッドは 200 OK を返し、セキュリティの推奨事項に関連付けられている脆弱性の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="7ee42-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="7ee42-134">例</span><span class="sxs-lookup"><span data-stu-id="7ee42-134">Example</span></span>

<span data-ttu-id="7ee42-135">**要求**</span><span class="sxs-lookup"><span data-stu-id="7ee42-135">**Request**</span></span>

<span data-ttu-id="7ee42-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="7ee42-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="7ee42-137">**応答**</span><span class="sxs-lookup"><span data-stu-id="7ee42-137">**Response**</span></span>

<span data-ttu-id="7ee42-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="7ee42-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a><span data-ttu-id="7ee42-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ee42-139">Related topics</span></span>
- [<span data-ttu-id="7ee42-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="7ee42-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="7ee42-141">脅威&脆弱性のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="7ee42-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
