---
title: サポートされている Microsoft Defender for Endpoint API
ms.reviewer: ''
description: API 呼び出しを作成できる特定のサポートされている Microsoft Defender for Endpoint エンティティについて説明します。
keywords: apis、サポートされている API、アクター、アラート、デバイス、ユーザー、ドメイン、IP、ファイル、高度なクエリ、高度な検索
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198326"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="ae3c8-104">サポートされている Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="ae3c8-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ae3c8-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ae3c8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ae3c8-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ae3c8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ae3c8-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="ae3c8-108">エンドポイント URI とバージョン管理</span><span class="sxs-lookup"><span data-stu-id="ae3c8-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="ae3c8-109">エンドポイント URI:            </span><span class="sxs-lookup"><span data-stu-id="ae3c8-109">Endpoint URI:</span></span>

> <span data-ttu-id="ae3c8-110">サービスベース URI は次の値です。 https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ae3c8-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="ae3c8-111">OData に基づくクエリには、'/api' プレフィックスがあります。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="ae3c8-112">たとえば、アラートを取得するには、GET 要求を https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="ae3c8-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="ae3c8-113">バージョン管理:</span><span class="sxs-lookup"><span data-stu-id="ae3c8-113">Versioning:</span></span>

> <span data-ttu-id="ae3c8-114">API はバージョン管理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="ae3c8-115">現在のバージョンは **V1.0 です**。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="ae3c8-116">特定のバージョンを使用するには、次の形式を使用します `https://api.securitycenter.microsoft.com/api/{Version}` 。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="ae3c8-117">例: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="ae3c8-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="ae3c8-118">任意のバージョン (例) を指定しない場合 https://api.securitycenter.microsoft.com/api/alerts は、最新バージョンにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="ae3c8-119">API 呼び出しを実行できる個々のサポートされるエンティティと、HTTP 要求値、要求ヘッダー、予期される応答などの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ae3c8-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ae3c8-120">In this section</span></span>

<span data-ttu-id="ae3c8-121">トピック</span><span class="sxs-lookup"><span data-stu-id="ae3c8-121">Topic</span></span> | <span data-ttu-id="ae3c8-122">説明</span><span class="sxs-lookup"><span data-stu-id="ae3c8-122">Description</span></span>
:---|:---
<span data-ttu-id="ae3c8-123">高度なハンティング</span><span class="sxs-lookup"><span data-stu-id="ae3c8-123">Advanced Hunting</span></span> | <span data-ttu-id="ae3c8-124">API からクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-124">Run queries from API.</span></span>
<span data-ttu-id="ae3c8-125">アラート</span><span class="sxs-lookup"><span data-stu-id="ae3c8-125">Alerts</span></span> | <span data-ttu-id="ae3c8-126">アラートの取得、アラートの作成、アラートの更新などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="ae3c8-127">ドメイン</span><span class="sxs-lookup"><span data-stu-id="ae3c8-127">Domains</span></span> | <span data-ttu-id="ae3c8-128">ドメイン関連デバイスの取得、ドメイン統計などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="ae3c8-129">Files</span><span class="sxs-lookup"><span data-stu-id="ae3c8-129">Files</span></span> | <span data-ttu-id="ae3c8-130">ファイル情報の取得、ファイル関連の通知、ファイル関連デバイス、ファイル統計などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="ae3c8-131">IPs</span><span class="sxs-lookup"><span data-stu-id="ae3c8-131">IPs</span></span> | <span data-ttu-id="ae3c8-132">IP 関連のアラートの取得や IP 統計情報の取得などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="ae3c8-133">マシン</span><span class="sxs-lookup"><span data-stu-id="ae3c8-133">Machines</span></span> | <span data-ttu-id="ae3c8-134">デバイスの取得、ID によるデバイスの取得、ログオンしているユーザーに関する情報、タグの編集などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="ae3c8-135">コンピューターのアクション</span><span class="sxs-lookup"><span data-stu-id="ae3c8-135">Machine Actions</span></span> | <span data-ttu-id="ae3c8-136">分離、ウイルス対策スキャンの実行などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="ae3c8-137">インジケーター</span><span class="sxs-lookup"><span data-stu-id="ae3c8-137">Indicators</span></span> | <span data-ttu-id="ae3c8-138">インジケーターの作成、インジケーターの取得、インジケーターの削除などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="ae3c8-139">Users</span><span class="sxs-lookup"><span data-stu-id="ae3c8-139">Users</span></span> | <span data-ttu-id="ae3c8-140">ユーザー関連の通知やユーザー関連デバイスの取得などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="ae3c8-141">スコア</span><span class="sxs-lookup"><span data-stu-id="ae3c8-141">Score</span></span> | <span data-ttu-id="ae3c8-142">露出スコアの取得やデバイスのセキュリティで保護されたスコアの取得などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="ae3c8-143">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="ae3c8-143">Software</span></span> | <span data-ttu-id="ae3c8-144">ソフトウェアによるリストの脆弱性などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="ae3c8-145">脆弱性</span><span class="sxs-lookup"><span data-stu-id="ae3c8-145">Vulnerability</span></span> | <span data-ttu-id="ae3c8-146">脆弱性によるリスト デバイスなどの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="ae3c8-147">推奨事項</span><span class="sxs-lookup"><span data-stu-id="ae3c8-147">Recommendation</span></span> | <span data-ttu-id="ae3c8-148">ID による推奨事項の取得などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae3c8-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae3c8-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae3c8-149">See also</span></span>
- [<span data-ttu-id="ae3c8-150">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ae3c8-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
