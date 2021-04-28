---
title: サポート対象 Microsoft Defender for Endpoint API
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
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073831"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="b83cf-104">サポート対象 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="b83cf-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b83cf-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b83cf-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b83cf-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="b83cf-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b83cf-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b83cf-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="b83cf-108">エンドポイント URI とバージョン管理</span><span class="sxs-lookup"><span data-stu-id="b83cf-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="b83cf-109">エンドポイント URI</span><span class="sxs-lookup"><span data-stu-id="b83cf-109">Endpoint URI</span></span>

> <span data-ttu-id="b83cf-110">サービスベース URI は次の値です。 [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b83cf-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="b83cf-111">OData に基づくクエリには、'/api' プレフィックスがあります。</span><span class="sxs-lookup"><span data-stu-id="b83cf-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="b83cf-112">たとえば、アラートを取得するには、GET 要求を [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="b83cf-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="b83cf-113">バージョン管理</span><span class="sxs-lookup"><span data-stu-id="b83cf-113">Versioning</span></span>

> <span data-ttu-id="b83cf-114">API はバージョン管理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b83cf-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="b83cf-115">現在のバージョンは **V1.0 です**。</span><span class="sxs-lookup"><span data-stu-id="b83cf-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="b83cf-116">特定のバージョンを使用するには、次の形式を使用します `https://api.securitycenter.microsoft.com/api/{Version}` 。</span><span class="sxs-lookup"><span data-stu-id="b83cf-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="b83cf-117">例: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="b83cf-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="b83cf-118">任意のバージョン (例) を指定しない場合 `https://api.securitycenter.microsoft.com/api/alerts` は、最新バージョンにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b83cf-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b83cf-119">API 呼び出しを実行できる個々のサポートされるエンティティと、HTTP 要求値、要求ヘッダー、予期される応答などの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b83cf-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b83cf-120">In this section</span></span>

<span data-ttu-id="b83cf-121">トピック</span><span class="sxs-lookup"><span data-stu-id="b83cf-121">Topic</span></span> | <span data-ttu-id="b83cf-122">説明</span><span class="sxs-lookup"><span data-stu-id="b83cf-122">Description</span></span>
:---|:---
[<span data-ttu-id="b83cf-123">高度な追求</span><span class="sxs-lookup"><span data-stu-id="b83cf-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="b83cf-124">API からクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-124">Run queries from API.</span></span>
[<span data-ttu-id="b83cf-125">アラート メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="b83cf-126">アラートの取得、アラートの作成、アラートの更新などの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="b83cf-127">自動調査の方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="b83cf-128">調査のコレクションを取得する \- などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="b83cf-129">ドメイン関連のアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="b83cf-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="b83cf-130">ドメイン関連デバイスの取得、ドメイン統計などの API 呼び出 \- しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="b83cf-131">ファイル メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="b83cf-132">ファイル情報の取得、ファイル関連の通知、ファイル関連デバイス、ファイル統計などの API 呼び出し \- を実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="b83cf-133">インジケーター メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="b83cf-134">インジケーターの取得、インジケーターの作成、インジケーターの削除などの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="b83cf-135">IP 関連のアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="b83cf-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="b83cf-136">IP 関連のアラートの取得や IP 統計情報の取得などの \- API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="b83cf-137">マシン メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="b83cf-138">デバイスの取得、ID によるデバイスの取得、ログオンしているユーザーに関する情報、タグの編集などの API 呼び出 \- しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="b83cf-139">マシン アクション メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="b83cf-140">分離、ウイルス対策スキャンの実行などの API 呼び出し \- を実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="b83cf-141">推奨メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="b83cf-142">ID による推奨事項の取得などの \- API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="b83cf-143">スコア メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-143">Score methods and properties</span></span>](score.md) | <span data-ttu-id="b83cf-144">露出スコアの取得やデバイス \- のセキュリティで保護されたスコアの取得などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-144">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="b83cf-145">ソフトウェア メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-145">Software methods and properties</span></span>](software.md) | <span data-ttu-id="b83cf-146">ソフトウェアによるリストの脆弱性などの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-146">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="b83cf-147">ユーザー メソッド</span><span class="sxs-lookup"><span data-stu-id="b83cf-147">User methods</span></span>](user.md) | <span data-ttu-id="b83cf-148">ユーザー関連の通知やユーザー関連 \- デバイスの取得などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-148">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="b83cf-149">脆弱性メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="b83cf-149">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="b83cf-150">脆弱性によるリスト デバイスなどの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="b83cf-150">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="b83cf-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="b83cf-151">See also</span></span>

- [<span data-ttu-id="b83cf-152">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b83cf-152">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="b83cf-153">Microsoft Defender for Endpoint API リリース ノート</span><span class="sxs-lookup"><span data-stu-id="b83cf-153">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
