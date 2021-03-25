---
title: コンピューターとソフトウェアによってすべての脆弱性を取得する
description: コンピューターとソフトウェアによって組織に影響を与えるすべての脆弱性の一覧を取得します。
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
ms.openlocfilehash: f7d67948e3b3e7a1a878386a397d2f4a6e8e998e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166900"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="13882-104">コンピューターとソフトウェアによる脆弱性の一覧表示</span><span class="sxs-lookup"><span data-stu-id="13882-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="13882-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="13882-105">**Applies to:**</span></span>
- [<span data-ttu-id="13882-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="13882-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="13882-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13882-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="13882-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="13882-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="13882-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="13882-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="13882-110">コンピューターとソフトウェアごとに組織に影響を与えるすべての脆弱性の一覧 [を](machine.md) 取得 [します](software.md)。</span><span class="sxs-lookup"><span data-stu-id="13882-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="13882-111">脆弱性に修正 KB がある場合は、応答に表示されます。</span><span class="sxs-lookup"><span data-stu-id="13882-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="13882-112">[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="13882-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="13882-113">OData ```$filter``` は、すべてのプロパティでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="13882-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="13882-114">これは、Power BI 統合のための [素晴らしい API です](api-power-bi.md)。</span><span class="sxs-lookup"><span data-stu-id="13882-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="13882-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="13882-115">Permissions</span></span>
<span data-ttu-id="13882-116">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="13882-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="13882-117">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13882-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="13882-118">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="13882-118">Permission type</span></span> |   <span data-ttu-id="13882-119">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="13882-119">Permission</span></span>  |   <span data-ttu-id="13882-120">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="13882-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="13882-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="13882-121">Application</span></span> |   <span data-ttu-id="13882-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="13882-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="13882-123">'脅威と脆弱性管理の脆弱性情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="13882-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="13882-124">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="13882-124">Delegated (work or school account)</span></span> | <span data-ttu-id="13882-125">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="13882-125">Vulnerability.Read</span></span> |   <span data-ttu-id="13882-126">'脅威と脆弱性管理の脆弱性情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="13882-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="13882-127">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="13882-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="13882-128">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="13882-128">Request headers</span></span>

<span data-ttu-id="13882-129">名前</span><span class="sxs-lookup"><span data-stu-id="13882-129">Name</span></span> | <span data-ttu-id="13882-130">種類</span><span class="sxs-lookup"><span data-stu-id="13882-130">Type</span></span> | <span data-ttu-id="13882-131">説明</span><span class="sxs-lookup"><span data-stu-id="13882-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="13882-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="13882-132">Authorization</span></span> | <span data-ttu-id="13882-133">文字列</span><span class="sxs-lookup"><span data-stu-id="13882-133">String</span></span> | <span data-ttu-id="13882-134">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="13882-134">Bearer {token}.</span></span> <span data-ttu-id="13882-135">**必須**</span><span class="sxs-lookup"><span data-stu-id="13882-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="13882-136">要求本文</span><span class="sxs-lookup"><span data-stu-id="13882-136">Request body</span></span>
<span data-ttu-id="13882-137">Empty</span><span class="sxs-lookup"><span data-stu-id="13882-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="13882-138">応答</span><span class="sxs-lookup"><span data-stu-id="13882-138">Response</span></span>
<span data-ttu-id="13882-139">成功した場合、このメソッドは 200 OK を返し、本文の脆弱性の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="13882-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="13882-140">例</span><span class="sxs-lookup"><span data-stu-id="13882-140">Example</span></span>

<span data-ttu-id="13882-141">**要求**</span><span class="sxs-lookup"><span data-stu-id="13882-141">**Request**</span></span>

<span data-ttu-id="13882-142">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="13882-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="13882-143">**応答**</span><span class="sxs-lookup"><span data-stu-id="13882-143">**Response**</span></span>

<span data-ttu-id="13882-144">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="13882-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="13882-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="13882-145">See also</span></span>

- [<span data-ttu-id="13882-146">リスクベースの脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="13882-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="13882-147">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="13882-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
