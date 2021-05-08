---
title: 修復アクティビティのメソッドとプロパティ
description: API 応答には、テナントで作成& 脆弱性の管理修復アクティビティの脅威が含まれる。 選択した修復タスクに対して、すべての修復アクティビティ、1 つの修復アクティビティ、または公開されているデバイスに関する情報を要求できます。
keywords: apis、修復、修復 API、get、修復タスク、修復方法、修復プロパティ、
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
ms.openlocfilehash: 4c0ecd89c45ec2c91dc37f0c9cd0bfb868c0474e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245542"
---
# <a name="remediation-activity-methods-and-properties"></a><span data-ttu-id="086a4-105">修復アクティビティのメソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="086a4-105">Remediation activity methods and properties</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="086a4-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="086a4-106">**Applies to:**</span></span>

- [<span data-ttu-id="086a4-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="086a4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="086a4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="086a4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="086a4-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="086a4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="086a4-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="086a4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="086a4-111">API 応答には、テナント [& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)   された脅威と修復アクティビティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="086a4-111">The API response contains [Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md) remediation activities that have been created in your tenant.</span></span>  

## <a name="methods"></a><span data-ttu-id="086a4-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="086a4-112">Methods</span></span>

<span data-ttu-id="086a4-113">メソッド</span><span class="sxs-lookup"><span data-stu-id="086a4-113">Method</span></span> | <span data-ttu-id="086a4-114">データ型</span><span class="sxs-lookup"><span data-stu-id="086a4-114">Data type</span></span> | <span data-ttu-id="086a4-115">説明</span><span class="sxs-lookup"><span data-stu-id="086a4-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="086a4-116">すべての修復作業を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="086a4-116">List all remediation activities</span></span>](get-remediation-all-activities.md) | <span data-ttu-id="086a4-117">調査コレクション</span><span class="sxs-lookup"><span data-stu-id="086a4-117">Investigation collection</span></span> | <span data-ttu-id="086a4-118">すべての修復アクティビティに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="086a4-118">Returns information about all remediation activities.</span></span>
[<span data-ttu-id="086a4-119">1 つの修復アクティビティの暴露デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="086a4-119">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md) | <span data-ttu-id="086a4-120">調査エンティティ</span><span class="sxs-lookup"><span data-stu-id="086a4-120">Investigation entity</span></span> | <span data-ttu-id="086a4-121">指定した修復アクティビティの公開デバイスに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="086a4-121">Returns information about exposed devices for the specified remediation activity.</span></span>
[<span data-ttu-id="086a4-122">ID による 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="086a4-122">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md) | <span data-ttu-id="086a4-123">調査エンティティ</span><span class="sxs-lookup"><span data-stu-id="086a4-123">Investigation entity</span></span> | <span data-ttu-id="086a4-124">指定した修復アクティビティの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="086a4-124">Returns information for the specified remediation activity.</span></span>

<span data-ttu-id="086a4-125">修復アクティビティの [詳細については、次の情報を参照してください](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="086a4-125">Learn more about [remediation activities](tvm-remediation.md).</span></span>

## <a name="properties"></a><span data-ttu-id="086a4-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="086a4-126">Properties</span></span>

<span data-ttu-id="086a4-127">プロパティ ID</span><span class="sxs-lookup"><span data-stu-id="086a4-127">Property id</span></span> | <span data-ttu-id="086a4-128">データ型</span><span class="sxs-lookup"><span data-stu-id="086a4-128">Data type</span></span> | <span data-ttu-id="086a4-129">説明</span><span class="sxs-lookup"><span data-stu-id="086a4-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="086a4-130">category</span><span class="sxs-lookup"><span data-stu-id="086a4-130">category</span></span> | <span data-ttu-id="086a4-131">String</span><span class="sxs-lookup"><span data-stu-id="086a4-131">String</span></span> | <span data-ttu-id="086a4-132">修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)</span><span class="sxs-lookup"><span data-stu-id="086a4-132">Category of the remediation activity (Software/Security configuration)</span></span>
<span data-ttu-id="086a4-133">completerEmail</span><span class="sxs-lookup"><span data-stu-id="086a4-133">completerEmail</span></span> | <span data-ttu-id="086a4-134">String</span><span class="sxs-lookup"><span data-stu-id="086a4-134">String</span></span> | <span data-ttu-id="086a4-135">修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる</span><span class="sxs-lookup"><span data-stu-id="086a4-135">If the remediation activity was manually completed by someone, this column contains their email</span></span>
<span data-ttu-id="086a4-136">completerId</span><span class="sxs-lookup"><span data-stu-id="086a4-136">completerId</span></span> | <span data-ttu-id="086a4-137">String</span><span class="sxs-lookup"><span data-stu-id="086a4-137">String</span></span> | <span data-ttu-id="086a4-138">修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる</span><span class="sxs-lookup"><span data-stu-id="086a4-138">If the remediation activity was manually completed by someone, this column contains their object id</span></span>
<span data-ttu-id="086a4-139">completionMethod</span><span class="sxs-lookup"><span data-stu-id="086a4-139">completionMethod</span></span> | <span data-ttu-id="086a4-140">String</span><span class="sxs-lookup"><span data-stu-id="086a4-140">String</span></span> | <span data-ttu-id="086a4-141">修復アクティビティは、"完了済みとしてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。</span><span class="sxs-lookup"><span data-stu-id="086a4-141">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed.”</span></span>
<span data-ttu-id="086a4-142">createdOn</span><span class="sxs-lookup"><span data-stu-id="086a4-142">createdOn</span></span> | <span data-ttu-id="086a4-143">DateTime</span><span class="sxs-lookup"><span data-stu-id="086a4-143">DateTime</span></span> | <span data-ttu-id="086a4-144">この修復アクティビティが作成された時刻</span><span class="sxs-lookup"><span data-stu-id="086a4-144">Time this remediation activity was created</span></span>
<span data-ttu-id="086a4-145">説明</span><span class="sxs-lookup"><span data-stu-id="086a4-145">description</span></span> | <span data-ttu-id="086a4-146">String</span><span class="sxs-lookup"><span data-stu-id="086a4-146">String</span></span> | <span data-ttu-id="086a4-147">この修復アクティビティの説明</span><span class="sxs-lookup"><span data-stu-id="086a4-147">Description of this remediation activity</span></span>
<span data-ttu-id="086a4-148">dueOn</span><span class="sxs-lookup"><span data-stu-id="086a4-148">dueOn</span></span> | <span data-ttu-id="086a4-149">DateTime</span><span class="sxs-lookup"><span data-stu-id="086a4-149">DateTime</span></span> | <span data-ttu-id="086a4-150">この修復アクティビティの作成者セットの期限</span><span class="sxs-lookup"><span data-stu-id="086a4-150">Due date the creator set for this remediation activity</span></span>
<span data-ttu-id="086a4-151">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="086a4-151">fixedDevices</span></span> |  | <span data-ttu-id="086a4-152">固定されているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="086a4-152">The number of devices that have been fixed</span></span>
<span data-ttu-id="086a4-153">id</span><span class="sxs-lookup"><span data-stu-id="086a4-153">id</span></span> | <span data-ttu-id="086a4-154">String</span><span class="sxs-lookup"><span data-stu-id="086a4-154">String</span></span> | <span data-ttu-id="086a4-155">この修復アクティビティの ID</span><span class="sxs-lookup"><span data-stu-id="086a4-155">ID of this remediation activity</span></span>
<span data-ttu-id="086a4-156">nameId</span><span class="sxs-lookup"><span data-stu-id="086a4-156">nameId</span></span> | <span data-ttu-id="086a4-157">String</span><span class="sxs-lookup"><span data-stu-id="086a4-157">String</span></span> | <span data-ttu-id="086a4-158">関連する製品名</span><span class="sxs-lookup"><span data-stu-id="086a4-158">Related product name</span></span>
<span data-ttu-id="086a4-159">priority</span><span class="sxs-lookup"><span data-stu-id="086a4-159">priority</span></span> | <span data-ttu-id="086a4-160">String</span><span class="sxs-lookup"><span data-stu-id="086a4-160">String</span></span> | <span data-ttu-id="086a4-161">この修復アクティビティの作成者セットの優先度 (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="086a4-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span>
<span data-ttu-id="086a4-162">productId</span><span class="sxs-lookup"><span data-stu-id="086a4-162">productId</span></span> | <span data-ttu-id="086a4-163">String</span><span class="sxs-lookup"><span data-stu-id="086a4-163">String</span></span> | <span data-ttu-id="086a4-164">関連する製品 ID</span><span class="sxs-lookup"><span data-stu-id="086a4-164">Related product ID</span></span>
<span data-ttu-id="086a4-165">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="086a4-165">productivityImpactRemediationType</span></span> | <span data-ttu-id="086a4-166">String</span><span class="sxs-lookup"><span data-stu-id="086a4-166">String</span></span> | <span data-ttu-id="086a4-167">いくつかの構成変更は、ユーザーに影響がないデバイスに対してだけ要求できます。</span><span class="sxs-lookup"><span data-stu-id="086a4-167">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="086a4-168">この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。</span><span class="sxs-lookup"><span data-stu-id="086a4-168">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span>
<span data-ttu-id="086a4-169">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="086a4-169">rbacGroupNames</span></span> | <span data-ttu-id="086a4-170">String</span><span class="sxs-lookup"><span data-stu-id="086a4-170">String</span></span> | <span data-ttu-id="086a4-171">関連するデバイス グループ名</span><span class="sxs-lookup"><span data-stu-id="086a4-171">Related device group names</span></span>
<span data-ttu-id="086a4-172">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="086a4-172">recommendedProgram</span></span> | <span data-ttu-id="086a4-173">String</span><span class="sxs-lookup"><span data-stu-id="086a4-173">String</span></span> | <span data-ttu-id="086a4-174">にアップグレードする推奨プログラム</span><span class="sxs-lookup"><span data-stu-id="086a4-174">Recommended program to upgrade to</span></span>
<span data-ttu-id="086a4-175">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="086a4-175">recommendedVendor</span></span> | <span data-ttu-id="086a4-176">String</span><span class="sxs-lookup"><span data-stu-id="086a4-176">String</span></span> | <span data-ttu-id="086a4-177">アップグレードの推奨ベンダー</span><span class="sxs-lookup"><span data-stu-id="086a4-177">Recommended vendor to upgrade to</span></span>
<span data-ttu-id="086a4-178">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="086a4-178">recommendedVersion</span></span> | <span data-ttu-id="086a4-179">String</span><span class="sxs-lookup"><span data-stu-id="086a4-179">String</span></span> | <span data-ttu-id="086a4-180">更新/アップグレードの推奨バージョン</span><span class="sxs-lookup"><span data-stu-id="086a4-180">Recommended version to update/upgrade to</span></span>
<span data-ttu-id="086a4-181">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="086a4-181">relatedComponent</span></span> | <span data-ttu-id="086a4-182">String</span><span class="sxs-lookup"><span data-stu-id="086a4-182">String</span></span> | <span data-ttu-id="086a4-183">この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)</span><span class="sxs-lookup"><span data-stu-id="086a4-183">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span>
<span data-ttu-id="086a4-184">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="086a4-184">requesterEmail</span></span> | <span data-ttu-id="086a4-185">String</span><span class="sxs-lookup"><span data-stu-id="086a4-185">String</span></span> | <span data-ttu-id="086a4-186">作成者の電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="086a4-186">Creator email address</span></span>
<span data-ttu-id="086a4-187">requesterId</span><span class="sxs-lookup"><span data-stu-id="086a4-187">requesterId</span></span> | <span data-ttu-id="086a4-188">String</span><span class="sxs-lookup"><span data-stu-id="086a4-188">String</span></span> | <span data-ttu-id="086a4-189">Creator オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="086a4-189">Creator object id</span></span>
<span data-ttu-id="086a4-190">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="086a4-190">requesterNotes</span></span> | <span data-ttu-id="086a4-191">String</span><span class="sxs-lookup"><span data-stu-id="086a4-191">String</span></span> | <span data-ttu-id="086a4-192">この修復アクティビティに作成者が追加したメモ (フリー テキスト)</span><span class="sxs-lookup"><span data-stu-id="086a4-192">The notes (free text) the creator added for this remediation activity</span></span>
<span data-ttu-id="086a4-193">scid</span><span class="sxs-lookup"><span data-stu-id="086a4-193">scid</span></span> | <span data-ttu-id="086a4-194">String</span><span class="sxs-lookup"><span data-stu-id="086a4-194">String</span></span> | <span data-ttu-id="086a4-195">関連するセキュリティ推奨事項の SCID</span><span class="sxs-lookup"><span data-stu-id="086a4-195">SCID of the related security recommendation</span></span>
<span data-ttu-id="086a4-196">status</span><span class="sxs-lookup"><span data-stu-id="086a4-196">status</span></span> | <span data-ttu-id="086a4-197">String</span><span class="sxs-lookup"><span data-stu-id="086a4-197">String</span></span> | <span data-ttu-id="086a4-198">修復アクティビティの状態 (アクティブ/完了)</span><span class="sxs-lookup"><span data-stu-id="086a4-198">Remediation activity status (Active/Completed)</span></span>
<span data-ttu-id="086a4-199">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="086a4-199">statusLastModifiedOn</span></span> | <span data-ttu-id="086a4-200">DateTime</span><span class="sxs-lookup"><span data-stu-id="086a4-200">DateTime</span></span> | <span data-ttu-id="086a4-201">状態フィールドが更新された日付</span><span class="sxs-lookup"><span data-stu-id="086a4-201">Date when the status field was updated</span></span>
<span data-ttu-id="086a4-202">targetDevices</span><span class="sxs-lookup"><span data-stu-id="086a4-202">targetDevices</span></span> | <span data-ttu-id="086a4-203">Long</span><span class="sxs-lookup"><span data-stu-id="086a4-203">Long</span></span> | <span data-ttu-id="086a4-204">この修復が適用される公開デバイスの数</span><span class="sxs-lookup"><span data-stu-id="086a4-204">Number of exposed devices that this remediation is applicable to</span></span>
<span data-ttu-id="086a4-205">title</span><span class="sxs-lookup"><span data-stu-id="086a4-205">title</span></span> | <span data-ttu-id="086a4-206">String</span><span class="sxs-lookup"><span data-stu-id="086a4-206">String</span></span> | <span data-ttu-id="086a4-207">この修復アクティビティのタイトル</span><span class="sxs-lookup"><span data-stu-id="086a4-207">Title of this remediation activity</span></span>
<span data-ttu-id="086a4-208">type</span><span class="sxs-lookup"><span data-stu-id="086a4-208">type</span></span> | <span data-ttu-id="086a4-209">String</span><span class="sxs-lookup"><span data-stu-id="086a4-209">String</span></span> | <span data-ttu-id="086a4-210">修復の種類</span><span class="sxs-lookup"><span data-stu-id="086a4-210">Remediation type</span></span>
<span data-ttu-id="086a4-211">vendorId</span><span class="sxs-lookup"><span data-stu-id="086a4-211">vendorId</span></span> | <span data-ttu-id="086a4-212">String</span><span class="sxs-lookup"><span data-stu-id="086a4-212">String</span></span> | <span data-ttu-id="086a4-213">関連ベンダー名</span><span class="sxs-lookup"><span data-stu-id="086a4-213">Related vendor name</span></span>

## <a name="see-also"></a><span data-ttu-id="086a4-214">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="086a4-214">See also</span></span>

- [<span data-ttu-id="086a4-215">ID による 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="086a4-215">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="086a4-216">すべての修復作業を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="086a4-216">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="086a4-217">1 つの修復アクティビティの暴露デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="086a4-217">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="086a4-218">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="086a4-218">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="086a4-219">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="086a4-219">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
