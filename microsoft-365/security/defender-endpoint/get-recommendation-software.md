---
title: ソフトウェアによる推奨事項の取得
description: 特定のソフトウェアに関連するセキュリティ推奨事項を取得します。
keywords: apis、graph api、サポートされている API、get、セキュリティ推奨事項、ソフトウェアのセキュリティ推奨事項、脅威と脆弱性の管理、脅威と脆弱性管理 API
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
ms.openlocfilehash: 82479b0248ceee95321d269e3f48a4eeea3ad193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199503"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="a38fd-104">ソフトウェアによる推奨事項の取得</span><span class="sxs-lookup"><span data-stu-id="a38fd-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a38fd-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a38fd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a38fd-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a38fd-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a38fd-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="a38fd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a38fd-108">特定のソフトウェアに関連するセキュリティ推奨事項を取得します。</span><span class="sxs-lookup"><span data-stu-id="a38fd-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="a38fd-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a38fd-109">Permissions</span></span>
<span data-ttu-id="a38fd-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a38fd-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a38fd-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a38fd-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="a38fd-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="a38fd-112">Permission type</span></span> |   <span data-ttu-id="a38fd-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a38fd-113">Permission</span></span>  |   <span data-ttu-id="a38fd-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="a38fd-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a38fd-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a38fd-115">Application</span></span> |   <span data-ttu-id="a38fd-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="a38fd-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="a38fd-117">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="a38fd-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="a38fd-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="a38fd-118">Delegated (work or school account)</span></span> | <span data-ttu-id="a38fd-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="a38fd-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="a38fd-120">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="a38fd-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="a38fd-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="a38fd-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="a38fd-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a38fd-122">Request headers</span></span>

<span data-ttu-id="a38fd-123">名前</span><span class="sxs-lookup"><span data-stu-id="a38fd-123">Name</span></span> | <span data-ttu-id="a38fd-124">種類</span><span class="sxs-lookup"><span data-stu-id="a38fd-124">Type</span></span> | <span data-ttu-id="a38fd-125">説明</span><span class="sxs-lookup"><span data-stu-id="a38fd-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="a38fd-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="a38fd-126">Authorization</span></span> | <span data-ttu-id="a38fd-127">文字列</span><span class="sxs-lookup"><span data-stu-id="a38fd-127">String</span></span> | <span data-ttu-id="a38fd-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="a38fd-128">Bearer {token}.</span></span> <span data-ttu-id="a38fd-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="a38fd-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a38fd-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="a38fd-130">Request body</span></span>
<span data-ttu-id="a38fd-131">Empty</span><span class="sxs-lookup"><span data-stu-id="a38fd-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a38fd-132">応答</span><span class="sxs-lookup"><span data-stu-id="a38fd-132">Response</span></span>
<span data-ttu-id="a38fd-133">成功した場合、このメソッドは、本文のセキュリティ推奨事項に関連付けられたソフトウェアで 200 OK を返します。</span><span class="sxs-lookup"><span data-stu-id="a38fd-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="a38fd-134">例</span><span class="sxs-lookup"><span data-stu-id="a38fd-134">Example</span></span>

<span data-ttu-id="a38fd-135">**要求**</span><span class="sxs-lookup"><span data-stu-id="a38fd-135">**Request**</span></span>

<span data-ttu-id="a38fd-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="a38fd-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="a38fd-137">**応答**</span><span class="sxs-lookup"><span data-stu-id="a38fd-137">**Response**</span></span>

<span data-ttu-id="a38fd-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="a38fd-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="a38fd-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="a38fd-139">Related topics</span></span>
- [<span data-ttu-id="a38fd-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="a38fd-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="a38fd-141">脅威&脆弱性のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="a38fd-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
