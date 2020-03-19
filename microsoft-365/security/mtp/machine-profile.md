---
title: Microsoft 365 セキュリティポータルのコンピュータープロファイル
description: 組織内のデバイスのリスクと露出レベルを表示します。 過去および現在の脅威を分析し、コンピューターを最新の更新プログラムで保護します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、Microsoft Threat Protection、MTP、セキュリティセンター、Microsoft Defender ATP、Office 365 ATP、Azure ATP、machine page、machine list、machine profile
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
ms.openlocfilehash: 7ab3f63008c65fca1a99128cc6f11f83bc86b2b4
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857696"
---
# <a name="machine-profile-page"></a><span data-ttu-id="69a39-105">コンピュータープロファイルページ</span><span class="sxs-lookup"><span data-stu-id="69a39-105">Machine profile page</span></span>

<span data-ttu-id="69a39-106">Microsoft 365 セキュリティポータルは、コンピュータープロファイルページを提供するので、ネットワーク上のデバイスの正常性と状態を評価できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-106">The Microsoft 365 security portal provides you with Machine profile pages, so you can assess the health and status of devices on your network.</span></span> <span data-ttu-id="69a39-107">各マシンプロファイルページには、デバイスに関する情報が豊富に含まれています。</span><span class="sxs-lookup"><span data-stu-id="69a39-107">Each Machine profile page contains a wealth of information about the device.</span></span>

<span data-ttu-id="69a39-108">実行しているソフトウェア、過去および現在のセキュリティイベントまたはアラートに関する詳細な情報を確認し、関連するソフトウェアパッチへのリンクを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="69a39-108">You can review in-depth information about what software it is running, any past and present security events or alerts, and find links to relevant software patches.</span></span>

<span data-ttu-id="69a39-109">また、コンピュータープロファイルを使用してセキュリティ関連の一般的なタスクを実行し、デバイスに関する基本的な情報をすばやく確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="69a39-109">You can also use the Machine profile to perform common security-related tasks, and quickly review basic details about the device.</span></span>

## <a name="navigating-the-machine-profile-page"></a><span data-ttu-id="69a39-110">[コンピュータープロファイル] ページのナビゲーション</span><span class="sxs-lookup"><span data-stu-id="69a39-110">Navigating the Machine profile page</span></span>

<span data-ttu-id="69a39-111">[コンピュータープロファイル] ページにアクセスするには、[コンピューター] リストでデバイス名を直接選択するか、[マシン] リストのポップアップで [**コンピューターを開く] ページ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="69a39-111">The Machine profile page can be accessed by directly selecting a device name on the Machines list or by choosing **Open Machine page** on the Machines list flyout.</span></span>

<span data-ttu-id="69a39-112">ページを開いたら、3つのセクションに分割されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="69a39-112">Once you have the page open, you'll find that it is broken up into three sections.</span></span>

