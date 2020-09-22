---
title: Microsoft 365 セキュリティポータルのデバイスプロファイル
description: 組織内のデバイスのリスクと露出レベルを表示します。 過去および現在の脅威を分析し、デバイスを最新の更新プログラムで保護します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、Microsoft Threat Protection、MTP、セキュリティセンター、Microsoft Defender ATP、Office 365 ATP、Azure ATP、デバイスページ、デバイスプロファイル、コンピューターページ、コンピュータープロファイル
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f6b79d3252084b298f94e01b18ebe3505f83b480
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196859"
---
# <a name="device-profile-page"></a><span data-ttu-id="f6e2b-105">デバイスプロファイルページ</span><span class="sxs-lookup"><span data-stu-id="f6e2b-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f6e2b-106">Microsoft 365 セキュリティポータルはデバイスプロファイルページを提供するので、ネットワーク上のデバイスの正常性と状態をすばやく評価できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6e2b-107">デバイスが Microsoft Defender ATP、Azure ATP、またはその両方に登録されているかどうかによって、デバイスプロファイルページがわずかに異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender ATP, Azure ATP, or both.</span></span>

<span data-ttu-id="f6e2b-108">デバイスが Microsoft Defender ATP に登録されている場合は、[デバイスプロファイル] ページを使用して、いくつかの一般的なセキュリティタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-108">If the device is enrolled in Microsoft Defender ATP, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="f6e2b-109">デバイスプロファイルページのナビゲーション</span><span class="sxs-lookup"><span data-stu-id="f6e2b-109">Navigating the device profile page</span></span>

<span data-ttu-id="f6e2b-110">プロファイルページは、さまざまなセクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-110">The profile page is broken up into several broad sections.</span></span>

