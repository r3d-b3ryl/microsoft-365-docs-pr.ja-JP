---
title: Microsoft 365 の自動調査の結果を表示する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 の自動調査の最中および実行後に、結果と主要な結果を表示することができます。
ms.date: 11/05/2020
ms.openlocfilehash: 4dc74987619c3f958c874927af6e4240b9d7e154
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357287"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a><span data-ttu-id="39571-104">Microsoft 365 での自動調査の詳細と結果</span><span class="sxs-lookup"><span data-stu-id="39571-104">Details and results of an automated investigation in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="39571-105">[Microsoft Defender For Office 365](office-365-atp.md)で[自動調査](office-365-air.md)が行われると、その調査に関する詳細が自動化された調査プロセスの間で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="39571-105">When an [automated investigation](office-365-air.md) occurs in [Microsoft Defender for Office 365](office-365-atp.md), details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="39571-106">必要なアクセス許可がある場合は、Microsoft 365 セキュリティセンターでその詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="39571-106">If you have the necessary permissions, you can view those details in the Microsoft 365 security center.</span></span> <span data-ttu-id="39571-107">調査の詳細には、最新の状態と、保留中のアクションを承認する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="39571-107">Investigation details provide you with up-to-date status, and the ability to approve any pending actions.</span></span>

## <a name="investigation-status"></a><span data-ttu-id="39571-108">調査の状態</span><span class="sxs-lookup"><span data-stu-id="39571-108">Investigation status</span></span>

<span data-ttu-id="39571-109">調査の状態は、分析と処理の進捗状況を示します。</span><span class="sxs-lookup"><span data-stu-id="39571-109">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="39571-110">調査が実行されると、状態の表示が変わり、脅威が検出されたかどうかと、処理が承認されているかどうかが示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="39571-110">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span>

