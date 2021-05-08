---
title: すべての修復作業を一覧表示する
description: すべての修復アクティビティに関する情報を返します。
keywords: apis、修復、修復 API、get、修復タスク、すべての修復、
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
ms.openlocfilehash: cf7c79cb6cc76af88ce0293a013ba6edbf435d8c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245494"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="a003c-104">すべての修復作業を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="a003c-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a003c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a003c-105">**Applies to:**</span></span>

- [<span data-ttu-id="a003c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a003c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a003c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a003c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a003c-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="a003c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a003c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="a003c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="a003c-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="a003c-110">API description</span></span>

<span data-ttu-id="a003c-111">すべての修復アクティビティに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a003c-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="a003c-112">[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="a003c-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="a003c-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="a003c-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="a003c-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a003c-114">Permissions</span></span>

<span data-ttu-id="a003c-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a003c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a003c-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a003c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="a003c-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="a003c-117">Permission type</span></span> | <span data-ttu-id="a003c-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a003c-118">Permission</span></span> | <span data-ttu-id="a003c-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="a003c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a003c-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a003c-120">Application</span></span> | <span data-ttu-id="a003c-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="a003c-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="a003c-122">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="a003c-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="a003c-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="a003c-123">Delegated (work or school account)</span></span> | <span data-ttu-id="a003c-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="a003c-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="a003c-125">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="a003c-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="a003c-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a003c-126">Properties</span></span>

<span data-ttu-id="a003c-127">プロパティ (id)</span><span class="sxs-lookup"><span data-stu-id="a003c-127">Property (id)</span></span> | <span data-ttu-id="a003c-128">データ型</span><span class="sxs-lookup"><span data-stu-id="a003c-128">Data type</span></span> | <span data-ttu-id="a003c-129">説明</span><span class="sxs-lookup"><span data-stu-id="a003c-129">Description</span></span> | <span data-ttu-id="a003c-130">返される値の例</span><span class="sxs-lookup"><span data-stu-id="a003c-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="a003c-131">category</span><span class="sxs-lookup"><span data-stu-id="a003c-131">category</span></span> | <span data-ttu-id="a003c-132">String</span><span class="sxs-lookup"><span data-stu-id="a003c-132">String</span></span> | <span data-ttu-id="a003c-133">修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)</span><span class="sxs-lookup"><span data-stu-id="a003c-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="a003c-134">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="a003c-134">Software</span></span>
<span data-ttu-id="a003c-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="a003c-135">completerEmail</span></span> | <span data-ttu-id="a003c-136">String</span><span class="sxs-lookup"><span data-stu-id="a003c-136">String</span></span> | <span data-ttu-id="a003c-137">修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる</span><span class="sxs-lookup"><span data-stu-id="a003c-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="a003c-138">null</span><span class="sxs-lookup"><span data-stu-id="a003c-138">null</span></span>
<span data-ttu-id="a003c-139">completerId</span><span class="sxs-lookup"><span data-stu-id="a003c-139">completerId</span></span> | <span data-ttu-id="a003c-140">String</span><span class="sxs-lookup"><span data-stu-id="a003c-140">String</span></span> | <span data-ttu-id="a003c-141">修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる</span><span class="sxs-lookup"><span data-stu-id="a003c-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="a003c-142">null</span><span class="sxs-lookup"><span data-stu-id="a003c-142">null</span></span>
<span data-ttu-id="a003c-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="a003c-143">completionMethod</span></span> | <span data-ttu-id="a003c-144">String</span><span class="sxs-lookup"><span data-stu-id="a003c-144">String</span></span> | <span data-ttu-id="a003c-145">修復アクティビティは、"完了としてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。</span><span class="sxs-lookup"><span data-stu-id="a003c-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="a003c-146">自動</span><span class="sxs-lookup"><span data-stu-id="a003c-146">Automatic</span></span>
<span data-ttu-id="a003c-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="a003c-147">createdOn</span></span> | <span data-ttu-id="a003c-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="a003c-148">DateTime</span></span> | <span data-ttu-id="a003c-149">この修復アクティビティが作成された時刻</span><span class="sxs-lookup"><span data-stu-id="a003c-149">Time this remediation activity was created</span></span> | <span data-ttu-id="a003c-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="a003c-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="a003c-151">説明</span><span class="sxs-lookup"><span data-stu-id="a003c-151">description</span></span> | <span data-ttu-id="a003c-152">String</span><span class="sxs-lookup"><span data-stu-id="a003c-152">String</span></span> | <span data-ttu-id="a003c-153">この修復アクティビティの説明</span><span class="sxs-lookup"><span data-stu-id="a003c-153">Description of this remediation activity</span></span> | <span data-ttu-id="a003c-154">デバイスに影響を与える既知の脆弱性を軽減するために、Microsoft Silverlight を新しいバージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="a003c-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="a003c-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="a003c-155">dueOn</span></span> | <span data-ttu-id="a003c-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="a003c-156">DateTime</span></span> | <span data-ttu-id="a003c-157">この修復アクティビティの作成者セットの期限</span><span class="sxs-lookup"><span data-stu-id="a003c-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="a003c-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="a003c-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="a003c-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="a003c-159">fixedDevices</span></span> | <span data-ttu-id="a003c-160">.</span><span class="sxs-lookup"><span data-stu-id="a003c-160">.</span></span> | <span data-ttu-id="a003c-161">固定されているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="a003c-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="a003c-162">2</span><span class="sxs-lookup"><span data-stu-id="a003c-162">2</span></span>
<span data-ttu-id="a003c-163">id</span><span class="sxs-lookup"><span data-stu-id="a003c-163">id</span></span> | <span data-ttu-id="a003c-164">String</span><span class="sxs-lookup"><span data-stu-id="a003c-164">String</span></span> | <span data-ttu-id="a003c-165">この修復アクティビティの ID</span><span class="sxs-lookup"><span data-stu-id="a003c-165">ID of this remediation activity</span></span> | <span data-ttu-id="a003c-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="a003c-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="a003c-167">nameId</span><span class="sxs-lookup"><span data-stu-id="a003c-167">nameId</span></span> | <span data-ttu-id="a003c-168">String</span><span class="sxs-lookup"><span data-stu-id="a003c-168">String</span></span> | <span data-ttu-id="a003c-169">関連する製品名</span><span class="sxs-lookup"><span data-stu-id="a003c-169">Related product name</span></span> | <span data-ttu-id="a003c-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="a003c-170">Microsoft Silverlight</span></span>
<span data-ttu-id="a003c-171">priority</span><span class="sxs-lookup"><span data-stu-id="a003c-171">priority</span></span> | <span data-ttu-id="a003c-172">String</span><span class="sxs-lookup"><span data-stu-id="a003c-172">String</span></span> | <span data-ttu-id="a003c-173">この修復アクティビティの作成者セットの優先度 (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="a003c-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="a003c-174">高い</span><span class="sxs-lookup"><span data-stu-id="a003c-174">High</span></span>
<span data-ttu-id="a003c-175">productId</span><span class="sxs-lookup"><span data-stu-id="a003c-175">productId</span></span> | <span data-ttu-id="a003c-176">String</span><span class="sxs-lookup"><span data-stu-id="a003c-176">String</span></span> | <span data-ttu-id="a003c-177">関連する製品 ID</span><span class="sxs-lookup"><span data-stu-id="a003c-177">Related product ID</span></span> | <span data-ttu-id="a003c-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="a003c-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="a003c-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="a003c-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="a003c-180">String</span><span class="sxs-lookup"><span data-stu-id="a003c-180">String</span></span> | <span data-ttu-id="a003c-181">いくつかの構成変更は、ユーザーに影響がないデバイスに対してだけ要求できます。</span><span class="sxs-lookup"><span data-stu-id="a003c-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="a003c-182">この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。</span><span class="sxs-lookup"><span data-stu-id="a003c-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="a003c-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="a003c-183">AllExposedAssets</span></span>
<span data-ttu-id="a003c-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="a003c-184">rbacGroupNames</span></span> | <span data-ttu-id="a003c-185">String</span><span class="sxs-lookup"><span data-stu-id="a003c-185">String</span></span> | <span data-ttu-id="a003c-186">関連するデバイス グループ名</span><span class="sxs-lookup"><span data-stu-id="a003c-186">Related device group names</span></span> | <span data-ttu-id="a003c-187">[ "Windows サーバー", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="a003c-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="a003c-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="a003c-188">recommendedProgram</span></span> | <span data-ttu-id="a003c-189">String</span><span class="sxs-lookup"><span data-stu-id="a003c-189">String</span></span> | <span data-ttu-id="a003c-190">にアップグレードする推奨プログラム</span><span class="sxs-lookup"><span data-stu-id="a003c-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="a003c-191">null</span><span class="sxs-lookup"><span data-stu-id="a003c-191">null</span></span>
<span data-ttu-id="a003c-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="a003c-192">recommendedVendor</span></span> | <span data-ttu-id="a003c-193">String</span><span class="sxs-lookup"><span data-stu-id="a003c-193">String</span></span> | <span data-ttu-id="a003c-194">アップグレードの推奨ベンダー</span><span class="sxs-lookup"><span data-stu-id="a003c-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="a003c-195">null</span><span class="sxs-lookup"><span data-stu-id="a003c-195">null</span></span>
<span data-ttu-id="a003c-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="a003c-196">recommendedVersion</span></span> | <span data-ttu-id="a003c-197">String</span><span class="sxs-lookup"><span data-stu-id="a003c-197">String</span></span> | <span data-ttu-id="a003c-198">更新/アップグレードの推奨バージョン</span><span class="sxs-lookup"><span data-stu-id="a003c-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="a003c-199">null</span><span class="sxs-lookup"><span data-stu-id="a003c-199">null</span></span>
<span data-ttu-id="a003c-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="a003c-200">relatedComponent</span></span> | <span data-ttu-id="a003c-201">String</span><span class="sxs-lookup"><span data-stu-id="a003c-201">String</span></span> | <span data-ttu-id="a003c-202">この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)</span><span class="sxs-lookup"><span data-stu-id="a003c-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="a003c-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="a003c-203">Microsoft Silverlight</span></span>
<span data-ttu-id="a003c-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="a003c-204">requesterEmail</span></span> | <span data-ttu-id="a003c-205">String</span><span class="sxs-lookup"><span data-stu-id="a003c-205">String</span></span> | <span data-ttu-id="a003c-206">作成者の電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="a003c-206">Creator email address</span></span> | <span data-ttu-id="a003c-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a003c-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="a003c-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="a003c-208">requesterId</span></span> | <span data-ttu-id="a003c-209">String</span><span class="sxs-lookup"><span data-stu-id="a003c-209">String</span></span> | <span data-ttu-id="a003c-210">Creator オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="a003c-210">Creator object id</span></span> | <span data-ttu-id="a003c-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="a003c-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="a003c-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="a003c-212">requesterNotes</span></span> | <span data-ttu-id="a003c-213">String</span><span class="sxs-lookup"><span data-stu-id="a003c-213">String</span></span> | <span data-ttu-id="a003c-214">この修復アクティビティに作成者が追加したメモ (フリー テキスト)</span><span class="sxs-lookup"><span data-stu-id="a003c-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="a003c-215">null</span><span class="sxs-lookup"><span data-stu-id="a003c-215">null</span></span>
<span data-ttu-id="a003c-216">scid</span><span class="sxs-lookup"><span data-stu-id="a003c-216">scid</span></span> | <span data-ttu-id="a003c-217">String</span><span class="sxs-lookup"><span data-stu-id="a003c-217">String</span></span> | <span data-ttu-id="a003c-218">関連するセキュリティ推奨事項の SCID</span><span class="sxs-lookup"><span data-stu-id="a003c-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="a003c-219">null</span><span class="sxs-lookup"><span data-stu-id="a003c-219">null</span></span>
<span data-ttu-id="a003c-220">status</span><span class="sxs-lookup"><span data-stu-id="a003c-220">status</span></span> | <span data-ttu-id="a003c-221">String</span><span class="sxs-lookup"><span data-stu-id="a003c-221">String</span></span> | <span data-ttu-id="a003c-222">修復アクティビティの状態 (アクティブ/完了)</span><span class="sxs-lookup"><span data-stu-id="a003c-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="a003c-223">Active</span><span class="sxs-lookup"><span data-stu-id="a003c-223">Active</span></span>
<span data-ttu-id="a003c-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="a003c-224">statusLastModifiedOn</span></span> | <span data-ttu-id="a003c-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="a003c-225">DateTime</span></span> | <span data-ttu-id="a003c-226">状態フィールドが更新された日付</span><span class="sxs-lookup"><span data-stu-id="a003c-226">Date when the status field was updated</span></span> | <span data-ttu-id="a003c-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="a003c-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="a003c-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="a003c-228">targetDevices</span></span> | <span data-ttu-id="a003c-229">Long</span><span class="sxs-lookup"><span data-stu-id="a003c-229">Long</span></span> | <span data-ttu-id="a003c-230">この修復が適用される公開デバイスの数</span><span class="sxs-lookup"><span data-stu-id="a003c-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="a003c-231">43</span><span class="sxs-lookup"><span data-stu-id="a003c-231">43</span></span>
<span data-ttu-id="a003c-232">title</span><span class="sxs-lookup"><span data-stu-id="a003c-232">title</span></span> | <span data-ttu-id="a003c-233">String</span><span class="sxs-lookup"><span data-stu-id="a003c-233">String</span></span> | <span data-ttu-id="a003c-234">この修復アクティビティのタイトル</span><span class="sxs-lookup"><span data-stu-id="a003c-234">Title of this remediation activity</span></span> | <span data-ttu-id="a003c-235">Microsoft Silverlight の更新</span><span class="sxs-lookup"><span data-stu-id="a003c-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="a003c-236">type</span><span class="sxs-lookup"><span data-stu-id="a003c-236">type</span></span> | <span data-ttu-id="a003c-237">String</span><span class="sxs-lookup"><span data-stu-id="a003c-237">String</span></span> | <span data-ttu-id="a003c-238">修復の種類</span><span class="sxs-lookup"><span data-stu-id="a003c-238">Remediation type</span></span> | <span data-ttu-id="a003c-239">Update</span><span class="sxs-lookup"><span data-stu-id="a003c-239">Update</span></span>
<span data-ttu-id="a003c-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="a003c-240">vendorId</span></span> | <span data-ttu-id="a003c-241">String</span><span class="sxs-lookup"><span data-stu-id="a003c-241">String</span></span> | <span data-ttu-id="a003c-242">関連ベンダー名</span><span class="sxs-lookup"><span data-stu-id="a003c-242">Related vendor name</span></span> | <span data-ttu-id="a003c-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="a003c-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="a003c-244">例</span><span class="sxs-lookup"><span data-stu-id="a003c-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="a003c-245">要求の例</span><span class="sxs-lookup"><span data-stu-id="a003c-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="a003c-246">応答の例</span><span class="sxs-lookup"><span data-stu-id="a003c-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a003c-247">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="a003c-247">See also</span></span>

- [<span data-ttu-id="a003c-248">修復方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="a003c-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="a003c-249">ID による 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="a003c-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="a003c-250">1 つの修復アクティビティの暴露デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="a003c-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="a003c-251">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="a003c-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="a003c-252">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="a003c-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
