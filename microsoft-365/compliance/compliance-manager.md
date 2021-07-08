---
title: Microsoft コンプライアンス マネージャー
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager は、組織がリスク評価を簡素化および自動化するのに役立ち、リスクに対処するために推奨されるアクションを提案します。
ms.openlocfilehash: 536a1c02a820b0ea36fc4fe39ca1d0d31f7bc994
ms.sourcegitcommit: 48e50a5445c63d397197af2bb7549cbec0bce790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53330943"
---
# <a name="microsoft-compliance-manager"></a><span data-ttu-id="f7991-103">Microsoft コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="f7991-103">Microsoft Compliance Manager</span></span>

<span data-ttu-id="f7991-104">**この記事では、次の情報を参照してください。** コンプライアンス マネージャーとは何か、コンプライアンスの簡素化とリスクの軽減に役立つ方法、および重要なコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7991-104">**In this article:** Learn what Compliance Manager is, how it helps simplify compliance and reduce risk, and its key components.</span></span>

## <a name="whats-new-the-ga-release-of-compliance-manager"></a><span data-ttu-id="f7991-105">新機能: コンプライアンス マネージャーの GA リリース</span><span class="sxs-lookup"><span data-stu-id="f7991-105">What's new: the GA release of Compliance Manager</span></span>

