---
title: 脅威の分析を使用して、新たな脅威を追跡し対応する
ms.reviewer: ''
description: 新たな脅威と攻撃の手法と、それらを停止する方法について説明します。 組織への影響を評価し、組織の回復力を評価します。
keywords: 脅威分析、リスク評価、Microsoft 365 Defender、M365D、軽減状態、セキュリティで保護された構成、Microsoft Defender for Office 365、Microsoft Defender for Office 365 脅威分析、MDO 脅威分析、統合 MDE および MDO 脅威分析データ、脅威分析データ統合、統合 Microsoft 365 Defender 脅威分析
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c03dfef28744e2ee565c25d921902b8d11ecb7a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290245"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="454de-105">脅威の分析を使用して、新たな脅威を追跡し対応する</span><span class="sxs-lookup"><span data-stu-id="454de-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="454de-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="454de-106">**Applies to:**</span></span>
- <span data-ttu-id="454de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="454de-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="454de-108">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="454de-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="454de-109">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="454de-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="454de-110">脅威分析は、Microsoft のセキュリティ研究者による製品内脅威インテリジェンス ソリューションで、セキュリティ チームが次の新たな脅威に直面しながら、可能な限り効率的に対応するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="454de-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="454de-111">アクティブな脅威アクターとそのキャンペーン</span><span class="sxs-lookup"><span data-stu-id="454de-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="454de-112">人気のある新しい攻撃手法</span><span class="sxs-lookup"><span data-stu-id="454de-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="454de-113">重大な脆弱性</span><span class="sxs-lookup"><span data-stu-id="454de-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="454de-114">一般的な攻撃の表面</span><span class="sxs-lookup"><span data-stu-id="454de-114">Common attack surfaces</span></span>
- <span data-ttu-id="454de-115">一般的なマルウェア</span><span class="sxs-lookup"><span data-stu-id="454de-115">Prevalent malware</span></span>

