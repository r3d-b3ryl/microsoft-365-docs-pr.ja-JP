---
title: Id で 1 つの修復アクティビティを取得する
description: 指定した修復アクティビティの情報を返します。
keywords: apis、修復、修復 API、get、修復タスク、ID による修復、
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
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244445"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="cdd76-104">Id で 1 つの修復アクティビティを取得する</span><span class="sxs-lookup"><span data-stu-id="cdd76-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cdd76-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cdd76-105">**Applies to:**</span></span>

- [<span data-ttu-id="cdd76-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cdd76-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cdd76-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdd76-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cdd76-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="cdd76-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cdd76-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="cdd76-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="cdd76-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="cdd76-110">API description</span></span>

<span data-ttu-id="cdd76-111">指定した修復アクティビティの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="cdd76-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="cdd76-112">[すべての修復アクティビティを取得 [する]](get-remediation-all-activities.md)と同じ列を表示しますが、指定した修復アクティビティ _の結果のみを返します_。</span><span class="sxs-lookup"><span data-stu-id="cdd76-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="cdd76-113">[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="cdd76-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="cdd76-114">(id) の指定された修復アクティビティを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="cdd76-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="cdd76-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="cdd76-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="cdd76-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="cdd76-116">Permissions</span></span>

<span data-ttu-id="cdd76-117">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="cdd76-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cdd76-118">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cdd76-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="cdd76-119">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="cdd76-119">Permission type</span></span> | <span data-ttu-id="cdd76-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="cdd76-120">Permission</span></span> | <span data-ttu-id="cdd76-121">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="cdd76-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cdd76-122">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="cdd76-122">Application</span></span> | <span data-ttu-id="cdd76-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="cdd76-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="cdd76-124">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="cdd76-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="cdd76-125">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="cdd76-125">Delegated (work or school account)</span></span> | <span data-ttu-id="cdd76-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="cdd76-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="cdd76-127">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="cdd76-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="cdd76-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cdd76-128">Properties</span></span>

<span data-ttu-id="cdd76-129">プロパティ (id)</span><span class="sxs-lookup"><span data-stu-id="cdd76-129">Property (id)</span></span> | <span data-ttu-id="cdd76-130">データ型</span><span class="sxs-lookup"><span data-stu-id="cdd76-130">Data type</span></span> | <span data-ttu-id="cdd76-131">説明</span><span class="sxs-lookup"><span data-stu-id="cdd76-131">Description</span></span> | <span data-ttu-id="cdd76-132">返される値の例</span><span class="sxs-lookup"><span data-stu-id="cdd76-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="cdd76-133">category</span><span class="sxs-lookup"><span data-stu-id="cdd76-133">category</span></span> | <span data-ttu-id="cdd76-134">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-134">String</span></span> | <span data-ttu-id="cdd76-135">修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)</span><span class="sxs-lookup"><span data-stu-id="cdd76-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="cdd76-136">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="cdd76-136">Software</span></span>
<span data-ttu-id="cdd76-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="cdd76-137">completerEmail</span></span> | <span data-ttu-id="cdd76-138">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-138">String</span></span> | <span data-ttu-id="cdd76-139">修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる</span><span class="sxs-lookup"><span data-stu-id="cdd76-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="cdd76-140">null</span><span class="sxs-lookup"><span data-stu-id="cdd76-140">null</span></span>
<span data-ttu-id="cdd76-141">completerId</span><span class="sxs-lookup"><span data-stu-id="cdd76-141">completerId</span></span> | <span data-ttu-id="cdd76-142">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-142">String</span></span> | <span data-ttu-id="cdd76-143">修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる</span><span class="sxs-lookup"><span data-stu-id="cdd76-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="cdd76-144">null</span><span class="sxs-lookup"><span data-stu-id="cdd76-144">null</span></span>
<span data-ttu-id="cdd76-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="cdd76-145">completionMethod</span></span> | <span data-ttu-id="cdd76-146">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-146">String</span></span> | <span data-ttu-id="cdd76-147">修復アクティビティは、"完了としてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。</span><span class="sxs-lookup"><span data-stu-id="cdd76-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="cdd76-148">自動</span><span class="sxs-lookup"><span data-stu-id="cdd76-148">Automatic</span></span>
<span data-ttu-id="cdd76-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="cdd76-149">createdOn</span></span> | <span data-ttu-id="cdd76-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="cdd76-150">DateTime</span></span> | <span data-ttu-id="cdd76-151">この修復アクティビティが作成された時刻</span><span class="sxs-lookup"><span data-stu-id="cdd76-151">Time this remediation activity was created</span></span> | <span data-ttu-id="cdd76-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="cdd76-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="cdd76-153">説明</span><span class="sxs-lookup"><span data-stu-id="cdd76-153">description</span></span> | <span data-ttu-id="cdd76-154">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-154">String</span></span> | <span data-ttu-id="cdd76-155">この修復アクティビティの説明</span><span class="sxs-lookup"><span data-stu-id="cdd76-155">Description of this remediation activity</span></span> | <span data-ttu-id="cdd76-156">デバイスに影響を与える既知の脆弱性を軽減するために、Microsoft Silverlight を新しいバージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="cdd76-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="cdd76-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="cdd76-157">dueOn</span></span> | <span data-ttu-id="cdd76-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="cdd76-158">DateTime</span></span> | <span data-ttu-id="cdd76-159">この修復アクティビティの作成者セットの期限</span><span class="sxs-lookup"><span data-stu-id="cdd76-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="cdd76-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="cdd76-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="cdd76-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="cdd76-161">fixedDevices</span></span> |  | <span data-ttu-id="cdd76-162">固定されているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="cdd76-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="cdd76-163">2</span><span class="sxs-lookup"><span data-stu-id="cdd76-163">2</span></span>
<span data-ttu-id="cdd76-164">id</span><span class="sxs-lookup"><span data-stu-id="cdd76-164">id</span></span> | <span data-ttu-id="cdd76-165">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-165">String</span></span> | <span data-ttu-id="cdd76-166">この修復アクティビティの ID</span><span class="sxs-lookup"><span data-stu-id="cdd76-166">ID of this remediation activity</span></span> | <span data-ttu-id="cdd76-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="cdd76-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="cdd76-168">nameId</span><span class="sxs-lookup"><span data-stu-id="cdd76-168">nameId</span></span> | <span data-ttu-id="cdd76-169">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-169">String</span></span> | <span data-ttu-id="cdd76-170">関連する製品名</span><span class="sxs-lookup"><span data-stu-id="cdd76-170">Related product name</span></span> | <span data-ttu-id="cdd76-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="cdd76-171">Microsoft Silverlight</span></span>
<span data-ttu-id="cdd76-172">priority</span><span class="sxs-lookup"><span data-stu-id="cdd76-172">priority</span></span> | <span data-ttu-id="cdd76-173">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-173">String</span></span> | <span data-ttu-id="cdd76-174">この修復アクティビティの作成者セットの優先度 (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="cdd76-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="cdd76-175">高い</span><span class="sxs-lookup"><span data-stu-id="cdd76-175">High</span></span>
<span data-ttu-id="cdd76-176">productId</span><span class="sxs-lookup"><span data-stu-id="cdd76-176">productId</span></span> | <span data-ttu-id="cdd76-177">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-177">String</span></span> | <span data-ttu-id="cdd76-178">関連する製品 ID</span><span class="sxs-lookup"><span data-stu-id="cdd76-178">Related product ID</span></span> | <span data-ttu-id="cdd76-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="cdd76-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="cdd76-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="cdd76-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="cdd76-181">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-181">String</span></span> | <span data-ttu-id="cdd76-182">いくつかの構成変更は、ユーザーに影響がないデバイスに対してだけ要求できます。</span><span class="sxs-lookup"><span data-stu-id="cdd76-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="cdd76-183">この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。</span><span class="sxs-lookup"><span data-stu-id="cdd76-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="cdd76-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="cdd76-184">AllExposedAssets</span></span>
<span data-ttu-id="cdd76-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="cdd76-185">rbacGroupNames</span></span> | <span data-ttu-id="cdd76-186">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-186">String</span></span> | <span data-ttu-id="cdd76-187">関連するデバイス グループ名</span><span class="sxs-lookup"><span data-stu-id="cdd76-187">Related device group names</span></span> | <span data-ttu-id="cdd76-188">[ "Windows サーバー", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="cdd76-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="cdd76-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="cdd76-189">recommendedProgram</span></span> | <span data-ttu-id="cdd76-190">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-190">String</span></span> | <span data-ttu-id="cdd76-191">にアップグレードする推奨プログラム</span><span class="sxs-lookup"><span data-stu-id="cdd76-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="cdd76-192">null</span><span class="sxs-lookup"><span data-stu-id="cdd76-192">null</span></span>
<span data-ttu-id="cdd76-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="cdd76-193">recommendedVendor</span></span> | <span data-ttu-id="cdd76-194">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-194">String</span></span> | <span data-ttu-id="cdd76-195">アップグレードの推奨ベンダー</span><span class="sxs-lookup"><span data-stu-id="cdd76-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="cdd76-196">null</span><span class="sxs-lookup"><span data-stu-id="cdd76-196">null</span></span>
<span data-ttu-id="cdd76-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="cdd76-197">recommendedVersion</span></span> | <span data-ttu-id="cdd76-198">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-198">String</span></span> | <span data-ttu-id="cdd76-199">更新/アップグレードの推奨バージョン</span><span class="sxs-lookup"><span data-stu-id="cdd76-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="cdd76-200">null</span><span class="sxs-lookup"><span data-stu-id="cdd76-200">null</span></span>
<span data-ttu-id="cdd76-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="cdd76-201">relatedComponent</span></span> | <span data-ttu-id="cdd76-202">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-202">String</span></span> | <span data-ttu-id="cdd76-203">この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)</span><span class="sxs-lookup"><span data-stu-id="cdd76-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="cdd76-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="cdd76-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="cdd76-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="cdd76-205">requesterEmail</span></span> | <span data-ttu-id="cdd76-206">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-206">String</span></span> | <span data-ttu-id="cdd76-207">作成者の電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="cdd76-207">Creator email address</span></span> | <span data-ttu-id="cdd76-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cdd76-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="cdd76-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="cdd76-209">requesterId</span></span> | <span data-ttu-id="cdd76-210">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-210">String</span></span> | <span data-ttu-id="cdd76-211">Creator オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="cdd76-211">Creator object id</span></span> | <span data-ttu-id="cdd76-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="cdd76-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="cdd76-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="cdd76-213">requesterNotes</span></span> | <span data-ttu-id="cdd76-214">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-214">String</span></span> | <span data-ttu-id="cdd76-215">この修復アクティビティに作成者が追加したメモ (フリー テキスト)</span><span class="sxs-lookup"><span data-stu-id="cdd76-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="cdd76-216">null</span><span class="sxs-lookup"><span data-stu-id="cdd76-216">null</span></span>
<span data-ttu-id="cdd76-217">scid</span><span class="sxs-lookup"><span data-stu-id="cdd76-217">scid</span></span> | <span data-ttu-id="cdd76-218">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-218">String</span></span> | <span data-ttu-id="cdd76-219">関連するセキュリティ推奨事項の SCID</span><span class="sxs-lookup"><span data-stu-id="cdd76-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="cdd76-220">null</span><span class="sxs-lookup"><span data-stu-id="cdd76-220">null</span></span>
<span data-ttu-id="cdd76-221">status</span><span class="sxs-lookup"><span data-stu-id="cdd76-221">status</span></span> | <span data-ttu-id="cdd76-222">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-222">String</span></span> | <span data-ttu-id="cdd76-223">修復アクティビティの状態 (アクティブ/完了)</span><span class="sxs-lookup"><span data-stu-id="cdd76-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="cdd76-224">有効</span><span class="sxs-lookup"><span data-stu-id="cdd76-224">Active</span></span>
<span data-ttu-id="cdd76-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="cdd76-225">statusLastModifiedOn</span></span> | <span data-ttu-id="cdd76-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="cdd76-226">DateTime</span></span> | <span data-ttu-id="cdd76-227">状態フィールドが更新された日付</span><span class="sxs-lookup"><span data-stu-id="cdd76-227">Date when the status field was updated</span></span> | <span data-ttu-id="cdd76-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="cdd76-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="cdd76-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="cdd76-229">targetDevices</span></span> | <span data-ttu-id="cdd76-230">Long</span><span class="sxs-lookup"><span data-stu-id="cdd76-230">Long</span></span> | <span data-ttu-id="cdd76-231">この修復が適用される公開デバイスの数</span><span class="sxs-lookup"><span data-stu-id="cdd76-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="cdd76-232">43</span><span class="sxs-lookup"><span data-stu-id="cdd76-232">43</span></span>
<span data-ttu-id="cdd76-233">title</span><span class="sxs-lookup"><span data-stu-id="cdd76-233">title</span></span> | <span data-ttu-id="cdd76-234">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-234">String</span></span> | <span data-ttu-id="cdd76-235">この修復アクティビティのタイトル</span><span class="sxs-lookup"><span data-stu-id="cdd76-235">Title of this remediation activity</span></span> | <span data-ttu-id="cdd76-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="cdd76-236">Microsoft Silverlight</span></span>
<span data-ttu-id="cdd76-237">type</span><span class="sxs-lookup"><span data-stu-id="cdd76-237">type</span></span> | <span data-ttu-id="cdd76-238">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-238">String</span></span> | <span data-ttu-id="cdd76-239">修復の種類</span><span class="sxs-lookup"><span data-stu-id="cdd76-239">Remediation type</span></span> | <span data-ttu-id="cdd76-240">Update</span><span class="sxs-lookup"><span data-stu-id="cdd76-240">Update</span></span>
<span data-ttu-id="cdd76-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="cdd76-241">vendorId</span></span> | <span data-ttu-id="cdd76-242">String</span><span class="sxs-lookup"><span data-stu-id="cdd76-242">String</span></span> | <span data-ttu-id="cdd76-243">関連ベンダー名</span><span class="sxs-lookup"><span data-stu-id="cdd76-243">Related vendor name</span></span> | <span data-ttu-id="cdd76-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="cdd76-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="cdd76-245">例</span><span class="sxs-lookup"><span data-stu-id="cdd76-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="cdd76-246">要求の例</span><span class="sxs-lookup"><span data-stu-id="cdd76-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="cdd76-247">応答の例</span><span class="sxs-lookup"><span data-stu-id="cdd76-247">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cdd76-248">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdd76-248">See also</span></span>

- [<span data-ttu-id="cdd76-249">修復方法とプロパティ</span><span class="sxs-lookup"><span data-stu-id="cdd76-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="cdd76-250">すべての修復作業を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="cdd76-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="cdd76-251">1 つの修復アクティビティの暴露デバイスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="cdd76-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="cdd76-252">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="cdd76-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="cdd76-253">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="cdd76-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
