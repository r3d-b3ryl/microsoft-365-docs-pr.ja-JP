---
title: Microsoft 365 セキュリティ ポータルのデバイス プロファイル
description: 組織内のデバイスのリスクと露出レベルを表示します。 過去および現在の脅威を分析し、最新の更新プログラムを使用してデバイスを保護します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、Microsoft 365 Defender、セキュリティ センター、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、デバイス ページ、デバイス プロファイル、コンピューター ページ、コンピューター プロファイル
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 8e2788fd9163a27b41bd3788facf5fc9623b0543
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935667"
---
# <a name="device-profile-page"></a><span data-ttu-id="916fd-105">[デバイス プロファイル] ページ</span><span class="sxs-lookup"><span data-stu-id="916fd-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="916fd-106">Microsoft 365 セキュリティ ポータルでは、デバイス プロファイル ページが提供され、ネットワーク上のデバイスの正常性と状態をすばやく評価できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="916fd-107">デバイス プロファイル ページは、デバイスが Microsoft Defender for Endpoint、Microsoft Defender for Identity、または両方に登録されているかどうかによって、若干異なって表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="916fd-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="916fd-108">デバイスが Microsoft Defender for Endpoint に登録されている場合は、デバイス プロファイル ページを使用して一般的なセキュリティ タスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="916fd-109">デバイス プロファイル ページの移動</span><span class="sxs-lookup"><span data-stu-id="916fd-109">Navigating the device profile page</span></span>

<span data-ttu-id="916fd-110">プロファイル ページは、いくつかの広範なセクションに分割されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-110">The profile page is broken up into several broad sections.</span></span>

