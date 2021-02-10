---
title: Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint
description: Microsoft Defender セキュリティ センターから Microsoft 365 セキュリティ センターへの変更点について説明します。
keywords: Microsoft 365 セキュリティ センター、OATP、MDATP、MDO、MDE、単一ウィンドウ、コンバージド ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 03b73901512522edec7fdbc579eaf4073eed5d48
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167465"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="99a36-104">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99a36-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="99a36-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="99a36-105">**Applies to:**</span></span>

- [<span data-ttu-id="99a36-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99a36-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="99a36-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99a36-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="99a36-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="99a36-108">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

<span data-ttu-id="99a36-109">強化された [Microsoft 365](overview-security-center.md) セキュリティ センターは、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能を組み合わせた [https://security.microsoft.com](https://security.microsoft.com) 機能です。</span><span class="sxs-lookup"><span data-stu-id="99a36-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="99a36-110">このセキュリティ センターには、Microsoft Defender セキュリティ センターや Office 365 セキュリティ センターコンプライアンス センターなど、既存の Microsoft セキュリティ ポータル&が組み込されています。</span><span class="sxs-lookup"><span data-stu-id="99a36-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="99a36-111">Microsoft Defender セキュリティ センターに慣れ親しんだ場合、この記事では、強化された Microsoft 365 セキュリティ センターの変更点と機能強化について説明します。</span><span class="sxs-lookup"><span data-stu-id="99a36-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="99a36-112">ただし、注意が必要な新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="99a36-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="99a36-113">従来 [、Microsoft Defender セキュリティ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) センターは、Microsoft Defender for Endpoint のホームでした。</span><span class="sxs-lookup"><span data-stu-id="99a36-113">Historically, the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="99a36-114">エンタープライズ セキュリティ チームは、この機能を使用して、潜在的な持続的脅威アクティビティやデータ侵害のアラートを監視し、対応しています。</span><span class="sxs-lookup"><span data-stu-id="99a36-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="99a36-115">ポータルの数を減らすために、Microsoft 365 セキュリティ センターは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。</span><span class="sxs-lookup"><span data-stu-id="99a36-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99a36-116">Microsoft 365 セキュリティ センターに表示される内容は、現在のサブスクリプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="99a36-116">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="99a36-117">たとえば、microsoft Defender for Office 365 のライセンスを持ってない場合、[メールとコラボレーション&は表示されません。</span><span class="sxs-lookup"><span data-stu-id="99a36-117">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

<span data-ttu-id="99a36-118">改善された Microsoft 365 セキュリティ センターをご覧ください [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="99a36-118">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="99a36-119">メリットの詳細については[、「Microsoft 365 セキュリティ センターの概要」を参照してください](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="99a36-119">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="99a36-120">変更内容</span><span class="sxs-lookup"><span data-stu-id="99a36-120">What's changed</span></span>

<span data-ttu-id="99a36-121">次の表は、Microsoft Defender セキュリティ センターと Microsoft 365 セキュリティ センターの間の変更点のクイック リファレンスです。</span><span class="sxs-lookup"><span data-stu-id="99a36-121">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="99a36-122">アラートとアクション</span><span class="sxs-lookup"><span data-stu-id="99a36-122">Alerts and actions</span></span>

|<span data-ttu-id="99a36-123">**領域**</span><span class="sxs-lookup"><span data-stu-id="99a36-123">**Area**</span></span>  |<span data-ttu-id="99a36-124">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="99a36-124">**Description of change**</span></span>  |
|---------|---------|
| [<span data-ttu-id="99a36-125">インシデント&アラート</span><span class="sxs-lookup"><span data-stu-id="99a36-125">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="99a36-126">Microsoft 365 セキュリティ センターでは、すべてのエンドポイント、メール、ID でインシデントとアラートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="99a36-126">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="99a36-127">関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスが集約されました。</span><span class="sxs-lookup"><span data-stu-id="99a36-127">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="99a36-128">詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="99a36-128">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="99a36-129">ハンティング</span><span class="sxs-lookup"><span data-stu-id="99a36-129">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="99a36-130">Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含めるには、自動的に Microsoft 365 Defender に移動します。</span><span class="sxs-lookup"><span data-stu-id="99a36-130">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="99a36-131">対応するアラートは、Microsoft 365 Defender にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="99a36-131">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="99a36-132">これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="99a36-132">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules).</span></span> <span data-ttu-id="99a36-133">高度 `DeviceAlertEvents` な検索の表は、Microsoft 365 Defender では使用できません。</span><span class="sxs-lookup"><span data-stu-id="99a36-133">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="99a36-134">Microsoft 365 Defender でデバイス固有のアラート情報をクエリするには、テーブルとテーブルを使用して、さまざまなソースからさらに多くの情報を `AlertInfo` `AlertEvidence` 取り込みます。</span><span class="sxs-lookup"><span data-stu-id="99a36-134">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="99a36-135">DeviceAlertEvents を使用せずに Write クエリに従って、次の [デバイス関連のクエリを作成します](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)。</span><span class="sxs-lookup"><span data-stu-id="99a36-135">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="99a36-136">アクション センター</span><span class="sxs-lookup"><span data-stu-id="99a36-136">Action center</span></span>](mtp-action-center.md)    | <span data-ttu-id="99a36-137">自動調査と修復アクションに従って実行された保留中のアクションと完了したアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="99a36-137">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="99a36-138">以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行された修復アクションの保留中および完了済みアクションが一覧表示され、自動調査ではアラートと状態が一覧表示されました。</span><span class="sxs-lookup"><span data-stu-id="99a36-138">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="99a36-139">強化された Microsoft 365 セキュリティ センターでは、アクション センターによって、メール、デバイス、ユーザー間の修復アクションと調査が 1 か所にまとめらされています。</span><span class="sxs-lookup"><span data-stu-id="99a36-139">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="99a36-140">脅威分析</span><span class="sxs-lookup"><span data-stu-id="99a36-140">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="99a36-141">ナビゲーション バーの上部に移動して、検出と使用を容易にします。</span><span class="sxs-lookup"><span data-stu-id="99a36-141">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="99a36-142">エンドポイントと電子メールとコラボレーションの両方の脅威情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="99a36-142">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="99a36-143">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="99a36-143">Endpoints</span></span>

|<span data-ttu-id="99a36-144">**領域**</span><span class="sxs-lookup"><span data-stu-id="99a36-144">**Area**</span></span>  |<span data-ttu-id="99a36-145">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="99a36-145">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="99a36-146">検索</span><span class="sxs-lookup"><span data-stu-id="99a36-146">Search</span></span>   |  <span data-ttu-id="99a36-147">見出しに表示される代わりに、Microsoft Defender for Endpoint の検索バーは [エンドポイント] セクションの下に移動しています。</span><span class="sxs-lookup"><span data-stu-id="99a36-147">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="99a36-148">デバイス、ファイル、ユーザー、URL、IPS、脆弱性、ソフトウェア、推奨事項を引き続き検索できます。</span><span class="sxs-lookup"><span data-stu-id="99a36-148">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="99a36-149">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="99a36-149">Dashboard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="99a36-150">これは、セキュリティ操作ダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="99a36-150">This is your security operations dashboard.</span></span> <span data-ttu-id="99a36-151">トリガーされたアクティブなアラートの数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、ユーザーの重大度レベルの概要を確認します。</span><span class="sxs-lookup"><span data-stu-id="99a36-151">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="99a36-152">また、デバイスにセンサーの問題、サービス全体の正常性、未解決のアラートが検出された方法を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="99a36-152">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="99a36-153">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="99a36-153">Device inventory</span></span> | <span data-ttu-id="99a36-154">変更なし。</span><span class="sxs-lookup"><span data-stu-id="99a36-154">No changes.</span></span> |
|[<span data-ttu-id="99a36-155">脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="99a36-155">Vulnerability management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="99a36-156">ナビゲーション ウィンドウに収まる名前が短くされました。</span><span class="sxs-lookup"><span data-stu-id="99a36-156">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="99a36-157">すべてのページが下にある脅威と脆弱性の管理セクションと同じです。</span><span class="sxs-lookup"><span data-stu-id="99a36-157">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="99a36-158">パートナーと API</span><span class="sxs-lookup"><span data-stu-id="99a36-158">Partners and APIs</span></span> | <span data-ttu-id="99a36-159">変更なし。</span><span class="sxs-lookup"><span data-stu-id="99a36-159">No changes.</span></span> |
| <span data-ttu-id="99a36-160">評価と&チュートリアル</span><span class="sxs-lookup"><span data-stu-id="99a36-160">Evaluations & tutorials</span></span>    |     <span data-ttu-id="99a36-161">新しいテストおよび学習機能。</span><span class="sxs-lookup"><span data-stu-id="99a36-161">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="99a36-162">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="99a36-162">Configuration management</span></span>   |  <span data-ttu-id="99a36-163">変更なし。</span><span class="sxs-lookup"><span data-stu-id="99a36-163">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="99a36-164">**自動調査と修復** は、インシデントの一部です。</span><span class="sxs-lookup"><span data-stu-id="99a36-164">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="99a36-165">自動調査と修復イベントは、[インシデントの調査] **タブ>確認** できます。</span><span class="sxs-lookup"><span data-stu-id="99a36-165">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="99a36-166">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="99a36-166">Access and reporting</span></span>

|<span data-ttu-id="99a36-167">**領域**</span><span class="sxs-lookup"><span data-stu-id="99a36-167">**Area**</span></span>  |<span data-ttu-id="99a36-168">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="99a36-168">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="99a36-169">レポート</span><span class="sxs-lookup"><span data-stu-id="99a36-169">Reports</span></span>  | <span data-ttu-id="99a36-170">脅威の防止、デバイスの正常性とコンプライアンス&脆弱なデバイスなど、コラボレーションの対象となるエンドポイントと電子メール のレポートをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="99a36-170">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="99a36-171">正常性</span><span class="sxs-lookup"><span data-stu-id="99a36-171">Health</span></span>  |  <span data-ttu-id="99a36-172">現在 [、Microsoft 365](https://admin.microsoft.com/)管理センターの [サービス正常性] ページにリンクしています。</span><span class="sxs-lookup"><span data-stu-id="99a36-172">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="99a36-173">設定</span><span class="sxs-lookup"><span data-stu-id="99a36-173">Settings</span></span> |  <span data-ttu-id="99a36-174">Microsoft 365 セキュリティ センター、Microsoft 365 Defender、エンドポイント、電子メール & コラボレーション、ID、デバイス検出の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="99a36-174">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="99a36-175">Microsoft 365 のセキュリティ ナビゲーションと機能</span><span class="sxs-lookup"><span data-stu-id="99a36-175">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="99a36-176">左側のナビゲーションまたはクイック起動バーは使い慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="99a36-176">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="99a36-177">ただし、このセキュリティ センターには、いくつかの新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="99a36-177">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="99a36-178">インシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="99a36-178">Incidents and alerts</span></span>

<span data-ttu-id="99a36-179">電子メール、デバイス、ID 全体にわたってインシデントとアラートの管理をまとめます。</span><span class="sxs-lookup"><span data-stu-id="99a36-179">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="99a36-180">アラート ページは、攻撃シグナルを組み合わせて詳細なストーリーを作成することで、アラートに対する完全なコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="99a36-180">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="99a36-181">新しい統一されたエクスペリエンスにより、ワークロード間で一貫したアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99a36-181">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="99a36-182">迅速にトリアージし、調査し、効果的なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="99a36-182">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="99a36-183">インシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="99a36-183">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="99a36-184">アラートの管理について詳しくは、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99a36-184">Learn more about managing alerts</span></span>](investigate-alerts.md)

![アラートとアクションのクイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="99a36-186">ハンティング</span><span class="sxs-lookup"><span data-stu-id="99a36-186">Hunting</span></span>

<span data-ttu-id="99a36-187">高度な捜索クエリを使用して、エンドポイント、Office 365 メールボックスなど、脅威、マルウェア、悪意のあるアクティビティを事前に [検索します](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="99a36-187">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="99a36-188">これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方に関する脅威インジケーターとエンティティを見つけて確認できます。</span><span class="sxs-lookup"><span data-stu-id="99a36-188">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="99a36-189">[カスタム検出ルールは](custom-detection-rules.md) 、高度な検索クエリから構築して、侵害アクティビティや誤構成されたデバイスを示している可能性があるイベントを事前に監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="99a36-189">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="99a36-190">アクション センター</span><span class="sxs-lookup"><span data-stu-id="99a36-190">Action center</span></span>

<span data-ttu-id="99a36-191">アクション センターには、自動調査および対応機能によって作成された調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="99a36-191">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="99a36-192">この Microsoft 365 Defender での自動自動修復は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。</span><span class="sxs-lookup"><span data-stu-id="99a36-192">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="99a36-193">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="99a36-193">Learn more about the Action center</span></span>](mtp-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="99a36-194">脅威分析</span><span class="sxs-lookup"><span data-stu-id="99a36-194">Threat Analytics</span></span>

<span data-ttu-id="99a36-195">Microsoft のセキュリティの専門家のリサーチ ャーから脅威インテリジェンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="99a36-195">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="99a36-196">脅威分析は、新たな脅威に直面した場合のセキュリティ チームの効率向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="99a36-196">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="99a36-197">脅威分析には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99a36-197">Threat Analytics includes:</span></span>

- <span data-ttu-id="99a36-198">Microsoft Defender for Office 365 からのメール関連の検出と軽減策。</span><span class="sxs-lookup"><span data-stu-id="99a36-198">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="99a36-199">これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えてです。</span><span class="sxs-lookup"><span data-stu-id="99a36-199">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="99a36-200">インシデントビューは、脅威に関連します。</span><span class="sxs-lookup"><span data-stu-id="99a36-200">Incidents view related to the threats.</span></span>
- <span data-ttu-id="99a36-201">レポート内の操作可能な情報をすばやく識別して使用するための強化されたエクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="99a36-201">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="99a36-202">脅威分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーからアクセスするか、組織の上位の脅威を表示する専用のダッシュボード カードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99a36-202">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="99a36-203">脅威分析を使用して新たな脅威 [を追跡して対応する方法について詳しくは、次のリンクを参照してください。](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span><span class="sxs-lookup"><span data-stu-id="99a36-203">Learn more about how to [track and respond to emerging threats with threat analytics](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="99a36-204">[エンドポイント] セクション</span><span class="sxs-lookup"><span data-stu-id="99a36-204">Endpoints section</span></span>

<span data-ttu-id="99a36-205">組織内のエンドポイントのセキュリティを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="99a36-205">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="99a36-206">Microsoft Defender セキュリティ センターを使ったことがある場合は、使い慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="99a36-206">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![エンドポイントのクイック起動バー](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="99a36-208">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="99a36-208">Access and reports</span></span>

<span data-ttu-id="99a36-209">レポートの表示、設定の変更、ユーザー ロールの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="99a36-209">View reports, change your settings, and modify user roles.</span></span>

![アクセスとレポートのクイック起動バー](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="99a36-211">SIEM API 接続</span><span class="sxs-lookup"><span data-stu-id="99a36-211">SIEM API connections</span></span>

<span data-ttu-id="99a36-212">Defender for [Endpoint SIEM API を](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)使用する場合は、引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="99a36-212">If you use the [Defender for Endpoint SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="99a36-213">アラート ページまたは Microsoft 365 セキュリティ ポータルのインシデント ページを指す新しいリンクが API ペイロードに追加されました。</span><span class="sxs-lookup"><span data-stu-id="99a36-213">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="99a36-214">新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99a36-214">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="99a36-215">詳しくは、「Microsoft Defender for Endpoint から [Microsoft 365](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)セキュリティ センターへのアカウントのリダイレクト」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="99a36-215">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="99a36-216">電子メール通知</span><span class="sxs-lookup"><span data-stu-id="99a36-216">Email alerts</span></span>

<span data-ttu-id="99a36-217">引き続きエンドポイント用 Defender のメール通知を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99a36-217">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="99a36-218">Microsoft 365 セキュリティ センターのアラート ページまたはインシデント ページを指す新しいリンクがメールに追加されました。</span><span class="sxs-lookup"><span data-stu-id="99a36-218">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="99a36-219">詳しくは、「Microsoft Defender for Endpoint から [Microsoft 365](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)セキュリティ センターへのアカウントのリダイレクト」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="99a36-219">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="99a36-220">関連情報</span><span class="sxs-lookup"><span data-stu-id="99a36-220">Related information</span></span>

- [<span data-ttu-id="99a36-221">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="99a36-221">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="99a36-222">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99a36-222">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="99a36-223">エンドポイント用 Microsoft Defender から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="99a36-223">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
