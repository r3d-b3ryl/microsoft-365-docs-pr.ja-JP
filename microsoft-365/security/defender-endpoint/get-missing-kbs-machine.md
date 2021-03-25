---
title: デバイス ID で不足している KB を取得する
description: デバイス ID によって不足しているセキュリティ更新プログラムを取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, device id, threat & 脆弱性管理 api, mdatp tvm api
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
ms.openlocfilehash: 908ddf531a5a20b9811084ba534a152ad6158170
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198851"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="007eb-104">デバイス ID で不足している KB を取得する</span><span class="sxs-lookup"><span data-stu-id="007eb-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="007eb-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="007eb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="007eb-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="007eb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="007eb-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="007eb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="007eb-108">デバイス ID によって不足している KB (セキュリティ更新プログラム) を取得します。</span><span class="sxs-lookup"><span data-stu-id="007eb-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="007eb-109">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="007eb-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="007eb-110">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="007eb-110">Request header</span></span>

<span data-ttu-id="007eb-111">Name</span><span class="sxs-lookup"><span data-stu-id="007eb-111">Name</span></span> | <span data-ttu-id="007eb-112">種類</span><span class="sxs-lookup"><span data-stu-id="007eb-112">Type</span></span> | <span data-ttu-id="007eb-113">説明</span><span class="sxs-lookup"><span data-stu-id="007eb-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="007eb-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="007eb-114">Authorization</span></span> | <span data-ttu-id="007eb-115">文字列</span><span class="sxs-lookup"><span data-stu-id="007eb-115">String</span></span> | <span data-ttu-id="007eb-116">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="007eb-116">Bearer {token}.</span></span> <span data-ttu-id="007eb-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="007eb-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="007eb-118">要求本文</span><span class="sxs-lookup"><span data-stu-id="007eb-118">Request body</span></span>

<span data-ttu-id="007eb-119">Empty</span><span class="sxs-lookup"><span data-stu-id="007eb-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="007eb-120">応答</span><span class="sxs-lookup"><span data-stu-id="007eb-120">Response</span></span>

<span data-ttu-id="007eb-121">成功した場合、このメソッドは 200 OK を返し、指定したデバイスには本文に kb データがありません。</span><span class="sxs-lookup"><span data-stu-id="007eb-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="007eb-122">例</span><span class="sxs-lookup"><span data-stu-id="007eb-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="007eb-123">要求</span><span class="sxs-lookup"><span data-stu-id="007eb-123">Request</span></span>

<span data-ttu-id="007eb-124">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="007eb-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="007eb-125">応答</span><span class="sxs-lookup"><span data-stu-id="007eb-125">Response</span></span>

<span data-ttu-id="007eb-126">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="007eb-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="007eb-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="007eb-127">Related topics</span></span>

- [<span data-ttu-id="007eb-128">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="007eb-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="007eb-129">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="007eb-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
