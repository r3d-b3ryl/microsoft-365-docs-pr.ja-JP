---
title: すべての脆弱性を取得する
description: 組織に影響を与えるすべての脆弱性の一覧を取得します。
keywords: apis, graph api, supported api, get, vulnerability information, mdatp tvm api
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
ms.technology: mde
ms.openlocfilehash: c97b70b682351e5ad9d92435068b97622032f769
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166899"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="ebffd-104">脆弱性の一覧</span><span class="sxs-lookup"><span data-stu-id="ebffd-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ebffd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ebffd-105">**Applies to:**</span></span>
- [<span data-ttu-id="ebffd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ebffd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ebffd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebffd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ebffd-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ebffd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ebffd-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ebffd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ebffd-110">組織に影響を与えるすべての脆弱性の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="ebffd-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="ebffd-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ebffd-111">Permissions</span></span>
<span data-ttu-id="ebffd-112">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ebffd-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ebffd-113">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebffd-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ebffd-114">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="ebffd-114">Permission type</span></span> |   <span data-ttu-id="ebffd-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ebffd-115">Permission</span></span>  |   <span data-ttu-id="ebffd-116">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="ebffd-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ebffd-117">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ebffd-117">Application</span></span> |   <span data-ttu-id="ebffd-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="ebffd-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="ebffd-119">'脅威と脆弱性管理の脆弱性情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="ebffd-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="ebffd-120">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="ebffd-120">Delegated (work or school account)</span></span> | <span data-ttu-id="ebffd-121">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="ebffd-121">Vulnerability.Read</span></span> |   <span data-ttu-id="ebffd-122">'脅威と脆弱性管理の脆弱性情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="ebffd-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ebffd-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="ebffd-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="ebffd-124">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="ebffd-124">Request headers</span></span>

<span data-ttu-id="ebffd-125">名前</span><span class="sxs-lookup"><span data-stu-id="ebffd-125">Name</span></span> | <span data-ttu-id="ebffd-126">種類</span><span class="sxs-lookup"><span data-stu-id="ebffd-126">Type</span></span> | <span data-ttu-id="ebffd-127">説明</span><span class="sxs-lookup"><span data-stu-id="ebffd-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="ebffd-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="ebffd-128">Authorization</span></span> | <span data-ttu-id="ebffd-129">文字列</span><span class="sxs-lookup"><span data-stu-id="ebffd-129">String</span></span> | <span data-ttu-id="ebffd-130">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="ebffd-130">Bearer {token}.</span></span> <span data-ttu-id="ebffd-131">**必須**</span><span class="sxs-lookup"><span data-stu-id="ebffd-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ebffd-132">要求本文</span><span class="sxs-lookup"><span data-stu-id="ebffd-132">Request body</span></span>
<span data-ttu-id="ebffd-133">Empty</span><span class="sxs-lookup"><span data-stu-id="ebffd-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ebffd-134">応答</span><span class="sxs-lookup"><span data-stu-id="ebffd-134">Response</span></span>
<span data-ttu-id="ebffd-135">成功した場合、このメソッドは 200 OK を返し、本文の脆弱性の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="ebffd-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="ebffd-136">例</span><span class="sxs-lookup"><span data-stu-id="ebffd-136">Example</span></span>

<span data-ttu-id="ebffd-137">**要求**</span><span class="sxs-lookup"><span data-stu-id="ebffd-137">**Request**</span></span>

<span data-ttu-id="ebffd-138">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="ebffd-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="ebffd-139">**応答**</span><span class="sxs-lookup"><span data-stu-id="ebffd-139">**Response**</span></span>

<span data-ttu-id="ebffd-140">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="ebffd-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="ebffd-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebffd-141">See also</span></span>
- [<span data-ttu-id="ebffd-142">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="ebffd-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ebffd-143">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="ebffd-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
