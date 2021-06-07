---
title: 推奨事項別にデバイスを一覧表示する
description: セキュリティ推奨事項に関連付けられているデバイスの一覧を取得します。
keywords: apis、graph api、サポートされている api、get、脆弱なデバイスのセキュリティ推奨事項、脅威と脆弱性の管理、脅威と脆弱性の管理 API
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6c762a15051444ec950e92998317db4f7e51783c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771815"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="99689-104">推奨事項別にデバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="99689-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="99689-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="99689-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="99689-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="99689-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="99689-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="99689-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="99689-108">セキュリティ推奨事項に関連付けられているデバイスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="99689-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="99689-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="99689-109">Permissions</span></span>
<span data-ttu-id="99689-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="99689-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="99689-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99689-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="99689-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="99689-112">Permission type</span></span> |   <span data-ttu-id="99689-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="99689-113">Permission</span></span>  |   <span data-ttu-id="99689-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="99689-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="99689-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="99689-115">Application</span></span> |   <span data-ttu-id="99689-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="99689-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="99689-117">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="99689-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="99689-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="99689-118">Delegated (work or school account)</span></span> | <span data-ttu-id="99689-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="99689-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="99689-120">'脅威と脆弱性管理のセキュリティに関する推奨事項情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="99689-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="99689-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="99689-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="99689-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="99689-122">Request headers</span></span>

<span data-ttu-id="99689-123">名前</span><span class="sxs-lookup"><span data-stu-id="99689-123">Name</span></span> | <span data-ttu-id="99689-124">種類</span><span class="sxs-lookup"><span data-stu-id="99689-124">Type</span></span> | <span data-ttu-id="99689-125">説明</span><span class="sxs-lookup"><span data-stu-id="99689-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="99689-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="99689-126">Authorization</span></span> | <span data-ttu-id="99689-127">String</span><span class="sxs-lookup"><span data-stu-id="99689-127">String</span></span> | <span data-ttu-id="99689-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="99689-128">Bearer {token}.</span></span> <span data-ttu-id="99689-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="99689-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="99689-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="99689-130">Request body</span></span>
<span data-ttu-id="99689-131">Empty</span><span class="sxs-lookup"><span data-stu-id="99689-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="99689-132">応答</span><span class="sxs-lookup"><span data-stu-id="99689-132">Response</span></span>
<span data-ttu-id="99689-133">成功した場合、このメソッドは 200 OK を返し、セキュリティの推奨事項に関連付けられているデバイスの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="99689-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="99689-134">例</span><span class="sxs-lookup"><span data-stu-id="99689-134">Example</span></span>

<span data-ttu-id="99689-135">**要求**</span><span class="sxs-lookup"><span data-stu-id="99689-135">**Request**</span></span>

<span data-ttu-id="99689-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="99689-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="99689-137">**応答**</span><span class="sxs-lookup"><span data-stu-id="99689-137">**Response**</span></span>

<span data-ttu-id="99689-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="99689-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="99689-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="99689-139">Related topics</span></span>
- [<span data-ttu-id="99689-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="99689-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="99689-141">脅威&脆弱性のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="99689-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