![(1) タブ領域 (2) サイドバーと (3) アクションが赤で強調表示されているデバイスプロファイルページのイメージ](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="f6e2b-112">サイドバー (1) には、デバイスに関する基本的な詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="f6e2b-113">メインコンテンツ領域 (2) には、デバイスに関するさまざまな種類の情報を表示するために切り替えることができるタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="f6e2b-114">デバイスが Microsoft Defender ATP に登録されている場合は、応答アクションの一覧も表示されます (3)。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-114">If the device is enrolled in Microsoft Defender ATP, you will also see a list of response actions (3).</span></span> <span data-ttu-id="f6e2b-115">応答アクションを使用すると、セキュリティ関連の一般的なタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="f6e2b-116">サイドバー</span><span class="sxs-lookup"><span data-stu-id="f6e2b-116">Sidebar</span></span>

<span data-ttu-id="f6e2b-117">[デバイスプロファイル] ページのメインコンテンツ領域の横に、サイドバーがあります。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![デバイスプロファイルの [サイドバー] タブのイメージ](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="f6e2b-119">サイドバーには、デバイスの完全な名前と露出レベルが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="f6e2b-120">また、以下のように、次のようないくつかの重要な基本的な情報を、開いた場合と閉じて設定したサブセクションで提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="f6e2b-121">**タグ** -デバイスに関連付けられている MICROSOFT Defender Atp、Azure atp、またはカスタムタグ。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-121">**Tags** - Any Microsoft Defender ATP, Azure ATP, or custom tags associated with the device.</span></span> <span data-ttu-id="f6e2b-122">Azure ATP からのタグは編集できません。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-122">Tags from Azure ATP are not editable.</span></span>
* <span data-ttu-id="f6e2b-123">**セキュリティ情報** -インシデントとアクティブなアラートを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="f6e2b-124">Microsoft Defender ATP に登録されているデバイスには、露出レベルとリスクレベルも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-124">Devices enrolled in Microsoft Defender ATP will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="f6e2b-125">露出レベルは、デバイスがセキュリティ上の推奨事項とどの程度準拠しているかに関係していますが、リスクレベルは、アクティブな通知の種類や重要度など、さまざまな要因に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="f6e2b-126">**デバイスの詳細** -デバイスが最初に表示されたときのドメイン、OS、タイムスタンプ、IP アドレス、リソース。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="f6e2b-127">Microsoft Defender ATP に登録されているデバイスには、正常性の状態も表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-127">Devices enrolled in Microsoft Defender ATP also display health state.</span></span> <span data-ttu-id="f6e2b-128">Azure ATP に登録されたデバイスは、最初にデバイスが作成されたときの SAM 名とタイムスタンプを表示します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-128">Devices enrolled in Azure ATP will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="f6e2b-129">**ネットワークアクティビティ** -最初の時点でのタイムスタンプ、およびデバイスがネットワーク上で最後に表示された時刻。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="f6e2b-130">**ディレクトリデータ** (*Azure ATP に登録されているデバイス専用*)- [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) のフラグ、 [spn](https://docs.microsoft.com/windows/win32/ad/service-principal-names)、およびグループメンバーシップ。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-130">**Directory data** (*only for devices enrolled in Azure ATP*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="f6e2b-131">応答アクション</span><span class="sxs-lookup"><span data-stu-id="f6e2b-131">Response actions</span></span>

<span data-ttu-id="f6e2b-132">応答アクションは、脅威を迅速に防御して分析する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![デバイスプロファイルのアクションバーの画像](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="f6e2b-134">[応答アクション](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) は、デバイスが MICROSOFT Defender ATP に登録されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender ATP.</span></span>
> * <span data-ttu-id="f6e2b-135">Microsoft Defender ATP に登録されているデバイスでは、デバイスの OS とバージョン番号に基づいて、異なる数の応答アクションが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-135">Devices that are enrolled in Microsoft Defender ATP may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="f6e2b-136">[デバイスプロファイル] ページで使用可能なアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="f6e2b-137">**タグの管理** -このデバイスに適用したカスタムタグを更新します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="f6e2b-138">**デバイスの分離** -Microsoft Defender Advanced Threat Protection に接続された状態を維持したまま、組織のネットワークからデバイスを分離します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="f6e2b-139">通信目的で、デバイスが分離されている間、Outlook、Teams、および Skype for Business を実行することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="f6e2b-140">**アクションセンター** -送信されたアクションの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="f6e2b-141">別のアクションが既に選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="f6e2b-142">**アプリの実行を制限** する-Microsoft によって署名されていないアプリケーションが実行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="f6e2b-143">**ウイルス対策スキャンを実行** する-Windows Defender ウイルス対策の定義を更新し、すぐにウイルス対策スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="f6e2b-144">クイックスキャンまたはフルスキャンのどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="f6e2b-145">**収集調査パッケージ** -デバイスに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="f6e2b-146">調査が完了したら、ダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="f6e2b-147">[ **Live Response Session を開始**する-[詳細なセキュリティ調査](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)のためにデバイス上のリモートシェルをロードします。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="f6e2b-148">**自動化** された調査を開始します。脅威を自動的に調査 [し、remediates](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="f6e2b-149">自動調査を手動でトリガーしてこのページから実行することもできますが、 [特定のアラートポリシーによっ](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) て自動的に調査がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="f6e2b-150">**アクションセンター** -現在実行されているすべての応答アクションに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="f6e2b-151">[タブ] セクション</span><span class="sxs-lookup"><span data-stu-id="f6e2b-151">Tabs section</span></span>

<span data-ttu-id="f6e2b-152">[デバイスプロファイル] タブを使用すると、デバイスに関するセキュリティ詳細の概要と、通知のリストを含むテーブルを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="f6e2b-153">Microsoft Defender ATP に登録されているデバイスには、タイムラインを機能するタブ、セキュリティに関する推奨事項の一覧、ソフトウェアインベントリ、検出された脆弱性の一覧、および KBs (セキュリティ更新プログラム) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-153">Devices enrolled in Microsoft Defender ATP will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="f6e2b-154">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="f6e2b-154">Overview tab</span></span>

<span data-ttu-id="f6e2b-155">既定のタブは **概要**です。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-155">The default tab is **Overview**.</span></span> <span data-ttu-id="f6e2b-156">これにより、デバイスに関する最も重要なセキュリティの事実をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-156">It provides a quick look at the most important security fact about the device.</span></span>

![デバイスプロファイルの [概要] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="f6e2b-158">ここでは、デバイスのアクティブな通知と、現在ログオンしているユーザーを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="f6e2b-159">デバイスが Microsoft Defender ATP に登録されている場合は、デバイスのリスクレベルとセキュリティ評価に関する利用可能なデータも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-159">If the device is enrolled in Microsoft Defender ATP, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="f6e2b-160">セキュリティ評価では、デバイスの公開レベルについて説明し、セキュリティに関する推奨事項を提示し、影響を受けるソフトウェアと検出された脆弱性を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="f6e2b-161">[通知] タブ</span><span class="sxs-lookup"><span data-stu-id="f6e2b-161">Alerts tab</span></span>

<span data-ttu-id="f6e2b-162">[ **通知** ] タブには、Azure Atp と MICROSOFT Defender atp の両方から、デバイス上で発生した通知の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Azure ATP and Microsoft Defender ATP.</span></span>

![デバイスプロファイルの [通知] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="f6e2b-164">表示されるアイテムの数、およびアイテムごとに表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="f6e2b-165">既定の動作は、ページごとに30個のアイテムを一覧表示することです。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="f6e2b-166">このタブの列には、アラートをトリガーした脅威の重要度、状態、調査状態、およびアラートが割り当てられている人物に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="f6e2b-167">[ *影響を受けるエンティティ* ] 列は、現在表示されているプロファイルを含むデバイス (エンティティ)、および影響を受けるネットワーク内の他のデバイスを参照します。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="f6e2b-168">このリストからアイテムを選択すると、選択した通知に関する詳細情報が含まれているフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="f6e2b-169">このリストは、重要度、状態、または通知の割り当て先によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="f6e2b-170">[タイムライン] タブ</span><span class="sxs-lookup"><span data-stu-id="f6e2b-170">Timeline tab</span></span>

<span data-ttu-id="f6e2b-171">[ **タイムライン** ] タブには、デバイス上で発生したすべてのイベントを示す対話的な時系列のグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="f6e2b-172">グラフの強調表示された領域を左または右に移動すると、さまざまな期間にわたるイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="f6e2b-173">対話型のグラフとイベントの一覧の間にあるドロップダウンメニューから、ユーザー設定の日付の範囲を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="f6e2b-174">グラフの下に、選択した日付範囲のイベントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-174">Below the chart is a list of events for the selected range of dates.</span></span>

![デバイスプロファイルの [タイムライン] タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="f6e2b-176">表示されるアイテムの数とリストの列の両方をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="f6e2b-177">既定の列には、イベント時間、アクティブなユーザー、アクションの種類、エンティティ (プロセス)、およびイベントに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="f6e2b-178">このリストから項目を選択すると、イベントエンティティグラフが表示されたフライアウトが開き、イベントに含まれる親と子のプロセスが示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="f6e2b-179">リストは特定の種類のイベントによってフィルター処理できます。たとえば、レジストリイベントや Smart Screen イベントなどがあります。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="f6e2b-180">また、リストを CSV ファイルにエクスポートして、ダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="f6e2b-181">ファイルはイベント数によって制限されませんが、エクスポートできる最大時間は7日です。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="f6e2b-182">[セキュリティの推奨事項] タブ</span><span class="sxs-lookup"><span data-stu-id="f6e2b-182">Security recommendations tab</span></span>

<span data-ttu-id="f6e2b-183">[ **セキュリティの推奨事項** ] タブには、デバイスを保護するために実行できるアクションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="f6e2b-184">このリストで項目を選択すると、推奨事項の適用方法を説明するポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![デバイスプロファイルの [セキュリティの推奨事項] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="f6e2b-186">前のタブと同様に、ページごとに表示されるアイテムの数と、表示されている列もカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="f6e2b-187">既定のビューには、セキュリティの弱点の詳細、関連する脅威、脅威の影響を受ける関連コンポーネントまたはソフトウェアなどの列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="f6e2b-188">アイテムは、推奨の状態によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="f6e2b-189">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="f6e2b-189">Software inventory</span></span>

<span data-ttu-id="f6e2b-190">[ **ソフトウェアインベントリ** ] タブには、デバイスにインストールされているソフトウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-190">The **Software inventory** tab lists software installed on the device.</span></span>

![デバイスプロファイルの [ソフトウェアインベントリ] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="f6e2b-192">既定の表示では、ソフトウェアベンダー、インストールされているバージョン番号、既知のソフトウェアの弱点の数、脅威の insights、製品コード、およびタグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="f6e2b-193">表示されるアイテムの数と表示される列の両方をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="f6e2b-194">この一覧から項目を選択すると、選択したソフトウェアの詳細と、ソフトウェアが最後に検出されたときのパスとタイムスタンプを含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="f6e2b-195">このリストは、製品コードによってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="f6e2b-196">[検出された脆弱性] タブ</span><span class="sxs-lookup"><span data-stu-id="f6e2b-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="f6e2b-197">[ **検出** された脆弱性] タブには、デバイスに影響を与える可能性のある一般的な脆弱性と悪用 (cves) が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![デバイスプロファイルの [検出された脆弱性] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="f6e2b-199">既定のビューには、CVE の重要度、共通の脆弱性スコア (CVS)、CVE に関連するソフトウェア、cve が発行されたとき、CVE が最後に更新された日時、および CVE に関連付けられている脅威が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="f6e2b-200">前のタブと同様に、表示されるアイテムの数と表示される列はカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="f6e2b-201">この一覧から項目を選択すると、CVE を説明するフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="f6e2b-202">KBs がありません</span><span class="sxs-lookup"><span data-stu-id="f6e2b-202">Missing KBs</span></span>

<span data-ttu-id="f6e2b-203">[ **Kb がありません** ] タブには、デバイスにまだ適用されていない Microsoft 更新プログラムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="f6e2b-204">質問の "KBs" は、これらの更新を説明する [サポート技術情報の記事](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) です。たとえば、 [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)のようになります。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![デバイスプロファイル用に [不足] タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="f6e2b-206">既定の表示では、更新プログラム、OS バージョン、影響を受けた製品、CVEs アドレス、KB 番号、タグを含むセキュリティ情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="f6e2b-207">ページごとに表示されるアイテムの数と表示される列は、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="f6e2b-208">アイテムを選択すると、更新プログラムにリンクするポップアップが開きます。</span><span class="sxs-lookup"><span data-stu-id="f6e2b-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f6e2b-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6e2b-209">Related topics</span></span>

* [<span data-ttu-id="f6e2b-210">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="f6e2b-210">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="f6e2b-211">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="f6e2b-211">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="f6e2b-212">Live response を使用してデバイスのエンティティを調査する</span><span class="sxs-lookup"><span data-stu-id="f6e2b-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="f6e2b-213">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="f6e2b-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
