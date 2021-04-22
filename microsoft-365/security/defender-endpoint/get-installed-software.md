---
title: インストールされたソフトウェアを取得する
description: 特定のデバイス ID に関連するインストール済みソフトウェアのコレクションを取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, software inventory, installed software per device, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: ebd689fd53dd804f857c6bec7a412c27988835d0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935115"
---
# <a name="get-installed-software"></a><span data-ttu-id="76741-104">インストールされたソフトウェアを取得する</span><span class="sxs-lookup"><span data-stu-id="76741-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="76741-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="76741-105">**Applies to:**</span></span>
- [<span data-ttu-id="76741-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="76741-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76741-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76741-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="76741-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="76741-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76741-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="76741-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="76741-110">特定のデバイス ID に関連するインストール済みソフトウェアのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="76741-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="76741-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="76741-111">Permissions</span></span>
<span data-ttu-id="76741-112">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="76741-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="76741-113">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="76741-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="76741-114">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="76741-114">Permission type</span></span> |   <span data-ttu-id="76741-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="76741-115">Permission</span></span>  |   <span data-ttu-id="76741-116">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="76741-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="76741-117">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="76741-117">Application</span></span> |<span data-ttu-id="76741-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="76741-118">Software.Read.All</span></span> |    <span data-ttu-id="76741-119">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="76741-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="76741-120">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="76741-120">Delegated (work or school account)</span></span> | <span data-ttu-id="76741-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="76741-121">Software.Read</span></span> |    <span data-ttu-id="76741-122">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="76741-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="76741-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="76741-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="76741-124">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="76741-124">Request headers</span></span>

<span data-ttu-id="76741-125">名前</span><span class="sxs-lookup"><span data-stu-id="76741-125">Name</span></span> | <span data-ttu-id="76741-126">型</span><span class="sxs-lookup"><span data-stu-id="76741-126">Type</span></span> | <span data-ttu-id="76741-127">説明</span><span class="sxs-lookup"><span data-stu-id="76741-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="76741-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="76741-128">Authorization</span></span> | <span data-ttu-id="76741-129">String</span><span class="sxs-lookup"><span data-stu-id="76741-129">String</span></span> | <span data-ttu-id="76741-130">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="76741-130">Bearer {token}.</span></span> <span data-ttu-id="76741-131">**必須**</span><span class="sxs-lookup"><span data-stu-id="76741-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="76741-132">要求本文</span><span class="sxs-lookup"><span data-stu-id="76741-132">Request body</span></span>
<span data-ttu-id="76741-133">Empty</span><span class="sxs-lookup"><span data-stu-id="76741-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="76741-134">応答</span><span class="sxs-lookup"><span data-stu-id="76741-134">Response</span></span>
<span data-ttu-id="76741-135">成功した場合、このメソッドは、本文にインストールされているソフトウェア情報を含む 200 OK を返します。</span><span class="sxs-lookup"><span data-stu-id="76741-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="76741-136">例</span><span class="sxs-lookup"><span data-stu-id="76741-136">Example</span></span>

<span data-ttu-id="76741-137">**要求**</span><span class="sxs-lookup"><span data-stu-id="76741-137">**Request**</span></span>

<span data-ttu-id="76741-138">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="76741-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="76741-139">**応答**</span><span class="sxs-lookup"><span data-stu-id="76741-139">**Response**</span></span>

<span data-ttu-id="76741-140">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="76741-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="76741-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="76741-141">See also</span></span>

- [<span data-ttu-id="76741-142">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="76741-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="76741-143">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="76741-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