|<span data-ttu-id="39571-111">状態</span><span class="sxs-lookup"><span data-stu-id="39571-111">Status</span></span>|<span data-ttu-id="39571-112">説明</span><span class="sxs-lookup"><span data-stu-id="39571-112">Description</span></span>|
|---|---|
|<span data-ttu-id="39571-113">**開始中**</span><span class="sxs-lookup"><span data-stu-id="39571-113">**Starting**</span></span>|<span data-ttu-id="39571-114">調査がトリガーされ、実行の開始を待機しています。</span><span class="sxs-lookup"><span data-stu-id="39571-114">The investigation has been triggered and waiting to start running.</span></span>|
|<span data-ttu-id="39571-115">**実行中**</span><span class="sxs-lookup"><span data-stu-id="39571-115">**Running**</span></span>|<span data-ttu-id="39571-116">調査プロセスが開始され、進行中です。</span><span class="sxs-lookup"><span data-stu-id="39571-116">The investigation process has started and is underway.</span></span> <span data-ttu-id="39571-117">この状態は、 [保留中のアクション](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) が承認されたときにも発生します。</span><span class="sxs-lookup"><span data-stu-id="39571-117">This state also occurs when [pending actions](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) are approved.</span></span>|
|<span data-ttu-id="39571-118">**脅威は見つかりませんでした**</span><span class="sxs-lookup"><span data-stu-id="39571-118">**No Threats Found**</span></span>|<span data-ttu-id="39571-119">調査が終了し、脅威 (ユーザーアカウント、電子メールメッセージ、URL、またはファイル) が特定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="39571-119">The investigation has finished and no threats (user account, email message, URL, or file) were identified.</span></span> <p> <span data-ttu-id="39571-120">**ヒント**: 何かが失われていると疑われる場合 (誤否定など)、 [脅威エクスプローラー](threat-explorer.md)を使用して操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="39571-120">**TIP**: If you suspect something was missed (such as a false negative), you can take action using [Threat Explorer](threat-explorer.md).</span></span>|
|<span data-ttu-id="39571-121">**脅威が検出されました**</span><span class="sxs-lookup"><span data-stu-id="39571-121">**Threats Found**</span></span>|<span data-ttu-id="39571-122">自動調査で問題が検出されましたが、その問題を解決するための特定の修復処置はありません。</span><span class="sxs-lookup"><span data-stu-id="39571-122">The automated investigation found issues, but there are no specific remediation actions to resolve those issues.</span></span> <p> <span data-ttu-id="39571-123">検出された **脅威** の状態は、一部の種類のユーザーアクティビティを識別したが、クリーンアップアクションを使用できない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39571-123">The **Threats Found** status can occur when some type of user activity was identified but no cleanup actions are available.</span></span> <span data-ttu-id="39571-124">例としては、次のいずれかのユーザーアクティビティが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="39571-124">Examples include any of the following user activities:</span></span> <ul><li><span data-ttu-id="39571-125">[データ損失防止](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies)(DLP) イベント</span><span class="sxs-lookup"><span data-stu-id="39571-125">A [data loss prevention](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (DLP) event</span></span></li><li><span data-ttu-id="39571-126">異常を送信している電子メール</span><span class="sxs-lookup"><span data-stu-id="39571-126">An email sending anomaly</span></span></li><li><span data-ttu-id="39571-127">送信されたマルウェア</span><span class="sxs-lookup"><span data-stu-id="39571-127">Sent malware</span></span></li><li><span data-ttu-id="39571-128">送信されたフィッシング</span><span class="sxs-lookup"><span data-stu-id="39571-128">Sent phish</span></span></li></ul> <p> <span data-ttu-id="39571-129">この調査では、修復する悪意のある Url、ファイル、または電子メールメッセージが見つかりません。また、転送ルールや委任をオフにするなど、修正するメールボックスアクティビティはありません。</span><span class="sxs-lookup"><span data-stu-id="39571-129">The investigation found no malicious URLs, files, or email messages to remediate, and no mailbox activity to fix, such as turning off forwarding rules or delegation.</span></span> <p> <span data-ttu-id="39571-130">**ヒント**: 何かが失われていると疑われる場合 (誤否定など)、 [脅威エクスプローラー](threat-explorer.md)を使用して調査し、アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="39571-130">**TIP**: If you suspect something was missed (such as a false negative), you can investigate and take action using [Threat Explorer](threat-explorer.md).</span></span>|
|<span data-ttu-id="39571-131">**システムによる終了**</span><span class="sxs-lookup"><span data-stu-id="39571-131">**Terminated By System**</span></span>|<span data-ttu-id="39571-132">調査が停止しました。</span><span class="sxs-lookup"><span data-stu-id="39571-132">The investigation stopped.</span></span> <span data-ttu-id="39571-133">調査は、いくつかの理由で停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="39571-133">An investigation can stop for several reasons:</span></span> <ul><li><span data-ttu-id="39571-134">調査の保留中のアクションが期限切れになった。</span><span class="sxs-lookup"><span data-stu-id="39571-134">The investigation's pending actions expired.</span></span> <span data-ttu-id="39571-135">1週間の承認を待機した後、保留中のアクションがタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="39571-135">Pending actions time out after awaiting approval for one week.</span></span></li><li><span data-ttu-id="39571-136">アクションが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="39571-136">There are too many actions.</span></span> <span data-ttu-id="39571-137">たとえば、悪意のある Url をクリックしているユーザーが多すぎると、調査を停止させることができるように、すべてのアナライザーを実行する調査の能力を超えることがあります。</span><span class="sxs-lookup"><span data-stu-id="39571-137">For example, if there are too many users clicking on malicious URLs, it can exceed the investigation's ability to run all the analyzers, so the investigation halts.</span></span></li></ul> <p> <span data-ttu-id="39571-138">**ヒント**: 操作が実行される前に調査が停止した場合は、 [脅威エクスプローラー](threat-explorer.md) を使用して脅威を見つけて解決します。</span><span class="sxs-lookup"><span data-stu-id="39571-138">**TIP**: If an investigation halts before actions were taken, try using [Threat Explorer](threat-explorer.md) to find and address threats.</span></span>|
|<span data-ttu-id="39571-139">**保留中のアクション**</span><span class="sxs-lookup"><span data-stu-id="39571-139">**Pending Action**</span></span>|<span data-ttu-id="39571-140">調査で、悪意のある電子メール、悪意のある URL、危険なメールボックスの設定などの脅威、および脅威が [承認待ち](air-review-approve-pending-completed-actions.md)であることを修復するアクションを検出しました。</span><span class="sxs-lookup"><span data-stu-id="39571-140">The investigation has found a threat, such as a malicious email, a malicious URL, or a risky mailbox setting, and an action to remediate that threat is [awaiting approval](air-review-approve-pending-completed-actions.md).</span></span> <p> <span data-ttu-id="39571-141">**保留中のアクション** の状態は、対応するアクションを含む脅威が見つかった場合にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="39571-141">The **Pending Action** state is triggered when any threat with a corresponding action is found.</span></span> <span data-ttu-id="39571-142">ただし、保留中のアクションのリストは、調査を実行すると増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39571-142">However, the list of pending actions can increase as an investigation runs.</span></span> <span data-ttu-id="39571-143">[調査ログ](#playbook-log)を調べて、他の項目がまだ完了待ち状態かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="39571-143">Check the [investigation log](#playbook-log) to see if other items are still pending completion.</span></span>|
|<span data-ttu-id="39571-144">**修復済み**</span><span class="sxs-lookup"><span data-stu-id="39571-144">**Remediated**</span></span>|<span data-ttu-id="39571-145">調査が終了し、すべての修復アクションが承認されました (完全に修復済みとして示されています)。</span><span class="sxs-lookup"><span data-stu-id="39571-145">The investigation finished and all remediation actions were approved (this is noted as fully remediated).</span></span> <p> <span data-ttu-id="39571-146">**注**: 承認された修復アクションには、アクションを実行できないエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="39571-146">**NOTE**: Approved remediation actions can have errors that prevent the actions from being taken.</span></span> <span data-ttu-id="39571-147">修復アクションが正常に完了したかどうかに関係なく、調査状況は変わりません。</span><span class="sxs-lookup"><span data-stu-id="39571-147">Regardless of whether remediation actions are successfully completed, the investigation status does not change.</span></span> <span data-ttu-id="39571-148">詳細な結果については、 [調査ログ](#playbook-log) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="39571-148">Check the [investigation log](#playbook-log) for detailed results.</span></span>|
|<span data-ttu-id="39571-149">**一部修復済み**</span><span class="sxs-lookup"><span data-stu-id="39571-149">**Partially Remediated**</span></span>|<span data-ttu-id="39571-150">調査で修復が行われ、一部が承認され、完了しています。</span><span class="sxs-lookup"><span data-stu-id="39571-150">The investigation resulted in remediation actions, and some were approved and completed.</span></span> <span data-ttu-id="39571-151">その他のアクションはまだ [保留中](air-review-approve-pending-completed-actions.md)です。</span><span class="sxs-lookup"><span data-stu-id="39571-151">Other actions are still [pending](air-review-approve-pending-completed-actions.md).</span></span>|
|<span data-ttu-id="39571-152">**Failed**</span><span class="sxs-lookup"><span data-stu-id="39571-152">**Failed**</span></span>|<span data-ttu-id="39571-153">少なくとも1つの調査アナライザーで、正常に完了できなかった問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="39571-153">At least one investigation analyzer ran into a problem where it could not complete properly.</span></span> <p> <span data-ttu-id="39571-154">**注**: 修復処置が承認された後に調査が失敗した場合でも、修復アクションが正常に完了している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39571-154">**NOTE**: If an investigation fails after remediation actions were approved, the remediation actions might still have succeeded.</span></span> <span data-ttu-id="39571-155">詳細な結果については、 [調査ログ](#playbook-log) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="39571-155">Check the [investigation log](#playbook-log) for detailed results.</span></span>|
|<span data-ttu-id="39571-156">**調整によってキューに入れられる**</span><span class="sxs-lookup"><span data-stu-id="39571-156">**Queued By Throttling**</span></span>|<span data-ttu-id="39571-157">調査はキューに保持されています。</span><span class="sxs-lookup"><span data-stu-id="39571-157">An investigation is being held in a queue.</span></span> <span data-ttu-id="39571-158">他の調査が完了すると、キュー調査が開始されます。</span><span class="sxs-lookup"><span data-stu-id="39571-158">When other investigations complete, queued investigations begin.</span></span> <span data-ttu-id="39571-159">調整によって、サービスのパフォーマンスが低下しないようにします。</span><span class="sxs-lookup"><span data-stu-id="39571-159">Throttling helps avoid poor service performance.</span></span>  <p> <span data-ttu-id="39571-160">**ヒント**: 保留中のアクションは、実行できる新しい調査の数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="39571-160">**TIP**: Pending actions can limit how many new investigations can run.</span></span> <span data-ttu-id="39571-161">[保留中のアクションを承認 (または拒否)](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39571-161">Make sure to [approve (or reject) pending actions](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).</span></span>|
|<span data-ttu-id="39571-162">**調整による終了**</span><span class="sxs-lookup"><span data-stu-id="39571-162">**Terminated By Throttling**</span></span>|<span data-ttu-id="39571-163">調査が長時間に保持されている場合は停止します。</span><span class="sxs-lookup"><span data-stu-id="39571-163">If an investigation is held in the queue too long, it stops.</span></span> <p> <span data-ttu-id="39571-164">**ヒント**: [脅威エクスプローラーから調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)できます。</span><span class="sxs-lookup"><span data-stu-id="39571-164">**TIP**: You can [start an investigation from Threat Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>|
|

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="39571-165">調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="39571-165">View details of an investigation</span></span>

1. <span data-ttu-id="39571-166">セキュリティ & コンプライアンスセンター () に移動し、 [https://protection.office.com](https://protection.office.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="39571-166">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="39571-167">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39571-167">Do one of the following actions:</span></span>

    - <span data-ttu-id="39571-168">[ **脅威管理**] \> **ダッシュボード** に移動します。</span><span class="sxs-lookup"><span data-stu-id="39571-168">Go to **Threat management** \> **Dashboard**.</span></span> <span data-ttu-id="39571-169">これにより、 [セキュリティダッシュボード](security-dashboard.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-169">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="39571-170">エアウィジェットは、 [セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-170">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="39571-171">**調査の概要** などのウィジェットを選択します。</span><span class="sxs-lookup"><span data-stu-id="39571-171">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="39571-172">[ **脅威管理** \> の **調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39571-172">Go to **Threat management** \> **Investigations**.</span></span>

    <span data-ttu-id="39571-173">どちらの方法でも、調査の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="39571-173">Either method takes you to a list of investigations.</span></span>

    ![AIR のメインの調査ページ](../../media/air-maininvestigationpage.png)

3. <span data-ttu-id="39571-175">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="39571-175">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="39571-176">これにより、調査の詳細ページが開き、[調査] グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-176">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![ARI の [調査グラフ] ページ](../../media/air-investigationgraphpage.png)

   <span data-ttu-id="39571-178">調査の詳細については、さまざまなタブを使用してください。</span><span class="sxs-lookup"><span data-stu-id="39571-178">Use the various tabs to learn more about the investigation.</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="39571-179">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="39571-179">View details about an alert related to an investigation</span></span>

<span data-ttu-id="39571-180">特定の種類の通知では、Microsoft 365 で自動調査がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="39571-180">Certain kinds of alerts trigger automated investigation in Microsoft 365.</span></span> <span data-ttu-id="39571-181">詳細については、「 [自動調査をトリガーするアラートポリシー](office-365-air.md#which-alert-policies-trigger-automated-investigations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39571-181">To learn more, see [alert policies that trigger automated investigations](office-365-air.md#which-alert-policies-trigger-automated-investigations).</span></span>

<span data-ttu-id="39571-182">次の手順を使用して、自動調査に関連付けられている通知の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="39571-182">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="39571-183">セキュリティ & コンプライアンスセンター () に移動し、 [https://protection.office.com](https://protection.office.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="39571-183">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="39571-184">[ **脅威管理** \> の **調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39571-184">Go to **Threat management** \> **Investigations**.</span></span>

3. <span data-ttu-id="39571-185">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="39571-185">In the list of investigations, select an item in the **ID** column.</span></span>

4. <span data-ttu-id="39571-186">調査の詳細を開いた状態で、[ **通知** ] タブを選択します。調査をトリガーしたアラートが一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="39571-186">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="39571-187">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="39571-187">Select an item in the list.</span></span> <span data-ttu-id="39571-188">ポップアップが開き、通知に関する詳細と追加情報およびアクションへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-188">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="39571-189">ポップアップの情報を確認し、特定の通知に応じて、ユーザーの **解決**、 **抑制**、または **通知** などのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="39571-189">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span>

    - <span data-ttu-id="39571-190">**解決** は通知を閉じることと同じです。</span><span class="sxs-lookup"><span data-stu-id="39571-190">**Resolve** is equivalent to closing an alert</span></span>

    - <span data-ttu-id="39571-191">**抑制** すると、指定した期間、ポリシーがアラートをトリガーしなくなります。</span><span class="sxs-lookup"><span data-stu-id="39571-191">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>

    - <span data-ttu-id="39571-192">**通知** ユーザーに既に入力されたユーザーのメールアドレスを使用してメールを開始し、セキュリティ運用チームがそれらのユーザーにメッセージを入力できるようにします。</span><span class="sxs-lookup"><span data-stu-id="39571-192">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="39571-193">(これは、 [脅威エクスプローラー](threat-explorer.md)を使用してメッセージを受信者に送信するのと似ています。)</span><span class="sxs-lookup"><span data-stu-id="39571-193">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>

## <a name="how-to-use-the-various-tabs"></a><span data-ttu-id="39571-194">さまざまなタブの使用方法</span><span class="sxs-lookup"><span data-stu-id="39571-194">How to use the various tabs</span></span>

<span data-ttu-id="39571-195">次のセクションでは、[自動調査] ページのさまざまなタブとその情報の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39571-195">The following sections walk you through the various tabs on the automated investigations page and how you can use the information.</span></span>

### <a name="automated-investigations-page"></a><span data-ttu-id="39571-196">自動調査ページ</span><span class="sxs-lookup"><span data-stu-id="39571-196">Automated investigations page</span></span>

<span data-ttu-id="39571-197">[自動調査] ページでは、組織での調査とその現在の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-197">The automated investigations page shows your organization's investigations and their current states.</span></span>

![AIR のメインの調査ページ](../../media/air-maininvestigationpage.png)

<span data-ttu-id="39571-199">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-199">You can:</span></span>

- <span data-ttu-id="39571-200">調査への直接の移動 ([**調査 ID**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="39571-200">Navigate directly to an investigation (select an **Investigation ID**).</span></span>

- <span data-ttu-id="39571-201">フィルターの適用。</span><span class="sxs-lookup"><span data-stu-id="39571-201">Apply filters.</span></span> <span data-ttu-id="39571-202">[**調査の種類**]、[**時間の範囲**]、[**状態**] から選択するか、これらの組み合わせを選択します。</span><span class="sxs-lookup"><span data-stu-id="39571-202">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>

- <span data-ttu-id="39571-203">データの .CSV ファイルへのエクスポート。</span><span class="sxs-lookup"><span data-stu-id="39571-203">Export the data to a .csv file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="39571-204">調査グラフ</span><span class="sxs-lookup"><span data-stu-id="39571-204">Investigation graph</span></span>

<span data-ttu-id="39571-205">特定の調査を開くと、[調査用グラフ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-205">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="39571-206">このページには、メール メッセージ、ユーザー (およびユーザーのアクティビティ)、トリガーされたアラートの一部として自動的に調査されたデバイスなど、さまざまなエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-206">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![ARI の [調査グラフ] ページ](../../media/air-investigationgraphpage.png)

<span data-ttu-id="39571-208">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-208">You can:</span></span>

- <span data-ttu-id="39571-209">現在の調査の概要図の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-209">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="39571-210">調査期間の概要の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-210">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="39571-211">概要図内のノードを選択すると、そのノードの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-211">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="39571-212">上部のタブを選択すると、選択したタブの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-212">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="39571-213">アラートの調査</span><span class="sxs-lookup"><span data-stu-id="39571-213">Alert investigation</span></span>

<span data-ttu-id="39571-214">調査の [**アラート**] タブでは、調査に関連するアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-214">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="39571-215">詳細には、調査に関連する、高リスクなサインイン、 [DLP ポリシー](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) 違反など、調査とその他の関連するアラートをトリガーしたアラートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="39571-215">Details include the alert that triggered the investigation and other correlated alerts, such as risky sign-in, [DLP policy](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) violations, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="39571-216">このページでは、セキュリティ アナリストは、個々のアラートの詳細情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="39571-216">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![AIR アラート ページ](../../media/air-investigationalertspage.png)

<span data-ttu-id="39571-218">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-218">You can:</span></span>

- <span data-ttu-id="39571-219">現在トリガーされているアラートおよびすべての関連アラートの概要図の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-219">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="39571-220">一覧でアラートを選択すると、アラートの完全な詳細情報を表示するフライアウト ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="39571-220">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="39571-221">メールの調査</span><span class="sxs-lookup"><span data-stu-id="39571-221">Email investigation</span></span>

<span data-ttu-id="39571-222">調査の [ **電子メール** ] タブで、調査の一部として識別された、元の電子メールと類似した電子メールのクラスターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-222">On the **Email** tab for an investigation, you can see the original emails and the clusters of similar email identified as part of the investigation.</span></span> <span data-ttu-id="39571-223">[**メール**] タブには、ユーザーから報告されたメールの詳細、最初に報告されたメール、マルウェア/フィッシングとしてゼロアワー自動消去されたメール メッセージなど、調査に関連するメール アイテムも表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-223">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

![ARI のメール調査ページ](../../media/air-investigationemailpage.png)

<span data-ttu-id="39571-225">電子メールの調査では、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="39571-225">With email investigation, you can:</span></span>

- <span data-ttu-id="39571-226">現在のクラスター化の結果と検出された脅威の概要図の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-226">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="39571-227">クラスター エンティティまたは脅威リストをクリックすると、アラートのすべての詳細情報を表示するフライアウト ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="39571-227">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="39571-228">[**電子メールクラスターの詳細**] タブの上部にある [ **Explorer で開く**] リンクをクリックして、電子メールクラスターをさらに詳しく調べます。</span><span class="sxs-lookup"><span data-stu-id="39571-228">Further investigate the email cluster by clicking the **Open in Explorer** link at the top of the **Email cluster details** tab</span></span>

![フライアウトの詳細情報を表示した AIR のメール調査](../../media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="39571-230">組織内のユーザーが送受信する膨大な量の電子メールと、電子メール通信や攻撃の複数ユーザーの性質を考慮すると、次のプロセスはかなりの時間がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39571-230">Given the sheer volume of email that users in an organization send and receive, plus the multi-user nature of email communications and attacks, the following process can take a significant amount of time:</span></span>

1. <span data-ttu-id="39571-231">メッセージヘッダー、本文、URL、および添付ファイルから類似した属性に基づいて電子メールメッセージをクラスター化する。</span><span class="sxs-lookup"><span data-stu-id="39571-231">Clustering email messages based on similar attributes from a message header, body, URL, and attachments.</span></span>
2. <span data-ttu-id="39571-232">悪意のある電子メールを適切な電子メールから分離します。</span><span class="sxs-lookup"><span data-stu-id="39571-232">Separating malicious email from the good email.</span></span>
3. <span data-ttu-id="39571-233">悪意のある電子メールメッセージに対してアクションを実行する。</span><span class="sxs-lookup"><span data-stu-id="39571-233">Taking action on malicious email messages.</span></span>

<span data-ttu-id="39571-234">空気はこのプロセスを自動化し、組織のセキュリティチームの時間と労力を節約します。</span><span class="sxs-lookup"><span data-stu-id="39571-234">AIR automates this process, saving your organization's security team time and effort.</span></span>

#### <a name="types-of-email-clusters"></a><span data-ttu-id="39571-235">電子メールクラスターの種類</span><span class="sxs-lookup"><span data-stu-id="39571-235">Types of email clusters</span></span>

<span data-ttu-id="39571-236">電子メールの分析手順では、次の3種類の電子メールクラスターを識別できます。類似性クラスター (すべての調査)、インジケータークラスター (すべての調査)、メールボックス/ユーザークラスター。</span><span class="sxs-lookup"><span data-stu-id="39571-236">Three different types of email clusters can be identified during the email analysis step: similarity clusters (all investigations), indicator clusters (all investigations), and mailbox/user clusters.</span></span> <span data-ttu-id="39571-237">次の表で、これらの種類の電子メールクラスターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="39571-237">The following table describes these types of email clusters.</span></span>

|<span data-ttu-id="39571-238">メールクラスター</span><span class="sxs-lookup"><span data-stu-id="39571-238">Email cluster</span></span>|<span data-ttu-id="39571-239">説明</span><span class="sxs-lookup"><span data-stu-id="39571-239">Description</span></span>|
|---|---|
|<span data-ttu-id="39571-240">類似性クラスター</span><span class="sxs-lookup"><span data-stu-id="39571-240">Similarity clusters</span></span>|<span data-ttu-id="39571-241">同じような送信者とコンテンツの属性を持つ電子メールを探して識別された電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="39571-241">Email messages identified by hunting for emails with similar sender and content attributes.</span></span> <span data-ttu-id="39571-242">これらのクラスターは、元の検出結果に基づいて、悪意のあるコンテンツについて評価されます。</span><span class="sxs-lookup"><span data-stu-id="39571-242">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="39571-243">悪意のある電子メールを検出するのに十分な数の電子メールクラスターが悪意のあるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="39571-243">Email clusters that contain enough malicious email detections are considered malicious.</span></span>|
|<span data-ttu-id="39571-244">インジケータークラスター</span><span class="sxs-lookup"><span data-stu-id="39571-244">Indicator clusters</span></span>|<span data-ttu-id="39571-245">元の電子メールから同じインジケーターエンティティ (ファイルハッシュまたは URL) を探して識別された電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="39571-245">Email messages that are identified by hunting for the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="39571-246">元のファイルまたは URL のエンティティが悪意のあるものであると特定されると、AIR によりそのエンティティを含むメール メッセージのクラスター全体にインジケーター判定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="39571-246">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="39571-247">マルウェアとして識別されたファイルは、そのファイルを含む電子メールメッセージのクラスターがマルウェアの電子メールメッセージとして扱われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="39571-247">A file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span>|
|<span data-ttu-id="39571-248">メールボックス/ユーザークラスター</span><span class="sxs-lookup"><span data-stu-id="39571-248">Mailbox/user clusters</span></span>|<span data-ttu-id="39571-249">ユーザーに関連する電子メールメッセージ。ユーザーが侵害された調査に関与します。</span><span class="sxs-lookup"><span data-stu-id="39571-249">Email messages related to the user involved in a user compromise investigation.</span></span> <span data-ttu-id="39571-250">これらの電子メールクラスターは、セキュリティ運用チームによる詳細な分析のためのものであり、電子メール修復アクションを生成しません。</span><span class="sxs-lookup"><span data-stu-id="39571-250">These email clusters are for further analysis by the security operations team and will not generate email remediation actions.</span></span> <p> <span data-ttu-id="39571-251">侵害されたユーザーのセキュリティのプレイブックは、分析対象のユーザーによって送信されるメールを確認するために、メールボックスから送信されるメールの潜在的な影響を把握します。</span><span class="sxs-lookup"><span data-stu-id="39571-251">The compromised user security playbook  reviews the emails being sent by the user being analyzed in order to understand the potential impact of the emails being sent from the mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="39571-252">クラスタリングの目的は、攻撃またはキャンペーンの一部として同じ送信者によって送信された他の関連する電子メールメッセージを探して検索することです。</span><span class="sxs-lookup"><span data-stu-id="39571-252">The goal of clustering is to hunt and find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>  <span data-ttu-id="39571-253">場合によっては、正当な電子メールによって調査がトリガーされることがあります (たとえば、ユーザーがマーケティング電子メールを報告した場合)。</span><span class="sxs-lookup"><span data-stu-id="39571-253">In some cases, legitimate email might trigger an investigation (for example, a user reports a marketing email).</span></span>  <span data-ttu-id="39571-254">このようなシナリオでは、電子メールクラスターが悪意のない電子メールクラスターであることを特定する必要があります。適切な場合は、脅威を示して **いない** か、または電子メールを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39571-254">In these scenarios, the email clustering should identify that email clusters are not malicious – when it appropriately does so, it will **not** indicate a threat, nor will it recommend email removal.</span></span>

#### <a name="email-classifications"></a><span data-ttu-id="39571-255">電子メールの分類</span><span class="sxs-lookup"><span data-stu-id="39571-255">Email classifications</span></span>

<span data-ttu-id="39571-256">電子メールメッセージが分析されると、 *悪意*、 *疑わしい*、または *クリーン* ( *脅威として識別されません*) として分類されます。</span><span class="sxs-lookup"><span data-stu-id="39571-256">As email messages are analyzed, they are classified as *malicious*, *suspicious*, or *clean* (as in, *not identified as a threat*):</span></span>

- <span data-ttu-id="39571-257">メールボックス/ユーザーから送信された悪意のある *電子* メールは、メールボックス/アカウントが侵害される可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="39571-257">*Malicious emails* sent from the mailbox/user  indicate potential compromise of the mailbox/account.</span></span> <span data-ttu-id="39571-258">悪意のある電子メールが侵害の一部として影響を受ける可能性がある他のユーザーまたはメールボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-258">Other users/mailboxes that are potentially impacted by malicious email as part of a compromise are shown.</span></span>

- <span data-ttu-id="39571-259">メールボックス/ユーザーによって送信された *疑わしいメール* は、アカウントが侵害されたり、不要な電子メールアクティビティが発生する可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="39571-259">*Suspicious emails* sent by the mailbox/user indicate the potential for a compromised account or unwanted email activity.</span></span> <span data-ttu-id="39571-260">これらのメッセージには、メールボックスから送信されたスパム/バルクメールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="39571-260">These messages include any spam/bulk email sent from the mailbox.</span></span>

- <span data-ttu-id="39571-261">メールボックスまたはユーザーによって送信された *クリーンメール*(脅威ではないと見なされるメール) は、送信された正当なユーザーメールのビューをセキュリティ運用チームに提供できます。</span><span class="sxs-lookup"><span data-stu-id="39571-261">*Clean emails* (emails that are considered not a threat) sent by the mailbox/user can provide your security operations team with a view of legitimate user emails sent.</span></span> <span data-ttu-id="39571-262">ただし、電子メールアカウントが侵害された場合は、これらの電子メールにデータ exfiltration フィルターを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="39571-262">However, these emails can also include data exfiltration if the email account is compromised.</span></span>

#### <a name="more-about-email-counts"></a><span data-ttu-id="39571-263">メール数の詳細</span><span class="sxs-lookup"><span data-stu-id="39571-263">More about email counts</span></span>

<span data-ttu-id="39571-264">[電子メール] タブで識別された電子メールの数は、[ **電子メール** ] タブに表示されているすべての電子メールメッセージの合計数を表します。電子メールメッセージは複数のクラスターに存在するため、識別された (修復操作の影響を受けた) 電子メールメッセージの実際の合計数は、すべてのクラスターと元の受信者の電子メールメッセージに含まれる一意の電子メールメッセージの数になります。</span><span class="sxs-lookup"><span data-stu-id="39571-264">The email count identified on the email tab currently represents the sum total of all email messages that shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span>

<span data-ttu-id="39571-265">セキュリティ verdicts、操作、および配信場所が受信者ごとに異なるため、 [エクスプローラー](threat-explorer.md) と AIR count の両方の電子メールメッセージは受信者ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="39571-265">Both [Explorer](threat-explorer.md) and AIR count email messages on a per-recipient basis, because the security verdicts, actions, and delivery locations vary on a per-recipient basis.</span></span> <span data-ttu-id="39571-266">そのため、3人のユーザーに送信される元の電子メールは、1つの電子メールではなく、合計で3つの電子メールメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="39571-266">Thus, an original email sent to three users counts as a total of three email messages instead of one email.</span></span>

<span data-ttu-id="39571-267">電子メールに複数のアクションが含まれている場合や、すべてのアクションが発生した場合に電子メールの複数のコピーがある場合などに、メールが2回カウントされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="39571-267">There might be cases where an email gets counted two or more times, such as when an email has multiple actions on it, or when there are multiple copies of the email when all the actions occur.</span></span>

<span data-ttu-id="39571-268">たとえば、配信時に検出されたマルウェア電子メールは、ブロックされた (検疫された) 電子メールと、置き換えられた電子メール (脅威ファイルが警告ファイルに置き換えられて、ユーザーのメールボックスに配信される) の両方になることがあります。</span><span class="sxs-lookup"><span data-stu-id="39571-268">For example, a malware email that is detected at delivery can result in both a blocked (quarantined) email and a replaced email (threat file replaced with a warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="39571-269">システムに電子メールのコピーが文字どおり2つ存在するため、両方ともクラスター数でカウントされます。</span><span class="sxs-lookup"><span data-stu-id="39571-269">Because there are literally two copies of the email in the system, both might be counted in cluster counts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39571-270">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="39571-270">Here are a few points to keep in mind:</span></span>
>
> - <span data-ttu-id="39571-271">メール数は調査時に計算され、調査 flyouts を開くと (基になるクエリに基づいて) いくつかのカウントが再計算されます。</span><span class="sxs-lookup"><span data-stu-id="39571-271">Email counts are calculated at the time of the investigation, and some counts are recalculated when you open investigation flyouts (based on an underlying query).</span></span>
>
> - <span data-ttu-id="39571-272">[ **電子** メール] タブの電子メールクラスターに表示される電子メール数と、クラスターポップアップに表示される電子メールの数量の値は、調査時に計算され、変更されません。</span><span class="sxs-lookup"><span data-stu-id="39571-272">The email counts shown for the email clusters on the **Email** tab and the email quantity value shown on cluster flyout are calculated at the time of investigation, and do not change.</span></span>
>
> - <span data-ttu-id="39571-273">メールクラスターポップアップの [ **電子メール** ] タブの下部に表示される電子メール数、および調査の最初の分析後に受信した電子メールメッセージがエクスプローラーに表示されるメールメッセージ数に反映されます。</span><span class="sxs-lookup"><span data-stu-id="39571-273">The email count shown at the bottom of the **Email** tab of the email cluster flyout and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span>

<span data-ttu-id="39571-274">そのため、元の10個の電子メールメッセージを表示する電子メールクラスターでは、調査分析フェーズと管理者が調査をレビューしたときに5件の電子メールメッセージが到着すると、電子メールリストの合計が15件表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-274">Thus, an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when five more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="39571-275">同様に、古い調査では、Microsoft Defender for Office 365 プラン2のデータは、試用期間が7日後、有料ライセンスの場合は30日後に期限切れになるため、エクスプローラークエリに表示される件数が多いことが示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-275">Likewise, old investigations might start showing higher counts than Explorer queries show, because data in Microsoft Defender for Office 365 Plan 2 expires after 7 days for trials and after 30 days for paid licenses.</span></span>

<span data-ttu-id="39571-276">カウント履歴と現在のカウントの両方を異なるビューで表示することによって、調査の時点での電子メールの影響、および修復が実行されるまでの現在の影響を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="39571-276">Showing both count historical and current counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

> [!NOTE]
> <span data-ttu-id="39571-277">電子メールのコンテキストでは、調査の一環としてボリュームの異常な脅威が表面化することがあります。</span><span class="sxs-lookup"><span data-stu-id="39571-277">In the context of email, you might see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="39571-278">異常な量の発生は、以前のタイムフレームと比べて、調査イベントの時間の前後に似たようなメール メッセージのスパイクがあったことを示します。</span><span class="sxs-lookup"><span data-stu-id="39571-278">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="39571-279">似たような特徴 (件名や送信者ドメイン、本文の類似性や送信者の IP) を持つメール トラフィックのスパイクは、メール キャンペーンまたは攻撃の開始の典型です。</span><span class="sxs-lookup"><span data-stu-id="39571-279">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span>
> <span data-ttu-id="39571-280">ただし、これらの特徴は多くの場合、バルク、スパム、および正当なメール キャンペーンでも同様にみられます。</span><span class="sxs-lookup"><span data-stu-id="39571-280">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span>
>
> <span data-ttu-id="39571-281">異常な量で示されるのは潜在的な脅威であることから、ウイルス対策エンジン、デトネーション、または悪意の評価を使用して特定されたマルウェアやフィッシングの脅威ほどは重大でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39571-281">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="39571-282">ユーザーの調査</span><span class="sxs-lookup"><span data-stu-id="39571-282">User investigation</span></span>

<span data-ttu-id="39571-283">[**ユーザー**] タブには、調査対象として特定されたすべてのユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-283">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="39571-284">ユーザー アカウントは、それらのユーザー アカウントが影響を受けたり侵害されたりした可能性があるイベントまたは兆候があった場合に調査に表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-284">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="39571-285">たとえば次の画像では、侵害および異常の兆候が、作成された新しい受信トレイ ルールに基づき AIR により特定されています。　</span><span class="sxs-lookup"><span data-stu-id="39571-285">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="39571-286">調査の追加の詳細 (エビデンス) は、このタブ内の詳細なビューから利用できます。侵害と異常のインジケーターには、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)からの異常な検出も含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="39571-286">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies might also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![ARI のユーザー調査ページ](../../media/air-investigationuserspage.png)

<span data-ttu-id="39571-288">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-288">You can:</span></span>

- <span data-ttu-id="39571-289">特定されたユーザーの結果と検出されたリスクの概要図の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-289">Get a visual overview of identified user results and risks found.</span></span>

- <span data-ttu-id="39571-290">ユーザーを選択すると、アラートのすべての詳細情報を表示するフライアウト ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="39571-290">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="39571-291">コンピューターの調査</span><span class="sxs-lookup"><span data-stu-id="39571-291">Machine investigation</span></span>

<span data-ttu-id="39571-292">[**コンピューター**] タブには、調査対象として特定されたすべてのコンピューターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-292">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span>

![ARI のコンピューター調査ページ](../../media/air-investigationmachinepage.png)

<span data-ttu-id="39571-294">一部のプレイブックの一部として、エアは電子メールの脅威をデバイス (Zapped マルウェアなど) に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="39571-294">As part of some playbooks, AIR correlates email threats to devices (for example, Zapped malware).</span></span> <span data-ttu-id="39571-295">たとえば、調査では [エンドポイントに対して Microsoft Defender に対して](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) 悪意のあるファイルハッシュを渡します。</span><span class="sxs-lookup"><span data-stu-id="39571-295">For example, an investigation passes a malicious file hash across to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="39571-296">これにより、ユーザーが関わるコンピューターを自動的に調査できるため、クラウドとエンドポイント全体の両方で脅威に対処で脅威に対処できるようになります。</span><span class="sxs-lookup"><span data-stu-id="39571-296">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span>

<span data-ttu-id="39571-297">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-297">You can:</span></span>

- <span data-ttu-id="39571-298">現在のコンピューターと検出された脅威の概要図の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-298">Get a visual overview of the current machines and threats found.</span></span>

- <span data-ttu-id="39571-299">Microsoft Defender セキュリティセンターの [エンドポイント調査に関連する Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) のビューを開くコンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="39571-299">Select a machine to open a view that into the related [Microsoft Defender for Endpoint investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="39571-300">エンティティの調査</span><span class="sxs-lookup"><span data-stu-id="39571-300">Entity investigation</span></span>

<span data-ttu-id="39571-301">[ **エンティティ** ] タブには、調査の一環として識別され分析されたエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-301">On the **Entities** tab, you can see the entities identified and analyzed as part of the investigation.</span></span>

<span data-ttu-id="39571-302">ここでは、調査済みのエンティティと、メール メッセージ、クラスター、IP アドレス、ユーザーといった、エンティティの種類に関する詳細情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="39571-302">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="39571-303">分析されたエンティティの数と、各エンティティに関連付けられた脅威も確認できます。</span><span class="sxs-lookup"><span data-stu-id="39571-303">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span>

![ARI のエンティティ調査ページ](../../media/air-investigationentitiespage.png)

<span data-ttu-id="39571-305">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-305">You can:</span></span>

- <span data-ttu-id="39571-306">調査エンティティと検出された脅威の概要図の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-306">Get a visual overview of the investigation entities and threats found.</span></span>

- <span data-ttu-id="39571-307">エンティティを選択すると、関連するエンティティの詳細情報を表示するフライアウト ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="39571-307">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![ARI のエンティティ調査の詳細情報](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="39571-309">プレイブック ログ</span><span class="sxs-lookup"><span data-stu-id="39571-309">Playbook log</span></span>

<span data-ttu-id="39571-310">[**ログ**] タブには、調査中に実行されたすべてのプレイブック手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-310">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="39571-311">このログは、Office 365 の自動調査機能によって実行されたすべてのアナライザーおよびアクションの完全なインベントリを AIR の一部としてキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="39571-311">The log captures a complete inventory of all analyzers and actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="39571-312">ログでは、処理そのもの、説明、実際の処理での開始から終了までの所要時間など、実行されたすべてのステップを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="39571-312">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span>

![AIR の調査ログ ページ](../../media/air-investigationlogpage.png)

<span data-ttu-id="39571-314">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-314">You can:</span></span>

- <span data-ttu-id="39571-315">実行されたプレイブック手順の概要図の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-315">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="39571-316">結果の CSV ファイルへのエクスポート。</span><span class="sxs-lookup"><span data-stu-id="39571-316">Export the results to a CSV file.</span></span>
- <span data-ttu-id="39571-317">ビューのフィルタリング。</span><span class="sxs-lookup"><span data-stu-id="39571-317">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="39571-318">推奨処理</span><span class="sxs-lookup"><span data-stu-id="39571-318">Recommended actions</span></span>

<span data-ttu-id="39571-319">[**処理**] タブには、調査完了後に修復することが推奨されるすべてのプレイブック処理が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39571-319">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> <span data-ttu-id="39571-320">処置調査の最後に、Microsoft が推奨する手順をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="39571-320">Actions capture the steps Microsoft recommends you take at the end of an investigation.</span></span> <span data-ttu-id="39571-321">ここでは、1 つまたは複数のアクションを選択して、修復処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-321">You can take remediation actions here by selecting one or more actions.</span></span>

<span data-ttu-id="39571-322">[ **承認** ] を選択すると、修復が開始されます。</span><span class="sxs-lookup"><span data-stu-id="39571-322">Selecting **Approve** allows remediation to begin.</span></span> <span data-ttu-id="39571-323">(適切なアクセス許可が必要です-エクスプローラーと AIR からアクションを実行するには、 **検索と削除** の役割が必要です)。</span><span class="sxs-lookup"><span data-stu-id="39571-323">(Appropriate permissions are needed - the **Search And Purge** role is required to run actions from Explorer and AIR).</span></span>

<span data-ttu-id="39571-324">たとえば、セキュリティ閲覧者はアクションを表示できますが、承認することはできません。</span><span class="sxs-lookup"><span data-stu-id="39571-324">For example, a Security Reader can view actions, but not approve them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39571-325">すべてのアクションを承認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="39571-325">You do not have to approve every action.</span></span> <span data-ttu-id="39571-326">推奨されるアクションと一致しない場合、または組織で特定の種類のアクションが選択されていない場合は、アクションを **拒否** するか、または単に無視してアクションを実行しないことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="39571-326">If you do not agree with the recommended action or your organization does not choose certain types of actions, then you can choose to **Reject** the actions or simply ignore them and take no action.</span></span>
> <span data-ttu-id="39571-327">すべてのアクションを承認または拒否することで、調査が完全に終了 (状態は修復可能) されます。一部のアクションは不完全な状態になり、調査の状態が部分的に修復された状態に変化します。</span><span class="sxs-lookup"><span data-stu-id="39571-327">Approving and/or rejecting all actions lets the investigation fully close (status becomes remediated), while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![AIR の調査処理 ページ](../../media/air-investigationactionspage.png)

<span data-ttu-id="39571-329">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39571-329">You can:</span></span>

- <span data-ttu-id="39571-330">プレイブック推奨の処理の概要図の表示。</span><span class="sxs-lookup"><span data-stu-id="39571-330">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="39571-331">1 つまたは複数の処理の選択。</span><span class="sxs-lookup"><span data-stu-id="39571-331">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="39571-332">推奨処理の承認または拒否とコメント付け。</span><span class="sxs-lookup"><span data-stu-id="39571-332">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="39571-333">結果の CSV ファイルへのエクスポート。</span><span class="sxs-lookup"><span data-stu-id="39571-333">Export the results to a CSV file.</span></span>
- <span data-ttu-id="39571-334">ビューのフィルタリング。</span><span class="sxs-lookup"><span data-stu-id="39571-334">Filter the view.</span></span>

## <a name="next-steps"></a><span data-ttu-id="39571-335">次の手順</span><span class="sxs-lookup"><span data-stu-id="39571-335">Next steps</span></span>

- [<span data-ttu-id="39571-336">保留中のアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="39571-336">Review and approve pending actions</span></span>](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
