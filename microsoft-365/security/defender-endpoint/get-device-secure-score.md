---
title: デバイスのセキュリティで保護されたスコアを取得する
description: 組織デバイスのセキュリティで保護されたスコアを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166887"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="b6cd4-104">デバイスのセキュリティで保護されたスコアを取得する</span><span class="sxs-lookup"><span data-stu-id="b6cd4-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b6cd4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b6cd4-105">**Applies to:**</span></span>
- [<span data-ttu-id="b6cd4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b6cd4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b6cd4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6cd4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b6cd4-108">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b6cd4-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b6cd4-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b6cd4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b6cd4-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="b6cd4-111">デバイスの [Microsoft Secure Score を取得します](tvm-microsoft-secure-score-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="b6cd4-112">デバイスの Microsoft セキュア スコアが高いということは、エンドポイントがサイバー セキュリティの脅威攻撃に対してより回復力があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="b6cd4-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b6cd4-113">Permissions</span></span>

<span data-ttu-id="b6cd4-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b6cd4-115">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b6cd4-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="b6cd4-116">Permission type</span></span> |   <span data-ttu-id="b6cd4-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b6cd4-117">Permission</span></span>  |   <span data-ttu-id="b6cd4-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="b6cd4-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b6cd4-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b6cd4-119">Application</span></span> |   <span data-ttu-id="b6cd4-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="b6cd4-120">Score.Read.Alll</span></span> |   <span data-ttu-id="b6cd4-121">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="b6cd4-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="b6cd4-122">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b6cd4-122">Delegated (work or school account)</span></span> | <span data-ttu-id="b6cd4-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="b6cd4-123">Score.Read</span></span> | <span data-ttu-id="b6cd4-124">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="b6cd4-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="b6cd4-125">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b6cd4-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="b6cd4-126">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b6cd4-126">Request headers</span></span>

<span data-ttu-id="b6cd4-127">名前</span><span class="sxs-lookup"><span data-stu-id="b6cd4-127">Name</span></span> | <span data-ttu-id="b6cd4-128">種類</span><span class="sxs-lookup"><span data-stu-id="b6cd4-128">Type</span></span> | <span data-ttu-id="b6cd4-129">説明</span><span class="sxs-lookup"><span data-stu-id="b6cd4-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="b6cd4-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="b6cd4-130">Authorization</span></span> | <span data-ttu-id="b6cd4-131">文字列</span><span class="sxs-lookup"><span data-stu-id="b6cd4-131">String</span></span> | <span data-ttu-id="b6cd4-132">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-132">Bearer {token}.</span></span> <span data-ttu-id="b6cd4-133">**必須**</span><span class="sxs-lookup"><span data-stu-id="b6cd4-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b6cd4-134">要求本文</span><span class="sxs-lookup"><span data-stu-id="b6cd4-134">Request body</span></span>

<span data-ttu-id="b6cd4-135">Empty</span><span class="sxs-lookup"><span data-stu-id="b6cd4-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b6cd4-136">応答</span><span class="sxs-lookup"><span data-stu-id="b6cd4-136">Response</span></span>

<span data-ttu-id="b6cd4-137">成功した場合、このメソッドは 200 OK を返し、デバイスのセキュリティで保護されたスコア データを応答本文に返します。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="b6cd4-138">例</span><span class="sxs-lookup"><span data-stu-id="b6cd4-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="b6cd4-139">要求</span><span class="sxs-lookup"><span data-stu-id="b6cd4-139">Request</span></span>

<span data-ttu-id="b6cd4-140">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="b6cd4-141">応答</span><span class="sxs-lookup"><span data-stu-id="b6cd4-141">Response</span></span>

<span data-ttu-id="b6cd4-142">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="b6cd4-143">ここに示す応答リストは、簡単に切り詰められることがあります。</span><span class="sxs-lookup"><span data-stu-id="b6cd4-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="b6cd4-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6cd4-144">See also</span></span>

- [<span data-ttu-id="b6cd4-145">エンドポイント用 Microsoft Defender を使用した OData クエリ</span><span class="sxs-lookup"><span data-stu-id="b6cd4-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)