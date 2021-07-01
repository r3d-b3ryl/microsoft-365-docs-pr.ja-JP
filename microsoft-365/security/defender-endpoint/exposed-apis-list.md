---
title: サポート対象 Microsoft Defender for Endpoint API
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 3f0f7a2b6a10c3469f0689419934fd8d19070999
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228629"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="052b6-104">サポート対象 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="052b6-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="052b6-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="052b6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="052b6-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="052b6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="052b6-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="052b6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="052b6-108">エンドポイント URI とバージョン管理</span><span class="sxs-lookup"><span data-stu-id="052b6-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="052b6-109">エンドポイント URI</span><span class="sxs-lookup"><span data-stu-id="052b6-109">Endpoint URI</span></span>

> <span data-ttu-id="052b6-110">サービスベース URI は次の値です。 [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="052b6-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="052b6-111">OData に基づくクエリには、'/api' プレフィックスがあります。</span><span class="sxs-lookup"><span data-stu-id="052b6-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="052b6-112">たとえば、アラートを取得するには、GET 要求を [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="052b6-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="052b6-113">バージョン管理</span><span class="sxs-lookup"><span data-stu-id="052b6-113">Versioning</span></span>

> <span data-ttu-id="052b6-114">API はバージョン管理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="052b6-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="052b6-115">現在のバージョンは **V1.0 です**。</span><span class="sxs-lookup"><span data-stu-id="052b6-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="052b6-116">特定のバージョンを使用するには、次の形式を使用します `https://api.securitycenter.microsoft.com/api/{Version}` 。</span><span class="sxs-lookup"><span data-stu-id="052b6-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="052b6-117">例: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="052b6-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="052b6-118">任意のバージョン (例) を指定しない場合 `https://api.securitycenter.microsoft.com/api/alerts` は、最新バージョンにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="052b6-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts`) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="052b6-119">API 呼び出しを実行できる個々のサポートされるエンティティと、HTTP 要求値、要求ヘッダー、予期される応答などの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="052b6-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="052b6-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="052b6-120">In this section</span></span>

<span data-ttu-id="052b6-121">トピック</span><span class="sxs-lookup"><span data-stu-id="052b6-121">Topic</span></span> | <span data-ttu-id="052b6-122">説明</span><span class="sxs-lookup"><span data-stu-id="052b6-122">Description</span></span>
:---|:---
[<span data-ttu-id="052b6-123">高度な追求</span><span class="sxs-lookup"><span data-stu-id="052b6-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="052b6-124">API からクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-124">Run queries from API.</span></span>
[<span data-ttu-id="052b6-125">アラート メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="052b6-126">アラートの取得、アラートの作成、アラートの更新などの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="052b6-127">デバイスごとの評価方法とプロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="052b6-127">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md) | <span data-ttu-id="052b6-128">API 呼び出しを実行して、安全な構成評価のエクスポート、ソフトウェア インベントリ評価のエクスポート、ソフトウェアの脆弱性評価のエクスポート、デルタ エクスポート ソフトウェアの脆弱性評価など、デバイスごとに脆弱性評価を収集します。 \-</span><span class="sxs-lookup"><span data-stu-id="052b6-128">Run API calls to gather vulnerability assessments on a per-device basis, such as: \- export secure configuration assessment, export software inventory assessment,  export software vulnerabilities assessment, and delta export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="052b6-129">自動調査の方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="052b6-130">調査のコレクションを取得する \- などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="052b6-131">ドメイン関連のアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="052b6-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="052b6-132">ドメイン関連デバイスの取得、ドメイン統計などの API 呼び出 \- しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="052b6-133">ファイル メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="052b6-134">ファイル情報の取得、ファイル関連の通知、ファイル関連デバイス、ファイル統計などの API 呼び出し \- を実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="052b6-135">インジケーター メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="052b6-136">インジケーターの取得、インジケーターの作成、インジケーターの削除などの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="052b6-137">IP 関連のアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="052b6-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="052b6-138">IP 関連のアラートの取得や IP 統計情報の取得などの \- API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="052b6-139">マシン メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="052b6-140">デバイスの取得、ID によるデバイスの取得、ログオンしているユーザーに関する情報、タグの編集などの API 呼び出 \- しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="052b6-141">マシン アクション メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="052b6-142">分離、ウイルス対策スキャンの実行などの API 呼び出し \- を実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="052b6-143">推奨メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="052b6-144">ID による推奨事項の取得などの \- API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="052b6-145">修復アクティビティのメソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="052b6-146">すべての修復タスクの取得、公開されたデバイス修復タスクの取得、ID による 1 つの修復タスクの取得などの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="052b6-147">スコア メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="052b6-148">露出スコアの取得やデバイス \- のセキュリティで保護されたスコアの取得などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="052b6-149">ソフトウェア メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="052b6-150">ソフトウェアによるリストの脆弱性などの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="052b6-151">ユーザー メソッド</span><span class="sxs-lookup"><span data-stu-id="052b6-151">User methods</span></span>](user.md) | <span data-ttu-id="052b6-152">ユーザー関連の通知やユーザー関連 \- デバイスの取得などの API 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="052b6-153">脆弱性メソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="052b6-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="052b6-154">脆弱性によるリスト デバイスなどの API \- 呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="052b6-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="052b6-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="052b6-155">See also</span></span>

- [<span data-ttu-id="052b6-156">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="052b6-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="052b6-157">Microsoft Defender for Endpoint API リリース ノート</span><span class="sxs-lookup"><span data-stu-id="052b6-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
