---
title: Microsoft コンプライアンススコア (プレビュー)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンススコア (プレビュー) を使用すると、組織はリスク評価を簡略化および自動化し、リスクに対処するための推奨される処置を提案します。
ms.openlocfilehash: 0cb8bd0b5aa39be2a9a6e706afa21bb7dc53eadb
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016140"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="4ad21-103">Microsoft コンプライアンススコア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4ad21-103">Microsoft Compliance Score (preview)</span></span>

<span data-ttu-id="4ad21-104">**この記事の内容**コンプライアンススコアの概要、コンプライアンスを管理する方法、および組織に合わせて設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-104">**In this article:** Learn what Compliance Score is, how it helps simplify the way you manage compliance, and how to set it up for your organization.</span></span>

<span data-ttu-id="4ad21-105">**新機能:** 2020年6月リリースには、評価を作成および管理するための新しい機能と、コンプライアンススコアの下のコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-105">**What's new:** The June 2020 release includes new functionality to create and manage assessments, and to view controls within Compliance Score.</span></span> <span data-ttu-id="4ad21-106">コンプライアンススコアの公開プレビューで新機能を確認するには、[コンプライアンススコアのリリースノート](compliance-score-release-notes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ad21-106">Visit the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new in the public preview of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="4ad21-107">コンプライアンススコアとは</span><span class="sxs-lookup"><span data-stu-id="4ad21-107">What is Compliance Score</span></span>