<span data-ttu-id="454de-116">この短いビデオでは、脅威分析が最新の脅威の追跡と停止に役立つ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="454de-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="454de-117">脅威分析には、Microsoft 365 セキュリティ ポータルのナビゲーション バーの左上から、または組織の上位脅威を示す専用のダッシュボード カードからアクセスできます。アクティブなキャンペーンや進行中のキャンペーンを可視化し、脅威分析を通じて何を行うのかを知ることにより、セキュリティ運用チームに情報に基づいた意思決定を行う際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="454de-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![脅威分析ダッシュボードのイメージ](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="454de-119">_脅威分析にアクセスする場所_</span><span class="sxs-lookup"><span data-stu-id="454de-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="454de-120">より高度な敵対者と新しい脅威が頻繁かつ一般に出現する中で、以下を迅速に実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="454de-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="454de-121">新たな脅威を特定して対応する</span><span class="sxs-lookup"><span data-stu-id="454de-121">Identify and react to emerging threats</span></span>
- <span data-ttu-id="454de-122">現在攻撃を受け取っている場合の詳細</span><span class="sxs-lookup"><span data-stu-id="454de-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="454de-123">資産に対する脅威の影響を評価する</span><span class="sxs-lookup"><span data-stu-id="454de-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="454de-124">脅威に対する回復力または暴露を確認する</span><span class="sxs-lookup"><span data-stu-id="454de-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="454de-125">脅威を停止または格納するために実行できる軽減、回復、または防止のアクションを特定する</span><span class="sxs-lookup"><span data-stu-id="454de-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="454de-126">各レポートは、追跡された脅威の分析と、その脅威から防御する方法に関する広範なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="454de-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="454de-127">また、ネットワークからのデータも組み込まれており、脅威がアクティブかどうか、適切な保護が適用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="454de-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="454de-128">脅威分析ダッシュボードの表示</span><span class="sxs-lookup"><span data-stu-id="454de-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="454de-129">脅威分析ダッシュボード[(security.microsoft.com/threatanalytics3)](https://security.microsoft.com/threatanalytics3)は、組織に最も関連性の高いレポートを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="454de-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="454de-130">次のセクションの脅威の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="454de-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="454de-131">**最新の脅威**— 最新の公開または更新された脅威レポートと、アクティブなアラートと解決されたアラートの数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="454de-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="454de-132">**影響の大きな脅威**:組織に最も大きな影響を与える脅威を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="454de-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="454de-133">このセクションでは、最初にアクティブなアラートと解決済みアラートの数が最も多い脅威の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="454de-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="454de-134">**脅威の概要**— アクティブなアラートと解決済みアラートを使用して脅威の数を表示することで、すべての追跡された脅威の全体的な影響を提供します。</span><span class="sxs-lookup"><span data-stu-id="454de-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="454de-135">ダッシュボードから脅威を選択して、その脅威のレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="454de-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![脅威分析ダッシュボードのスクリーンショット](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="454de-137">_脅威分析ダッシュボード。検索アイコンをクリックして、読み取る脅威分析レポートに関連するキーワードをキー設定することもできます。_</span><span class="sxs-lookup"><span data-stu-id="454de-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="454de-138">脅威分析レポートの表示</span><span class="sxs-lookup"><span data-stu-id="454de-138">View a threat analytics report</span></span>

<span data-ttu-id="454de-139">各脅威分析レポートには、次のいくつかのセクションの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="454de-139">Each threat analytics report provides information in several sections:</span></span>

- [<span data-ttu-id="454de-140">**概要**</span><span class="sxs-lookup"><span data-stu-id="454de-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses)
- [<span data-ttu-id="454de-141">**アナリスト レポート**</span><span class="sxs-lookup"><span data-stu-id="454de-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="454de-142">**関連するインシデント**</span><span class="sxs-lookup"><span data-stu-id="454de-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="454de-143">**影響を受け取ったアセット**</span><span class="sxs-lookup"><span data-stu-id="454de-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="454de-144">**メールの試行の防止**</span><span class="sxs-lookup"><span data-stu-id="454de-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="454de-145">**軽減策**</span><span class="sxs-lookup"><span data-stu-id="454de-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="454de-146">概要: 脅威をすばやく理解し、影響を評価し、防御を確認する</span><span class="sxs-lookup"><span data-stu-id="454de-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="454de-147">[ **概要]** セクションには、詳細なアナリスト レポートのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="454de-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="454de-148">また、組織に対する脅威の影響と、構成が正しく設定されていないデバイスや未パッチのデバイスによる露出を強調するグラフも提供されます。</span><span class="sxs-lookup"><span data-stu-id="454de-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![脅威分析レポートの概要セクションのイメージ](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="454de-150">_脅威分析レポートの概要セクション_</span><span class="sxs-lookup"><span data-stu-id="454de-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="454de-151">組織への影響を評価する</span><span class="sxs-lookup"><span data-stu-id="454de-151">Assess impact on your organization</span></span>

<span data-ttu-id="454de-152">各レポートには、脅威の組織への影響に関する情報を提供するように設計されたグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="454de-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>

- <span data-ttu-id="454de-153">**関連するインシデント**— 追跡された脅威が組織に与える影響の概要と、次のデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="454de-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="454de-154">アクティブなアラートの数と、関連付けられているアクティブ なインシデントの数</span><span class="sxs-lookup"><span data-stu-id="454de-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="454de-155">アクティブ なインシデントの重大度</span><span class="sxs-lookup"><span data-stu-id="454de-155">Severity of active incidents</span></span>
- <span data-ttu-id="454de-156">**時間の間のアラート**— 関連するアクティブアラートと解決済みアラート **の時間** の数を示します。</span><span class="sxs-lookup"><span data-stu-id="454de-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="454de-157">解決済みアラートの数は、組織が脅威に関連付けられたアラートに応答する時間を示します。</span><span class="sxs-lookup"><span data-stu-id="454de-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="454de-158">理想的には、グラフは数日以内に解決されたアラートを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="454de-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="454de-159">**影響を受け取** ったアセット : 現在、追跡される脅威に関連付けられているアクティブなアラートが 1 つ以上ある個別のデバイスと電子メール アカウント (メールボックス) の数を示します。</span><span class="sxs-lookup"><span data-stu-id="454de-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="454de-160">アラートは、脅威メールを受信したメールボックスに対してトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="454de-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="454de-161">組織レベルとユーザー レベルの両方のポリシーで、脅威メールの配信を引き起こす上書きを確認します。</span><span class="sxs-lookup"><span data-stu-id="454de-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="454de-162">**[メールの試行を** 防止する] — 配信前にブロックされた過去 7 日間のメールの数、または迷惑メール フォルダーへの配信の回数を示します。</span><span class="sxs-lookup"><span data-stu-id="454de-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="454de-163">セキュリティの回復力と姿勢を確認する</span><span class="sxs-lookup"><span data-stu-id="454de-163">Review security resilience and posture</span></span>

<span data-ttu-id="454de-164">各レポートには、組織が特定の脅威に対する回復力の概要を示すグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="454de-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>

- <span data-ttu-id="454de-165">**セキュリティで保護された構成** 状態 —構成が誤ったセキュリティ設定を持つデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="454de-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="454de-166">脅威を軽減するために推奨されるセキュリティ設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="454de-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="454de-167">デバイスがすべての追跡 **設定を** 適用している _場合、_ デバイスは Secure と見なされます。</span><span class="sxs-lookup"><span data-stu-id="454de-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="454de-168">**脆弱性の修正プログラムの状態**:脆弱なデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="454de-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="454de-169">脅威によって悪用される脆弱性に対処するために、セキュリティ更新プログラムまたはパッチを適用します。</span><span class="sxs-lookup"><span data-stu-id="454de-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

#### <a name="view-reports-per-threat-tags"></a><span data-ttu-id="454de-170">脅威タグごとにレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="454de-170">View reports per threat tags</span></span>

<span data-ttu-id="454de-171">脅威レポートリストをフィルター処理し、特定の脅威タグ (カテゴリ) またはレポートの種類に従って最も関連性の高いレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="454de-171">You can filter the threat report list and view the most relevant reports according to a specific threat tag (category) or a report type.</span></span>

- <span data-ttu-id="454de-172">**脅威タグ**— 特定の脅威カテゴリに従って最も関連性の高いレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="454de-172">**Threat tags**—assist you in viewing the most relevant reports according to a specific threat category.</span></span> <span data-ttu-id="454de-173">たとえば、ランサムウェアに関連するレポートすべてです。</span><span class="sxs-lookup"><span data-stu-id="454de-173">For example, all reports related to ransomware.</span></span>
- <span data-ttu-id="454de-174">**レポートの種類**- 特定のレポートの種類に応じて最も関連性の高いレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="454de-174">**Report types**—assist you in viewing the most relevant reports according to a specific report type.</span></span> <span data-ttu-id="454de-175">たとえば、ツールとテクニックをカバーするレポートすべてです。</span><span class="sxs-lookup"><span data-stu-id="454de-175">For example, all reports that cover tools and techniques.</span></span> 
- <span data-ttu-id="454de-176">**フィルター**— 脅威レポートの一覧を効率的に確認し、特定の脅威タグまたはレポートの種類に基づいてビューをフィルター処理する場合に役立つ。</span><span class="sxs-lookup"><span data-stu-id="454de-176">**Filters**—assist you in efficiently reviewing the threat report list and filtering the view based on a specific threat tag or report type.</span></span> <span data-ttu-id="454de-177">たとえば、ランサムウェアカテゴリに関連する脅威レポート、または脆弱性をカバーする脅威レポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="454de-177">For example, review all threat reports related to ransomware category, or threat reports that cover vulnerabilities.</span></span>

##### <a name="how-does-it-work"></a><span data-ttu-id="454de-178">どのような仕組みですか?</span><span class="sxs-lookup"><span data-stu-id="454de-178">How does it work?</span></span>

<span data-ttu-id="454de-179">Microsoft Threat Intelligence チームは、各脅威レポートに脅威タグを追加しました。</span><span class="sxs-lookup"><span data-stu-id="454de-179">The Microsoft Threat Intelligence team has added threat tags to each threat report:</span></span>

- <span data-ttu-id="454de-180">次の 4 つの脅威タグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="454de-180">Four threat tags are now available:</span></span>
  - <span data-ttu-id="454de-181">ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="454de-181">Ransomware</span></span>
  - <span data-ttu-id="454de-182">フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="454de-182">Phishing</span></span>
  - <span data-ttu-id="454de-183">脆弱性</span><span class="sxs-lookup"><span data-stu-id="454de-183">Vulnerability</span></span>
  - <span data-ttu-id="454de-184">アクティビティ グループ</span><span class="sxs-lookup"><span data-stu-id="454de-184">Activity group</span></span>
- <span data-ttu-id="454de-185">脅威タグは、脅威分析ページの上部に表示され、各タグの下で使用可能なレポート数のカウンターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="454de-185">Threat tags are presented at the top of the threat analytics page, with counters for the number of available reports under each tag.</span></span>

  ![脅威タグ](../../media/threat-analytics/ta-threattags-mtp.png)

- <span data-ttu-id="454de-187">リストは、脅威タグで並べ替えすることもできます。</span><span class="sxs-lookup"><span data-stu-id="454de-187">The list can also be sorted by threat tags:</span></span>

  ![lists](../../media/threat-analytics//ta-taglist-mtp.png)

- <span data-ttu-id="454de-189">フィルターは、脅威タグとレポートの種類ごとに使用できます。</span><span class="sxs-lookup"><span data-stu-id="454de-189">Filters are available per threat tag and report type:</span></span>

  ![フィルター](../../media/threat-analytics/ta-threattag-filters-mtp.png)

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="454de-191">アナリスト レポート: Microsoft セキュリティ研究者から専門家の分析情報を取得する</span><span class="sxs-lookup"><span data-stu-id="454de-191">Analyst report: Get expert insight from Microsoft security researchers</span></span>

<span data-ttu-id="454de-192">[ **アナリスト レポート] セクション** で、詳細なエキスパートの書き込みについて説明します。</span><span class="sxs-lookup"><span data-stu-id="454de-192">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="454de-193">ほとんどのレポートには、MITRE ATT&CK フレームワークにマップされた戦術や手法、推奨事項の網羅的なリスト、強力な脅威検出ガイダンスなど、攻撃チェーンの詳細[](advanced-hunting-overview.md)な説明が記載されています。</span><span class="sxs-lookup"><span data-stu-id="454de-193">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="454de-194">アナリスト レポートの詳細</span><span class="sxs-lookup"><span data-stu-id="454de-194">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="454de-195">関連インシデント: 関連するインシデントの表示と管理</span><span class="sxs-lookup"><span data-stu-id="454de-195">Related incidents: View and manage related incidents</span></span>

<span data-ttu-id="454de-196">[ **関連インシデント] タブ** には、追跡された脅威に関連するすべてのインシデントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="454de-196">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="454de-197">インシデントを割り当てるか、各インシデントにリンクされたアラートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="454de-197">You can assign incidents or manage alerts linked to each incident.</span></span> 


![脅威分析レポートの関連インシデント セクションのイメージ](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="454de-199">_脅威分析レポートの関連インシデント セクション_</span><span class="sxs-lookup"><span data-stu-id="454de-199">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="454de-200">影響を受け取ったアセット: 影響を受け取ったデバイスとメールボックスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="454de-200">Impacted assets: Get list of impacted devices and mailboxes</span></span>

<span data-ttu-id="454de-201">アセットは、アクティブで未解決のアラートの影響を受けた場合に影響を受けたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="454de-201">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="454de-202">[ **影響を受け取ったアセット]** タブには、影響を受け取るアセットの次の種類が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="454de-202">The **Impacted assets** tab lists the following types of impacted assets:</span></span>

- <span data-ttu-id="454de-203">**影響を受け**、Microsoft Defender for Endpoint アラートが未解決のエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="454de-203">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="454de-204">これらのアラートは、通常、既知の脅威インジケーターとアクティビティの目撃情報に対して発生します。</span><span class="sxs-lookup"><span data-stu-id="454de-204">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="454de-205">**影響を受けたメールボックス**—Microsoft Defender が警告を受け取った電子メール メッセージを受信したメールボックスOffice 365します。</span><span class="sxs-lookup"><span data-stu-id="454de-205">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="454de-206">通常、アラートをトリガーするほとんどのメッセージはブロックされますが、ユーザーレベルまたは組織レベルのポリシーはフィルターを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="454de-206">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![脅威分析レポートの影響を受け取ったアセット セクションのイメージ](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="454de-208">_脅威分析レポートの影響を受け取ったアセット セクション_</span><span class="sxs-lookup"><span data-stu-id="454de-208">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="454de-209">電子メールの試行を防止する: ブロックまたは迷惑メールの脅威メールを表示する</span><span class="sxs-lookup"><span data-stu-id="454de-209">Prevented email attempts: View blocked or junked threat emails</span></span>

<span data-ttu-id="454de-210">Microsoft Defender for Office 365、悪意のあるリンクや添付ファイルを含む既知の脅威インジケーターを含む電子メールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="454de-210">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="454de-211">場合によっては、疑わしいコンテンツをチェックするプロアクティブ フィルターメカニズムによって、脅威メールが迷惑メール フォルダーに送信される場合があります。</span><span class="sxs-lookup"><span data-stu-id="454de-211">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="454de-212">いずれの場合も、デバイス上で脅威がマルウェア コードを起動する可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="454de-212">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="454de-213">[**メールの試行を** 防止する] タブには、配信前にブロックされたメール、または Microsoft Defender によって迷惑メール フォルダーに送信されたメールOffice 365。</span><span class="sxs-lookup"><span data-stu-id="454de-213">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![脅威分析レポートの [電子メール試行の防止] セクションのイメージ](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="454de-215">_脅威分析レポートの [メールの試行の防止] セクション_</span><span class="sxs-lookup"><span data-stu-id="454de-215">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="454de-216">軽減策: 軽減策の一覧とデバイスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="454de-216">Mitigations: Review list of mitigations and the status of your devices</span></span>

<span data-ttu-id="454de-217">[軽減 **策] セクション** で、脅威に対する組織の回復力を高めるのに役立つ具体的なアクション可能な推奨事項の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="454de-217">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="454de-218">追跡される軽減策の一覧には、次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="454de-218">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="454de-219">**セキュリティ更新** プログラム —オンボード デバイスで見つかった脆弱性に対するサポートされているソフトウェア セキュリティ更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="454de-219">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="454de-220">**サポートされているセキュリティ構成**</span><span class="sxs-lookup"><span data-stu-id="454de-220">**Supported security configurations**</span></span>
  - <span data-ttu-id="454de-221">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="454de-221">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="454de-222">望ましくない可能性のあるアプリケーション (PUA) 保護</span><span class="sxs-lookup"><span data-stu-id="454de-222">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="454de-223">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="454de-223">Real-time protection</span></span>

<span data-ttu-id="454de-224">このセクションの軽減情報には、脅威と脆弱性の管理からの[](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)データが組み込まれており、レポート内のさまざまなリンクからの詳細なドリルダウン情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="454de-224">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

![セキュリティで保護された構成の詳細を示す脅威分析レポートの軽減セクションのイメージ](../../media/threat-analytics/ta_mitigations_mtp.png)

![脆弱性の詳細を示す脅威分析レポートの軽減セクションの画像](../../media/threat-analytics/ta_mitigations_mtp2.png)

<span data-ttu-id="454de-227">_脅威分析レポートの [軽減策] セクション_</span><span class="sxs-lookup"><span data-stu-id="454de-227">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="454de-228">その他のレポートの詳細と制限事項</span><span class="sxs-lookup"><span data-stu-id="454de-228">Additional report details and limitations</span></span>

> [!NOTE]
> <span data-ttu-id="454de-229">統合セキュリティ エクスペリエンスの一環として、脅威分析は Microsoft Defender for Endpoint だけでなく、E5 ライセンス所有者向け Microsoft Defender Officeも利用できます。</span><span class="sxs-lookup"><span data-stu-id="454de-229">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
>
> <span data-ttu-id="454de-230">Microsoft 365 セキュリティ ポータル (Microsoft 365 Defender) を使用していない場合は、Microsoft Defender セキュリティ センター ポータル (Microsoft Defender for Endpoint) でレポートの詳細 (microsoft Defender for Office データなし) も確認できます。</span><span class="sxs-lookup"><span data-stu-id="454de-230">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span>

<span data-ttu-id="454de-231">脅威分析レポートにアクセスするには、特定の役割とアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="454de-231">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="454de-232">詳細[については、「役割ベースのアクセス制御における](custom-roles.md)カスタム ロール」を参照Microsoft 365 Defender参照してください。</span><span class="sxs-lookup"><span data-stu-id="454de-232">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>

- <span data-ttu-id="454de-233">アラート、インシデント、または影響を受けたアセット データを表示するには、Office または Microsoft Defender for Endpoint アラート データ、または両方に対する Microsoft Defender へのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="454de-233">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
- <span data-ttu-id="454de-234">電子メールの試行が防止されたのを表示するには、Microsoft Defender に対するアクセス許可を持ち、Officeする必要があります。</span><span class="sxs-lookup"><span data-stu-id="454de-234">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
- <span data-ttu-id="454de-235">軽減策を表示するには、Microsoft Defender for Endpoint でデータ脅威と脆弱性の管理アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="454de-235">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="454de-236">脅威分析データを見る場合は、次の要素を覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="454de-236">When looking at the threat analytics data, remember the following factors:</span></span>

- <span data-ttu-id="454de-237">グラフには、追跡される軽減策だけが反映されます。</span><span class="sxs-lookup"><span data-stu-id="454de-237">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="454de-238">グラフに表示されない追加の軽減策については、レポートの概要を確認してください。</span><span class="sxs-lookup"><span data-stu-id="454de-238">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="454de-239">軽減策は、完全な復元を保証するものではありません。</span><span class="sxs-lookup"><span data-stu-id="454de-239">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="454de-240">提供される軽減策は、回復性を向上させるために必要な最善のアクションを反映しています。</span><span class="sxs-lookup"><span data-stu-id="454de-240">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="454de-241">デバイスは、サービスにデータを送信していない場合は、"使用不可" としてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="454de-241">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="454de-242">ウイルス対策関連の統計情報は、ユーザー設定Microsoft Defender ウイルス対策されます。</span><span class="sxs-lookup"><span data-stu-id="454de-242">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="454de-243">サードパーティのウイルス対策ソリューションを使用するデバイスは、"公開" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="454de-243">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="454de-244">関連項目</span><span class="sxs-lookup"><span data-stu-id="454de-244">Related topics</span></span>

- [<span data-ttu-id="454de-245">高度な検索で脅威を事前に検出する</span><span class="sxs-lookup"><span data-stu-id="454de-245">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- <span data-ttu-id="454de-246">[[アナリスト レポート] セクションについて](threat-analytics-analyst-reports.md)</span><span class="sxs-lookup"><span data-stu-id="454de-246">[Understand the analyst report section](threat-analytics-analyst-reports.md)</span></span>
- [<span data-ttu-id="454de-247">セキュリティの弱点と露出を評価して解決する</span><span class="sxs-lookup"><span data-stu-id="454de-247">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
