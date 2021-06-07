---
title: 推奨メソッドとプロパティ
description: 最近使用した上位のアラートを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: bd7aa2af2c7500bbe02108bb8aa5dee452ff2998
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771599"
---
# <a name="recommendation-resource-type"></a><span data-ttu-id="9e38b-104">おすすめリソースの種類</span><span class="sxs-lookup"><span data-stu-id="9e38b-104">Recommendation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9e38b-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9e38b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="9e38b-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="9e38b-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9e38b-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="9e38b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="9e38b-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e38b-108">Methods</span></span>
<span data-ttu-id="9e38b-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e38b-109">Method</span></span> |<span data-ttu-id="9e38b-110">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="9e38b-110">Return Type</span></span> |<span data-ttu-id="9e38b-111">説明</span><span class="sxs-lookup"><span data-stu-id="9e38b-111">Description</span></span>
:---|:---|:---
[<span data-ttu-id="9e38b-112">すべての推奨事項を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="9e38b-112">List all recommendations</span></span>](get-all-recommendations.md) | <span data-ttu-id="9e38b-113">おすすめコレクション</span><span class="sxs-lookup"><span data-stu-id="9e38b-113">Recommendation collection</span></span> | <span data-ttu-id="9e38b-114">組織に影響を与えるすべてのセキュリティ推奨事項の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e38b-114">Retrieves a list of all security recommendations affecting the organization</span></span>
[<span data-ttu-id="9e38b-115">ID による推奨事項の取得</span><span class="sxs-lookup"><span data-stu-id="9e38b-115">Get recommendation by Id</span></span>](get-recommendation-by-id.md) | <span data-ttu-id="9e38b-116">推奨事項</span><span class="sxs-lookup"><span data-stu-id="9e38b-116">Recommendation</span></span> | <span data-ttu-id="9e38b-117">セキュリティの推奨事項を ID で取得します。</span><span class="sxs-lookup"><span data-stu-id="9e38b-117">Retrieves a security recommendation by its ID</span></span>
[<span data-ttu-id="9e38b-118">おすすめソフトウェアを取得する</span><span class="sxs-lookup"><span data-stu-id="9e38b-118">Get recommendation software</span></span>](get-recommendation-software.md)| [<span data-ttu-id="9e38b-119">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="9e38b-119">Software</span></span>](software.md) | <span data-ttu-id="9e38b-120">特定のソフトウェアに関連するセキュリティ推奨事項を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e38b-120">Retrieves a security recommendation related to a specific software</span></span>
[<span data-ttu-id="9e38b-121">おすすめデバイスを取得する</span><span class="sxs-lookup"><span data-stu-id="9e38b-121">Get recommendation devices</span></span>](get-recommendation-machines.md)|<span data-ttu-id="9e38b-122">MachineRef コレクション</span><span class="sxs-lookup"><span data-stu-id="9e38b-122">MachineRef collection</span></span> | <span data-ttu-id="9e38b-123">セキュリティ推奨事項に関連付けられているデバイスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e38b-123">Retrieves a list of devices associated with the security recommendation</span></span>
[<span data-ttu-id="9e38b-124">推奨事項の脆弱性を取得する</span><span class="sxs-lookup"><span data-stu-id="9e38b-124">Get recommendation vulnerabilities</span></span>](get-recommendation-vulnerabilities.md) | <span data-ttu-id="9e38b-125">[脆弱性の](vulnerability.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="9e38b-125">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="9e38b-126">セキュリティ推奨事項に関連付けられている脆弱性の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e38b-126">Retrieves a list of vulnerabilities associated with the security recommendation</span></span>


## <a name="properties"></a><span data-ttu-id="9e38b-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e38b-127">Properties</span></span>
<span data-ttu-id="9e38b-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9e38b-128">Property</span></span> |   <span data-ttu-id="9e38b-129">種類</span><span class="sxs-lookup"><span data-stu-id="9e38b-129">Type</span></span>   |   <span data-ttu-id="9e38b-130">説明</span><span class="sxs-lookup"><span data-stu-id="9e38b-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="9e38b-131">id</span><span class="sxs-lookup"><span data-stu-id="9e38b-131">id</span></span> | <span data-ttu-id="9e38b-132">String</span><span class="sxs-lookup"><span data-stu-id="9e38b-132">String</span></span> | <span data-ttu-id="9e38b-133">推奨事項 ID</span><span class="sxs-lookup"><span data-stu-id="9e38b-133">Recommendation ID</span></span>
<span data-ttu-id="9e38b-134">productName</span><span class="sxs-lookup"><span data-stu-id="9e38b-134">productName</span></span> | <span data-ttu-id="9e38b-135">文字列型 (String)</span><span class="sxs-lookup"><span data-stu-id="9e38b-135">String</span></span> | <span data-ttu-id="9e38b-136">関連するソフトウェア名</span><span class="sxs-lookup"><span data-stu-id="9e38b-136">Related software name</span></span>  
<span data-ttu-id="9e38b-137">recommendationName</span><span class="sxs-lookup"><span data-stu-id="9e38b-137">recommendationName</span></span> | <span data-ttu-id="9e38b-138">String</span><span class="sxs-lookup"><span data-stu-id="9e38b-138">String</span></span> | <span data-ttu-id="9e38b-139">おすすめ名</span><span class="sxs-lookup"><span data-stu-id="9e38b-139">Recommendation name</span></span>
<span data-ttu-id="9e38b-140">弱点</span><span class="sxs-lookup"><span data-stu-id="9e38b-140">Weaknesses</span></span> | <span data-ttu-id="9e38b-141">Long</span><span class="sxs-lookup"><span data-stu-id="9e38b-141">Long</span></span> | <span data-ttu-id="9e38b-142">検出された脆弱性の数</span><span class="sxs-lookup"><span data-stu-id="9e38b-142">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="9e38b-143">ベンダー</span><span class="sxs-lookup"><span data-stu-id="9e38b-143">Vendor</span></span> | <span data-ttu-id="9e38b-144">String</span><span class="sxs-lookup"><span data-stu-id="9e38b-144">String</span></span> | <span data-ttu-id="9e38b-145">関連ベンダー名</span><span class="sxs-lookup"><span data-stu-id="9e38b-145">Related vendor name</span></span>
<span data-ttu-id="9e38b-146">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="9e38b-146">recommendedVersion</span></span> | <span data-ttu-id="9e38b-147">String</span><span class="sxs-lookup"><span data-stu-id="9e38b-147">String</span></span> | <span data-ttu-id="9e38b-148">推奨バージョン</span><span class="sxs-lookup"><span data-stu-id="9e38b-148">Recommended version</span></span>
<span data-ttu-id="9e38b-149">recommendationCategory</span><span class="sxs-lookup"><span data-stu-id="9e38b-149">recommendationCategory</span></span> | <span data-ttu-id="9e38b-150">String</span><span class="sxs-lookup"><span data-stu-id="9e38b-150">String</span></span> | <span data-ttu-id="9e38b-151">おすすめカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="9e38b-151">Recommendation category.</span></span> <span data-ttu-id="9e38b-152">使用できる値は、"Accounts"、"Application"、"Network"、"OS"、"SecurityStack" です。</span><span class="sxs-lookup"><span data-stu-id="9e38b-152">Possible values are: "Accounts", "Application", "Network", "OS", "SecurityStack</span></span>
<span data-ttu-id="9e38b-153">subCategory</span><span class="sxs-lookup"><span data-stu-id="9e38b-153">subCategory</span></span> | <span data-ttu-id="9e38b-154">String</span><span class="sxs-lookup"><span data-stu-id="9e38b-154">String</span></span> | <span data-ttu-id="9e38b-155">おすすめサブカテゴリ</span><span class="sxs-lookup"><span data-stu-id="9e38b-155">Recommendation sub-category</span></span>
<span data-ttu-id="9e38b-156">severityScore</span><span class="sxs-lookup"><span data-stu-id="9e38b-156">severityScore</span></span> | <span data-ttu-id="9e38b-157">Double</span><span class="sxs-lookup"><span data-stu-id="9e38b-157">Double</span></span> | <span data-ttu-id="9e38b-158">組織の Microsoft Secure Score for Devices に対する構成の潜在的な影響 (1-10)</span><span class="sxs-lookup"><span data-stu-id="9e38b-158">Potential impact of the configuration to the organization's Microsoft Secure Score for Devices (1-10)</span></span>
<span data-ttu-id="9e38b-159">publicExploit</span><span class="sxs-lookup"><span data-stu-id="9e38b-159">publicExploit</span></span> | <span data-ttu-id="9e38b-160">Boolean</span><span class="sxs-lookup"><span data-stu-id="9e38b-160">Boolean</span></span> | <span data-ttu-id="9e38b-161">パブリックエクスプロイトが利用可能</span><span class="sxs-lookup"><span data-stu-id="9e38b-161">Public exploit is available</span></span> 
<span data-ttu-id="9e38b-162">activeAlert</span><span class="sxs-lookup"><span data-stu-id="9e38b-162">activeAlert</span></span> | <span data-ttu-id="9e38b-163">Boolean</span><span class="sxs-lookup"><span data-stu-id="9e38b-163">Boolean</span></span> | <span data-ttu-id="9e38b-164">アクティブなアラートは、この推奨事項に関連付けられている</span><span class="sxs-lookup"><span data-stu-id="9e38b-164">Active alert is associated with this recommendation</span></span>
<span data-ttu-id="9e38b-165">associatedThreats</span><span class="sxs-lookup"><span data-stu-id="9e38b-165">associatedThreats</span></span> | <span data-ttu-id="9e38b-166">String collection</span><span class="sxs-lookup"><span data-stu-id="9e38b-166">String collection</span></span> | <span data-ttu-id="9e38b-167">脅威分析レポートは、この推奨事項に関連付けられている</span><span class="sxs-lookup"><span data-stu-id="9e38b-167">Threat analytics report is associated with this recommendation</span></span>
<span data-ttu-id="9e38b-168">remediationType</span><span class="sxs-lookup"><span data-stu-id="9e38b-168">remediationType</span></span> | <span data-ttu-id="9e38b-169">String</span><span class="sxs-lookup"><span data-stu-id="9e38b-169">String</span></span> | <span data-ttu-id="9e38b-170">修復の種類。</span><span class="sxs-lookup"><span data-stu-id="9e38b-170">Remediation type.</span></span> <span data-ttu-id="9e38b-171">指定できる値は、"ConfigurationChange"、"Update"、"Upgrade"、"Uninstall" です。</span><span class="sxs-lookup"><span data-stu-id="9e38b-171">Possible values are: "ConfigurationChange","Update","Upgrade","Uninstall"</span></span>
<span data-ttu-id="9e38b-172">状態</span><span class="sxs-lookup"><span data-stu-id="9e38b-172">Status</span></span> | <span data-ttu-id="9e38b-173">列挙</span><span class="sxs-lookup"><span data-stu-id="9e38b-173">Enum</span></span> | <span data-ttu-id="9e38b-174">推奨事項の例外の状態。</span><span class="sxs-lookup"><span data-stu-id="9e38b-174">Recommendation exception status.</span></span> <span data-ttu-id="9e38b-175">指定できる値は、"Active" と "Exception" です。</span><span class="sxs-lookup"><span data-stu-id="9e38b-175">Possible values are: "Active" and "Exception"</span></span>
<span data-ttu-id="9e38b-176">configScoreImpact</span><span class="sxs-lookup"><span data-stu-id="9e38b-176">configScoreImpact</span></span> | <span data-ttu-id="9e38b-177">Double</span><span class="sxs-lookup"><span data-stu-id="9e38b-177">Double</span></span> | <span data-ttu-id="9e38b-178">デバイスの Microsoft Secure Score の影響</span><span class="sxs-lookup"><span data-stu-id="9e38b-178">Microsoft Secure Score for Devices impact</span></span>
<span data-ttu-id="9e38b-179">exposureImpacte</span><span class="sxs-lookup"><span data-stu-id="9e38b-179">exposureImpacte</span></span> | <span data-ttu-id="9e38b-180">Double</span><span class="sxs-lookup"><span data-stu-id="9e38b-180">Double</span></span> | <span data-ttu-id="9e38b-181">露出スコアの影響</span><span class="sxs-lookup"><span data-stu-id="9e38b-181">Exposure score impact</span></span>
<span data-ttu-id="9e38b-182">totalMachineCount</span><span class="sxs-lookup"><span data-stu-id="9e38b-182">totalMachineCount</span></span> | <span data-ttu-id="9e38b-183">Long</span><span class="sxs-lookup"><span data-stu-id="9e38b-183">Long</span></span> | <span data-ttu-id="9e38b-184">インストールされているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="9e38b-184">Number of installed devices</span></span>
<span data-ttu-id="9e38b-185">exposedMachinesCount</span><span class="sxs-lookup"><span data-stu-id="9e38b-185">exposedMachinesCount</span></span> | <span data-ttu-id="9e38b-186">Long</span><span class="sxs-lookup"><span data-stu-id="9e38b-186">Long</span></span> | <span data-ttu-id="9e38b-187">脆弱性にさらされるインストール済みデバイスの数</span><span class="sxs-lookup"><span data-stu-id="9e38b-187">Number of installed devices that are exposed to vulnerabilities</span></span>
<span data-ttu-id="9e38b-188">nonProductivityImpactedAssets</span><span class="sxs-lookup"><span data-stu-id="9e38b-188">nonProductivityImpactedAssets</span></span> | <span data-ttu-id="9e38b-189">Long</span><span class="sxs-lookup"><span data-stu-id="9e38b-189">Long</span></span> | <span data-ttu-id="9e38b-190">影響を受けないデバイスの数</span><span class="sxs-lookup"><span data-stu-id="9e38b-190">Number of devices which are not affected</span></span>  
<span data-ttu-id="9e38b-191">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="9e38b-191">relatedComponent</span></span> | <span data-ttu-id="9e38b-192">String</span><span class="sxs-lookup"><span data-stu-id="9e38b-192">String</span></span> |  <span data-ttu-id="9e38b-193">関連するソフトウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9e38b-193">Related software component</span></span>