<span data-ttu-id="f7991-106">コンプライアンス マネージャーは、一般に利用できる (GA) のコンプライアンス管理ソリューションとして[、Microsoft 365 コンプライアンス センター。](microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="f7991-106">Compliance Manager is now generally available (GA) as an end-to-end compliance management solution inside the [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span> <span data-ttu-id="f7991-107">このリリースでは、コンプライアンス マネージャーは Microsoft Service Trust Portal の以前の場所からの移行を完了します。</span><span class="sxs-lookup"><span data-stu-id="f7991-107">With this release, Compliance Manager completes the transition from its previous location in the Microsoft Service Trust Portal.</span></span> <span data-ttu-id="f7991-108">コンプライアンス マネージャーは、米国政府機関 (Community) (GCC) 中程度、GCC高、および国防総省 (DoD) のお客様にも利用できます。</span><span class="sxs-lookup"><span data-stu-id="f7991-108">Compliance Manager is also  available to US Government Community (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span>

<span data-ttu-id="f7991-109">コンプライアンス スコアのパブリック プレビューから始まったのは、強化されたコンプライアンス管理機能と使いやすさを備えた一元化されたツールに進化しました。</span><span class="sxs-lookup"><span data-stu-id="f7991-109">What began as the public preview of Compliance Score has evolved into a centralized tool with enhanced compliance management capabilities and greater ease of use.</span></span>  <span data-ttu-id="f7991-110">GA リリースでは、コンプライアンス 活動の拡大に役立つ、事前に構築された評価のコレクションが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="f7991-110">The GA release brings a larger collection of pre-built assessments to help you scale your compliance activities.</span></span>

<span data-ttu-id="f7991-111">**GA リリースの詳細については、次の情報を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="f7991-111">**Learn more about the GA release:**</span></span>
- <span data-ttu-id="f7991-112">よく [寄せられる質問は](compliance-manager-faq.yml) 、進化の詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="f7991-112">Our [frequently asked questions](compliance-manager-faq.yml) walk you through the evolution in greater detail.</span></span>
- <span data-ttu-id="f7991-113">このブログ記事の GA 機能拡張 [について説明します](https://aka.ms/compliancemanager/GAblog)。</span><span class="sxs-lookup"><span data-stu-id="f7991-113">Read about GA feature enhancements in [this blog post](https://aka.ms/compliancemanager/GAblog).</span></span>

<span data-ttu-id="f7991-114">コンプライアンス マネージャーが組織がコンプライアンスを管理する方法を簡略化する方法については、以下のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7991-114">Watch the video below to learn how Compliance Manager can help simplify how your organization manages compliance:</span></span>
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a><span data-ttu-id="f7991-115">コンプライアンス マネージャーとは</span><span class="sxs-lookup"><span data-stu-id="f7991-115">What is Compliance Manager</span></span>

<span data-ttu-id="f7991-116">[Microsoft コンプライアンス マネージャー](https://compliance.microsoft.com/compliancemanager)は、組織[](microsoft-365-compliance-center.md)Microsoft 365 コンプライアンス センターのコンプライアンス要件を簡単に管理し、利便性を高め、管理するのに役立つ機能です。</span><span class="sxs-lookup"><span data-stu-id="f7991-116">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that helps you manage your organization’s compliance requirements with greater ease and convenience.</span></span> <span data-ttu-id="f7991-117">コンプライアンス マネージャーは、データ保護リスクのインベントリの取得から、制御の実装の複雑さの管理、規制と認定の最新の状態を確保すること、監査人への報告まで、コンプライアンスの取り組み全体を通じてお手伝いします。</span><span class="sxs-lookup"><span data-stu-id="f7991-117">Compliance Manager can help you throughout your compliance journey, from taking inventory of your data protection risks to managing the complexities of implementing controls, staying current with regulations and certifications, and reporting to auditors.</span></span>

<span data-ttu-id="f7991-118">コンプライアンス マネージャーは、次の機能を提供することで、コンプライアンスの簡素化とリスクの軽減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f7991-118">Compliance Manager helps simplify compliance and reduce risk by providing:</span></span>

- <span data-ttu-id="f7991-119">一般的な業界および地域の標準および規制に対する事前構築された評価、または独自のコンプライアンスニーズを満たすカスタム評価 (利用可能な評価は、ライセンス契約によって異なる。 [詳細については、「詳細」を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance))。</span><span class="sxs-lookup"><span data-stu-id="f7991-119">Pre-built assessments for common industry and regional standards and regulations, or custom assessments to meet your unique compliance needs (available assessments depend on your licensing agreement; [learn more](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)).</span></span>

- <span data-ttu-id="f7991-120">1 つのツールを使用してリスク評価を効率的に完了するのに役立つワークフロー機能。</span><span class="sxs-lookup"><span data-stu-id="f7991-120">Workflow capabilities to help you efficiently complete your risk assessments through a single tool.</span></span>

- <span data-ttu-id="f7991-121">組織に最も関連性の高い標準と規制を遵守するための推奨される改善措置に関する詳細なステップ バイ ステップ ガイダンス。</span><span class="sxs-lookup"><span data-stu-id="f7991-121">Detailed step-by-step guidance on suggested improvement actions to help you comply with the standards and regulations that are most relevant for your organization.</span></span> <span data-ttu-id="f7991-122">Microsoft によって管理されるアクションについては、実装の詳細と監査結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7991-122">For actions that are managed by Microsoft, you’ll see implementation details and audit results.</span></span>

- <span data-ttu-id="f7991-123">改善アクションの進捗を測定することで、コンプライアンスの姿勢を理解するのに役立つリスクベースのコンプライアンス スコア。</span><span class="sxs-lookup"><span data-stu-id="f7991-123">A risk-based compliance score to help you understand your compliance posture by measuring your progress in completing improvement actions.</span></span>

<span data-ttu-id="f7991-124">コンプライアンス マネージャー ダッシュボードには、現在のコンプライアンス スコアが表示され、注意が必要な情報が表示され、重要な改善アクションが示されます。</span><span class="sxs-lookup"><span data-stu-id="f7991-124">Your Compliance Manager dashboard shows your current compliance score, helps you see what needs attention, and guides you to key improvement actions.</span></span> <span data-ttu-id="f7991-125">コンプライアンス マネージャー ダッシュボードの外観の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f7991-125">Below is an example of what your Compliance Manager dashboard will look like:</span></span>

<span data-ttu-id="f7991-126">![コンプライアンス マネージャー - ダッシュ ボード](../media/compliance-manager-dashboard.png "コンプライアンス マネージャーのダッシュ ボード")</span><span class="sxs-lookup"><span data-stu-id="f7991-126">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

## <a name="understanding-your-compliance-score"></a><span data-ttu-id="f7991-127">コンプライアンス スコアについて</span><span class="sxs-lookup"><span data-stu-id="f7991-127">Understanding your compliance score</span></span>

<span data-ttu-id="f7991-128">コンプライアンス マネージャーは、規制、標準、またはポリシーに準拠するために実行される改善アクションを完了するためのポイントを与え、それらのポイントを全体的なコンプライアンス スコアに結合します。</span><span class="sxs-lookup"><span data-stu-id="f7991-128">Compliance Manager awards you points for completing improvement actions taken to comply with a regulation, standard, or policy, and combines those points into an overall compliance score.</span></span> <span data-ttu-id="f7991-129">各アクションは、関連する潜在的なリスクに応じてスコアに異なる影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="f7991-129">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="f7991-130">コンプライアンス スコアは、コンプライアンスの全体的な姿勢を向上させるために、どのアクションに重点を置くのかの優先順位を付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f7991-130">Your compliance score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="f7991-131">コンプライアンス マネージャーは、Microsoft 365 データ保護ベースラインに基づいて、初期スコアを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7991-131">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="f7991-132">このベースラインは、データ保護と一般的なデータ ガバナンスに関する主要な規制と基準を含む一連のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="f7991-132">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="f7991-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f7991-133">Learn more</span></span>

<span data-ttu-id="f7991-134">[コンプライアンス スコアの計算方法を理解します](compliance-score-calculation.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-134">[Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

<span data-ttu-id="f7991-135">[改善アクションを操作する方法について学習します](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-135">[Learn how to work with improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="f7991-136">重要な要素: コントロール、評価、テンプレート、改善アクション</span><span class="sxs-lookup"><span data-stu-id="f7991-136">Key elements: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="f7991-137">コンプライアンス マネージャーは、コンプライアンス アクティビティの管理に役立つ複数のデータ要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7991-137">Compliance Manager uses several data elements to help you manage your compliance activities.</span></span> <span data-ttu-id="f7991-138">コンプライアンス マネージャーを使用してコンプライアンス アクティビティを割り当て、テストし、監視する場合は、コントロール、評価、テンプレート、および改善アクションという重要な要素について基本的な理解を深めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f7991-138">As you use Compliance Manager to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key elements: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="f7991-139">コントロール</span><span class="sxs-lookup"><span data-stu-id="f7991-139">Controls</span></span>

<span data-ttu-id="f7991-140">コントロールは、規制、標準、またはポリシーの要件のことです。</span><span class="sxs-lookup"><span data-stu-id="f7991-140">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="f7991-141">コントロールは、システム構成、組織のプロセス、および規制、標準、ポリシーの特定の要件への準拠に関する責任者を評価し、管理する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f7991-141">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="f7991-142">コンプライアンス マネージャーは、次の種類のコントロールを追跡します。</span><span class="sxs-lookup"><span data-stu-id="f7991-142">Compliance Manager tracks the following types of controls:</span></span>

1. <span data-ttu-id="f7991-143">**Microsoft マネージ コントロール**: Microsoft クラウド サービスのコントロール(Microsoft が実装を担当する)</span><span class="sxs-lookup"><span data-stu-id="f7991-143">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="f7991-144">**コントロール**: 顧客管理コントロールと呼ばれる場合があります。これらは組織によって実装および管理されるコントロールです。</span><span class="sxs-lookup"><span data-stu-id="f7991-144">**Your controls**: sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
3. <span data-ttu-id="f7991-145">**共有コントロール**: これらは、組織と Microsoft の両方が実装の責任を共有するコントロールです。</span><span class="sxs-lookup"><span data-stu-id="f7991-145">**Shared controls**: these are controls that both your organization and Microsoft share responsibility for implementing</span></span>

##### <a name="learn-more"></a><span data-ttu-id="f7991-146">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f7991-146">Learn more</span></span>

<span data-ttu-id="f7991-147">[コントロールの進行状況を監視します](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)。</span><span class="sxs-lookup"><span data-stu-id="f7991-147">[Monitor progress of your controls](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).</span></span>

<span data-ttu-id="f7991-148">[コンプライアンス マネージャーがコントロールを継続的に評価する方法について学習します](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)。</span><span class="sxs-lookup"><span data-stu-id="f7991-148">[Learn how Compliance Manager continuously assesses controls](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="f7991-149">評価</span><span class="sxs-lookup"><span data-stu-id="f7991-149">Assessments</span></span>

<span data-ttu-id="f7991-150">評価とは、特定の規制、標準、またはポリシーからのコントロールのグループ化です。</span><span class="sxs-lookup"><span data-stu-id="f7991-150">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="f7991-151">評価は、標準、規則、または法律の要件を満たすのに役立つ評価内で処置を完了します。</span><span class="sxs-lookup"><span data-stu-id="f7991-151">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="f7991-152">たとえば、その中のすべてのアクションを完了すると、ISO 27001 の要件に沿った Microsoft 365 設定を作成するのに役立つ評価を受ける場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7991-152">For example, you may have an assessment that, when you complete all actions within it, helps to bring your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="f7991-153">評価には、次のいくつかのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="f7991-153">Assessments have several components:</span></span>

- <span data-ttu-id="f7991-154">**範囲内のサービス**: 評価に適用される Microsoft サービスの特定のセット</span><span class="sxs-lookup"><span data-stu-id="f7991-154">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="f7991-155">**Microsoft マネージ コントロール**: Microsoft クラウド サービスのコントロール。Microsoft がユーザーに代わって実装する</span><span class="sxs-lookup"><span data-stu-id="f7991-155">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft implements on your behalf</span></span>
- <span data-ttu-id="f7991-156">**コントロール**: 顧客管理コントロールと呼ばれる場合があります。これらは組織によって実装および管理されるコントロールです。</span><span class="sxs-lookup"><span data-stu-id="f7991-156">**Your controls**: sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
- <span data-ttu-id="f7991-157">**共有コントロール**: これらは、組織と Microsoft の両方が実装の責任を共有するコントロールです。</span><span class="sxs-lookup"><span data-stu-id="f7991-157">**Shared controls**: these are controls that both your organization and Microsoft share responsibility for implementing</span></span>
- <span data-ttu-id="f7991-158">**評価スコア**: 組織と Microsoft が管理する評価内のアクションから、可能な合計ポイントを達成するための進捗状況を示します。</span><span class="sxs-lookup"><span data-stu-id="f7991-158">**Assessment score**: shows your progress in achieving total possible points from actions within the assessment that are managed by your organization and by Microsoft</span></span>

<span data-ttu-id="f7991-159">評価を作成する場合は、それらをグループに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7991-159">When creating assessments, you’ll assign them to a group.</span></span> <span data-ttu-id="f7991-160">組織にとって最も論理的な方法でグループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f7991-160">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="f7991-161">たとえば、監査年、地域、ソリューション、組織内のチーム、その他の方法で評価をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="f7991-161">For example, you may group assessments by audit year, region, solution, teams within your organization, or some other way.</span></span> <span data-ttu-id="f7991-162">グループを作成したら、コンプライアンス マネージャー [ダッシュボード](compliance-manager-setup.md#filtering-your-dashboard-view) をフィルター処理して、1 つ以上のグループでスコアを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f7991-162">Once you create groups, you can [filter your Compliance Manager dashboard](compliance-manager-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="f7991-163">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f7991-163">Learn more</span></span>

<span data-ttu-id="f7991-164">[コンプライアンス マネージャーで評価を構築および管理します](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-164">[Build and manage assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="f7991-165">テンプレート</span><span class="sxs-lookup"><span data-stu-id="f7991-165">Templates</span></span>

<span data-ttu-id="f7991-166">コンプライアンス マネージャーには、評価をすばやく作成するためのテンプレートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="f7991-166">Compliance Manager provides templates to help you quickly create assessments.</span></span> <span data-ttu-id="f7991-167">これらのテンプレートを変更して、ニーズに合った評価を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f7991-167">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="f7991-168">独自のコントロールとアクションを使用してテンプレートを作成することで、カスタム評価を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7991-168">You can also build a custom assessment by creating a template with your own controls and actions.</span></span> <span data-ttu-id="f7991-169">たとえば、テンプレートが内部のビジネス プロセスコントロール、または 325 以上の事前に構築された評価テンプレートの 1 つでカバーされていない地域のデータ保護標準をカバーする場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7991-169">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our 325+ pre-built assessment templates.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="f7991-170">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f7991-170">Learn more</span></span>

<span data-ttu-id="f7991-171">[コンプライアンス マネージャーによって提供される評価テンプレートの一覧を表示します](compliance-manager-templates-list.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-171">[View the list of assessment templates provided by Compliance Manager](compliance-manager-templates-list.md).</span></span>

<span data-ttu-id="f7991-172">[評価用のテンプレートを作成および変更するための詳細な手順を取得します](compliance-manager-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-172">[Get detailed instructions for creating and modifying templates for assessments](compliance-manager-templates.md).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="f7991-173">改善のための処置</span><span class="sxs-lookup"><span data-stu-id="f7991-173">Improvement actions</span></span>

<span data-ttu-id="f7991-174">改善アクションは、コンプライアンス活動を一元化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f7991-174">Improvement actions help centralize your compliance activities.</span></span> <span data-ttu-id="f7991-175">各改善アクションは、データ保護の規制と標準に合わせて役立つ推奨ガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7991-175">Each improvement action provides recommended guidance that’s intended to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="f7991-176">改善のための処置は、実装やテスト作業を行う組織内のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f7991-176">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="f7991-177">また、改善のための処置の中にドキュメント、メモ、記録状態の更新を保存することができます。</span><span class="sxs-lookup"><span data-stu-id="f7991-177">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="f7991-178">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f7991-178">Learn more</span></span>

<span data-ttu-id="f7991-179">[コンプライアンス ワークフローを管理するには、改善アクションを使用します](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-179">[Use improvement actions to manage your compliance workflow](compliance-manager-improvement-actions.md).</span></span>

<span data-ttu-id="f7991-180">[アクションがコンプライアンス スコアに与える影響について学習します](compliance-score-calculation.md#action-types-and-points)。</span><span class="sxs-lookup"><span data-stu-id="f7991-180">[Learn how actions impact your compliance score](compliance-score-calculation.md#action-types-and-points).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="f7991-181">サポートされている言語</span><span class="sxs-lookup"><span data-stu-id="f7991-181">Supported languages</span></span>

<span data-ttu-id="f7991-182">コンプライアンス マネージャーは、次の言語で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7991-182">Compliance Manager is available in the following languages:</span></span>

- <span data-ttu-id="f7991-183">英語</span><span class="sxs-lookup"><span data-stu-id="f7991-183">English</span></span>
- <span data-ttu-id="f7991-184">Bahasa インドネシア語</span><span class="sxs-lookup"><span data-stu-id="f7991-184">Bahasa Indonesian</span></span>
- <span data-ttu-id="f7991-185">バハサ マレー語</span><span class="sxs-lookup"><span data-stu-id="f7991-185">Bahasa Malay</span></span>
- <span data-ttu-id="f7991-186">簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="f7991-186">Chinese (Simplified)</span></span>
- <span data-ttu-id="f7991-187">繁体字中国語</span><span class="sxs-lookup"><span data-stu-id="f7991-187">Chinese (Traditional)</span></span>
- <span data-ttu-id="f7991-188">チェコ語</span><span class="sxs-lookup"><span data-stu-id="f7991-188">Czech</span></span>
- <span data-ttu-id="f7991-189">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="f7991-189">Danish</span></span>
- <span data-ttu-id="f7991-190">オランダ語</span><span class="sxs-lookup"><span data-stu-id="f7991-190">Dutch</span></span>
- <span data-ttu-id="f7991-191">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="f7991-191">Finnish</span></span>
- <span data-ttu-id="f7991-192">フランス語</span><span class="sxs-lookup"><span data-stu-id="f7991-192">French</span></span>
- <span data-ttu-id="f7991-193">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="f7991-193">German</span></span>
- <span data-ttu-id="f7991-194">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="f7991-194">Hebrew</span></span>
- <span data-ttu-id="f7991-195">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="f7991-195">Hungarian</span></span>
- <span data-ttu-id="f7991-196">イタリア語</span><span class="sxs-lookup"><span data-stu-id="f7991-196">Italian</span></span>
- <span data-ttu-id="f7991-197">日本語</span><span class="sxs-lookup"><span data-stu-id="f7991-197">Japanese</span></span>
- <span data-ttu-id="f7991-198">韓国語</span><span class="sxs-lookup"><span data-stu-id="f7991-198">Korean</span></span>
- <span data-ttu-id="f7991-199">ノルウェー語</span><span class="sxs-lookup"><span data-stu-id="f7991-199">Norwegian</span></span>
- <span data-ttu-id="f7991-200">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="f7991-200">Polish</span></span>
- <span data-ttu-id="f7991-201">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="f7991-201">Portuguese (Brazilian)</span></span>
- <span data-ttu-id="f7991-202">ロシア語</span><span class="sxs-lookup"><span data-stu-id="f7991-202">Russian</span></span>
- <span data-ttu-id="f7991-203">スペイン語</span><span class="sxs-lookup"><span data-stu-id="f7991-203">Spanish</span></span>
- <span data-ttu-id="f7991-204">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="f7991-204">Swedish</span></span>
- <span data-ttu-id="f7991-205">タイ語</span><span class="sxs-lookup"><span data-stu-id="f7991-205">Thai</span></span>
- <span data-ttu-id="f7991-206">トルコ語</span><span class="sxs-lookup"><span data-stu-id="f7991-206">Turkish</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="f7991-207">次の手順: セットアップとカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f7991-207">Next steps: set up and customize</span></span>

<span data-ttu-id="f7991-208">「コンプライアンス マネージャーの使用を開始する」で、サインイン、アクセス許可と役割の割り当て、設定の構成、ダッシュボード ビューのカスタマイズを行う [方法について学習します](compliance-manager-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-208">Learn how to sign in, assign permissions and roles, configure settings, and personalize your dashboard view at [Get started with Compliance Manager](compliance-manager-setup.md).</span></span>

<span data-ttu-id="f7991-209">次に、コンプライアンス マネージャーのカスタマイズを開始し、評価を設定することで、組織にとって最も重要な業界標準に [準拠できます](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-209">Then start customizing Compliance Manager to help you comply with industry standards that matter most to your organization by [setting up assessments](compliance-manager-assessments.md).</span></span>

<span data-ttu-id="f7991-210">データ プライバシー規制の遵守を支援するために、コンプライアンス マネージャーの使用を含め、Microsoft 365 全体で機能を計画および実装するためのエンド Microsoft 365 プロセスをガイドするワークフローを設計しました。</span><span class="sxs-lookup"><span data-stu-id="f7991-210">To help you comply with data privacy regulations, we’ve designed a workflow to guide you through an end-to-end process to plan and implement capabilities across Microsoft 365, including using Compliance Manager.</span></span> <span data-ttu-id="f7991-211">詳細については、「[Microsoft 365を使用したデータプライバシー規制の情報保護の展開 (aka.ms/m365dataprivacy)](../solutions/information-protection-deploy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7991-211">For more information, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span></span> 