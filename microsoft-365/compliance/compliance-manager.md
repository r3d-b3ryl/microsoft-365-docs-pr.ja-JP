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
ms.openlocfilehash: d26d187277b021e278667b6e0ae19a0772b34f03
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368130"
---
# <a name="microsoft-compliance-manager"></a><span data-ttu-id="937e7-103">Microsoft コンプライアンスマネージャー</span><span class="sxs-lookup"><span data-stu-id="937e7-103">Microsoft Compliance Manager</span></span>

<span data-ttu-id="937e7-104">**この記事の内容** コンプライアンスマネージャーとは何か、コンプライアンスを簡素化してリスクを軽減する方法、および主要なコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="937e7-104">**In this article:** Learn what Compliance Manager is, how it helps simplify compliance and reduce risk, and its key components.</span></span>

## <a name="whats-new-the-ga-release-of-compliance-manager"></a><span data-ttu-id="937e7-105">新機能: コンプライアンスマネージャーの GA リリース</span><span class="sxs-lookup"><span data-stu-id="937e7-105">What's new: the GA release of Compliance Manager</span></span>

<span data-ttu-id="937e7-106">コンプライアンスマネージャーは、一般公開 (GA) として、 [Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)内のエンドツーエンドのコンプライアンス管理ソリューションとして提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="937e7-106">Compliance Manager is now generally available (GA) as an end-to-end compliance management solution inside the [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span> <span data-ttu-id="937e7-107">このリリースでは、コンプライアンスマネージャーは、Microsoft Service Trust Portal の以前の場所から移行を完了します。</span><span class="sxs-lookup"><span data-stu-id="937e7-107">With this release, Compliance Manager completes the transition from its previous location in the Microsoft Service Trust Portal.</span></span>

<span data-ttu-id="937e7-108">コンプライアンススコアのパブリックプレビューとして開始されたものは、コンプライアンス管理機能が強化され、使いやすさが向上した一元的なツールに発展しました。</span><span class="sxs-lookup"><span data-stu-id="937e7-108">What began as the public preview of Compliance Score has evolved into a centralized tool with enhanced compliance management capabilities and greater ease of use.</span></span>  <span data-ttu-id="937e7-109">GA リリースは、コンプライアンスアクティビティを拡張するのに役立つ、事前に作成された評価のコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="937e7-109">The GA release brings a larger collection of pre-built assessments to help you scale your compliance activities.</span></span>

<span data-ttu-id="937e7-110">**GA リリースの詳細については、以下を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="937e7-110">**Learn more about the GA release:**</span></span>
- <span data-ttu-id="937e7-111">[よく寄せられる質問](compliance-manager-faq.md)では、展開について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="937e7-111">Our [frequently asked questions](compliance-manager-faq.md) walk you through the evolution in greater detail.</span></span>
- <span data-ttu-id="937e7-112">[このブログ投稿](https://aka.ms/compliancemanager/GAblog)の GA 機能の拡張についてお読みください。</span><span class="sxs-lookup"><span data-stu-id="937e7-112">Read about GA feature enhancements in [this blog post](https://aka.ms/compliancemanager/GAblog).</span></span>

<span data-ttu-id="937e7-113">コンプライアンスマネージャーが組織によるコンプライアンスの管理を簡単にする方法については、以下のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="937e7-113">Watch the video below to learn how Compliance Manager can help simplify how your organization manages compliance:</span></span>
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a><span data-ttu-id="937e7-114">コンプライアンスマネージャーとは</span><span class="sxs-lookup"><span data-stu-id="937e7-114">What is Compliance Manager</span></span>

<span data-ttu-id="937e7-115">[Microsoft コンプライアンスマネージャー](https://compliance.microsoft.com/compliancemanager) は、 [microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md) の機能です。これにより、組織のコンプライアンス要件をより簡単かつ便利に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="937e7-115">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that helps you manage your organization’s compliance requirements with greater ease and convenience.</span></span> <span data-ttu-id="937e7-116">コンプライアンスマネージャーは、データ保護のリスクのインベントリを取って、統制の実装の複雑さを管理し、現在の規制と証明書を維持し、監査担当者に報告することから、コンプライアンスへの移行を通じてお客様を支援します。</span><span class="sxs-lookup"><span data-stu-id="937e7-116">Compliance Manager can help you throughout your compliance journey, from taking inventory of your data protection risks to managing the complexities of implementing controls, staying current with regulations and certifications, and reporting to auditors.</span></span>

<span data-ttu-id="937e7-117">コンプライアンスマネージャーは、コンプライアンスを簡素化し、以下を提供することによりリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="937e7-117">Compliance Manager helps simplify compliance and reduce risk by providing:</span></span>

- <span data-ttu-id="937e7-118">一般的な業界および地域の標準および規制の事前に作成された評価、または独自のコンプライアンスニーズに応じたカスタム評価 (利用可能な評価はライセンス契約によって異なります。 [詳細をご覧](https://go.microsoft.com/fwlink/?linkid=2132371)ください)。</span><span class="sxs-lookup"><span data-stu-id="937e7-118">Pre-built assessments for common industry and regional standards and regulations, or custom assessments to meet your unique compliance needs (available assessments depend on your licensing agreement; [learn more](https://go.microsoft.com/fwlink/?linkid=2132371)).</span></span>

- <span data-ttu-id="937e7-119">単一のツールを使用してリスク評価を効率的に完了するためのワークフロー機能。</span><span class="sxs-lookup"><span data-stu-id="937e7-119">Workflow capabilities to help you efficiently complete your risk assessments through a single tool.</span></span>

- <span data-ttu-id="937e7-120">お客様の組織にとって最も関連性のある基準と規制に準拠するために役立つ、推奨される改善アクションの詳細なステップごとのガイダンス。</span><span class="sxs-lookup"><span data-stu-id="937e7-120">Detailed step-by-step guidance on suggested improvement actions to help you comply with the standards and regulations that are most relevant for your organization.</span></span> <span data-ttu-id="937e7-121">Microsoft によって管理されるアクションについては、「実装の詳細と監査結果」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="937e7-121">For actions that are managed by Microsoft, you’ll see implementation details and audit results.</span></span>

- <span data-ttu-id="937e7-122">リスクベースのコンプライアンススコア。これにより、改善アクションの完了の進捗状況を測定することによって、コンプライアンスの姿勢を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="937e7-122">A risk-based compliance score to help you understand your compliance posture by measuring your progress in completing improvement actions.</span></span>

<span data-ttu-id="937e7-123">コンプライアンスマネージャーのダッシュボードには、現在のコンプライアンススコアが表示され、注意が必要な事項が表示されます。また、重要な改善アクションを案内します。</span><span class="sxs-lookup"><span data-stu-id="937e7-123">Your Compliance Manager dashboard shows your current compliance score, helps you see what needs attention, and guides you to key improvement actions.</span></span> <span data-ttu-id="937e7-124">コンプライアンスマネージャーのダッシュボードがどのように表示されるかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="937e7-124">Below is an example of what your Compliance Manager dashboard will look like:</span></span>

<span data-ttu-id="937e7-125">![コンプライアンスマネージャー-ダッシュボード](../media/compliance-manager-dashboard.png "コンプライアンスマネージャーダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="937e7-125">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

## <a name="understanding-your-compliance-score"></a><span data-ttu-id="937e7-126">コンプライアンススコアを理解する</span><span class="sxs-lookup"><span data-stu-id="937e7-126">Understanding your compliance score</span></span>

<span data-ttu-id="937e7-127">コンプライアンスマネージャー賞は、規制、標準、またはポリシーに準拠するために行われた改善アクションを完了するためのもので、それらのポイントを総合的なコンプライアンススコアに結合します。</span><span class="sxs-lookup"><span data-stu-id="937e7-127">Compliance Manager awards you points for completing improvement actions taken to comply with a regulation, standard, or policy, and combines those points into an overall compliance score.</span></span> <span data-ttu-id="937e7-128">各アクションは、発生する可能性のあるリスクに応じて、スコアにさまざまな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="937e7-128">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="937e7-129">コンプライアンススコアは、全体的なコンプライアンスの姿勢を改善するために、どのアクションに焦点を当てるかを優先することができます。</span><span class="sxs-lookup"><span data-stu-id="937e7-129">Your compliance score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="937e7-130">コンプライアンスマネージャーには、Microsoft 365 データ保護基準に基づく初期スコアが与えられます。</span><span class="sxs-lookup"><span data-stu-id="937e7-130">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="937e7-131">このベースラインは、データ保護と一般的なデータガバナンスに関する主要な規制と標準を含む一連のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="937e7-131">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="937e7-132">詳細情報</span><span class="sxs-lookup"><span data-stu-id="937e7-132">Learn more</span></span>

<span data-ttu-id="937e7-133">[コンプライアンススコアの計算方法について理解](compliance-score-calculation.md)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-133">[Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

<span data-ttu-id="937e7-134">[改善アクションを操作する方法について説明](compliance-manager-improvement-actions.md)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-134">[Learn how to work with improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="937e7-135">主な要素: コントロール、評価、テンプレート、改善アクション</span><span class="sxs-lookup"><span data-stu-id="937e7-135">Key elements: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="937e7-136">コンプライアンスマネージャーは、コンプライアンスアクティビティを管理するために、いくつかのデータ要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="937e7-136">Compliance Manager uses several data elements to help you manage your compliance activities.</span></span> <span data-ttu-id="937e7-137">コンプライアンスマネージャーを使用してコンプライアンスアクティビティの割り当て、テスト、および監視を行う際には、主要な要素であるコントロール、評価、テンプレート、改善アクションについて、基本的な理解を深めることができます。</span><span class="sxs-lookup"><span data-stu-id="937e7-137">As you use Compliance Manager to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key elements: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="937e7-138">コントロール</span><span class="sxs-lookup"><span data-stu-id="937e7-138">Controls</span></span>

<span data-ttu-id="937e7-139">コントロールは、規制、標準、またはポリシーの要件です。</span><span class="sxs-lookup"><span data-stu-id="937e7-139">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="937e7-140">システム構成、組織プロセス、および規制、標準、またはポリシーの特定の要件を満たす責任者を評価および管理する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="937e7-140">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="937e7-141">コンプライアンスマネージャーは、次の種類のコントロールを追跡します。</span><span class="sxs-lookup"><span data-stu-id="937e7-141">Compliance Manager tracks the following types of controls:</span></span>

1. <span data-ttu-id="937e7-142">**Microsoft managed controls**: microsoft クラウドサービスのコントロール (microsoft が実装する責任者)</span><span class="sxs-lookup"><span data-stu-id="937e7-142">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="937e7-143">顧客管理コントロールと呼ばれることもあり**ます。これらのコントロールは**、組織によって実装および管理されます。</span><span class="sxs-lookup"><span data-stu-id="937e7-143">**Your controls**: sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
3. <span data-ttu-id="937e7-144">**共有コントロール**: これらのコントロールは、組織と Microsoft 共有の両方が責任を負うことになります。</span><span class="sxs-lookup"><span data-stu-id="937e7-144">**Shared controls**: these are controls that both your organization and Microsoft share responsibility for implementing</span></span>

##### <a name="learn-more"></a><span data-ttu-id="937e7-145">詳細情報</span><span class="sxs-lookup"><span data-stu-id="937e7-145">Learn more</span></span>

<span data-ttu-id="937e7-146">[コントロールの進行状況を監視](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-146">[Monitor progress of your controls](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).</span></span>

<span data-ttu-id="937e7-147">[コンプライアンスマネージャーが継続的に制御を評価する方法について説明](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-147">[Learn how Compliance Manager continuously assesses controls](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="937e7-148">講習</span><span class="sxs-lookup"><span data-stu-id="937e7-148">Assessments</span></span>

<span data-ttu-id="937e7-149">評価は、特定の規制、標準、またはポリシーによって制御をグループ化したものです。</span><span class="sxs-lookup"><span data-stu-id="937e7-149">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="937e7-150">評価でのアクションの完了は、標準、規制、または法律の要件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="937e7-150">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="937e7-151">たとえば、すべてのアクションを完了したときに、ISO 27001 の要件に合わせて Microsoft 365 の設定をオンラインにするための評価を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="937e7-151">For example, you may have an assessment that, when you complete all actions within it, helps to bring your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="937e7-152">評価にはいくつかのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="937e7-152">Assessments have several components:</span></span>

- <span data-ttu-id="937e7-153">**スコープ内サービス**: 評価に適用可能な Microsoft サービスの特定のセット</span><span class="sxs-lookup"><span data-stu-id="937e7-153">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="937e7-154">**Microsoft managed controls**: microsoft がお客様の代わりに実装する microsoft クラウドサービスのコントロール</span><span class="sxs-lookup"><span data-stu-id="937e7-154">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft implements on your behalf</span></span>
- <span data-ttu-id="937e7-155">顧客管理コントロールと呼ばれることもあり**ます。これらのコントロールは**、組織によって実装および管理されます。</span><span class="sxs-lookup"><span data-stu-id="937e7-155">**Your controls**: sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
- <span data-ttu-id="937e7-156">**共有コントロール**: これらのコントロールは、組織と Microsoft 共有の両方が責任を負うことになります。</span><span class="sxs-lookup"><span data-stu-id="937e7-156">**Shared controls**: these are controls that both your organization and Microsoft share responsibility for implementing</span></span>
- <span data-ttu-id="937e7-157">**評価スコア**: 組織で管理されている、Microsoft によって管理されている評価内のアクションからの総ポイントを実現するための進行状況を示します。</span><span class="sxs-lookup"><span data-stu-id="937e7-157">**Assessment score**: shows your progress in achieving total possible points from actions within the assessment that are managed by your organization and by Microsoft</span></span>

<span data-ttu-id="937e7-158">評価を作成する場合は、それらをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="937e7-158">When creating assessments, you’ll assign them to a group.</span></span> <span data-ttu-id="937e7-159">組織にとって最も論理的な方法でグループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="937e7-159">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="937e7-160">たとえば、監査年、地域、ソリューション、組織内のチーム、またはその他の方法で評価をグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="937e7-160">For example, you may group assessments by audit year, region, solution, teams within your organization, or some other way.</span></span> <span data-ttu-id="937e7-161">グループを作成すると、 [コンプライアンスマネージャーダッシュボードをフィルター処理](compliance-manager-setup.md#filtering-your-dashboard-view) して、1つまたは複数のグループでスコアを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="937e7-161">Once you create groups, you can [filter your Compliance Manager dashboard](compliance-manager-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="937e7-162">詳細情報</span><span class="sxs-lookup"><span data-stu-id="937e7-162">Learn more</span></span>

<span data-ttu-id="937e7-163">[コンプライアンスマネージャーで評価を作成および管理](compliance-manager-assessments.md)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-163">[Build and manage assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="937e7-164">テンプレート</span><span class="sxs-lookup"><span data-stu-id="937e7-164">Templates</span></span>

<span data-ttu-id="937e7-165">コンプライアンスマネージャーには、評価をすばやく作成するために役立つテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="937e7-165">Compliance Manager provides templates to help you quickly create assessments.</span></span> <span data-ttu-id="937e7-166">これらのテンプレートを変更して、ニーズに合わせて最適化された評価を作成できます。</span><span class="sxs-lookup"><span data-stu-id="937e7-166">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="937e7-167">独自のコントロールとアクションを使用してテンプレートを作成することによって、カスタム評価を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="937e7-167">You can also build a custom assessment by creating a template with your own controls and actions.</span></span> <span data-ttu-id="937e7-168">たとえば、テンプレートでは、内部のビジネスプロセスコントロール、または、150以上の事前に作成されている評価テンプレートのいずれにも対応していない地域データ保護の標準を対象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="937e7-168">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our 150+ pre-built assessment templates.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="937e7-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="937e7-169">Learn more</span></span>

<span data-ttu-id="937e7-170">[コンプライアンスマネージャーによって提供される評価テンプレートの一覧を表示](compliance-manager-templates-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-170">[View the list of assessment templates provided by Compliance Manager](compliance-manager-templates-list.md).</span></span>

<span data-ttu-id="937e7-171">[評価のためのテンプレートを作成および変更するための詳細な手順を取得](compliance-manager-templates.md)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-171">[Get detailed instructions for creating and modifying templates for assessments](compliance-manager-templates.md).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="937e7-172">向上アクション</span><span class="sxs-lookup"><span data-stu-id="937e7-172">Improvement actions</span></span>

<span data-ttu-id="937e7-173">改善アクションは、コンプライアンスアクティビティを集中管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="937e7-173">Improvement actions help centralize your compliance activities.</span></span> <span data-ttu-id="937e7-174">各改善アクションには、データ保護の規則と標準に沿った統合を支援するための推奨ガイダンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="937e7-174">Each improvement action provides recommended guidance that’s intended to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="937e7-175">改善アクションを組織内のユーザーに割り当てて、実装とテストの作業を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="937e7-175">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="937e7-176">また、ドキュメント、メモ、およびレコードの状態の更新を、改善アクションの中に保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="937e7-176">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="937e7-177">詳細情報</span><span class="sxs-lookup"><span data-stu-id="937e7-177">Learn more</span></span>

<span data-ttu-id="937e7-178">[改善アクションを使用して、コンプライアンスワークフローを管理](compliance-manager-improvement-actions.md)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-178">[Use improvement actions to manage your compliance workflow](compliance-manager-improvement-actions.md).</span></span>

<span data-ttu-id="937e7-179">[アクションがコンプライアンススコアに及ぼす影響について説明](compliance-score-calculation.md#action-types-and-points)します。</span><span class="sxs-lookup"><span data-stu-id="937e7-179">[Learn how actions impact your compliance score](compliance-score-calculation.md#action-types-and-points).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="937e7-180">サポートされている言語</span><span class="sxs-lookup"><span data-stu-id="937e7-180">Supported languages</span></span>

<span data-ttu-id="937e7-181">コンプライアンスマネージャーは、次の言語で使用できます。</span><span class="sxs-lookup"><span data-stu-id="937e7-181">Compliance Manger is available in the following languages:</span></span>

- <span data-ttu-id="937e7-182">英語</span><span class="sxs-lookup"><span data-stu-id="937e7-182">English</span></span>
- <span data-ttu-id="937e7-183">Bahasa インドネシア</span><span class="sxs-lookup"><span data-stu-id="937e7-183">Bahasa Indonesian</span></span>
- <span data-ttu-id="937e7-184">Bahasa マレー語</span><span class="sxs-lookup"><span data-stu-id="937e7-184">Bahasa Malay</span></span>
- <span data-ttu-id="937e7-185">簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="937e7-185">Chinese (Simplified)</span></span>
- <span data-ttu-id="937e7-186">繁体字中国語</span><span class="sxs-lookup"><span data-stu-id="937e7-186">Chinese (Traditional)</span></span>
- <span data-ttu-id="937e7-187">チェコ語</span><span class="sxs-lookup"><span data-stu-id="937e7-187">Czech</span></span>
- <span data-ttu-id="937e7-188">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="937e7-188">Danish</span></span>
- <span data-ttu-id="937e7-189">オランダ語</span><span class="sxs-lookup"><span data-stu-id="937e7-189">Dutch</span></span>
- <span data-ttu-id="937e7-190">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="937e7-190">Finnish</span></span>
- <span data-ttu-id="937e7-191">フランス語</span><span class="sxs-lookup"><span data-stu-id="937e7-191">French</span></span>
- <span data-ttu-id="937e7-192">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="937e7-192">German</span></span>
- <span data-ttu-id="937e7-193">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="937e7-193">Hebrew</span></span>
- <span data-ttu-id="937e7-194">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="937e7-194">Hungarian</span></span>
- <span data-ttu-id="937e7-195">イタリア語</span><span class="sxs-lookup"><span data-stu-id="937e7-195">Italian</span></span>
- <span data-ttu-id="937e7-196">日本語</span><span class="sxs-lookup"><span data-stu-id="937e7-196">Japanese</span></span>
- <span data-ttu-id="937e7-197">韓国語</span><span class="sxs-lookup"><span data-stu-id="937e7-197">Korean</span></span>
- <span data-ttu-id="937e7-198">ノルウェー語</span><span class="sxs-lookup"><span data-stu-id="937e7-198">Norwegian</span></span>
- <span data-ttu-id="937e7-199">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="937e7-199">Polish</span></span>
- <span data-ttu-id="937e7-200">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="937e7-200">Portuguese (Brazilian)</span></span>
- <span data-ttu-id="937e7-201">ロシア語</span><span class="sxs-lookup"><span data-stu-id="937e7-201">Russian</span></span>
- <span data-ttu-id="937e7-202">スペイン語</span><span class="sxs-lookup"><span data-stu-id="937e7-202">Spanish</span></span>
- <span data-ttu-id="937e7-203">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="937e7-203">Swedish</span></span>
- <span data-ttu-id="937e7-204">タイ語</span><span class="sxs-lookup"><span data-stu-id="937e7-204">Thai</span></span>
- <span data-ttu-id="937e7-205">トルコ語</span><span class="sxs-lookup"><span data-stu-id="937e7-205">Turkish</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="937e7-206">次の手順: セットアップとカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="937e7-206">Next steps: set up and customize</span></span>

<span data-ttu-id="937e7-207">[コンプライアンスマネージャーを使用](compliance-manager-setup.md)して作業を開始するときに、サインイン、アクセス許可と役割の割り当て、設定の構成、およびダッシュボード表示の個人用設定を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="937e7-207">Learn how to sign in, assign permissions and roles, configure settings, and personalize your dashboard view at [Get started with Compliance Manager](compliance-manager-setup.md).</span></span>

<span data-ttu-id="937e7-208">次に、 [評価を設定](compliance-manager-assessments.md)することで、組織にとって最も重要な業界標準に準拠するためのコンプライアンスマネージャーのカスタマイズを開始します。</span><span class="sxs-lookup"><span data-stu-id="937e7-208">Then start customizing Compliance Manager to help you comply with industry standards that matter most to your organization by [setting up assessments](compliance-manager-assessments.md).</span></span>