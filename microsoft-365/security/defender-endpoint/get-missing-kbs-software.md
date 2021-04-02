---
title: ソフトウェア ID で不足している KB を取得する
description: ソフトウェア ID によって不足しているセキュリティ更新プログラムを取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, software ID, threat & 脆弱性管理 api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e5d84a3eadab85713779dd70848bc11d27484dcc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499390"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="74e41-104">ソフトウェア ID で不足している KB を取得する</span><span class="sxs-lookup"><span data-stu-id="74e41-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74e41-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="74e41-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="74e41-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="74e41-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74e41-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="74e41-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="74e41-108">ソフトウェア ID によって不足している KB (セキュリティ更新プログラム) を取得します。</span><span class="sxs-lookup"><span data-stu-id="74e41-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="74e41-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="74e41-109">Permissions</span></span>

<span data-ttu-id="74e41-110">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="74e41-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="74e41-111">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e41-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="74e41-112">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="74e41-112">Permission type</span></span> |   <span data-ttu-id="74e41-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="74e41-113">Permission</span></span>   |   <span data-ttu-id="74e41-114">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="74e41-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="74e41-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="74e41-115">Application</span></span> |<span data-ttu-id="74e41-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="74e41-116">Software.Read.All</span></span> |   <span data-ttu-id="74e41-117">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="74e41-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="74e41-118">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="74e41-118">Delegated (work or school account)</span></span> | <span data-ttu-id="74e41-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="74e41-119">Software.Read</span></span> |   <span data-ttu-id="74e41-120">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="74e41-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="74e41-121">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="74e41-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="74e41-122">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="74e41-122">Request header</span></span>

<span data-ttu-id="74e41-123">名前</span><span class="sxs-lookup"><span data-stu-id="74e41-123">Name</span></span> | <span data-ttu-id="74e41-124">型</span><span class="sxs-lookup"><span data-stu-id="74e41-124">Type</span></span> | <span data-ttu-id="74e41-125">説明</span><span class="sxs-lookup"><span data-stu-id="74e41-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="74e41-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="74e41-126">Authorization</span></span> | <span data-ttu-id="74e41-127">String</span><span class="sxs-lookup"><span data-stu-id="74e41-127">String</span></span> | <span data-ttu-id="74e41-128">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="74e41-128">Bearer {token}.</span></span> <span data-ttu-id="74e41-129">**必須**</span><span class="sxs-lookup"><span data-stu-id="74e41-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="74e41-130">要求本文</span><span class="sxs-lookup"><span data-stu-id="74e41-130">Request body</span></span>

<span data-ttu-id="74e41-131">Empty</span><span class="sxs-lookup"><span data-stu-id="74e41-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="74e41-132">応答</span><span class="sxs-lookup"><span data-stu-id="74e41-132">Response</span></span>

<span data-ttu-id="74e41-133">成功した場合、このメソッドは 200 OK を返し、指定したソフトウェアは本文に kb データがありません。</span><span class="sxs-lookup"><span data-stu-id="74e41-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="74e41-134">例</span><span class="sxs-lookup"><span data-stu-id="74e41-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="74e41-135">要求</span><span class="sxs-lookup"><span data-stu-id="74e41-135">Request</span></span>

<span data-ttu-id="74e41-136">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="74e41-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="74e41-137">応答</span><span class="sxs-lookup"><span data-stu-id="74e41-137">Response</span></span>

<span data-ttu-id="74e41-138">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="74e41-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="74e41-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="74e41-139">Related topics</span></span>

- [<span data-ttu-id="74e41-140">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="74e41-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="74e41-141">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="74e41-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
