---
title: Microsoft Defender ATP の脅威分析を使用して、新たな脅威を追跡して対応する
ms.reviewer: ''
description: 新たな脅威と攻撃の手法と、それらを停止する方法について説明します。 組織への影響を評価し、組織の回復力を評価します。
keywords: 脅威分析、リスク評価、OS 軽減、マイクロコード軽減、軽減状態
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 853a862556825e714bb06e51839f9c026e0cc0e0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501188"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="2a4cb-105">脅威の分析を使用して、新たな脅威を追跡し対応する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a4cb-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2a4cb-106">**Applies to:**</span></span>
- [<span data-ttu-id="2a4cb-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2a4cb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2a4cb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a4cb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a4cb-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="2a4cb-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a4cb-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2a4cb-111">より高度な敵対者と新しい脅威が頻繁かつ一般に出現する中で、以下を迅速に実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="2a4cb-112">新しい脅威の影響を評価する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="2a4cb-113">脅威に対する回復力または暴露を確認する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="2a4cb-114">脅威を停止または格納するために実行できるアクションを特定する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="2a4cb-115">脅威分析は、以下を含む、最も関連性の高い脅威をカバーする Microsoft の専門家のセキュリティ研究者からの一連のレポートです。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="2a4cb-116">アクティブな脅威アクターとそのキャンペーン</span><span class="sxs-lookup"><span data-stu-id="2a4cb-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="2a4cb-117">人気のある新しい攻撃手法</span><span class="sxs-lookup"><span data-stu-id="2a4cb-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="2a4cb-118">重大な脆弱性</span><span class="sxs-lookup"><span data-stu-id="2a4cb-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="2a4cb-119">一般的な攻撃の表面</span><span class="sxs-lookup"><span data-stu-id="2a4cb-119">Common attack surfaces</span></span>
- <span data-ttu-id="2a4cb-120">一般的なマルウェア</span><span class="sxs-lookup"><span data-stu-id="2a4cb-120">Prevalent malware</span></span>

<span data-ttu-id="2a4cb-121">各レポートは、脅威の詳細な分析と、その脅威から防御する方法に関する広範なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="2a4cb-122">また、ネットワークからのデータも組み込まれており、脅威がアクティブかどうか、適切な保護が適用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="2a4cb-123">この短いビデオでは、脅威分析が最新の脅威の追跡と停止に役立つ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="2a4cb-124">脅威分析ダッシュボードの表示</span><span class="sxs-lookup"><span data-stu-id="2a4cb-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="2a4cb-125">脅威分析ダッシュボードは、組織に最も関連性の高いレポートにアクセスする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="2a4cb-126">次のセクションの脅威の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="2a4cb-127">**最新の脅威**— 最新の公開された脅威レポートと、アクティブなアラートと解決済みアラートを含むデバイスの数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="2a4cb-128">**影響の大きな脅威**:組織に最も大きな影響を与えた脅威を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="2a4cb-129">このセクションでは、アクティブなアラートを持つデバイスの数によって脅威をランク付けします。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="2a4cb-130">**脅威の概要**— アクティブなアラートと解決済みアラートを含む脅威の数を表示することで、追跡された脅威の全体的な影響を示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="2a4cb-131">ダッシュボードから脅威を選択して、その脅威のレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![脅威分析ダッシュボードのイメージ](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="2a4cb-133">脅威分析レポートの表示</span><span class="sxs-lookup"><span data-stu-id="2a4cb-133">View a threat analytics report</span></span>

<span data-ttu-id="2a4cb-134">各脅威分析レポートには、概要、**アナリスト** レポート、および軽減策の 3 つの **セクションで情報\*\*\*\*が提供されます**。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="2a4cb-135">概要: 脅威をすばやく理解し、影響を評価し、防御を確認する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="2a4cb-136">[ **概要]** セクションには、詳細なアナリスト レポートのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="2a4cb-137">また、組織に対する脅威の影響と、構成が正しく設定されていないデバイスや未パッチのデバイスによる露出を強調するグラフも提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="2a4cb-138">![脅威分析レポートの脅威分析レポートの概要セクションの ](images/ta-overview.png)
 _概要セクションのイメージ_</span><span class="sxs-lookup"><span data-stu-id="2a4cb-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="2a4cb-139">組織への影響を評価する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-139">Assess the impact to your organization</span></span>
<span data-ttu-id="2a4cb-140">各レポートには、脅威の組織への影響に関する情報を提供するように設計されたグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="2a4cb-141">**アラートを含むデバイス**—脅威の影響を受け取った個別のデバイスの現在の数を示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="2a4cb-142">デバイスは、その脅威に関連付けられているアラートが少なくとも 1 つある場合はアクティブに分類され、デバイス上の脅威に関連付けられているすべてのアラートが解決されている場合は解決されます。 </span><span class="sxs-lookup"><span data-stu-id="2a4cb-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="2a4cb-143">**時間の間にアラートが発生した** デバイスは、アクティブなアラートと解決済みアラートを持つ個別のデバイスの数 **を** 示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="2a4cb-144">解決済みアラートの数は、組織が脅威に関連付けられたアラートに応答する時間を示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="2a4cb-145">理想的には、グラフは数日以内に解決されたアラートを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="2a4cb-146">セキュリティの回復力と姿勢を確認する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-146">Review security resilience and posture</span></span>
<span data-ttu-id="2a4cb-147">各レポートには、組織が特定の脅威に対する回復力の概要を示すグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="2a4cb-148">**セキュリティ構成の状態**:脅威の軽減に役立つ推奨セキュリティ設定を適用したデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="2a4cb-149">デバイスがすべての追跡 **設定を** 適用している _場合、_ デバイスは Secure と見なされます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="2a4cb-150">**脆弱性の修正プログラムの状態**:脅威によって悪用される脆弱性に対処するセキュリティ更新プログラムまたはパッチを適用したデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="2a4cb-151">アナリスト レポート: Microsoft セキュリティ研究者から専門家の分析情報を取得する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="2a4cb-152">[アナリスト レポート **] セクションに移動** して、詳細なエキスパートの書き込みを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="2a4cb-153">ほとんどのレポートには、MITRE ATT&CK フレームワークにマップされた戦術や手法、推奨事項の網羅的なリスト、強力な脅威検出ガイダンスなど、攻撃チェーンの詳細[](advanced-hunting-overview.md)な説明が記載されています。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="2a4cb-154">アナリスト レポートの詳細</span><span class="sxs-lookup"><span data-stu-id="2a4cb-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="2a4cb-155">軽減策: 軽減策の一覧とデバイスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="2a4cb-156">[軽減 **策] セクション** で、脅威に対する組織の回復力を高めるのに役立つ具体的なアクション可能な推奨事項の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="2a4cb-157">追跡される軽減策の一覧には、次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="2a4cb-158">**セキュリティ更新** プログラム -脆弱性に対するセキュリティ更新プログラムまたはパッチの展開</span><span class="sxs-lookup"><span data-stu-id="2a4cb-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="2a4cb-159">**Microsoft Defender ウイルス対策の設定**</span><span class="sxs-lookup"><span data-stu-id="2a4cb-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="2a4cb-160">セキュリティ インテリジェンスのバージョン</span><span class="sxs-lookup"><span data-stu-id="2a4cb-160">Security intelligence version</span></span>
  - <span data-ttu-id="2a4cb-161">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="2a4cb-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="2a4cb-162">望ましくない可能性のあるアプリケーション (PUA) 保護</span><span class="sxs-lookup"><span data-stu-id="2a4cb-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="2a4cb-163">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="2a4cb-163">Real-time protection</span></span>
 
<span data-ttu-id="2a4cb-164">このセクションの軽減情報には、脅威と[](next-gen-threat-and-vuln-mgt.md)脆弱性管理のデータが組み込まれており、レポート内のさまざまなリンクからの詳細なドリルダウン情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="2a4cb-165">![脅威分析レポートの [脅威分析レポートの軽減策] セクションの ](images/ta-mitigations.png)
 _[軽減策] セクションのイメージ_</span><span class="sxs-lookup"><span data-stu-id="2a4cb-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="2a4cb-166">その他のレポートの詳細と制限事項</span><span class="sxs-lookup"><span data-stu-id="2a4cb-166">Additional report details and limitations</span></span>
<span data-ttu-id="2a4cb-167">レポートを使用する場合は、次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="2a4cb-168">データの範囲は、役割ベースのアクセス制御 (RBAC) スコープに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="2a4cb-169">アクセスできるグループ内のデバイスの [状態が表示されます](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="2a4cb-170">グラフには、追跡される軽減策だけが反映されます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="2a4cb-171">グラフに表示されない追加の軽減策については、レポートの概要を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="2a4cb-172">軽減策は、完全な復元を保証するものではありません。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="2a4cb-173">提供される軽減策は、回復性を向上させるために必要な最善のアクションを反映しています。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="2a4cb-174">デバイスは、サービスにデータを送信していない場合は、"使用不可" としてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="2a4cb-175">ウイルス対策関連の統計情報は、Microsoft Defender ウイルス対策の設定に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="2a4cb-176">サードパーティのウイルス対策ソリューションを使用するデバイスは、"公開" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a4cb-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a4cb-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a4cb-177">Related topics</span></span>
- [<span data-ttu-id="2a4cb-178">高度な検索で脅威を事前に検出する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- <span data-ttu-id="2a4cb-179">[[アナリスト レポート] セクションについて](threat-analytics-analyst-reports.md)</span><span class="sxs-lookup"><span data-stu-id="2a4cb-179">[Understand the analyst report section](threat-analytics-analyst-reports.md)</span></span>
- [<span data-ttu-id="2a4cb-180">セキュリティの弱点と露出を評価して解決する</span><span class="sxs-lookup"><span data-stu-id="2a4cb-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)