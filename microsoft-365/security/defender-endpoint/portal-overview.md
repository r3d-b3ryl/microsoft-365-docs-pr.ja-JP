---
title: Microsoft Defender for Endpoint ポータルの概要
description: Microsoft Defender Security Center は、エンタープライズ ネットワークを監視し、潜在的な高度な永続的脅威 (APT) やデータ侵害への対応を支援できます。
keywords: Microsoft Defender Security Center, portal, サイバーセキュリティ脅威インテリジェンス, ダッシュボード, アラート キュー, デバイスリスト, 設定, デバイス管理, 高度な攻撃
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa7f2df1f0164f24c7f4698e8aa0b699f4884c09
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186223"
---
# <a name="microsoft-defender-security-center-portal-overview"></a><span data-ttu-id="982dd-104">Microsoft Defender Security Center ポータルの概要</span><span class="sxs-lookup"><span data-stu-id="982dd-104">Microsoft Defender Security Center portal overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="982dd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="982dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="982dd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="982dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="982dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="982dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="982dd-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="982dd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="982dd-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="982dd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink) 

<span data-ttu-id="982dd-110">エンタープライズ セキュリティ チームは、Microsoft Defender セキュリティ センターを使用して、潜在的な高度な永続的な脅威アクティビティやデータ侵害に関するアラートの監視と対応を支援できます。</span><span class="sxs-lookup"><span data-stu-id="982dd-110">Enterprise security teams can use Microsoft Defender Security Center to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span>

