---
title: Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender
description: Microsoft Defender セキュリティ センターから Microsoft 365 セキュリティ センターへの変更点について説明します。
keywords: Microsoft 365 セキュリティ センター、OATP、MDATP、MDO、MDE、単一ウィンドウ、統合ポータル、セキュリティ ポータル、Defender セキュリティ ポータルの使用を開始する
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
ms.openlocfilehash: 1fd32aa688256f1ac8e63eec902c3a18b2143f09
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242916"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="2f919-104">Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f919-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="2f919-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2f919-105">**Applies to:**</span></span>

- [<span data-ttu-id="2f919-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f919-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="2f919-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2f919-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2f919-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2f919-108">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

<span data-ttu-id="2f919-109">強化された [Microsoft 365](overview-security-center.md) セキュリティ センターは、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能を組み合わせた [https://security.microsoft.com](https://security.microsoft.com) 機能です。</span><span class="sxs-lookup"><span data-stu-id="2f919-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="2f919-110">このセキュリティ センターには、Microsoft Defender セキュリティ センターや Office 365 セキュリティ センターコンプライアンス センターなど、既存の Microsoft セキュリティ ポータル&が組み込されています。</span><span class="sxs-lookup"><span data-stu-id="2f919-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="2f919-111">Microsoft Defender セキュリティ センターに慣れ親しんだ場合、この記事では、強化された Microsoft 365 セキュリティ センターの変更点と改善点について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f919-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="2f919-112">ただし、注意が必要な新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="2f919-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="2f919-113">従来 [、Microsoft Defender セキュリティ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) センターは、Microsoft Defender for Endpoint のホームでした。</span><span class="sxs-lookup"><span data-stu-id="2f919-113">Historically, the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2f919-114">エンタープライズ セキュリティ チームは、この機能を使用して、潜在的な持続的脅威アクティビティやデータ侵害のアラートを監視し、対応しています。</span><span class="sxs-lookup"><span data-stu-id="2f919-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="2f919-115">ポータルの数を減らすために、Microsoft 365 セキュリティ センターは、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。</span><span class="sxs-lookup"><span data-stu-id="2f919-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="2f919-116">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は[、Microsoft Defender](mssp-access.md)セキュリティ センターで付与されるのと同じ方法で、管理されたセキュリティ サービス プロバイダー [(MSSP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="2f919-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="2f919-117">Microsoft 365 セキュリティ センターに表示される内容は、現在のサブスクリプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2f919-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="2f919-118">たとえば、Office 365 用の Microsoft Defender のライセンスを持ってない場合、[メールとグループ&] セクションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2f919-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

<span data-ttu-id="2f919-119">改善された Microsoft 365 セキュリティ センターをご覧 [https://security.microsoft.com](https://security.microsoft.com) ください。</span><span class="sxs-lookup"><span data-stu-id="2f919-119">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="2f919-120">メリットの詳細については[、「Microsoft 365 セキュリティ センターの概要」を参照してください](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2f919-120">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="2f919-121">変更内容</span><span class="sxs-lookup"><span data-stu-id="2f919-121">What's changed</span></span>

<span data-ttu-id="2f919-122">次の表は、Microsoft Defender セキュリティ センターと Microsoft 365 セキュリティ センターの間の変更点のクイック リファレンスです。</span><span class="sxs-lookup"><span data-stu-id="2f919-122">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="2f919-123">アラートとアクション</span><span class="sxs-lookup"><span data-stu-id="2f919-123">Alerts and actions</span></span>

|<span data-ttu-id="2f919-124">**領域**</span><span class="sxs-lookup"><span data-stu-id="2f919-124">**Area**</span></span>  |<span data-ttu-id="2f919-125">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="2f919-125">**Description of change**</span></span>  |
|---------|---------|
| [<span data-ttu-id="2f919-126">インシデント&アラート</span><span class="sxs-lookup"><span data-stu-id="2f919-126">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="2f919-127">Microsoft 365 セキュリティ センターでは、すべてのエンドポイント、メール、ID でインシデントとアラートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2f919-127">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="2f919-128">関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスが集約されました。</span><span class="sxs-lookup"><span data-stu-id="2f919-128">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="2f919-129">詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2f919-129">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="2f919-130">ハンティング</span><span class="sxs-lookup"><span data-stu-id="2f919-130">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="2f919-131">Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含めるには、自動的に Microsoft 365 Defender に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f919-131">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="2f919-132">対応するアラートは、Microsoft 365 Defender にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f919-132">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="2f919-133">これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="2f919-133">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules).</span></span> <span data-ttu-id="2f919-134">高度 `DeviceAlertEvents` な検索の表は、Microsoft 365 Defender では使用できません。</span><span class="sxs-lookup"><span data-stu-id="2f919-134">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="2f919-135">Microsoft 365 Defender でデバイス固有のアラート情報を照会するには、テーブルとテーブルを使用して、さまざまなソースからさらに多くの情報を `AlertInfo` `AlertEvidence` 取り込みます。</span><span class="sxs-lookup"><span data-stu-id="2f919-135">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="2f919-136">DeviceAlertEvents を使用せずに Write クエリに従って、次の [デバイス関連のクエリを作成します](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)。</span><span class="sxs-lookup"><span data-stu-id="2f919-136">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="2f919-137">アクション センター</span><span class="sxs-lookup"><span data-stu-id="2f919-137">Action center</span></span>](mtp-action-center.md)    | <span data-ttu-id="2f919-138">自動調査と修復アクションに従って実行された保留中のアクションと完了したアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2f919-138">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="2f919-139">以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行された修復アクションの保留中のアクションと完了したアクションが一覧表示され、自動調査ではアラートと状態が一覧表示されました。</span><span class="sxs-lookup"><span data-stu-id="2f919-139">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="2f919-140">強化された Microsoft 365 セキュリティ センターでは、アクション センターによって、メール、デバイス、ユーザー間の修復アクションと調査が 1 か所にまとめらされています。</span><span class="sxs-lookup"><span data-stu-id="2f919-140">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="2f919-141">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="2f919-141">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="2f919-142">ナビゲーション バーの上部に移動して、検出と使用を容易にします。</span><span class="sxs-lookup"><span data-stu-id="2f919-142">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="2f919-143">エンドポイントと電子メールとコラボレーションの両方の脅威情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="2f919-143">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="2f919-144">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="2f919-144">Endpoints</span></span>

|<span data-ttu-id="2f919-145">**領域**</span><span class="sxs-lookup"><span data-stu-id="2f919-145">**Area**</span></span>  |<span data-ttu-id="2f919-146">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="2f919-146">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="2f919-147">検索</span><span class="sxs-lookup"><span data-stu-id="2f919-147">Search</span></span>   |  <span data-ttu-id="2f919-148">見出しに表示される代わりに、Microsoft Defender for Endpoint の検索バーは [エンドポイント] セクションの下に移動しています。</span><span class="sxs-lookup"><span data-stu-id="2f919-148">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="2f919-149">デバイス、ファイル、ユーザー、URL、IPS、脆弱性、ソフトウェア、推奨事項を引き続き検索できます。</span><span class="sxs-lookup"><span data-stu-id="2f919-149">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="2f919-150">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="2f919-150">Dashboard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="2f919-151">これは、セキュリティ運用ダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="2f919-151">This is your security operations dashboard.</span></span> <span data-ttu-id="2f919-152">トリガーされたアクティブなアラートの数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、ユーザーの重大度レベルの概要を確認します。</span><span class="sxs-lookup"><span data-stu-id="2f919-152">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="2f919-153">また、デバイスにセンサーの問題が発生している場合、サービス全体の正常性、未解決のアラートが検出された方法も確認できます。</span><span class="sxs-lookup"><span data-stu-id="2f919-153">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="2f919-154">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="2f919-154">Device inventory</span></span> | <span data-ttu-id="2f919-155">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="2f919-155">No changes.</span></span> |
|[<span data-ttu-id="2f919-156">脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="2f919-156">Vulnerability management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="2f919-157">ナビゲーション ウィンドウに収まる名前が短くされました。</span><span class="sxs-lookup"><span data-stu-id="2f919-157">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="2f919-158">これは、脅威と脆弱性の管理セクションと同じであり、すべてのページが下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f919-158">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="2f919-159">パートナーと API</span><span class="sxs-lookup"><span data-stu-id="2f919-159">Partners and APIs</span></span> | <span data-ttu-id="2f919-160">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="2f919-160">No changes.</span></span> |
| <span data-ttu-id="2f919-161">評価と&チュートリアル</span><span class="sxs-lookup"><span data-stu-id="2f919-161">Evaluations & tutorials</span></span>    |     <span data-ttu-id="2f919-162">新しいテストおよび学習機能。</span><span class="sxs-lookup"><span data-stu-id="2f919-162">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="2f919-163">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="2f919-163">Configuration management</span></span>   |  <span data-ttu-id="2f919-164">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="2f919-164">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="2f919-165">**自動調査と修復** は、インシデントの一部です。</span><span class="sxs-lookup"><span data-stu-id="2f919-165">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="2f919-166">自動調査と修復イベントは、[インシデントの調査] **タブ>確認** できます。</span><span class="sxs-lookup"><span data-stu-id="2f919-166">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="2f919-167">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="2f919-167">Access and reporting</span></span>

|<span data-ttu-id="2f919-168">**領域**</span><span class="sxs-lookup"><span data-stu-id="2f919-168">**Area**</span></span>  |<span data-ttu-id="2f919-169">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="2f919-169">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="2f919-170">レポート</span><span class="sxs-lookup"><span data-stu-id="2f919-170">Reports</span></span>  | <span data-ttu-id="2f919-171">脅威の防止、デバイスの正常性とコンプライアンス&脆弱なデバイスなど、コラボレーションに関するエンドポイントと電子メール のレポートをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2f919-171">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="2f919-172">正常性</span><span class="sxs-lookup"><span data-stu-id="2f919-172">Health</span></span>  |  <span data-ttu-id="2f919-173">現在 [、Microsoft 365](https://admin.microsoft.com/)管理センターの [サービス正常性] ページにリンクしています。</span><span class="sxs-lookup"><span data-stu-id="2f919-173">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="2f919-174">設定</span><span class="sxs-lookup"><span data-stu-id="2f919-174">Settings</span></span> |  <span data-ttu-id="2f919-175">Microsoft 365 セキュリティ センター、Microsoft 365 Defender、エンドポイント、メール & コラボレーション、ID、デバイス検出の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="2f919-175">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="2f919-176">Microsoft 365 のセキュリティ ナビゲーションと機能</span><span class="sxs-lookup"><span data-stu-id="2f919-176">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="2f919-177">左側のナビゲーションまたはクイック起動バーは使い慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="2f919-177">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="2f919-178">ただし、このセキュリティ センターには、いくつかの新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="2f919-178">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="2f919-179">インシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="2f919-179">Incidents and alerts</span></span>

<span data-ttu-id="2f919-180">電子メール、デバイス、ID 全体にわたってインシデントとアラートの管理をまとめます。</span><span class="sxs-lookup"><span data-stu-id="2f919-180">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="2f919-181">アラート ページは、攻撃シグナルを組み合わせて詳細なストーリーを構築することで、アラートに対する完全なコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f919-181">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="2f919-182">新しい統一されたエクスペリエンスにより、ワークロード間で一貫したアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f919-182">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="2f919-183">迅速にトリアージし、調査し、効果的なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2f919-183">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="2f919-184">インシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="2f919-184">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="2f919-185">アラートの管理について詳しくは、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f919-185">Learn more about managing alerts</span></span>](investigate-alerts.md)

![アラートとアクションのクイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="2f919-187">ハンティング</span><span class="sxs-lookup"><span data-stu-id="2f919-187">Hunting</span></span>

<span data-ttu-id="2f919-188">高度な捜索クエリを使用して、エンドポイント、Office 365 メールボックスなど、脅威、マルウェア、悪意のあるアクティビティを事前に [検索します](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2f919-188">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="2f919-189">これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方に関する脅威インジケーターとエンティティを見つけて確認できます。</span><span class="sxs-lookup"><span data-stu-id="2f919-189">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="2f919-190">[カスタム検出ルールは](custom-detection-rules.md) 、高度なハンティング クエリから構築して、侵害アクティビティや誤構成されたデバイスを示している可能性があるイベントを事前に監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f919-190">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="2f919-191">アクション センター</span><span class="sxs-lookup"><span data-stu-id="2f919-191">Action center</span></span>

<span data-ttu-id="2f919-192">アクション センターには、自動調査および対応機能によって作成された調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f919-192">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="2f919-193">この Microsoft 365 Defender での自動自動修復は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。</span><span class="sxs-lookup"><span data-stu-id="2f919-193">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="2f919-194">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="2f919-194">Learn more about the Action center</span></span>](mtp-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="2f919-195">脅威分析</span><span class="sxs-lookup"><span data-stu-id="2f919-195">Threat Analytics</span></span>

<span data-ttu-id="2f919-196">Microsoft のセキュリティの専門家のリサーチ ャーから脅威インテリジェンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2f919-196">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="2f919-197">脅威分析は、新たな脅威に直面した場合のセキュリティ チームの効率向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f919-197">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="2f919-198">脅威分析には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f919-198">Threat Analytics includes:</span></span>

- <span data-ttu-id="2f919-199">Microsoft Defender for Office 365 からのメール関連の検出と軽減策。</span><span class="sxs-lookup"><span data-stu-id="2f919-199">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="2f919-200">これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えてです。</span><span class="sxs-lookup"><span data-stu-id="2f919-200">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="2f919-201">インシデントビューは、脅威に関連します。</span><span class="sxs-lookup"><span data-stu-id="2f919-201">Incidents view related to the threats.</span></span>
- <span data-ttu-id="2f919-202">レポート内の操作可能な情報をすばやく識別して使用するための強化されたエクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="2f919-202">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="2f919-203">脅威分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーからアクセスするか、組織の上位の脅威を表示する専用のダッシュボード カードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2f919-203">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="2f919-204">脅威分析を使用して新たな脅威 [を追跡して対応する方法について詳しくは、次のリンクを参照してください。](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span><span class="sxs-lookup"><span data-stu-id="2f919-204">Learn more about how to [track and respond to emerging threats with threat analytics](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="2f919-205">[エンドポイント] セクション</span><span class="sxs-lookup"><span data-stu-id="2f919-205">Endpoints section</span></span>

<span data-ttu-id="2f919-206">組織内のエンドポイントのセキュリティを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="2f919-206">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="2f919-207">Microsoft Defender セキュリティ センターを使ったことがある場合は、使い慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="2f919-207">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![エンドポイントのクイック起動バー](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="2f919-209">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="2f919-209">Access and reports</span></span>

<span data-ttu-id="2f919-210">レポートの表示、設定の変更、ユーザー ロールの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="2f919-210">View reports, change your settings, and modify user roles.</span></span>

![アクセスとレポートのクイック起動バー](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="2f919-212">SIEM API 接続</span><span class="sxs-lookup"><span data-stu-id="2f919-212">SIEM API connections</span></span>

<span data-ttu-id="2f919-213">Defender for [Endpoint SIEM API を使用](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)する場合は、引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f919-213">If you use the [Defender for Endpoint SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="2f919-214">アラート ページまたは Microsoft 365 セキュリティ ポータルのインシデント ページを指す新しいリンクが API ペイロードに追加されました。</span><span class="sxs-lookup"><span data-stu-id="2f919-214">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="2f919-215">新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f919-215">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="2f919-216">詳しくは、「Microsoft Defender for Endpoint から [Microsoft 365](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)セキュリティ センターへのアカウントのリダイレクト」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2f919-216">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="2f919-217">電子メール通知</span><span class="sxs-lookup"><span data-stu-id="2f919-217">Email alerts</span></span>

<span data-ttu-id="2f919-218">引き続きエンドポイント用 Defender のメール通知を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f919-218">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="2f919-219">Microsoft 365 セキュリティ センターのアラート ページまたはインシデント ページを指す新しいリンクがメールに追加されました。</span><span class="sxs-lookup"><span data-stu-id="2f919-219">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="2f919-220">詳しくは、「Microsoft Defender for Endpoint から [Microsoft 365](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)セキュリティ センターへのアカウントのリダイレクト」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2f919-220">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="2f919-221">関連情報</span><span class="sxs-lookup"><span data-stu-id="2f919-221">Related information</span></span>

- [<span data-ttu-id="2f919-222">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="2f919-222">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="2f919-223">Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f919-223">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="2f919-224">エンドポイント用 Microsoft Defender から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="2f919-224">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
