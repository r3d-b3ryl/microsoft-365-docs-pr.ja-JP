---
title: Microsoft 365 セキュリティ ポータルのデバイス プロファイル
description: 組織内のデバイスのリスクと露出のレベルを表示します。 過去および現在の脅威を分析し、最新の更新プログラムでデバイスを保護します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, Microsoft Threat Protection, MTP, セキュリティ センター, Microsoft Defender ATP, Office 365 ATP, Azure ATP, デバイス ページ, デバイス プロファイル, コンピューター ページ, コンピューター プロファイル
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929576"
---
# <a name="device-profile-page"></a><span data-ttu-id="080e4-105">デバイス プロファイル ページ</span><span class="sxs-lookup"><span data-stu-id="080e4-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="080e4-106">Microsoft 365 セキュリティ ポータルでは、デバイス プロファイル ページが提供され、ネットワーク上のデバイスの正常性と状態をすばやく評価できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="080e4-107">デバイス プロファイル ページは、デバイスが Microsoft Defender for Endpoint、Microsoft Defender for Identity、または両方に登録されているかどうかに応じて、少し異なって表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="080e4-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="080e4-108">デバイスが Microsoft Defender for Endpoint に登録されている場合は、デバイス プロファイル ページを使用して一般的なセキュリティ タスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="080e4-109">デバイス プロファイル ページの移動</span><span class="sxs-lookup"><span data-stu-id="080e4-109">Navigating the device profile page</span></span>

<span data-ttu-id="080e4-110">プロファイル ページは、いくつかの広範なセクションに分割されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-110">The profile page is broken up into several broad sections.</span></span>

