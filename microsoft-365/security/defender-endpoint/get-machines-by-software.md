---
title: ソフトウェア別にデバイスを一覧表示する
description: このソフトウェアがインストールされているデバイスの一覧を取得します。
keywords: apis, graph api, supported api, get, list devices, devices list, list devices by software, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 8312818fe06b5a25ae32bf1f9585a51fe8848de6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845380"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="d5502-104">ソフトウェア別にデバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="d5502-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d5502-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d5502-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d5502-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="d5502-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d5502-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d5502-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d5502-108">このソフトウェアがインストールされているデバイス参照の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d5502-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="d5502-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d5502-109">Permissions</span></span>
<span data-ttu-id="d5502-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d5502-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d5502-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5502-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="d5502-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="d5502-112">Permission type</span></span> |   <span data-ttu-id="d5502-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d5502-113">Permission</span></span>  |   <span data-ttu-id="d5502-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="d5502-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d5502-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d5502-115">Application</span></span> | <span data-ttu-id="d5502-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="d5502-116">Software.Read.All</span></span> | <span data-ttu-id="d5502-117">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="d5502-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="d5502-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="d5502-118">Delegated (work or school account)</span></span> | <span data-ttu-id="d5502-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="d5502-119">Software.Read</span></span> | <span data-ttu-id="d5502-120">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="d5502-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="d5502-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="d5502-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="d5502-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="d5502-122">Request headers</span></span>

| <span data-ttu-id="d5502-123">名前</span><span class="sxs-lookup"><span data-stu-id="d5502-123">Name</span></span>        | <span data-ttu-id="d5502-124">型</span><span class="sxs-lookup"><span data-stu-id="d5502-124">Type</span></span> | <span data-ttu-id="d5502-125">説明</span><span class="sxs-lookup"><span data-stu-id="d5502-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="d5502-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="d5502-126">Authorization</span></span> | <span data-ttu-id="d5502-127">String</span><span class="sxs-lookup"><span data-stu-id="d5502-127">String</span></span> | <span data-ttu-id="d5502-128">ベアラー {token}。**必須**。</span><span class="sxs-lookup"><span data-stu-id="d5502-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d5502-129">要求本文</span><span class="sxs-lookup"><span data-stu-id="d5502-129">Request body</span></span>
<span data-ttu-id="d5502-130">Empty</span><span class="sxs-lookup"><span data-stu-id="d5502-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d5502-131">応答</span><span class="sxs-lookup"><span data-stu-id="d5502-131">Response</span></span>
<span data-ttu-id="d5502-132">成功した場合、このメソッドは 200 OK を返し、本体にソフトウェアがインストールされているデバイスの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="d5502-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="d5502-133">例</span><span class="sxs-lookup"><span data-stu-id="d5502-133">Example</span></span>

<span data-ttu-id="d5502-134">**要求**</span><span class="sxs-lookup"><span data-stu-id="d5502-134">**Request**</span></span>

<span data-ttu-id="d5502-135">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="d5502-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="d5502-136">**応答**</span><span class="sxs-lookup"><span data-stu-id="d5502-136">**Response**</span></span>

<span data-ttu-id="d5502-137">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="d5502-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="d5502-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5502-138">Related topics</span></span>
- [<span data-ttu-id="d5502-139">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="d5502-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="d5502-140">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="d5502-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
