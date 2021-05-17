---
title: 脅威と脆弱性の管理
description: この新しい機能では、エンドポイントの脆弱性と誤った構成の検出、事前設定、修復に対して、ゲームを変えるリスクベースのアプローチを使用します。
keywords: threat & 脆弱性の管理, 脅威と脆弱性の管理, Microsoft Defender for Endpoint TVM, Microsoft Defender for Endpoint-TVM, 脆弱性の管理, 脆弱性評価, 脅威と脆弱性スキャン, セキュリティで保護された構成評価, Microsoft Defender for Endpoint, endpoint の脆弱性, 次世代
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 474b8f032d32668eaea3a477da013c2b8e74019b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934167"
---
# <a name="threat-and-vulnerability-management"></a><span data-ttu-id="1ed9e-104">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="1ed9e-104">Threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1ed9e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1ed9e-105">**Applies to:**</span></span>
- [<span data-ttu-id="1ed9e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ed9e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1ed9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ed9e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="1ed9e-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1ed9e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1ed9e-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="1ed9e-110">エンドポイントの弱点を効果的に特定、評価、修復するには、健全なセキュリティ プログラムを実行し、組織のリスクを軽減する上で極めて重要です。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-110">Effectively identifying, assessing, and remediating endpoint weaknesses is pivotal in running a healthy security program and reducing organizational risk.</span></span> <span data-ttu-id="1ed9e-111">脅威と脆弱性の管理は、組織の暴露を削減し、エンドポイントの役割を強化し、組織の回復性を向上させるためのインフラストラクチャとして機能します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-111">Threat and vulnerability management serves as an infrastructure for reducing organizational exposure, hardening endpoint surface area, and increasing organizational resilience.</span></span>

<span data-ttu-id="1ed9e-112">センサーを使用して、エージェントや定期的なスキャンを必要とせずに、脆弱性と誤った構成をリアルタイムで検出します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-112">Discover vulnerabilities and misconfigurations in real time with sensors, and without the need of agents or periodic scans.</span></span> <span data-ttu-id="1ed9e-113">脅威の状況、組織内の検出、脆弱なデバイスに関する機密情報、およびビジネス コンテキストに基づいて脆弱性の優先順位を設定します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-113">It prioritizes vulnerabilities based on the threat landscape, detections in your organization, sensitive information on vulnerable devices, and business context.</span></span>

<span data-ttu-id="1ed9e-114">詳細については、このビデオをご覧脅威と脆弱性の管理。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-114">Watch this video for a quick overview of threat and vulnerability management.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a><span data-ttu-id="1ed9e-115">ワークフローのギャップを埋める</span><span class="sxs-lookup"><span data-stu-id="1ed9e-115">Bridging the workflow gaps</span></span>

<span data-ttu-id="1ed9e-116">脅威と脆弱性の管理は、リアルタイムで構築され、クラウドに対応しています。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-116">Threat and vulnerability management is built in, real time, and cloud powered.</span></span> <span data-ttu-id="1ed9e-117">Microsoft エンドポイント セキュリティ スタック、Microsoft Intelligent Security Graph、およびアプリケーション分析のナレッジ ベースと完全に統合されています。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-117">It's fully integrated with Microsoft endpoint security stack, the Microsoft Intelligent Security Graph, and the application analytics knowledge base.</span></span>  

<span data-ttu-id="1ed9e-118">脆弱性管理は、修復プロセス中にセキュリティ管理と IT 管理の間のギャップを埋める業界初のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-118">Vulnerability management is the first solution in the industry to bridge the gap between security administration and IT administration during remediation process.</span></span> <span data-ttu-id="1ed9e-119">セキュリティ タスクまたはチケットを作成するには、セキュリティ タスクとMicrosoft IntuneとMicrosoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-119">Create a security task or ticket by integrating with Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span>

### <a name="real-time-discovery"></a><span data-ttu-id="1ed9e-120">リアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="1ed9e-120">Real-time discovery</span></span>

<span data-ttu-id="1ed9e-121">エンドポイントの脆弱性と構成の誤りを検出するために、脅威と脆弱性の管理 は同じエージェントレス組み込みの Defender for Endpoint センサーを使用して、面倒なネットワーク スキャンと IT オーバーヘッドを削減します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-121">To discover endpoint vulnerabilities and misconfiguration, threat and vulnerability management uses the same agentless built-in Defender for Endpoint sensors to reduce cumbersome network scans and IT overhead.</span></span>

<span data-ttu-id="1ed9e-122">また、次の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-122">It also provides:</span></span>

- <span data-ttu-id="1ed9e-123">**リアルタイム デバイス インベントリ** - Defender for Endpoint にオンボードされたデバイスは、脆弱性とセキュリティ構成データをダッシュボードに自動的に報告してプッシュします。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-123">**Real-time device inventory** - Devices onboarded to Defender for Endpoint automatically report and push vulnerability and security configuration data to the dashboard.</span></span>
- <span data-ttu-id="1ed9e-124">**ソフトウェアと脆弱性の** 可視化 - 組織のソフトウェア インベントリへのオプティクス、インストール、アンインストール、パッチなど、ソフトウェアの変更。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-124">**Visibility into software and vulnerabilities** - Optics into the organization's software inventory, and software changes like installations, uninstalls, and patches.</span></span> <span data-ttu-id="1ed9e-125">新たに発見された脆弱性は、第 1 および第 3 者のアプリケーションに対する対処可能な軽減策の推奨事項で報告されます。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-125">Newly discovered vulnerabilities are reported with actionable mitigation recommendations for 1st and 3rd party applications.</span></span>
- <span data-ttu-id="1ed9e-126">**アプリケーション ランタイム コンテキスト** - アプリケーションの使用状況パターンを表示して、より良い事前設定と意思決定を行います。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-126">**Application runtime context** - Visibility on application usage patterns for better prioritization and decision-making.</span></span>
- <span data-ttu-id="1ed9e-127">**構成の体制** - 組織のセキュリティ構成または構成の誤りを表示します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-127">**Configuration posture** - Visibility into organizational security configuration or misconfigurations.</span></span> <span data-ttu-id="1ed9e-128">問題はダッシュボードで報告されます。セキュリティに関する推奨事項を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-128">Issues are reported in the dashboard with actionable security recommendations.</span></span>

### <a name="intelligence-driven-prioritization"></a><span data-ttu-id="1ed9e-129">インテリジェンスによる事前設定</span><span class="sxs-lookup"><span data-stu-id="1ed9e-129">Intelligence-driven prioritization</span></span>

<span data-ttu-id="1ed9e-130">脅威と脆弱性の管理は、お客様が組織に最も緊急かつ最も高いリスクを与える弱点に優先順位を付け、集中するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-130">Threat and vulnerability management helps customers prioritize and focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="1ed9e-131">セキュリティに関する推奨事項と動的な脅威とビジネス コンテキストを融合します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-131">It fuses security recommendations with dynamic threat and business context:</span></span>

- <span data-ttu-id="1ed9e-132">**新しい攻撃を野生で** 公開する - セキュリティ推奨事項の事前設定を動的に調整します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-132">**Exposing emerging attacks in the wild** - Dynamically aligns the prioritization of security recommendations.</span></span> <span data-ttu-id="1ed9e-133">脅威と脆弱性の管理は、最もリスクの高い、新しい脅威で現在悪用されている脆弱性に焦点を当て、</span><span class="sxs-lookup"><span data-stu-id="1ed9e-133">Threat and vulnerability management focuses on vulnerabilities currently being exploited in the wild and emerging threats that pose the highest risk.</span></span>
- <span data-ttu-id="1ed9e-134">**アクティブな侵害を特定** する - 脅威と脆弱性の管理とEDRを関連付け、組織内のアクティブな侵害で悪用される脆弱性を優先順位付けします。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-134">**Pinpointing active breaches** - Correlates threat and vulnerability management and EDR insights to prioritize vulnerabilities being exploited in an active breach within the organization.</span></span>
- <span data-ttu-id="1ed9e-135">**価値の高い資産の** 保護 - ビジネスクリティカルなアプリケーション、機密データ、または価値の高いユーザーを使用して、公開されているデバイスを特定します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-135">**Protecting high-value assets** - Identify the exposed devices with business-critical applications, confidential data, or high-value users.</span></span>

### <a name="seamless-remediation"></a><span data-ttu-id="1ed9e-136">シームレスな修復</span><span class="sxs-lookup"><span data-stu-id="1ed9e-136">Seamless remediation</span></span>

<span data-ttu-id="1ed9e-137">脅威と脆弱性の管理により、セキュリティ管理者と IT 管理者はシームレスに共同作業して問題を修復できます。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-137">Threat and vulnerability management allows security administrators and IT administrators to collaborate seamlessly to remediate issues.</span></span>

- <span data-ttu-id="1ed9e-138">**IT に送信される修復要求**- 特定のセキュリティ推奨事項からMicrosoft Intune修復タスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-138">**Remediation requests sent to IT** - Create a remediation task in Microsoft Intune from a specific security recommendation.</span></span> <span data-ttu-id="1ed9e-139">この機能を他の IT セキュリティ管理プラットフォームに拡張する予定です。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-139">We plan to expand this capability to other IT security management platforms.</span></span>
- <span data-ttu-id="1ed9e-140">**代替の軽減** 策 - ソフトウェアの脆弱性に関連するリスクを軽減できる構成の変更など、追加の軽減策に関する洞察を得る。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-140">**Alternate mitigations** - Gain insights on additional mitigations, such as configuration changes that can reduce risk associated with software vulnerabilities.</span></span>
- <span data-ttu-id="1ed9e-141">**リアルタイムの修復状態** - 組織全体の修復アクティビティの状態と進捗状況をリアルタイムで監視します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-141">**Real-time remediation status** - Real-time monitoring of the status and progress of remediation activities across the organization.</span></span>

## <a name="threat-and-vulnerability-management-walk-through"></a><span data-ttu-id="1ed9e-142">脅威と脆弱性の管理のウォークスルー</span><span class="sxs-lookup"><span data-stu-id="1ed9e-142">Threat and vulnerability management walk-through</span></span>

<span data-ttu-id="1ed9e-143">このビデオでは、このビデオを参照して、詳細な脅威と脆弱性の管理。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-143">Watch this video for a comprehensive walk-through of threat and vulnerability management.</span></span>

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a><span data-ttu-id="1ed9e-144">ナビゲーション ウィンドウ </span><span class="sxs-lookup"><span data-stu-id="1ed9e-144">Navigation pane</span></span>

<span data-ttu-id="1ed9e-145">分野</span><span class="sxs-lookup"><span data-stu-id="1ed9e-145">Area</span></span> | <span data-ttu-id="1ed9e-146">説明</span><span class="sxs-lookup"><span data-stu-id="1ed9e-146">Description</span></span>
:---|:---
<span data-ttu-id="1ed9e-147">**ダッシュボード**</span><span class="sxs-lookup"><span data-stu-id="1ed9e-147">**Dashboard**</span></span>   | <span data-ttu-id="1ed9e-148">組織の露出スコア、Microsoft Secure Score for Devices、デバイスの露出分布、トップ セキュリティ推奨事項、脆弱なソフトウェアの上位、トップ修復アクティビティ、および公開されているデバイス データの上位レベルのビューを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-148">Get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span>
[<span data-ttu-id="1ed9e-149">**セキュリティ上の推奨事項**</span><span class="sxs-lookup"><span data-stu-id="1ed9e-149">**Security recommendations**</span></span>](tvm-security-recommendation.md) | <span data-ttu-id="1ed9e-150">セキュリティに関する推奨事項と関連する脅威情報の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-150">See the list of security recommendations and related threat information.</span></span> <span data-ttu-id="1ed9e-151">リストからアイテムを選択すると、フライアウト パネルが開き、脆弱性の詳細、ソフトウェア ページを開くリンク、修復と例外のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-151">When you select an item from the list, a flyout panel opens with vulnerability details, a link to open the software page, and remediation and exception options.</span></span> <span data-ttu-id="1ed9e-152">デバイスがエンドポイント経由で参加し、Defender for Endpoint で Intune 接続を有効にしている場合Azure Active Directory Intune でチケットを開く方法もできます。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-152">You can also open a ticket in Intune if your devices are joined through Azure Active Directory and you've enabled your Intune connections in Defender for Endpoint.</span></span>
[<span data-ttu-id="1ed9e-153">**修復**</span><span class="sxs-lookup"><span data-stu-id="1ed9e-153">**Remediation**</span></span>](tvm-remediation.md) | <span data-ttu-id="1ed9e-154">作成した修復アクティビティと推奨事項の例外を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-154">See remediation activities you've created and recommendation exceptions.</span></span>
[<span data-ttu-id="1ed9e-155">**ソフトウェア インベントリ**</span><span class="sxs-lookup"><span data-stu-id="1ed9e-155">**Software inventory**</span></span>](tvm-software-inventory.md) | <span data-ttu-id="1ed9e-156">組織内の脆弱なソフトウェアの一覧と、弱点と脅威に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-156">See the list of vulnerable software in your organization, along with weakness and threat information.</span></span>
[<span data-ttu-id="1ed9e-157">**弱点**</span><span class="sxs-lookup"><span data-stu-id="1ed9e-157">**Weaknesses**</span></span>](tvm-weaknesses.md) | <span data-ttu-id="1ed9e-158">組織の一般的な脆弱性と露出 (CVEs) の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-158">See the list of common vulnerabilities and exposures (CVEs) in your organization.</span></span>
[<span data-ttu-id="1ed9e-159">**イベントのタイムライン**</span><span class="sxs-lookup"><span data-stu-id="1ed9e-159">**Event timeline**</span></span>](threat-and-vuln-mgt-event-timeline.md) | <span data-ttu-id="1ed9e-160">組織のリスクに影響を与える可能性があるイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-160">View events that may impact your organization's risk.</span></span>

## <a name="apis"></a><span data-ttu-id="1ed9e-161">API</span><span class="sxs-lookup"><span data-stu-id="1ed9e-161">APIs</span></span>

<span data-ttu-id="1ed9e-162">関連脅威と脆弱性の管理 API 呼び出しを実行して、ワークフロー脆弱性の管理自動化します。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-162">Run threat and vulnerability management-related API calls to automate vulnerability management workflows.</span></span> <span data-ttu-id="1ed9e-163">詳細については、[この Microsoft Tech のブログCommunityを参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-163">Learn more from this [Microsoft Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).</span></span>

<span data-ttu-id="1ed9e-164">関連する API については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed9e-164">See the following articles for related APIs:</span></span>

- [<span data-ttu-id="1ed9e-165">サポート対象 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="1ed9e-165">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="1ed9e-166">コンピューター API</span><span class="sxs-lookup"><span data-stu-id="1ed9e-166">Machine APIs</span></span>](machine.md)
- [<span data-ttu-id="1ed9e-167">推奨事項 API</span><span class="sxs-lookup"><span data-stu-id="1ed9e-167">Recommendation APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="1ed9e-168">API のスコア付け</span><span class="sxs-lookup"><span data-stu-id="1ed9e-168">Score APIs</span></span>](score.md)
- [<span data-ttu-id="1ed9e-169">ソフトウェア API</span><span class="sxs-lookup"><span data-stu-id="1ed9e-169">Software APIs</span></span>](software.md)
- [<span data-ttu-id="1ed9e-170">脆弱性 API</span><span class="sxs-lookup"><span data-stu-id="1ed9e-170">Vulnerability APIs</span></span>](vulnerability.md)
- [<span data-ttu-id="1ed9e-171">マシンとソフトウェアによる脆弱性の一覧表示</span><span class="sxs-lookup"><span data-stu-id="1ed9e-171">List vulnerabilities by machine and software</span></span>](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a><span data-ttu-id="1ed9e-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ed9e-172">See also</span></span>

- [<span data-ttu-id="1ed9e-173">サポート対象オペレーティング システムとプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="1ed9e-173">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="1ed9e-174">脅威と脆弱性の管理ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="1ed9e-174">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="1ed9e-175">ブログ: Microsoft の脅威&脆弱性管理は、何千人もの顧客が脆弱性をリアルタイムで検出、優先順位付け、修復するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="1ed9e-175">BLOG: Microsoft's Threat & Vulnerability Management now helps thousands of customers to discover, prioritize, and remediate vulnerabilities in real time</span></span>](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
