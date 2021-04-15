---
title: データ損失防止アラート ダッシュボードの詳細
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: データ損失防止アラートとアラート ダッシュボードについて学習します。
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760781"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a><span data-ttu-id="541ab-103">データ損失防止アラート ダッシュボードの詳細</span><span class="sxs-lookup"><span data-stu-id="541ab-103">Learn about the data loss prevention Alerts dashboard</span></span>

<span data-ttu-id="541ab-104">データ損失防止 (DLP) ポリシーの条件が、ユーザーが機密性の高いアイテムに対して実行しているアクションと一致する場合、ポリシーはアラートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="541ab-104">When the criteria in a Data loss prevention (DLP) policy is matched by the actions a user is taking on a sensitive item, the policy can generate an alert.</span></span> <span data-ttu-id="541ab-105">これにより、多くのアラートが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="541ab-105">This can result in a high volume of alerts.</span></span> <span data-ttu-id="541ab-106">DLP アラートは、アラート ダッシュボードで収集されます。</span><span class="sxs-lookup"><span data-stu-id="541ab-106">DLP alerts are collected in the alerts dashboard.</span></span> <span data-ttu-id="541ab-107">アラート ダッシュボードを使用すると、ポリシーの一致に関する詳細の詳細を詳細に調べることができます。</span><span class="sxs-lookup"><span data-stu-id="541ab-107">The alerts dashboard gives you a single place to go to perform a deep investigation of all the details regarding the policy match.</span></span>  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a><span data-ttu-id="541ab-108">ワークロード</span><span class="sxs-lookup"><span data-stu-id="541ab-108">Workloads</span></span>