<span data-ttu-id="982dd-111">Microsoft Defender セキュリティ [センターを使用すると、次のコマンドを実行](https://securitycenter.windows.com/) できます。</span><span class="sxs-lookup"><span data-stu-id="982dd-111">You can use [Microsoft Defender Security Center](https://securitycenter.windows.com/) to:</span></span>

- <span data-ttu-id="982dd-112">エンドポイントからのアラートの表示、並べ替え、トリアージ</span><span class="sxs-lookup"><span data-stu-id="982dd-112">View, sort, and triage alerts from your endpoints</span></span>
- <span data-ttu-id="982dd-113">ファイルや IP アドレスなどの観測インジケーターの詳細を検索する</span><span class="sxs-lookup"><span data-stu-id="982dd-113">Search for more information on observed indicators such as files and IP Addresses</span></span>
- <span data-ttu-id="982dd-114">Microsoft Defender for Endpoint の設定 (タイム ゾーンを含む) を変更し、ライセンス情報を確認する</span><span class="sxs-lookup"><span data-stu-id="982dd-114">Change Microsoft Defender for Endpoint settings, including time zone and review licensing information</span></span>

## <a name="microsoft-defender-security-center"></a><span data-ttu-id="982dd-115">Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="982dd-115">Microsoft Defender Security Center</span></span>

<span data-ttu-id="982dd-116">ポータルを開く際に、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="982dd-116">When you open the portal, you'll see:</span></span>

- <span data-ttu-id="982dd-117">(1) ナビゲーション ウィンドウ (ナビゲーション ウィンドウの上部にある水平線を選択して表示または非表示にする)</span><span class="sxs-lookup"><span data-stu-id="982dd-117">(1) Navigation pane (select the horizontal lines at the top of the navigation pane to show or hide it)</span></span>
- <span data-ttu-id="982dd-118">(2) 検索、コミュニティ センター、ローカライズ、ヘルプとサポート、フィードバック</span><span class="sxs-lookup"><span data-stu-id="982dd-118">(2) Search, Community center, Localization, Help and support, Feedback</span></span>

 ![Microsoft Defender for Endpoint portal](images/mdatp-portal-overview.png)

> [!NOTE]
> <span data-ttu-id="982dd-120">マルウェア関連の検出は、デバイスが Microsoft Defender ウイルス対策を既定のリアルタイム保護マルウェア対策製品として使用している場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="982dd-120">Malware related detections will only appear if your devices are using Microsoft Defender Antivirus as the default real-time protection antimalware product.</span></span>

<span data-ttu-id="982dd-121">すべてのセクションで使用できるメニュー オプションを使用して、ポータル内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="982dd-121">You can navigate through the portal using the menu options available in all sections.</span></span> <span data-ttu-id="982dd-122">各セクションの説明については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="982dd-122">Refer to the following table for a description of each section.</span></span>

<span data-ttu-id="982dd-123">分野</span><span class="sxs-lookup"><span data-stu-id="982dd-123">Area</span></span> | <span data-ttu-id="982dd-124">説明</span><span class="sxs-lookup"><span data-stu-id="982dd-124">Description</span></span>
:---|:---
<span data-ttu-id="982dd-125">**(1) ナビゲーション ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="982dd-125">**(1) Navigation pane**</span></span> | <span data-ttu-id="982dd-126">ナビゲーション ウィンドウを使用して、ダッシュボード 、インシデント、デバイス リスト、アラートキュー、自動調査、高度な検索、**レポート**、パートナー & **API、Threat** **&** の脆弱性管理、評価とチュートリアル、サービス正常性、構成管理、および **設定** の間を移動します。   </span><span class="sxs-lookup"><span data-stu-id="982dd-126">Use the navigation pane to move between **Dashboards**, **Incidents**, **Devices list**, **Alerts queue**, **Automated investigations**, **Advanced hunting**, **Reports**, **Partners & APIs**, **Threat & Vulnerability Management**, **Evaluation and tutorials**, **Service health**, **Configuration management**, and **Settings**.</span></span> <span data-ttu-id="982dd-127">ナビゲーション ウィンドウの上部にある水平線を選択して、表示または非表示を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="982dd-127">Select the horizontal lines at the top of the navigation pane to show or hide it.</span></span>
<span data-ttu-id="982dd-128">**ダッシュボード**</span><span class="sxs-lookup"><span data-stu-id="982dd-128">**Dashboards**</span></span> | <span data-ttu-id="982dd-129">アクティブな自動調査、アクティブなアラート、自動調査統計、危険にさらされているデバイス、危険にさらされているユーザー、センサーの問題を持つデバイス、サービスの正常性、検出ソース、および毎日のデバイスレポートダッシュボードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="982dd-129">Access the active automated investigations, active alerts, automated investigations statistics, devices at risk, users at risk, devices with sensor issues, service health, detection sources, and daily devices reporting dashboards.</span></span>
<span data-ttu-id="982dd-130">**インシデント**</span><span class="sxs-lookup"><span data-stu-id="982dd-130">**Incidents**</span></span> | <span data-ttu-id="982dd-131">インシデントとして集計されたアラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="982dd-131">View alerts that have been aggregated as incidents.</span></span>
<span data-ttu-id="982dd-132">**デバイスの一覧**</span><span class="sxs-lookup"><span data-stu-id="982dd-132">**Devices list**</span></span> | <span data-ttu-id="982dd-133">Defender for Endpoint にオンボードされているデバイスの一覧、そのデバイスに関する情報、およびデバイスの露出とリスク レベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="982dd-133">Displays the list of devices that are onboarded to Defender for Endpoint, some information about them, and their exposure and risk levels.</span></span>
<span data-ttu-id="982dd-134">**アラート キュー**</span><span class="sxs-lookup"><span data-stu-id="982dd-134">**Alerts queue**</span></span> | <span data-ttu-id="982dd-135">組織のデバイスから生成されたアラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="982dd-135">View alerts generated from devices in your organizations.</span></span>
<span data-ttu-id="982dd-136">**自動化された調査**</span><span class="sxs-lookup"><span data-stu-id="982dd-136">**Automated investigations**</span></span> | <span data-ttu-id="982dd-137">ネットワークで行われた自動調査、アラートのトリガー、各調査の状態、調査の開始時間や調査期間などの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="982dd-137">Displays automated investigations that have been conducted in the network, triggering alert, the status of each investigation and other details such as when the investigation started and the duration of the investigation.</span></span>
<span data-ttu-id="982dd-138">**高度な検出**</span><span class="sxs-lookup"><span data-stu-id="982dd-138">**Advanced hunting**</span></span> | <span data-ttu-id="982dd-139">高度な検索を使用すると、強力な検索およびクエリ ツールを使用して、組織全体で積極的に検索および調査できます。</span><span class="sxs-lookup"><span data-stu-id="982dd-139">Advanced hunting allows you to proactively hunt and investigate across your organization using a powerful search and query tool.</span></span>
<span data-ttu-id="982dd-140">**レポート**</span><span class="sxs-lookup"><span data-stu-id="982dd-140">**Reports**</span></span> | <span data-ttu-id="982dd-141">脅威の保護、デバイスの正常性とコンプライアンス、Web 保護、および脆弱性に関するグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="982dd-141">View graphs detailing threat protection, device health and compliance, web protection, and vulnerability.</span></span>
<span data-ttu-id="982dd-142">**パートナー& API**</span><span class="sxs-lookup"><span data-stu-id="982dd-142">**Partners & APIs**</span></span> | <span data-ttu-id="982dd-143">サポートされているパートナー接続を表示し、プラットフォームの検出、調査、および脅威インテリジェンス機能を強化します。</span><span class="sxs-lookup"><span data-stu-id="982dd-143">View supported partner connections, which enhance the detection, investigation, and threat intelligence capabilities of the platform.</span></span> <span data-ttu-id="982dd-144">接続されているアプリケーション、API エクスプローラー、API 使用状況の概要、およびデータエクスポート設定を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="982dd-144">You can also view connected applications, the API explorer, API usage overview, and data export settings.</span></span>
<span data-ttu-id="982dd-145">**脅威&の管理**</span><span class="sxs-lookup"><span data-stu-id="982dd-145">**Threat & Vulnerability management**</span></span> | <span data-ttu-id="982dd-146">デバイスの Microsoft Secure Score、露出スコア、露出デバイス、脆弱なソフトウェアを表示し、セキュリティに関する推奨事項の上位に対処します。</span><span class="sxs-lookup"><span data-stu-id="982dd-146">View your Microsoft Secure Score for Devices, exposure score, exposed devices, vulnerable software, and take action on top security recommendations.</span></span>
<span data-ttu-id="982dd-147">**評価とチュートリアル**</span><span class="sxs-lookup"><span data-stu-id="982dd-147">**Evaluation and tutorials**</span></span> | <span data-ttu-id="982dd-148">テスト デバイス、攻撃シミュレーション、レポートを管理します。</span><span class="sxs-lookup"><span data-stu-id="982dd-148">Manage test devices, attack simulations, and reports.</span></span> <span data-ttu-id="982dd-149">試用版環境でのガイド付きウォークスルーを通じて、Defender for Endpoint の機能を学び、体験してください。</span><span class="sxs-lookup"><span data-stu-id="982dd-149">Learn and experience the Defender for Endpoint capabilities through a guided walk-through in a trial environment.</span></span>
<span data-ttu-id="982dd-150">**サービス正常性**</span><span class="sxs-lookup"><span data-stu-id="982dd-150">**Service health**</span></span> | <span data-ttu-id="982dd-151">Defender for Endpoint サービスの現在の状態に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="982dd-151">Provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="982dd-152">サービスの正常性が正常か、現在の問題が発生した場合に確認できます。</span><span class="sxs-lookup"><span data-stu-id="982dd-152">You'll be able to verify that the service health is healthy or if there are current issues.</span></span>
<span data-ttu-id="982dd-153">**構成管理**</span><span class="sxs-lookup"><span data-stu-id="982dd-153">**Configuration management**</span></span> | <span data-ttu-id="982dd-154">オンボード デバイス、組織のセキュリティ ベースライン、予測分析、Web 保護範囲を表示し、デバイスで攻撃表面管理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="982dd-154">Displays on-boarded devices, your organizations' security baseline, predictive analysis, web protection coverage, and allows you to perform attack surface management on your devices.</span></span>
<span data-ttu-id="982dd-155">**設定**</span><span class="sxs-lookup"><span data-stu-id="982dd-155">**Settings**</span></span> | <span data-ttu-id="982dd-156">オンボーディング中に選択した設定を表示し、業界の基本設定と保持ポリシー期間を更新できます。</span><span class="sxs-lookup"><span data-stu-id="982dd-156">Shows the settings you selected during onboarding and lets you update your industry preferences and retention policy period.</span></span> <span data-ttu-id="982dd-157">アクセス許可、API、ルール、デバイス管理、IT サービス管理、ネットワーク評価などの他の構成設定を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="982dd-157">You can also set other configuration settings such as permissions, APIs, rules, device management, IT service management, and network assessments.</span></span>
<span data-ttu-id="982dd-158">**(2) 検索、コミュニティ センター、ローカライズ、ヘルプとサポート、フィードバック**</span><span class="sxs-lookup"><span data-stu-id="982dd-158">**(2) Search, Community center, Localization,  Help and support, Feedback**</span></span> | <span data-ttu-id="982dd-159">**検索** - デバイス、ファイル、ユーザー、URL、IP、脆弱性、ソフトウェア、推奨事項で検索します。</span><span class="sxs-lookup"><span data-stu-id="982dd-159">**Search** - search by device, file, user, URL, IP, vulnerability, software, and recommendation.</span></span> </br></br> <span data-ttu-id="982dd-160">**コミュニティ センター** - コミュニティ センターにアクセスして、製品に関するエクスペリエンスを学び、共同作業し、共有します。</span><span class="sxs-lookup"><span data-stu-id="982dd-160">**Community center** - Access the Community center to learn, collaborate, and share experiences about the product.</span></span> </br></br>  <span data-ttu-id="982dd-161">**ローカライズ** - タイム ゾーンを設定します。</span><span class="sxs-lookup"><span data-stu-id="982dd-161">**Localization** - Set time zones.</span></span> </br></br>  <span data-ttu-id="982dd-162">**ヘルプとサポート** - Defender for Endpoint ガイド、Microsoft と Microsoft Premier のサポート、ライセンス情報、シミュレーション & チュートリアル、Defender for Endpoint 評価ラボにアクセスし、脅威の専門家に相談してください。</span><span class="sxs-lookup"><span data-stu-id="982dd-162">**Help and support** - Access the Defender for Endpoint guide, Microsoft and Microsoft Premier support, license information, simulations & tutorials, Defender for Endpoint evaluation lab, consult a threat expert.</span></span></br></br> <span data-ttu-id="982dd-163">**フィードバック** - 好きな操作や、より良い操作を行う方法に関するコメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="982dd-163">**Feedback** - Provide comments about what you like or what we can do better.</span></span>

> [!NOTE]
> <span data-ttu-id="982dd-164">高解像度の DPI スケーリングの問題があるデバイスについては、考えられる解決策については、「高 DPI デバイスの Windows スケーリングの [問題」](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="982dd-164">For devices with high resolution DPI scaling issues, please see [Windows scaling issues for high-DPI devices](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) for possible solutions.</span></span>

## <a name="microsoft-defender-for-endpoint-icons"></a><span data-ttu-id="982dd-165">Microsoft Defender for Endpoint アイコン</span><span class="sxs-lookup"><span data-stu-id="982dd-165">Microsoft Defender for Endpoint icons</span></span>

<span data-ttu-id="982dd-166">次の表に、ポータル全体で使用されるアイコンに関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="982dd-166">The following table provides information on the icons used all throughout the portal:</span></span>

<span data-ttu-id="982dd-167">アイコン</span><span class="sxs-lookup"><span data-stu-id="982dd-167">Icon</span></span> | <span data-ttu-id="982dd-168">説明</span><span class="sxs-lookup"><span data-stu-id="982dd-168">Description</span></span>
:---|:---
![ATP ロゴ アイコン](images/atp-logo-icon.png)| <span data-ttu-id="982dd-170">Microsoft Defender for Endpoint ロゴ</span><span class="sxs-lookup"><span data-stu-id="982dd-170">Microsoft Defender for Endpoint logo</span></span>
![アラート アイコン](images/alert-icon.png)| <span data-ttu-id="982dd-172">アラート – 高度な攻撃と相関するアクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="982dd-172">Alert – Indication of an activity correlated with advanced attacks.</span></span>
![検出アイコン](images/detection-icon.png)| <span data-ttu-id="982dd-174">検出 – マルウェアの脅威の検出を示します。</span><span class="sxs-lookup"><span data-stu-id="982dd-174">Detection – Indication of a malware threat detection.</span></span>
![アクティブな脅威アイコン](images/active-threat-icon.png)| <span data-ttu-id="982dd-176">アクティブな脅威 – 検出時にアクティブに実行される脅威。</span><span class="sxs-lookup"><span data-stu-id="982dd-176">Active threat – Threats actively executing at the time of detection.</span></span>
![修復された icon1](images/remediated-icon.png)| <span data-ttu-id="982dd-178">修復された – デバイスから削除された脅威。</span><span class="sxs-lookup"><span data-stu-id="982dd-178">Remediated – Threat removed from the device.</span></span>
![修復されていないアイコン](images/not-remediated-icon.png)| <span data-ttu-id="982dd-180">修復されない – デバイスから脅威が削除されません。</span><span class="sxs-lookup"><span data-stu-id="982dd-180">Not remediated – Threat not removed from the device.</span></span>
![Thunderbolt アイコン](images/atp-thunderbolt-icon.png)| <span data-ttu-id="982dd-182">アラート プロセス ツリーでアラートをトリガーしたイベント **を示します**。</span><span class="sxs-lookup"><span data-stu-id="982dd-182">Indicates events that triggered an alert in the **Alert process tree**.</span></span>
![デバイス アイコン](images/atp-machine-icon.png)| <span data-ttu-id="982dd-184">デバイス アイコン</span><span class="sxs-lookup"><span data-stu-id="982dd-184">Device icon</span></span>
![Microsoft Defender AV イベント アイコン](images/atp-windows-defender-av-events-icon.png)| <span data-ttu-id="982dd-186">Microsoft Defender ウイルス対策イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-186">Microsoft Defender Antivirus events</span></span>
![Application Guard イベント アイコン](images/atp-Application-Guard-events-icon.png)| <span data-ttu-id="982dd-188">Windows Defender Application Guard イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-188">Windows Defender Application Guard events</span></span>
![Device Guard イベント アイコン](images/atp-Device-Guard-events-icon.png)| <span data-ttu-id="982dd-190">Windows Defender Device Guard イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-190">Windows Defender Device Guard events</span></span>
![Exploit Guard イベント アイコン](images/atp-Exploit-Guard-events-icon.png)| <span data-ttu-id="982dd-192">Windows Defender Exploit Guard イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-192">Windows Defender Exploit Guard events</span></span>
![SmartScreen イベント アイコン](images/atp-Smart-Screen-events-icon.png)| <span data-ttu-id="982dd-194">Windows Defender SmartScreen イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-194">Windows Defender SmartScreen events</span></span>
![ファイアウォール イベント アイコン](images/atp-Firewall-events-icon.png)| <span data-ttu-id="982dd-196">Windows ファイアウォール イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-196">Windows Firewall events</span></span>
![応答アクション アイコン](images/atp-respond-action-icon.png)| <span data-ttu-id="982dd-198">応答アクション</span><span class="sxs-lookup"><span data-stu-id="982dd-198">Response action</span></span>
![プロセス イベント アイコン](images/atp-process-event-icon.png)| <span data-ttu-id="982dd-200">プロセス イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-200">Process events</span></span>
![ネットワーク通信イベント アイコン](images/atp-network-communications-icon.png)| <span data-ttu-id="982dd-202">ネットワーク イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-202">Network events</span></span>
![ファイルの観測イベント アイコン](images/atp-file-observed-icon.png)| <span data-ttu-id="982dd-204">ファイル イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-204">File  events</span></span>
![レジストリ イベント アイコン](images/atp-registry-event-icon.png)| <span data-ttu-id="982dd-206">レジストリ イベント</span><span class="sxs-lookup"><span data-stu-id="982dd-206">Registry events</span></span>
![モジュール読み込み DLL イベント アイコン](images/atp-module-load-icon.png)| <span data-ttu-id="982dd-208">DLL イベントの読み込み</span><span class="sxs-lookup"><span data-stu-id="982dd-208">Load DLL events</span></span>
![その他のイベント アイコン](images/atp-Other-events-icon.png)| <span data-ttu-id="982dd-210">その他のイベント</span><span class="sxs-lookup"><span data-stu-id="982dd-210">Other events</span></span>
![アクセス トークンの変更アイコン](images/atp-access-token-modification-icon.png)| <span data-ttu-id="982dd-212">アクセス トークンの変更</span><span class="sxs-lookup"><span data-stu-id="982dd-212">Access token modification</span></span>
![ファイル作成アイコン](images/atp-file-creation-icon.png)| <span data-ttu-id="982dd-214">ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="982dd-214">File creation</span></span>
![署名者アイコン](images/atp-signer-icon.png)| <span data-ttu-id="982dd-216">署名者</span><span class="sxs-lookup"><span data-stu-id="982dd-216">Signer</span></span>
![ファイル パス アイコン](images/atp-File-path-icon.png)| <span data-ttu-id="982dd-218">ファイル パス</span><span class="sxs-lookup"><span data-stu-id="982dd-218">File path</span></span>
![コマンド ライン アイコン](images/atp-command-line-icon.png)| <span data-ttu-id="982dd-220">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="982dd-220">Command line</span></span>
![署名されていないファイル アイコン](images/atp-unsigned-file-icon.png)| <span data-ttu-id="982dd-222">署名されていないファイル</span><span class="sxs-lookup"><span data-stu-id="982dd-222">Unsigned file</span></span>
![プロセス ツリー アイコン](images/atp-process-tree.png)| <span data-ttu-id="982dd-224">プロセス ツリー</span><span class="sxs-lookup"><span data-stu-id="982dd-224">Process tree</span></span>
![メモリ割り当てアイコン](images/atp-memory-allocation-icon.png)| <span data-ttu-id="982dd-226">メモリ割り当て</span><span class="sxs-lookup"><span data-stu-id="982dd-226">Memory allocation</span></span>
![プロセスの挿入アイコン](images/atp-process-injection.png)| <span data-ttu-id="982dd-228">プロセスの挿入</span><span class="sxs-lookup"><span data-stu-id="982dd-228">Process injection</span></span>
![Powershell コマンドの実行アイコン](images/atp-powershell-command-run-icon.png)| <span data-ttu-id="982dd-230">Powershell コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="982dd-230">Powershell command run</span></span>
![コミュニティ センターのアイコン](images/atp-community-center.png) | <span data-ttu-id="982dd-232">コミュニティ センター</span><span class="sxs-lookup"><span data-stu-id="982dd-232">Community center</span></span>
![通知アイコン](images/atp-notifications.png) | <span data-ttu-id="982dd-234">通知</span><span class="sxs-lookup"><span data-stu-id="982dd-234">Notifications</span></span>
![脅威は検出されませんでした](images/no-threats-found.png) | <span data-ttu-id="982dd-236">自動調査 - 脅威が見つかりません</span><span class="sxs-lookup"><span data-stu-id="982dd-236">Automated investigation - no threats found</span></span>
![失敗したアイコン](images/failed.png) | <span data-ttu-id="982dd-238">自動調査 - 失敗</span><span class="sxs-lookup"><span data-stu-id="982dd-238">Automated investigation - failed</span></span>
![部分的に修復されたアイコン](images/partially-investigated.png) | <span data-ttu-id="982dd-240">自動調査 - 部分的に調査</span><span class="sxs-lookup"><span data-stu-id="982dd-240">Automated investigation - partially investigated</span></span>
![システムにより終了](images/terminated-by-system.png) | <span data-ttu-id="982dd-242">自動調査 - システムによって終了</span><span class="sxs-lookup"><span data-stu-id="982dd-242">Automated investigation - terminated by system</span></span>
![保留中のアイコン](images/pending.png) | <span data-ttu-id="982dd-244">自動調査 - 保留中</span><span class="sxs-lookup"><span data-stu-id="982dd-244">Automated investigation - pending</span></span>
![実行中のアイコン](images/running.png) | <span data-ttu-id="982dd-246">自動調査 - 実行</span><span class="sxs-lookup"><span data-stu-id="982dd-246">Automated investigation - running</span></span>
![修復された icon2](images/remediated.png) | <span data-ttu-id="982dd-248">自動調査 - 修復</span><span class="sxs-lookup"><span data-stu-id="982dd-248">Automated investigation - remediated</span></span>
![部分的に調査されたアイコン](images/partially_remediated.png) | <span data-ttu-id="982dd-250">自動調査 - 部分的に修復</span><span class="sxs-lookup"><span data-stu-id="982dd-250">Automated investigation - partially remediated</span></span>
![脅威の分析情報アイコン](images/tvm_bug_icon.png) | <span data-ttu-id="982dd-252">脅威&の管理 - 脅威の分析情報</span><span class="sxs-lookup"><span data-stu-id="982dd-252">Threat & Vulnerability Management - threat insights</span></span>
![有効なアラート アイコン](images/tvm_alert_icon.png) | <span data-ttu-id="982dd-254">脅威&の管理 - アクティブなアラートの可能性</span><span class="sxs-lookup"><span data-stu-id="982dd-254">Threat & Vulnerability Management - possible active alert</span></span>
![推奨事項の分析情報アイコン](images/tvm_insight_icon.png) | <span data-ttu-id="982dd-256">脅威&の管理 - 推奨事項の分析情報</span><span class="sxs-lookup"><span data-stu-id="982dd-256">Threat & Vulnerability Management - recommendation insights</span></span>

## <a name="related-topics"></a><span data-ttu-id="982dd-257">関連項目</span><span class="sxs-lookup"><span data-stu-id="982dd-257">Related topics</span></span>

- [<span data-ttu-id="982dd-258">Microsoft Defender セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="982dd-258">Overview of Microsoft Defender Security Center</span></span>](use.md)
- [<span data-ttu-id="982dd-259">セキュリティ操作ダッシュボードの表示</span><span class="sxs-lookup"><span data-stu-id="982dd-259">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="982dd-260">[[脅威の管理] &のダッシュボードを表示する](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="982dd-260">[View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md)</span></span>
- [<span data-ttu-id="982dd-261">脅威分析ダッシュボードを表示し、推奨される軽減アクションを実行する</span><span class="sxs-lookup"><span data-stu-id="982dd-261">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
