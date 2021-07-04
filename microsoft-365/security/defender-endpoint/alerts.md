---
title: アラート API の取得
description: Microsoft Defender for Endpoint の Alert リソースタイプのメソッドとプロパティについて説明します。
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289681"
---
# <a name="alert-resource-type"></a><span data-ttu-id="65227-104">アラート リソースの種類</span><span class="sxs-lookup"><span data-stu-id="65227-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65227-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="65227-105">**Applies to:**</span></span>
- [<span data-ttu-id="65227-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="65227-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="65227-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="65227-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="65227-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="65227-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="65227-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="65227-109">Methods</span></span>

<span data-ttu-id="65227-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="65227-110">Method</span></span> |<span data-ttu-id="65227-111">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="65227-111">Return Type</span></span> |<span data-ttu-id="65227-112">説明</span><span class="sxs-lookup"><span data-stu-id="65227-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="65227-113">警告の取得</span><span class="sxs-lookup"><span data-stu-id="65227-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="65227-114">アラート</span><span class="sxs-lookup"><span data-stu-id="65227-114">Alert</span></span>](alerts.md) | <span data-ttu-id="65227-115">1 つのアラート [オブジェクトを取得](alerts.md) します。</span><span class="sxs-lookup"><span data-stu-id="65227-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="65227-116">警告の一覧表示</span><span class="sxs-lookup"><span data-stu-id="65227-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="65227-117">[アラート](alerts.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="65227-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="65227-118">アラート [コレクションを一覧表示](alerts.md) します。</span><span class="sxs-lookup"><span data-stu-id="65227-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="65227-119">警告の更新</span><span class="sxs-lookup"><span data-stu-id="65227-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="65227-120">アラート</span><span class="sxs-lookup"><span data-stu-id="65227-120">Alert</span></span>](alerts.md) | <span data-ttu-id="65227-121">特定のアラートを [更新します](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="65227-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="65227-122">バッチ更新の通知</span><span class="sxs-lookup"><span data-stu-id="65227-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="65227-123">アラートのバッチを更新 [します](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="65227-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="65227-124">アラートの作成</span><span class="sxs-lookup"><span data-stu-id="65227-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="65227-125">アラート</span><span class="sxs-lookup"><span data-stu-id="65227-125">Alert</span></span>](alerts.md)|<span data-ttu-id="65227-126">Advanced Hunting から取得したイベント データに基づいてアラート [を作成します](run-advanced-query-api.md)。</span><span class="sxs-lookup"><span data-stu-id="65227-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="65227-127">関連するドメインを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="65227-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="65227-128">ドメイン コレクション</span><span class="sxs-lookup"><span data-stu-id="65227-128">Domain collection</span></span>| <span data-ttu-id="65227-129">アラートに関連付けられている URL を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="65227-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="65227-130">関連ファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="65227-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="65227-131">[ファイル](files.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="65227-131">[File](files.md) collection</span></span> |  <span data-ttu-id="65227-132">アラートに [関連](files.md) 付けられているファイル エンティティを一覧表示 [します](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="65227-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="65227-133">関連する IPs の一覧</span><span class="sxs-lookup"><span data-stu-id="65227-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="65227-134">IP コレクション</span><span class="sxs-lookup"><span data-stu-id="65227-134">IP collection</span></span> | <span data-ttu-id="65227-135">アラートに関連付けられているリストの AP。</span><span class="sxs-lookup"><span data-stu-id="65227-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="65227-136">関連するコンピューターを取得する</span><span class="sxs-lookup"><span data-stu-id="65227-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="65227-137">マシン</span><span class="sxs-lookup"><span data-stu-id="65227-137">Machine</span></span>](machine.md) | <span data-ttu-id="65227-138">アラート [に](machine.md) 関連付けられている [コンピューター](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="65227-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="65227-139">関連ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="65227-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="65227-140">ユーザー</span><span class="sxs-lookup"><span data-stu-id="65227-140">User</span></span>](user.md) | <span data-ttu-id="65227-141">アラート [に](user.md) 関連付けられている [ユーザー](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="65227-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>

## <a name="properties"></a><span data-ttu-id="65227-142">プロパティ</span><span class="sxs-lookup"><span data-stu-id="65227-142">Properties</span></span>

<span data-ttu-id="65227-143">プロパティ</span><span class="sxs-lookup"><span data-stu-id="65227-143">Property</span></span> |    <span data-ttu-id="65227-144">種類</span><span class="sxs-lookup"><span data-stu-id="65227-144">Type</span></span>    |    <span data-ttu-id="65227-145">説明</span><span class="sxs-lookup"><span data-stu-id="65227-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="65227-146">id</span><span class="sxs-lookup"><span data-stu-id="65227-146">id</span></span> | <span data-ttu-id="65227-147">String</span><span class="sxs-lookup"><span data-stu-id="65227-147">String</span></span> | <span data-ttu-id="65227-148">アラート ID。</span><span class="sxs-lookup"><span data-stu-id="65227-148">Alert ID.</span></span>
<span data-ttu-id="65227-149">title</span><span class="sxs-lookup"><span data-stu-id="65227-149">title</span></span> | <span data-ttu-id="65227-150">String</span><span class="sxs-lookup"><span data-stu-id="65227-150">String</span></span> | <span data-ttu-id="65227-151">警告タイトル。</span><span class="sxs-lookup"><span data-stu-id="65227-151">Alert title.</span></span>
<span data-ttu-id="65227-152">説明</span><span class="sxs-lookup"><span data-stu-id="65227-152">description</span></span> | <span data-ttu-id="65227-153">String</span><span class="sxs-lookup"><span data-stu-id="65227-153">String</span></span> | <span data-ttu-id="65227-154">警告の説明。</span><span class="sxs-lookup"><span data-stu-id="65227-154">Alert description.</span></span>
<span data-ttu-id="65227-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="65227-155">alertCreationTime</span></span> | <span data-ttu-id="65227-156">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="65227-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="65227-157">アラートが作成された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="65227-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="65227-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="65227-158">lastEventTime</span></span> | <span data-ttu-id="65227-159">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="65227-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="65227-160">同じデバイスでアラートをトリガーしたイベントの最後の発生。</span><span class="sxs-lookup"><span data-stu-id="65227-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="65227-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="65227-161">firstEventTime</span></span> | <span data-ttu-id="65227-162">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="65227-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="65227-163">そのデバイスでアラートをトリガーしたイベントの最初の発生。</span><span class="sxs-lookup"><span data-stu-id="65227-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="65227-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="65227-164">lastUpdateTime</span></span> | <span data-ttu-id="65227-165">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="65227-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="65227-166">アラートが最後に更新された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="65227-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="65227-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="65227-167">resolvedTime</span></span> | <span data-ttu-id="65227-168">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="65227-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="65227-169">アラートの状態が [解決済み] に変更された日時。</span><span class="sxs-lookup"><span data-stu-id="65227-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="65227-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="65227-170">incidentId</span></span> | <span data-ttu-id="65227-171">Null 許容長</span><span class="sxs-lookup"><span data-stu-id="65227-171">Nullable Long</span></span> | <span data-ttu-id="65227-172">アラート [の](view-incidents-queue.md) インシデント ID。</span><span class="sxs-lookup"><span data-stu-id="65227-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="65227-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="65227-173">investigationId</span></span> | <span data-ttu-id="65227-174">Null 許容長</span><span class="sxs-lookup"><span data-stu-id="65227-174">Nullable Long</span></span> | <span data-ttu-id="65227-175">アラート [に](automated-investigations.md) 関連する調査 ID。</span><span class="sxs-lookup"><span data-stu-id="65227-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="65227-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="65227-176">investigationState</span></span> | <span data-ttu-id="65227-177">Null 許容列挙</span><span class="sxs-lookup"><span data-stu-id="65227-177">Nullable Enum</span></span> | <span data-ttu-id="65227-178">調査の現在の [状態](automated-investigations.md)です。</span><span class="sxs-lookup"><span data-stu-id="65227-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="65227-179">指定できる値は、'Unknown'、'Terminated'、 'SuccessfullyRemediated', '良性', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'unsupportedAlertType', 'unsupportedAlertType''</span><span class="sxs-lookup"><span data-stu-id="65227-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="65227-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="65227-180">assignedTo</span></span> | <span data-ttu-id="65227-181">String</span><span class="sxs-lookup"><span data-stu-id="65227-181">String</span></span> | <span data-ttu-id="65227-182">アラートの所有者。</span><span class="sxs-lookup"><span data-stu-id="65227-182">Owner of the alert.</span></span>
<span data-ttu-id="65227-183">severity</span><span class="sxs-lookup"><span data-stu-id="65227-183">severity</span></span> | <span data-ttu-id="65227-184">列挙</span><span class="sxs-lookup"><span data-stu-id="65227-184">Enum</span></span> | <span data-ttu-id="65227-185">アラートの重大度。</span><span class="sxs-lookup"><span data-stu-id="65227-185">Severity of the alert.</span></span> <span data-ttu-id="65227-186">指定できる値は、'UnSpecified'、'Informational'、'Low'、'Medium' および 'High' です。</span><span class="sxs-lookup"><span data-stu-id="65227-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="65227-187">status</span><span class="sxs-lookup"><span data-stu-id="65227-187">status</span></span> | <span data-ttu-id="65227-188">列挙</span><span class="sxs-lookup"><span data-stu-id="65227-188">Enum</span></span> | <span data-ttu-id="65227-189">アラートの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="65227-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="65227-190">指定できる値は、'Unknown'、'New'、'InProgress'、'Resolved' です。</span><span class="sxs-lookup"><span data-stu-id="65227-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="65227-191">classification</span><span class="sxs-lookup"><span data-stu-id="65227-191">classification</span></span> | <span data-ttu-id="65227-192">Null 許容列挙</span><span class="sxs-lookup"><span data-stu-id="65227-192">Nullable Enum</span></span> | <span data-ttu-id="65227-193">アラートの仕様。</span><span class="sxs-lookup"><span data-stu-id="65227-193">Specification of the alert.</span></span> <span data-ttu-id="65227-194">指定できる値は、'Unknown'、'FalsePositive'、'TruePositive'です。</span><span class="sxs-lookup"><span data-stu-id="65227-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="65227-195">決定</span><span class="sxs-lookup"><span data-stu-id="65227-195">determination</span></span> | <span data-ttu-id="65227-196">Null 許容列挙</span><span class="sxs-lookup"><span data-stu-id="65227-196">Nullable Enum</span></span> | <span data-ttu-id="65227-197">アラートの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="65227-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="65227-198">指定できる値は、'NotAvailable'、'Apt'、'Malware'、'SecurityPersonnel'、'SecurityTesting'、'UnwantedSoftware'、'Other' です。</span><span class="sxs-lookup"><span data-stu-id="65227-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="65227-199">category</span><span class="sxs-lookup"><span data-stu-id="65227-199">category</span></span>| <span data-ttu-id="65227-200">String</span><span class="sxs-lookup"><span data-stu-id="65227-200">String</span></span> | <span data-ttu-id="65227-201">アラートのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="65227-201">Category of the alert.</span></span>
<span data-ttu-id="65227-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="65227-202">detectionSource</span></span> | <span data-ttu-id="65227-203">String</span><span class="sxs-lookup"><span data-stu-id="65227-203">String</span></span> | <span data-ttu-id="65227-204">検出ソース。</span><span class="sxs-lookup"><span data-stu-id="65227-204">Detection source.</span></span>
<span data-ttu-id="65227-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="65227-205">threatFamilyName</span></span> | <span data-ttu-id="65227-206">String</span><span class="sxs-lookup"><span data-stu-id="65227-206">String</span></span> | <span data-ttu-id="65227-207">脅威ファミリ。</span><span class="sxs-lookup"><span data-stu-id="65227-207">Threat family.</span></span>
<span data-ttu-id="65227-208">threatName</span><span class="sxs-lookup"><span data-stu-id="65227-208">threatName</span></span> | <span data-ttu-id="65227-209">String</span><span class="sxs-lookup"><span data-stu-id="65227-209">String</span></span> | <span data-ttu-id="65227-210">脅威の名前。</span><span class="sxs-lookup"><span data-stu-id="65227-210">Threat name.</span></span>
<span data-ttu-id="65227-211">machineId</span><span class="sxs-lookup"><span data-stu-id="65227-211">machineId</span></span> | <span data-ttu-id="65227-212">String</span><span class="sxs-lookup"><span data-stu-id="65227-212">String</span></span> | <span data-ttu-id="65227-213">アラートに [関連付](machine.md) けられているコンピューター エンティティの ID。</span><span class="sxs-lookup"><span data-stu-id="65227-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="65227-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="65227-214">computerDnsName</span></span> | <span data-ttu-id="65227-215">String</span><span class="sxs-lookup"><span data-stu-id="65227-215">String</span></span> | <span data-ttu-id="65227-216">[コンピューター](machine.md) の完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="65227-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="65227-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="65227-217">aadTenantId</span></span> | <span data-ttu-id="65227-218">String</span><span class="sxs-lookup"><span data-stu-id="65227-218">String</span></span> | <span data-ttu-id="65227-219">ユーザー ID Azure Active Directory ID。</span><span class="sxs-lookup"><span data-stu-id="65227-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="65227-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="65227-220">detectorId</span></span> | <span data-ttu-id="65227-221">String</span><span class="sxs-lookup"><span data-stu-id="65227-221">String</span></span> | <span data-ttu-id="65227-222">アラートをトリガーした検出器の ID。</span><span class="sxs-lookup"><span data-stu-id="65227-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="65227-223">comments</span><span class="sxs-lookup"><span data-stu-id="65227-223">comments</span></span> | <span data-ttu-id="65227-224">アラートコメントの一覧</span><span class="sxs-lookup"><span data-stu-id="65227-224">List of Alert comments</span></span> | <span data-ttu-id="65227-225">Alert Comment オブジェクトには、コメント文字列、createBy 文字列、createTime 日付時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="65227-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="65227-226">証拠</span><span class="sxs-lookup"><span data-stu-id="65227-226">Evidence</span></span> | <span data-ttu-id="65227-227">アラート証拠の一覧</span><span class="sxs-lookup"><span data-stu-id="65227-227">List of Alert evidence</span></span> | <span data-ttu-id="65227-228">アラートに関連する証拠。</span><span class="sxs-lookup"><span data-stu-id="65227-228">Evidence related to the alert.</span></span> <span data-ttu-id="65227-229">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65227-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="65227-230">1 つのアラートを取得する場合の応答例:</span><span class="sxs-lookup"><span data-stu-id="65227-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
