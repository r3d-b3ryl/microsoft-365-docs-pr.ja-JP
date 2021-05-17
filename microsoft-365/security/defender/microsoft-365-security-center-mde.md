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
ms.openlocfilehash: bad31160bb27c79f672ddd28a5fced3bf8c2ee1b
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51943043"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="666ae-104">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="666ae-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="666ae-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="666ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="666ae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="666ae-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="666ae-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="666ae-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="666ae-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="666ae-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

<span data-ttu-id="666ae-109">セキュリティ センター Microsoft 365[強化](overview-security-center.md)され、電子メール、コラボレーション、ID、デバイスの脅威を保護、検出、調査、および対応するセキュリティ機能 [https://security.microsoft.com](https://security.microsoft.com) が組み合わせ込みされています。</span><span class="sxs-lookup"><span data-stu-id="666ae-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="666ae-110">このセキュリティ センターは、既存の Microsoft セキュリティ ポータル (Microsoft Defender セキュリティ センター および Office 365 セキュリティ &機能を統合します。</span><span class="sxs-lookup"><span data-stu-id="666ae-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="666ae-111">この記事では、セキュリティ センターの機能強化に関する一部Microsoft Defender セキュリティ センターと改善点について説明します。この記事では、Microsoft 365説明します。</span><span class="sxs-lookup"><span data-stu-id="666ae-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="666ae-112">ただし、注意が必要な新しい要素と更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="666ae-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="666ae-113">これまで[、Microsoft Defender セキュリティ センターは](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)Microsoft Defender for Endpoint のホームでした。</span><span class="sxs-lookup"><span data-stu-id="666ae-113">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="666ae-114">Enterpriseチームは、セキュリティ チームを使用して、潜在的な高度な永続的な脅威アクティビティやデータ侵害に関するアラートの監視と対応を支援しています。</span><span class="sxs-lookup"><span data-stu-id="666ae-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="666ae-115">Microsoft 365 セキュリティ センターは、ポータルの数を減らすために、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するホームになります。</span><span class="sxs-lookup"><span data-stu-id="666ae-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="666ae-116">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は[、Microsoft Defender](mssp-access.md)セキュリティ センターでアクセスを許可するのと同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="666ae-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="666ae-117">セキュリティ センターに表示されるMicrosoft 365は、現在のサブスクリプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="666ae-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="666ae-118">たとえば、Microsoft Defender for Office 365 のライセンスを持Office 365場合、[電子メール & コラボレーション] セクションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="666ae-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="666ae-119">新しい統合ポータルは、次の場合は使用できません。</span><span class="sxs-lookup"><span data-stu-id="666ae-119">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="666ae-120">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="666ae-120">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="666ae-121">米国 Government Community Cloud高 (GCC高)</span><span class="sxs-lookup"><span data-stu-id="666ae-121">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="666ae-122">米国国防総省</span><span class="sxs-lookup"><span data-stu-id="666ae-122">US Department of Defense</span></span>
>- <span data-ttu-id="666ae-123">商用ライセンスを持つすべての米国政府機関</span><span class="sxs-lookup"><span data-stu-id="666ae-123">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="666ae-124">強化されたセキュリティ センターをMicrosoft 365します [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="666ae-124">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="666ae-125">利点の詳細説明: [Microsoft 365 セキュリティ センターの概要](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="666ae-125">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="666ae-126">変更内容</span><span class="sxs-lookup"><span data-stu-id="666ae-126">What's changed</span></span>

<span data-ttu-id="666ae-127">次の表は、セキュリティ センターとセキュリティ センター Microsoft Defender セキュリティ センター変更Microsoft 365参照します。</span><span class="sxs-lookup"><span data-stu-id="666ae-127">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="666ae-128">アラートとアクション</span><span class="sxs-lookup"><span data-stu-id="666ae-128">Alerts and actions</span></span>

|<span data-ttu-id="666ae-129">**領域**</span><span class="sxs-lookup"><span data-stu-id="666ae-129">**Area**</span></span>  |<span data-ttu-id="666ae-130">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="666ae-130">**Description of change**</span></span> |
|---------|---------|
| [<span data-ttu-id="666ae-131">インシデント&アラート</span><span class="sxs-lookup"><span data-stu-id="666ae-131">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="666ae-132">セキュリティ センター Microsoft 365、すべてのエンドポイント、電子メール、および ID でインシデントとアラートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-132">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="666ae-133">関連するイベントを簡単に見つけ出すのに役立つエクスペリエンスを統合しました。</span><span class="sxs-lookup"><span data-stu-id="666ae-133">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="666ae-134">詳細については、「インシデントの [概要」を参照してください](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="666ae-134">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="666ae-135">検索</span><span class="sxs-lookup"><span data-stu-id="666ae-135">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="666ae-136">Microsoft Defender for Endpoint で作成されたカスタム検出ルールを変更して、ID テーブルと電子メール テーブルを含める場合は、自動的に Id テーブルと電子メール テーブルMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="666ae-136">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="666ae-137">対応するアラートは、Defender のMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="666ae-137">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="666ae-138">これらの変更の詳細については、「カスタム検出ルールの移行 [」を参照してください](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="666ae-138">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="666ae-139">高度 `DeviceAlertEvents` な検索のテーブルは、Defender ではMicrosoft 365できません。</span><span class="sxs-lookup"><span data-stu-id="666ae-139">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="666ae-140">Microsoft 365 Defender でデバイス固有のアラート情報を照会するには、and テーブルを使用して、さまざまなソース セットからのさらに多くの情報に `AlertInfo` `AlertEvidence` 対応できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-140">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="666ae-141">[DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)なしで書き込みクエリを実行して、次のデバイス関連のクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="666ae-141">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="666ae-142">アクション センター</span><span class="sxs-lookup"><span data-stu-id="666ae-142">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="666ae-143">自動調査と修復アクションに続いて実行された保留中のアクションと完了したアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="666ae-143">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="666ae-144">以前は、Microsoft Defender セキュリティ センターのアクション センターには、デバイスでのみ実行される修復アクションの保留中および完了したアクションが一覧表示され、自動調査にはアラートと状態が一覧表示されました。</span><span class="sxs-lookup"><span data-stu-id="666ae-144">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="666ae-145">強化されたセキュリティ センター Microsoft 365アクション センターでは、電子メール、デバイス、およびユーザー間の修復アクションと調査が 1 つの場所にまとめされます。</span><span class="sxs-lookup"><span data-stu-id="666ae-145">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="666ae-146">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="666ae-146">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="666ae-147">ナビゲーション バーの上部に移動し、検出と使用を容易にします。</span><span class="sxs-lookup"><span data-stu-id="666ae-147">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="666ae-148">エンドポイントと電子メールとコラボレーションの両方に関する脅威情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="666ae-148">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="666ae-149">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="666ae-149">Endpoints</span></span>

|<span data-ttu-id="666ae-150">**領域**</span><span class="sxs-lookup"><span data-stu-id="666ae-150">**Area**</span></span>  |<span data-ttu-id="666ae-151">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="666ae-151">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="666ae-152">検索</span><span class="sxs-lookup"><span data-stu-id="666ae-152">Search</span></span>   |  <span data-ttu-id="666ae-153">見出しの代わりに、Microsoft Defender for Endpoint 検索バーが [エンドポイント] セクションの下を移動しています。</span><span class="sxs-lookup"><span data-stu-id="666ae-153">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="666ae-154">引き続きデバイス、ファイル、ユーザー、URL、IPs、脆弱性、ソフトウェア、推奨事項を検索できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-154">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="666ae-155">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="666ae-155">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="666ae-156">これは、セキュリティ操作ダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="666ae-156">This is your security operations dashboard.</span></span> <span data-ttu-id="666ae-157">アクティブなアラートがトリガーされた数、どのデバイスが危険にさらされているか、どのユーザーが危険にさらされているのか、アラート、デバイス、およびユーザーの重大度レベルの概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="666ae-157">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="666ae-158">また、センサーの問題が発生したデバイス、サービス全体の正常性、未解決のアラートが検出された方法も確認できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-158">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="666ae-159">デバイス一覧</span><span class="sxs-lookup"><span data-stu-id="666ae-159">Device inventory</span></span> | <span data-ttu-id="666ae-160">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="666ae-160">No changes.</span></span> |
|[<span data-ttu-id="666ae-161">脆弱性管理</span><span class="sxs-lookup"><span data-stu-id="666ae-161">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="666ae-162">ナビゲーション ウィンドウに収まる名前が短縮されました。</span><span class="sxs-lookup"><span data-stu-id="666ae-162">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="666ae-163">すべてのページが下にある[脅威と脆弱性の管理]セクションと同じです。</span><span class="sxs-lookup"><span data-stu-id="666ae-163">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="666ae-164">パートナーと API</span><span class="sxs-lookup"><span data-stu-id="666ae-164">Partners and APIs</span></span> | <span data-ttu-id="666ae-165">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="666ae-165">No changes.</span></span> |
| <span data-ttu-id="666ae-166">評価&チュートリアル</span><span class="sxs-lookup"><span data-stu-id="666ae-166">Evaluations & tutorials</span></span>    |     <span data-ttu-id="666ae-167">新しいテストと学習機能。</span><span class="sxs-lookup"><span data-stu-id="666ae-167">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="666ae-168">構成管理環境</span><span class="sxs-lookup"><span data-stu-id="666ae-168">Configuration management</span></span>   |  <span data-ttu-id="666ae-169">変更はありません。</span><span class="sxs-lookup"><span data-stu-id="666ae-169">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="666ae-170">**自動調査と修復** は、インシデントの一部です。</span><span class="sxs-lookup"><span data-stu-id="666ae-170">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="666ae-171">[インシデントの調査] タブには、[自動調査と修復イベント> **確認** できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-171">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

> [!TIP]
> <span data-ttu-id="666ae-172">デバイスの検索は、エンドポイントと検索>されます。</span><span class="sxs-lookup"><span data-stu-id="666ae-172">Device search is done from Endpoints > Search.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="666ae-173">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="666ae-173">Access and reporting</span></span>

|<span data-ttu-id="666ae-174">**領域**</span><span class="sxs-lookup"><span data-stu-id="666ae-174">**Area**</span></span>  |<span data-ttu-id="666ae-175">**変更の説明**</span><span class="sxs-lookup"><span data-stu-id="666ae-175">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="666ae-176">レポート</span><span class="sxs-lookup"><span data-stu-id="666ae-176">Reports</span></span>  | <span data-ttu-id="666ae-177">脅威の保護、デバイスの正常性とコンプライアンス、脆弱な&など、エンドポイントと電子メール のコラボレーションに関するレポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="666ae-177">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="666ae-178">正常性</span><span class="sxs-lookup"><span data-stu-id="666ae-178">Health</span></span>  |  <span data-ttu-id="666ae-179">現在、管理センターの [サービス正常性][ページMicrosoft 365リンクします](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="666ae-179">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="666ae-180">設定</span><span class="sxs-lookup"><span data-stu-id="666ae-180">Settings</span></span> |  <span data-ttu-id="666ae-181">セキュリティ センター、Microsoft 365 Microsoft 365 Defender、Endpoints、Email &コラボレーション、ID、デバイス検出の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="666ae-181">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="666ae-182">Microsoft 365のナビゲーションと機能</span><span class="sxs-lookup"><span data-stu-id="666ae-182">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="666ae-183">左側のナビゲーションまたはクイック起動バーは見慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="666ae-183">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="666ae-184">ただし、このセキュリティ センターには、いくつかの新しい要素や更新された要素があります。</span><span class="sxs-lookup"><span data-stu-id="666ae-184">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="666ae-185">インシデントと警告</span><span class="sxs-lookup"><span data-stu-id="666ae-185">Incidents and alerts</span></span>

<span data-ttu-id="666ae-186">メール、デバイス、ID 全体でインシデントと通知の管理を 1 か所で行います。</span><span class="sxs-lookup"><span data-stu-id="666ae-186">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="666ae-187">アラート ページは、攻撃信号を組み合わせて詳細なストーリーを作成することで、アラートに対する完全なコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="666ae-187">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="666ae-188">新しく統合されたエクスペリエンスにより、さまざまなワークロード全体で一貫した警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="666ae-188">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="666ae-189">トリアージ、調査、効果的なアクションをすばやく実行できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-189">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="666ae-190">インシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="666ae-190">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="666ae-191">通知の管理に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="666ae-191">Learn more about managing alerts</span></span>](investigate-alerts.md)

![通知とアクションのクイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="666ae-193">検索</span><span class="sxs-lookup"><span data-stu-id="666ae-193">Hunting</span></span>

<span data-ttu-id="666ae-194">エンドポイント、Office 365 メールボックスなどに対する脅威、マルウェア、悪意のあるアクティビティを積極的に検索するために、[高度な検索クエリ](advanced-hunting-overview.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="666ae-194">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="666ae-195">これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方について脅威インジケーターとエンティティを見つけて確認できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-195">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="666ae-196">[カスタム検出ルールは](custom-detection-rules.md) 、高度な検索クエリから構築して、侵害アクティビティや誤った構成済みデバイスを示す可能性があるイベントを事前に監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="666ae-196">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="666ae-197">アクション センター</span><span class="sxs-lookup"><span data-stu-id="666ae-197">Action center</span></span>

<span data-ttu-id="666ae-198">アクション センターには、自動調査と自動応答機能によって作成された調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="666ae-198">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="666ae-199">この Microsoft 365 Defender の自動自己修復機能は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。</span><span class="sxs-lookup"><span data-stu-id="666ae-199">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="666ae-200">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="666ae-200">Learn more about the Action center</span></span>](m365d-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="666ae-201">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="666ae-201">Threat Analytics</span></span>

<span data-ttu-id="666ae-202">専門家の Microsoft セキュリティ調査員から脅威インテリジェンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="666ae-202">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="666ae-203">脅威の分析は、新たな脅威に直面している場合に、セキュリティ チームの効率を向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="666ae-203">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="666ae-204">脅威の分析には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="666ae-204">Threat Analytics includes:</span></span>

- <span data-ttu-id="666ae-205">Microsoft Defender for Office 365 からのメール関連の検出と移行。</span><span class="sxs-lookup"><span data-stu-id="666ae-205">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="666ae-206">これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて表示されます。</span><span class="sxs-lookup"><span data-stu-id="666ae-206">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="666ae-207">脅威に関連するインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="666ae-207">Incidents view related to the threats.</span></span>
- <span data-ttu-id="666ae-208">レポート内のアクション可能な情報をすばやく認識して使用するための強化されたエクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="666ae-208">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="666ae-209">脅威分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーから、または組織の上位の脅威を示す専用のダッシュボード カードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="666ae-209">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="666ae-210">[[脅威の分析を使用して、新たな脅威を追跡し対応する]](./threat-analytics.md)の詳細説明</span><span class="sxs-lookup"><span data-stu-id="666ae-210">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="666ae-211">[エンドポイント] セクション</span><span class="sxs-lookup"><span data-stu-id="666ae-211">Endpoints section</span></span>

<span data-ttu-id="666ae-212">組織のエンドポイントのセキュリティを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="666ae-212">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="666ae-213">このファイルを使用したMicrosoft Defender セキュリティ センター見慣れたものに見えます。</span><span class="sxs-lookup"><span data-stu-id="666ae-213">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![Endpoints のクイック 起動バー](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="666ae-215">アクセスとレポート</span><span class="sxs-lookup"><span data-stu-id="666ae-215">Access and reports</span></span>

<span data-ttu-id="666ae-216">レポートの表示、設定の変更、およびユーザーの役割変更を行います。</span><span class="sxs-lookup"><span data-stu-id="666ae-216">View reports, change your settings, and modify user roles.</span></span>

![[アクセスとレポート] クイック起動バー](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="666ae-218">SIEM API 接続</span><span class="sxs-lookup"><span data-stu-id="666ae-218">SIEM API connections</span></span>

<span data-ttu-id="666ae-219">Defender for [Endpoint SIEM API を使用する場合](../defender-endpoint/enable-siem-integration.md)は、引き続き実行できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-219">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="666ae-220">API ペイロードに、セキュリティ ポータルのアラート ページまたはインシデント ページをポイントする新しいリンクMicrosoft 365しました。</span><span class="sxs-lookup"><span data-stu-id="666ae-220">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="666ae-221">新しい API フィールドには、LinkToMTP と IncidentLinkToMTP が含まれます。</span><span class="sxs-lookup"><span data-stu-id="666ae-221">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="666ae-222">詳細については、「Microsoft Defender for Endpoint からセキュリティ センターへのアカウントMicrosoft 365[する」を参照してください](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="666ae-222">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="666ae-223">電子メール通知</span><span class="sxs-lookup"><span data-stu-id="666ae-223">Email alerts</span></span>

<span data-ttu-id="666ae-224">Defender for Endpoint の電子メール 通知は引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="666ae-224">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="666ae-225">電子メールに新しいリンクが追加され、アラート ページまたはインシデント ページがセキュリティ センター Microsoft 365されました。</span><span class="sxs-lookup"><span data-stu-id="666ae-225">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="666ae-226">詳細については、「Microsoft Defender for Endpoint からセキュリティ センターへのアカウントMicrosoft 365[する」を参照してください](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="666ae-226">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="666ae-227">関連情報</span><span class="sxs-lookup"><span data-stu-id="666ae-227">Related information</span></span>

- [<span data-ttu-id="666ae-228">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="666ae-228">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="666ae-229">Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="666ae-229">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="666ae-230">アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="666ae-230">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)