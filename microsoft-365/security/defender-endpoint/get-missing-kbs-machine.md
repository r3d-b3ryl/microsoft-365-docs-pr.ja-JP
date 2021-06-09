---
title: デバイス ID で不足している KB を取得する
description: デバイス ID によって不足しているセキュリティ更新プログラムを取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, device id, threat & 脆弱性の管理 api, Microsoft Defender for Endpoint tvm api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 63400295061cd7adc58a4ddebf73f4c82b0cc969
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845236"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="8ac18-104">デバイス ID で不足している KB を取得する</span><span class="sxs-lookup"><span data-stu-id="8ac18-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ac18-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8ac18-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8ac18-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="8ac18-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8ac18-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8ac18-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="8ac18-108">デバイス ID によって不足している KB (セキュリティ更新プログラム) を取得します。</span><span class="sxs-lookup"><span data-stu-id="8ac18-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="8ac18-109">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="8ac18-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="8ac18-110">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8ac18-110">Request header</span></span>

<span data-ttu-id="8ac18-111">名前</span><span class="sxs-lookup"><span data-stu-id="8ac18-111">Name</span></span> | <span data-ttu-id="8ac18-112">型</span><span class="sxs-lookup"><span data-stu-id="8ac18-112">Type</span></span> | <span data-ttu-id="8ac18-113">説明</span><span class="sxs-lookup"><span data-stu-id="8ac18-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="8ac18-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="8ac18-114">Authorization</span></span> | <span data-ttu-id="8ac18-115">String</span><span class="sxs-lookup"><span data-stu-id="8ac18-115">String</span></span> | <span data-ttu-id="8ac18-116">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="8ac18-116">Bearer {token}.</span></span> <span data-ttu-id="8ac18-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="8ac18-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8ac18-118">要求本文</span><span class="sxs-lookup"><span data-stu-id="8ac18-118">Request body</span></span>

<span data-ttu-id="8ac18-119">Empty</span><span class="sxs-lookup"><span data-stu-id="8ac18-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8ac18-120">応答</span><span class="sxs-lookup"><span data-stu-id="8ac18-120">Response</span></span>

<span data-ttu-id="8ac18-121">成功した場合、このメソッドは 200 OK を返し、指定したデバイスには本文に kb データがありません。</span><span class="sxs-lookup"><span data-stu-id="8ac18-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="8ac18-122">例</span><span class="sxs-lookup"><span data-stu-id="8ac18-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="8ac18-123">要求</span><span class="sxs-lookup"><span data-stu-id="8ac18-123">Request</span></span>

<span data-ttu-id="8ac18-124">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="8ac18-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="8ac18-125">応答</span><span class="sxs-lookup"><span data-stu-id="8ac18-125">Response</span></span>

<span data-ttu-id="8ac18-126">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="8ac18-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="8ac18-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ac18-127">Related topics</span></span>

- [<span data-ttu-id="8ac18-128">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="8ac18-128">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8ac18-129">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="8ac18-129">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
