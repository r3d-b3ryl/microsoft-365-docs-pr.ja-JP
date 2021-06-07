---
title: インストールされたソフトウェアを取得する
description: 特定のデバイス ID に関連するインストール済みソフトウェアのコレクションを取得します。
keywords: apis、 graph api, supported apis, get, list, file, information, software inventory, installed software per device, threat & 脆弱性の管理 api, Microsoft Defender for Endpoint tvm api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 35cbeedc5d13f5eeb99718b4f98e2d8aabe1e965
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770159"
---
# <a name="get-installed-software"></a><span data-ttu-id="c91b0-104">インストールされたソフトウェアを取得する</span><span class="sxs-lookup"><span data-stu-id="c91b0-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c91b0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c91b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="c91b0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c91b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c91b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c91b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c91b0-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="c91b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c91b0-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c91b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="c91b0-110">特定のデバイス ID に関連するインストール済みソフトウェアのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="c91b0-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="c91b0-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c91b0-111">Permissions</span></span>
<span data-ttu-id="c91b0-112">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c91b0-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c91b0-113">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c91b0-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c91b0-114">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="c91b0-114">Permission type</span></span> |   <span data-ttu-id="c91b0-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c91b0-115">Permission</span></span>  |   <span data-ttu-id="c91b0-116">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="c91b0-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c91b0-117">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c91b0-117">Application</span></span> |<span data-ttu-id="c91b0-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="c91b0-118">Software.Read.All</span></span> |    <span data-ttu-id="c91b0-119">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="c91b0-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="c91b0-120">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="c91b0-120">Delegated (work or school account)</span></span> | <span data-ttu-id="c91b0-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="c91b0-121">Software.Read</span></span> |    <span data-ttu-id="c91b0-122">'脅威と脆弱性管理ソフトウェア情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="c91b0-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="c91b0-123">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="c91b0-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="c91b0-124">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="c91b0-124">Request headers</span></span>

<span data-ttu-id="c91b0-125">名前</span><span class="sxs-lookup"><span data-stu-id="c91b0-125">Name</span></span> | <span data-ttu-id="c91b0-126">種類</span><span class="sxs-lookup"><span data-stu-id="c91b0-126">Type</span></span> | <span data-ttu-id="c91b0-127">説明</span><span class="sxs-lookup"><span data-stu-id="c91b0-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="c91b0-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="c91b0-128">Authorization</span></span> | <span data-ttu-id="c91b0-129">String</span><span class="sxs-lookup"><span data-stu-id="c91b0-129">String</span></span> | <span data-ttu-id="c91b0-130">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="c91b0-130">Bearer {token}.</span></span> <span data-ttu-id="c91b0-131">**必須**</span><span class="sxs-lookup"><span data-stu-id="c91b0-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c91b0-132">要求本文</span><span class="sxs-lookup"><span data-stu-id="c91b0-132">Request body</span></span>
<span data-ttu-id="c91b0-133">Empty</span><span class="sxs-lookup"><span data-stu-id="c91b0-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c91b0-134">応答</span><span class="sxs-lookup"><span data-stu-id="c91b0-134">Response</span></span>
<span data-ttu-id="c91b0-135">成功した場合、このメソッドは、本文にインストールされているソフトウェア情報を含む 200 OK を返します。</span><span class="sxs-lookup"><span data-stu-id="c91b0-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="c91b0-136">例</span><span class="sxs-lookup"><span data-stu-id="c91b0-136">Example</span></span>

<span data-ttu-id="c91b0-137">**要求**</span><span class="sxs-lookup"><span data-stu-id="c91b0-137">**Request**</span></span>

<span data-ttu-id="c91b0-138">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="c91b0-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="c91b0-139">**応答**</span><span class="sxs-lookup"><span data-stu-id="c91b0-139">**Response**</span></span>

<span data-ttu-id="c91b0-140">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="c91b0-140">Here is an example of the response.</span></span>


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

## <a name="see-also"></a><span data-ttu-id="c91b0-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="c91b0-141">See also</span></span>

- [<span data-ttu-id="c91b0-142">リスクベースの脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="c91b0-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c91b0-143">脅威&ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="c91b0-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
