---
title: すべての修復アクティビティを一覧表示する
description: すべての修復アクティビティに関する情報を返します。
keywords: apis、修復、修復 API、get、修復タスク、
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061163"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="013f8-104">すべての修復アクティビティを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="013f8-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="013f8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="013f8-105">**Applies to:**</span></span>

- [<span data-ttu-id="013f8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="013f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="013f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="013f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="013f8-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="013f8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="013f8-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="013f8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="013f8-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="013f8-110">API description</span></span>

<span data-ttu-id="013f8-111">すべての修復アクティビティに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="013f8-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="013f8-112">[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="013f8-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="013f8-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="013f8-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="013f8-114">**プロパティの** 詳細</span><span class="sxs-lookup"><span data-stu-id="013f8-114">**Properties** details</span></span>

<span data-ttu-id="013f8-115">プロパティ (id)</span><span class="sxs-lookup"><span data-stu-id="013f8-115">Property (id)</span></span> | <span data-ttu-id="013f8-116">データ型</span><span class="sxs-lookup"><span data-stu-id="013f8-116">Data type</span></span> | <span data-ttu-id="013f8-117">説明</span><span class="sxs-lookup"><span data-stu-id="013f8-117">Description</span></span> | <span data-ttu-id="013f8-118">返される値の例</span><span class="sxs-lookup"><span data-stu-id="013f8-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="013f8-119">category</span><span class="sxs-lookup"><span data-stu-id="013f8-119">category</span></span> | <span data-ttu-id="013f8-120">String</span><span class="sxs-lookup"><span data-stu-id="013f8-120">String</span></span> | <span data-ttu-id="013f8-121">修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)</span><span class="sxs-lookup"><span data-stu-id="013f8-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="013f8-122">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="013f8-122">Software</span></span>
<span data-ttu-id="013f8-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="013f8-123">completerEmail</span></span> | <span data-ttu-id="013f8-124">String</span><span class="sxs-lookup"><span data-stu-id="013f8-124">String</span></span> | <span data-ttu-id="013f8-125">修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる</span><span class="sxs-lookup"><span data-stu-id="013f8-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="013f8-126">null</span><span class="sxs-lookup"><span data-stu-id="013f8-126">null</span></span>
<span data-ttu-id="013f8-127">completerId</span><span class="sxs-lookup"><span data-stu-id="013f8-127">completerId</span></span> | <span data-ttu-id="013f8-128">String</span><span class="sxs-lookup"><span data-stu-id="013f8-128">String</span></span> | <span data-ttu-id="013f8-129">修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる</span><span class="sxs-lookup"><span data-stu-id="013f8-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="013f8-130">null</span><span class="sxs-lookup"><span data-stu-id="013f8-130">null</span></span>
<span data-ttu-id="013f8-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="013f8-131">completionMethod</span></span> | <span data-ttu-id="013f8-132">String</span><span class="sxs-lookup"><span data-stu-id="013f8-132">String</span></span> | <span data-ttu-id="013f8-133">修復アクティビティは、"完了としてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。</span><span class="sxs-lookup"><span data-stu-id="013f8-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="013f8-134">自動</span><span class="sxs-lookup"><span data-stu-id="013f8-134">Automatic</span></span>
<span data-ttu-id="013f8-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="013f8-135">createdOn</span></span> | <span data-ttu-id="013f8-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="013f8-136">DateTime</span></span> | <span data-ttu-id="013f8-137">この修復アクティビティが作成された時刻</span><span class="sxs-lookup"><span data-stu-id="013f8-137">Time this remediation activity was created</span></span> | <span data-ttu-id="013f8-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="013f8-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="013f8-139">説明</span><span class="sxs-lookup"><span data-stu-id="013f8-139">description</span></span> | <span data-ttu-id="013f8-140">String</span><span class="sxs-lookup"><span data-stu-id="013f8-140">String</span></span> | <span data-ttu-id="013f8-141">この修復アクティビティの説明</span><span class="sxs-lookup"><span data-stu-id="013f8-141">Description of this remediation activity</span></span> | <span data-ttu-id="013f8-142">Chrome を新しいバージョンに更新して、デバイスに影響を与える既知の 1248 件の脆弱性を軽減します。</span><span class="sxs-lookup"><span data-stu-id="013f8-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="013f8-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="013f8-143">dueOn</span></span> | <span data-ttu-id="013f8-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="013f8-144">DateTime</span></span> | <span data-ttu-id="013f8-145">この修復アクティビティの作成者セットの期限</span><span class="sxs-lookup"><span data-stu-id="013f8-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="013f8-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="013f8-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="013f8-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="013f8-147">fixedDevices</span></span> | <span data-ttu-id="013f8-148">.</span><span class="sxs-lookup"><span data-stu-id="013f8-148">.</span></span> | <span data-ttu-id="013f8-149">固定されているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="013f8-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="013f8-150">2</span><span class="sxs-lookup"><span data-stu-id="013f8-150">2</span></span>
<span data-ttu-id="013f8-151">id</span><span class="sxs-lookup"><span data-stu-id="013f8-151">id</span></span> | <span data-ttu-id="013f8-152">String</span><span class="sxs-lookup"><span data-stu-id="013f8-152">String</span></span> | <span data-ttu-id="013f8-153">この修復アクティビティの ID</span><span class="sxs-lookup"><span data-stu-id="013f8-153">ID of this remediation activity</span></span> | <span data-ttu-id="013f8-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="013f8-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="013f8-155">nameId</span><span class="sxs-lookup"><span data-stu-id="013f8-155">nameId</span></span> | <span data-ttu-id="013f8-156">String</span><span class="sxs-lookup"><span data-stu-id="013f8-156">String</span></span> | <span data-ttu-id="013f8-157">関連する製品名</span><span class="sxs-lookup"><span data-stu-id="013f8-157">Related product name</span></span> | <span data-ttu-id="013f8-158">クロム</span><span class="sxs-lookup"><span data-stu-id="013f8-158">chrome</span></span>
<span data-ttu-id="013f8-159">priority</span><span class="sxs-lookup"><span data-stu-id="013f8-159">priority</span></span> | <span data-ttu-id="013f8-160">String</span><span class="sxs-lookup"><span data-stu-id="013f8-160">String</span></span> | <span data-ttu-id="013f8-161">この修復アクティビティの作成者セットの優先度 (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="013f8-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="013f8-162">高</span><span class="sxs-lookup"><span data-stu-id="013f8-162">High</span></span>
<span data-ttu-id="013f8-163">productId</span><span class="sxs-lookup"><span data-stu-id="013f8-163">productId</span></span> | <span data-ttu-id="013f8-164">String</span><span class="sxs-lookup"><span data-stu-id="013f8-164">String</span></span> | <span data-ttu-id="013f8-165">関連する製品 ID</span><span class="sxs-lookup"><span data-stu-id="013f8-165">Related product ID</span></span> | <span data-ttu-id="013f8-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="013f8-166">google-_-chrome</span></span>
<span data-ttu-id="013f8-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="013f8-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="013f8-168">String</span><span class="sxs-lookup"><span data-stu-id="013f8-168">String</span></span> | <span data-ttu-id="013f8-169">いくつかの構成変更は、ユーザーに影響がないデバイスに対してだけ要求できます。</span><span class="sxs-lookup"><span data-stu-id="013f8-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="013f8-170">この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。</span><span class="sxs-lookup"><span data-stu-id="013f8-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="013f8-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="013f8-171">AllExposedAssets</span></span>
<span data-ttu-id="013f8-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="013f8-172">rbacGroupNames</span></span> | <span data-ttu-id="013f8-173">String</span><span class="sxs-lookup"><span data-stu-id="013f8-173">String</span></span> | <span data-ttu-id="013f8-174">関連するデバイス グループ名</span><span class="sxs-lookup"><span data-stu-id="013f8-174">Related device group names</span></span> | <span data-ttu-id="013f8-175">[ "Windows サーバー", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="013f8-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="013f8-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="013f8-176">recommendedProgram</span></span> | <span data-ttu-id="013f8-177">String</span><span class="sxs-lookup"><span data-stu-id="013f8-177">String</span></span> | <span data-ttu-id="013f8-178">にアップグレードする推奨プログラム</span><span class="sxs-lookup"><span data-stu-id="013f8-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="013f8-179">null</span><span class="sxs-lookup"><span data-stu-id="013f8-179">null</span></span>
<span data-ttu-id="013f8-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="013f8-180">recommendedVendor</span></span> | <span data-ttu-id="013f8-181">String</span><span class="sxs-lookup"><span data-stu-id="013f8-181">String</span></span> | <span data-ttu-id="013f8-182">アップグレードの推奨ベンダー</span><span class="sxs-lookup"><span data-stu-id="013f8-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="013f8-183">null</span><span class="sxs-lookup"><span data-stu-id="013f8-183">null</span></span>
<span data-ttu-id="013f8-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="013f8-184">recommendedVersion</span></span> | <span data-ttu-id="013f8-185">String</span><span class="sxs-lookup"><span data-stu-id="013f8-185">String</span></span> | <span data-ttu-id="013f8-186">更新/アップグレードの推奨バージョン</span><span class="sxs-lookup"><span data-stu-id="013f8-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="013f8-187">null</span><span class="sxs-lookup"><span data-stu-id="013f8-187">null</span></span>
<span data-ttu-id="013f8-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="013f8-188">relatedComponent</span></span> | <span data-ttu-id="013f8-189">String</span><span class="sxs-lookup"><span data-stu-id="013f8-189">String</span></span> | <span data-ttu-id="013f8-190">この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)</span><span class="sxs-lookup"><span data-stu-id="013f8-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="013f8-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="013f8-191">Google Chrome</span></span>
<span data-ttu-id="013f8-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="013f8-192">requesterEmail</span></span> | <span data-ttu-id="013f8-193">String</span><span class="sxs-lookup"><span data-stu-id="013f8-193">String</span></span> | <span data-ttu-id="013f8-194">作成者の電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="013f8-194">Creator email address</span></span> | <span data-ttu-id="013f8-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="013f8-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="013f8-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="013f8-196">requesterId</span></span> | <span data-ttu-id="013f8-197">String</span><span class="sxs-lookup"><span data-stu-id="013f8-197">String</span></span> | <span data-ttu-id="013f8-198">Creator オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="013f8-198">Creator object id</span></span> | <span data-ttu-id="013f8-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="013f8-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="013f8-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="013f8-200">requesterNotes</span></span> | <span data-ttu-id="013f8-201">String</span><span class="sxs-lookup"><span data-stu-id="013f8-201">String</span></span> | <span data-ttu-id="013f8-202">この修復アクティビティに作成者が追加したメモ (フリー テキスト)</span><span class="sxs-lookup"><span data-stu-id="013f8-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="013f8-203">null</span><span class="sxs-lookup"><span data-stu-id="013f8-203">null</span></span>
<span data-ttu-id="013f8-204">scid</span><span class="sxs-lookup"><span data-stu-id="013f8-204">scid</span></span> | <span data-ttu-id="013f8-205">String</span><span class="sxs-lookup"><span data-stu-id="013f8-205">String</span></span> | <span data-ttu-id="013f8-206">関連するセキュリティ推奨事項の SCID</span><span class="sxs-lookup"><span data-stu-id="013f8-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="013f8-207">null</span><span class="sxs-lookup"><span data-stu-id="013f8-207">null</span></span>
<span data-ttu-id="013f8-208">status</span><span class="sxs-lookup"><span data-stu-id="013f8-208">status</span></span> | <span data-ttu-id="013f8-209">String</span><span class="sxs-lookup"><span data-stu-id="013f8-209">String</span></span> | <span data-ttu-id="013f8-210">修復アクティビティの状態 (アクティブ/完了)</span><span class="sxs-lookup"><span data-stu-id="013f8-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="013f8-211">Active</span><span class="sxs-lookup"><span data-stu-id="013f8-211">Active</span></span>
<span data-ttu-id="013f8-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="013f8-212">statusLastModifiedOn</span></span> | <span data-ttu-id="013f8-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="013f8-213">DateTime</span></span> | <span data-ttu-id="013f8-214">状態フィールドが更新された日付</span><span class="sxs-lookup"><span data-stu-id="013f8-214">Date when the status field was updated</span></span> | <span data-ttu-id="013f8-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="013f8-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="013f8-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="013f8-216">targetDevices</span></span> | <span data-ttu-id="013f8-217">Long</span><span class="sxs-lookup"><span data-stu-id="013f8-217">Long</span></span> | <span data-ttu-id="013f8-218">この修復が適用される公開デバイスの数</span><span class="sxs-lookup"><span data-stu-id="013f8-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="013f8-219">43</span><span class="sxs-lookup"><span data-stu-id="013f8-219">43</span></span>
<span data-ttu-id="013f8-220">title</span><span class="sxs-lookup"><span data-stu-id="013f8-220">title</span></span> | <span data-ttu-id="013f8-221">String</span><span class="sxs-lookup"><span data-stu-id="013f8-221">String</span></span> | <span data-ttu-id="013f8-222">この修復アクティビティのタイトル</span><span class="sxs-lookup"><span data-stu-id="013f8-222">Title of this remediation activity</span></span> | <span data-ttu-id="013f8-223">Google Chrome を更新する</span><span class="sxs-lookup"><span data-stu-id="013f8-223">Update Google Chrome</span></span>
<span data-ttu-id="013f8-224">type</span><span class="sxs-lookup"><span data-stu-id="013f8-224">type</span></span> | <span data-ttu-id="013f8-225">String</span><span class="sxs-lookup"><span data-stu-id="013f8-225">String</span></span> | <span data-ttu-id="013f8-226">修復の種類</span><span class="sxs-lookup"><span data-stu-id="013f8-226">Remediation type</span></span> | <span data-ttu-id="013f8-227">Update</span><span class="sxs-lookup"><span data-stu-id="013f8-227">Update</span></span>
<span data-ttu-id="013f8-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="013f8-228">vendorId</span></span> | <span data-ttu-id="013f8-229">String</span><span class="sxs-lookup"><span data-stu-id="013f8-229">String</span></span> | <span data-ttu-id="013f8-230">関連ベンダー名</span><span class="sxs-lookup"><span data-stu-id="013f8-230">Related vendor name</span></span> | <span data-ttu-id="013f8-231">google</span><span class="sxs-lookup"><span data-stu-id="013f8-231">google</span></span>

## <a name="example"></a><span data-ttu-id="013f8-232">例</span><span class="sxs-lookup"><span data-stu-id="013f8-232">Example</span></span>

<span data-ttu-id="013f8-233">**要求の** 例</span><span class="sxs-lookup"><span data-stu-id="013f8-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="013f8-234">**応答** の例</span><span class="sxs-lookup"><span data-stu-id="013f8-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="013f8-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="013f8-235">See also</span></span>

- [<span data-ttu-id="013f8-236">修復方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="013f8-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="013f8-237">Id で 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="013f8-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="013f8-238">1 つの修復アクティビティの公開デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="013f8-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="013f8-239">リスクベースの脅威と&管理</span><span class="sxs-lookup"><span data-stu-id="013f8-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="013f8-240">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="013f8-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