![(1) タブ領域 (2) サイドバーと (3) アクションが赤で強調表示されているデバイス プロファイル ページの画像](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="080e4-112">サイドバー (1) には、デバイスに関する基本的な詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="080e4-113">メイン コンテンツ領域 (2) には、デバイスに関するさまざまな種類の情報を表示するために切り替え可能なタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="080e4-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="080e4-114">デバイスが Microsoft Defender for Endpoint に登録されている場合は、対応アクションの一覧 (3) も表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="080e4-115">対応アクションを使用すると、セキュリティ関連の一般的なタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="080e4-116">サイドバー</span><span class="sxs-lookup"><span data-stu-id="080e4-116">Sidebar</span></span>

<span data-ttu-id="080e4-117">デバイス プロファイル ページのメイン コンテンツ領域の横にサイドバーがあります。</span><span class="sxs-lookup"><span data-stu-id="080e4-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![デバイス プロファイルのサイドバー タブの画像](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="080e4-119">サイドバーには、デバイスの完全な名前と露出レベルが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="080e4-120">また、次のような、開くまたは閉じた状態に切り替え可能な小さなサブセクションの重要な基本情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="080e4-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="080e4-121">**タグ** - デバイスに関連付けられているエンドポイント用 Microsoft Defender、Id 用 Microsoft Defender、またはカスタム タグ。</span><span class="sxs-lookup"><span data-stu-id="080e4-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="080e4-122">Id 用 Microsoft Defender のタグは編集できません。</span><span class="sxs-lookup"><span data-stu-id="080e4-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="080e4-123">**セキュリティ情報** - インシデントとアクティブなアラートを開きます。</span><span class="sxs-lookup"><span data-stu-id="080e4-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="080e4-124">Microsoft Defender for Endpoint に登録されているデバイスには、露出レベルとリスク レベルも表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="080e4-125">露出レベルは、デバイスがセキュリティの推奨事項にどの程度準拠しているのかに関係し、リスク レベルはアクティブなアラートの種類や重大度など、さまざまな要因に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="080e4-126">**デバイスの** 詳細 - ドメイン、OS、デバイスが最初に表示された時刻のタイムスタンプ、IP アドレス、リソース。</span><span class="sxs-lookup"><span data-stu-id="080e4-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="080e4-127">Microsoft Defender for Endpoint に登録されているデバイスでも、正常性状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="080e4-128">Id 用 Microsoft Defender に登録されているデバイスには、デバイスが最初に作成された日時の SAM 名とタイムスタンプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="080e4-129">**ネットワーク アクティビティ** - デバイスがネットワーク上で最初に確認された時刻と最後のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="080e4-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="080e4-130">\**ディレクトリ データ\*\*\*(Id* 用 Microsoft Defender に登録されているデバイスの場合のみ) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview)フラグ [、SPN、](https://docs.microsoft.com/windows/win32/ad/service-principal-names)およびグループ メンバーシップ。</span><span class="sxs-lookup"><span data-stu-id="080e4-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="080e4-131">応答アクション</span><span class="sxs-lookup"><span data-stu-id="080e4-131">Response actions</span></span>

<span data-ttu-id="080e4-132">対応アクションは、脅威から迅速に防御して分析する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="080e4-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![デバイス プロファイルのアクション バーの画像](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="080e4-134">[応答アクション](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) は、デバイスが Microsoft Defender for Endpoint に登録されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="080e4-135">Microsoft Defender for Endpoint に登録されているデバイスでは、デバイスの OS とバージョン番号に基づいて、異なる数の応答アクションが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="080e4-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="080e4-136">デバイス プロファイル ページで使用可能なアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="080e4-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="080e4-137">**タグの管理** - このデバイスに適用したカスタム タグを更新します。</span><span class="sxs-lookup"><span data-stu-id="080e4-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="080e4-138">**デバイスの** 分離 - デバイスを Microsoft Defender for Endpoint に接続した状態に保ちながら、組織のネットワークからデバイスを分離します。</span><span class="sxs-lookup"><span data-stu-id="080e4-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="080e4-139">通信の目的で、デバイスが分離されている間に Outlook、Teams、Skype for Business の実行を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="080e4-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="080e4-140">**アクション センター** - 送信されたアクションの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="080e4-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="080e4-141">別のアクションが既に選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="080e4-142">**アプリの実行を** 制限する - Microsoft によって署名されていないアプリケーションが実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="080e4-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="080e4-143">**ウイルス対策スキャンの** 実行 - ウイルスWindows Defender定義を更新し、ウイルス対策スキャンを直ちに実行します。</span><span class="sxs-lookup"><span data-stu-id="080e4-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="080e4-144">クイック スキャンまたはフル スキャンを選択します。</span><span class="sxs-lookup"><span data-stu-id="080e4-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="080e4-145">**調査パッケージの収集** - デバイスに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="080e4-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="080e4-146">調査が完了したら、ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="080e4-147">**ライブ応答セッションの開始** - 詳細なセキュリティ調査のためにデバイスにリモート シェル [を読み込む](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。</span><span class="sxs-lookup"><span data-stu-id="080e4-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="080e4-148">**自動調査の開始** - 脅威 [を自動的に調査して修復します](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。</span><span class="sxs-lookup"><span data-stu-id="080e4-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="080e4-149">このページから自動調査を手動で実行することもできますが、特定のアラート[](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies)ポリシーによって自動的に調査がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="080e4-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="080e4-150">**アクション センター** - 現在実行中の応答アクションに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="080e4-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="080e4-151">[タブ] セクション</span><span class="sxs-lookup"><span data-stu-id="080e4-151">Tabs section</span></span>

<span data-ttu-id="080e4-152">[デバイス プロファイル] タブでは、デバイスに関するセキュリティの詳細の概要と、アラートの一覧を含むテーブルを切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="080e4-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="080e4-153">Microsoft Defender for Endpoint に登録されているデバイスには、タイムライン、セキュリティに関する推奨事項の一覧、ソフトウェア インベントリ、検出された脆弱性の一覧、不足している KB (セキュリティ更新プログラム) を備えたタブも表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="080e4-154">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="080e4-154">Overview tab</span></span>

<span data-ttu-id="080e4-155">既定のタブは [概要] **です**。</span><span class="sxs-lookup"><span data-stu-id="080e4-155">The default tab is **Overview**.</span></span> <span data-ttu-id="080e4-156">デバイスに関する最も重要なセキュリティの事実を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-156">It provides a quick look at the most important security fact about the device.</span></span>

![デバイス プロファイルの [概要] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="080e4-158">ここでは、デバイスのアクティブなアラートと、現在ログオンしているユーザーを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="080e4-159">デバイスが Microsoft Defender for Endpoint に登録されている場合は、デバイスのリスク レベルと、セキュリティ評価に関する利用可能なデータも表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="080e4-160">セキュリティ評価では、デバイスの露出レベルについて説明し、セキュリティの推奨事項を示し、影響を受けるソフトウェアと検出された脆弱性の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="080e4-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="080e4-161">[通知] タブ</span><span class="sxs-lookup"><span data-stu-id="080e4-161">Alerts tab</span></span>

<span data-ttu-id="080e4-162">[ **アラート]** タブには、Microsoft Defender for Identity と Microsoft Defender for Endpoint の両方から、デバイスで発生したアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![デバイス プロファイルの [アラート] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="080e4-164">表示されるアイテムの数、および各アイテムに対して表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="080e4-165">既定の動作では、1 ページあたり 30 アイテムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="080e4-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="080e4-166">このタブの列には、アラートをトリガーした脅威の重大度、状態、調査状態、アラートが割り当てられているユーザーに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="080e4-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="080e4-167">影響 *を受けるエンティティ* 列は、現在表示しているプロファイルを持つデバイス (エンティティ) と、影響を受けるネットワーク内の他のデバイスを参照します。</span><span class="sxs-lookup"><span data-stu-id="080e4-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="080e4-168">この一覧からアイテムを選択すると、選択したアラートに関するさらに多くの情報を含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="080e4-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="080e4-169">この一覧は、重大度、状態、またはアラートが割り当てられているユーザーでフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="080e4-170">[タイムライン] タブ</span><span class="sxs-lookup"><span data-stu-id="080e4-170">Timeline tab</span></span>

<span data-ttu-id="080e4-171">[ **タイムライン]** タブには、デバイスで発生したイベントの対話型の時系列グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="080e4-172">グラフの強調表示された領域を左または右に移動すると、さまざまな期間のイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="080e4-173">また、対話型グラフとイベントの一覧の間にあるドロップダウン メニューから、日付のカスタム範囲を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="080e4-174">グラフの下には、選択した日付範囲のイベントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-174">Below the chart is a list of events for the selected range of dates.</span></span>

![デバイス プロファイルのタイムライン タブの画像](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="080e4-176">表示されるアイテムの数とリストの列の両方をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="080e4-177">既定の列には、イベント時間、アクティブ ユーザー、アクションの種類、エンティティ (プロセス)、およびイベントに関する追加情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="080e4-178">このリストからアイテムを選択すると、イベント エンティティのグラフを表示するフライアウトが開き、イベントに関係する親プロセスと子プロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="080e4-179">リストは、特定の種類のイベントでフィルター処理できます。たとえば、レジストリ イベントやスマート スクリーン イベントなどです。</span><span class="sxs-lookup"><span data-stu-id="080e4-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="080e4-180">この一覧は、ダウンロード用に CSV ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="080e4-181">ファイルはイベントの数によって制限されるのではなく、エクスポートできる最大時間の範囲は 7 日間です。</span><span class="sxs-lookup"><span data-stu-id="080e4-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="080e4-182">[セキュリティの推奨事項] タブ</span><span class="sxs-lookup"><span data-stu-id="080e4-182">Security recommendations tab</span></span>

<span data-ttu-id="080e4-183">[ **セキュリティの推奨事項]** タブには、デバイスを保護するために実行できるアクションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="080e4-184">この一覧で項目を選択すると、フライアウトが開き、推奨事項を適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="080e4-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![デバイス プロファイルの [セキュリティの推奨事項] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="080e4-186">前のタブと同様に、ページごとに表示されるアイテムの数と表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="080e4-187">既定のビューには、対処するセキュリティ上の弱点、関連する脅威、脅威の影響を受ける関連コンポーネントまたはソフトウェアなどについて詳しく説明する列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="080e4-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="080e4-188">アイテムは、推奨事項の状態によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="080e4-189">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="080e4-189">Software inventory</span></span>

<span data-ttu-id="080e4-190">[ **ソフトウェア インベントリ]** タブには、デバイスにインストールされているソフトウェアが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-190">The **Software inventory** tab lists software installed on the device.</span></span>

![デバイス プロファイルの [ソフトウェア インベントリ] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="080e4-192">既定のビューには、ソフトウェア ベンダー、インストールされているバージョン番号、既知のソフトウェアの弱点の数、脅威の分析情報、製品コード、タグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="080e4-193">表示されるアイテムの数と表示される列の両方をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="080e4-194">この一覧から項目を選択すると、選択したソフトウェアに関する詳細と、ソフトウェアが最後に見つかった時点のパスとタイムスタンプを含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="080e4-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="080e4-195">この一覧は、製品コードでフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="080e4-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="080e4-196">[検出された脆弱性] タブ</span><span class="sxs-lookup"><span data-stu-id="080e4-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="080e4-197">[ **検出された脆弱性]** タブには、デバイスに影響を与える可能性のある一般的な脆弱性と悪用 (CVEs) が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![デバイス プロファイルの [検出された脆弱性] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="080e4-199">既定のビューには、CVE の重要度、共通脆弱性スコア (CVS)、CVE に関連するソフトウェア、CVE の公開日、CVE が最後に更新された日、および CVE に関連する脅威が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="080e4-200">前のタブと同様に、表示されるアイテムの数と表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="080e4-201">このリストから項目を選択すると、CVE を説明するフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="080e4-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="080e4-202">不足している KB</span><span class="sxs-lookup"><span data-stu-id="080e4-202">Missing KBs</span></span>

<span data-ttu-id="080e4-203">[ **不足している KB]** タブには、デバイスにまだ適用されていない Microsoft 更新プログラムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="080e4-204">問題の "KBs" は、これらの [更新プログラムについて](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) 説明するサポート技術情報の記事です。たとえば [、KB4551762 です](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)。</span><span class="sxs-lookup"><span data-stu-id="080e4-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![デバイス プロファイルの [kbs] タブが見つからない画像](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="080e4-206">既定のビューには、更新プログラム、OS バージョン、影響を受ける製品、アドレス指定された CVEs、KB 番号、タグが含まれる情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="080e4-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="080e4-207">ページごとに表示されるアイテムの数と表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="080e4-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="080e4-208">アイテムを選択すると、更新プログラムにリンクするフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="080e4-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="080e4-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="080e4-209">Related topics</span></span>

* [<span data-ttu-id="080e4-210">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="080e4-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="080e4-211">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="080e4-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="080e4-212">ライブ応答を使用して、デバイス上のエンティティを調査する</span><span class="sxs-lookup"><span data-stu-id="080e4-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="080e4-213">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="080e4-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
