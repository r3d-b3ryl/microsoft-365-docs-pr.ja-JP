---
title: Microsoft コンプライアンスマネージャー
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
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
description: Microsoft コンプライアンスマネージャーを使用すると、組織はリスク評価を簡略化および自動化し、リスクに対処するための推奨される処置を提案します。
ms.openlocfilehash: 4508f07b0077d409de1ac033de67d20d1c3f2a7e
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072936"
---
# <a name="microsoft-compliance-manager"></a><span data-ttu-id="4496e-103">Microsoft コンプライアンスマネージャー</span><span class="sxs-lookup"><span data-stu-id="4496e-103">Microsoft Compliance Manager</span></span>

<span data-ttu-id="4496e-104">**この記事の内容** コンプライアンスマネージャーとは何か、コンプライアンスを簡素化してリスクを軽減する方法、および主要なコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4496e-104">**In this article:** Learn what Compliance Manager is, how it helps simplify compliance and reduce risk, and its key components.</span></span>

## <a name="whats-new-the-ga-release-of-compliance-manager"></a><span data-ttu-id="4496e-105">新機能: コンプライアンスマネージャーの GA リリース</span><span class="sxs-lookup"><span data-stu-id="4496e-105">What's new: the GA release of Compliance Manager</span></span>

<span data-ttu-id="4496e-106">コンプライアンスマネージャーは、一般公開 (GA) として、 [Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)内のエンドツーエンドのコンプライアンス管理ソリューションとして提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4496e-106">Compliance Manager is now generally available (GA) as an end-to-end compliance management solution inside the [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span> <span data-ttu-id="4496e-107">このリリースでは、コンプライアンスマネージャーは、Microsoft Service Trust Portal の以前の場所から移行を完了します。</span><span class="sxs-lookup"><span data-stu-id="4496e-107">With this release, Compliance Manager completes the transition from its previous location in the Microsoft Service Trust Portal.</span></span> <span data-ttu-id="4496e-108">また、コンプライアンスマネージャーは米国政府機関 (GCC) のお客様にも提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4496e-108">Compliance Manager is also now available to US Government Community (GCC) Moderate customers.</span></span>

<span data-ttu-id="4496e-109">コンプライアンススコアのパブリックプレビューとして開始されたものは、コンプライアンス管理機能が強化され、使いやすさが向上した一元的なツールに発展しました。</span><span class="sxs-lookup"><span data-stu-id="4496e-109">What began as the public preview of Compliance Score has evolved into a centralized tool with enhanced compliance management capabilities and greater ease of use.</span></span>  <span data-ttu-id="4496e-110">GA リリースは、コンプライアンスアクティビティを拡張するのに役立つ、事前に作成された評価のコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="4496e-110">The GA release brings a larger collection of pre-built assessments to help you scale your compliance activities.</span></span>

