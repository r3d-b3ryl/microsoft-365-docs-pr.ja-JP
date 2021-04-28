---
title: Id で 1 つの修復アクティビティを取得する
description: 指定した修復アクティビティの情報を返します。
keywords: apis, 修復, 修復 API, get, 修復タスク, リスト
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061164"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="ea119-104">Id で 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="ea119-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ea119-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ea119-105">**Applies to:**</span></span>

- [<span data-ttu-id="ea119-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ea119-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ea119-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea119-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ea119-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="ea119-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ea119-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ea119-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ea119-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="ea119-110">API description</span></span>

<span data-ttu-id="ea119-111">指定した修復アクティビティの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ea119-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="ea119-112">[すべての修復アクティビティを取得 [する]](get-remediation-all-activities.md)と同じ列を表示しますが、指定した修復アクティビティ _の結果のみを返します_。</span><span class="sxs-lookup"><span data-stu-id="ea119-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="ea119-113">[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="ea119-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="ea119-114">(id) の指定された修復アクティビティを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="ea119-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="ea119-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="ea119-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="ea119-116">**プロパティの** 詳細</span><span class="sxs-lookup"><span data-stu-id="ea119-116">**Properties** details</span></span>

<span data-ttu-id="ea119-117">プロパティ (id)</span><span class="sxs-lookup"><span data-stu-id="ea119-117">Property (id)</span></span> | <span data-ttu-id="ea119-118">データ型</span><span class="sxs-lookup"><span data-stu-id="ea119-118">Data type</span></span> | <span data-ttu-id="ea119-119">説明</span><span class="sxs-lookup"><span data-stu-id="ea119-119">Description</span></span> | <span data-ttu-id="ea119-120">返される値の例</span><span class="sxs-lookup"><span data-stu-id="ea119-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="ea119-121">category</span><span class="sxs-lookup"><span data-stu-id="ea119-121">category</span></span> | <span data-ttu-id="ea119-122">String</span><span class="sxs-lookup"><span data-stu-id="ea119-122">String</span></span> | <span data-ttu-id="ea119-123">修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)</span><span class="sxs-lookup"><span data-stu-id="ea119-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="ea119-124">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="ea119-124">Software</span></span>
<span data-ttu-id="ea119-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="ea119-125">completerEmail</span></span> | <span data-ttu-id="ea119-126">String</span><span class="sxs-lookup"><span data-stu-id="ea119-126">String</span></span> | <span data-ttu-id="ea119-127">修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる</span><span class="sxs-lookup"><span data-stu-id="ea119-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="ea119-128">null</span><span class="sxs-lookup"><span data-stu-id="ea119-128">null</span></span>
<span data-ttu-id="ea119-129">completerId</span><span class="sxs-lookup"><span data-stu-id="ea119-129">completerId</span></span> | <span data-ttu-id="ea119-130">String</span><span class="sxs-lookup"><span data-stu-id="ea119-130">String</span></span> | <span data-ttu-id="ea119-131">修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる</span><span class="sxs-lookup"><span data-stu-id="ea119-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="ea119-132">null</span><span class="sxs-lookup"><span data-stu-id="ea119-132">null</span></span>
<span data-ttu-id="ea119-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="ea119-133">completionMethod</span></span> | <span data-ttu-id="ea119-134">String</span><span class="sxs-lookup"><span data-stu-id="ea119-134">String</span></span> | <span data-ttu-id="ea119-135">修復アクティビティは、"完了としてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。</span><span class="sxs-lookup"><span data-stu-id="ea119-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="ea119-136">自動</span><span class="sxs-lookup"><span data-stu-id="ea119-136">Automatic</span></span>
<span data-ttu-id="ea119-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="ea119-137">createdOn</span></span> | <span data-ttu-id="ea119-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="ea119-138">DateTime</span></span> | <span data-ttu-id="ea119-139">この修復アクティビティが作成された時刻</span><span class="sxs-lookup"><span data-stu-id="ea119-139">Time this remediation activity was created</span></span> | <span data-ttu-id="ea119-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="ea119-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="ea119-141">説明</span><span class="sxs-lookup"><span data-stu-id="ea119-141">description</span></span> | <span data-ttu-id="ea119-142">String</span><span class="sxs-lookup"><span data-stu-id="ea119-142">String</span></span> | <span data-ttu-id="ea119-143">この修復アクティビティの説明</span><span class="sxs-lookup"><span data-stu-id="ea119-143">Description of this remediation activity</span></span> | <span data-ttu-id="ea119-144">Chrome を新しいバージョンに更新して、デバイスに影響を与える既知の 1248 件の脆弱性を軽減します。</span><span class="sxs-lookup"><span data-stu-id="ea119-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="ea119-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="ea119-145">dueOn</span></span> | <span data-ttu-id="ea119-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="ea119-146">DateTime</span></span> | <span data-ttu-id="ea119-147">この修復アクティビティの作成者セットの期限</span><span class="sxs-lookup"><span data-stu-id="ea119-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="ea119-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="ea119-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="ea119-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="ea119-149">fixedDevices</span></span> |  | <span data-ttu-id="ea119-150">固定されているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="ea119-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="ea119-151">2</span><span class="sxs-lookup"><span data-stu-id="ea119-151">2</span></span>
<span data-ttu-id="ea119-152">id</span><span class="sxs-lookup"><span data-stu-id="ea119-152">id</span></span> | <span data-ttu-id="ea119-153">String</span><span class="sxs-lookup"><span data-stu-id="ea119-153">String</span></span> | <span data-ttu-id="ea119-154">この修復アクティビティの ID</span><span class="sxs-lookup"><span data-stu-id="ea119-154">ID of this remediation activity</span></span> | <span data-ttu-id="ea119-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="ea119-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="ea119-156">nameId</span><span class="sxs-lookup"><span data-stu-id="ea119-156">nameId</span></span> | <span data-ttu-id="ea119-157">String</span><span class="sxs-lookup"><span data-stu-id="ea119-157">String</span></span> | <span data-ttu-id="ea119-158">関連する製品名</span><span class="sxs-lookup"><span data-stu-id="ea119-158">Related product name</span></span> | <span data-ttu-id="ea119-159">クロム</span><span class="sxs-lookup"><span data-stu-id="ea119-159">chrome</span></span>
<span data-ttu-id="ea119-160">priority</span><span class="sxs-lookup"><span data-stu-id="ea119-160">priority</span></span> | <span data-ttu-id="ea119-161">String</span><span class="sxs-lookup"><span data-stu-id="ea119-161">String</span></span> | <span data-ttu-id="ea119-162">この修復アクティビティの作成者セットの優先度 (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="ea119-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="ea119-163">高</span><span class="sxs-lookup"><span data-stu-id="ea119-163">High</span></span>
<span data-ttu-id="ea119-164">productId</span><span class="sxs-lookup"><span data-stu-id="ea119-164">productId</span></span> | <span data-ttu-id="ea119-165">String</span><span class="sxs-lookup"><span data-stu-id="ea119-165">String</span></span> | <span data-ttu-id="ea119-166">関連する製品 ID</span><span class="sxs-lookup"><span data-stu-id="ea119-166">Related product ID</span></span> | <span data-ttu-id="ea119-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="ea119-167">google-_-chrome</span></span>
<span data-ttu-id="ea119-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="ea119-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="ea119-169">String</span><span class="sxs-lookup"><span data-stu-id="ea119-169">String</span></span> | <span data-ttu-id="ea119-170">いくつかの構成変更は、ユーザーに影響がないデバイスに対してだけ要求できます。</span><span class="sxs-lookup"><span data-stu-id="ea119-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="ea119-171">この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。</span><span class="sxs-lookup"><span data-stu-id="ea119-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="ea119-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="ea119-172">AllExposedAssets</span></span>
<span data-ttu-id="ea119-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="ea119-173">rbacGroupNames</span></span> | <span data-ttu-id="ea119-174">String</span><span class="sxs-lookup"><span data-stu-id="ea119-174">String</span></span> | <span data-ttu-id="ea119-175">関連するデバイス グループ名</span><span class="sxs-lookup"><span data-stu-id="ea119-175">Related device group names</span></span> | <span data-ttu-id="ea119-176">[ "Windows サーバー", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="ea119-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="ea119-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="ea119-177">recommendedProgram</span></span> | <span data-ttu-id="ea119-178">String</span><span class="sxs-lookup"><span data-stu-id="ea119-178">String</span></span> | <span data-ttu-id="ea119-179">にアップグレードする推奨プログラム</span><span class="sxs-lookup"><span data-stu-id="ea119-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="ea119-180">null</span><span class="sxs-lookup"><span data-stu-id="ea119-180">null</span></span>
<span data-ttu-id="ea119-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="ea119-181">recommendedVendor</span></span> | <span data-ttu-id="ea119-182">String</span><span class="sxs-lookup"><span data-stu-id="ea119-182">String</span></span> | <span data-ttu-id="ea119-183">アップグレードの推奨ベンダー</span><span class="sxs-lookup"><span data-stu-id="ea119-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="ea119-184">null</span><span class="sxs-lookup"><span data-stu-id="ea119-184">null</span></span>
<span data-ttu-id="ea119-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="ea119-185">recommendedVersion</span></span> | <span data-ttu-id="ea119-186">String</span><span class="sxs-lookup"><span data-stu-id="ea119-186">String</span></span> | <span data-ttu-id="ea119-187">更新/アップグレードの推奨バージョン</span><span class="sxs-lookup"><span data-stu-id="ea119-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="ea119-188">null</span><span class="sxs-lookup"><span data-stu-id="ea119-188">null</span></span>
<span data-ttu-id="ea119-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="ea119-189">relatedComponent</span></span> | <span data-ttu-id="ea119-190">String</span><span class="sxs-lookup"><span data-stu-id="ea119-190">String</span></span> | <span data-ttu-id="ea119-191">この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)</span><span class="sxs-lookup"><span data-stu-id="ea119-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="ea119-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="ea119-192">Google Chrome</span></span>
<span data-ttu-id="ea119-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="ea119-193">requesterEmail</span></span> | <span data-ttu-id="ea119-194">String</span><span class="sxs-lookup"><span data-stu-id="ea119-194">String</span></span> | <span data-ttu-id="ea119-195">作成者の電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="ea119-195">Creator email address</span></span> | <span data-ttu-id="ea119-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea119-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="ea119-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="ea119-197">requesterId</span></span> | <span data-ttu-id="ea119-198">String</span><span class="sxs-lookup"><span data-stu-id="ea119-198">String</span></span> | <span data-ttu-id="ea119-199">Creator オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="ea119-199">Creator object id</span></span> | <span data-ttu-id="ea119-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="ea119-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="ea119-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="ea119-201">requesterNotes</span></span> | <span data-ttu-id="ea119-202">String</span><span class="sxs-lookup"><span data-stu-id="ea119-202">String</span></span> | <span data-ttu-id="ea119-203">この修復アクティビティに作成者が追加したメモ (フリー テキスト)</span><span class="sxs-lookup"><span data-stu-id="ea119-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="ea119-204">null</span><span class="sxs-lookup"><span data-stu-id="ea119-204">null</span></span>
<span data-ttu-id="ea119-205">scid</span><span class="sxs-lookup"><span data-stu-id="ea119-205">scid</span></span> | <span data-ttu-id="ea119-206">String</span><span class="sxs-lookup"><span data-stu-id="ea119-206">String</span></span> | <span data-ttu-id="ea119-207">関連するセキュリティ推奨事項の SCID</span><span class="sxs-lookup"><span data-stu-id="ea119-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="ea119-208">null</span><span class="sxs-lookup"><span data-stu-id="ea119-208">null</span></span>
<span data-ttu-id="ea119-209">status</span><span class="sxs-lookup"><span data-stu-id="ea119-209">status</span></span> | <span data-ttu-id="ea119-210">String</span><span class="sxs-lookup"><span data-stu-id="ea119-210">String</span></span> | <span data-ttu-id="ea119-211">修復アクティビティの状態 (アクティブ/完了)</span><span class="sxs-lookup"><span data-stu-id="ea119-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="ea119-212">Active</span><span class="sxs-lookup"><span data-stu-id="ea119-212">Active</span></span>
<span data-ttu-id="ea119-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="ea119-213">statusLastModifiedOn</span></span> | <span data-ttu-id="ea119-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="ea119-214">DateTime</span></span> | <span data-ttu-id="ea119-215">状態フィールドが更新された日付</span><span class="sxs-lookup"><span data-stu-id="ea119-215">Date when the status field was updated</span></span> | <span data-ttu-id="ea119-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="ea119-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="ea119-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="ea119-217">targetDevices</span></span> | <span data-ttu-id="ea119-218">Long</span><span class="sxs-lookup"><span data-stu-id="ea119-218">Long</span></span> | <span data-ttu-id="ea119-219">この修復が適用される公開デバイスの数</span><span class="sxs-lookup"><span data-stu-id="ea119-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="ea119-220">43</span><span class="sxs-lookup"><span data-stu-id="ea119-220">43</span></span>
<span data-ttu-id="ea119-221">title</span><span class="sxs-lookup"><span data-stu-id="ea119-221">title</span></span> | <span data-ttu-id="ea119-222">String</span><span class="sxs-lookup"><span data-stu-id="ea119-222">String</span></span> | <span data-ttu-id="ea119-223">この修復アクティビティのタイトル</span><span class="sxs-lookup"><span data-stu-id="ea119-223">Title of this remediation activity</span></span> | <span data-ttu-id="ea119-224">Google Chrome を更新する</span><span class="sxs-lookup"><span data-stu-id="ea119-224">Update Google Chrome</span></span>
<span data-ttu-id="ea119-225">type</span><span class="sxs-lookup"><span data-stu-id="ea119-225">type</span></span> | <span data-ttu-id="ea119-226">String</span><span class="sxs-lookup"><span data-stu-id="ea119-226">String</span></span> | <span data-ttu-id="ea119-227">修復の種類</span><span class="sxs-lookup"><span data-stu-id="ea119-227">Remediation type</span></span> | <span data-ttu-id="ea119-228">Update</span><span class="sxs-lookup"><span data-stu-id="ea119-228">Update</span></span>
<span data-ttu-id="ea119-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="ea119-229">vendorId</span></span> | <span data-ttu-id="ea119-230">String</span><span class="sxs-lookup"><span data-stu-id="ea119-230">String</span></span> | <span data-ttu-id="ea119-231">関連ベンダー名</span><span class="sxs-lookup"><span data-stu-id="ea119-231">Related vendor name</span></span> | <span data-ttu-id="ea119-232">google</span><span class="sxs-lookup"><span data-stu-id="ea119-232">google</span></span>

## <a name="example"></a><span data-ttu-id="ea119-233">例</span><span class="sxs-lookup"><span data-stu-id="ea119-233">Example</span></span>

<span data-ttu-id="ea119-234">**要求の** 例</span><span class="sxs-lookup"><span data-stu-id="ea119-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="ea119-235">**応答** の例</span><span class="sxs-lookup"><span data-stu-id="ea119-235">**Response** example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a><span data-ttu-id="ea119-236">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea119-236">See also</span></span>

- [<span data-ttu-id="ea119-237">修復方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="ea119-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="ea119-238">すべての修復アクティビティを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="ea119-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="ea119-239">1 つの修復アクティビティの公開デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="ea119-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="ea119-240">リスクベースの脅威と&管理</span><span class="sxs-lookup"><span data-stu-id="ea119-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="ea119-241">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="ea119-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
