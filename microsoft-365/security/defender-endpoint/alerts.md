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
ms.technology: mde
ms.openlocfilehash: 4997d7118b139d993ed94ed917137ca107940e46
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199623"
---
# <a name="alert-resource-type"></a><span data-ttu-id="b13c9-104">アラート リソースの種類</span><span class="sxs-lookup"><span data-stu-id="b13c9-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b13c9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b13c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="b13c9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b13c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="b13c9-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b13c9-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b13c9-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b13c9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="b13c9-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="b13c9-109">Methods</span></span>

<span data-ttu-id="b13c9-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="b13c9-110">Method</span></span> |<span data-ttu-id="b13c9-111">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="b13c9-111">Return Type</span></span> |<span data-ttu-id="b13c9-112">説明</span><span class="sxs-lookup"><span data-stu-id="b13c9-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="b13c9-113">警告の取得</span><span class="sxs-lookup"><span data-stu-id="b13c9-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="b13c9-114">アラート</span><span class="sxs-lookup"><span data-stu-id="b13c9-114">Alert</span></span>](alerts.md) | <span data-ttu-id="b13c9-115">1 つのアラート [オブジェクトを取得](alerts.md) します。</span><span class="sxs-lookup"><span data-stu-id="b13c9-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="b13c9-116">警告の一覧表示</span><span class="sxs-lookup"><span data-stu-id="b13c9-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="b13c9-117">[アラート](alerts.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="b13c9-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="b13c9-118">アラート [コレクションを一覧表示](alerts.md) します。</span><span class="sxs-lookup"><span data-stu-id="b13c9-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="b13c9-119">警告の更新</span><span class="sxs-lookup"><span data-stu-id="b13c9-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="b13c9-120">アラート</span><span class="sxs-lookup"><span data-stu-id="b13c9-120">Alert</span></span>](alerts.md) | <span data-ttu-id="b13c9-121">特定のアラートを [更新します](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b13c9-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="b13c9-122">バッチ更新の通知</span><span class="sxs-lookup"><span data-stu-id="b13c9-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="b13c9-123">アラートのバッチを更新 [します](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b13c9-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="b13c9-124">アラートの作成</span><span class="sxs-lookup"><span data-stu-id="b13c9-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="b13c9-125">アラート</span><span class="sxs-lookup"><span data-stu-id="b13c9-125">Alert</span></span>](alerts.md)|<span data-ttu-id="b13c9-126">Advanced Hunting から取得したイベント データに基づいてアラート [を作成します](run-advanced-query-api.md)。</span><span class="sxs-lookup"><span data-stu-id="b13c9-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="b13c9-127">関連するドメインを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="b13c9-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="b13c9-128">ドメイン コレクション</span><span class="sxs-lookup"><span data-stu-id="b13c9-128">Domain collection</span></span>| <span data-ttu-id="b13c9-129">アラートに関連付けられている URL を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b13c9-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="b13c9-130">関連ファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="b13c9-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="b13c9-131">[ファイル](files.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="b13c9-131">[File](files.md) collection</span></span> |  <span data-ttu-id="b13c9-132">アラートに [関連](files.md) 付けられているファイル エンティティを一覧表示 [します](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b13c9-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="b13c9-133">関連する IPs の一覧</span><span class="sxs-lookup"><span data-stu-id="b13c9-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="b13c9-134">IP コレクション</span><span class="sxs-lookup"><span data-stu-id="b13c9-134">IP collection</span></span> | <span data-ttu-id="b13c9-135">アラートに関連付けられているリストの AP。</span><span class="sxs-lookup"><span data-stu-id="b13c9-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="b13c9-136">関連するコンピューターを取得する</span><span class="sxs-lookup"><span data-stu-id="b13c9-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="b13c9-137">マシン</span><span class="sxs-lookup"><span data-stu-id="b13c9-137">Machine</span></span>](machine.md) | <span data-ttu-id="b13c9-138">アラート [に](machine.md) 関連付けられている [コンピューター](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b13c9-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="b13c9-139">関連ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="b13c9-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="b13c9-140">User</span><span class="sxs-lookup"><span data-stu-id="b13c9-140">User</span></span>](user.md) | <span data-ttu-id="b13c9-141">アラート [に](user.md) 関連付けられている [ユーザー](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b13c9-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="b13c9-142">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b13c9-142">Properties</span></span>

<span data-ttu-id="b13c9-143">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b13c9-143">Property</span></span> |    <span data-ttu-id="b13c9-144">種類</span><span class="sxs-lookup"><span data-stu-id="b13c9-144">Type</span></span>    |    <span data-ttu-id="b13c9-145">説明</span><span class="sxs-lookup"><span data-stu-id="b13c9-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="b13c9-146">id</span><span class="sxs-lookup"><span data-stu-id="b13c9-146">id</span></span> | <span data-ttu-id="b13c9-147">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-147">String</span></span> | <span data-ttu-id="b13c9-148">アラート ID。</span><span class="sxs-lookup"><span data-stu-id="b13c9-148">Alert ID.</span></span>
<span data-ttu-id="b13c9-149">title</span><span class="sxs-lookup"><span data-stu-id="b13c9-149">title</span></span> | <span data-ttu-id="b13c9-150">String</span><span class="sxs-lookup"><span data-stu-id="b13c9-150">String</span></span> | <span data-ttu-id="b13c9-151">警告タイトル。</span><span class="sxs-lookup"><span data-stu-id="b13c9-151">Alert title.</span></span>
<span data-ttu-id="b13c9-152">説明</span><span class="sxs-lookup"><span data-stu-id="b13c9-152">description</span></span> | <span data-ttu-id="b13c9-153">String</span><span class="sxs-lookup"><span data-stu-id="b13c9-153">String</span></span> | <span data-ttu-id="b13c9-154">警告の説明。</span><span class="sxs-lookup"><span data-stu-id="b13c9-154">Alert description.</span></span>
<span data-ttu-id="b13c9-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="b13c9-155">alertCreationTime</span></span> | <span data-ttu-id="b13c9-156">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b13c9-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="b13c9-157">アラートが作成された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="b13c9-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="b13c9-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="b13c9-158">lastEventTime</span></span> | <span data-ttu-id="b13c9-159">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b13c9-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="b13c9-160">同じデバイスでアラートをトリガーしたイベントの最後の発生。</span><span class="sxs-lookup"><span data-stu-id="b13c9-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="b13c9-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="b13c9-161">firstEventTime</span></span> | <span data-ttu-id="b13c9-162">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b13c9-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="b13c9-163">そのデバイスでアラートをトリガーしたイベントの最初の発生。</span><span class="sxs-lookup"><span data-stu-id="b13c9-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="b13c9-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="b13c9-164">lastUpdateTime</span></span> | <span data-ttu-id="b13c9-165">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b13c9-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="b13c9-166">アラートが最後に更新された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="b13c9-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="b13c9-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="b13c9-167">resolvedTime</span></span> | <span data-ttu-id="b13c9-168">Null 許容の DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b13c9-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="b13c9-169">アラートの状態が [解決済み] に変更された日時。</span><span class="sxs-lookup"><span data-stu-id="b13c9-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="b13c9-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="b13c9-170">incidentId</span></span> | <span data-ttu-id="b13c9-171">Null 許容長</span><span class="sxs-lookup"><span data-stu-id="b13c9-171">Nullable Long</span></span> | <span data-ttu-id="b13c9-172">アラート [の](view-incidents-queue.md) インシデント ID。</span><span class="sxs-lookup"><span data-stu-id="b13c9-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="b13c9-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="b13c9-173">investigationId</span></span> | <span data-ttu-id="b13c9-174">Null 許容長</span><span class="sxs-lookup"><span data-stu-id="b13c9-174">Nullable Long</span></span> | <span data-ttu-id="b13c9-175">アラート [に](automated-investigations.md) 関連する調査 ID。</span><span class="sxs-lookup"><span data-stu-id="b13c9-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="b13c9-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="b13c9-176">investigationState</span></span> | <span data-ttu-id="b13c9-177">Null 許容列挙</span><span class="sxs-lookup"><span data-stu-id="b13c9-177">Nullable Enum</span></span> | <span data-ttu-id="b13c9-178">調査の現在の [状態](automated-investigations.md)です。</span><span class="sxs-lookup"><span data-stu-id="b13c9-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="b13c9-179">指定できる値は、'Unknown'、'Terminated'、 'SuccessfullyRemediated', '良性', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'unsupportedAlertType', 'unsupportedAlertType''</span><span class="sxs-lookup"><span data-stu-id="b13c9-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="b13c9-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="b13c9-180">assignedTo</span></span> | <span data-ttu-id="b13c9-181">String</span><span class="sxs-lookup"><span data-stu-id="b13c9-181">String</span></span> | <span data-ttu-id="b13c9-182">アラートの所有者。</span><span class="sxs-lookup"><span data-stu-id="b13c9-182">Owner of the alert.</span></span>
<span data-ttu-id="b13c9-183">severity</span><span class="sxs-lookup"><span data-stu-id="b13c9-183">severity</span></span> | <span data-ttu-id="b13c9-184">列挙</span><span class="sxs-lookup"><span data-stu-id="b13c9-184">Enum</span></span> | <span data-ttu-id="b13c9-185">アラートの重大度。</span><span class="sxs-lookup"><span data-stu-id="b13c9-185">Severity of the alert.</span></span> <span data-ttu-id="b13c9-186">指定できる値は、'UnSpecified'、'Informational'、'Low'、'Medium' および 'High' です。</span><span class="sxs-lookup"><span data-stu-id="b13c9-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="b13c9-187">status</span><span class="sxs-lookup"><span data-stu-id="b13c9-187">status</span></span> | <span data-ttu-id="b13c9-188">列挙</span><span class="sxs-lookup"><span data-stu-id="b13c9-188">Enum</span></span> | <span data-ttu-id="b13c9-189">アラートの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="b13c9-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="b13c9-190">指定できる値は、'Unknown'、'New'、'InProgress'、'Resolved' です。</span><span class="sxs-lookup"><span data-stu-id="b13c9-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="b13c9-191">classification</span><span class="sxs-lookup"><span data-stu-id="b13c9-191">classification</span></span> | <span data-ttu-id="b13c9-192">Null 許容列挙</span><span class="sxs-lookup"><span data-stu-id="b13c9-192">Nullable Enum</span></span> | <span data-ttu-id="b13c9-193">アラートの仕様。</span><span class="sxs-lookup"><span data-stu-id="b13c9-193">Specification of the alert.</span></span> <span data-ttu-id="b13c9-194">指定できる値は、'Unknown'、'FalsePositive'、'TruePositive'です。</span><span class="sxs-lookup"><span data-stu-id="b13c9-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="b13c9-195">決定</span><span class="sxs-lookup"><span data-stu-id="b13c9-195">determination</span></span> | <span data-ttu-id="b13c9-196">Null 許容列挙</span><span class="sxs-lookup"><span data-stu-id="b13c9-196">Nullable Enum</span></span> | <span data-ttu-id="b13c9-197">アラートの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b13c9-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="b13c9-198">指定できる値は、'NotAvailable'、'Apt'、'Malware'、'SecurityPersonnel'、'SecurityTesting'、'UnwantedSoftware'、'Other' です。</span><span class="sxs-lookup"><span data-stu-id="b13c9-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="b13c9-199">category</span><span class="sxs-lookup"><span data-stu-id="b13c9-199">category</span></span>| <span data-ttu-id="b13c9-200">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-200">String</span></span> | <span data-ttu-id="b13c9-201">アラートのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="b13c9-201">Category of the alert.</span></span>
<span data-ttu-id="b13c9-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="b13c9-202">detectionSource</span></span> | <span data-ttu-id="b13c9-203">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-203">String</span></span> | <span data-ttu-id="b13c9-204">検出ソース。</span><span class="sxs-lookup"><span data-stu-id="b13c9-204">Detection source.</span></span>
<span data-ttu-id="b13c9-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="b13c9-205">threatFamilyName</span></span> | <span data-ttu-id="b13c9-206">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-206">String</span></span> | <span data-ttu-id="b13c9-207">脅威ファミリ。</span><span class="sxs-lookup"><span data-stu-id="b13c9-207">Threat family.</span></span>
<span data-ttu-id="b13c9-208">threatName</span><span class="sxs-lookup"><span data-stu-id="b13c9-208">threatName</span></span> | <span data-ttu-id="b13c9-209">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-209">String</span></span> | <span data-ttu-id="b13c9-210">脅威の名前。</span><span class="sxs-lookup"><span data-stu-id="b13c9-210">Threat name.</span></span>
<span data-ttu-id="b13c9-211">machineId</span><span class="sxs-lookup"><span data-stu-id="b13c9-211">machineId</span></span> | <span data-ttu-id="b13c9-212">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-212">String</span></span> | <span data-ttu-id="b13c9-213">アラートに [関連付](machine.md) けられているコンピューター エンティティの ID。</span><span class="sxs-lookup"><span data-stu-id="b13c9-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="b13c9-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="b13c9-214">computerDnsName</span></span> | <span data-ttu-id="b13c9-215">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-215">String</span></span> | <span data-ttu-id="b13c9-216">[コンピューター](machine.md) の完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="b13c9-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="b13c9-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="b13c9-217">aadTenantId</span></span> | <span data-ttu-id="b13c9-218">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-218">String</span></span> | <span data-ttu-id="b13c9-219">Azure Active Directory ID。</span><span class="sxs-lookup"><span data-stu-id="b13c9-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="b13c9-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="b13c9-220">detectorId</span></span> | <span data-ttu-id="b13c9-221">文字列</span><span class="sxs-lookup"><span data-stu-id="b13c9-221">String</span></span> | <span data-ttu-id="b13c9-222">アラートをトリガーした検出器の ID。</span><span class="sxs-lookup"><span data-stu-id="b13c9-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="b13c9-223">comments</span><span class="sxs-lookup"><span data-stu-id="b13c9-223">comments</span></span> | <span data-ttu-id="b13c9-224">アラートコメントの一覧</span><span class="sxs-lookup"><span data-stu-id="b13c9-224">List of Alert comments</span></span> | <span data-ttu-id="b13c9-225">Alert Comment オブジェクトには、コメント文字列、createBy 文字列、createTime 日付時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b13c9-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="b13c9-226">証拠</span><span class="sxs-lookup"><span data-stu-id="b13c9-226">Evidence</span></span> | <span data-ttu-id="b13c9-227">アラート証拠の一覧</span><span class="sxs-lookup"><span data-stu-id="b13c9-227">List of Alert evidence</span></span> | <span data-ttu-id="b13c9-228">アラートに関連する証拠。</span><span class="sxs-lookup"><span data-stu-id="b13c9-228">Evidence related to the alert.</span></span> <span data-ttu-id="b13c9-229">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b13c9-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="b13c9-230">1 つのアラートを取得する場合の応答例:</span><span class="sxs-lookup"><span data-stu-id="b13c9-230">Response example for getting single alert:</span></span>

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
