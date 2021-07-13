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
ms.openlocfilehash: c89de5fbf5d5b4d5d5e53074109bc8884a271eea
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394895"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="d466c-104">Microsoft Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="d466c-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d466c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d466c-105">**Applies to:**</span></span>
- [<span data-ttu-id="d466c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d466c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d466c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d466c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d466c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d466c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d466c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d466c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="d466c-110">特定のデバイスで発生したアラートの詳細を調べて、アラートまたは侵害の潜在的な範囲に関連する可能性のある他の動作またはイベントを特定します。</span><span class="sxs-lookup"><span data-stu-id="d466c-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="d466c-111">調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。</span><span class="sxs-lookup"><span data-stu-id="d466c-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="d466c-112">次の方法: デバイスから [調査パッケージを収集します](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)。</span><span class="sxs-lookup"><span data-stu-id="d466c-112">Here's how: [Collect investigation package from devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="d466c-113">影響を受けるデバイスをポータルに表示するたびにクリックすると、そのデバイスに関する詳細なレポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="d466c-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="d466c-114">影響を受けるデバイスは、次の領域で識別されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="d466c-115">デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="d466c-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="d466c-116">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="d466c-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="d466c-117">セキュリティ運用ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="d466c-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="d466c-118">個々のアラート</span><span class="sxs-lookup"><span data-stu-id="d466c-118">Any individual alert</span></span>
- <span data-ttu-id="d466c-119">個々のファイルの詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="d466c-119">Any individual file details view</span></span>
- <span data-ttu-id="d466c-120">任意の IP アドレスまたはドメインの詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="d466c-120">Any IP address or domain details view</span></span>

<span data-ttu-id="d466c-121">特定のデバイスを調査すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="d466c-122">デバイスの詳細</span><span class="sxs-lookup"><span data-stu-id="d466c-122">Device details</span></span>
- <span data-ttu-id="d466c-123">応答アクション</span><span class="sxs-lookup"><span data-stu-id="d466c-123">Response actions</span></span>
- <span data-ttu-id="d466c-124">タブ (概要、アラート、タイムライン、セキュリティ推奨事項、ソフトウェア インベントリ、検出された脆弱性、不足している KB)</span><span class="sxs-lookup"><span data-stu-id="d466c-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="d466c-125">カード (アクティブなアラート、ログオンしているユーザー、セキュリティ評価)</span><span class="sxs-lookup"><span data-stu-id="d466c-125">Cards (active alerts, logged on users, security assessment)</span></span>

![デバイス ビューのイメージ](images/specific-device.png)

> [!NOTE]
> <span data-ttu-id="d466c-127">製品の制約により、デバイス プロファイルは 、(デバイス ページにも見られる) 'Last Seen' 時間枠を決定する際に、すべてのサイバー証拠を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d466c-127">Due to product constrains, the device profile does not consider all cyber evidence when determining the 'Last Seen' timeframe (as seen on the device page as well).</span></span>
> <span data-ttu-id="d466c-128">たとえば、[デバイス] ページの [最後に見た] 値は、コンピューターのタイムラインで最新のアラートやデータを使用できる場合でも、古い時間枠を表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d466c-128">For example, the 'Last seen' value in the Device page may show an older time frame even though more recent alerts or data is available in the machine's timeline.</span></span>

## <a name="device-details"></a><span data-ttu-id="d466c-129">デバイスの詳細</span><span class="sxs-lookup"><span data-stu-id="d466c-129">Device details</span></span>

<span data-ttu-id="d466c-130">[デバイスの詳細] セクションには、デバイスのドメイン、OS、正常性状態などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-130">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="d466c-131">デバイスで利用可能な調査パッケージがある場合は、パッケージをダウンロードできるリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-131">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="d466c-132">応答アクション</span><span class="sxs-lookup"><span data-stu-id="d466c-132">Response actions</span></span>

<span data-ttu-id="d466c-133">応答アクションは、特定のデバイス ページの上部に沿って実行され、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d466c-133">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="d466c-134">タグの管理</span><span class="sxs-lookup"><span data-stu-id="d466c-134">Manage tags</span></span>
- <span data-ttu-id="d466c-135">デバイスの分離</span><span class="sxs-lookup"><span data-stu-id="d466c-135">Isolate device</span></span>
- <span data-ttu-id="d466c-136">アプリの実行を制限する</span><span class="sxs-lookup"><span data-stu-id="d466c-136">Restrict app execution</span></span>
- <span data-ttu-id="d466c-137">ウイルス対策スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="d466c-137">Run antivirus scan</span></span>
- <span data-ttu-id="d466c-138">調査パッケージの収集</span><span class="sxs-lookup"><span data-stu-id="d466c-138">Collect investigation package</span></span>
- <span data-ttu-id="d466c-139">ライブ応答セッションの開始</span><span class="sxs-lookup"><span data-stu-id="d466c-139">Initiate Live Response Session</span></span>
- <span data-ttu-id="d466c-140">自動調査の開始</span><span class="sxs-lookup"><span data-stu-id="d466c-140">Initiate automated investigation</span></span>
- <span data-ttu-id="d466c-141">脅威のエキスパートに相談する</span><span class="sxs-lookup"><span data-stu-id="d466c-141">Consult a threat expert</span></span>
- <span data-ttu-id="d466c-142">アクション センター</span><span class="sxs-lookup"><span data-stu-id="d466c-142">Action center</span></span>

<span data-ttu-id="d466c-143">アクション センター、特定のデバイス ページ、または特定のファイル ページで応答アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d466c-143">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="d466c-144">デバイスでアクションを実行する方法の詳細については、「デバイスで応答アクションを実行 [する」を参照してください](respond-machine-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="d466c-144">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="d466c-145">詳細については、「ユーザー エンティティの [調査」を参照してください](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d466c-145">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="d466c-146">タブ</span><span class="sxs-lookup"><span data-stu-id="d466c-146">Tabs</span></span>

<span data-ttu-id="d466c-147">タブには、デバイスに関連する関連するセキュリティと脅威防止情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-147">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="d466c-148">各タブで、列ヘッダーの上のバーから [列のカスタマイズ] を選択して、表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d466c-148">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="d466c-149">概要</span><span class="sxs-lookup"><span data-stu-id="d466c-149">Overview</span></span>
<span data-ttu-id="d466c-150">[ **概要]** タブには、アクティブ [なアラート](#cards) 、ログオンしているユーザー、およびセキュリティ評価のカードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-150">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![デバイス ページの [概要] タブのイメージ](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="d466c-152">アラート</span><span class="sxs-lookup"><span data-stu-id="d466c-152">Alerts</span></span>

<span data-ttu-id="d466c-153">[ **アラート]** タブには、デバイスに関連付けられているアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-153">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="d466c-154">このリストは、アラート キューのフィルター[](alerts-queue.md)処理されたバージョンで、アラート、重大度 (高、中、低、情報)、キュー内の状態 (新規、進行中、解決済み)、分類 (設定されていない、誤ったアラート、真のアラート)、調査状態、アラートのカテゴリ、アラートに対処しているユーザー、および最後のアクティビティの短い説明を示します。</span><span class="sxs-lookup"><span data-stu-id="d466c-154">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="d466c-155">アラートをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d466c-155">You can also filter the alerts.</span></span>

![デバイスに関連するアラートのイメージ](images/alerts-device.png)

<span data-ttu-id="d466c-157">アラートの左側にある円のアイコンが選択されている場合は、フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-157">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="d466c-158">このパネルでは、アラートを管理し、インシデント番号や関連デバイスなどの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d466c-158">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="d466c-159">一度に複数のアラートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d466c-159">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="d466c-160">インシデント グラフやプロセス ツリーを含むアラートの完全なページ ビューを表示するには、アラートのタイトルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d466c-160">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="d466c-161">タイムライン</span><span class="sxs-lookup"><span data-stu-id="d466c-161">Timeline</span></span>

<span data-ttu-id="d466c-162">[ **タイムライン]** タブには、デバイスで観測されたイベントと関連するアラートの時系列ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-162">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="d466c-163">これにより、デバイスに関連するイベント、ファイル、IP アドレスを関連付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d466c-163">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="d466c-164">タイムラインでは、特定の期間に発生したイベントを選択的にドリルダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d466c-164">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="d466c-165">選択した期間にデバイスで発生したイベントの一時的なシーケンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d466c-165">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="d466c-166">ビューをさらに制御するには、イベント グループでフィルター処理するか、列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d466c-166">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="d466c-167">ファイアウォール イベントを表示するには、監査ポリシーを有効にする必要があります。「Audit [Filtering Platform 接続」を参照してください](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)。</span><span class="sxs-lookup"><span data-stu-id="d466c-167">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="d466c-168">ファイアウォールは、次のイベントをカバーします。</span><span class="sxs-lookup"><span data-stu-id="d466c-168">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="d466c-169">[5025](/windows/security/threat-protection/auditing/event-5025) - ファイアウォール サービスが停止しました</span><span class="sxs-lookup"><span data-stu-id="d466c-169">[5025](/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="d466c-170">[5031](/windows/security/threat-protection/auditing/event-5031) - アプリケーションがネットワーク上の受信接続を受け入れるのをブロックする</span><span class="sxs-lookup"><span data-stu-id="d466c-170">[5031](/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="d466c-171">[5157](/windows/security/threat-protection/auditing/event-5157) - ブロックされた接続</span><span class="sxs-lookup"><span data-stu-id="d466c-171">[5157](/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![イベントを含むデバイス タイムラインのイメージ](images/timeline-device.png)

<span data-ttu-id="d466c-173&quot;>一部の機能には、次の機能が含まれます。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-173&quot;>Some of the functionality includes:</span></span>

- <span data-ttu-id=&quot;d466c-174&quot;>特定のイベントを検索する</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-174&quot;>Search for specific events</span></span>
  - <span data-ttu-id=&quot;d466c-175&quot;>検索バーを使用して、特定のタイムライン イベントを検索します。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-175&quot;>Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id=&quot;d466c-176&quot;>特定の日付からイベントをフィルター処理する</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-176&quot;>Filter events from a specific date</span></span>
  - <span data-ttu-id=&quot;d466c-177&quot;>表の左上にあるカレンダー アイコンを選択して、過去の日、週、30 日、またはカスタム範囲のイベントを表示します。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-177&quot;>Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id=&quot;d466c-178&quot;>既定では、デバイスタイムラインは過去 30 日間のイベントを表示するために設定されています。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-178&quot;>By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id=&quot;d466c-179&quot;>タイムラインを使用して、セクションを強調表示して特定の時間にジャンプします。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-179&quot;>Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id=&quot;d466c-180&quot;>タイムライン上の矢印は、自動化された調査を特定します</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-180&quot;>The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id=&quot;d466c-181&quot;>デバイスの詳細なタイムライン イベントをエクスポートする</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-181&quot;>Export detailed device timeline events</span></span>
  - <span data-ttu-id=&quot;d466c-182&quot;>現在の日付または指定した日付範囲のデバイス タイムラインを最大 7 日間エクスポートします。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-182&quot;>Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id=&quot;d466c-183&quot;>特定のイベントの詳細については、「追加情報」 **セクションを参照** してください。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-183&quot;>More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id=&quot;d466c-184&quot;>これらの詳細は、次に示すイベントの種類によって異なります。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-184&quot;>These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id=&quot;d466c-185&quot;>Application Guard に含まれる - Web ブラウザー イベントは、分離されたコンテナーによって制限されました</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-185&quot;>Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id=&quot;d466c-186&quot;>アクティブな脅威が検出されました - 脅威の実行中に脅威の検出が発生しました</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-186&quot;>Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id=&quot;d466c-187&quot;>修復に失敗しました - 検出された脅威を修復しようとしたが、失敗しました</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-187&quot;>Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id=&quot;d466c-188&quot;>修復が成功しました - 検出された脅威が停止してクリーンアップされました</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-188&quot;>Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id=&quot;d466c-189&quot;>ユーザーによってバイパスされた警告 - SmartScreen Windows Defenderが無視され、ユーザーによって上書きされた場合</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-189&quot;>Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id=&quot;d466c-190&quot;>疑わしいスクリプトが検出されました - 悪意のある可能性のあるスクリプトが実行されているのが見つかりました</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;d466c-190&quot;>Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id=&quot;d466c-191&quot;>アラート カテゴリ - イベントがアラートの生成につながった場合、アラート カテゴリ (たとえば&quot;横方向の移動") が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-191">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="d466c-192">イベントの詳細</span><span class="sxs-lookup"><span data-stu-id="d466c-192">Event details</span></span>
<span data-ttu-id="d466c-193">イベントを選択して、そのイベントに関する関連する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="d466c-193">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="d466c-194">一般的なイベント情報を表示するパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-194">A panel displays to show general event information.</span></span> <span data-ttu-id="d466c-195">適用可能なデータが使用可能な場合は、関連するエンティティとその関係を示すグラフも表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-195">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="d466c-196">イベントと関連イベントをさらに調するには、[関連イベントのハント][](advanced-hunting-overview.md)を選択して高度な検索クエリ **をすばやく実行できます**。</span><span class="sxs-lookup"><span data-stu-id="d466c-196">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="d466c-197">クエリは、選択したイベントと、同じエンドポイントで同時に発生した他のイベントの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="d466c-197">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![イベントの詳細パネルのイメージ](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="d466c-199">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="d466c-199">Security recommendations</span></span>

<span data-ttu-id="d466c-200">**セキュリティに関する推奨事項** は、Microsoft Defender for Endpoint の Threat & [管理機能から生成](tvm-dashboard-insights.md) されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-200">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="d466c-201">推奨事項を選択すると、推奨事項の説明や、推奨事項の制定に関連する潜在的なリスクなどの関連する詳細を表示できるパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-201">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="d466c-202">詳細については [、「セキュリティに関する推奨事項](tvm-security-recommendation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d466c-202">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![[セキュリティの推奨事項] タブの画像](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="d466c-204">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="d466c-204">Software inventory</span></span>

<span data-ttu-id="d466c-205">[ **ソフトウェア インベントリ]** タブでは、デバイス上のソフトウェアと、弱点や脅威を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d466c-205">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="d466c-206">ソフトウェアの名前を選択すると、ソフトウェアの詳細ページに移動し、セキュリティの推奨事項、検出された脆弱性、インストールされているデバイス、およびバージョン配布を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d466c-206">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="d466c-207">詳細については [、「ソフトウェア インベントリ」](tvm-software-inventory.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d466c-207">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![[ソフトウェア インベントリ] タブのイメージ](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="d466c-209">検出された脆弱性</span><span class="sxs-lookup"><span data-stu-id="d466c-209">Discovered vulnerabilities</span></span>

<span data-ttu-id="d466c-210">[ **検出された脆弱性]** タブには、デバイスで検出された脆弱性の名前、重大度、および脅威の分析情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-210">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="d466c-211">特定の脆弱性を選択すると、説明と詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-211">Selecting specific vulnerabilities will show a description and details.</span></span>

![[検出された脆弱性] タブの画像](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="d466c-213">不足している KB</span><span class="sxs-lookup"><span data-stu-id="d466c-213">Missing KBs</span></span>
<span data-ttu-id="d466c-214">[ **不足している KB]** タブには、デバイスの不足しているセキュリティ更新プログラムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-214">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![不足している kbs タブのイメージ](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="d466c-216">カード</span><span class="sxs-lookup"><span data-stu-id="d466c-216">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="d466c-217">アクティブなアラート</span><span class="sxs-lookup"><span data-stu-id="d466c-217">Active alerts</span></span>

<span data-ttu-id="d466c-218">Microsoft Defender for Identity 機能を有効にし、アクティブなアラートがある場合、Azure Advanced **Threat Protection** カードには、デバイスとそのリスク レベルに関連するアラートの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-218">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="d466c-219">詳細については、「アラート」ドリルダウンで確認できます。</span><span class="sxs-lookup"><span data-stu-id="d466c-219">More information is available in the "Alerts" drill down.</span></span>

![アクティブなアラート カードのイメージ](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="d466c-221">この機能を使用するには、Microsoft Defender for Identity と Defender for Endpoint の両方で統合を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d466c-221">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="d466c-222">Defender for Endpoint では、高度な機能でこの機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d466c-222">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="d466c-223">高度な機能を有効にする方法の詳細については、「高度な機能を有効 [にする」を参照してください](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="d466c-223">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="d466c-224">ログオンしているユーザー</span><span class="sxs-lookup"><span data-stu-id="d466c-224">Logged on users</span></span>

<span data-ttu-id="d466c-225">[ **ログオンユーザー] カード** には、過去 30 日間にログオンしたユーザーの数と、最も頻度の少ないユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-225">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="d466c-226">[すべてのユーザーを表示する] リンクを選択すると、詳細ウィンドウが開き、ユーザーの種類、ログオンの種類、ユーザーが最初と最後に表示された時間などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-226">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="d466c-227">詳細については、「ユーザー エンティティの [調査」を参照してください](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d466c-227">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![ユーザーの詳細ウィンドウのイメージ](images/logged-on-users.png)
> [!NOTE]
> <span data-ttu-id="d466c-229">「最も頻繁に」ユーザー値は、対話的に正常にログオンしたユーザーの証拠にのみ基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-229">The 'Most frequent' user value is calculated only based on evidence of users who successfully logged on interactively.</span></span> <span data-ttu-id="d466c-230">ただし、[すべてのユーザー] サイド ウィンドウでは、すべての種類のユーザー ログオンが計算されます。そのため、ユーザーが対話型ではない可能性がある場合に、サイド ウィンドウでユーザーが頻繁に表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d466c-230">However, the "All users" side-pane calculates all sorts of user logons so it is expected to see more frequent users in the side-pane, given that those users may not be interactive.</span></span>

### <a name="security-assessments"></a><span data-ttu-id="d466c-231">セキュリティ評価</span><span class="sxs-lookup"><span data-stu-id="d466c-231">Security assessments</span></span>

<span data-ttu-id="d466c-232">セキュリティ **評価カードには** 、全体的な露出レベル、セキュリティ推奨事項、インストール済みソフトウェア、および検出された脆弱性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d466c-232">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="d466c-233">デバイスの露出レベルは、保留中のセキュリティ推奨事項の累積的な影響によって決まります。</span><span class="sxs-lookup"><span data-stu-id="d466c-233">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![セキュリティ評価カードのイメージ](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="d466c-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="d466c-235">Related topics</span></span>

- [<span data-ttu-id="d466c-236">Microsoft Defender for Endpoint アラート キューを表示して整理する</span><span class="sxs-lookup"><span data-stu-id="d466c-236">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="d466c-237">エンドポイント通知の Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="d466c-237">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="d466c-238">Microsoft Defender for Endpoint アラートの調査</span><span class="sxs-lookup"><span data-stu-id="d466c-238">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="d466c-239">Defender for Endpoint アラートに関連付けられたファイルを調査する</span><span class="sxs-lookup"><span data-stu-id="d466c-239">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="d466c-240">Defender for Endpoint アラートに関連付けられている IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="d466c-240">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="d466c-241">Defender for Endpoint アラートに関連付けられているドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="d466c-241">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="d466c-242">Defender for Endpoint のユーザー アカウントを調査する</span><span class="sxs-lookup"><span data-stu-id="d466c-242">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="d466c-243">セキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="d466c-243">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="d466c-244">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="d466c-244">Software inventory</span></span>](tvm-software-inventory.md)
