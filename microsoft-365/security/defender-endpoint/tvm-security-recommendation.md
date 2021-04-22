---
title: 脅威と脆弱性の管理によるセキュリティに関する推奨事項
description: 脅威、侵害される可能性、および脅威と脆弱性の管理における価値によって優先順位付けされた、アクション可能なセキュリティの推奨事項を取得します。
keywords: 脅威と脆弱性の管理、Microsoft Defender for Endpoint tvm セキュリティ推奨事項、サイバーセキュリティの推奨事項、アクション可能なセキュリティの推奨事項
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: af22bac911339de9c2e02df24a77c1889a33d43a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933735"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="95207-104">セキュリティに関する推奨事項 - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="95207-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95207-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="95207-105">**Applies to:**</span></span>

- [<span data-ttu-id="95207-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="95207-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="95207-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="95207-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="95207-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95207-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="95207-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="95207-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="95207-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="95207-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="95207-111">組織内で特定されたサイバーセキュリティの弱点は、アクション可能なセキュリティ推奨事項にマップされ、影響によって優先順位が付けされます。</span><span class="sxs-lookup"><span data-stu-id="95207-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="95207-112">優先順位付けされた推奨事項は、脆弱性を軽減または修復し、コンプライアンスを推進する時間を短縮するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95207-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="95207-113">各セキュリティ推奨事項には、アクション可能な修復手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="95207-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="95207-114">タスク管理を支援するために、Microsoft Intune と Microsoft Endpoint Configuration Manager を使用して推奨事項を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="95207-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="95207-115">脅威の状況が変化すると、環境から情報を継続的に収集する際に、推奨事項も変更されます。</span><span class="sxs-lookup"><span data-stu-id="95207-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="95207-116">新しい脆弱性イベントに関する電子メールを取得するには [、「Configure vulnerability email notifications in Microsoft Defender for Endpoint」を参照してください。](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="95207-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="95207-117">メカニズム</span><span class="sxs-lookup"><span data-stu-id="95207-117">How it works</span></span>

<span data-ttu-id="95207-118">組織内の各デバイスは、3 つの重要な要素に基づいてスコア付けされます。</span><span class="sxs-lookup"><span data-stu-id="95207-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="95207-119">**脅威** - 組織のデバイスの脆弱性と悪用の特徴と侵害履歴。</span><span class="sxs-lookup"><span data-stu-id="95207-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="95207-120">これらの要因に基づいて、セキュリティに関する推奨事項には、アクティブなアラート、継続的な脅威キャンペーン、対応する脅威分析レポートへの対応するリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95207-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="95207-121">**侵害の可能性** - 組織のセキュリティ体制と脅威に対する回復力</span><span class="sxs-lookup"><span data-stu-id="95207-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="95207-122">**ビジネス価値** - 組織の資産、重要なプロセス、および知的財産</span><span class="sxs-lookup"><span data-stu-id="95207-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="95207-123">[セキュリティの推奨事項] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="95207-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="95207-124">[セキュリティの推奨事項] ページにアクセスするには、次のいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="95207-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="95207-125">Microsoft Defender セキュリティ センターの脅威と脆弱性 [の管理ナビゲーション メニュー](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="95207-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="95207-126">脅威と脆弱性管理ダッシュボードのセキュリティ [に関する推奨事項の上位](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="95207-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="95207-127">関連するセキュリティに関する推奨事項を次の場所で表示します。</span><span class="sxs-lookup"><span data-stu-id="95207-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="95207-128">[ソフトウェア] ページ</span><span class="sxs-lookup"><span data-stu-id="95207-128">Software page</span></span>
- <span data-ttu-id="95207-129">[デバイス] ページ</span><span class="sxs-lookup"><span data-stu-id="95207-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="95207-130">ナビゲーション メニュー</span><span class="sxs-lookup"><span data-stu-id="95207-130">Navigation menu</span></span>

<span data-ttu-id="95207-131">[脅威と脆弱性の管理] ナビゲーション メニューに移動し、[セキュリティの推奨事項 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95207-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="95207-132">このページには、組織で見つかった脅威と脆弱性に関するセキュリティ推奨事項の一覧が含まれている。</span><span class="sxs-lookup"><span data-stu-id="95207-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="95207-133">脅威と脆弱性管理ダッシュボードのセキュリティに関する推奨事項の上位</span><span class="sxs-lookup"><span data-stu-id="95207-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="95207-134">セキュリティ管理者として特定の日に、脅威と脆弱性管理ダッシュボードを見て[](tvm-dashboard-insights.md)[、Microsoft Secure Score for](tvm-microsoft-secure-score-devices.md) [](tvm-exposure-score.md) Devices と並べて露出スコアを確認できます。</span><span class="sxs-lookup"><span data-stu-id="95207-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="95207-135">目標は、組織の脆弱性による露出を低くし、組織のデバイス セキュリティを強化して、サイバーセキュリティの脅威攻撃に対する回復力を高める方法です。</span><span class="sxs-lookup"><span data-stu-id="95207-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="95207-136">セキュリティに関する推奨事項の上位一覧は、その目標を達成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95207-136">The top security recommendations list can help you achieve that goal.</span></span>

![4 つのセキュリティ推奨事項を含むトップ セキュリティ推奨事項カードの例。](images/top-security-recommendations350.png)

<span data-ttu-id="95207-138">上位のセキュリティ推奨事項は、前のセクションで説明した重要な要因 (脅威、侵害される可能性、および価値) に基づいて優先順位付けされた改善の機会を示しています。</span><span class="sxs-lookup"><span data-stu-id="95207-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="95207-139">推奨事項を選択すると、詳細を示すセキュリティの推奨事項ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95207-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="95207-140">セキュリティに関する推奨事項の概要</span><span class="sxs-lookup"><span data-stu-id="95207-140">Security recommendations overview</span></span>

<span data-ttu-id="95207-141">推奨事項、見つかった弱点の数、関連するコンポーネント、脅威の分析情報、公開されているデバイスの数、状態、修復の種類、修復アクティビティ、露出スコアと Microsoft Secure Score for Devices への影響、および関連タグを表示します。</span><span class="sxs-lookup"><span data-stu-id="95207-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="95207-142">露出デバイスグラフの **色は** 、傾向の変化に合って変化します。</span><span class="sxs-lookup"><span data-stu-id="95207-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="95207-143">公開されているデバイスの数が増えている場合、色は赤に変わります。</span><span class="sxs-lookup"><span data-stu-id="95207-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="95207-144">公開されているデバイスの数が減った場合、グラフの色は緑に変わります。</span><span class="sxs-lookup"><span data-stu-id="95207-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="95207-145">脅威と脆弱性の管理では、最大 **30** 日前に使用していたデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95207-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="95207-146">これは、他の Microsoft Defender for Endpoint とは異なります。デバイスが 7 日間以上使用されていない場合は、"非アクティブ" 状態になっています。</span><span class="sxs-lookup"><span data-stu-id="95207-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![セキュリティに関する推奨事項のランディング ページの例。](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="95207-148">アイコン</span><span class="sxs-lookup"><span data-stu-id="95207-148">Icons</span></span>

<span data-ttu-id="95207-149">役に立つアイコンは、次の点に注意を迅速に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="95207-149">Useful icons also quickly call your attention to:</span></span>
- ![ターゲットに当たる矢印](images/tvm_alert_icon.png) <span data-ttu-id="95207-151">有効なアラートの可能性</span><span class="sxs-lookup"><span data-stu-id="95207-151">possible active alerts</span></span>
- ![赤いバグ](images/tvm_bug_icon.png) <span data-ttu-id="95207-153">関連するパブリックエクスプロイト</span><span class="sxs-lookup"><span data-stu-id="95207-153">associated public exploits</span></span>
- ![電球](images/tvm_insight_icon.png) <span data-ttu-id="95207-155">推奨事項の分析情報</span><span class="sxs-lookup"><span data-stu-id="95207-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="95207-156">セキュリティに関する推奨事項のオプションを確認する</span><span class="sxs-lookup"><span data-stu-id="95207-156">Explore security recommendation options</span></span>

<span data-ttu-id="95207-157">調査または処理するセキュリティ推奨事項を選択します。</span><span class="sxs-lookup"><span data-stu-id="95207-157">Select the security recommendation that you want to investigate or process.</span></span>

![セキュリティ推奨事項のフライアウト ページの例。](images/secrec-flyouteolsw.png)

<span data-ttu-id="95207-159">フライアウトから、次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="95207-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="95207-160">**[ソフトウェア ページを開** く] - ソフトウェア ページを開いて、ソフトウェアのコンテキストと配布方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="95207-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="95207-161">この情報には、脅威コンテキスト、関連する推奨事項、検出された弱点、公開されたデバイスの数、検出された脆弱性、ソフトウェアがインストールされているデバイスの名前と詳細、バージョンの配布が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95207-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="95207-162">[**修復オプション**](tvm-remediation.md) - 修復要求を送信して、IT 管理者がピックアップしてアドレス指定するためのチケットを Microsoft Intune で開きます。</span><span class="sxs-lookup"><span data-stu-id="95207-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="95207-163">[修復] ページで修復アクティビティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="95207-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="95207-164">[**例外オプション**](tvm-exception.md) - まだ問題を修復できない場合は、例外を送信し、正当化を提供し、例外期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="95207-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="95207-165">デバイスでソフトウェアの変更が行われた場合、通常、データがセキュリティ ポータルに反映されるのに 2 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="95207-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="95207-166">ただし、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95207-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="95207-167">構成の変更には、4 ~ 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95207-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="95207-168">デバイスの露出や影響の変化を調査する</span><span class="sxs-lookup"><span data-stu-id="95207-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="95207-169">公開されているデバイスの数が大きく増加したり、組織の露出スコアや Microsoft Secure Score for Devices への影響が急激に増加する場合は、そのセキュリティ推奨事項を調査する価値があります。</span><span class="sxs-lookup"><span data-stu-id="95207-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="95207-170">推奨事項と [ソフトウェアを開 **く] ページを選択する**</span><span class="sxs-lookup"><span data-stu-id="95207-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="95207-171">[イベント タイムライン **] タブを** 選択すると、新しい脆弱性や新しいパブリックエクスプロイトなど、そのソフトウェアに関連する影響を受けのあるすべてのイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95207-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="95207-172">イベントタイムラインの詳細</span><span class="sxs-lookup"><span data-stu-id="95207-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="95207-173">修復要求の提出など、増加または組織の露出に対処する方法を決定する</span><span class="sxs-lookup"><span data-stu-id="95207-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="95207-174">修復の要求</span><span class="sxs-lookup"><span data-stu-id="95207-174">Request remediation</span></span>

<span data-ttu-id="95207-175">脅威と脆弱性管理の修復機能は、修復要求ワークフローを通じて、セキュリティ管理者と IT 管理者の間のギャップを埋め合わせています。</span><span class="sxs-lookup"><span data-stu-id="95207-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="95207-176">IT 管理者に対して、セキュリティの推奨事項ページから Intune への脆弱性の修復を要求できるセキュリティ管理者。</span><span class="sxs-lookup"><span data-stu-id="95207-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="95207-177">修復オプションの詳細</span><span class="sxs-lookup"><span data-stu-id="95207-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="95207-178">修復を要求する方法</span><span class="sxs-lookup"><span data-stu-id="95207-178">How to request remediation</span></span>

<span data-ttu-id="95207-179">修復を要求するセキュリティ推奨事項を選択し、[修復オプション] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95207-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="95207-180">フォームに入力し、[要求の送信] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95207-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="95207-181">[修復] [**ページに**](tvm-remediation.md) 移動して、修復要求の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="95207-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="95207-182">修復を要求する方法の詳細</span><span class="sxs-lookup"><span data-stu-id="95207-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="95207-183">例外ファイル</span><span class="sxs-lookup"><span data-stu-id="95207-183">File for exception</span></span>

<span data-ttu-id="95207-184">推奨事項が現時点では関連しない場合の修復要求の代わりに、推奨事項の例外を作成できます。</span><span class="sxs-lookup"><span data-stu-id="95207-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="95207-185">例外の詳細</span><span class="sxs-lookup"><span data-stu-id="95207-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="95207-186">"例外処理" アクセス許可を持つユーザーだけが例外を追加できます。</span><span class="sxs-lookup"><span data-stu-id="95207-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="95207-187">[RBAC の役割について詳しくは、次のページを参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="95207-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="95207-188">推奨事項に対して例外が作成されると、推奨事項はアクティブではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="95207-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="95207-189">推奨事項の状態が [完全な例外] **または [部分的な** 例外] (デバイス **グループ** 別) に変更されます。</span><span class="sxs-lookup"><span data-stu-id="95207-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="95207-190">例外を作成する方法</span><span class="sxs-lookup"><span data-stu-id="95207-190">How to create an exception</span></span>

<span data-ttu-id="95207-191">例外を作成するセキュリティ推奨事項を選択し、[例外オプション] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95207-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

!["例外オプション" のボタンがセキュリティ推奨事項のフライアウト内の場所である場所を表示します。](images/tvm-exception-options.png)

<span data-ttu-id="95207-193">フォームに入力して送信します。</span><span class="sxs-lookup"><span data-stu-id="95207-193">Fill out the form and submit.</span></span> <span data-ttu-id="95207-194">すべての例外 (現在と過去) を表示するには、[脅威 [](tvm-remediation.md)**&** の脆弱性管理] メニューの [修復] ページに移動し、[例外] タブを選択します。例外を作成する方法の詳細について説明 [します](tvm-exception.md#create-an-exception)。</span><span class="sxs-lookup"><span data-stu-id="95207-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="95207-195">レポートの不正確さ</span><span class="sxs-lookup"><span data-stu-id="95207-195">Report inaccuracy</span></span>

<span data-ttu-id="95207-196">あいまいで不正確、不完全、または既に修復済みのセキュリティ推奨情報が表示された場合は、誤検知を報告できます。</span><span class="sxs-lookup"><span data-stu-id="95207-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="95207-197">セキュリティの推奨事項を開きます。</span><span class="sxs-lookup"><span data-stu-id="95207-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="95207-198">報告するセキュリティ推奨事項の横にある 3 つの点を選択し、[不正確なレポート] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95207-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![[不正確なレポート] ボタンがセキュリティ推奨事項のフライアウト内にある場所を表示します。](images/report-inaccuracy500.png)

3. <span data-ttu-id="95207-200">フライアウト ウィンドウで、ドロップダウン メニューから不正確なカテゴリを選択し、電子メール アドレスを入力し、不正確に関する詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="95207-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="95207-201">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95207-201">Select **Submit**.</span></span> <span data-ttu-id="95207-202">フィードバックは、脅威と脆弱性管理の専門家に直ちに送信されます。</span><span class="sxs-lookup"><span data-stu-id="95207-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="95207-203">関連記事</span><span class="sxs-lookup"><span data-stu-id="95207-203">Related articles</span></span>

- [<span data-ttu-id="95207-204">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="95207-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="95207-205">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="95207-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="95207-206">暴露スコア</span><span class="sxs-lookup"><span data-stu-id="95207-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="95207-207">デバイス向けの Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="95207-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="95207-208">脆弱性を修復する</span><span class="sxs-lookup"><span data-stu-id="95207-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="95207-209">セキュリティに関する推奨事項の例外を作成および表示する</span><span class="sxs-lookup"><span data-stu-id="95207-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="95207-210">イベントのタイムライン</span><span class="sxs-lookup"><span data-stu-id="95207-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
