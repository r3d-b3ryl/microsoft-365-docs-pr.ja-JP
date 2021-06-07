---
title: デバイスのセキュア スコアを取得する
description: 組織デバイスのセキュリティで保護されたスコアを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd9def688619b6079d947cb76069aa0f77d768de
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772307"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="efb96-104">デバイスのセキュア スコアを取得する</span><span class="sxs-lookup"><span data-stu-id="efb96-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="efb96-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="efb96-105">**Applies to:**</span></span>
- [<span data-ttu-id="efb96-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="efb96-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="efb96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="efb96-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="efb96-108">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="efb96-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="efb96-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="efb96-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="efb96-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="efb96-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="efb96-111">デバイスの [Microsoft Secure Score を取得します](tvm-microsoft-secure-score-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="efb96-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="efb96-112">デバイスの Microsoft セキュア スコアが高いということは、エンドポイントがサイバー セキュリティの脅威攻撃に対してより回復力があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="efb96-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="efb96-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="efb96-113">Permissions</span></span>

<span data-ttu-id="efb96-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="efb96-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="efb96-115">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb96-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="efb96-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="efb96-116">Permission type</span></span> |   <span data-ttu-id="efb96-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="efb96-117">Permission</span></span>  |   <span data-ttu-id="efb96-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="efb96-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="efb96-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="efb96-119">Application</span></span> |   <span data-ttu-id="efb96-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="efb96-120">Score.Read.Alll</span></span> |   <span data-ttu-id="efb96-121">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="efb96-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="efb96-122">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="efb96-122">Delegated (work or school account)</span></span> | <span data-ttu-id="efb96-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="efb96-123">Score.Read</span></span> | <span data-ttu-id="efb96-124">'Read Threat and Vulnerability Management score'</span><span class="sxs-lookup"><span data-stu-id="efb96-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="efb96-125">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="efb96-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="efb96-126">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="efb96-126">Request headers</span></span>

<span data-ttu-id="efb96-127">名前</span><span class="sxs-lookup"><span data-stu-id="efb96-127">Name</span></span> | <span data-ttu-id="efb96-128">種類</span><span class="sxs-lookup"><span data-stu-id="efb96-128">Type</span></span> | <span data-ttu-id="efb96-129">説明</span><span class="sxs-lookup"><span data-stu-id="efb96-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="efb96-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="efb96-130">Authorization</span></span> | <span data-ttu-id="efb96-131">String</span><span class="sxs-lookup"><span data-stu-id="efb96-131">String</span></span> | <span data-ttu-id="efb96-132">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="efb96-132">Bearer {token}.</span></span> <span data-ttu-id="efb96-133">**必須**</span><span class="sxs-lookup"><span data-stu-id="efb96-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="efb96-134">要求本文</span><span class="sxs-lookup"><span data-stu-id="efb96-134">Request body</span></span>

<span data-ttu-id="efb96-135">Empty</span><span class="sxs-lookup"><span data-stu-id="efb96-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="efb96-136">応答</span><span class="sxs-lookup"><span data-stu-id="efb96-136">Response</span></span>

<span data-ttu-id="efb96-137">成功した場合、このメソッドは 200 OK を返し、デバイスのセキュリティで保護されたスコア データを応答本文に返します。</span><span class="sxs-lookup"><span data-stu-id="efb96-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="efb96-138">例</span><span class="sxs-lookup"><span data-stu-id="efb96-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="efb96-139">要求</span><span class="sxs-lookup"><span data-stu-id="efb96-139">Request</span></span>

<span data-ttu-id="efb96-140">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="efb96-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="efb96-141">応答</span><span class="sxs-lookup"><span data-stu-id="efb96-141">Response</span></span>

<span data-ttu-id="efb96-142">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="efb96-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="efb96-143">ここに示す応答リストは、簡単に切り詰められることがあります。</span><span class="sxs-lookup"><span data-stu-id="efb96-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="efb96-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="efb96-144">See also</span></span>

- [<span data-ttu-id="efb96-145">エンドポイント用 Microsoft Defender を使用した OData クエリ</span><span class="sxs-lookup"><span data-stu-id="efb96-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