![(1) タブ領域 (2) サイドバーと (3) アクションが赤で強調表示されているコンピュータープロファイルページのイメージ](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

<span data-ttu-id="69a39-114">メインコンテンツ領域 (1) には、コンピューターに関するさまざまな種類の情報を表示できる7つのタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="69a39-114">The main content area (1) contains seven tabs that you can toggle through to view different kinds of information about the machine.</span></span>

<span data-ttu-id="69a39-115">サイドバー (2) には、コンピューターに関する基本的な詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-115">The sidebar (2) lists basic details about the machine.</span></span>

<span data-ttu-id="69a39-116">サイドバーとメインコンテンツセクションの前にヘッダー (3) で使用可能な応答アクションもあります。</span><span class="sxs-lookup"><span data-stu-id="69a39-116">There are also response actions available in a header (3) before the sidebar and main content sections.</span></span> <span data-ttu-id="69a39-117">このヘッダー内のアクションを使用して、一般的なセキュリティ関連のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-117">You can use the actions in this header to perform common security-related tasks.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="69a39-118">[タブ] セクション</span><span class="sxs-lookup"><span data-stu-id="69a39-118">Tabs section</span></span>

<span data-ttu-id="69a39-119">[マシンプロファイル] タブを使用すると、コンピューターに関するセキュリティ詳細の概要と、アラートのリストを含むテーブル、タイムライン、セキュリティ推奨事項のリスト、ソフトウェアインベントリ、検出された脆弱性のリストを表示することができます。KBs (セキュリティ更新プログラム)。</span><span class="sxs-lookup"><span data-stu-id="69a39-119">The Machine profile tabs allow you to toggle through an overview of security details about the machine, and tables containing a list of alerts, a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="69a39-120">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="69a39-120">Overview tab</span></span>

<span data-ttu-id="69a39-121">既定のタブは**概要**です。</span><span class="sxs-lookup"><span data-stu-id="69a39-121">The default tab is **Overview**.</span></span> <span data-ttu-id="69a39-122">これにより、デバイスに関する最も重要なセキュリティの事実をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-122">It provides a quick look at the most important security fact about the device.</span></span>

![コンピュータープロファイルの概要タブの画像](../../media/mtp-machine-profile/overview.png)

<span data-ttu-id="69a39-124">ここでは、デバイスのリスクレベルとアクティブな通知、現在ログオンしているユーザー、頻繁に使用されるユーザーの一覧、デバイスの露出レベル、セキュリティに関する推奨事項、影響を受けるソフトウェア、およびその他のセキュリティ評価のグラフを見つけることができます。検出された脆弱性。</span><span class="sxs-lookup"><span data-stu-id="69a39-124">Here, you can find a chart of the device's risk level and active alerts, any currently logged on users, a brief list of most and least frequent users, and security assessments that detail the device's exposure level, security recommendations, affected software, and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="69a39-125">[通知] タブ</span><span class="sxs-lookup"><span data-stu-id="69a39-125">Alerts tab</span></span>

<span data-ttu-id="69a39-126">[**通知**] タブには、デバイスで報告された通知の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69a39-126">The **Alerts** tab contains a list of alerts that have been reported on the device.</span></span>

![コンピュータープロファイルの [通知] タブの画像](../../media/mtp-machine-profile/alerts.png)

<span data-ttu-id="69a39-128">表示されるアイテムの数、およびアイテムごとに表示される列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="69a39-128">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="69a39-129">既定の動作は、ページごとに30個のアイテムを一覧表示し、11列を表示するように切り替えます。</span><span class="sxs-lookup"><span data-stu-id="69a39-129">The default behavior is to list 30 items per page, and have 11 columns toggled on to display.</span></span>

<span data-ttu-id="69a39-130">このタブの列には、アラートをトリガーした脅威の重要度、状態、調査状態、およびアラートが割り当てられているユーザーがいるかどうかに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="69a39-130">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who if anyone the alert has been assigned to.</span></span>

<span data-ttu-id="69a39-131">[*影響を受けるエンティティ*] 列は、現在表示されているプロファイルを含むマシン (エンティティ) と、その影響を受けるネットワーク内の他のコンピューターを参照しています。</span><span class="sxs-lookup"><span data-stu-id="69a39-131">The *impacted entities* column refers to the machine (entity) whose profile you are currently viewing, plus any other machines in your network that are affected.</span></span>

<span data-ttu-id="69a39-132">この一覧から項目を選択すると、選択した通知へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-132">Selecting an item from this list will open a link to the selected alert.</span></span>

<span data-ttu-id="69a39-133">このリストは、重要度、状態、または担当者によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-133">This list can be filtered by severity, status, or assignee.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="69a39-134">[タイムライン] タブ</span><span class="sxs-lookup"><span data-stu-id="69a39-134">Timeline tab</span></span>

<span data-ttu-id="69a39-135">[**タイムライン**] タブには、デバイス上で発生するイベントの対話的な時系列のグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="69a39-135">The **Timeline** tab includes a interactive, chronological chart of events raised on the device.</span></span> <span data-ttu-id="69a39-136">グラフの強調表示された領域を移動すると、さまざまな時間範囲のイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-136">By moving the highlighted area of the chart, you can view events over different ranges of time.</span></span> <span data-ttu-id="69a39-137">日付のカスタム範囲を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="69a39-137">You can also type in a custom range of dates.</span></span>

<span data-ttu-id="69a39-138">グラフの下に、選択した日付範囲のイベントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-138">Below the chart is a list of events for the selected range of dates.</span></span>

![コンピュータープロファイルの [タイムライン] タブのイメージ](../../media/mtp-machine-profile/timeline.png)

<span data-ttu-id="69a39-140">表示されるアイテムの数とリストの列の両方をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="69a39-140">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="69a39-141">既定の列には、イベント時間、アクティブなユーザー、アクションの種類、エンティティ (プロセス)、およびイベントに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-141">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="69a39-142">リストから項目を選択すると、イベントエンティティグラフが表示されたフライアウトが開き、イベントを発生させた親と子のプロセスが示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-142">Selecting an item from the list will open a flyout displaying an Event entities graph, showing the parent and child processes that triggered the event.</span></span>

<span data-ttu-id="69a39-143">このリストは、特定の種類のイベントによってフィルター処理できます。たとえば、レジストリイベントや Smart Screen イベントなどがあります。</span><span class="sxs-lookup"><span data-stu-id="69a39-143">This list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="69a39-144">[セキュリティの推奨事項] タブ</span><span class="sxs-lookup"><span data-stu-id="69a39-144">Security recommendations tab</span></span>

<span data-ttu-id="69a39-145">[**セキュリティの推奨事項**] タブには、デバイスを保護するために実行できるアクションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-145">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="69a39-146">このリストで項目を選択すると、推奨事項の適用方法を説明するポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-146">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![コンピュータープロファイルの [セキュリティの推奨事項] タブの画像](../../media/mtp-machine-profile/security-recs.png)

<span data-ttu-id="69a39-148">前のタブと同様に、ページごとに表示されるアイテムの数と表示される列はカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="69a39-148">As with the previous tabs, the number of items displayed per page and which columns are visible can be customized.</span></span>

<span data-ttu-id="69a39-149">既定のビューには、セキュリティの弱点の詳細、関連する脅威、脅威の影響を受ける関連コンポーネントまたはソフトウェアなどの列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69a39-149">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="69a39-150">アイテムは、推奨の状態によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-150">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="69a39-151">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="69a39-151">Software inventory</span></span>

<span data-ttu-id="69a39-152">[**ソフトウェアインベントリ**] タブには、デバイスにインストールされているソフトウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-152">The **Software inventory** tab lists software installed on the device.</span></span>

![コンピュータープロファイルの [ソフトウェアインベントリ] タブのイメージ](../../media/mtp-machine-profile/software-inventory.png)

<span data-ttu-id="69a39-154">既定の表示では、ソフトウェアベンダー、インストールされているバージョン番号、既知のソフトウェアの弱点の数、脅威の insights、製品コード、およびタグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-154">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="69a39-155">表示されるアイテムの数と表示される列の両方をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="69a39-155">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="69a39-156">この一覧から項目を選択すると、選択したソフトウェアの詳細と、ソフトウェアが最後に検出されたときのパスとタイムスタンプを含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="69a39-156">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="69a39-157">このリストは、製品コードによってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-157">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="69a39-158">[検出された脆弱性] タブ</span><span class="sxs-lookup"><span data-stu-id="69a39-158">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="69a39-159">[**検出**された脆弱性] タブには、デバイスに影響を与える可能性のある一般的な脆弱性と悪用 (cves) が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-159">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![コンピュータープロファイルの [検出された脆弱性] タブの画像](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

<span data-ttu-id="69a39-161">既定のビューには、CVE の重要度、共通の脆弱性スコア (CVS)、CVE に関連するソフトウェア、cve が発行されたとき、CVE が最後に更新された日時、および CVE に関連付けられている脅威が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-161">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="69a39-162">前のタブと同様に、表示されるアイテムの数と表示される列はカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="69a39-162">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="69a39-163">この一覧から項目を選択すると、CVE を説明するフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="69a39-163">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="69a39-164">KBs がありません</span><span class="sxs-lookup"><span data-stu-id="69a39-164">Missing KBs</span></span>

<span data-ttu-id="69a39-165">[ **Kb がありません**] タブには、コンピューターにまだ適用されていない Microsoft の更新プログラムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-165">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the machine.</span></span> <span data-ttu-id="69a39-166">質問の "KBs" は、これらの更新を説明する[サポート技術情報の記事](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query)です。たとえば、 [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)のようになります。</span><span class="sxs-lookup"><span data-stu-id="69a39-166">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![コンピュータープロファイル用の [kbs] タブがない画像](../../media/mtp-machine-profile/missing-kbs.PNG)

<span data-ttu-id="69a39-168">既定の表示では、更新プログラム、OS バージョン、影響を受けた製品、CVEs アドレス、KB 番号、タグを含むセキュリティ情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a39-168">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="69a39-169">ページごとに表示されるアイテムの数と表示される列は、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="69a39-169">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="69a39-170">アイテムを選択すると、更新プログラムにリンクするポップアップが開きます。</span><span class="sxs-lookup"><span data-stu-id="69a39-170">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="sidebar"></a><span data-ttu-id="69a39-171">サイドバー</span><span class="sxs-lookup"><span data-stu-id="69a39-171">Sidebar</span></span>

<span data-ttu-id="69a39-172">[コンピュータープロファイル] ページのメインコンテンツ領域の横に、サイドバーがあります。</span><span class="sxs-lookup"><span data-stu-id="69a39-172">Beside the main content area of the Machine profile page is the sidebar.</span></span>

![コンピュータープロファイルの [サイドバー] タブのイメージ](../../media/mtp-machine-profile/sidebar.png)

<span data-ttu-id="69a39-174">サイドバーには、次の重要な基本情報が含まれています。これは、開いた状態または閉じた状態で切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="69a39-174">The sidebar provides some important basic information in small subsections which can be toggled open or closed:</span></span>

* <span data-ttu-id="69a39-175">**タグ**-デバイスに関連付けられているタグ</span><span class="sxs-lookup"><span data-stu-id="69a39-175">**Tags** - Any tags associated with the device</span></span>
* <span data-ttu-id="69a39-176">**セキュリティ情報**-オープンインシデント、アクティブなアラート、露出レベルおよびリスクレベル</span><span class="sxs-lookup"><span data-stu-id="69a39-176">**Security info** - Open incidents, active alerts, exposure level and risk level</span></span>
* <span data-ttu-id="69a39-177">**デバイスの詳細**-ドメイン、OS、資産グループ、正常性状態、データの秘密度、および IP アドレス</span><span class="sxs-lookup"><span data-stu-id="69a39-177">**Device details** - Domain, OS, Asset group, health state, data sensitivity, and IP addresses</span></span>
* <span data-ttu-id="69a39-178">**ネットワークアクティビティ**-最初の時点でのタイムスタンプ、およびデバイスがネットワーク上で最後に表示された時刻</span><span class="sxs-lookup"><span data-stu-id="69a39-178">**Network activity** - Timestamps for the first time and last time the device was seen on the network</span></span>

<span data-ttu-id="69a39-179">このセクションには、デバイスの名前と露出レベル、および現在ネットワーク上でアクティブであるかどうかを示すアイコンも含まれています。</span><span class="sxs-lookup"><span data-stu-id="69a39-179">This section also includes the name and exposure level of the device, and an icon to indicate if it is currently active on the network.</span></span>

## <a name="response-actions"></a><span data-ttu-id="69a39-180">応答アクション</span><span class="sxs-lookup"><span data-stu-id="69a39-180">Response actions</span></span>

<span data-ttu-id="69a39-181">応答アクションは、脅威を迅速に防御して分析する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="69a39-181">Response actions offer a quick way to defend against and analyze threats.</span></span>

![コンピュータープロファイルの [サイドバー] タブのイメージ](../../media/mtp-machine-profile/actions.PNG)

<span data-ttu-id="69a39-183">ここで使用できる応答アクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="69a39-183">The response actions available to you here include:</span></span>

* <span data-ttu-id="69a39-184">**タグの管理**-このデバイスに適用したカスタムタグを更新します。</span><span class="sxs-lookup"><span data-stu-id="69a39-184">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="69a39-185">**分離マシン**-Microsoft Defender Advanced Threat Protection に接続したまま、組織のネットワークからコンピューターを分離します。</span><span class="sxs-lookup"><span data-stu-id="69a39-185">**Isolate machine** - Isolates the machine from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="69a39-186">通信の目的で、コンピューターが分離されている間、Outlook、Teams、Skype for Business の実行を許可するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-186">You can choose to allow Outlook, Teams, and Skype for Business to run while the machine is isolated, for communication purposes.</span></span>
* <span data-ttu-id="69a39-187">**アプリの実行を制限**する-Microsoft によって署名されていないアプリケーションが実行されないようにする</span><span class="sxs-lookup"><span data-stu-id="69a39-187">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running</span></span>
* <span data-ttu-id="69a39-188">**ウイルス対策スキャンを実行**する-Windows Defender ウイルス対策の定義を更新し、すぐにウイルス対策スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="69a39-188">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="69a39-189">クイックスキャンまたはフルスキャンのどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="69a39-189">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="69a39-190">**収集調査パッケージ**-コンピューターに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="69a39-190">**Collect investigation package** - Gathers information about the machine.</span></span> <span data-ttu-id="69a39-191">調査が完了したら、ダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="69a39-191">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="69a39-192">**Live Response session を開始**する-[詳細なセキュリティ調査](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)を行うために、コンピューター上のリモートシェルをロードします。</span><span class="sxs-lookup"><span data-stu-id="69a39-192">**Initiate Live Response session** - Loads a remote shell on the machine for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="69a39-193">**自動化**された調査を開始します。脅威を自動的に調査[し、remediates](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)します。</span><span class="sxs-lookup"><span data-stu-id="69a39-193">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="69a39-194">自動調査を手動でトリガーしてこのページから実行することもできますが、[特定のアラートポリシーによっ](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies)て自動的に調査がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="69a39-194">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="69a39-195">**アクションセンター** -送信されたアクションの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="69a39-195">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="69a39-196">別のアクションが既に選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="69a39-196">Only available if another action has already been selected.</span></span>

## <a name="related-topics"></a><span data-ttu-id="69a39-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="69a39-197">Related topics</span></span>

* [<span data-ttu-id="69a39-198">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="69a39-198">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="69a39-199">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="69a39-199">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="69a39-200">Live response を使用してコンピューターのエンティティを調査する</span><span class="sxs-lookup"><span data-stu-id="69a39-200">Investigate entities on machines using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="69a39-201">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="69a39-201">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
