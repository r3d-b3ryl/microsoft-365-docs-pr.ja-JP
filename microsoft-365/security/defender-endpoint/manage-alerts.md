---
title: エンドポイント通知の Microsoft Defender の管理
description: '[アラートの管理] メニューを使用して、アラートの状態を変更し、抑制ルールを作成して、アラートを非表示にし、コメントを送信し、個々のアラートの変更履歴を確認します。'
keywords: アラートの管理、管理、アラート、状態、新規、進行中、解決済み、アラートの解決、抑制、抑制、ルール、コンテキスト、履歴、コメント、変更
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187003"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="e17db-104">エンドポイント通知の Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="e17db-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e17db-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e17db-105">**Applies to:**</span></span>
- [<span data-ttu-id="e17db-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e17db-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e17db-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e17db-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="e17db-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e17db-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e17db-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e17db-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="e17db-110">Defender for Endpoint は、悪意のあるイベント、属性、コンテキスト情報の可能性を通知します。</span><span class="sxs-lookup"><span data-stu-id="e17db-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="e17db-111">新しいアラートの概要がセキュリティ操作ダッシュボードに表示され、アラート キュー内のすべてのアラートに **アクセスできます**。</span><span class="sxs-lookup"><span data-stu-id="e17db-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="e17db-112">アラートを管理するには、個別のデバイスの [通知] キューまたは[デバイス] ページの [アラート] タブでアラートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e17db-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="e17db-113">いずれかの場所でアラートを選択すると、[アラート管理] **ウィンドウが表示されます**。</span><span class="sxs-lookup"><span data-stu-id="e17db-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![アラート管理ウィンドウとアラート キューのイメージ](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="e17db-115">別のインシデントへのリンク</span><span class="sxs-lookup"><span data-stu-id="e17db-115">Link to another incident</span></span>
<span data-ttu-id="e17db-116">アラートまたは既存のインシデントへのリンクから新しいインシデントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="e17db-117">アラートの割り当て</span><span class="sxs-lookup"><span data-stu-id="e17db-117">Assign alerts</span></span>
<span data-ttu-id="e17db-118">アラートがまだ割り当てられていない場合は、[自分に **割** り当てる] を選択して、自分にアラートを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e17db-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="e17db-119">アラートを抑制する</span><span class="sxs-lookup"><span data-stu-id="e17db-119">Suppress alerts</span></span>
<span data-ttu-id="e17db-120">警告が表示されるのを抑制する必要があるシナリオMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="e17db-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="e17db-121">Defender for Endpoint を使用すると、組織内の既知のツールやプロセスなど、無実と知られている特定のアラートに対して抑制ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="e17db-122">抑制ルールは、既存のアラートから作成できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="e17db-123">必要に応じて無効にし、再び有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e17db-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="e17db-124">抑制ルールが作成されると、ルールが作成された時点から有効になります。</span><span class="sxs-lookup"><span data-stu-id="e17db-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="e17db-125">ルールは、ルールの作成前にキューに既に存在するアラートには影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="e17db-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="e17db-126">ルールは、ルールの作成後に設定された条件を満たすアラートにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e17db-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="e17db-127">抑制ルールには、次の 2 つのコンテキストから選択できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="e17db-128">**このデバイスのアラートを抑制する**</span><span class="sxs-lookup"><span data-stu-id="e17db-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="e17db-129">**組織内のアラートを抑制する**</span><span class="sxs-lookup"><span data-stu-id="e17db-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="e17db-130">ルールのコンテキストを使用すると、ポータルに表示される情報を調整し、実際のセキュリティアラートだけがポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e17db-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="e17db-131">次の表の例を使用して、抑制ルールのコンテキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="e17db-132">**Context**</span><span class="sxs-lookup"><span data-stu-id="e17db-132">**Context**</span></span>                           | <span data-ttu-id="e17db-133">**定義**</span><span class="sxs-lookup"><span data-stu-id="e17db-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="e17db-134">**シナリオの例**</span><span class="sxs-lookup"><span data-stu-id="e17db-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e17db-135">**このデバイスのアラートを抑制する**</span><span class="sxs-lookup"><span data-stu-id="e17db-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="e17db-136">同じアラート タイトルを持つアラートと、その特定のデバイス上のアラートだけが表示されません。</span><span class="sxs-lookup"><span data-stu-id="e17db-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="e17db-137">そのデバイス上の他のすべてのアラートは抑制されません。</span><span class="sxs-lookup"><span data-stu-id="e17db-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="e17db-138">セキュリティ研究者が、組織内の他のデバイスを攻撃するために使用された悪意のあるスクリプトを調査しています。</span><span class="sxs-lookup"><span data-stu-id="e17db-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="e17db-139">開発者は、チームの PowerShell スクリプトを定期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="e17db-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="e17db-140">**組織内のアラートを抑制する**</span><span class="sxs-lookup"><span data-stu-id="e17db-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="e17db-141">どのデバイスでも同じアラート タイトルを持つアラートは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e17db-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="e17db-142">良性の管理ツールは、組織内のすべてのユーザーが使用します。</span><span class="sxs-lookup"><span data-stu-id="e17db-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="e17db-143">アラートを抑制し、新しい抑制ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e17db-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="e17db-144">カスタム ルールを作成して、アラートを抑制または解決する時間を制御します。</span><span class="sxs-lookup"><span data-stu-id="e17db-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="e17db-145">アラートのタイトル、侵害のインジケーター、および条件を指定することで、アラートが抑制される状況のコンテキストを制御できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="e17db-146">コンテキストを指定すると、アラートのアクションとスコープを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="e17db-147">非表示にするアラートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e17db-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="e17db-148">これにより、[アラート管理] **ウィンドウが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e17db-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="e17db-149">[抑制 **ルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e17db-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="e17db-150">これらの属性を使用して抑制条件を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="e17db-151">AND 演算子は各条件の間に適用され、すべての条件が満たされた場合にのみ抑制が行われます。</span><span class="sxs-lookup"><span data-stu-id="e17db-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="e17db-152">ファイル SHA1</span><span class="sxs-lookup"><span data-stu-id="e17db-152">File SHA1</span></span>
    * <span data-ttu-id="e17db-153">ファイル名 - ワイルドカードがサポートされています</span><span class="sxs-lookup"><span data-stu-id="e17db-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="e17db-154">フォルダー パス - ワイルドカードがサポートされています</span><span class="sxs-lookup"><span data-stu-id="e17db-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="e17db-155">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e17db-155">IP address</span></span>
    * <span data-ttu-id="e17db-156">URL - ワイルドカードがサポートされています</span><span class="sxs-lookup"><span data-stu-id="e17db-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="e17db-157">コマンド ライン - ワイルドカードがサポートされています</span><span class="sxs-lookup"><span data-stu-id="e17db-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="e17db-158">[トリガー **IOC] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e17db-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="e17db-159">アラートのアクションとスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="e17db-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="e17db-160">アラートを自動的に解決するか、ポータルから非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="e17db-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="e17db-161">自動的に解決されるアラートは、アラート キュー、アラート ページ、デバイス タイムラインの解決済みセクションに表示され、Defender for Endpoint API 全体で解決済みとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e17db-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="e17db-162">非表示としてマークされたアラートは、デバイスの関連付けられたアラートとダッシュボードの両方でシステム全体から抑制され、Defender for Endpoint API 全体でストリーミングされません。</span><span class="sxs-lookup"><span data-stu-id="e17db-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="e17db-163">ルール名とコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="e17db-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="e17db-164">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e17db-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="e17db-165">抑制ルールの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="e17db-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="e17db-166">ナビゲーション ウィンドウで、[アラートの抑制]**設定**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e17db-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="e17db-167">抑制ルールの一覧には、組織内のユーザーが作成したすべてのルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e17db-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="e17db-168">抑制ルールの管理の詳細については、「抑制ルールの [管理」を参照してください。](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="e17db-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="e17db-169">アラートの状態を変更する</span><span class="sxs-lookup"><span data-stu-id="e17db-169">Change the status of an alert</span></span>

<span data-ttu-id="e17db-170">調査の進行に合わせ、アラートの状態を変更することで、アラート (New、In **Progress、** または **Resolved)** を分類できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="e17db-171">これにより、チームがアラートに応答する方法を整理および管理できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="e17db-172">たとえば、チーム リーダーは、すべての新しいアラートを確認し、そのアラートを進行中のキューに割り当て、さらに分析を行います。</span><span class="sxs-lookup"><span data-stu-id="e17db-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="e17db-173">または、チーム リーダーは、アラートが良性であること、無関係なデバイス (セキュリティ管理者に属するデバイスなど) からのアラート、または以前のアラートを介して処理されている場合に、解決済みキューにアラートを割り当てる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e17db-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="e17db-174">アラートの分類</span><span class="sxs-lookup"><span data-stu-id="e17db-174">Alert classification</span></span>
<span data-ttu-id="e17db-175">分類を設定しないか、アラートが真のアラートか誤ったアラートかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="e17db-176">真陽性/誤検知の分類を提供することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e17db-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="e17db-177">この分類は、アラートの品質を監視し、アラートをより正確にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e17db-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="e17db-178">"決定" フィールドは、"真の正" 分類に対する追加の忠実度を定義します。</span><span class="sxs-lookup"><span data-stu-id="e17db-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="e17db-179">コメントを追加し、アラートの履歴を表示する</span><span class="sxs-lookup"><span data-stu-id="e17db-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="e17db-180">コメントを追加し、アラートに関する履歴イベントを表示して、アラートに加えた以前の変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e17db-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="e17db-181">通知に対して変更またはコメントが行われた場合は常に、[コメントと履歴] **セクションに記録** されます。</span><span class="sxs-lookup"><span data-stu-id="e17db-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="e17db-182">追加されたコメントは直ちにウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e17db-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e17db-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="e17db-183">Related topics</span></span>
- [<span data-ttu-id="e17db-184">抑制ルールの管理</span><span class="sxs-lookup"><span data-stu-id="e17db-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="e17db-185">Microsoft Defender for Endpoint Alerts キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="e17db-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="e17db-186">Microsoft Defender for Endpoint アラートの調査</span><span class="sxs-lookup"><span data-stu-id="e17db-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="e17db-187">Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する</span><span class="sxs-lookup"><span data-stu-id="e17db-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="e17db-188">Microsoft Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="e17db-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="e17db-189">Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="e17db-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="e17db-190">Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="e17db-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="e17db-191">Microsoft Defender for Endpoint のユーザー アカウントを調査する</span><span class="sxs-lookup"><span data-stu-id="e17db-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
