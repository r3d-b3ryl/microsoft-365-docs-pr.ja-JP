---
title: デバイス グループ別の露出スコアの一覧表示
description: デバイス グループ別の露出スコアの一覧を取得します。
keywords: apis、graph api、サポートされている API、get、露出スコア、デバイス グループ、デバイス グループの露出スコア
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 54b3e0cd63189e67de0aa101634508ff8833dc6a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500244"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="b93f4-104">デバイス グループ別の露出スコアの一覧表示</span><span class="sxs-lookup"><span data-stu-id="b93f4-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b93f4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b93f4-105">**Applies to:**</span></span>
- [<span data-ttu-id="b93f4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b93f4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b93f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b93f4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b93f4-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b93f4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b93f4-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b93f4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b93f4-110">特定のドメイン アドレスに関連するアラートのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="b93f4-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="b93f4-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b93f4-111">Permissions</span></span>

<span data-ttu-id="b93f4-112">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="b93f4-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b93f4-113">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b93f4-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b93f4-114">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="b93f4-114">Permission type</span></span> |   <span data-ttu-id="b93f4-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b93f4-115">Permission</span></span>  |   <span data-ttu-id="b93f4-116">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="b93f4-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b93f4-117">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b93f4-117">Application</span></span> | <span data-ttu-id="b93f4-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="b93f4-118">Score.Read.All</span></span> | <span data-ttu-id="b93f4-119">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="b93f4-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="b93f4-120">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b93f4-120">Delegated (work or school account)</span></span> | <span data-ttu-id="b93f4-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="b93f4-121">Score.Read</span></span> | <span data-ttu-id="b93f4-122">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="b93f4-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="b93f4-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b93f4-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="b93f4-124">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b93f4-124">Request headers</span></span>

| <span data-ttu-id="b93f4-125">名前</span><span class="sxs-lookup"><span data-stu-id="b93f4-125">Name</span></span>        | <span data-ttu-id="b93f4-126">型</span><span class="sxs-lookup"><span data-stu-id="b93f4-126">Type</span></span> | <span data-ttu-id="b93f4-127">説明</span><span class="sxs-lookup"><span data-stu-id="b93f4-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="b93f4-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="b93f4-128">Authorization</span></span> | <span data-ttu-id="b93f4-129">String</span><span class="sxs-lookup"><span data-stu-id="b93f4-129">String</span></span> | <span data-ttu-id="b93f4-130">ベアラー {token}。**必須**。</span><span class="sxs-lookup"><span data-stu-id="b93f4-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b93f4-131">要求本文</span><span class="sxs-lookup"><span data-stu-id="b93f4-131">Request body</span></span>

<span data-ttu-id="b93f4-132">Empty</span><span class="sxs-lookup"><span data-stu-id="b93f4-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b93f4-133">応答</span><span class="sxs-lookup"><span data-stu-id="b93f4-133">Response</span></span>

<span data-ttu-id="b93f4-134">成功した場合、このメソッドは 200 OK を返し、応答本文のデバイス グループ データごとの露出スコアの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="b93f4-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="b93f4-135">例</span><span class="sxs-lookup"><span data-stu-id="b93f4-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="b93f4-136">要求</span><span class="sxs-lookup"><span data-stu-id="b93f4-136">Request</span></span>

<span data-ttu-id="b93f4-137">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="b93f4-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="b93f4-138">応答</span><span class="sxs-lookup"><span data-stu-id="b93f4-138">Response</span></span>

<span data-ttu-id="b93f4-139">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="b93f4-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b93f4-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="b93f4-140">Related topics</span></span>

- [<span data-ttu-id="b93f4-141">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="b93f4-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b93f4-142">脅威&脆弱性の暴露スコア</span><span class="sxs-lookup"><span data-stu-id="b93f4-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
