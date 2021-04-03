---
title: 暴露スコアを取得する
description: 組織の露出スコアを取得します。
keywords: apis, graph api, supported apis, get, exposure score, 組織の露出スコア
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
ms.openlocfilehash: c6b3f965c7abb1cb9208f0bfa157c1fd8aa3f891
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500708"
---
# <a name="get-exposure-score"></a><span data-ttu-id="67bf2-104">暴露スコアを取得する</span><span class="sxs-lookup"><span data-stu-id="67bf2-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="67bf2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="67bf2-105">**Applies to:**</span></span>
- [<span data-ttu-id="67bf2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="67bf2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67bf2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67bf2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67bf2-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="67bf2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67bf2-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="67bf2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="67bf2-110">組織の露出スコアを取得します。</span><span class="sxs-lookup"><span data-stu-id="67bf2-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="67bf2-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="67bf2-111">Permissions</span></span>

<span data-ttu-id="67bf2-112">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="67bf2-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="67bf2-113">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="67bf2-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="67bf2-114">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="67bf2-114">Permission type</span></span> | <span data-ttu-id="67bf2-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="67bf2-115">Permission</span></span> | <span data-ttu-id="67bf2-116">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="67bf2-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="67bf2-117">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="67bf2-117">Application</span></span> | <span data-ttu-id="67bf2-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="67bf2-118">Score.Read.All</span></span> | <span data-ttu-id="67bf2-119">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="67bf2-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="67bf2-120">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="67bf2-120">Delegated (work or school account)</span></span> | <span data-ttu-id="67bf2-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="67bf2-121">Score.Read</span></span> | <span data-ttu-id="67bf2-122">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="67bf2-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="67bf2-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="67bf2-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="67bf2-124">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="67bf2-124">Request headers</span></span>

<span data-ttu-id="67bf2-125">名前</span><span class="sxs-lookup"><span data-stu-id="67bf2-125">Name</span></span> | <span data-ttu-id="67bf2-126">型</span><span class="sxs-lookup"><span data-stu-id="67bf2-126">Type</span></span> | <span data-ttu-id="67bf2-127">説明</span><span class="sxs-lookup"><span data-stu-id="67bf2-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="67bf2-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="67bf2-128">Authorization</span></span> | <span data-ttu-id="67bf2-129">String</span><span class="sxs-lookup"><span data-stu-id="67bf2-129">String</span></span> | <span data-ttu-id="67bf2-130">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="67bf2-130">Bearer {token}.</span></span> <span data-ttu-id="67bf2-131">**必須**</span><span class="sxs-lookup"><span data-stu-id="67bf2-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="67bf2-132">要求本文</span><span class="sxs-lookup"><span data-stu-id="67bf2-132">Request body</span></span>

<span data-ttu-id="67bf2-133">Empty</span><span class="sxs-lookup"><span data-stu-id="67bf2-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="67bf2-134">応答</span><span class="sxs-lookup"><span data-stu-id="67bf2-134">Response</span></span>

<span data-ttu-id="67bf2-135">成功した場合、このメソッドは 200 OK を返し、応答本文に露出データを返します。</span><span class="sxs-lookup"><span data-stu-id="67bf2-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="67bf2-136">例</span><span class="sxs-lookup"><span data-stu-id="67bf2-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="67bf2-137">要求</span><span class="sxs-lookup"><span data-stu-id="67bf2-137">Request</span></span>

<span data-ttu-id="67bf2-138">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="67bf2-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="67bf2-139">応答</span><span class="sxs-lookup"><span data-stu-id="67bf2-139">Response</span></span>

<span data-ttu-id="67bf2-140">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="67bf2-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="67bf2-141">ここに示す応答リストは、簡単に切り詰められることがあります。</span><span class="sxs-lookup"><span data-stu-id="67bf2-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="67bf2-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="67bf2-142">See also</span></span>

- [<span data-ttu-id="67bf2-143">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="67bf2-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="67bf2-144">脅威&脆弱性の暴露スコア</span><span class="sxs-lookup"><span data-stu-id="67bf2-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
