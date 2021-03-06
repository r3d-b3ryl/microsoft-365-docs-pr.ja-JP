---
title: Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender
description: Microsoft Defender セキュリティ センターから Microsoft 365 セキュリティ センターへの変更点について説明します。
keywords: Microsoft 365 セキュリティ センター、OATP、MDATP、MDO、MDE、単一ウィンドウ のガラス、コンバージド ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
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
ms.openlocfilehash: 63f40ff12972695e391bd25973fd9a7195fab5b1
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515030"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="e7380-104">Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e7380-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="e7380-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e7380-105">**Applies to:**</span></span>

- [<span data-ttu-id="e7380-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7380-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="e7380-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e7380-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e7380-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="e7380-108">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

<span data-ttu-id="e7380-109">強化された [Microsoft 365](overview-security-center.md) セキュリティ センターは、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能を組み合 [https://security.microsoft.com](https://security.microsoft.com) わせたもの。</span><span class="sxs-lookup"><span data-stu-id="e7380-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="e7380-110">このセキュリティ センターは、Microsoft Defender セキュリティ センターやコンプライアンス センターの Office 365 セキュリティ &など、既存の Microsoft セキュリティ ポータルの機能を統合します。</span><span class="sxs-lookup"><span data-stu-id="e7380-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="e7380-111">Microsoft Defender セキュリティ センターについて理解している場合、この記事では、強化された Microsoft 365 セキュリティ センターの変更点と改善点の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7380-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="e7380-112">ただし、注意が必要な新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="e7380-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="e7380-113">これまで [、Microsoft Defender セキュリティ センターは](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) Microsoft Defender for Endpoint のホームでした。</span><span class="sxs-lookup"><span data-stu-id="e7380-113">Historically, the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e7380-114">エンタープライズ セキュリティ チームは、高度な永続的な脅威アクティビティやデータ侵害の可能性に関するアラートの監視と対応に使用しています。</span><span class="sxs-lookup"><span data-stu-id="e7380-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="e7380-115">ポータルの数を減らすのに役立つ Microsoft 365 セキュリティ センターは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。</span><span class="sxs-lookup"><span data-stu-id="e7380-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="e7380-116">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は[、Microsoft Defender](mssp-access.md)セキュリティ センターでアクセスを許可するのと同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセス許可をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e7380-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e7380-117">Microsoft 365 セキュリティ センターに表示される内容は、現在のサブスクリプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e7380-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="e7380-118">たとえば、Microsoft Defender for Office 365 のライセンスをお持ちではない場合、[メール & コラボレーション] セクションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e7380-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="e7380-119">新しい統合ポータルは使用できません:米国政府機関コミュニティ クラウド (GCC) US Government Community Cloud High (GCC High) 米国国防総省 商用ライセンスを持つすべての米国政府機関</span><span class="sxs-lookup"><span data-stu-id="e7380-119">The new unified portal is not available for: US Government Community Cloud (GCC) US Government Community Cloud High (GCC High) US Department of Defense All US government institutions with commercial licenses</span></span>

<span data-ttu-id="e7380-120">改善された Microsoft 365 セキュリティ センターを見 [https://security.microsoft.com](https://security.microsoft.com) てみろ。</span><span class="sxs-lookup"><span data-stu-id="e7380-120">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="e7380-121">メリットの詳細: Microsoft [365](overview-security-center.md)セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="e7380-121">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="e7380-122">変更内容</span><span class="sxs-lookup"><span data-stu-id="e7380-122">What's changed</span></span>

<span data-ttu-id="e7380-123">次の表は、Microsoft Defender セキュリティ センターと Microsoft 365 セキュリティ センターの間の変更点の簡単な参照です。</span><span class="sxs-lookup"><span data-stu-id="e7380-123">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="e7380-124">アラートとアクション</span><span class="sxs-lookup"><span data-stu-id="e7380-124">Alerts and actions</span></span>

|<span data-ttu-id="e7380-125">**領域**</span><span class="sxs-lookup"><span data-stu-id="e7380-125">**Area**</span></span>  |<span data-ttu-id="e7380-126">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="e7380-126">**Description of change**</span></span>  |
|---------|---------|
| [<span data-ttu-id="e7380-127">インシデント&アラート</span><span class="sxs-lookup"><span data-stu-id="e7380-127">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="e7380-128">Microsoft 365 セキュリティ センターでは、すべてのエンドポイント、電子メール、および ID でインシデントとアラートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-128">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="e7380-129">関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスを統合しました。</span><span class="sxs-lookup"><span data-stu-id="e7380-129">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="e7380-130">詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e7380-130">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="e7380-131">ハンティング</span><span class="sxs-lookup"><span data-stu-id="e7380-131">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="e7380-132">Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含め、自動的に Microsoft 365 Defender に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7380-132">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="e7380-133">対応するアラートは Microsoft 365 Defender にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7380-133">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="e7380-134">これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="e7380-134">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules).</span></span> <span data-ttu-id="e7380-135">高度 `DeviceAlertEvents` な検索の表は、Microsoft 365 Defender では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e7380-135">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="e7380-136">Microsoft 365 Defender でデバイス固有のアラート情報を照会するには、テーブルとテーブルを使用して、さまざまなソース セットからのさらに多くの情報に `AlertInfo` `AlertEvidence` 対応できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-136">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="e7380-137">[DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)なしで書き込みクエリを実行して、次のデバイス関連のクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7380-137">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="e7380-138">アクション センター</span><span class="sxs-lookup"><span data-stu-id="e7380-138">Action center</span></span>](mtp-action-center.md)    | <span data-ttu-id="e7380-139">自動調査と修復アクションに続いて実行された保留中のアクションと完了したアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e7380-139">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="e7380-140">以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行される修復アクションの保留中および完了したアクションが一覧表示され、自動調査ではアラートと状態が一覧表示されました。</span><span class="sxs-lookup"><span data-stu-id="e7380-140">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="e7380-141">強化された Microsoft 365 セキュリティ センターでは、アクション センターでは、電子メール、デバイス、およびユーザー間の修復アクションと調査を 1 つの場所にまとめます。</span><span class="sxs-lookup"><span data-stu-id="e7380-141">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="e7380-142">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="e7380-142">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="e7380-143">ナビゲーション バーの上部に移動し、検出と使用を容易にします。</span><span class="sxs-lookup"><span data-stu-id="e7380-143">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="e7380-144">エンドポイントと電子メールとコラボレーションの両方に関する脅威情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="e7380-144">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="e7380-145">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="e7380-145">Endpoints</span></span>

|<span data-ttu-id="e7380-146">**領域**</span><span class="sxs-lookup"><span data-stu-id="e7380-146">**Area**</span></span>  |<span data-ttu-id="e7380-147">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="e7380-147">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="e7380-148">検索</span><span class="sxs-lookup"><span data-stu-id="e7380-148">Search</span></span>   |  <span data-ttu-id="e7380-149">見出しの代わりに、Microsoft Defender for Endpoint 検索バーが [エンドポイント] セクションの下を移動しています。</span><span class="sxs-lookup"><span data-stu-id="e7380-149">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="e7380-150">引き続きデバイス、ファイル、ユーザー、URL、IPs、脆弱性、ソフトウェア、推奨事項を検索できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-150">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="e7380-151">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e7380-151">Dashboard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="e7380-152">これは、セキュリティ操作ダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="e7380-152">This is your security operations dashboard.</span></span> <span data-ttu-id="e7380-153">アクティブなアラートがトリガーされた数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、およびユーザーの重大度レベルの概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7380-153">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="e7380-154">また、センサーの問題が発生したデバイス、サービス全体の正常性、未解決のアラートが検出された方法も確認できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-154">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="e7380-155">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="e7380-155">Device inventory</span></span> | <span data-ttu-id="e7380-156">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="e7380-156">No changes.</span></span> |
|[<span data-ttu-id="e7380-157">脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="e7380-157">Vulnerability management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="e7380-158">ナビゲーション ウィンドウに収まる名前が短縮されました。</span><span class="sxs-lookup"><span data-stu-id="e7380-158">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="e7380-159">脅威と脆弱性の管理セクションと同じで、すべてのページが下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7380-159">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="e7380-160">パートナーと API</span><span class="sxs-lookup"><span data-stu-id="e7380-160">Partners and APIs</span></span> | <span data-ttu-id="e7380-161">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="e7380-161">No changes.</span></span> |
| <span data-ttu-id="e7380-162">評価&チュートリアル</span><span class="sxs-lookup"><span data-stu-id="e7380-162">Evaluations & tutorials</span></span>    |     <span data-ttu-id="e7380-163">新しいテストと学習機能。</span><span class="sxs-lookup"><span data-stu-id="e7380-163">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="e7380-164">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="e7380-164">Configuration management</span></span>   |  <span data-ttu-id="e7380-165">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="e7380-165">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="e7380-166">**自動調査と修復** は、インシデントの一部です。</span><span class="sxs-lookup"><span data-stu-id="e7380-166">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="e7380-167">[インシデントの調査] タブには、[自動調査と修復イベント> **確認** できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-167">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="e7380-168">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="e7380-168">Access and reporting</span></span>

|<span data-ttu-id="e7380-169">**領域**</span><span class="sxs-lookup"><span data-stu-id="e7380-169">**Area**</span></span>  |<span data-ttu-id="e7380-170">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="e7380-170">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="e7380-171">レポート</span><span class="sxs-lookup"><span data-stu-id="e7380-171">Reports</span></span>  | <span data-ttu-id="e7380-172">脅威の保護、デバイスの正常性とコンプライアンス、脆弱な&など、エンドポイントと電子メール のコラボレーションに関するレポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7380-172">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="e7380-173">正常性</span><span class="sxs-lookup"><span data-stu-id="e7380-173">Health</span></span>  |  <span data-ttu-id="e7380-174">現在、Microsoft 365 管理センターの [サービス正常性] [ページにリンクしています](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="e7380-174">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="e7380-175">設定</span><span class="sxs-lookup"><span data-stu-id="e7380-175">Settings</span></span> |  <span data-ttu-id="e7380-176">Microsoft 365 セキュリティ センター、Microsoft 365 Defender、Endpoints、Email &コラボレーション、ID、デバイス検出の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="e7380-176">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="e7380-177">Microsoft 365 のセキュリティ ナビゲーションと機能</span><span class="sxs-lookup"><span data-stu-id="e7380-177">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="e7380-178">左側のナビゲーション、またはクイック起動バーは見慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="e7380-178">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="e7380-179">ただし、このセキュリティ センターには、いくつかの新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="e7380-179">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="e7380-180">インシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="e7380-180">Incidents and alerts</span></span>

<span data-ttu-id="e7380-181">電子メール、デバイス、および ID 間でインシデントとアラートの管理をまとめます。</span><span class="sxs-lookup"><span data-stu-id="e7380-181">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="e7380-182">アラート ページは、攻撃信号を組み合わせて詳細なストーリーを作成することで、アラートに対する完全なコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="e7380-182">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="e7380-183">新しい統合エクスペリエンスにより、ワークロード全体で一貫したアラートの表示が実現されました。</span><span class="sxs-lookup"><span data-stu-id="e7380-183">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="e7380-184">すばやくトリアージ、調査、効果的なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-184">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="e7380-185">インシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="e7380-185">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="e7380-186">アラートの管理の詳細</span><span class="sxs-lookup"><span data-stu-id="e7380-186">Learn more about managing alerts</span></span>](investigate-alerts.md)

![[アラートとアクション] クイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="e7380-188">ハンティング</span><span class="sxs-lookup"><span data-stu-id="e7380-188">Hunting</span></span>

<span data-ttu-id="e7380-189">高度なハンティング クエリを使用して、エンドポイント全体の脅威、マルウェア、悪意のあるアクティビティ、Office 365 メールボックスなど、積極的に [検索します](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e7380-189">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="e7380-190">これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方について脅威インジケーターとエンティティを見つけて確認できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-190">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="e7380-191">[カスタム検出ルールは](custom-detection-rules.md) 、高度な検索クエリから構築して、侵害アクティビティや誤った構成済みデバイスを示す可能性があるイベントを事前に監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7380-191">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="e7380-192">アクション センター</span><span class="sxs-lookup"><span data-stu-id="e7380-192">Action center</span></span>

<span data-ttu-id="e7380-193">アクション センターには、自動調査と対応機能によって作成された調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7380-193">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="e7380-194">Microsoft 365 Defender のこの自動自己修復は、セキュリティ チームが特定のイベントに自動的に応答することで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7380-194">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="e7380-195">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="e7380-195">Learn more about the Action center</span></span>](mtp-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="e7380-196">Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="e7380-196">Threat Analytics</span></span>

<span data-ttu-id="e7380-197">Microsoft の専門家のセキュリティ研究者から脅威インテリジェンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e7380-197">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="e7380-198">Threat Analytics は、新たな脅威に直面する際にセキュリティ チームの効率を向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7380-198">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="e7380-199">Threat Analytics には、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7380-199">Threat Analytics includes:</span></span>

- <span data-ttu-id="e7380-200">Microsoft Defender からの電子メール関連の検出と軽減策 (Office 365)</span><span class="sxs-lookup"><span data-stu-id="e7380-200">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e7380-201">これは、Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えてです。</span><span class="sxs-lookup"><span data-stu-id="e7380-201">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="e7380-202">インシデント ビューは、脅威に関連します。</span><span class="sxs-lookup"><span data-stu-id="e7380-202">Incidents view related to the threats.</span></span>
- <span data-ttu-id="e7380-203">レポート内のアクション可能な情報をすばやく識別して使用するための拡張エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="e7380-203">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="e7380-204">脅威分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーから、または組織の上位の脅威を示す専用のダッシュボード カードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e7380-204">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="e7380-205">脅威分析を使用して新たな脅威を追跡して対応する [方法の詳細](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span><span class="sxs-lookup"><span data-stu-id="e7380-205">Learn more about how to [track and respond to emerging threats with threat analytics](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="e7380-206">[エンドポイント] セクション</span><span class="sxs-lookup"><span data-stu-id="e7380-206">Endpoints section</span></span>

<span data-ttu-id="e7380-207">組織のエンドポイントのセキュリティを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="e7380-207">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="e7380-208">Microsoft Defender セキュリティ センターを使用している場合は、よく知られているものに見えます。</span><span class="sxs-lookup"><span data-stu-id="e7380-208">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![Endpoints のクイック 起動バー](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="e7380-210">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="e7380-210">Access and reports</span></span>

<span data-ttu-id="e7380-211">レポートの表示、設定の変更、ユーザー ロールの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="e7380-211">View reports, change your settings, and modify user roles.</span></span>

![[アクセスとレポート] クイック起動バー](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="e7380-213">SIEM API 接続</span><span class="sxs-lookup"><span data-stu-id="e7380-213">SIEM API connections</span></span>

<span data-ttu-id="e7380-214">Defender for [Endpoint SIEM API を使用する場合](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)は、引き続き実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-214">If you use the [Defender for Endpoint SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="e7380-215">Microsoft 365 セキュリティ ポータルのアラート ページまたはインシデント ページをポイントする新しいリンクが API ペイロードに追加されました。</span><span class="sxs-lookup"><span data-stu-id="e7380-215">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="e7380-216">新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7380-216">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="e7380-217">詳細については、「アカウントを Microsoft Defender for Endpoint から [Microsoft 365 セキュリティ センターにリダイレクトする」を参照してください](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="e7380-217">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="e7380-218">電子メール通知</span><span class="sxs-lookup"><span data-stu-id="e7380-218">Email alerts</span></span>

<span data-ttu-id="e7380-219">Defender for Endpoint の電子メール 通知は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="e7380-219">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="e7380-220">Microsoft 365 セキュリティ センターのアラート ページまたはインシデント ページを指す新しいリンクがメールに追加されました。</span><span class="sxs-lookup"><span data-stu-id="e7380-220">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="e7380-221">詳細については、「アカウントを Microsoft Defender for Endpoint から [Microsoft 365 セキュリティ センターにリダイレクトする」を参照してください](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="e7380-221">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="e7380-222">関連情報</span><span class="sxs-lookup"><span data-stu-id="e7380-222">Related information</span></span>

- [<span data-ttu-id="e7380-223">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="e7380-223">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="e7380-224">Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e7380-224">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="e7380-225">Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="e7380-225">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
