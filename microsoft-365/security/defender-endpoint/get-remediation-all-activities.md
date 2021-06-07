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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b95fa2da177a3ecb93bcf3e2085be6111c2c641e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770519"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="4a49a-104">すべての修復作業を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4a49a-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a49a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4a49a-105">**Applies to:**</span></span>

- [<span data-ttu-id="4a49a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4a49a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4a49a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a49a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4a49a-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="4a49a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4a49a-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="4a49a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="4a49a-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="4a49a-110">API description</span></span>

<span data-ttu-id="4a49a-111">すべての修復アクティビティに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4a49a-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="4a49a-112">[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="4a49a-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="4a49a-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="4a49a-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="4a49a-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="4a49a-114">Permissions</span></span>

<span data-ttu-id="4a49a-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a49a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4a49a-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4a49a-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="4a49a-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="4a49a-117">Permission type</span></span> | <span data-ttu-id="4a49a-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="4a49a-118">Permission</span></span> | <span data-ttu-id="4a49a-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="4a49a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4a49a-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="4a49a-120">Application</span></span> | <span data-ttu-id="4a49a-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="4a49a-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="4a49a-122">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="4a49a-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="4a49a-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="4a49a-123">Delegated (work or school account)</span></span> | <span data-ttu-id="4a49a-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="4a49a-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="4a49a-125">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="4a49a-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="4a49a-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4a49a-126">Properties</span></span>

<span data-ttu-id="4a49a-127">プロパティ (id)</span><span class="sxs-lookup"><span data-stu-id="4a49a-127">Property (id)</span></span> | <span data-ttu-id="4a49a-128">データ型</span><span class="sxs-lookup"><span data-stu-id="4a49a-128">Data type</span></span> | <span data-ttu-id="4a49a-129">説明</span><span class="sxs-lookup"><span data-stu-id="4a49a-129">Description</span></span> | <span data-ttu-id="4a49a-130">返される値の例</span><span class="sxs-lookup"><span data-stu-id="4a49a-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="4a49a-131">category</span><span class="sxs-lookup"><span data-stu-id="4a49a-131">category</span></span> | <span data-ttu-id="4a49a-132">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-132">String</span></span> | <span data-ttu-id="4a49a-133">修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)</span><span class="sxs-lookup"><span data-stu-id="4a49a-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="4a49a-134">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="4a49a-134">Software</span></span>
<span data-ttu-id="4a49a-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="4a49a-135">completerEmail</span></span> | <span data-ttu-id="4a49a-136">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-136">String</span></span> | <span data-ttu-id="4a49a-137">修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる</span><span class="sxs-lookup"><span data-stu-id="4a49a-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="4a49a-138">null</span><span class="sxs-lookup"><span data-stu-id="4a49a-138">null</span></span>
<span data-ttu-id="4a49a-139">completerId</span><span class="sxs-lookup"><span data-stu-id="4a49a-139">completerId</span></span> | <span data-ttu-id="4a49a-140">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-140">String</span></span> | <span data-ttu-id="4a49a-141">修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる</span><span class="sxs-lookup"><span data-stu-id="4a49a-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="4a49a-142">null</span><span class="sxs-lookup"><span data-stu-id="4a49a-142">null</span></span>
<span data-ttu-id="4a49a-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="4a49a-143">completionMethod</span></span> | <span data-ttu-id="4a49a-144">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-144">String</span></span> | <span data-ttu-id="4a49a-145">修復アクティビティは、"完了としてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。</span><span class="sxs-lookup"><span data-stu-id="4a49a-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="4a49a-146">自動</span><span class="sxs-lookup"><span data-stu-id="4a49a-146">Automatic</span></span>
<span data-ttu-id="4a49a-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="4a49a-147">createdOn</span></span> | <span data-ttu-id="4a49a-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="4a49a-148">DateTime</span></span> | <span data-ttu-id="4a49a-149">この修復アクティビティが作成された時刻</span><span class="sxs-lookup"><span data-stu-id="4a49a-149">Time this remediation activity was created</span></span> | <span data-ttu-id="4a49a-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="4a49a-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="4a49a-151">説明</span><span class="sxs-lookup"><span data-stu-id="4a49a-151">description</span></span> | <span data-ttu-id="4a49a-152">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-152">String</span></span> | <span data-ttu-id="4a49a-153">この修復アクティビティの説明</span><span class="sxs-lookup"><span data-stu-id="4a49a-153">Description of this remediation activity</span></span> | <span data-ttu-id="4a49a-154">デバイスに影響を与える既知の脆弱性を軽減するために、Microsoft Silverlight を新しいバージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="4a49a-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="4a49a-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="4a49a-155">dueOn</span></span> | <span data-ttu-id="4a49a-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="4a49a-156">DateTime</span></span> | <span data-ttu-id="4a49a-157">この修復アクティビティの作成者セットの期限</span><span class="sxs-lookup"><span data-stu-id="4a49a-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="4a49a-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="4a49a-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="4a49a-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="4a49a-159">fixedDevices</span></span> | <span data-ttu-id="4a49a-160">.</span><span class="sxs-lookup"><span data-stu-id="4a49a-160">.</span></span> | <span data-ttu-id="4a49a-161">固定されているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="4a49a-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="4a49a-162">2</span><span class="sxs-lookup"><span data-stu-id="4a49a-162">2</span></span>
<span data-ttu-id="4a49a-163">id</span><span class="sxs-lookup"><span data-stu-id="4a49a-163">id</span></span> | <span data-ttu-id="4a49a-164">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-164">String</span></span> | <span data-ttu-id="4a49a-165">この修復アクティビティの ID</span><span class="sxs-lookup"><span data-stu-id="4a49a-165">ID of this remediation activity</span></span> | <span data-ttu-id="4a49a-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="4a49a-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="4a49a-167">nameId</span><span class="sxs-lookup"><span data-stu-id="4a49a-167">nameId</span></span> | <span data-ttu-id="4a49a-168">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-168">String</span></span> | <span data-ttu-id="4a49a-169">関連する製品名</span><span class="sxs-lookup"><span data-stu-id="4a49a-169">Related product name</span></span> | <span data-ttu-id="4a49a-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="4a49a-170">Microsoft Silverlight</span></span>
<span data-ttu-id="4a49a-171">priority</span><span class="sxs-lookup"><span data-stu-id="4a49a-171">priority</span></span> | <span data-ttu-id="4a49a-172">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-172">String</span></span> | <span data-ttu-id="4a49a-173">この修復アクティビティの作成者セットの優先度 (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="4a49a-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="4a49a-174">高い</span><span class="sxs-lookup"><span data-stu-id="4a49a-174">High</span></span>
<span data-ttu-id="4a49a-175">productId</span><span class="sxs-lookup"><span data-stu-id="4a49a-175">productId</span></span> | <span data-ttu-id="4a49a-176">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-176">String</span></span> | <span data-ttu-id="4a49a-177">関連する製品 ID</span><span class="sxs-lookup"><span data-stu-id="4a49a-177">Related product ID</span></span> | <span data-ttu-id="4a49a-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="4a49a-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="4a49a-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="4a49a-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="4a49a-180">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-180">String</span></span> | <span data-ttu-id="4a49a-181">いくつかの構成変更は、ユーザーに影響がないデバイスに対してだけ要求できます。</span><span class="sxs-lookup"><span data-stu-id="4a49a-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="4a49a-182">この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。</span><span class="sxs-lookup"><span data-stu-id="4a49a-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="4a49a-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="4a49a-183">AllExposedAssets</span></span>
<span data-ttu-id="4a49a-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="4a49a-184">rbacGroupNames</span></span> | <span data-ttu-id="4a49a-185">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-185">String</span></span> | <span data-ttu-id="4a49a-186">関連するデバイス グループ名</span><span class="sxs-lookup"><span data-stu-id="4a49a-186">Related device group names</span></span> | <span data-ttu-id="4a49a-187">[ "Windows サーバー", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="4a49a-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="4a49a-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="4a49a-188">recommendedProgram</span></span> | <span data-ttu-id="4a49a-189">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-189">String</span></span> | <span data-ttu-id="4a49a-190">にアップグレードする推奨プログラム</span><span class="sxs-lookup"><span data-stu-id="4a49a-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="4a49a-191">null</span><span class="sxs-lookup"><span data-stu-id="4a49a-191">null</span></span>
<span data-ttu-id="4a49a-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="4a49a-192">recommendedVendor</span></span> | <span data-ttu-id="4a49a-193">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-193">String</span></span> | <span data-ttu-id="4a49a-194">アップグレードの推奨ベンダー</span><span class="sxs-lookup"><span data-stu-id="4a49a-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="4a49a-195">null</span><span class="sxs-lookup"><span data-stu-id="4a49a-195">null</span></span>
<span data-ttu-id="4a49a-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="4a49a-196">recommendedVersion</span></span> | <span data-ttu-id="4a49a-197">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-197">String</span></span> | <span data-ttu-id="4a49a-198">更新/アップグレードの推奨バージョン</span><span class="sxs-lookup"><span data-stu-id="4a49a-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="4a49a-199">null</span><span class="sxs-lookup"><span data-stu-id="4a49a-199">null</span></span>
<span data-ttu-id="4a49a-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="4a49a-200">relatedComponent</span></span> | <span data-ttu-id="4a49a-201">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-201">String</span></span> | <span data-ttu-id="4a49a-202">この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)</span><span class="sxs-lookup"><span data-stu-id="4a49a-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="4a49a-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="4a49a-203">Microsoft Silverlight</span></span>
<span data-ttu-id="4a49a-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="4a49a-204">requesterEmail</span></span> | <span data-ttu-id="4a49a-205">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-205">String</span></span> | <span data-ttu-id="4a49a-206">作成者の電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="4a49a-206">Creator email address</span></span> | <span data-ttu-id="4a49a-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4a49a-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="4a49a-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="4a49a-208">requesterId</span></span> | <span data-ttu-id="4a49a-209">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-209">String</span></span> | <span data-ttu-id="4a49a-210">Creator オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="4a49a-210">Creator object id</span></span> | <span data-ttu-id="4a49a-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="4a49a-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="4a49a-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="4a49a-212">requesterNotes</span></span> | <span data-ttu-id="4a49a-213">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-213">String</span></span> | <span data-ttu-id="4a49a-214">この修復アクティビティに作成者が追加したメモ (フリー テキスト)</span><span class="sxs-lookup"><span data-stu-id="4a49a-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="4a49a-215">null</span><span class="sxs-lookup"><span data-stu-id="4a49a-215">null</span></span>
<span data-ttu-id="4a49a-216">scid</span><span class="sxs-lookup"><span data-stu-id="4a49a-216">scid</span></span> | <span data-ttu-id="4a49a-217">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-217">String</span></span> | <span data-ttu-id="4a49a-218">関連するセキュリティ推奨事項の SCID</span><span class="sxs-lookup"><span data-stu-id="4a49a-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="4a49a-219">null</span><span class="sxs-lookup"><span data-stu-id="4a49a-219">null</span></span>
<span data-ttu-id="4a49a-220">status</span><span class="sxs-lookup"><span data-stu-id="4a49a-220">status</span></span> | <span data-ttu-id="4a49a-221">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-221">String</span></span> | <span data-ttu-id="4a49a-222">修復アクティビティの状態 (アクティブ/完了)</span><span class="sxs-lookup"><span data-stu-id="4a49a-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="4a49a-223">有効</span><span class="sxs-lookup"><span data-stu-id="4a49a-223">Active</span></span>
<span data-ttu-id="4a49a-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="4a49a-224">statusLastModifiedOn</span></span> | <span data-ttu-id="4a49a-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="4a49a-225">DateTime</span></span> | <span data-ttu-id="4a49a-226">状態フィールドが更新された日付</span><span class="sxs-lookup"><span data-stu-id="4a49a-226">Date when the status field was updated</span></span> | <span data-ttu-id="4a49a-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="4a49a-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="4a49a-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="4a49a-228">targetDevices</span></span> | <span data-ttu-id="4a49a-229">Long</span><span class="sxs-lookup"><span data-stu-id="4a49a-229">Long</span></span> | <span data-ttu-id="4a49a-230">この修復が適用される公開デバイスの数</span><span class="sxs-lookup"><span data-stu-id="4a49a-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="4a49a-231">43</span><span class="sxs-lookup"><span data-stu-id="4a49a-231">43</span></span>
<span data-ttu-id="4a49a-232">title</span><span class="sxs-lookup"><span data-stu-id="4a49a-232">title</span></span> | <span data-ttu-id="4a49a-233">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-233">String</span></span> | <span data-ttu-id="4a49a-234">この修復アクティビティのタイトル</span><span class="sxs-lookup"><span data-stu-id="4a49a-234">Title of this remediation activity</span></span> | <span data-ttu-id="4a49a-235">Microsoft Silverlight の更新</span><span class="sxs-lookup"><span data-stu-id="4a49a-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="4a49a-236">type</span><span class="sxs-lookup"><span data-stu-id="4a49a-236">type</span></span> | <span data-ttu-id="4a49a-237">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-237">String</span></span> | <span data-ttu-id="4a49a-238">修復の種類</span><span class="sxs-lookup"><span data-stu-id="4a49a-238">Remediation type</span></span> | <span data-ttu-id="4a49a-239">Update</span><span class="sxs-lookup"><span data-stu-id="4a49a-239">Update</span></span>
<span data-ttu-id="4a49a-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="4a49a-240">vendorId</span></span> | <span data-ttu-id="4a49a-241">String</span><span class="sxs-lookup"><span data-stu-id="4a49a-241">String</span></span> | <span data-ttu-id="4a49a-242">関連ベンダー名</span><span class="sxs-lookup"><span data-stu-id="4a49a-242">Related vendor name</span></span> | <span data-ttu-id="4a49a-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="4a49a-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="4a49a-244">例</span><span class="sxs-lookup"><span data-stu-id="4a49a-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="4a49a-245">要求の例</span><span class="sxs-lookup"><span data-stu-id="4a49a-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="4a49a-246">応答の例</span><span class="sxs-lookup"><span data-stu-id="4a49a-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4a49a-247">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a49a-247">See also</span></span>

- [<span data-ttu-id="4a49a-248">修復方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="4a49a-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="4a49a-249">ID による 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="4a49a-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="4a49a-250">1 つの修復アクティビティの暴露デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4a49a-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="4a49a-251">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="4a49a-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="4a49a-252">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="4a49a-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
