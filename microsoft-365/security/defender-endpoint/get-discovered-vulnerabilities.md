---
title: 検出された脆弱性を取得する
description: 特定のデバイス ID に関連する検出された脆弱性のコレクションを取得します。
keywords: apis、 graph api、 supported apis, get, list, file, information, discovered vulnerabilits, threat & 脆弱性管理 api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 73b8fe5140ff635791e7d42358024bb7fb4ee926
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570329"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="cfb1f-104">検出された脆弱性を取得する</span><span class="sxs-lookup"><span data-stu-id="cfb1f-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cfb1f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cfb1f-105">**Applies to:**</span></span>
- [<span data-ttu-id="cfb1f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cfb1f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cfb1f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfb1f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cfb1f-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="cfb1f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cfb1f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="cfb1f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="cfb1f-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="cfb1f-110">API description</span></span>
<span data-ttu-id="cfb1f-111">特定のデバイス ID に関連する検出された脆弱性のコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="cfb1f-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="cfb1f-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="cfb1f-112">Limitations</span></span>
1. <span data-ttu-id="cfb1f-113">この API のレート制限は、1 分あたり 50 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="cfb1f-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="cfb1f-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="cfb1f-114">Permissions</span></span>

<span data-ttu-id="cfb1f-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="cfb1f-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cfb1f-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cfb1f-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cfb1f-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="cfb1f-117">Permission type</span></span> | <span data-ttu-id="cfb1f-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="cfb1f-118">Permission</span></span> | <span data-ttu-id="cfb1f-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="cfb1f-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cfb1f-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="cfb1f-120">Application</span></span> |<span data-ttu-id="cfb1f-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="cfb1f-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="cfb1f-122">'脅威と脆弱性管理の脆弱性情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="cfb1f-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="cfb1f-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="cfb1f-123">Delegated (work or school account)</span></span> | <span data-ttu-id="cfb1f-124">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="cfb1f-124">Vulnerability.Read</span></span> | <span data-ttu-id="cfb1f-125">'脅威と脆弱性管理の脆弱性情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="cfb1f-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="cfb1f-126">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="cfb1f-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="cfb1f-127">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="cfb1f-127">Request headers</span></span>

<span data-ttu-id="cfb1f-128">名前</span><span class="sxs-lookup"><span data-stu-id="cfb1f-128">Name</span></span> | <span data-ttu-id="cfb1f-129">型</span><span class="sxs-lookup"><span data-stu-id="cfb1f-129">Type</span></span> | <span data-ttu-id="cfb1f-130">説明</span><span class="sxs-lookup"><span data-stu-id="cfb1f-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="cfb1f-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="cfb1f-131">Authorization</span></span> | <span data-ttu-id="cfb1f-132">String</span><span class="sxs-lookup"><span data-stu-id="cfb1f-132">String</span></span> | <span data-ttu-id="cfb1f-133">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="cfb1f-133">Bearer {token}.</span></span> <span data-ttu-id="cfb1f-134">**必須**</span><span class="sxs-lookup"><span data-stu-id="cfb1f-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="cfb1f-135">要求本文</span><span class="sxs-lookup"><span data-stu-id="cfb1f-135">Request body</span></span>

<span data-ttu-id="cfb1f-136">Empty</span><span class="sxs-lookup"><span data-stu-id="cfb1f-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cfb1f-137">応答</span><span class="sxs-lookup"><span data-stu-id="cfb1f-137">Response</span></span>

<span data-ttu-id="cfb1f-138">成功した場合、このメソッドは 200 OK を返し、検出された脆弱性情報を本文に返します。</span><span class="sxs-lookup"><span data-stu-id="cfb1f-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="cfb1f-139">例</span><span class="sxs-lookup"><span data-stu-id="cfb1f-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="cfb1f-140">要求</span><span class="sxs-lookup"><span data-stu-id="cfb1f-140">Request</span></span>

<span data-ttu-id="cfb1f-141">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="cfb1f-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="cfb1f-142">応答</span><span class="sxs-lookup"><span data-stu-id="cfb1f-142">Response</span></span>

<span data-ttu-id="cfb1f-143">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="cfb1f-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="cfb1f-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfb1f-144">See also</span></span>

- [<span data-ttu-id="cfb1f-145">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="cfb1f-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="cfb1f-146">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="cfb1f-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
