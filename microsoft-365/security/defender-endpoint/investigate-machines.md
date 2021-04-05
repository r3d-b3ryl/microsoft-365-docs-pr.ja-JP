---
title: Defender for Endpoint Devices リストのデバイスを調査する
description: アラート、ネットワーク接続情報、デバイス タグとグループの追加、サービスの正常性の確認を行って、影響を受けるデバイスを調査します。
keywords: デバイス、タグ、グループ、エンドポイント、アラート キュー、アラート、デバイス名、ドメイン、最後に表示される、内部 IP、アクティブなアラート、脅威カテゴリ、フィルター、並べ替え、アラートの確認、ネットワーク、接続、種類、パスワードの盗み取り、ランサムウェア、悪用、脅威、重要度の低い、サービスの正常性
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 154ecd66399b031ef2e60eef16227bb9bc2f8785
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587721"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="9e3a3-104">Microsoft Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9e3a3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9e3a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="9e3a3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9e3a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9e3a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e3a3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9e3a3-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="9e3a3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9e3a3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="9e3a3-110">特定のデバイスで発生したアラートの詳細を調べて、アラートまたは侵害の潜在的な範囲に関連する可能性のある他の動作またはイベントを特定します。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="9e3a3-111">調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="9e3a3-112">次の方法: デバイスから [調査パッケージを収集します](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="9e3a3-113">影響を受けるデバイスをポータルに表示するたびにクリックすると、そのデバイスに関する詳細なレポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="9e3a3-114">影響を受けるデバイスは、次の領域で識別されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="9e3a3-115">デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="9e3a3-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="9e3a3-116">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="9e3a3-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="9e3a3-117">セキュリティ運用ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="9e3a3-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="9e3a3-118">個々のアラート</span><span class="sxs-lookup"><span data-stu-id="9e3a3-118">Any individual alert</span></span>
- <span data-ttu-id="9e3a3-119">個々のファイルの詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="9e3a3-119">Any individual file details view</span></span>
- <span data-ttu-id="9e3a3-120">任意の IP アドレスまたはドメインの詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="9e3a3-120">Any IP address or domain details view</span></span>

<span data-ttu-id="9e3a3-121">特定のデバイスを調査すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="9e3a3-122">デバイスの詳細</span><span class="sxs-lookup"><span data-stu-id="9e3a3-122">Device details</span></span>
- <span data-ttu-id="9e3a3-123">応答アクション</span><span class="sxs-lookup"><span data-stu-id="9e3a3-123">Response actions</span></span>
- <span data-ttu-id="9e3a3-124">タブ (概要、アラート、タイムライン、セキュリティ推奨事項、ソフトウェア インベントリ、検出された脆弱性、不足している KB)</span><span class="sxs-lookup"><span data-stu-id="9e3a3-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="9e3a3-125">カード (アクティブなアラート、ログオンしているユーザー、セキュリティ評価)</span><span class="sxs-lookup"><span data-stu-id="9e3a3-125">Cards (active alerts, logged on users, security assessment)</span></span>

