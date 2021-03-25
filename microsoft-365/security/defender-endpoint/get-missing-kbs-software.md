---
title: ソフトウェア ID で不足している KB を取得する
description: ソフトウェア ID によって不足しているセキュリティ更新プログラムを取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, software ID, threat & 脆弱性管理 api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c90854b043674a61c4996456c9d718b3c25afd1c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197790"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="c7bdd-104">ソフトウェア ID で不足している KB を取得する</span><span class="sxs-lookup"><span data-stu-id="c7bdd-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c7bdd-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c7bdd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c7bdd-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c7bdd-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c7bdd-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="c7bdd-108">ソフトウェア ID によって不足している KB (セキュリティ更新プログラム) を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="c7bdd-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c7bdd-109">Permissions</span></span>

<span data-ttu-id="c7bdd-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c7bdd-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="c7bdd-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="c7bdd-112">Permission type</span></span> |   <span data-ttu-id="c7bdd-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c7bdd-113">Permission</span></span>   |   <span data-ttu-id="c7bdd-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="c7bdd-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c7bdd-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c7bdd-115">Application</span></span> |<span data-ttu-id="c7bdd-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="c7bdd-116">Software.Read.All</span></span> |   <span data-ttu-id="c7bdd-117">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="c7bdd-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="c7bdd-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="c7bdd-118">Delegated (work or school account)</span></span> | <span data-ttu-id="c7bdd-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="c7bdd-119">Software.Read</span></span> |   <span data-ttu-id="c7bdd-120">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="c7bdd-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="c7bdd-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="c7bdd-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="c7bdd-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="c7bdd-122">Request header</span></span>

<span data-ttu-id="c7bdd-123">Name</span><span class="sxs-lookup"><span data-stu-id="c7bdd-123">Name</span></span> | <span data-ttu-id="c7bdd-124">種類</span><span class="sxs-lookup"><span data-stu-id="c7bdd-124">Type</span></span> | <span data-ttu-id="c7bdd-125">説明</span><span class="sxs-lookup"><span data-stu-id="c7bdd-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="c7bdd-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="c7bdd-126">Authorization</span></span> | <span data-ttu-id="c7bdd-127">文字列</span><span class="sxs-lookup"><span data-stu-id="c7bdd-127">String</span></span> | <span data-ttu-id="c7bdd-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-128">Bearer {token}.</span></span> <span data-ttu-id="c7bdd-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="c7bdd-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c7bdd-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="c7bdd-130">Request body</span></span>

<span data-ttu-id="c7bdd-131">Empty</span><span class="sxs-lookup"><span data-stu-id="c7bdd-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c7bdd-132">応答</span><span class="sxs-lookup"><span data-stu-id="c7bdd-132">Response</span></span>

<span data-ttu-id="c7bdd-133">成功した場合、このメソッドは 200 OK を返し、指定したソフトウェアは本文に kb データがありません。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="c7bdd-134">例</span><span class="sxs-lookup"><span data-stu-id="c7bdd-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="c7bdd-135">要求</span><span class="sxs-lookup"><span data-stu-id="c7bdd-135">Request</span></span>

<span data-ttu-id="c7bdd-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="c7bdd-137">応答</span><span class="sxs-lookup"><span data-stu-id="c7bdd-137">Response</span></span>

<span data-ttu-id="c7bdd-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="c7bdd-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7bdd-139">Related topics</span></span>

- [<span data-ttu-id="c7bdd-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="c7bdd-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c7bdd-141">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="c7bdd-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)