<span data-ttu-id="541ab-109">Microsoft [365](https://compliance.microsoft.com/)コンプライアンス センターの[DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)アラート管理ダッシュボードには、次のワークロードに対する DLP ポリシーのアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="541ab-109">The [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts), in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), shows alerts for DLP policies on these workloads:</span></span>

- <span data-ttu-id="541ab-110">Exchange</span><span class="sxs-lookup"><span data-stu-id="541ab-110">Exchange</span></span>
- <span data-ttu-id="541ab-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="541ab-111">SharePoint</span></span>
- <span data-ttu-id="541ab-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="541ab-112">OneDrive</span></span>
- <span data-ttu-id="541ab-113">Teams</span><span class="sxs-lookup"><span data-stu-id="541ab-113">Teams</span></span>
- <span data-ttu-id="541ab-114">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="541ab-114">Windows 10 devices</span></span> 

> [!TIP]
> <span data-ttu-id="541ab-115">[Teams DLP](dlp-microsoft-teams.md)の対象[となるエンドポイント DLP](endpoint-dlp-learn-about.md)を使用しているお客様は、DLP アラート管理ダッシュボードにエンドポイント DLP ポリシーアラートと Teams DLP ポリシーアラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="541ab-115">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

## <a name="single-alert-and-aggregate-alert"></a><span data-ttu-id="541ab-116">単一のアラートと集約アラート</span><span class="sxs-lookup"><span data-stu-id="541ab-116">Single alert and aggregate alert</span></span>

<span data-ttu-id="541ab-117">DLP ポリシーで構成できるアラートには、2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="541ab-117">There are two types of alerts that can be configured in DLP policies.</span></span>

<span data-ttu-id="541ab-118">**通常** 、単一イベントアラートは、10 以上の顧客クレジット カード番号が組織外に送信される単一の電子メールなど、ボリュームが少ない状態で発生する機密性の高いイベントを監視するポリシーで使用されます。</span><span class="sxs-lookup"><span data-stu-id="541ab-118">**Single-event alerts** are typically used in policies that monitor for highly sensitive events that occur in a low volume, like a single email with 10 or more customer credit card numbers being sent outside your organization.</span></span>

<span data-ttu-id="541ab-119">**通常、集約イベントアラート** は、一期間に渡って大きなボリュームで発生するイベントを監視するポリシーで使用されます。</span><span class="sxs-lookup"><span data-stu-id="541ab-119">**Aggregate-event alerts** are typically used in policies that monitor for events that occur in a higher volume over a period of time.</span></span> <span data-ttu-id="541ab-120">たとえば、1 つの顧客クレジット カード番号を持つ 10 個の個別の電子メールが組織外に 48 時間以上送信されると、集約アラートをトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="541ab-120">For example, an aggregate alert can be triggered when 10 individual emails each with one customer credit card number is sent outside your org over 48 hours.</span></span>

## <a name="types-of-events"></a><span data-ttu-id="541ab-121">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="541ab-121">Types of events</span></span>

<span data-ttu-id="541ab-122">アラートに関連付けられているイベントの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="541ab-122">Here are some of the events associated with an alert.</span></span> <span data-ttu-id="541ab-123">UI では、特定のイベントを選択して詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="541ab-123">In the UI, you can choose a particular event to view its details.</span></span> 

### <a name="event-details"></a><span data-ttu-id="541ab-124">イベントの詳細</span><span class="sxs-lookup"><span data-stu-id="541ab-124">Event details</span></span>

|<span data-ttu-id="541ab-125">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="541ab-125">Property name</span></span>  |<span data-ttu-id="541ab-126">説明</span><span class="sxs-lookup"><span data-stu-id="541ab-126">Description</span></span>  |<span data-ttu-id="541ab-127">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="541ab-127">Event types</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="541ab-128">ID</span><span class="sxs-lookup"><span data-stu-id="541ab-128">ID</span></span> |<span data-ttu-id="541ab-129">イベントに関連付けられた一意の ID</span><span class="sxs-lookup"><span data-stu-id="541ab-129">unique ID associated with the event</span></span> |<span data-ttu-id="541ab-130">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-130">all events</span></span> |
|<span data-ttu-id="541ab-131">場所</span><span class="sxs-lookup"><span data-stu-id="541ab-131">Location</span></span> |<span data-ttu-id="541ab-132">イベントが検出されたワークロード</span><span class="sxs-lookup"><span data-stu-id="541ab-132">workload where the event was detected</span></span>|<span data-ttu-id="541ab-133">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-133">all events</span></span> |
|<span data-ttu-id="541ab-134">アクティビティの時間</span><span class="sxs-lookup"><span data-stu-id="541ab-134">time of activity</span></span>     |<span data-ttu-id="541ab-135">DLP ポリシーの条件に一致したユーザー アクティビティの時間</span><span class="sxs-lookup"><span data-stu-id="541ab-135">time of the user activity that matched the criteria of the DLP policy</span></span> |

### <a name="impacted-entities"></a><span data-ttu-id="541ab-136">影響を受け取ったエンティティ</span><span class="sxs-lookup"><span data-stu-id="541ab-136">Impacted entities</span></span>

|<span data-ttu-id="541ab-137">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="541ab-137">Property name</span></span> |<span data-ttu-id="541ab-138">説明</span><span class="sxs-lookup"><span data-stu-id="541ab-138">Description</span></span>| <span data-ttu-id="541ab-139">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="541ab-139">Event types</span></span>|
|---------|---------|---------|
|<span data-ttu-id="541ab-140">ユーザー</span><span class="sxs-lookup"><span data-stu-id="541ab-140">user</span></span> | <span data-ttu-id="541ab-141">ポリシーの一致を引き起こしたアクションを実行したユーザー</span><span class="sxs-lookup"><span data-stu-id="541ab-141">user who took the action that caused the policy match</span></span> | <span data-ttu-id="541ab-142">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-142">all events</span></span>|
|<span data-ttu-id="541ab-143">ホスト名</span><span class="sxs-lookup"><span data-stu-id="541ab-143">hostname</span></span> | <span data-ttu-id="541ab-144">DLP ポリシーの一致が発生したコンピューターのホスト名</span><span class="sxs-lookup"><span data-stu-id="541ab-144">host name of the computer where the DLP policy match occurred</span></span> | <span data-ttu-id="541ab-145">デバイス イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-145">device events</span></span>|
|<span data-ttu-id="541ab-146">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="541ab-146">IP address</span></span> | <span data-ttu-id="541ab-147">DLP ポリシーの一致が発生したコンピューターの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="541ab-147">IP address of the computer where the DLP policy match occurred</span></span> | <span data-ttu-id="541ab-148">デバイス イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-148">device events</span></span>|
|<span data-ttu-id="541ab-149">sha1</span><span class="sxs-lookup"><span data-stu-id="541ab-149">sha1</span></span> |<span data-ttu-id="541ab-150">ファイルの SHA-1 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="541ab-150">SHA-1 hash of the file</span></span> | <span data-ttu-id="541ab-151">デバイス イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-151">device events</span></span>|
|<span data-ttu-id="541ab-152">sha256</span><span class="sxs-lookup"><span data-stu-id="541ab-152">sha256</span></span> | <span data-ttu-id="541ab-153">ファイルの SHA-256 ハッシュ</span><span class="sxs-lookup"><span data-stu-id="541ab-153">SHA-256 hash of the file</span></span> | <span data-ttu-id="541ab-154">デバイス イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-154">device events</span></span>|
|<span data-ttu-id="541ab-155">MDATP デバイス ID</span><span class="sxs-lookup"><span data-stu-id="541ab-155">MDATP device ID</span></span> | <span data-ttu-id="541ab-156">エンドポイント デバイス MDATP ID</span><span class="sxs-lookup"><span data-stu-id="541ab-156">endpoint device MDATP ID</span></span>|
|<span data-ttu-id="541ab-157">ファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="541ab-157">file size</span></span> | <span data-ttu-id="541ab-158">ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="541ab-158">size of the file</span></span>| <span data-ttu-id="541ab-159">SharePoint、OneDrive、およびデバイス イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-159">SharePoint, OneDrive, and device events</span></span>|
|<span data-ttu-id="541ab-160">ファイル パス</span><span class="sxs-lookup"><span data-stu-id="541ab-160">file path</span></span> | <span data-ttu-id="541ab-161">DLP ポリシーの一致に関連するアイテムの絶対パス</span><span class="sxs-lookup"><span data-stu-id="541ab-161">the absolute path of the item involved with the DLP policy match</span></span> | <span data-ttu-id="541ab-162">SharePoint イベント、OneDrive イベント、デバイス イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-162">SharePoint, OneDrive, and devices events</span></span>|
|<span data-ttu-id="541ab-163">電子メールの受信者</span><span class="sxs-lookup"><span data-stu-id="541ab-163">email recipients</span></span> |<span data-ttu-id="541ab-164">電子メールが DLP ポリシーと一致する機密性の高いアイテムである場合、このフィールドには、その電子メールの受信者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="541ab-164">if an email was the sensitive item that matched the DLP policy, this field includes the recipients of that email</span></span>| <span data-ttu-id="541ab-165">Exchange イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-165">Exchange events</span></span>|
|<span data-ttu-id="541ab-166">電子メールの件名</span><span class="sxs-lookup"><span data-stu-id="541ab-166">email subject</span></span> |<span data-ttu-id="541ab-167">DLP ポリシーに一致した電子メールの件名</span><span class="sxs-lookup"><span data-stu-id="541ab-167">subject of the email that matched the DLP policy</span></span> |<span data-ttu-id="541ab-168">Exchange イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-168">Exchange events</span></span>|
|<span data-ttu-id="541ab-169">電子メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="541ab-169">email attachments</span></span> | <span data-ttu-id="541ab-170">DLP ポリシーに一致した電子メール内の添付ファイルの名前</span><span class="sxs-lookup"><span data-stu-id="541ab-170">names of the attachments in the email that matched the DLP policy</span></span>| <span data-ttu-id="541ab-171">Exchange イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-171">Exchange events</span></span>|
|<span data-ttu-id="541ab-172">サイトの所有者</span><span class="sxs-lookup"><span data-stu-id="541ab-172">site owner</span></span> |<span data-ttu-id="541ab-173">サイト所有者の名前</span><span class="sxs-lookup"><span data-stu-id="541ab-173">name of the site owner</span></span>| <span data-ttu-id="541ab-174">SharePoint イベントと OneDrive イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-174">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="541ab-175">サイト URL</span><span class="sxs-lookup"><span data-stu-id="541ab-175">site URL</span></span> |<span data-ttu-id="541ab-176">DLP ポリシーの一致が発生した SharePoint または OneDrive サイトの URL の完全</span><span class="sxs-lookup"><span data-stu-id="541ab-176">full of the URL of the SharePoint or OneDrive site where the DLP policy match occurred</span></span> |<span data-ttu-id="541ab-177">SharePoint イベントと OneDrive イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-177">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="541ab-178">作成されたファイル</span><span class="sxs-lookup"><span data-stu-id="541ab-178">file created</span></span> |<span data-ttu-id="541ab-179">DLP ポリシーに一致したファイルの作成時間</span><span class="sxs-lookup"><span data-stu-id="541ab-179">time of creation of the file that matched the DLP policy</span></span> |<span data-ttu-id="541ab-180">SharePoint イベントと OneDrive イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-180">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="541ab-181">ファイルの最終変更</span><span class="sxs-lookup"><span data-stu-id="541ab-181">file last modified</span></span> | <span data-ttu-id="541ab-182">DLP ポリシーに一致したファイルが最後に変更された時刻</span><span class="sxs-lookup"><span data-stu-id="541ab-182">the last time that the file that matched the DLP policy was changed</span></span> | <span data-ttu-id="541ab-183">SharePoint イベントと OneDrive イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-183">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="541ab-184">ファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="541ab-184">file size</span></span> | <span data-ttu-id="541ab-185">DLP ポリシーに一致したファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="541ab-185">size of the file that matched the DLP policy</span></span> |<span data-ttu-id="541ab-186">SharePoint イベントと OneDrive イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-186">SharePoint and OneDrive events</span></span>|
|<span data-ttu-id="541ab-187">ファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="541ab-187">file owner</span></span> |<span data-ttu-id="541ab-188">DLP ポリシーに一致したファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="541ab-188">owner of the file that matched the DLP policy</span></span> |<span data-ttu-id="541ab-189">SharePoint イベントと OneDrive イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-189">SharePoint and OneDrive events</span></span>|  

### <a name="policy-details"></a><span data-ttu-id="541ab-190">ポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="541ab-190">Policy details</span></span>

|<span data-ttu-id="541ab-191">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="541ab-191">Property name</span></span> |<span data-ttu-id="541ab-192">説明</span><span class="sxs-lookup"><span data-stu-id="541ab-192">Description</span></span> |<span data-ttu-id="541ab-193">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="541ab-193">Event types</span></span> |
|---------|---------|---------|
|<span data-ttu-id="541ab-194">DLP ポリシーの一致</span><span class="sxs-lookup"><span data-stu-id="541ab-194">DLP policy matched</span></span> |<span data-ttu-id="541ab-195">一致する DLP ポリシーの名前</span><span class="sxs-lookup"><span data-stu-id="541ab-195">name of the matched DLP policy</span></span> |<span data-ttu-id="541ab-196">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-196">all events</span></span>|
|<span data-ttu-id="541ab-197">ルールの一致</span><span class="sxs-lookup"><span data-stu-id="541ab-197">rule matched</span></span> |<span data-ttu-id="541ab-198">一致する DLP ポリシー ルールの名前</span><span class="sxs-lookup"><span data-stu-id="541ab-198">name of the matched DLP policy rule</span></span> |<span data-ttu-id="541ab-199">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-199">all events</span></span>|
|<span data-ttu-id="541ab-200">機密情報の種類 (SIT) が検出されました</span><span class="sxs-lookup"><span data-stu-id="541ab-200">sensitive information types (SIT) detected</span></span>|<span data-ttu-id="541ab-201">DLP ポリシーの一致の一部として検出された SIT</span><span class="sxs-lookup"><span data-stu-id="541ab-201">SITs that were detected as part of the DLP policy match</span></span> |<span data-ttu-id="541ab-202">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-202">all events</span></span>|
|<span data-ttu-id="541ab-203">実行された処理</span><span class="sxs-lookup"><span data-stu-id="541ab-203">actions taken</span></span> |<span data-ttu-id="541ab-204">DLP ポリシーの一致を引き起こしたアクション</span><span class="sxs-lookup"><span data-stu-id="541ab-204">actions that were taken that caused the DLP policy match</span></span>| <span data-ttu-id="541ab-205">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-205">all events</span></span>|
|<span data-ttu-id="541ab-206">違反アクション</span><span class="sxs-lookup"><span data-stu-id="541ab-206">violating action</span></span> | <span data-ttu-id="541ab-207">DLP アラートを発生したエンドポイント デバイスのアクション</span><span class="sxs-lookup"><span data-stu-id="541ab-207">action on the endpoint device that raised the DLP alert</span></span>| <span data-ttu-id="541ab-208">デバイス イベント</span><span class="sxs-lookup"><span data-stu-id="541ab-208">device events</span></span> | 
|<span data-ttu-id="541ab-209">ユーザーのオーバーロード ポリシー</span><span class="sxs-lookup"><span data-stu-id="541ab-209">user overrode policy</span></span> |<span data-ttu-id="541ab-210">ユーザーがポリシー ヒントを使用してポリシーを上書きしました</span><span class="sxs-lookup"><span data-stu-id="541ab-210">did the user override the policy via a policy tip</span></span> | <span data-ttu-id="541ab-211">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-211">all events</span></span>|
|<span data-ttu-id="541ab-212">オーバーライドの位置合わせを使用する</span><span class="sxs-lookup"><span data-stu-id="541ab-212">use override justification</span></span> |<span data-ttu-id="541ab-213">オーバーライドのためにユーザーが提供する理由のテキスト</span><span class="sxs-lookup"><span data-stu-id="541ab-213">the text of the reason provided by the user for the override</span></span> | <span data-ttu-id="541ab-214">すべてのイベント</span><span class="sxs-lookup"><span data-stu-id="541ab-214">all events</span></span>|   

## <a name="see-also"></a><span data-ttu-id="541ab-215">関連項目</span><span class="sxs-lookup"><span data-stu-id="541ab-215">See Also</span></span>

- [<span data-ttu-id="541ab-216">データ損失防止アラート ダッシュボードの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="541ab-216">Get started with the data loss prevention alert dashboard</span></span>](dlp-alerts-dashboard-get-started.md)
- [<span data-ttu-id="541ab-217">データ損失防止を開始する場所</span><span class="sxs-lookup"><span data-stu-id="541ab-217">Where to start with data loss prevention</span></span>](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)