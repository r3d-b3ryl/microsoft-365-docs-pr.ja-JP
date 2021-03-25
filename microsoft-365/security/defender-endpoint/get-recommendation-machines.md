---
title: 推奨事項別にデバイスを一覧表示する
description: セキュリティ推奨事項に関連付けられているデバイスの一覧を取得します。
keywords: apis、graph api、サポートされている API、get、脆弱なデバイスのセキュリティ推奨事項、脅威と脆弱性の管理、脅威と脆弱性管理 API
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
ms.openlocfilehash: 515542f6eca208e92228a8d0b344b6013b11a148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198271"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="dfc47-104">推奨事項別にデバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="dfc47-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dfc47-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dfc47-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="dfc47-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="dfc47-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dfc47-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="dfc47-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="dfc47-108">セキュリティ推奨事項に関連付けられているデバイスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfc47-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="dfc47-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="dfc47-109">Permissions</span></span>
<span data-ttu-id="dfc47-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfc47-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dfc47-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfc47-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="dfc47-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="dfc47-112">Permission type</span></span> |   <span data-ttu-id="dfc47-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="dfc47-113">Permission</span></span>  |   <span data-ttu-id="dfc47-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="dfc47-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dfc47-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="dfc47-115">Application</span></span> |   <span data-ttu-id="dfc47-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="dfc47-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="dfc47-117">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="dfc47-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="dfc47-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="dfc47-118">Delegated (work or school account)</span></span> | <span data-ttu-id="dfc47-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="dfc47-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="dfc47-120">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="dfc47-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="dfc47-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="dfc47-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="dfc47-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="dfc47-122">Request headers</span></span>

<span data-ttu-id="dfc47-123">名前</span><span class="sxs-lookup"><span data-stu-id="dfc47-123">Name</span></span> | <span data-ttu-id="dfc47-124">種類</span><span class="sxs-lookup"><span data-stu-id="dfc47-124">Type</span></span> | <span data-ttu-id="dfc47-125">説明</span><span class="sxs-lookup"><span data-stu-id="dfc47-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="dfc47-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="dfc47-126">Authorization</span></span> | <span data-ttu-id="dfc47-127">文字列</span><span class="sxs-lookup"><span data-stu-id="dfc47-127">String</span></span> | <span data-ttu-id="dfc47-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="dfc47-128">Bearer {token}.</span></span> <span data-ttu-id="dfc47-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="dfc47-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="dfc47-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="dfc47-130">Request body</span></span>
<span data-ttu-id="dfc47-131">Empty</span><span class="sxs-lookup"><span data-stu-id="dfc47-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dfc47-132">応答</span><span class="sxs-lookup"><span data-stu-id="dfc47-132">Response</span></span>
<span data-ttu-id="dfc47-133">成功した場合、このメソッドは 200 OK を返し、セキュリティの推奨事項に関連付けられているデバイスの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="dfc47-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="dfc47-134">例</span><span class="sxs-lookup"><span data-stu-id="dfc47-134">Example</span></span>

<span data-ttu-id="dfc47-135">**要求**</span><span class="sxs-lookup"><span data-stu-id="dfc47-135">**Request**</span></span>

<span data-ttu-id="dfc47-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="dfc47-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="dfc47-137">**応答**</span><span class="sxs-lookup"><span data-stu-id="dfc47-137">**Response**</span></span>

<span data-ttu-id="dfc47-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="dfc47-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="dfc47-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfc47-139">Related topics</span></span>
- [<span data-ttu-id="dfc47-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="dfc47-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="dfc47-141">脅威&脆弱性のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="dfc47-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