<span data-ttu-id="4ad21-108">[Microsoft コンプライアンススコア](https://compliance.microsoft.com/compliancescore)は、 [microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)のプレビュー機能で、組織の法令遵守状況を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-108">[Microsoft Compliance Score](https://compliance.microsoft.com/compliancescore) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture.</span></span> <span data-ttu-id="4ad21-109">データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-109">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="4ad21-110">コンプライアンススコアをツールとして使用して、すべてのリスク評価を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-110">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="4ad21-111">これにより、一般的なツールを使用してリスク評価を効率的に完了できるようにするためのワークフロー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-111">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="4ad21-112">コンプライアンス[マネージャー](compliance-manager-overview.md)ユーザーには、コンプライアンスのスコアが、より簡単でわかりやすい設計になったスタンドアロンの機能であることがわかります。これにより、組織はコンプライアンスをより簡単に管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ad21-112">[Compliance Manager](compliance-manager-overview.md) users will notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help organizations more easily manage compliance.</span></span>

<span data-ttu-id="4ad21-113">メインのコンプライアンススコアページはカスタムダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="4ad21-113">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="4ad21-114">現在のスコアが表示され、注意が必要な点を確認したり、スコアを向上させるためのアクションを案内したりできます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-114">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="4ad21-115">コンプライアンススコアのダッシュボードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4ad21-115">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="4ad21-116">![コンプライアンススコア-ダッシュボード](../media/compliance-score-dashboard.png "コンプライアンススコアダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="4ad21-116">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="4ad21-117">容易なコンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="4ad21-117">Simplified compliance management</span></span>

<span data-ttu-id="4ad21-118">コンプライアンススコアは、以下を提供することによりコンプライアンス管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-118">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="4ad21-119">**継続的な評価**: Microsoft 365 環境を自動的にスキャンして、システム内のデータ保護コントロールの有効性を検出および監視します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-119">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="4ad21-120">**推奨されるアクション**: コントロールを実装してスコアを最大化する方法について、推奨事項と詳しいガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-120">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="4ad21-121">**組み込みのコントロールマッピング**: 組み込みのコモンコントロールフレームワークを提供することにより、進化し続けるコンプライアンスの状況を最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-121">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ad21-122">コンプライアンス スコアおよびコンプライアンス マネージャーからの推奨事項は、コンプライアンスの保証として解釈してはいけません。</span><span class="sxs-lookup"><span data-stu-id="4ad21-122">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="4ad21-123">お客様は、お客様の規制環境に応じて、カスタマーコントロールの有効性を評価および検証することができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-123">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="4ad21-124">これらのサービスは現在プレビュー段階であり、[オンラインサービス](https://go.microsoft.com/fwlink/?linkid=2108910)の使用条件に従っています。</span><span class="sxs-lookup"><span data-stu-id="4ad21-124">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="4ad21-125">[セキュリティとコンプライアンスのための Microsoft 365 ライセンスガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ad21-125">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="4ad21-126">コンプライアンスマネージャーとの関係</span><span class="sxs-lookup"><span data-stu-id="4ad21-126">Relationship to Compliance Manager</span></span>

<span data-ttu-id="4ad21-127">コンプライアンスマネージャーの簡単な操作性として、コンプライアンススコアを考えます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-127">Think of Compliance Score as a simplified experience of Compliance Manager.</span></span> <span data-ttu-id="4ad21-128">2つの機能は、個別の統合されたツールとして存在しますが、コンプライアンススコアを使用すると、全体的なコンプライアンスの状況を簡単に監視し、改善するための手順を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-128">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="4ad21-129">コンプライアンススコアは、コンプライアンスマネージャーと同じバックエンドを共有します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-129">Compliance Score shares the same backend with Compliance Manager.</span></span> <span data-ttu-id="4ad21-130">1つのツールで行う操作は、他のツールにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-130">Anything that you do in one tool will surface in the other tool.</span></span>

<span data-ttu-id="4ad21-131">評価およびテンプレート管理の一部の機能は、パブリックプレビュー中にコンプライアンスマネージャーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-131">Some functionality for assessment and template management remains in Compliance Manager during public preview.</span></span> <span data-ttu-id="4ad21-132">コンプライアンススコアでコンプライアンス管理アクティビティをすべて開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4ad21-132">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="4ad21-133">コンプライアンスマネージャーによって処理された機能に進入した場合は、その機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-133">When you come to functions handled by Compliance Manager, we’ll guide you there.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="4ad21-134">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4ad21-134">Learn more</span></span>

<span data-ttu-id="4ad21-135">[コンプライアンススコアとコンプライアンスマネージャーの関係を理解](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-135">[Understand the relationship between Compliance Score and Compliance Manager](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="4ad21-136">スコアを理解する</span><span class="sxs-lookup"><span data-stu-id="4ad21-136">Understanding your score</span></span>

<span data-ttu-id="4ad21-137">コンプライアンススコア賞は、規制、標準、またはポリシーに準拠するために実行されたアクションを完了するためのものです。</span><span class="sxs-lookup"><span data-stu-id="4ad21-137">Compliance Score awards you points for completing actions taken to comply with a regulation, standard, or policy.</span></span> <span data-ttu-id="4ad21-138">各アクションは、発生する可能性のあるリスクに応じて、スコアにさまざまな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-138">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="4ad21-139">スコアは、全体的なコンプライアンス姿勢を改善するために、どのアクションに焦点を当てるかを優先することができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-139">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="4ad21-140">コンプライアンススコアには、Microsoft 365 データ保護基準に基づく初期スコアが与えられます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-140">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span>  <span data-ttu-id="4ad21-141">このベースラインは、データ保護と一般的なデータガバナンスに関する主要な規制と標準を含む一連のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="4ad21-141">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="4ad21-142">この基準は、主に NIST CSF (米国国立標準およびテクノロジ Cybersecurity フレームワーク) および ISO (国際標準化機構)、および、FedRAMP (連邦リスクおよび承認管理プログラム) および GDPR (欧州連合の一般的なデータ保護規則) からの要素を描画します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-142">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="4ad21-143">その他の評価を構成する前に、データ保護のベースライン評価を使用して最初のスコアを計算します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-143">The data protection baseline assessment is used to calculate your initial score before you configure any other assessments.</span></span> <span data-ttu-id="4ad21-144">最初の訪問時に、コンプライアンススコアは既に Microsoft 365 ソリューションからの信号を収集しています。</span><span class="sxs-lookup"><span data-stu-id="4ad21-144">Upon your first visit, Compliance Score is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="4ad21-145">重要なデータ保護の標準および規制について、組織がどのように実行されているかがひとめでわかり、推奨される改善アクションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-145">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="4ad21-146">すべての組織に固有のニーズがあるため、コンプライアンススコアは、自分の評価を設定し管理することによって、リスクをより良く軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-146">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to better mitigate risks.</span></span> <span data-ttu-id="4ad21-147">たとえば、組織が金融サービス業界に属している場合は、FFIEC 評価を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-147">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="4ad21-148">組織が医療機関に属している場合は、HIPAA/ヒット査定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-148">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="4ad21-149">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4ad21-149">Learn more</span></span>

<span data-ttu-id="4ad21-150">[コンプライアンススコアが計算され継続的に監視される方法について理解し](compliance-score-methodology.md)ます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-150">[Understand how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>

<span data-ttu-id="4ad21-151">[コンプライアンススコアの評価を作成し、管理](compliance-score-assessments.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-151">[Create and manage assessments in Compliance Score](compliance-score-assessments.md).</span></span>

## <a name="key-components-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="4ad21-152">主要なコンポーネント: コントロール、評価、テンプレート、改善アクション</span><span class="sxs-lookup"><span data-stu-id="4ad21-152">Key components: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="4ad21-153">コンプライアンススコアは、コンプライアンスアクティビティの管理に役立ついくつかのコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-153">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="4ad21-154">コンプライアンススコアを使用してコンプライアンスアクティビティの割り当て、テスト、および監視を行う際には、主要なコンポーネントであるコントロール、評価、テンプレート、改善アクションについて、基本的な理解を深めることができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-154">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key components: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="4ad21-155">コントロール</span><span class="sxs-lookup"><span data-stu-id="4ad21-155">Controls</span></span>

<span data-ttu-id="4ad21-156">コントロールは、規制、標準、またはポリシーの要件です。</span><span class="sxs-lookup"><span data-stu-id="4ad21-156">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="4ad21-157">システム構成、組織プロセス、および規制、標準、またはポリシーの特定の要件を満たす責任者を評価および管理する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-157">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="4ad21-158">コンプライアンススコアは、次の2種類のコントロールを追跡します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-158">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="4ad21-159">**Microsoft managed controls**: microsoft クラウドサービスのコントロール (microsoft が実装する責任者)</span><span class="sxs-lookup"><span data-stu-id="4ad21-159">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="4ad21-160">ユーザーコントロールと呼ばれることもあり**ます。これ**は、組織によって実装および管理されるコントロールです。</span><span class="sxs-lookup"><span data-stu-id="4ad21-160">**Your controls**: sometimes referred to as customer controls, these are controls implemented and managed by your organization</span></span>

#### <a name="learn-more"></a><span data-ttu-id="4ad21-161">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4ad21-161">Learn more</span></span>

<span data-ttu-id="4ad21-162">[コントロールの進行状況を監視](compliance-score-assessments.md#monitor-assessment-progress-and-controls)します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-162">[Monitor progress of your controls](compliance-score-assessments.md#monitor-assessment-progress-and-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="4ad21-163">講習</span><span class="sxs-lookup"><span data-stu-id="4ad21-163">Assessments</span></span>

<span data-ttu-id="4ad21-164">評価は、特定の規制、標準、またはポリシーによって制御をグループ化したものです。</span><span class="sxs-lookup"><span data-stu-id="4ad21-164">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="4ad21-165">評価でのアクションの完了は、標準、規制、または法律の要件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-165">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="4ad21-166">たとえば、すべてのアクションを完了したときに、ISO 27001 の要件に合わせて Microsoft 365 の設定をオンラインにするという評価がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ad21-166">For example, you may have an assessment that, when you complete all actions within it, brings your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="4ad21-167">評価にはいくつかのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="4ad21-167">Assessments have several components:</span></span>

- <span data-ttu-id="4ad21-168">**スコープ内サービス**: 評価に適用可能な Microsoft サービスの特定のセット</span><span class="sxs-lookup"><span data-stu-id="4ad21-168">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="4ad21-169">**Microsoft マネージコントロール**: microsoft が実装およびテストするコントロール</span><span class="sxs-lookup"><span data-stu-id="4ad21-169">**Microsoft managed controls**: controls that Microsoft implements and tests</span></span>
- <span data-ttu-id="4ad21-170">**コントロール**: 管理するコントロール</span><span class="sxs-lookup"><span data-stu-id="4ad21-170">**Your controls**: controls that you manage</span></span>
- <span data-ttu-id="4ad21-171">**評価スコア**: その評価内で改善アクションを完了して得られたポイントのパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="4ad21-171">**Assessment score**: the percentage of the points achieved by completing improvement actions within that assessment</span></span>

<span data-ttu-id="4ad21-172">評価を作成する場合は、それらを**グループ**に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-172">When creating assessments, you'll assign them to a **group**.</span></span> <span data-ttu-id="4ad21-173">組織にとって最も論理的な方法でグループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-173">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="4ad21-174">たとえば、年、コンプライアンス標準、サービス、組織内のチーム、またはその他の方法で評価をグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-174">For example, you may group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span> <span data-ttu-id="4ad21-175">グループを作成すると、[コンプライアンススコアダッシュボードをフィルター処理](compliance-score-setup.md#filtering-your-dashboard-view)して、1つ以上のグループでスコアを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-175">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="4ad21-176">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4ad21-176">Learn more</span></span>

<span data-ttu-id="4ad21-177">[コンプライアンススコアの評価を作成し、管理](compliance-score-assessments.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-177">[Create and manage assessments in Compliance Score](compliance-score-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="4ad21-178">テンプレート</span><span class="sxs-lookup"><span data-stu-id="4ad21-178">Templates</span></span>

<span data-ttu-id="4ad21-179">コンプライアンススコアには、評価をすばやく作成するための準備が整ったテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4ad21-179">Compliance Score provides templates that are ready for you to quickly create assessments.</span></span> <span data-ttu-id="4ad21-180">これらのテンプレートを変更して、ニーズに合わせて最適化された評価を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-180">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="4ad21-181">独自のコントロールとアクションを使用して独自のテンプレートを開発することにより、カスタム評価を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-181">You can also create a Custom Assessment by developing your own template with your own controls and actions.</span></span> <span data-ttu-id="4ad21-182">たとえば、テンプレートに内部ビジネスプロセスコントロール、またはテンプレートの1つには含まれていない地域データ保護の標準を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-182">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our templates.</span></span>

<span data-ttu-id="4ad21-183">独自のテンプレートを作成することで、Microsoft クラウドの評価だけでなく、組織のスコープ内でのその他のリスク評価も追跡できます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-183">Creating your own templates lets you track not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="4ad21-184">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4ad21-184">Learn more</span></span>

<span data-ttu-id="4ad21-185">[評価を作成するためにコンプライアンススコアで利用可能なテンプレートを表示](compliance-score-templates.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-185">[View the templates available in Compliance Score for building assessments](compliance-score-templates.md).</span></span>

<span data-ttu-id="4ad21-186">[テンプレートコンプライアンスマネージャーを作成および変更するための詳細な手順を](working-with-compliance-manager.md#templates)説明します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-186">[Get detailed instructions for creating and modifying templates Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="4ad21-187">向上アクション</span><span class="sxs-lookup"><span data-stu-id="4ad21-187">Improvement actions</span></span>

<span data-ttu-id="4ad21-188">改善アクションにより、コンプライアンスアクティビティを集中管理できます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-188">Improvement actions centralize your compliance activities.</span></span> <span data-ttu-id="4ad21-189">各改善アクションには、データ保護の規則および標準に沿った統合に役立つ詳細な実装ガイダンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4ad21-189">Each improvement action gives detailed implementation guidance to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="4ad21-190">実装とテストの作業を実行するために、組織内のユーザーにアクションを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-190">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="4ad21-191">また、ドキュメント、メモ、およびレコードの状態の更新を、改善アクションの中に保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ad21-191">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="4ad21-192">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4ad21-192">Learn more</span></span>

<span data-ttu-id="4ad21-193">[改善アクションを使用して、コンプライアンスワークフローを管理](compliance-score-improvement-actions.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-193">[Use improvement actions to manage your compliance workflow](compliance-score-improvement-actions.md).</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="4ad21-194">次の手順: セットアップとカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4ad21-194">Next steps: set up and customize</span></span>

<span data-ttu-id="4ad21-195">[コンプライアンススコア](compliance-score-setup.md)の設定で、サインイン、アクセス許可と役割の設定、セキュリティで保護されたスコア更新の構成、およびダッシュボード表示の個人用設定を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-195">Learn how to sign in, set permissions and roles, configure Secure Score updates, and personalize your dashboard view at [Compliance Score setup](compliance-score-setup.md).</span></span>

<span data-ttu-id="4ad21-196">[評価を設定](compliance-score-assessments.md)して、組織のコンプライアンススコアのカスタマイズを開始します。</span><span class="sxs-lookup"><span data-stu-id="4ad21-196">Then start customizing Compliance Score for your organization by [setting up assessments](compliance-score-assessments.md).</span></span>