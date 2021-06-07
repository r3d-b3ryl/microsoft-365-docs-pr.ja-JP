---
title: Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint
description: セキュリティ センターへの変更Microsoft Defender セキュリティ センター詳細Microsoft 365する
keywords: Microsoft 365 セキュリティ センター、microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、単一ウィンドウ のガラス、コンバージド ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
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
ms.openlocfilehash: 487fc87c613d7321e3ae608097d98d2c90f8874e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771911"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="51740-104">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51740-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="51740-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="51740-105">**Applies to:**</span></span>

- [<span data-ttu-id="51740-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51740-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="51740-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51740-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51740-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="51740-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a><span data-ttu-id="51740-109">クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="51740-109">Quick reference</span></span>

<span data-ttu-id="51740-110">次の図と表に、セキュリティ センターとセキュリティ センターの間Microsoft Defender セキュリティ センター変更点Microsoft 365示します。</span><span class="sxs-lookup"><span data-stu-id="51740-110">The image and the table below lists the changes in navigation between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="51740-111">![移動先のイメージ](../../media/mde-m3d-security-center.png)</span><span class="sxs-lookup"><span data-stu-id="51740-111">![Image of what moved to where](../../media/mde-m3d-security-center.png)</span></span>

| <span data-ttu-id="51740-112">Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="51740-112">Microsoft Defender Security Center</span></span> | <span data-ttu-id="51740-113">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="51740-113">Microsoft 365 security center</span></span> |
|---------|---------|
| <span data-ttu-id="51740-114">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="51740-114">Dashboards</span></span> <ul><li><span data-ttu-id="51740-115">セキュリティ操作</span><span class="sxs-lookup"><span data-stu-id="51740-115">Security Operations</span></span></li><li><span data-ttu-id="51740-116">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="51740-116">Threat Analytics</span></span></li></ul>  |<span data-ttu-id="51740-117">ホーム</span><span class="sxs-lookup"><span data-stu-id="51740-117">Home</span></span> <ul><li><span data-ttu-id="51740-118">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="51740-118">Threat analytics</span></span></li></ul>   |
| <span data-ttu-id="51740-119">インシデント</span><span class="sxs-lookup"><span data-stu-id="51740-119">Incidents</span></span> | <span data-ttu-id="51740-120">インシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="51740-120">Incidents & alerts</span></span> |
| <span data-ttu-id="51740-121">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="51740-121">Device inventory</span></span> | <span data-ttu-id="51740-122">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="51740-122">Device inventory</span></span> |
| <span data-ttu-id="51740-123">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="51740-123">Alerts queue</span></span> | <span data-ttu-id="51740-124">インシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="51740-124">Incidents & alerts</span></span> |
| <span data-ttu-id="51740-125">自動化された調査</span><span class="sxs-lookup"><span data-stu-id="51740-125">Automated investigations</span></span> | <span data-ttu-id="51740-126">アクション センター</span><span class="sxs-lookup"><span data-stu-id="51740-126">Action center</span></span> |
| <span data-ttu-id="51740-127">高度な検出</span><span class="sxs-lookup"><span data-stu-id="51740-127">Advanced hunting</span></span> | <span data-ttu-id="51740-128">検索</span><span class="sxs-lookup"><span data-stu-id="51740-128">Hunting</span></span> |
| <span data-ttu-id="51740-129">レポート</span><span class="sxs-lookup"><span data-stu-id="51740-129">Reports</span></span> | <span data-ttu-id="51740-130">レポート</span><span class="sxs-lookup"><span data-stu-id="51740-130">Reports</span></span> |
| <span data-ttu-id="51740-131">パートナー& API</span><span class="sxs-lookup"><span data-stu-id="51740-131">Partners & APIs</span></span> | <span data-ttu-id="51740-132">パートナー& API</span><span class="sxs-lookup"><span data-stu-id="51740-132">Partners & APIs</span></span> |
| <span data-ttu-id="51740-133">脅威&の管理</span><span class="sxs-lookup"><span data-stu-id="51740-133">Threat & Vulnerability Management</span></span> | <span data-ttu-id="51740-134">脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="51740-134">Vulnerability management</span></span> |
| <span data-ttu-id="51740-135">評価とチュートリアル</span><span class="sxs-lookup"><span data-stu-id="51740-135">Evaluation and tutorials</span></span> | <span data-ttu-id="51740-136">評価&チュートリアル</span><span class="sxs-lookup"><span data-stu-id="51740-136">Evaluation & tutorials</span></span> |
| <span data-ttu-id="51740-137">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="51740-137">Configuration management</span></span> | <span data-ttu-id="51740-138">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="51740-138">Configuration management</span></span> |
| <span data-ttu-id="51740-139">Settings</span><span class="sxs-lookup"><span data-stu-id="51740-139">Settings</span></span> | <span data-ttu-id="51740-140">Settings</span><span class="sxs-lookup"><span data-stu-id="51740-140">Settings</span></span> | 

<span data-ttu-id="51740-141">セキュリティ センター Microsoft 365[強化](overview-security-center.md)され、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能 [https://security.microsoft.com](https://security.microsoft.com) が組み合わせ込みされています。</span><span class="sxs-lookup"><span data-stu-id="51740-141">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="51740-142">このセキュリティ センターは、既存の Microsoft セキュリティ ポータル (Microsoft Defender セキュリティ センター および Office 365 セキュリティ &機能を統合します。</span><span class="sxs-lookup"><span data-stu-id="51740-142">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="51740-143">この記事では、セキュリティ センターの機能強化に関する一部Microsoft Defender セキュリティ センターと改善点について説明します。この記事では、Microsoft 365説明します。</span><span class="sxs-lookup"><span data-stu-id="51740-143">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="51740-144">ただし、注意が必要な新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="51740-144">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="51740-145">これまで[、Microsoft Defender セキュリティ センターは](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)Microsoft Defender for Endpoint のホームでした。</span><span class="sxs-lookup"><span data-stu-id="51740-145">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="51740-146">Enterpriseチームは、セキュリティ チームを使用して、潜在的な高度な永続的な脅威アクティビティやデータ侵害に関するアラートの監視と対応を支援しています。</span><span class="sxs-lookup"><span data-stu-id="51740-146">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="51740-147">Microsoft 365 セキュリティ センターは、ポータルの数を減らすために、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。</span><span class="sxs-lookup"><span data-stu-id="51740-147">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="51740-148">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は[、Microsoft Defender](mssp-access.md)セキュリティ センターでアクセスを許可するのと同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="51740-148">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="51740-149">セキュリティ センターに表示されるMicrosoft 365は、現在のサブスクリプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="51740-149">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="51740-150">たとえば、Microsoft Defender for Office 365 のライセンスを持Office 365場合、[電子メール & コラボレーション] セクションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="51740-150">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="51740-151">新しい統合ポータルは、次の場合は使用できません。</span><span class="sxs-lookup"><span data-stu-id="51740-151">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="51740-152">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="51740-152">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="51740-153">米国 Government Community Cloud高 (GCC高)</span><span class="sxs-lookup"><span data-stu-id="51740-153">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="51740-154">米国国防総省</span><span class="sxs-lookup"><span data-stu-id="51740-154">US Department of Defense</span></span>
>- <span data-ttu-id="51740-155">商用ライセンスを持つすべての米国政府機関</span><span class="sxs-lookup"><span data-stu-id="51740-155">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="51740-156">強化されたセキュリティ センターをMicrosoft 365します [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="51740-156">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="51740-157">利点の詳細説明: [Microsoft 365 セキュリティ センターの概要](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="51740-157">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="51740-158">変更内容</span><span class="sxs-lookup"><span data-stu-id="51740-158">What's changed</span></span>

<span data-ttu-id="51740-159">次の表は、セキュリティ センターとセキュリティ センター Microsoft Defender セキュリティ センター変更Microsoft 365参照します。</span><span class="sxs-lookup"><span data-stu-id="51740-159">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="51740-160">アラートとアクション</span><span class="sxs-lookup"><span data-stu-id="51740-160">Alerts and actions</span></span>

| <span data-ttu-id="51740-161">分野</span><span class="sxs-lookup"><span data-stu-id="51740-161">Area</span></span> | <span data-ttu-id="51740-162">変更の説明</span><span class="sxs-lookup"><span data-stu-id="51740-162">Description of change</span></span> |
|---------|---------|
| [<span data-ttu-id="51740-163">インシデント&アラート</span><span class="sxs-lookup"><span data-stu-id="51740-163">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="51740-164">セキュリティ センター Microsoft 365、すべてのエンドポイント、電子メール、および ID でインシデントとアラートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="51740-164">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="51740-165">関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスを統合しました。</span><span class="sxs-lookup"><span data-stu-id="51740-165">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="51740-166">詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="51740-166">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="51740-167">検索</span><span class="sxs-lookup"><span data-stu-id="51740-167">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="51740-168">Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含める場合は、自動的に Id テーブルと電子メール テーブルMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="51740-168">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="51740-169">対応するアラートは、Defender のMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="51740-169">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="51740-170">これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="51740-170">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="51740-171">高度 `DeviceAlertEvents` な検索のテーブルは、Defender ではMicrosoft 365できません。</span><span class="sxs-lookup"><span data-stu-id="51740-171">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="51740-172">Microsoft 365 Defender でデバイス固有のアラート情報を照会するには、and テーブルを使用して、さまざまなソース セットからのさらに多くの情報に `AlertInfo` `AlertEvidence` 対応できます。</span><span class="sxs-lookup"><span data-stu-id="51740-172">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="51740-173">[DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)なしで書き込みクエリを実行して、次のデバイス関連のクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="51740-173">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="51740-174">アクション センター</span><span class="sxs-lookup"><span data-stu-id="51740-174">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="51740-175">自動調査と修復アクションに続いて実行された保留中のアクションと完了したアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="51740-175">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="51740-176">以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行される修復アクションの保留中および完了したアクションが一覧表示され、自動調査にはアラートと状態が一覧表示されました。</span><span class="sxs-lookup"><span data-stu-id="51740-176">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="51740-177">強化されたセキュリティ センター Microsoft 365アクション センターでは、電子メール、デバイス、およびユーザー間の修復アクションと調査が 1 つの場所にまとめされます。</span><span class="sxs-lookup"><span data-stu-id="51740-177">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="51740-178">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="51740-178">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="51740-179">ナビゲーション バーの上部に移動し、検出と使用を容易にします。</span><span class="sxs-lookup"><span data-stu-id="51740-179">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="51740-180">エンドポイントと電子メールとコラボレーションの両方に関する脅威情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="51740-180">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="51740-181">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="51740-181">Endpoints</span></span>

| <span data-ttu-id="51740-182">分野</span><span class="sxs-lookup"><span data-stu-id="51740-182">Area</span></span> | <span data-ttu-id="51740-183">変更の説明</span><span class="sxs-lookup"><span data-stu-id="51740-183">Description of change</span></span> |
|---------|---------|
|<span data-ttu-id="51740-184">検索</span><span class="sxs-lookup"><span data-stu-id="51740-184">Search</span></span>   |  <span data-ttu-id="51740-185">見出しの代わりに、Microsoft Defender for Endpoint 検索バーが [エンドポイント] セクションの下を移動しています。</span><span class="sxs-lookup"><span data-stu-id="51740-185">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="51740-186">引き続きデバイス、ファイル、ユーザー、URL、IPs、脆弱性、ソフトウェア、推奨事項を検索できます。</span><span class="sxs-lookup"><span data-stu-id="51740-186">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="51740-187">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="51740-187">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="51740-188">これは、セキュリティ操作ダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="51740-188">This is your security operations dashboard.</span></span> <span data-ttu-id="51740-189">アクティブなアラートがトリガーされた数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、およびユーザーの重大度レベルの概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51740-189">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="51740-190">また、センサーの問題が発生したデバイス、サービス全体の正常性、未解決のアラートが検出された方法も確認できます。</span><span class="sxs-lookup"><span data-stu-id="51740-190">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="51740-191">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="51740-191">Device inventory</span></span> | <span data-ttu-id="51740-192">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="51740-192">No changes.</span></span> |
|[<span data-ttu-id="51740-193">脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="51740-193">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="51740-194">ナビゲーション ウィンドウに収まる名前が短縮されました。</span><span class="sxs-lookup"><span data-stu-id="51740-194">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="51740-195">すべてのページが下にある[脅威と脆弱性の管理]セクションと同じです。</span><span class="sxs-lookup"><span data-stu-id="51740-195">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="51740-196">パートナーと API</span><span class="sxs-lookup"><span data-stu-id="51740-196">Partners and APIs</span></span> | <span data-ttu-id="51740-197">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="51740-197">No changes.</span></span> |
| <span data-ttu-id="51740-198">評価&チュートリアル</span><span class="sxs-lookup"><span data-stu-id="51740-198">Evaluations & tutorials</span></span>    |     <span data-ttu-id="51740-199">新しいテストと学習機能。</span><span class="sxs-lookup"><span data-stu-id="51740-199">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="51740-200">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="51740-200">Configuration management</span></span>   |  <span data-ttu-id="51740-201">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="51740-201">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="51740-202">**自動調査と修復** は、インシデントの一部です。</span><span class="sxs-lookup"><span data-stu-id="51740-202">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="51740-203">[インシデントの調査] タブには、[自動調査と修復イベント> **確認** できます。</span><span class="sxs-lookup"><span data-stu-id="51740-203">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

> [!TIP]
> <span data-ttu-id="51740-204">デバイスの検索は、エンドポイントと検索>されます。</span><span class="sxs-lookup"><span data-stu-id="51740-204">Device search is done from Endpoints > Search.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="51740-205">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="51740-205">Access and reporting</span></span>

| <span data-ttu-id="51740-206">分野</span><span class="sxs-lookup"><span data-stu-id="51740-206">Area</span></span> | <span data-ttu-id="51740-207">変更の説明</span><span class="sxs-lookup"><span data-stu-id="51740-207">Description of change</span></span> |
|---------|---------|
| <span data-ttu-id="51740-208">レポート</span><span class="sxs-lookup"><span data-stu-id="51740-208">Reports</span></span>  | <span data-ttu-id="51740-209">脅威の保護、デバイスの正常性とコンプライアンス、脆弱な&など、エンドポイントと電子メール のコラボレーションに関するレポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51740-209">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="51740-210">正常性</span><span class="sxs-lookup"><span data-stu-id="51740-210">Health</span></span>  |  <span data-ttu-id="51740-211">現在、管理センターの [サービス正常性][ページMicrosoft 365リンクします](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="51740-211">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="51740-212">Settings</span><span class="sxs-lookup"><span data-stu-id="51740-212">Settings</span></span> |  <span data-ttu-id="51740-213">セキュリティ センター、Microsoft 365 Microsoft 365 Defender、Endpoints、Email &コラボレーション、ID、デバイス検出の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="51740-213">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="51740-214">Microsoft 365のナビゲーションと機能</span><span class="sxs-lookup"><span data-stu-id="51740-214">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="51740-215">左側のナビゲーションまたはクイック起動バーは見慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="51740-215">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="51740-216">ただし、このセキュリティ センターには、いくつかの新しい要素や更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="51740-216">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="51740-217">インシデントと警告</span><span class="sxs-lookup"><span data-stu-id="51740-217">Incidents and alerts</span></span>

<span data-ttu-id="51740-218">メール、デバイス、ID 全体でインシデントと通知の管理を 1 か所で行います。</span><span class="sxs-lookup"><span data-stu-id="51740-218">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="51740-219">アラート ページは、攻撃信号を組み合わせて詳細なストーリーを作成することで、アラートに対する完全なコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="51740-219">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="51740-220">新しく統合されたエクスペリエンスにより、さまざまなワークロード全体で一貫した警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51740-220">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="51740-221">トリアージ、調査、効果的なアクションをすばやく実行できます。</span><span class="sxs-lookup"><span data-stu-id="51740-221">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="51740-222">インシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="51740-222">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="51740-223">通知の管理に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="51740-223">Learn more about managing alerts</span></span>](investigate-alerts.md)

![通知とアクションのクイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="51740-225">検索</span><span class="sxs-lookup"><span data-stu-id="51740-225">Hunting</span></span>

<span data-ttu-id="51740-226">エンドポイント、Office 365 メールボックスなどに対する脅威、マルウェア、悪意のあるアクティビティを積極的に検索するために、[高度な検索クエリ](advanced-hunting-overview.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="51740-226">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="51740-227">これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方について脅威インジケーターとエンティティを見つけて確認できます。</span><span class="sxs-lookup"><span data-stu-id="51740-227">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="51740-228">[カスタム検出ルールは](custom-detection-rules.md) 、高度な検索クエリから構築して、侵害アクティビティや誤った構成済みデバイスを示す可能性があるイベントを事前に監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51740-228">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="51740-229">アクション センター</span><span class="sxs-lookup"><span data-stu-id="51740-229">Action center</span></span>

<span data-ttu-id="51740-230">アクション センターには、自動調査と自動応答機能によって作成された調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51740-230">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="51740-231">この Microsoft 365 Defender の自動自己修復機能は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。</span><span class="sxs-lookup"><span data-stu-id="51740-231">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

<span data-ttu-id="51740-232">[アクション センターの詳細については、以下を参照してください](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="51740-232">[Learn more about the Action center](m365d-action-center.md).</span></span>

### <a name="threat-analytics"></a><span data-ttu-id="51740-233">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="51740-233">Threat Analytics</span></span>

<span data-ttu-id="51740-234">専門家の Microsoft セキュリティ調査員から脅威インテリジェンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="51740-234">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="51740-235">脅威の分析は、新たな脅威に直面している場合に、セキュリティ チームの効率を向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51740-235">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="51740-236">脅威の分析には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51740-236">Threat Analytics includes:</span></span>

- <span data-ttu-id="51740-237">Microsoft Defender for Office 365 からのメール関連の検出と移行。</span><span class="sxs-lookup"><span data-stu-id="51740-237">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="51740-238">これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて表示されます。</span><span class="sxs-lookup"><span data-stu-id="51740-238">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="51740-239">脅威に関連するインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51740-239">Incidents view related to the threats.</span></span>
- <span data-ttu-id="51740-240">レポート内のアクション可能な情報をすばやく認識して使用するための強化されたエクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="51740-240">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="51740-241">脅威分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーから、または組織の上位の脅威を示す専用のダッシュボード カードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="51740-241">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="51740-242">脅威分析を使用して新たな脅威を追跡して対応する [方法について詳しくは、次のページをご覧ください](./threat-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="51740-242">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md).</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="51740-243">[エンドポイント] セクション</span><span class="sxs-lookup"><span data-stu-id="51740-243">Endpoints section</span></span>

<span data-ttu-id="51740-244">組織のエンドポイントのセキュリティを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="51740-244">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="51740-245">このファイルを使用したMicrosoft Defender セキュリティ センター見慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="51740-245">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![Endpoints のクイック 起動バー](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="51740-247">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="51740-247">Access and reports</span></span>

<span data-ttu-id="51740-248">レポートの表示、設定の変更、およびユーザーの役割変更を行います。</span><span class="sxs-lookup"><span data-stu-id="51740-248">View reports, change your settings, and modify user roles.</span></span>

![[アクセスとレポート] クイック起動バー](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="51740-250">SIEM API 接続</span><span class="sxs-lookup"><span data-stu-id="51740-250">SIEM API connections</span></span>

<span data-ttu-id="51740-251">Defender for [Endpoint SIEM API を使用する場合](../defender-endpoint/enable-siem-integration.md)は、引き続き実行できます。</span><span class="sxs-lookup"><span data-stu-id="51740-251">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="51740-252">API ペイロードに、セキュリティ ポータルのアラート ページまたはインシデント ページをポイントする新しいリンクMicrosoft 365しました。</span><span class="sxs-lookup"><span data-stu-id="51740-252">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="51740-253">新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51740-253">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="51740-254">詳細については、「Microsoft Defender for Endpoint からセキュリティ センターへのアカウントMicrosoft 365[する」を参照してください](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="51740-254">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="51740-255">電子メール通知</span><span class="sxs-lookup"><span data-stu-id="51740-255">Email alerts</span></span>

<span data-ttu-id="51740-256">Defender for Endpoint の電子メール 通知は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="51740-256">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="51740-257">電子メールに新しいリンクが追加され、アラート ページまたはインシデント ページがセキュリティ センター Microsoft 365されました。</span><span class="sxs-lookup"><span data-stu-id="51740-257">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="51740-258">詳細については、「Microsoft Defender for Endpoint からセキュリティ センターへのアカウントMicrosoft 365[する」を参照してください](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="51740-258">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="managed-security-service-providers-mssp"></a><span data-ttu-id="51740-259">Managed Security Service Providers (MSSP)</span><span class="sxs-lookup"><span data-stu-id="51740-259">Managed Security Service Providers (MSSP)</span></span>

<span data-ttu-id="51740-260">同じブラウズ セッションで複数のテナントに同時にログインする方法は、統合ポータルでは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="51740-260">Logging in to multiple tenants simultaneously in the same browsing session is currently not supported in the unified portal.</span></span> <span data-ttu-id="51740-261">自動リダイレクトをオプトアウトするには、元の [Microsoft Defender for Endpoint](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)ポータルに戻して、問題が解決されるまでこの機能を維持できます。</span><span class="sxs-lookup"><span data-stu-id="51740-261">You can opt-out of the automatic redirection by [reverting to the former Microsoft Defender for Endpoint portal](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal), to maintain this functionality until the issue is resolved.</span></span>

## <a name="related-information"></a><span data-ttu-id="51740-262">関連情報</span><span class="sxs-lookup"><span data-stu-id="51740-262">Related information</span></span>

- [<span data-ttu-id="51740-263">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="51740-263">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="51740-264">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51740-264">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="51740-265">アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="51740-265">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
