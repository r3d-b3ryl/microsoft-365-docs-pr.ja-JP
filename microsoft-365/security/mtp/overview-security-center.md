---
title: Microsoft 365 セキュリティ センターの概要
description: Microsoft 365 セキュリティ センターの利点は、Microsoft Defender for Office 365 (MDO) と Microsoft Defender for Endpoint (MDE) と Microsoft Defender for Identity (MDI) と Microsoft Cloud App Security (MCAS) の組み合わせです。 この記事では、管理者向け Microsoft 365 セキュリティ センターの概要を説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、監視、レポート、ID、データ、デバイス、アプリ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 87149ab9c99168d62f5114555a46b8bfaee83ab2
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712104"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a><span data-ttu-id="a67ca-105">統合された Microsoft 365 セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="a67ca-105">The unified Microsoft 365 security center overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="a67ca-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a67ca-106">**Applies to:**</span></span>

- [<span data-ttu-id="a67ca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a67ca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="a67ca-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a67ca-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a67ca-109">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a67ca-109">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

> <span data-ttu-id="a67ca-110">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a67ca-110">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="a67ca-111">ラボ環境 [で評価したり、パイロット](https://aka.ms/mtp-trial-lab) プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="a67ca-111">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>

<span data-ttu-id="a67ca-112">強化された **Microsoft 365** セキュリティ センター ( ) は、電子メール、コラボレーション、ID、およびデバイスの脅威に対する保護、検出、調査、および応答を中央ポータルに [https://security.microsoft.com](https://security.microsoft.com) 組み合わせたものになります。    </span><span class="sxs-lookup"><span data-stu-id="a67ca-112">The improved **Microsoft 365 security center** ([https://security.microsoft.com](https://security.microsoft.com)) combines protection, detection, investigation, and response to *email*, *collaboration*, *identity*, and *device* threats, in a central portal.</span></span>

<span data-ttu-id="a67ca-113">Microsoft 365 セキュリティ センターは、Microsoft Defender セキュリティ センターや Office 365 セキュリティ & コンプライアンス センターなど、既存の Microsoft セキュリティ ポータルの機能を統合します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-113">Microsoft 365 security center brings together functionality from existing Microsoft security portals, like Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span> <span data-ttu-id="a67ca-114">セキュリティ センターでは、情報への迅速なアクセス、レイアウトの簡易性、関連情報のまとめを重視し、使いやすくしています。</span><span class="sxs-lookup"><span data-stu-id="a67ca-114">The security center emphasizes quick access to information, simpler layouts, and bringing related information together for easier use.</span></span> <span data-ttu-id="a67ca-115">このセンターには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-115">This center includes:</span></span>

- <span data-ttu-id="a67ca-116">**[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 は、組織が電子メールを保護し、365 リソースを保護するための一連の予防、検出、調査、およびOfficeを支援します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-116">**[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 helps organizations secure their enterprise with a set of prevention, detection, investigation and hunting features to protect email, and Office 365 resources.</span></span>
- <span data-ttu-id="a67ca-117">**[Microsoft Defender for Endpoint は](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** 、組織内のデバイスに対する予防保護、侵害後の検出、自動調査、および対応を提供します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-117">**[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** delivers preventative protection, post-breach detection, automated investigation, and response for devices in your organization.</span></span>
- <span data-ttu-id="a67ca-118">**[Microsoft 365 Defender](microsoft-threat-protection.md)** は、Microsoft 365 セキュリティ ポートフォリオを活用してドメイン全体の脅威データを自動的に分析し、1 つのダッシュボードに対する攻撃の画像を作成する Microsoft の拡張検出および応答 (XDR) ソリューションの一部です。 </span><span class="sxs-lookup"><span data-stu-id="a67ca-118">**[Microsoft 365 Defender](microsoft-threat-protection.md)** is part of Microsoft’s *Extended Detection and Response* (XDR) solution that leverages the Microsoft 365 security portfolio to automatically analyze threat data across domains, and build a picture of an attack on a single dashboard.</span></span>

<span data-ttu-id="a67ca-119">コンプライアンス センターまたは Microsoft Defender セキュリティ センター Office 365 セキュリティ &変更点に関する情報が必要な場合は、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a67ca-119">If you need information about what's changed from the Office 365 Security & Compliance center or the Microsoft Defender Security Center, see:</span></span>

- [<span data-ttu-id="a67ca-120">Microsoft 365 セキュリティ センターの Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a67ca-120">Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="a67ca-121">Microsoft 365 セキュリティ センターの Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a67ca-121">Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a><span data-ttu-id="a67ca-122">何を期待する</span><span class="sxs-lookup"><span data-stu-id="a67ca-122">What to expect</span></span>

<span data-ttu-id="a67ca-123">Office 365 セキュリティ とコンプライアンス センター (protection.office.com) と Microsoft Defender セキュリティ センター (securitycenter.microsoft.com) で使用するセキュリティ コンテンツはすべて *、Microsoft 365* セキュリティ センターにあります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-123">All the security content that you use in the Office 365 Security and Compliance Center (protection.office.com) and the Microsoft Defender security center (securitycenter.microsoft.com) can now be found in the *Microsoft 365 security center*.</span></span>

<span data-ttu-id="a67ca-124">Microsoft 365 セキュリティ センターは、セキュリティ チームがさまざまなワークロードからの信号を単一の統合エクスペリエンスに収め、攻撃を調査して対応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-124">Microsoft 365 security center helps security teams investigate and respond to attacks by brining in signals from different workloads into a single, unified experiences:</span></span>

- <span data-ttu-id="a67ca-125">インシデント&アラート</span><span class="sxs-lookup"><span data-stu-id="a67ca-125">Incidents & alerts</span></span>
- <span data-ttu-id="a67ca-126">ハンティング</span><span class="sxs-lookup"><span data-stu-id="a67ca-126">Hunting</span></span>
- <span data-ttu-id="a67ca-127">アクション センター</span><span class="sxs-lookup"><span data-stu-id="a67ca-127">Action Center</span></span>
- <span data-ttu-id="a67ca-128">脅威の分析</span><span class="sxs-lookup"><span data-stu-id="a67ca-128">Threat analytics</span></span>

<span data-ttu-id="a67ca-129">Microsoft 365 セキュリティ センターでは、Microsoft Defender for Office 365 と Microsoft Defender for Endpoint が統合され、統一性、明快さ、共通の目標が強調されています。</span><span class="sxs-lookup"><span data-stu-id="a67ca-129">The Microsoft 365 security center emphasizes *unity, clarity, and common goals* as it merges Microsoft Defender for Office 365 and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a67ca-130">マージは、以下に示す優先順位に基づいて行われたので、各セキュリティ スイートが組み合わせに持ち込んだ機能を犠牲にすることなく行いました。</span><span class="sxs-lookup"><span data-stu-id="a67ca-130">The merge was based on the priorities listed below, and made without sacrificing the capabilities that each security suite brought to the combination:</span></span>

- <span data-ttu-id="a67ca-131">共通の構成要素</span><span class="sxs-lookup"><span data-stu-id="a67ca-131">common building blocks</span></span>
- <span data-ttu-id="a67ca-132">一般的な用語</span><span class="sxs-lookup"><span data-stu-id="a67ca-132">common terminology</span></span>
- <span data-ttu-id="a67ca-133">共通エンティティ</span><span class="sxs-lookup"><span data-stu-id="a67ca-133">common entities</span></span>
- <span data-ttu-id="a67ca-134">他のワークロードとの機能のパリティ</span><span class="sxs-lookup"><span data-stu-id="a67ca-134">feature parity with other workloads</span></span>

## <a name="unified-investigations"></a><span data-ttu-id="a67ca-135">統合された調査</span><span class="sxs-lookup"><span data-stu-id="a67ca-135">Unified investigations</span></span>

<span data-ttu-id="a67ca-136">セキュリティ センターを合理化すると、Microsoft 365 組織全体のインシデントを調査する 1 つのウィンドウが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-136">Streamlining security centers creates a single pane for investigating any incidents across a Microsoft 365 organization.</span></span> <span data-ttu-id="a67ca-137">主な例は **、Microsoft** 365 セキュリティ センターのクイック 起動のインシデント ノードです。</span><span class="sxs-lookup"><span data-stu-id="a67ca-137">A primary example is the **Incidents** node on the quick launch of the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO の [インシデント] ページ。":::

<span data-ttu-id="a67ca-139">たとえば、重大度が高いインシデント名をダブルクリックすると、センターを集約する利点を示すページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-139">As an example, double-clicking on an incident name with **High** severity brings you to a page that demonstrates the advantage of converging centers.</span></span>

![複数のエンドポイントでの特権エスカレーションに関する複数ステージのインシデントで、影響を受けたデバイス 16 台と影響を受けたユーザー 9 人が表示されます。](../../media/converged-incident-info-3.png)

> [!TIP]
> <span data-ttu-id="a67ca-141">[コンバージド **ユーザー]** タブは、お問い合わせを開始する際に役立つ場所です。</span><span class="sxs-lookup"><span data-stu-id="a67ca-141">The converged **Users** tab is a good place to begin your inquiries.</span></span> <span data-ttu-id="a67ca-142">この単一ページは、統合ワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、MCAS を活用している場合) と、オンプレミスの Active Directory、Azure Active Directory、同期、ローカル、サード パーティのユーザーなどのさまざまなソースからの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-142">This single page surfaces information for users from converged workloads (Microsoft Defender for Endpoint, Microsoft Defender for Identity, and MCAS, if you leverage it) and a range of sources such as on-premises Active Directory, Azure Active Directory, synced, local, and third-party users.</span></span> <span data-ttu-id="a67ca-143">新しいユーザー [エクスペリエンスの詳細については、以下を参照してください](investigate-users.md)。</span><span class="sxs-lookup"><span data-stu-id="a67ca-143">Learn more about [the new Users experience](investigate-users.md).</span></span>

<span data-ttu-id="a67ca-144">インシデント情報には、影響を受けるメールボックスの横に、ユーザー/ID 固有のデバイスと危険にさらされているデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-144">Incident information shows user/identity specifics and at-risk devices, beside affected mailboxes.</span></span> <span data-ttu-id="a67ca-145">また、調査情報と **収集された** 証拠も関連 **付けされます**。</span><span class="sxs-lookup"><span data-stu-id="a67ca-145">It also relates any **Investigation information** and gathered **Evidence**.</span></span> <span data-ttu-id="a67ca-146">これにより、管理者とセキュリティ操作チームは、リスクの高い 1 つのアラートから影響を受けるユーザーやメールボックスに簡単にピボットできます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-146">This makes it easier for admins and security operation teams to pivot from one high-risk alert to the affected users and mailboxes.</span></span> <span data-ttu-id="a67ca-147">このページの上部にある **[インシデント** ] タブを見て、この 1 つの場所から使用できる他の重要なセキュリティ ピボットがあります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-147">Looking at the **Incident** tabs at the top of this page, there are other key security pivots available from this single location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a67ca-148">特定のインシデントの任意のページの上部に、[概要]、[通知]、[デバイス]、[ユーザー]、[メールボックス]、[調査]、および [証拠] タブが **表示** されます。 </span><span class="sxs-lookup"><span data-stu-id="a67ca-148">Along the top of any page for a specific Incident, you'll see the **Summary**, **Alerts**, **Devices**, **Users**, **Mailboxes**, **Investigations**, and **Evidence** tabs.</span></span>

<span data-ttu-id="a67ca-149">[調査 **] を選択** すると、分析のグラフィックが表示されたページが開き、修復の状態 (保留中の **承認など)** が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-149">Selecting **Investigations** opens  a page that features a graphic of the analysis taking place and lists a status (such as **pending approval**) for remediation.</span></span> <span data-ttu-id="a67ca-150">環境内の特定のインシデントを選択し、これらのタブをドリルダウンし、さまざまな種類の脅威のプロファイルを作成する方法を時間を取ります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-150">Take time to select specific incidents in your environment, drill down into these tabs, and practice building a profile for different kinds of threats.</span></span> <span data-ttu-id="a67ca-151">慣れ親しみは、後で迫った調査の恩恵を受けるでしょう。</span><span class="sxs-lookup"><span data-stu-id="a67ca-151">Familiarity will benefit any later pressing investigations.</span></span>

## <a name="improved-processes"></a><span data-ttu-id="a67ca-152">プロセスの改善</span><span class="sxs-lookup"><span data-stu-id="a67ca-152">Improved processes</span></span>

<span data-ttu-id="a67ca-153">共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードに凝縮され、見つけやすくなります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-153">Common controls and content either appear in the same place, or are condensed into one feed of data making it easier to find.</span></span> <span data-ttu-id="a67ca-154">たとえば、統合された設定です。</span><span class="sxs-lookup"><span data-stu-id="a67ca-154">For example, unified settings.</span></span>

### <a name="unified-settings"></a><span data-ttu-id="a67ca-155">統合設定</span><span class="sxs-lookup"><span data-stu-id="a67ca-155">Unified settings</span></span>

![[役割] をクリックし、[設定] ページを開きます。これには、全般設定、アクセス許可、API、ルールが含まれます。](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a><span data-ttu-id="a67ca-159">ロール&アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a67ca-159">Permissions & roles</span></span>

![[アクセス許可&グループ、役割、デバイス グループ&エンドポイントの役割を示す [役割] ページ。](../../media/converged-roles-5.png)

 <span data-ttu-id="a67ca-161">Access the Microsoft 365 security center is configured with Azure Active Directory global roles or using custom roles.</span><span class="sxs-lookup"><span data-stu-id="a67ca-161">Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles.</span></span> <span data-ttu-id="a67ca-162">Defender for Endpoint については、「ユーザー アクセスを Microsoft Defender セキュリティ センターに割り [当てる」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)。</span><span class="sxs-lookup"><span data-stu-id="a67ca-162">For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access).</span></span> <span data-ttu-id="a67ca-163">Defender for Office 365 については [、「Microsoft 365](../office-365-security/permissions-microsoft-365-compliance-security.md)コンプライアンス センターのアクセス許可」および「Microsoft 365 セキュリティ センター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a67ca-163">For Defender for Office 365, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](../office-365-security/permissions-microsoft-365-compliance-security.md).</span></span>

- <span data-ttu-id="a67ca-164">[Microsoft 365 Defender へのアクセスを管理する方法の詳細](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="a67ca-164">Learn more about how to [manage access to Microsoft 365 Defender](mtp-permissions.md)</span></span>
- <span data-ttu-id="a67ca-165">Microsoft 365 セキュリティ センター [でカスタム](custom-roles.md) ロールを作成する方法の詳細</span><span class="sxs-lookup"><span data-stu-id="a67ca-165">Learn more about how to [create custom roles](custom-roles.md) in Microsoft 365 security center</span></span>

### <a name="integrated-reports"></a><span data-ttu-id="a67ca-166">統合レポート</span><span class="sxs-lookup"><span data-stu-id="a67ca-166">Integrated reports</span></span>

<span data-ttu-id="a67ca-167">レポートは、Microsoft 365 セキュリティ センターでも統合されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-167">Reports are also unified in the Microsoft 365 security center.</span></span> <span data-ttu-id="a67ca-168">管理者は、一般的なセキュリティ レポートから始め、エンドポイント、電子メール、コラボレーションに関する特定のレポート&できます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-168">Admins can start with a general security report, and branch into specific reports about endpoints, email & collaboration.</span></span> <span data-ttu-id="a67ca-169">ここでのリンクは、ワークロード構成に基づいて動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-169">The links here are dynamically generated based upon workload configuration.</span></span>

### <a name="quickly-view-your-microsoft-365-environment"></a><span data-ttu-id="a67ca-170">Microsoft 365 環境をすばやく表示する</span><span class="sxs-lookup"><span data-stu-id="a67ca-170">Quickly view your Microsoft 365 environment</span></span>

<span data-ttu-id="a67ca-171">[ **ホーム]** ページには、セキュリティ チームが必要とする一般的なカードの多くが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-171">The **Home** page shows many of the common cards that security teams need.</span></span> <span data-ttu-id="a67ca-172">カードとデータの構成は、ユーザー の役割によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-172">The composition of cards and data is dependent on the user role.</span></span> <span data-ttu-id="a67ca-173">Microsoft 365 セキュリティ センターは役割ベースのアクセス制御を使用しますので、役割ごとに、毎日のジョブにとってより意味のあるカードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-173">Because the Microsoft 365 security center uses role-based access control, different roles will see cards that are more meaningful to their day to day jobs.</span></span>  

<span data-ttu-id="a67ca-174">この一目でわかる情報は、組織内の最新のアクティビティについて把握するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-174">This at-a-glance information helps you keep up with the latest activities in your organization.</span></span> <span data-ttu-id="a67ca-175">Microsoft 365 セキュリティ センターは、さまざまなソースからの信号をまとめ、Microsoft 365 環境の全体像を示します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-175">The Microsoft 365 security center brings together signals from different sources to present a holistic view of your Microsoft 365 environment.</span></span>

<span data-ttu-id="a67ca-176">カードは次のカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-176">The cards fall into these categories:</span></span>

- <span data-ttu-id="a67ca-177">**[ID]**- 組織内の ID を監視し、疑わしい動作や危険な動作を追跡します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-177">**Identities**- Monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="a67ca-178">[ID 保護の詳細については、次の情報を参照してください](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="a67ca-178">[Learn more about identity protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>
- <span data-ttu-id="a67ca-179">**データ** - 許可されていないデータ漏えいにつながる可能性があるユーザー アクティビティの追跡に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-179">**Data** - Help track user activity that could lead to unauthorized data disclosure.</span></span>
- <span data-ttu-id="a67ca-180">**デバイス** - デバイス上のアラート、侵害アクティビティ、その他の脅威に関する最新の情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-180">**Devices** - Get up-to-date information on alerts, breach activity, and other threats on your devices.</span></span>
- <span data-ttu-id="a67ca-181">**アプリ** - クラウド アプリが組織でどのように使用されているのかについて、分析情報を得る。</span><span class="sxs-lookup"><span data-stu-id="a67ca-181">**Apps** - Gain insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="a67ca-182">[クラウド アプリ セキュリティで検出されたアプリの詳細については、次のページを参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="a67ca-182">[Learn more about Cloud App Security discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="threat-analytics-with-better-data-coverage"></a><span data-ttu-id="a67ca-183">より優れたデータカバレッジを備えた脅威分析</span><span class="sxs-lookup"><span data-stu-id="a67ca-183">Threat analytics with better data coverage</span></span>
<span data-ttu-id="a67ca-184">次の Microsoft 365 Defender 脅威分析統合エクスペリエンスを使用して、新たな脅威を追跡して対応します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-184">Track and respond to emerging threats with the following Microsoft 365 Defender threat analytics integrated experience:</span></span>

- <span data-ttu-id="a67ca-185">microsoft Defender for Endpoint と Microsoft Defender for Office 365 のデータカバレッジが向上し、インシデント管理、自動調査、修復、およびドメイン全体での予防的または事後的な脅威検出が可能になります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-185">Better data coverage between Microsoft Defender for Endpoint and Microsoft Defender for Office 365, making combined incident management, automatic investigation, remediation, and proactive or reactive threat hunting across-domain possible.</span></span> 
- <span data-ttu-id="a67ca-186">Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えて、Office 365 用 Microsoft Defender からの電子メール関連の検出と軽減策。</span><span class="sxs-lookup"><span data-stu-id="a67ca-186">Email-related detections and mitigations from Microsoft Defender for Office 365, in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="a67ca-187">Microsoft Defender for Endpoint および microsoft Defender for Office 365 全体のエンドツーエンド攻撃ストーリーにアラートを集約し、作業キューを削減し、調査を簡素化および高速化する脅威関連インシデントのビュー。</span><span class="sxs-lookup"><span data-stu-id="a67ca-187">A view of threat-related incidents which aggregate alerts into end-to-end attack stories across Microsoft Defender for Endpoint and Microsoft Defender for Office 365 to reduce the work queue, as well as simplify and speed up your investigation.</span></span>
- <span data-ttu-id="a67ca-188">Microsoft 365 Defender ソリューションによって検出およびブロックされた攻撃の試行。</span><span class="sxs-lookup"><span data-stu-id="a67ca-188">Attack attempts detected and blocked by Microsoft 365 Defender solutions.</span></span> <span data-ttu-id="a67ca-189">また、さらなる暴露のリスクを軽減し、回復力を高める予防措置を実行するために使用できるデータも用意されています。</span><span class="sxs-lookup"><span data-stu-id="a67ca-189">There's also data that you can use to drive preventive actions that mitigate the risk of further exposure and increase resilience.</span></span> 
- <span data-ttu-id="a67ca-190">アクション可能な情報をスポットライトに当てる強化された設計により、レポートに緊急に焦点を当て、調査し、活用するためのデータをすばやく特定できます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-190">Enhanced design that puts actionable information in the spotlight to help you  quickly identify data to urgently focus on, investigate, and leverage from the reports.</span></span>

## <a name="a-centralized-learning-hub"></a><span data-ttu-id="a67ca-191">集中学習ハブ</span><span class="sxs-lookup"><span data-stu-id="a67ca-191">A centralized Learning Hub</span></span>

<span data-ttu-id="a67ca-192">Microsoft 365 セキュリティ センターには、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、docs.microsoft.com の公式ドキュメントなどのリソースからの公式ガイダンスを吹き込む学習ハブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a67ca-192">The Microsoft 365 security center includes a learning hub that bubbles up official guidance from resources such as the Microsoft security blog, the Microsoft security community on YouTube, and the official documentation at docs.microsoft.com.</span></span>

<span data-ttu-id="a67ca-193">学習ハブ内では、Email & Collaboration (Microsoft Defender for Office 365 または MDO) のガイダンスは、エンドポイント (エンドポイントまたは MDE 用 Microsoft Defender)、および Microsoft 365 Defender ラーニング リソースと並べて行います。</span><span class="sxs-lookup"><span data-stu-id="a67ca-193">Inside the learning hub, Email & Collaboration (Microsoft Defender for Office 365 or MDO) guidance is side-by-side with Endpoint (Microsoft Defender for Endpoint or MDE), and Microsoft 365 Defender learning resources.</span></span>

<span data-ttu-id="a67ca-194">学習ハブが開き、「Microsoft 365 Defender を使用して調査する方法」などのトピックに関するラーニング パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-194">The learning hub opens with Learning paths organized around topics such as “How to Investigate Using Microsoft 365 Defender?”</span></span> <span data-ttu-id="a67ca-195">および "Microsoft Defender for Office 365 ベスト プラクティス"。</span><span class="sxs-lookup"><span data-stu-id="a67ca-195">and “Microsoft Defender for Office 365 Best Practices”.</span></span> <span data-ttu-id="a67ca-196">このセクションは現在、Microsoft 内のセキュリティ製品グループによって管理されています。</span><span class="sxs-lookup"><span data-stu-id="a67ca-196">This section is currently curated by the security Product Group inside Microsoft.</span></span> <span data-ttu-id="a67ca-197">各ラーニング パスには、概念の取得に要する投影時間が反映されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-197">Each Learning path reflects a projected time it takes to get through the concepts.</span></span> <span data-ttu-id="a67ca-198">たとえば、「Office 365 ユーザー アカウントの Microsoft Defender が侵害された場合に実行する手順」は、8 分かかると見なされ、その際に学習する価値があります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-198">For example 'Steps to take when a Microsoft Defender for Office 365 user account is compromised' is projected to take 8 minutes, and is valuable learning on the fly.</span></span>

<span data-ttu-id="a67ca-199">コンテンツをクリックすると、このサイトをブックマークし、ブックマークを 'Security' または 'Critical' フォルダーに整理すると便利です。</span><span class="sxs-lookup"><span data-stu-id="a67ca-199">After clicking through to the content, it may be useful to bookmark this site and organize bookmarks into a 'Security' or 'Critical' folder.</span></span> <span data-ttu-id="a67ca-200">すべてのラーニング パスを表示するには、メイン パネルの [すべて表示] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67ca-200">To see all Learning paths, click the Show all link in the main panel.</span></span>

> [!NOTE]
> <span data-ttu-id="a67ca-201">Microsoft 365 セキュリティ センターラーニング ハブの上部には、製品 (現在は Microsoft 365 Defender、Microsoft Defender for Endpoint、Microsoft Defender for Office 365) を選択できる便利なフィルターがあります。 </span><span class="sxs-lookup"><span data-stu-id="a67ca-201">There are helpful **filters** along the top of the Microsoft 365 security center learning hub that will let you choose between products (currently Microsoft 365 Defender, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365).</span></span> <span data-ttu-id="a67ca-202">各セクションの学習リソースの数が一覧表示され、学習者がトレーニングと学習に必要なリソースの数を追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-202">Notice that the number of learning resources for each section is listed, which can help learners keep track of how many resources they have at hand for training and learning.</span></span>
>
> <span data-ttu-id="a67ca-203">製品フィルターと共に、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する親しみや経験のレベル、セキュリティ ロール、製品機能が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-203">Along with the Product filter, current topics, types of resources (from videos to webinars), levels of familiarity or experience with security areas, security roles, and product features are listed.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="a67ca-204">フィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="a67ca-204">Send us your feedback</span></span>

<span data-ttu-id="a67ca-205">フィードバックが必要です。</span><span class="sxs-lookup"><span data-stu-id="a67ca-205">We need your feedback.</span></span> <span data-ttu-id="a67ca-206">常に改善を行う必要がある場合は [、Microsoft 365 Defender](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)フィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="a67ca-206">We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).</span></span>

<span data-ttu-id="a67ca-207">また、この記事からのフィードバックを残す方法があります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-207">You can also leave feedback from this article.</span></span> <span data-ttu-id="a67ca-208">[フィードバックの送信と表示] の最後にある [フィードバック] セクションで、オプションは [この *製品*] または [このページ] *です*。</span><span class="sxs-lookup"><span data-stu-id="a67ca-208">In the 'Feedback' section at the end under 'Submit and view feedback for', the options are *This product*, or *This page*.</span></span>

<span data-ttu-id="a67ca-209">製品フィードバック **には、[この製品** ] ボタン *を使用* します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-209">Use the **This product** button for *product* feedback:</span></span>

1. <span data-ttu-id="a67ca-210">記事 *の下部にある* [この製品] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-210">Select *This product* at the bottom of the article.</span></span>
    1. <span data-ttu-id="a67ca-211">これらの指示を読み続ける場合は、ボタンを右クリックし、[新しいタブで開く] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67ca-211">Right-click the button and 'Open in a new tab' if you want to keep reading these directions.</span></span>
2. <span data-ttu-id="a67ca-212">これにより **、UserVoice フォーラムに移動します**。</span><span class="sxs-lookup"><span data-stu-id="a67ca-212">This will navigate to the **UserVoice forum**.</span></span>
3. <span data-ttu-id="a67ca-213">次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a67ca-213">You have 2 options:</span></span>
    1. <span data-ttu-id="a67ca-214">テキスト ボックスまで下にスクロールする コンプライアンスを改善するか、Office *365* でユーザーを保護するには *、Microsoft 365* セキュリティ センターに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-214">Scroll down to the text box *How can we improve compliance or protect your users better in Office 365?* and paste in *Microsoft 365 security center*.</span></span> <span data-ttu-id="a67ca-215">結果を検索して、自分のようなアイデアを検索して投票するか、新しいアイデアを投稿するボタン **を使用します**。</span><span class="sxs-lookup"><span data-stu-id="a67ca-215">You can search the results for an idea like yours and up-vote it, or use the button for **Post a new idea**.</span></span>
    1. <span data-ttu-id="a67ca-216">この問題が既に報告され、投票 (または投票) でプロファイルを上げる場合は、UserVoiceの右側にある [フィードバックの提供] ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-216">If you feel certain this issue is already reported, and want to raise its profile with a vote (or votes), use the *Give Feedback* box on the right side of UserVoice.</span></span> <span data-ttu-id="a67ca-217">Microsoft *365 セキュリティ センターを検索* し、問題 **を** 検索し、投票ボタンを使用して状態を上げる。</span><span class="sxs-lookup"><span data-stu-id="a67ca-217">Search for *Microsoft 365 security center*, **find the issue, and use the vote button** to raise its status.</span></span>

<span data-ttu-id="a67ca-218">記事 *自体に* 関するフィードバックについては、このページを使用します。</span><span class="sxs-lookup"><span data-stu-id="a67ca-218">Use *This page* for feedback on the article itself.</span></span> <span data-ttu-id="a67ca-219">ご意見ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-219">Thanks for your feedback.</span></span> <span data-ttu-id="a67ca-220">お客様の声は、製品の改善に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a67ca-220">Your voice helps us improve products.</span></span>

### <a name="explore-what-the-security-center-has-to-offer"></a><span data-ttu-id="a67ca-221">セキュリティ センターが提供する機能を確認する</span><span class="sxs-lookup"><span data-stu-id="a67ca-221">Explore what the security center has to offer</span></span>

<span data-ttu-id="a67ca-222">Microsoft 365 セキュリティ センターの機能を引き続き確認してください。</span><span class="sxs-lookup"><span data-stu-id="a67ca-222">Keep exploring the features and capabilities in the Microsoft 365 security center:</span></span>

- [<span data-ttu-id="a67ca-223">インシデントとアラートの管理</span><span class="sxs-lookup"><span data-stu-id="a67ca-223">Manage incidents and alerts</span></span>](manage-incidents.md)
- [<span data-ttu-id="a67ca-224">脅威分析による新たな脅威の追跡と対応</span><span class="sxs-lookup"><span data-stu-id="a67ca-224">Track and respond to emerging threats with threat analytics</span></span>](threat-analytics.md)
- [<span data-ttu-id="a67ca-225">アクション センター</span><span class="sxs-lookup"><span data-stu-id="a67ca-225">The Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="a67ca-226">デバイス、電子メール、アプリ、および ID 間の脅威を検出する</span><span class="sxs-lookup"><span data-stu-id="a67ca-226">Hunt for threats across devices, emails, apps, and identities</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [<span data-ttu-id="a67ca-227">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="a67ca-227">Custom detection rules</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [<span data-ttu-id="a67ca-228">メール&コラボレーション通知</span><span class="sxs-lookup"><span data-stu-id="a67ca-228">Email & collaboration alerts</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- <span data-ttu-id="a67ca-229">[フィッシング攻撃シミュレーションを作成し、](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training)[チームをトレーニングするペイロードを作成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="a67ca-229">[Create a phishing attack simulation](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) and [create a payload for training your teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span></span>
 
### <a name="related-information"></a><span data-ttu-id="a67ca-230">関連情報</span><span class="sxs-lookup"><span data-stu-id="a67ca-230">Related information</span></span>
- [<span data-ttu-id="a67ca-231">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="a67ca-231">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="a67ca-232">Microsoft 365 セキュリティ Office 365 の Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a67ca-232">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="a67ca-233">Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a67ca-233">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="a67ca-234">Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="a67ca-234">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