![デバイス ビューのイメージ](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="9e3a3-127">デバイスの詳細</span><span class="sxs-lookup"><span data-stu-id="9e3a3-127">Device details</span></span>

<span data-ttu-id="9e3a3-128">[デバイスの詳細] セクションには、デバイスのドメイン、OS、正常性状態などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="9e3a3-129">デバイスで利用可能な調査パッケージがある場合は、パッケージをダウンロードできるリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="9e3a3-130">応答アクション</span><span class="sxs-lookup"><span data-stu-id="9e3a3-130">Response actions</span></span>

<span data-ttu-id="9e3a3-131">応答アクションは、特定のデバイス ページの上部に沿って実行され、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="9e3a3-132">タグの管理</span><span class="sxs-lookup"><span data-stu-id="9e3a3-132">Manage tags</span></span>
- <span data-ttu-id="9e3a3-133">デバイスの分離</span><span class="sxs-lookup"><span data-stu-id="9e3a3-133">Isolate device</span></span>
- <span data-ttu-id="9e3a3-134">アプリの実行を制限する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-134">Restrict app execution</span></span>
- <span data-ttu-id="9e3a3-135">ウイルス対策スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-135">Run antivirus scan</span></span>
- <span data-ttu-id="9e3a3-136">調査パッケージの収集</span><span class="sxs-lookup"><span data-stu-id="9e3a3-136">Collect investigation package</span></span>
- <span data-ttu-id="9e3a3-137">ライブ応答セッションの開始</span><span class="sxs-lookup"><span data-stu-id="9e3a3-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="9e3a3-138">自動調査の開始</span><span class="sxs-lookup"><span data-stu-id="9e3a3-138">Initiate automated investigation</span></span>
- <span data-ttu-id="9e3a3-139">脅威のエキスパートに相談する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-139">Consult a threat expert</span></span>
- <span data-ttu-id="9e3a3-140">アクション センター</span><span class="sxs-lookup"><span data-stu-id="9e3a3-140">Action center</span></span>

<span data-ttu-id="9e3a3-141">アクション センター、特定のデバイス ページ、または特定のファイル ページで応答アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="9e3a3-142">デバイスでアクションを実行する方法の詳細については、「デバイスで応答アクションを実行 [する」を参照してください](respond-machine-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="9e3a3-143">詳細については、「ユーザー エンティティの [調査」を参照してください](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="9e3a3-144">タブ</span><span class="sxs-lookup"><span data-stu-id="9e3a3-144">Tabs</span></span>

<span data-ttu-id="9e3a3-145">タブには、デバイスに関連する関連するセキュリティと脅威防止情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="9e3a3-146">各タブで、列ヘッダーの上のバーから [列のカスタマイズ] を選択して、表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="9e3a3-147">概要</span><span class="sxs-lookup"><span data-stu-id="9e3a3-147">Overview</span></span>
<span data-ttu-id="9e3a3-148">[ **概要]** タブには、アクティブ [なアラート](#cards) 、ログオンしているユーザー、およびセキュリティ評価のカードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![デバイス ページの [概要] タブのイメージ](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="9e3a3-150">アラート</span><span class="sxs-lookup"><span data-stu-id="9e3a3-150">Alerts</span></span>

<span data-ttu-id="9e3a3-151">[ **アラート]** タブには、デバイスに関連付けられているアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="9e3a3-152">このリストは、アラート キューのフィルター[](alerts-queue.md)処理されたバージョンで、アラート、重大度 (高、中、低、情報)、キュー内の状態 (新規、進行中、解決済み)、分類 (設定されていない、誤ったアラート、真のアラート)、調査状態、アラートのカテゴリ、アラートに対処しているユーザー、および最後のアクティビティの短い説明を示します。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="9e3a3-153">アラートをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-153">You can also filter the alerts.</span></span>

![デバイスに関連するアラートのイメージ](images/alerts-device.png)

<span data-ttu-id="9e3a3-155">アラートの左側にある円のアイコンが選択されている場合は、フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="9e3a3-156">このパネルでは、アラートを管理し、インシデント番号や関連デバイスなどの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="9e3a3-157">一度に複数のアラートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="9e3a3-158">インシデント グラフやプロセス ツリーを含むアラートの完全なページ ビューを表示するには、アラートのタイトルを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="9e3a3-159">タイムライン</span><span class="sxs-lookup"><span data-stu-id="9e3a3-159">Timeline</span></span>

<span data-ttu-id="9e3a3-160">[ **タイムライン]** タブには、デバイスで観測されたイベントと関連するアラートの時系列ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="9e3a3-161">これにより、デバイスに関連するイベント、ファイル、IP アドレスを関連付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="9e3a3-162">タイムラインでは、特定の期間に発生したイベントを選択的にドリルダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="9e3a3-163">選択した期間にデバイスで発生したイベントの一時的なシーケンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="9e3a3-164">ビューをさらに制御するには、イベント グループでフィルター処理するか、列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="9e3a3-165">ファイアウォール イベントを表示するには、監査ポリシーを有効にする必要があります。「Audit [Filtering Platform 接続」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection)。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="9e3a3-166">ファイアウォールは、次のイベントをカバーします。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="9e3a3-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - ファイアウォール サービスが停止しました</span><span class="sxs-lookup"><span data-stu-id="9e3a3-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="9e3a3-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - アプリケーションがネットワーク上の受信接続を受け入れるのをブロックする</span><span class="sxs-lookup"><span data-stu-id="9e3a3-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="9e3a3-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - ブロックされた接続</span><span class="sxs-lookup"><span data-stu-id="9e3a3-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![イベントを含むデバイス タイムラインのイメージ](images/timeline-device.png)

<span data-ttu-id="9e3a3-171">一部の機能には、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="9e3a3-172">特定のイベントを検索する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-172">Search for specific events</span></span>
  - <span data-ttu-id="9e3a3-173">検索バーを使用して、特定のタイムライン イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="9e3a3-174">特定の日付からイベントをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="9e3a3-175">表の左上にあるカレンダー アイコンを選択して、過去の日、週、30 日、またはカスタム範囲のイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="9e3a3-176">既定では、デバイスタイムラインは過去 30 日間のイベントを表示するために設定されています。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="9e3a3-177">タイムラインを使用して、セクションを強調表示して特定の時間にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="9e3a3-178">タイムライン上の矢印は、自動化された調査を特定します</span><span class="sxs-lookup"><span data-stu-id="9e3a3-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="9e3a3-179">デバイスの詳細なタイムライン イベントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="9e3a3-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="9e3a3-180">現在の日付または指定した日付範囲のデバイス タイムラインを最大 7 日間エクスポートします。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="9e3a3-181">特定のイベントの詳細については、「追加情報」 **セクションを参照** してください。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="9e3a3-182">これらの詳細は、次に示すイベントの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="9e3a3-183">Application Guard に含まれる - Web ブラウザー イベントは、分離されたコンテナーによって制限されました</span><span class="sxs-lookup"><span data-stu-id="9e3a3-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="9e3a3-184">アクティブな脅威が検出されました - 脅威の実行中に脅威の検出が発生しました</span><span class="sxs-lookup"><span data-stu-id="9e3a3-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="9e3a3-185">修復に失敗しました - 検出された脅威を修復しようとしたが、失敗しました</span><span class="sxs-lookup"><span data-stu-id="9e3a3-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="9e3a3-186">修復が成功しました - 検出された脅威が停止してクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="9e3a3-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="9e3a3-187">ユーザーによってバイパスされた警告 - SmartScreen Windows Defenderが無視され、ユーザーによって上書きされた場合</span><span class="sxs-lookup"><span data-stu-id="9e3a3-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="9e3a3-188">疑わしいスクリプトが検出されました - 悪意のある可能性のあるスクリプトが実行されているのが見つかりました</span><span class="sxs-lookup"><span data-stu-id="9e3a3-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="9e3a3-189">アラート カテゴリ - イベントがアラートの生成につながった場合、アラート カテゴリ (たとえば"横方向の移動") が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="9e3a3-190">イベントの詳細</span><span class="sxs-lookup"><span data-stu-id="9e3a3-190">Event details</span></span>
<span data-ttu-id="9e3a3-191">イベントを選択して、そのイベントに関する関連する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="9e3a3-192">一般的なイベント情報を表示するパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-192">A panel displays to show general event information.</span></span> <span data-ttu-id="9e3a3-193">適用可能なデータが使用可能な場合は、関連するエンティティとその関係を示すグラフも表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="9e3a3-194">イベントと関連イベントをさらに調するには、[関連イベントのハント][](advanced-hunting-overview.md)を選択して高度な検索クエリ **をすばやく実行できます**。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="9e3a3-195">クエリは、選択したイベントと、同じエンドポイントで同時に発生した他のイベントの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![イベントの詳細パネルのイメージ](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="9e3a3-197">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="9e3a3-197">Security recommendations</span></span>

<span data-ttu-id="9e3a3-198">**セキュリティに関する推奨事項** は、Microsoft Defender for Endpoint の Threat & [管理機能から生成](tvm-dashboard-insights.md) されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="9e3a3-199">推奨事項を選択すると、推奨事項の説明や、推奨事項の制定に関連する潜在的なリスクなどの関連する詳細を表示できるパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="9e3a3-200">詳細については [、「セキュリティに関する推奨事項](tvm-security-recommendation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![[セキュリティの推奨事項] タブの画像](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="9e3a3-202">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="9e3a3-202">Software inventory</span></span>

<span data-ttu-id="9e3a3-203">[ **ソフトウェア インベントリ]** タブでは、デバイス上のソフトウェアと、弱点や脅威を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="9e3a3-204">ソフトウェアの名前を選択すると、ソフトウェアの詳細ページに移動し、セキュリティの推奨事項、検出された脆弱性、インストールされているデバイス、およびバージョン配布を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="9e3a3-205">詳細については [、「ソフトウェア インベントリ」](tvm-software-inventory.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![[ソフトウェア インベントリ] タブのイメージ](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="9e3a3-207">検出された脆弱性</span><span class="sxs-lookup"><span data-stu-id="9e3a3-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="9e3a3-208">[ **検出された脆弱性]** タブには、デバイスで検出された脆弱性の名前、重大度、および脅威の分析情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="9e3a3-209">特定の脆弱性を選択すると、説明と詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![[検出された脆弱性] タブの画像](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="9e3a3-211">不足している KB</span><span class="sxs-lookup"><span data-stu-id="9e3a3-211">Missing KBs</span></span>
<span data-ttu-id="9e3a3-212">[ **不足している KB]** タブには、デバイスの不足しているセキュリティ更新プログラムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![不足している kbs タブのイメージ](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="9e3a3-214">カード</span><span class="sxs-lookup"><span data-stu-id="9e3a3-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="9e3a3-215">アクティブなアラート</span><span class="sxs-lookup"><span data-stu-id="9e3a3-215">Active alerts</span></span>

<span data-ttu-id="9e3a3-216">Azure Advanced **Threat Protection** カードには、Azure ATP 機能を有効にし、アクティブなアラートがある場合、デバイスとそのリスク レベルに関連するアラートの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Azure ATP feature, and there are any active alerts.</span></span> <span data-ttu-id="9e3a3-217">詳細については、「アラート」ドリルダウンで確認できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-217">More information is available in the "Alerts" drill down.</span></span>

![アクティブなアラート カードのイメージ](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="9e3a3-219">この機能を使用するには、Azure ATP と Defender for Endpoint の両方で統合を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-219">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="9e3a3-220">Defender for Endpoint では、高度な機能でこの機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="9e3a3-221">高度な機能を有効にする方法の詳細については、「高度な機能を有効 [にする」を参照してください](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="9e3a3-222">ログオンしているユーザー</span><span class="sxs-lookup"><span data-stu-id="9e3a3-222">Logged on users</span></span>

<span data-ttu-id="9e3a3-223">[ **ログオンユーザー] カード** には、過去 30 日間にログオンしたユーザーの数と、最も頻度の少ないユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="9e3a3-224">[すべてのユーザーを表示する] リンクを選択すると、詳細ウィンドウが開き、ユーザーの種類、ログオンの種類、ユーザーが最初と最後に表示された時間などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="9e3a3-225">詳細については、「ユーザー エンティティの [調査」を参照してください](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![ユーザーの詳細ウィンドウのイメージ](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="9e3a3-227">セキュリティ評価</span><span class="sxs-lookup"><span data-stu-id="9e3a3-227">Security assessments</span></span>

<span data-ttu-id="9e3a3-228">セキュリティ **評価カードには** 、全体的な露出レベル、セキュリティ推奨事項、インストール済みソフトウェア、および検出された脆弱性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="9e3a3-229">デバイスの露出レベルは、保留中のセキュリティ推奨事項の累積的な影響によって決まります。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![セキュリティ評価カードのイメージ](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="9e3a3-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e3a3-231">Related topics</span></span>

- [<span data-ttu-id="9e3a3-232">Microsoft Defender for Endpoint Alerts キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="9e3a3-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="9e3a3-233">エンドポイント通知の Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="9e3a3-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="9e3a3-234">Microsoft Defender for Endpoint アラートの調査</span><span class="sxs-lookup"><span data-stu-id="9e3a3-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="9e3a3-235">Defender for Endpoint アラートに関連付けられたファイルを調査する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="9e3a3-236">Defender for Endpoint アラートに関連付けられている IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="9e3a3-237">Defender for Endpoint アラートに関連付けられているドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="9e3a3-238">Defender for Endpoint のユーザー アカウントを調査する</span><span class="sxs-lookup"><span data-stu-id="9e3a3-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="9e3a3-239">セキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="9e3a3-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="9e3a3-240">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="9e3a3-240">Software inventory</span></span>](tvm-software-inventory.md)
