---
title: ソフトウェア別に脆弱性を一覧表示する
description: インストールされているソフトウェアの脆弱性の一覧を取得します。
keywords: apis, graph api, supported api, get, vulnerabilities list, mdatp tvm api
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
ms.openlocfilehash: 8f05c1a67c845e7f88cbcb3ee88cf7a664d5a4bf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167211"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="f0e03-104">ソフトウェア別に脆弱性を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="f0e03-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f0e03-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f0e03-105">**Applies to:**</span></span>
- [<span data-ttu-id="f0e03-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f0e03-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f0e03-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0e03-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f0e03-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f0e03-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f0e03-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f0e03-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f0e03-110">インストールされているソフトウェアの脆弱性の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="f0e03-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="f0e03-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f0e03-111">Permissions</span></span>
<span data-ttu-id="f0e03-112">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0e03-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f0e03-113">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e03-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f0e03-114">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="f0e03-114">Permission type</span></span> |   <span data-ttu-id="f0e03-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f0e03-115">Permission</span></span>  |   <span data-ttu-id="f0e03-116">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="f0e03-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f0e03-117">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f0e03-117">Application</span></span> | <span data-ttu-id="f0e03-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="f0e03-118">Software.Read.All</span></span> | <span data-ttu-id="f0e03-119">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="f0e03-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="f0e03-120">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="f0e03-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f0e03-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="f0e03-121">Software.Read</span></span> | <span data-ttu-id="f0e03-122">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="f0e03-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f0e03-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="f0e03-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="f0e03-124">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f0e03-124">Request headers</span></span>

| <span data-ttu-id="f0e03-125">名前</span><span class="sxs-lookup"><span data-stu-id="f0e03-125">Name</span></span>        | <span data-ttu-id="f0e03-126">種類</span><span class="sxs-lookup"><span data-stu-id="f0e03-126">Type</span></span> | <span data-ttu-id="f0e03-127">説明</span><span class="sxs-lookup"><span data-stu-id="f0e03-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="f0e03-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="f0e03-128">Authorization</span></span> | <span data-ttu-id="f0e03-129">文字列</span><span class="sxs-lookup"><span data-stu-id="f0e03-129">String</span></span> | <span data-ttu-id="f0e03-130">ベアラー {token}。**必須**。</span><span class="sxs-lookup"><span data-stu-id="f0e03-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f0e03-131">要求本文</span><span class="sxs-lookup"><span data-stu-id="f0e03-131">Request body</span></span>
<span data-ttu-id="f0e03-132">Empty</span><span class="sxs-lookup"><span data-stu-id="f0e03-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f0e03-133">応答</span><span class="sxs-lookup"><span data-stu-id="f0e03-133">Response</span></span>
<span data-ttu-id="f0e03-134">成功した場合、このメソッドは 200 OK を返し、指定したソフトウェアによって公開される脆弱性の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="f0e03-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="f0e03-135">例</span><span class="sxs-lookup"><span data-stu-id="f0e03-135">Example</span></span>

<span data-ttu-id="f0e03-136">**要求**</span><span class="sxs-lookup"><span data-stu-id="f0e03-136">**Request**</span></span>

<span data-ttu-id="f0e03-137">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="f0e03-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="f0e03-138">**応答**</span><span class="sxs-lookup"><span data-stu-id="f0e03-138">**Response**</span></span>

<span data-ttu-id="f0e03-139">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="f0e03-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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

