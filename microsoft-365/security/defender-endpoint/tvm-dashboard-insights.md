---
title: ダッシュボードの分析情報 - 脅威と脆弱性の管理
description: 脅威と脆弱性管理ダッシュボードは、SecOps とセキュリティ管理者がサイバーセキュリティの脅威に対処し、組織のセキュリティの回復力を構築するのに役立ちます。
keywords: mdatp-tvm、mdatp-tvm ダッシュボード、脅威 & 脆弱性管理、脅威と脆弱性管理、リスクベースの脅威 & 脆弱性管理、セキュリティ構成、Microsoft Secure Score for Devices、露出スコア
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 594d4b5790f95abed966163e448d332467f35b51
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068755"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a><span data-ttu-id="fd38d-104">ダッシュボードの分析情報 - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="fd38d-104">Dashboard insights - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fd38d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fd38d-105">**Applies to:**</span></span>

- [<span data-ttu-id="fd38d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fd38d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fd38d-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="fd38d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="fd38d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd38d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fd38d-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fd38d-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fd38d-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="fd38d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="fd38d-111">脅威と脆弱性の管理は Defender for Endpoint のコンポーネントであり、セキュリティ管理者とセキュリティ運用チームの両方に、次の固有の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-111">Threat and vulnerability management is a component of Defender for Endpoint, and provides both security administrators and security operations teams with unique value, including:</span></span>


- <span data-ttu-id="fd38d-112">エンドポイントの脆弱性に関連したリアルタイムのエンドポイント検出と応答（EDR）の分析</span><span class="sxs-lookup"><span data-stu-id="fd38d-112">Real-time endpoint detection and response (EDR) insights correlated with endpoint vulnerabilities</span></span>
- <span data-ttu-id="fd38d-113">インシデント調査中の貴重なデバイスの脆弱性コンテキスト</span><span class="sxs-lookup"><span data-stu-id="fd38d-113">Invaluable device vulnerability context during incident investigations</span></span>
- <span data-ttu-id="fd38d-114">Microsoft Intune と Microsoft Endpoint Configuration Manager による組み込みの修復プロセス</span><span class="sxs-lookup"><span data-stu-id="fd38d-114">Built-in remediation processes through Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>  
  
<span data-ttu-id="fd38d-115">Microsoft Defender セキュリティ センターの脅威と脆弱性の管理機能を使用すると、次の [機能を使用](https://securitycenter.windows.com/) できます。</span><span class="sxs-lookup"><span data-stu-id="fd38d-115">You can use the threat and vulnerability management capability in [Microsoft Defender Security Center](https://securitycenter.windows.com/) to:</span></span>

- <span data-ttu-id="fd38d-116">露出スコアと Microsoft Secure Score for Devices を、セキュリティ上の推奨事項、ソフトウェアの脆弱性、修復アクティビティ、公開されたデバイスと共に表示する</span><span class="sxs-lookup"><span data-stu-id="fd38d-116">View you exposure score and Microsoft Secure Score for Devices, along with top security recommendations, software vulnerability, remediation activities, and exposed devices</span></span>
- <span data-ttu-id="fd38d-117">EDR インサイトとエンドポイントの脆弱性を関連付け、それらを処理する</span><span class="sxs-lookup"><span data-stu-id="fd38d-117">Correlate EDR insights with endpoint vulnerabilities and process them</span></span>
- <span data-ttu-id="fd38d-118">修復オプションを選択して修復タスクをトリアージおよび追跡する</span><span class="sxs-lookup"><span data-stu-id="fd38d-118">Select remediation options to triage and track the remediation tasks</span></span>
- <span data-ttu-id="fd38d-119">例外オプションを選択し、アクティブな例外を追跡する</span><span class="sxs-lookup"><span data-stu-id="fd38d-119">Select exception options and track active exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="fd38d-120">過去 30 日間にアクティブではないデバイスは、組織の脅威と脆弱性管理の露出スコアと Microsoft Secure Score for Devices を反映するデータには考慮されません。</span><span class="sxs-lookup"><span data-stu-id="fd38d-120">Devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management exposure score and Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="fd38d-121">脅威と脆弱性管理ダッシュボードの概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fd38d-121">Watch this video for a quick overview of what is in the threat and vulnerability management dashboard.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="fd38d-122">脅威と脆弱性の管理ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="fd38d-122">Threat and vulnerability management dashboard</span></span>

 ![Microsoft Defender for Endpoint portal](images/tvm-dashboard-devices.png)

<span data-ttu-id="fd38d-124">分野</span><span class="sxs-lookup"><span data-stu-id="fd38d-124">Area</span></span> | <span data-ttu-id="fd38d-125">説明</span><span class="sxs-lookup"><span data-stu-id="fd38d-125">Description</span></span>
:---|:---
<span data-ttu-id="fd38d-126">**選択したデバイス グループ (#/#)**</span><span class="sxs-lookup"><span data-stu-id="fd38d-126">**Selected device groups (#/#)**</span></span>   | <span data-ttu-id="fd38d-127">ダッシュボードに表示する脅威と脆弱性の管理データを、デバイス グループ別にフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-127">Filter the threat and vulnerability management data you want to see in the dashboard and cards by device groups.</span></span> <span data-ttu-id="fd38d-128">フィルターで選択した項目は、脅威と脆弱性の管理ページ全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fd38d-128">What you select in the filter applies throughout the threat and vulnerability management pages.</span></span>
[<span data-ttu-id="fd38d-129">**露出スコア**</span><span class="sxs-lookup"><span data-stu-id="fd38d-129">**Exposure score**</span></span>](tvm-exposure-score.md)   | <span data-ttu-id="fd38d-130">組織のデバイスが脅威や脆弱性にさらされている現在の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-130">See the current state of your organization's device exposure to threats and vulnerabilities.</span></span> <span data-ttu-id="fd38d-131">デバイスで検出された弱点、デバイスが侵害される可能性、組織に対するデバイスの価値、デバイスで検出された関連アラートなど、組織の露出スコアに影響を与える要因がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="fd38d-131">Several factors affect your organization's exposure score: weaknesses discovered in your devices, likelihood of your devices to be breached, value of the devices to your organization, and relevant alerts discovered with your devices.</span></span> <span data-ttu-id="fd38d-132">目標は、組織の露出スコアを下げ、より安全に行う方法です。</span><span class="sxs-lookup"><span data-stu-id="fd38d-132">The goal is to lower the exposure score of your organization to be more secure.</span></span> <span data-ttu-id="fd38d-133">スコアを減らすには、セキュリティに関する推奨事項に記載されている関連するセキュリティ構成の問題を修復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd38d-133">To reduce the score, you need to remediate the related security configuration issues listed in the security recommendations.</span></span>
[<span data-ttu-id="fd38d-134">**デバイスの Microsoft Secure Score**</span><span class="sxs-lookup"><span data-stu-id="fd38d-134">**Microsoft Secure Score for Devices**</span></span>](tvm-microsoft-secure-score-devices.md) | <span data-ttu-id="fd38d-135">組織のオペレーティング システム、アプリケーション、ネットワーク、アカウント、およびセキュリティ制御のセキュリティ体制を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd38d-135">See the security posture of the operating system, applications, network, accounts, and security controls of your organization.</span></span> <span data-ttu-id="fd38d-136">目標は、関連するセキュリティ構成の問題を修復して、デバイスのスコアを上げです。</span><span class="sxs-lookup"><span data-stu-id="fd38d-136">The goal is to remediate the related security configuration issues to increase your score for devices.</span></span> <span data-ttu-id="fd38d-137">バーを選択すると、[セキュリティの推奨事項] **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-137">Selecting the bars will take you to the **Security recommendation** page.</span></span>
<span data-ttu-id="fd38d-138">**デバイスの露出の分布**</span><span class="sxs-lookup"><span data-stu-id="fd38d-138">**Device exposure distribution**</span></span> | <span data-ttu-id="fd38d-139">露出レベルに基づいて公開されるデバイスの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-139">See how many devices are exposed based on their exposure level.</span></span> <span data-ttu-id="fd38d-140">ドーナツ グラフのセクションを選択して、[デバイス] リストページに移動し、影響を受けるデバイス名、露出レベル、リスク レベル、その他の詳細 (ドメイン、オペレーティング システム プラットフォーム、正常性状態、最後に表示された状態、タグなど) を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-140">Select a section in the doughnut chart to go to the **Devices list** page and view the affected device names, exposure level, risk level, and other details such as domain, operating system platform, its health state, when it was last seen, and its tags.</span></span>
<span data-ttu-id="fd38d-141">**セキュリティに関する推奨事項の上位**</span><span class="sxs-lookup"><span data-stu-id="fd38d-141">**Top security recommendations**</span></span> | <span data-ttu-id="fd38d-142">組織のリスクエクスポージャーと必要な緊急性に基づいて並べ替え、優先順位が付けられている照合されたセキュリティ推奨事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd38d-142">See the collated security recommendations that are sorted and prioritized based on your organization's risk exposure and the urgency that it requires.</span></span> <span data-ttu-id="fd38d-143">[ **詳細を表示]** を選択すると、一覧に残りのセキュリティ推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd38d-143">Select **Show more** to see the rest of the security recommendations in the list.</span></span> <span data-ttu-id="fd38d-144">例外 **がある推奨事項の一** 覧の [例外の表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-144">Select **Show exceptions** for the list of recommendations that have an exception.</span></span>
<span data-ttu-id="fd38d-145">**脆弱なソフトウェアの上位**</span><span class="sxs-lookup"><span data-stu-id="fd38d-145">**Top vulnerable software**</span></span> | <span data-ttu-id="fd38d-146">ネットワークのデバイスにインストールされている脆弱なソフトウェアのスタックランクのリストと、そのソフトウェアが組織の露出スコアに与える影響について、組織のソフトウェア インベントリをリアルタイムで可視化します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-146">Get real-time visibility into your organization's software inventory with a stack-ranked list of vulnerable software installed on your network's devices and how they impact your organizational exposure score.</span></span> <span data-ttu-id="fd38d-147">[ソフトウェア インベントリ]ページで、脆弱なソフトウェアリストの残りの部分を表示するには、詳細のアイテムを選択するか、[詳細を表示]**を選択** します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-147">Select an item for details or **Show more** to see the rest of the vulnerable software list in the **Software inventory** page.</span></span>
<span data-ttu-id="fd38d-148">**上位の修復アクティビティ**</span><span class="sxs-lookup"><span data-stu-id="fd38d-148">**Top remediation activities**</span></span> | <span data-ttu-id="fd38d-149">セキュリティ推奨事項から生成された修復アクティビティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-149">Track the remediation activities generated from the security recommendations.</span></span> <span data-ttu-id="fd38d-150">リスト上の各アイテムを選択して、[修復] ページで詳細を表示するか、[詳細を表示] を選択して、残りの修復アクティビティとアクティブな例外を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fd38d-150">You can select each item on the list to see the details in the **Remediation** page or select **Show more** to view the rest of the remediation activities, and active exceptions.</span></span>
<span data-ttu-id="fd38d-151">**上位の公開デバイス**</span><span class="sxs-lookup"><span data-stu-id="fd38d-151">**Top exposed devices**</span></span> | <span data-ttu-id="fd38d-152">公開されているデバイス名とその露出レベルを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-152">View exposed device names and their exposure level.</span></span> <span data-ttu-id="fd38d-153">リストからデバイス名を選択すると、デバイス ページに移動して、公開されているデバイスに関連するアラート、リスク、インシデント、セキュリティ推奨事項、インストール済みソフトウェア、および検出された脆弱性を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fd38d-153">Select a device name from the list to go to the device page where you can view the alerts, risks, incidents, security recommendations, installed software, and discovered vulnerabilities associated with the exposed devices.</span></span> <span data-ttu-id="fd38d-154">[ **詳細を表示] を** 選択して、公開されているデバイスの残りの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd38d-154">Select **Show more** to see the rest of the exposed devices list.</span></span> <span data-ttu-id="fd38d-155">デバイスリストから、タグの管理、自動調査の開始、ライブ応答セッションの開始、調査パッケージの収集、ウイルス対策スキャンの実行、アプリの実行の制限、デバイスの分離を行えます。</span><span class="sxs-lookup"><span data-stu-id="fd38d-155">From the devices list, you can manage tags, initiate automated investigations, initiate a live response session, collect an investigation package, run antivirus scan, restrict app execution, and isolate device.</span></span>

<span data-ttu-id="fd38d-156">ポータル全体で使用されるアイコンの詳細については [、「Microsoft Defender for Endpoint アイコン」を参照してください](portal-overview.md#microsoft-defender-for-endpoint-icons)。</span><span class="sxs-lookup"><span data-stu-id="fd38d-156">For more information on the icons used throughout the portal, see [Microsoft Defender for Endpoint icons](portal-overview.md#microsoft-defender-for-endpoint-icons).</span></span>


## <a name="related-topics"></a><span data-ttu-id="fd38d-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd38d-157">Related topics</span></span>

- [<span data-ttu-id="fd38d-158">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="fd38d-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="fd38d-159">露出スコア</span><span class="sxs-lookup"><span data-stu-id="fd38d-159">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="fd38d-160">デバイスの Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="fd38d-160">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="fd38d-161">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="fd38d-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="fd38d-162">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="fd38d-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="fd38d-163">イベントタイムライン</span><span class="sxs-lookup"><span data-stu-id="fd38d-163">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)