![(1) タブ領域 (2) サイドバーと (3) アクションが赤色で強調表示されたデバイス プロファイル ページのイメージ](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="916fd-112">サイドバー (1) には、デバイスに関する基本的な詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="916fd-113">メイン コンテンツ領域 (2) には、デバイスに関するさまざまな種類の情報を表示するために切り替え可能なタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="916fd-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="916fd-114">デバイスが Microsoft Defender for Endpoint に登録されている場合は、応答アクションの一覧 (3) も表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="916fd-115">応答アクションを使用すると、一般的なセキュリティ関連のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="916fd-116">サイドバー</span><span class="sxs-lookup"><span data-stu-id="916fd-116">Sidebar</span></span>

<span data-ttu-id="916fd-117">デバイス プロファイル ページのメイン コンテンツ領域の横にサイドバーがあります。</span><span class="sxs-lookup"><span data-stu-id="916fd-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![デバイス プロファイルのサイドバー タブのイメージ](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="916fd-119">サイドバーには、デバイスの完全な名前と露出レベルが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="916fd-120">また、次のような、開くまたは閉じ切り替えできる小さなサブセクションの重要な基本情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="916fd-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="916fd-121">**タグ** - デバイスに関連付けられた Microsoft Defender for Endpoint、Microsoft Defender for Identity、またはカスタム タグ。</span><span class="sxs-lookup"><span data-stu-id="916fd-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="916fd-122">Microsoft Defender for Identity のタグは編集できません。</span><span class="sxs-lookup"><span data-stu-id="916fd-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="916fd-123">**セキュリティ情報** - インシデントとアクティブなアラートを開きます。</span><span class="sxs-lookup"><span data-stu-id="916fd-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="916fd-124">Microsoft Defender for Endpoint に登録されているデバイスには、露出レベルとリスク レベルも表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="916fd-125">露出レベルは、デバイスがセキュリティ推奨事項に準拠している量に関連しますが、リスク レベルはアクティブなアラートの種類や重大度など、さまざまな要因に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="916fd-126">**デバイスの詳細** - ドメイン、OS、デバイスが最初に表示された時刻のタイムスタンプ、IP アドレス、リソース。</span><span class="sxs-lookup"><span data-stu-id="916fd-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="916fd-127">Microsoft Defender for Endpoint に登録されているデバイスにも正常性状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="916fd-128">Microsoft Defender for Identity に登録されているデバイスには、デバイスが最初に作成された時刻の SAM 名とタイムスタンプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="916fd-129">**ネットワーク アクティビティ** - デバイスがネットワーク上で初めて、最後に表示されたタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="916fd-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="916fd-130">\**ディレクトリ データ\*\*\*(Microsoft Defender for Identity* に登録されているデバイスの場合のみ) - UAC フラグ [、SPN、](/windows/win32/ad/service-principal-names)およびグループ メンバーシップ。 [](/windows/security/identity-protection/user-account-control/user-account-control-overview)</span><span class="sxs-lookup"><span data-stu-id="916fd-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="916fd-131">応答アクション</span><span class="sxs-lookup"><span data-stu-id="916fd-131">Response actions</span></span>

<span data-ttu-id="916fd-132">応答アクションは、脅威に対する防御と分析を迅速に行う方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="916fd-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![デバイス プロファイルのアクション バーのイメージ](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="916fd-134">[応答アクション](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) は、デバイスが Microsoft Defender for Endpoint に登録されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-134">[Response actions](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="916fd-135">Microsoft Defender for Endpoint に登録されているデバイスでは、デバイスの OS とバージョン番号に基づいて、応答アクションの数が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="916fd-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="916fd-136">デバイス プロファイル ページで使用できるアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="916fd-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="916fd-137">**タグの管理** - このデバイスに適用したカスタム タグを更新します。</span><span class="sxs-lookup"><span data-stu-id="916fd-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="916fd-138">**デバイスの分離** - デバイスを Microsoft Defender for Endpoint に接続しながら、組織のネットワークからデバイスを分離します。</span><span class="sxs-lookup"><span data-stu-id="916fd-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="916fd-139">通信の目的で、デバイスの分離中に Outlook、Teams、Skype for Business の実行を許可できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="916fd-140">**アクション センター** - 送信されたアクションの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="916fd-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="916fd-141">別のアクションが既に選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="916fd-142">**アプリの実行を制限** する - Microsoft によって署名されていないアプリケーションが実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="916fd-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="916fd-143">**ウイルス対策スキャンの実行** - ウイルスWindows Defender定義を更新し、すぐにウイルス対策スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="916fd-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="916fd-144">[クイック スキャン] または [フル スキャン] の間で選択します。</span><span class="sxs-lookup"><span data-stu-id="916fd-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="916fd-145">**調査パッケージの収集** - デバイスに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="916fd-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="916fd-146">調査が完了したら、ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="916fd-147">**ライブ応答セッションの開始** - デバイスにリモート シェルを読み込んで、詳細なセキュリティ [調査を行います](/microsoft-365/security/defender-endpoint/live-response)。</span><span class="sxs-lookup"><span data-stu-id="916fd-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](/microsoft-365/security/defender-endpoint/live-response).</span></span>
* <span data-ttu-id="916fd-148">**自動調査の開始** - 脅威 [を自動的に調査および修復します](../office-365-security/office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="916fd-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](../office-365-security/office-365-air.md).</span></span> <span data-ttu-id="916fd-149">このページから自動調査を手動で実行することもできますが、特定のアラート[](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies)ポリシーによって独自に自動調査がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="916fd-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="916fd-150">**アクション センター** - 現在実行中の応答アクションに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="916fd-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="916fd-151">[タブ] セクション</span><span class="sxs-lookup"><span data-stu-id="916fd-151">Tabs section</span></span>

<span data-ttu-id="916fd-152">デバイス プロファイル タブを使用すると、デバイスに関するセキュリティの詳細と、アラートの一覧を含むテーブルの概要を切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="916fd-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="916fd-153">Microsoft Defender for Endpoint に登録されているデバイスには、タイムライン、セキュリティ推奨事項の一覧、ソフトウェア インベントリ、検出された脆弱性の一覧、および不足している KB (セキュリティ更新プログラム) を備えたタブも表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="916fd-154">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="916fd-154">Overview tab</span></span>

<span data-ttu-id="916fd-155">既定のタブは [概要] **です**。</span><span class="sxs-lookup"><span data-stu-id="916fd-155">The default tab is **Overview**.</span></span> <span data-ttu-id="916fd-156">デバイスに関する最も重要なセキュリティの事実を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-156">It provides a quick look at the most important security fact about the device.</span></span>

![デバイス プロファイルの [概要] タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="916fd-158">ここでは、デバイスのアクティブなアラートと、現在ログオンしているユーザーを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="916fd-159">デバイスが Microsoft Defender for Endpoint に登録されている場合は、デバイスのリスク レベルと、セキュリティ評価に関して利用可能なデータも表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="916fd-160">セキュリティ評価では、デバイスの露出レベルを説明し、セキュリティに関する推奨事項を提供し、影響を受けるソフトウェアと検出された脆弱性を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="916fd-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="916fd-161">[通知] タブ</span><span class="sxs-lookup"><span data-stu-id="916fd-161">Alerts tab</span></span>

<span data-ttu-id="916fd-162">[ **アラート]** タブには、Microsoft Defender for Identity と Microsoft Defender for Endpoint の両方から、デバイスで発生したアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![デバイス プロファイルの [アラート] タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="916fd-164">表示されるアイテムの数と、各アイテムに対して表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="916fd-165">既定の動作では、ページごとに 30 アイテムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="916fd-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="916fd-166">このタブの列には、アラートをトリガーした脅威の重大度、および状態、調査状態、アラートが割り当てられているユーザーに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="916fd-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="916fd-167">[ *影響を受けるエンティティ* ] 列は、現在表示されているプロファイルと、影響を受けるネットワーク内の他のデバイスを含むデバイス (エンティティ) を参照します。</span><span class="sxs-lookup"><span data-stu-id="916fd-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="916fd-168">このリストからアイテムを選択すると、選択したアラートに関するさらに詳しい情報を含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="916fd-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="916fd-169">このリストは、重大度、状態、またはアラートが割り当てられているユーザーによってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="916fd-170">[タイムライン] タブ</span><span class="sxs-lookup"><span data-stu-id="916fd-170">Timeline tab</span></span>

<span data-ttu-id="916fd-171">[ **タイムライン]** タブには、デバイスで発生したすべてのイベントの対話型の時系列グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="916fd-172">グラフの強調表示された領域を左または右に移動すると、さまざまな期間のイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="916fd-173">また、対話型グラフとイベントの一覧の間にあるドロップダウン メニューから、日付のカスタム範囲を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="916fd-174">グラフの下には、選択した日付範囲のイベントの一覧があります。</span><span class="sxs-lookup"><span data-stu-id="916fd-174">Below the chart is a list of events for the selected range of dates.</span></span>

![デバイス プロファイルの [タイムライン] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="916fd-176">表示されるアイテムの数とリストの列の両方をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="916fd-177">既定の列には、イベント時間、アクティブ ユーザー、アクションの種類、エンティティ (プロセス)、およびイベントに関する追加情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="916fd-178">このリストからアイテムを選択すると、イベントに関係する親プロセスと子プロセスを示すイベント エンティティ グラフが表示されるフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="916fd-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="916fd-179">リストは、特定の種類のイベントでフィルター処理できます。たとえば、レジストリ イベントやスマート スクリーン イベントなどです。</span><span class="sxs-lookup"><span data-stu-id="916fd-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="916fd-180">リストは、ダウンロード用に CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="916fd-181">ファイルはイベントの数によって制限されるのではなく、エクスポートできる最大時間範囲は 7 日間です。</span><span class="sxs-lookup"><span data-stu-id="916fd-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="916fd-182">[セキュリティの推奨事項] タブ</span><span class="sxs-lookup"><span data-stu-id="916fd-182">Security recommendations tab</span></span>

<span data-ttu-id="916fd-183">[ **セキュリティの推奨事項] タブ** には、デバイスを保護するために実行できるアクションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="916fd-184">このリストでアイテムを選択すると、提案の適用方法に関する手順を取得できるフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="916fd-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![デバイス プロファイルの [セキュリティの推奨事項] タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="916fd-186">前のタブと同様に、ページごとに表示されるアイテムの数と表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="916fd-187">既定のビューには、対応するセキュリティの弱点、関連する脅威、脅威の影響を受ける関連コンポーネントまたはソフトウェアなどについて詳しく説明する列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="916fd-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="916fd-188">アイテムは、推奨事項の状態によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="916fd-189">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="916fd-189">Software inventory</span></span>

<span data-ttu-id="916fd-190">[ **ソフトウェア インベントリ] タブ** には、デバイスにインストールされているソフトウェアが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-190">The **Software inventory** tab lists software installed on the device.</span></span>

![デバイス プロファイルの [ソフトウェア インベントリ] タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="916fd-192">既定のビューには、ソフトウェア ベンダー、インストールされているバージョン番号、既知のソフトウェアの弱点の数、脅威の分析情報、製品コード、およびタグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="916fd-193">表示されるアイテムの数と表示される列の両方をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="916fd-194">このリストからアイテムを選択すると、選択したソフトウェアの詳細と、ソフトウェアが最後に見つかった時点のパスとタイムスタンプを含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="916fd-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="916fd-195">このリストは、製品コードでフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="916fd-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="916fd-196">[検出された脆弱性] タブ</span><span class="sxs-lookup"><span data-stu-id="916fd-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="916fd-197">[ **検出された脆弱性] タブ** には、デバイスに影響を与える可能性のある一般的な脆弱性と悪用 (CVEs) が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![デバイス プロファイルの [検出された脆弱性] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="916fd-199">既定のビューには、CVE の重大度、共通の脆弱性スコア (CVS)、CVE に関連するソフトウェア、CVE が公開された場合、CVE が最後に更新された場合、および CVE に関連する脅威が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="916fd-200">前のタブと同様に、表示されるアイテムの数と表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="916fd-201">このリストからアイテムを選択すると、CVE を説明するフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="916fd-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="916fd-202">不足している KB</span><span class="sxs-lookup"><span data-stu-id="916fd-202">Missing KBs</span></span>

<span data-ttu-id="916fd-203">[ **不足している KB]** タブには、デバイスにまだ適用されていない Microsoft 更新プログラムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="916fd-204">問題の "KB" は、これらの [更新プログラムについて説明](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) するサポート技術情報の記事です。たとえば [、KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="916fd-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![デバイス プロファイルの不足している kbs タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="916fd-206">既定のビューには、更新プログラム、OS バージョン、影響を受ける製品、アドレス指定された CVEs、KB 番号、およびタグが含まれるセキュリティ情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fd-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="916fd-207">ページごとに表示されるアイテムの数と表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="916fd-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="916fd-208">アイテムを選択すると、更新プログラムにリンクするフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="916fd-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="916fd-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="916fd-209">Related topics</span></span>

* [<span data-ttu-id="916fd-210">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="916fd-210">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
* [<span data-ttu-id="916fd-211">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="916fd-211">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
* [<span data-ttu-id="916fd-212">ライブ応答を使用して、デバイス上のエンティティを調査する</span><span class="sxs-lookup"><span data-stu-id="916fd-212">Investigate entities on devices, using live response</span></span>](../defender-endpoint/live-response.md)
* [<span data-ttu-id="916fd-213">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="916fd-213">Automated investigation and response (AIR) in Office 365</span></span>](../office-365-security/office-365-air.md)