<span data-ttu-id="4496e-111">**GA リリースの詳細については、以下を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="4496e-111">**Learn more about the GA release:**</span></span>
- <span data-ttu-id="4496e-112">[よく寄せられる質問](compliance-manager-faq.md)では、展開について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="4496e-112">Our [frequently asked questions](compliance-manager-faq.md) walk you through the evolution in greater detail.</span></span>
- <span data-ttu-id="4496e-113">[このブログ投稿](https://aka.ms/compliancemanager/GAblog)の GA 機能の拡張についてお読みください。</span><span class="sxs-lookup"><span data-stu-id="4496e-113">Read about GA feature enhancements in [this blog post](https://aka.ms/compliancemanager/GAblog).</span></span>

<span data-ttu-id="4496e-114">コンプライアンスマネージャーが組織によるコンプライアンスの管理を簡単にする方法については、以下のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4496e-114">Watch the video below to learn how Compliance Manager can help simplify how your organization manages compliance:</span></span>
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a><span data-ttu-id="4496e-115">コンプライアンスマネージャーとは</span><span class="sxs-lookup"><span data-stu-id="4496e-115">What is Compliance Manager</span></span>

<span data-ttu-id="4496e-116">[Microsoft コンプライアンスマネージャー](https://compliance.microsoft.com/compliancemanager) は、 [microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md) の機能です。これにより、組織のコンプライアンス要件をより簡単かつ便利に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4496e-116">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that helps you manage your organization’s compliance requirements with greater ease and convenience.</span></span> <span data-ttu-id="4496e-117">コンプライアンスマネージャーは、データ保護のリスクのインベントリを取って、統制の実装の複雑さを管理し、現在の規制と証明書を維持し、監査担当者に報告することから、コンプライアンスへの移行を通じてお客様を支援します。</span><span class="sxs-lookup"><span data-stu-id="4496e-117">Compliance Manager can help you throughout your compliance journey, from taking inventory of your data protection risks to managing the complexities of implementing controls, staying current with regulations and certifications, and reporting to auditors.</span></span>

<span data-ttu-id="4496e-118">コンプライアンスマネージャーは、コンプライアンスを簡素化し、以下を提供することによりリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="4496e-118">Compliance Manager helps simplify compliance and reduce risk by providing:</span></span>

- <span data-ttu-id="4496e-119">一般的な業界および地域の標準および規制の事前に作成された評価、または独自のコンプライアンスニーズに応じたカスタム評価 (利用可能な評価はライセンス契約によって異なります。 [詳細をご覧](https://go.microsoft.com/fwlink/?linkid=2132371)ください)。</span><span class="sxs-lookup"><span data-stu-id="4496e-119">Pre-built assessments for common industry and regional standards and regulations, or custom assessments to meet your unique compliance needs (available assessments depend on your licensing agreement; [learn more](https://go.microsoft.com/fwlink/?linkid=2132371)).</span></span>

- <span data-ttu-id="4496e-120">単一のツールを使用してリスク評価を効率的に完了するためのワークフロー機能。</span><span class="sxs-lookup"><span data-stu-id="4496e-120">Workflow capabilities to help you efficiently complete your risk assessments through a single tool.</span></span>

- <span data-ttu-id="4496e-121">お客様の組織にとって最も関連性のある基準と規制に準拠するために役立つ、推奨される改善アクションの詳細なステップごとのガイダンス。</span><span class="sxs-lookup"><span data-stu-id="4496e-121">Detailed step-by-step guidance on suggested improvement actions to help you comply with the standards and regulations that are most relevant for your organization.</span></span> <span data-ttu-id="4496e-122">Microsoft によって管理されるアクションについては、「実装の詳細と監査結果」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4496e-122">For actions that are managed by Microsoft, you’ll see implementation details and audit results.</span></span>

- <span data-ttu-id="4496e-123">リスクベースのコンプライアンススコア。これにより、改善アクションの完了の進捗状況を測定することによって、コンプライアンスの姿勢を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4496e-123">A risk-based compliance score to help you understand your compliance posture by measuring your progress in completing improvement actions.</span></span>

<span data-ttu-id="4496e-124">コンプライアンスマネージャーのダッシュボードには、現在のコンプライアンススコアが表示され、注意が必要な事項が表示されます。また、重要な改善アクションを案内します。</span><span class="sxs-lookup"><span data-stu-id="4496e-124">Your Compliance Manager dashboard shows your current compliance score, helps you see what needs attention, and guides you to key improvement actions.</span></span> <span data-ttu-id="4496e-125">コンプライアンスマネージャーのダッシュボードがどのように表示されるかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4496e-125">Below is an example of what your Compliance Manager dashboard will look like:</span></span>

<span data-ttu-id="4496e-126">![コンプライアンスマネージャー-ダッシュボード](../media/compliance-manager-dashboard.png "コンプライアンスマネージャーダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="4496e-126">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

## <a name="understanding-your-compliance-score"></a><span data-ttu-id="4496e-127">コンプライアンススコアを理解する</span><span class="sxs-lookup"><span data-stu-id="4496e-127">Understanding your compliance score</span></span>

<span data-ttu-id="4496e-128">コンプライアンスマネージャー賞は、規制、標準、またはポリシーに準拠するために行われた改善アクションを完了するためのもので、それらのポイントを総合的なコンプライアンススコアに結合します。</span><span class="sxs-lookup"><span data-stu-id="4496e-128">Compliance Manager awards you points for completing improvement actions taken to comply with a regulation, standard, or policy, and combines those points into an overall compliance score.</span></span> <span data-ttu-id="4496e-129">各アクションは、発生する可能性のあるリスクに応じて、スコアにさまざまな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="4496e-129">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="4496e-130">コンプライアンススコアは、全体的なコンプライアンスの姿勢を改善するために、どのアクションに焦点を当てるかを優先することができます。</span><span class="sxs-lookup"><span data-stu-id="4496e-130">Your compliance score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="4496e-131">コンプライアンスマネージャーには、Microsoft 365 データ保護基準に基づく初期スコアが与えられます。</span><span class="sxs-lookup"><span data-stu-id="4496e-131">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="4496e-132">このベースラインは、データ保護と一般的なデータガバナンスに関する主要な規制と標準を含む一連のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="4496e-132">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4496e-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4496e-133">Learn more</span></span>

<span data-ttu-id="4496e-134">[コンプライアンススコアの計算方法について理解](compliance-score-calculation.md)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-134">[Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

<span data-ttu-id="4496e-135">[改善アクションを操作する方法について説明](compliance-manager-improvement-actions.md)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-135">[Learn how to work with improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="4496e-136">主な要素: コントロール、評価、テンプレート、改善アクション</span><span class="sxs-lookup"><span data-stu-id="4496e-136">Key elements: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="4496e-137">コンプライアンスマネージャーは、コンプライアンスアクティビティを管理するために、いくつかのデータ要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="4496e-137">Compliance Manager uses several data elements to help you manage your compliance activities.</span></span> <span data-ttu-id="4496e-138">コンプライアンスマネージャーを使用してコンプライアンスアクティビティの割り当て、テスト、および監視を行う際には、主要な要素であるコントロール、評価、テンプレート、改善アクションについて、基本的な理解を深めることができます。</span><span class="sxs-lookup"><span data-stu-id="4496e-138">As you use Compliance Manager to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key elements: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="4496e-139">コントロール</span><span class="sxs-lookup"><span data-stu-id="4496e-139">Controls</span></span>

<span data-ttu-id="4496e-140">コントロールは、規制、標準、またはポリシーの要件です。</span><span class="sxs-lookup"><span data-stu-id="4496e-140">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="4496e-141">システム構成、組織プロセス、および規制、標準、またはポリシーの特定の要件を満たす責任者を評価および管理する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="4496e-141">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="4496e-142">コンプライアンスマネージャーは、次の種類のコントロールを追跡します。</span><span class="sxs-lookup"><span data-stu-id="4496e-142">Compliance Manager tracks the following types of controls:</span></span>

1. <span data-ttu-id="4496e-143">**Microsoft managed controls** : microsoft クラウドサービスのコントロール (microsoft が実装する責任者)</span><span class="sxs-lookup"><span data-stu-id="4496e-143">**Microsoft managed controls** : controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="4496e-144">顧客管理コントロールと呼ばれることもあり **ます。これらのコントロールは** 、組織によって実装および管理されます。</span><span class="sxs-lookup"><span data-stu-id="4496e-144">**Your controls** : sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
3. <span data-ttu-id="4496e-145">**共有コントロール** : これらのコントロールは、組織と Microsoft 共有の両方が責任を負うことになります。</span><span class="sxs-lookup"><span data-stu-id="4496e-145">**Shared controls** : these are controls that both your organization and Microsoft share responsibility for implementing</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4496e-146">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4496e-146">Learn more</span></span>

<span data-ttu-id="4496e-147">[コントロールの進行状況を監視](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-147">[Monitor progress of your controls](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).</span></span>

<span data-ttu-id="4496e-148">[コンプライアンスマネージャーが継続的に制御を評価する方法について説明](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-148">[Learn how Compliance Manager continuously assesses controls](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="4496e-149">講習</span><span class="sxs-lookup"><span data-stu-id="4496e-149">Assessments</span></span>

<span data-ttu-id="4496e-150">評価は、特定の規制、標準、またはポリシーによって制御をグループ化したものです。</span><span class="sxs-lookup"><span data-stu-id="4496e-150">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="4496e-151">評価でのアクションの完了は、標準、規制、または法律の要件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4496e-151">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="4496e-152">たとえば、すべてのアクションを完了したときに、ISO 27001 の要件に合わせて Microsoft 365 の設定をオンラインにするための評価を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4496e-152">For example, you may have an assessment that, when you complete all actions within it, helps to bring your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="4496e-153">評価にはいくつかのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="4496e-153">Assessments have several components:</span></span>

- <span data-ttu-id="4496e-154">**スコープ内サービス** : 評価に適用可能な Microsoft サービスの特定のセット</span><span class="sxs-lookup"><span data-stu-id="4496e-154">**In-scope services** : the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="4496e-155">**Microsoft managed controls** : microsoft がお客様の代わりに実装する microsoft クラウドサービスのコントロール</span><span class="sxs-lookup"><span data-stu-id="4496e-155">**Microsoft managed controls** : controls for Microsoft cloud services, which Microsoft implements on your behalf</span></span>
- <span data-ttu-id="4496e-156">顧客管理コントロールと呼ばれることもあり **ます。これらのコントロールは** 、組織によって実装および管理されます。</span><span class="sxs-lookup"><span data-stu-id="4496e-156">**Your controls** : sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
- <span data-ttu-id="4496e-157">**共有コントロール** : これらのコントロールは、組織と Microsoft 共有の両方が責任を負うことになります。</span><span class="sxs-lookup"><span data-stu-id="4496e-157">**Shared controls** : these are controls that both your organization and Microsoft share responsibility for implementing</span></span>
- <span data-ttu-id="4496e-158">**評価スコア** : 組織で管理されている、Microsoft によって管理されている評価内のアクションからの総ポイントを実現するための進行状況を示します。</span><span class="sxs-lookup"><span data-stu-id="4496e-158">**Assessment score** : shows your progress in achieving total possible points from actions within the assessment that are managed by your organization and by Microsoft</span></span>

<span data-ttu-id="4496e-159">評価を作成する場合は、それらをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4496e-159">When creating assessments, you’ll assign them to a group.</span></span> <span data-ttu-id="4496e-160">組織にとって最も論理的な方法でグループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4496e-160">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="4496e-161">たとえば、監査年、地域、ソリューション、組織内のチーム、またはその他の方法で評価をグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="4496e-161">For example, you may group assessments by audit year, region, solution, teams within your organization, or some other way.</span></span> <span data-ttu-id="4496e-162">グループを作成すると、 [コンプライアンスマネージャーダッシュボードをフィルター処理](compliance-manager-setup.md#filtering-your-dashboard-view) して、1つまたは複数のグループでスコアを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4496e-162">Once you create groups, you can [filter your Compliance Manager dashboard](compliance-manager-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4496e-163">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4496e-163">Learn more</span></span>

<span data-ttu-id="4496e-164">[コンプライアンスマネージャーで評価を作成および管理](compliance-manager-assessments.md)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-164">[Build and manage assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="4496e-165">テンプレート</span><span class="sxs-lookup"><span data-stu-id="4496e-165">Templates</span></span>

<span data-ttu-id="4496e-166">コンプライアンスマネージャーには、評価をすばやく作成するために役立つテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4496e-166">Compliance Manager provides templates to help you quickly create assessments.</span></span> <span data-ttu-id="4496e-167">これらのテンプレートを変更して、ニーズに合わせて最適化された評価を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4496e-167">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="4496e-168">独自のコントロールとアクションを使用してテンプレートを作成することによって、カスタム評価を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4496e-168">You can also build a custom assessment by creating a template with your own controls and actions.</span></span> <span data-ttu-id="4496e-169">たとえば、テンプレートでは、内部のビジネスプロセスコントロール、または、150以上の事前に作成されている評価テンプレートのいずれにも対応していない地域データ保護の標準を対象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4496e-169">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our 150+ pre-built assessment templates.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4496e-170">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4496e-170">Learn more</span></span>

<span data-ttu-id="4496e-171">[コンプライアンスマネージャーによって提供される評価テンプレートの一覧を表示](compliance-manager-templates-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-171">[View the list of assessment templates provided by Compliance Manager](compliance-manager-templates-list.md).</span></span>

<span data-ttu-id="4496e-172">[評価のためのテンプレートを作成および変更するための詳細な手順を取得](compliance-manager-templates.md)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-172">[Get detailed instructions for creating and modifying templates for assessments](compliance-manager-templates.md).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="4496e-173">向上アクション</span><span class="sxs-lookup"><span data-stu-id="4496e-173">Improvement actions</span></span>

<span data-ttu-id="4496e-174">改善アクションは、コンプライアンスアクティビティを集中管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4496e-174">Improvement actions help centralize your compliance activities.</span></span> <span data-ttu-id="4496e-175">各改善アクションには、データ保護の規則と標準に沿った統合を支援するための推奨ガイダンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4496e-175">Each improvement action provides recommended guidance that’s intended to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="4496e-176">改善アクションを組織内のユーザーに割り当てて、実装とテストの作業を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4496e-176">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="4496e-177">また、ドキュメント、メモ、およびレコードの状態の更新を、改善アクションの中に保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="4496e-177">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="4496e-178">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4496e-178">Learn more</span></span>

<span data-ttu-id="4496e-179">[改善アクションを使用して、コンプライアンスワークフローを管理](compliance-manager-improvement-actions.md)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-179">[Use improvement actions to manage your compliance workflow](compliance-manager-improvement-actions.md).</span></span>

<span data-ttu-id="4496e-180">[アクションがコンプライアンススコアに及ぼす影響について説明](compliance-score-calculation.md#action-types-and-points)します。</span><span class="sxs-lookup"><span data-stu-id="4496e-180">[Learn how actions impact your compliance score](compliance-score-calculation.md#action-types-and-points).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="4496e-181">サポートされている言語</span><span class="sxs-lookup"><span data-stu-id="4496e-181">Supported languages</span></span>

<span data-ttu-id="4496e-182">コンプライアンスマネージャーは、次の言語で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4496e-182">Compliance Manager is available in the following languages:</span></span>

- <span data-ttu-id="4496e-183">英語</span><span class="sxs-lookup"><span data-stu-id="4496e-183">English</span></span>
- <span data-ttu-id="4496e-184">Bahasa インドネシア</span><span class="sxs-lookup"><span data-stu-id="4496e-184">Bahasa Indonesian</span></span>
- <span data-ttu-id="4496e-185">Bahasa マレー語</span><span class="sxs-lookup"><span data-stu-id="4496e-185">Bahasa Malay</span></span>
- <span data-ttu-id="4496e-186">簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="4496e-186">Chinese (Simplified)</span></span>
- <span data-ttu-id="4496e-187">繁体字中国語</span><span class="sxs-lookup"><span data-stu-id="4496e-187">Chinese (Traditional)</span></span>
- <span data-ttu-id="4496e-188">チェコ語</span><span class="sxs-lookup"><span data-stu-id="4496e-188">Czech</span></span>
- <span data-ttu-id="4496e-189">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="4496e-189">Danish</span></span>
- <span data-ttu-id="4496e-190">オランダ語</span><span class="sxs-lookup"><span data-stu-id="4496e-190">Dutch</span></span>
- <span data-ttu-id="4496e-191">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="4496e-191">Finnish</span></span>
- <span data-ttu-id="4496e-192">フランス語</span><span class="sxs-lookup"><span data-stu-id="4496e-192">French</span></span>
- <span data-ttu-id="4496e-193">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="4496e-193">German</span></span>
- <span data-ttu-id="4496e-194">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="4496e-194">Hebrew</span></span>
- <span data-ttu-id="4496e-195">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="4496e-195">Hungarian</span></span>
- <span data-ttu-id="4496e-196">イタリア語</span><span class="sxs-lookup"><span data-stu-id="4496e-196">Italian</span></span>
- <span data-ttu-id="4496e-197">日本語</span><span class="sxs-lookup"><span data-stu-id="4496e-197">Japanese</span></span>
- <span data-ttu-id="4496e-198">韓国語</span><span class="sxs-lookup"><span data-stu-id="4496e-198">Korean</span></span>
- <span data-ttu-id="4496e-199">ノルウェー語</span><span class="sxs-lookup"><span data-stu-id="4496e-199">Norwegian</span></span>
- <span data-ttu-id="4496e-200">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="4496e-200">Polish</span></span>
- <span data-ttu-id="4496e-201">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="4496e-201">Portuguese (Brazilian)</span></span>
- <span data-ttu-id="4496e-202">ロシア語</span><span class="sxs-lookup"><span data-stu-id="4496e-202">Russian</span></span>
- <span data-ttu-id="4496e-203">スペイン語</span><span class="sxs-lookup"><span data-stu-id="4496e-203">Spanish</span></span>
- <span data-ttu-id="4496e-204">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="4496e-204">Swedish</span></span>
- <span data-ttu-id="4496e-205">タイ語</span><span class="sxs-lookup"><span data-stu-id="4496e-205">Thai</span></span>
- <span data-ttu-id="4496e-206">トルコ語</span><span class="sxs-lookup"><span data-stu-id="4496e-206">Turkish</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="4496e-207">次の手順: セットアップとカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4496e-207">Next steps: set up and customize</span></span>

<span data-ttu-id="4496e-208">[コンプライアンスマネージャーを使用](compliance-manager-setup.md)して作業を開始するときに、サインイン、アクセス許可と役割の割り当て、設定の構成、およびダッシュボード表示の個人用設定を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4496e-208">Learn how to sign in, assign permissions and roles, configure settings, and personalize your dashboard view at [Get started with Compliance Manager](compliance-manager-setup.md).</span></span>

<span data-ttu-id="4496e-209">次に、 [評価を設定](compliance-manager-assessments.md)することで、組織にとって最も重要な業界標準に準拠するためのコンプライアンスマネージャーのカスタマイズを開始します。</span><span class="sxs-lookup"><span data-stu-id="4496e-209">Then start customizing Compliance Manager to help you comply with industry standards that matter most to your organization by [setting up assessments](compliance-manager-assessments.md).</span></span>