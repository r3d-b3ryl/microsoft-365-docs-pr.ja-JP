---
title: Microsoft Defender for Endpoint in Microsoft 365 Defender
description: ユーザーから Defender への変更Microsoft Defender セキュリティ センター Microsoft 365する
keywords: Microsoft 365 Defender、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: b43b7c99c6585e8610d34f3c4e5b372fb1c829a2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842628"
---
# <a name="microsoft-defender-for-endpoint-in-microsoft-365-defender"></a><span data-ttu-id="75211-104">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75211-104">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="75211-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="75211-105">**Applies to:**</span></span>

- [<span data-ttu-id="75211-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75211-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="75211-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="75211-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="quick-reference"></a><span data-ttu-id="75211-108">クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="75211-108">Quick reference</span></span>

<span data-ttu-id="75211-109">次の図と表に、Defender と Defender の間のナビゲーションMicrosoft Defender セキュリティ センター示Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="75211-109">The image and the table below lists the changes in navigation between the Microsoft Defender Security Center and Microsoft 365 Defender.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="75211-110">![移動先のイメージ](../../media/mde-m3d-security-center.png)</span><span class="sxs-lookup"><span data-stu-id="75211-110">![Image of what moved to where](../../media/mde-m3d-security-center.png)</span></span>

| <span data-ttu-id="75211-111">Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="75211-111">Microsoft Defender Security Center</span></span> | <span data-ttu-id="75211-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75211-112">Microsoft 365 Defender</span></span> |
|---------|---------|
| <span data-ttu-id="75211-113">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="75211-113">Dashboards</span></span> <ul><li><span data-ttu-id="75211-114">セキュリティ操作</span><span class="sxs-lookup"><span data-stu-id="75211-114">Security Operations</span></span></li><li><span data-ttu-id="75211-115">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="75211-115">Threat Analytics</span></span></li></ul>  |<span data-ttu-id="75211-116">ホーム</span><span class="sxs-lookup"><span data-stu-id="75211-116">Home</span></span> <ul><li><span data-ttu-id="75211-117">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="75211-117">Threat analytics</span></span></li></ul>   |
| <span data-ttu-id="75211-118">インシデント</span><span class="sxs-lookup"><span data-stu-id="75211-118">Incidents</span></span> | <span data-ttu-id="75211-119">インシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="75211-119">Incidents & alerts</span></span> |
| <span data-ttu-id="75211-120">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="75211-120">Device inventory</span></span> | <span data-ttu-id="75211-121">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="75211-121">Device inventory</span></span> |
| <span data-ttu-id="75211-122">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="75211-122">Alerts queue</span></span> | <span data-ttu-id="75211-123">インシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="75211-123">Incidents & alerts</span></span> |
| <span data-ttu-id="75211-124">自動化された調査</span><span class="sxs-lookup"><span data-stu-id="75211-124">Automated investigations</span></span> | <span data-ttu-id="75211-125">アクション センター</span><span class="sxs-lookup"><span data-stu-id="75211-125">Action center</span></span> |
| <span data-ttu-id="75211-126">高度な検出</span><span class="sxs-lookup"><span data-stu-id="75211-126">Advanced hunting</span></span> | <span data-ttu-id="75211-127">検索</span><span class="sxs-lookup"><span data-stu-id="75211-127">Hunting</span></span> |
| <span data-ttu-id="75211-128">レポート</span><span class="sxs-lookup"><span data-stu-id="75211-128">Reports</span></span> | <span data-ttu-id="75211-129">レポート</span><span class="sxs-lookup"><span data-stu-id="75211-129">Reports</span></span> |
| <span data-ttu-id="75211-130">パートナー& API</span><span class="sxs-lookup"><span data-stu-id="75211-130">Partners & APIs</span></span> | <span data-ttu-id="75211-131">パートナー& API</span><span class="sxs-lookup"><span data-stu-id="75211-131">Partners & APIs</span></span> |
| <span data-ttu-id="75211-132">脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="75211-132">Threat & Vulnerability Management</span></span> | <span data-ttu-id="75211-133">脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="75211-133">Vulnerability management</span></span> |
| <span data-ttu-id="75211-134">評価とチュートリアル</span><span class="sxs-lookup"><span data-stu-id="75211-134">Evaluation and tutorials</span></span> | <span data-ttu-id="75211-135">評価&チュートリアル</span><span class="sxs-lookup"><span data-stu-id="75211-135">Evaluation & tutorials</span></span> |
| <span data-ttu-id="75211-136">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="75211-136">Configuration management</span></span> | <span data-ttu-id="75211-137">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="75211-137">Configuration management</span></span> |
| <span data-ttu-id="75211-138">設定</span><span class="sxs-lookup"><span data-stu-id="75211-138">Settings</span></span> | <span data-ttu-id="75211-139">設定</span><span class="sxs-lookup"><span data-stu-id="75211-139">Settings</span></span> | 

<span data-ttu-id="75211-140">Defender のMicrosoft 365[強化](overview-security-center.md)された機能は、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能 [https://security.microsoft.com](https://security.microsoft.com) を組み合わせた機能です。</span><span class="sxs-lookup"><span data-stu-id="75211-140">The improved [Microsoft 365 Defender](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="75211-141">これにより、既存の Microsoft セキュリティ ポータルの機能が統合され、Microsoft Defender セキュリティ センターコンプライアンス センター Office 365セキュリティ &されます。</span><span class="sxs-lookup"><span data-stu-id="75211-141">This  brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="75211-142">この記事では、Microsoft Defender セキュリティ センター Defender の変更点と改善点の一部について説明Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="75211-142">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in Microsoft 365 Defender.</span></span> <span data-ttu-id="75211-143">ただし、注意が必要な新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="75211-143">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="75211-144">これまで[、Microsoft Defender セキュリティ センターは](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)Microsoft Defender for Endpoint のホームでした。</span><span class="sxs-lookup"><span data-stu-id="75211-144">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75211-145">Enterpriseチームは、セキュリティ チームを使用して、潜在的な高度な永続的な脅威アクティビティやデータ侵害に関するアラートの監視と対応を支援しています。</span><span class="sxs-lookup"><span data-stu-id="75211-145">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="75211-146">Microsoft 365 Defender は、ポータルの数を減らすのに役立つ、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。</span><span class="sxs-lookup"><span data-stu-id="75211-146">To help reduce the number of portals, Microsoft 365 Defender will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="75211-147">microsoft Defender for Endpoint in Microsoft 365 Defender は[、Microsoft Defender](mssp-access.md)セキュリティ センターでアクセスを許可するのと同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセス許可をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="75211-147">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75211-148">Defender に表示される内容Microsoft 365現在のサブスクリプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="75211-148">What you see in Microsoft 365 Defender depends on your current subscriptions.</span></span> <span data-ttu-id="75211-149">たとえば、Microsoft Defender for Office 365 のライセンスを持Office 365場合、[電子メール & コラボレーション] セクションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="75211-149">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

> [!Note]
> <span data-ttu-id="75211-150">Microsoft 365Defender は次の場合は使用できません。</span><span class="sxs-lookup"><span data-stu-id="75211-150">Microsoft 365 Defender is not available for:</span></span>
>- <span data-ttu-id="75211-151">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="75211-151">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="75211-152">米国 Government Community Cloud高 (GCC高)</span><span class="sxs-lookup"><span data-stu-id="75211-152">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="75211-153">米国国防総省</span><span class="sxs-lookup"><span data-stu-id="75211-153">US Department of Defense</span></span>
>- <span data-ttu-id="75211-154">商用ライセンスを持つすべての米国政府機関</span><span class="sxs-lookup"><span data-stu-id="75211-154">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="75211-155">Defender を見Microsoft 365します [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="75211-155">Take a look at Microsoft 365 Defender: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="75211-156">メリットの詳細: Defender の概要[Microsoft 365する](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="75211-156">Learn more about the benefits: [Overview of Microsoft 365 Defender](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="75211-157">変更内容</span><span class="sxs-lookup"><span data-stu-id="75211-157">What's changed</span></span>

<span data-ttu-id="75211-158">次の表は、Defender と Defender の間のMicrosoft Defender セキュリティ センター参照Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="75211-158">This table is a quick reference of the changes between the Microsoft Defender Security Center and Microsoft 365 Defender.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="75211-159">アラートとアクション</span><span class="sxs-lookup"><span data-stu-id="75211-159">Alerts and actions</span></span>

| <span data-ttu-id="75211-160">分野</span><span class="sxs-lookup"><span data-stu-id="75211-160">Area</span></span> | <span data-ttu-id="75211-161">変更の説明</span><span class="sxs-lookup"><span data-stu-id="75211-161">Description of change</span></span> |
|---------|---------|
| [<span data-ttu-id="75211-162">インシデント&アラート</span><span class="sxs-lookup"><span data-stu-id="75211-162">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="75211-163">Defender Microsoft 365、すべてのエンドポイント、電子メール、および ID でインシデントとアラートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="75211-163">In Microsoft 365 Defender, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="75211-164">関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスを統合しました。</span><span class="sxs-lookup"><span data-stu-id="75211-164">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="75211-165">詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="75211-165">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="75211-166">検索</span><span class="sxs-lookup"><span data-stu-id="75211-166">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="75211-167">Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含める場合は、自動的に Id テーブルと電子メール テーブルMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="75211-167">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="75211-168">対応するアラートは、Defender のMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="75211-168">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="75211-169">これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="75211-169">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="75211-170">高度 `DeviceAlertEvents` な検索のテーブルは、Defender ではMicrosoft 365できません。</span><span class="sxs-lookup"><span data-stu-id="75211-170">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="75211-171">Microsoft 365 Defender でデバイス固有のアラート情報を照会するには、and テーブルを使用して、さまざまなソース セットからのさらに多くの情報に `AlertInfo` `AlertEvidence` 対応できます。</span><span class="sxs-lookup"><span data-stu-id="75211-171">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="75211-172">[DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)なしで書き込みクエリを実行して、次のデバイス関連のクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="75211-172">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="75211-173">アクション センター</span><span class="sxs-lookup"><span data-stu-id="75211-173">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="75211-174">自動調査と修復アクションに続いて実行された保留中のアクションと完了したアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="75211-174">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="75211-175">以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行される修復アクションの保留中および完了したアクションが一覧表示され、自動調査にはアラートと状態が一覧表示されました。</span><span class="sxs-lookup"><span data-stu-id="75211-175">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="75211-176">Defender の強化Microsoft 365、アクション センターでは、電子メール、デバイス、およびユーザー間の修復アクションと調査を 1 つの場所にまとめます。</span><span class="sxs-lookup"><span data-stu-id="75211-176">In the  improved Microsoft 365 Defender, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="75211-177">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="75211-177">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="75211-178">ナビゲーション バーの上部に移動し、検出と使用を容易にします。</span><span class="sxs-lookup"><span data-stu-id="75211-178">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="75211-179">エンドポイントと電子メールとコラボレーションの両方に関する脅威情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="75211-179">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="75211-180">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="75211-180">Endpoints</span></span>

| <span data-ttu-id="75211-181">分野</span><span class="sxs-lookup"><span data-stu-id="75211-181">Area</span></span> | <span data-ttu-id="75211-182">変更の説明</span><span class="sxs-lookup"><span data-stu-id="75211-182">Description of change</span></span> |
|---------|---------|
|<span data-ttu-id="75211-183">検索</span><span class="sxs-lookup"><span data-stu-id="75211-183">Search</span></span>   |  <span data-ttu-id="75211-184">見出しの代わりに、Microsoft Defender for Endpoint 検索バーが [エンドポイント] セクションの下を移動しています。</span><span class="sxs-lookup"><span data-stu-id="75211-184">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="75211-185">引き続きデバイス、ファイル、ユーザー、URL、IPs、脆弱性、ソフトウェア、推奨事項を検索できます。</span><span class="sxs-lookup"><span data-stu-id="75211-185">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="75211-186">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="75211-186">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="75211-187">これは、セキュリティ操作ダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="75211-187">This is your security operations dashboard.</span></span> <span data-ttu-id="75211-188">アクティブなアラートがトリガーされた数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、およびユーザーの重大度レベルの概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75211-188">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="75211-189">また、センサーの問題が発生したデバイス、サービス全体の正常性、未解決のアラートが検出された方法も確認できます。</span><span class="sxs-lookup"><span data-stu-id="75211-189">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="75211-190">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="75211-190">Device inventory</span></span> | <span data-ttu-id="75211-191">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="75211-191">No changes.</span></span> |
|[<span data-ttu-id="75211-192">脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="75211-192">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="75211-193">ナビゲーション ウィンドウに収まる名前が短縮されました。</span><span class="sxs-lookup"><span data-stu-id="75211-193">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="75211-194">すべてのページが下にある[脅威と脆弱性の管理]セクションと同じです。</span><span class="sxs-lookup"><span data-stu-id="75211-194">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="75211-195">パートナーと API</span><span class="sxs-lookup"><span data-stu-id="75211-195">Partners and APIs</span></span> | <span data-ttu-id="75211-196">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="75211-196">No changes.</span></span> |
| <span data-ttu-id="75211-197">評価&チュートリアル</span><span class="sxs-lookup"><span data-stu-id="75211-197">Evaluations & tutorials</span></span>    |     <span data-ttu-id="75211-198">新しいテストと学習機能。</span><span class="sxs-lookup"><span data-stu-id="75211-198">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="75211-199">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="75211-199">Configuration management</span></span>   |  <span data-ttu-id="75211-200">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="75211-200">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="75211-201">**自動調査と修復** は、インシデントの一部です。</span><span class="sxs-lookup"><span data-stu-id="75211-201">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="75211-202">[インシデントの調査] タブには、[自動調査と修復イベント> **確認** できます。</span><span class="sxs-lookup"><span data-stu-id="75211-202">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

> [!TIP]
> <span data-ttu-id="75211-203">デバイスの検索は、エンドポイントと検索>されます。</span><span class="sxs-lookup"><span data-stu-id="75211-203">Device search is done from Endpoints > Search.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="75211-204">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="75211-204">Access and reporting</span></span>

| <span data-ttu-id="75211-205">分野</span><span class="sxs-lookup"><span data-stu-id="75211-205">Area</span></span> | <span data-ttu-id="75211-206">変更の説明</span><span class="sxs-lookup"><span data-stu-id="75211-206">Description of change</span></span> |
|---------|---------|
| <span data-ttu-id="75211-207">レポート</span><span class="sxs-lookup"><span data-stu-id="75211-207">Reports</span></span>  | <span data-ttu-id="75211-208">脅威の保護、デバイスの正常性とコンプライアンス、脆弱な&など、エンドポイントと電子メール のコラボレーションに関するレポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75211-208">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="75211-209">正常性</span><span class="sxs-lookup"><span data-stu-id="75211-209">Health</span></span>  |  <span data-ttu-id="75211-210">現在、管理センターの [サービス正常性][ページMicrosoft 365リンクします](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="75211-210">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="75211-211">設定</span><span class="sxs-lookup"><span data-stu-id="75211-211">Settings</span></span> |  <span data-ttu-id="75211-212">Defender、Endpoints、Microsoft 365 Email &コラボレーション、ID、デバイス検出の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="75211-212">Manage your settings for Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="75211-213">Microsoft 365のナビゲーションと機能</span><span class="sxs-lookup"><span data-stu-id="75211-213">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="75211-214">左側のナビゲーションまたはクイック起動バーは見慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="75211-214">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="75211-215">ただし、このセキュリティ センターには、いくつかの新しい要素や更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="75211-215">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="75211-216">インシデントと警告</span><span class="sxs-lookup"><span data-stu-id="75211-216">Incidents and alerts</span></span>

<span data-ttu-id="75211-217">メール、デバイス、ID 全体でインシデントと通知の管理を 1 か所で行います。</span><span class="sxs-lookup"><span data-stu-id="75211-217">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="75211-218">アラート ページは、攻撃信号を組み合わせて詳細なストーリーを作成することで、アラートに対する完全なコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="75211-218">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="75211-219">新しく統合されたエクスペリエンスにより、さまざまなワークロード全体で一貫した警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75211-219">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="75211-220">トリアージ、調査、効果的なアクションをすばやく実行できます。</span><span class="sxs-lookup"><span data-stu-id="75211-220">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="75211-221">インシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="75211-221">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="75211-222">通知の管理に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="75211-222">Learn more about managing alerts</span></span>](investigate-alerts.md)

![通知とアクションのクイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="75211-224">検索</span><span class="sxs-lookup"><span data-stu-id="75211-224">Hunting</span></span>

<span data-ttu-id="75211-225">エンドポイント、Office 365 メールボックスなどに対する脅威、マルウェア、悪意のあるアクティビティを積極的に検索するために、[高度な検索クエリ](advanced-hunting-overview.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="75211-225">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="75211-226">これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方について脅威インジケーターとエンティティを見つけて確認できます。</span><span class="sxs-lookup"><span data-stu-id="75211-226">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="75211-227">[カスタム検出ルールは](custom-detection-rules.md) 、高度な検索クエリから構築して、侵害アクティビティや誤った構成済みデバイスを示す可能性があるイベントを事前に監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="75211-227">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="75211-228">アクション センター</span><span class="sxs-lookup"><span data-stu-id="75211-228">Action center</span></span>

<span data-ttu-id="75211-229">アクション センターには、自動調査と自動応答機能によって作成された調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75211-229">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="75211-230">この Microsoft 365 Defender の自動自己修復機能は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。</span><span class="sxs-lookup"><span data-stu-id="75211-230">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

<span data-ttu-id="75211-231">[アクション センターの詳細については、以下を参照してください](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="75211-231">[Learn more about the Action center](m365d-action-center.md).</span></span>

### <a name="threat-analytics"></a><span data-ttu-id="75211-232">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="75211-232">Threat Analytics</span></span>

<span data-ttu-id="75211-233">専門家の Microsoft セキュリティ調査員から脅威インテリジェンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="75211-233">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="75211-234">脅威の分析は、新たな脅威に直面している場合に、セキュリティ チームの効率を向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="75211-234">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="75211-235">脅威の分析には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75211-235">Threat Analytics includes:</span></span>

- <span data-ttu-id="75211-236">Microsoft Defender for Office 365 からのメール関連の検出と移行。</span><span class="sxs-lookup"><span data-stu-id="75211-236">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="75211-237">これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて表示されます。</span><span class="sxs-lookup"><span data-stu-id="75211-237">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="75211-238">脅威に関連するインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75211-238">Incidents view related to the threats.</span></span>
- <span data-ttu-id="75211-239">レポート内のアクション可能な情報をすばやく認識して使用するための強化されたエクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="75211-239">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="75211-240">脅威分析には、Microsoft 365 Defender の左上のナビゲーション バーから、または組織の上位の脅威を示す専用のダッシュボード カードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="75211-240">You can access threat analytics either from the upper left navigation bar in Microsoft 365 Defender, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="75211-241">脅威分析を使用して新たな脅威を追跡して対応する [方法について詳しくは、次のページをご覧ください](./threat-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="75211-241">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md).</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="75211-242">[エンドポイント] セクション</span><span class="sxs-lookup"><span data-stu-id="75211-242">Endpoints section</span></span>

<span data-ttu-id="75211-243">組織のエンドポイントのセキュリティを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="75211-243">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="75211-244">このファイルを使用したMicrosoft Defender セキュリティ センター見慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="75211-244">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![Endpoints のクイック 起動バー](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="75211-246">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="75211-246">Access and reports</span></span>

<span data-ttu-id="75211-247">レポートの表示、設定の変更、およびユーザーの役割変更を行います。</span><span class="sxs-lookup"><span data-stu-id="75211-247">View reports, change your settings, and modify user roles.</span></span>

![[アクセスとレポート] クイック起動バー](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="75211-249">SIEM API 接続</span><span class="sxs-lookup"><span data-stu-id="75211-249">SIEM API connections</span></span>

<span data-ttu-id="75211-250">Defender for [Endpoint SIEM API を使用する場合](../defender-endpoint/enable-siem-integration.md)は、引き続き実行できます。</span><span class="sxs-lookup"><span data-stu-id="75211-250">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="75211-251">API ペイロードに、セキュリティ ポータルのアラート ページまたはインシデント ページをポイントする新しいリンクMicrosoft 365しました。</span><span class="sxs-lookup"><span data-stu-id="75211-251">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="75211-252">新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75211-252">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="75211-253">詳細については、「アカウントを Microsoft Defender for Endpoint から Defender にリダイレクト[するMicrosoft 365参照してください](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="75211-253">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="75211-254">電子メール通知</span><span class="sxs-lookup"><span data-stu-id="75211-254">Email alerts</span></span>

<span data-ttu-id="75211-255">Defender for Endpoint の電子メール 通知は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="75211-255">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="75211-256">メールに、Defender のアラート ページまたはインシデント ページをポイントする新しいMicrosoft 365しました。</span><span class="sxs-lookup"><span data-stu-id="75211-256">We've added new links in the emails that point to the alert page or the incident page in Microsoft 365 Defender.</span></span> <span data-ttu-id="75211-257">詳細については、「アカウントを Microsoft Defender for Endpoint から Defender にリダイレクト[するMicrosoft 365参照してください](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="75211-257">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="managed-security-service-providers-mssp"></a><span data-ttu-id="75211-258">Managed Security Service Providers (MSSP)</span><span class="sxs-lookup"><span data-stu-id="75211-258">Managed Security Service Providers (MSSP)</span></span>

<span data-ttu-id="75211-259">同じブラウズ セッションで複数のテナントに同時にログインする方法は、統合ポータルでは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="75211-259">Logging in to multiple tenants simultaneously in the same browsing session is currently not supported in the unified portal.</span></span> <span data-ttu-id="75211-260">自動リダイレクトをオプトアウトするには、元の [Microsoft Defender for Endpoint](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)ポータルに戻して、問題が解決されるまでこの機能を維持できます。</span><span class="sxs-lookup"><span data-stu-id="75211-260">You can opt-out of the automatic redirection by [reverting to the former Microsoft Defender for Endpoint portal](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal), to maintain this functionality until the issue is resolved.</span></span>

## <a name="related-information"></a><span data-ttu-id="75211-261">関連情報</span><span class="sxs-lookup"><span data-stu-id="75211-261">Related information</span></span>

- [<span data-ttu-id="75211-262">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75211-262">Microsoft 365 Defender</span></span>](overview-security-center.md)
- [<span data-ttu-id="75211-263">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75211-263">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="75211-264">Microsoft Defender for Endpoint から Microsoft Defender へのアカウントのリダイレクトMicrosoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75211-264">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>](microsoft-365-security-mde-redirection.md)
