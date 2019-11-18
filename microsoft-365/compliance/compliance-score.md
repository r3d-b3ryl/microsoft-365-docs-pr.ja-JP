---
title: Microsoft コンプライアンススコア
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
description: Microsoft コンプライアンススコアを使用すると、組織はリスク評価を簡略化および自動化し、リスクに対処するための推奨される処置を提案します。
ms.openlocfilehash: f604f52fd66664aeb1b61fb873cfe40e8f48115c
ms.sourcegitcommit: 544b10cc3abe04a47438085d51c4250c9238f76f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "38686665"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="d1bc5-103">Microsoft コンプライアンススコア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d1bc5-103">Microsoft Compliance Score (Preview)</span></span>

<span data-ttu-id="d1bc5-104">Microsoft コンプライアンススコアは、コンプライアンスの管理方法を簡素化し、ユーザーフレンドリな環境でコンプライアンスリスクを軽減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-104">Microsoft Compliance Score helps to simplify the way you manage compliance and reduce compliance risks through a user-friendly experience.</span></span> <span data-ttu-id="d1bc5-105">コンプライアンススコアは、 [Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)のパブリックプレビューで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-105">Compliance Score is now available for public preview in the  [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span> <span data-ttu-id="d1bc5-106">この記事を読むと、コンプライアンススコアの概要、組織のコンプライアンスを管理する方法、および使用を開始する方法を理解できます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-106">Read this article to understand what Compliance Score is, how it can help you manage compliance for your organization, and how to get started.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="d1bc5-107">コンプライアンススコアとは</span><span class="sxs-lookup"><span data-stu-id="d1bc5-107">What is Compliance Score</span></span>

<span data-ttu-id="d1bc5-108">Microsoft コンプライアンススコアは、Microsoft 365 コンプライアンスセンターのプレビュー機能で、組織の法令遵守状況を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-108">Microsoft Compliance Score is a preview feature in the Microsoft 365 compliance center to help you understand your organization’s compliance posture.</span></span> <span data-ttu-id="d1bc5-109">データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-109">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="d1bc5-110">コンプライアンススコアをツールとして使用して、すべてのリスク評価を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-110">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="d1bc5-111">これにより、一般的なツールを使用してリスク評価を効率的に実行および完了できるようにするためのワークフロー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-111">It provides workflow capabilities to help you efficiently perform and complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="d1bc5-112">現在[コンプライアンスマネージャー](compliance-manager-overview.md)を使用している場合は、コンプライアンスをより簡単に管理できるようにするための、よりシンプルでわかりやすい設計のスタンドアロンの機能としてコンプライアンススコアが表示されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-112">If you currently use [Compliance Manager](compliance-manager-overview.md), you’ll notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help you manage compliance more easily.</span></span> 

<span data-ttu-id="d1bc5-113">メインのコンプライアンススコアページはカスタムダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-113">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="d1bc5-114">現在のスコアが表示され、注意が必要な点を確認したり、スコアを向上させるためのアクションを案内したりできます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-114">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="d1bc5-115">コンプライアンススコアダッシュボードは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-115">This is what your Compliance Score dashboard will look like:</span></span>

<span data-ttu-id="d1bc5-116">![コンプライアンススコア-ダッシュボード](media/compliance-score-dashboard.png "コンプライアンススコアダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="d1bc5-116">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="d1bc5-117">容易なコンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="d1bc5-117">Simplified compliance management</span></span>

<span data-ttu-id="d1bc5-118">コンプライアンススコアは、以下を提供することによりコンプライアンス管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-118">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="d1bc5-119">**継続的な評価**: Microsoft 365 環境を自動的にスキャンして、システム内のデータ保護コントロールの有効性を検出および監視します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-119">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="d1bc5-120">**推奨されるアクション**: コントロールを実装してスコアを最大化する方法について、推奨事項と詳しいガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-120">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="d1bc5-121">**組み込みのコントロールマッピング**: 組み込みのコモンコントロールフレームワークを提供することにより、進化し続けるコンプライアンスの状況を最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-121">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="d1bc5-122">コンプライアンススコアは、特定の標準または規制に対する組織のコンプライアンスの絶対的な測定基準を表しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-122">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="d1bc5-123">このことは、個人データや個人のプライバシーに対するリスクを軽減するために、制御を採用した範囲を表しています。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-123">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="d1bc5-124">コンプライアンススコアとコンプライアンスマネージャーからの推奨事項は、コンプライアンスの保証として解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-124">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="d1bc5-125">このサービスは現在プレビュー段階であり、[オンラインサービス](https://go.microsoft.com/fwlink/?linkid=2108910)の使用条件の条件に従います。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-125">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="d1bc5-126">コンプライアンスマネージャーとの関係</span><span class="sxs-lookup"><span data-stu-id="d1bc5-126">Relationship to Compliance Manager</span></span>

<span data-ttu-id="d1bc5-127">コンプライアンスマネージャーの簡易版として、コンプライアンススコアと考えてください。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-127">Think of Compliance Score as a simplified version of Compliance Manager.</span></span> <span data-ttu-id="d1bc5-128">2つの機能は、個別の統合されたツールとして存在しますが、コンプライアンススコアを使用すると、全体的なコンプライアンスの状況を簡単に監視し、改善するための手順を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-128">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="d1bc5-129">コンプライアンススコアは、コンプライアンスマネージャーと同じバックエンドを共有するので、コンプライアンスマネージャーに既に所有しているデータがコンプライアンススコアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-129">Compliance Score shares the same backend with Compliance Manager, so any data you may already have in Compliance Manager will show in Compliance Score.</span></span>

<span data-ttu-id="d1bc5-130">パブリックプレビュー中には、評価の管理やテンプレートの作成など、コンプライアンスマネージャーだけで一部の機能が維持されます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-130">During public preview, some functionality remains solely in Compliance Manager, such as managing assessments and creating templates.</span></span> <span data-ttu-id="d1bc5-131">コンプライアンススコアでコンプライアンス管理アクティビティをすべて開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-131">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="d1bc5-132">コンプライアンスマネージャーによって処理された機能に到着すると、そのツールにガイドされます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-132">When you come to functions handled by Compliance Manager, you will be guided to that tool.</span></span> <span data-ttu-id="d1bc5-133">そのため、このドキュメントの一部では、コンプライアンスマネージャーのトピックについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-133">For that reason, some of this documentation directs you to Compliance Manager topics.</span></span>

<span data-ttu-id="d1bc5-134">コンプライアンススコアとコンプライアンスマネージャーの関係の詳細については、「[コンプライアンススコアのリリースノート](compliance-score-release-notes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-134">Learn more about the relationship between Compliance Score and Compliance Manager in the [Compliance Score release notes](compliance-score-release-notes.md).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="d1bc5-135">スコアを理解する</span><span class="sxs-lookup"><span data-stu-id="d1bc5-135">Understanding your score</span></span>

<span data-ttu-id="d1bc5-136">コンプライアンススコアは、Microsoft 365 データ保護基準に基づいた標準スコアを提供します。これは、一般的な業界の規制と標準を含む一連のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-136">Compliance Score gives you an out-of-the-box score based on the Microsoft 365 data protection baseline, which is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="d1bc5-137">このスコアは、コンプライアンスを評価するための開始点として最適ですが、組織にとってより関連性の高い評価を追加すると、コンプライアンススコアはより強力になります。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-137">While this score is a good starting point for assessing your compliance posture, Compliance Score becomes more powerful for you once you add assessments that are more relevant to your organization.</span></span>

<span data-ttu-id="d1bc5-138">たとえば、組織が金融サービス業界に属している場合は、FFIEC 評価を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-138">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="d1bc5-139">組織が医療機関に属している場合は、HIPAA/ヒット査定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-139">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span> <span data-ttu-id="d1bc5-140">[コンプライアンスマネージャーで評価を追加](working-with-compliance-manager.md#assessments)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-140">Learn how to [add assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

<span data-ttu-id="d1bc5-141">[コンプライアンススコアが計算され継続的に監視される方法](compliance-score-methodology.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-141">Learn more about [how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>


## <a name="key-components-controls-assessments-templates-groups"></a><span data-ttu-id="d1bc5-142">主要なコンポーネント: コントロール、評価、テンプレート、グループ</span><span class="sxs-lookup"><span data-stu-id="d1bc5-142">Key components: controls, assessments, templates, groups</span></span>

<span data-ttu-id="d1bc5-143">コンプライアンススコアは、コンプライアンスアクティビティの管理に役立ついくつかのコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-143">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="d1bc5-144">コンプライアンススコアを使用してコンプライアンスアクティビティの割り当て、テスト、および監視を行うときは、これらの主要なコンポーネントについて基本的な理解を得ておくと役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-144">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of these key components.</span></span> <span data-ttu-id="d1bc5-145">この図は、それらの間の関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-145">This diagram shows the relationships among them:</span></span>

<span data-ttu-id="d1bc5-146">![コンプライアンスマネージャーバージョン3のリレーションシップ](media/compliance-manager-relationships.png "コンプライアンススコアコンポーネント")</span><span class="sxs-lookup"><span data-stu-id="d1bc5-146">![Relationships in Compliance Manager Version 3](media/compliance-manager-relationships.png "Compliance Score components")</span></span>

### <a name="controls"></a><span data-ttu-id="d1bc5-147">コントロール</span><span class="sxs-lookup"><span data-stu-id="d1bc5-147">Controls</span></span>

<span data-ttu-id="d1bc5-148">コントロールは、規制、標準、または内部ポリシーの特定の要件を満たすために、システム構成、組織プロセス、および人のアカウンタビリティを評価および管理する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-148">A control defines how you assess and manage system configuration, organizational process, and people accountability to meet a specific requirement of a regulation, standard, or internal policy.</span></span>

<span data-ttu-id="d1bc5-149">コンプライアンススコアは、次の2種類のコントロールを追跡します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-149">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="d1bc5-150">**Microsoft が管理するコントロール**: これらは microsoft クラウドサービスのためのコントロールであり、microsoft はこれらを実装しています。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-150">**Microsoft-managed controls**: these are controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="d1bc5-151">**お客様が管理するコントロール**: これらは、組織によって管理されるコントロールで、これを実装する責任があります。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-151">**Customer-managed controls**: these are controls managed by your organization, which you are responsible for implementing</span></span>
 
### <a name="assessments"></a><span data-ttu-id="d1bc5-152">講習</span><span class="sxs-lookup"><span data-stu-id="d1bc5-152">Assessments</span></span>

<span data-ttu-id="d1bc5-153">評価は、組織のスコアリングプロセスを開始するテンプレートの評価です。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-153">An assessment is an evaluation of a template that initiates the scoring process for your organization.</span></span> <span data-ttu-id="d1bc5-154">評価標準、規制、または法律の要件を満たすために必要な処置をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-154">Assessments group the actions necessary to meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="d1bc5-155">たとえば、すべてのアクションを完了したときに、ISO 27001 要件に合わせて Office 365 の設定をオンラインにするという評価がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-155">For example, you may have an assessment that, when you complete all actions within it, brings your Office 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="d1bc5-156">既定では、コンプライアンススコアは、Microsoft 365 データ保護基準に基づいた評価を組織に提供します。これには、データ保護とコンプライアンスのリスクを軽減するための推奨事項があります (詳細については、こちらを[参照](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)してください)。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-156">By default, Compliance Score provides your organization with an assessment based on the Microsoft 365 data protection baseline, a recommendation for reducing your data protection and compliance risks ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

<span data-ttu-id="d1bc5-157">評価には、いくつかのコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-157">Assessments include several components:</span></span>

- <span data-ttu-id="d1bc5-158">**スコープ内サービス**: 評価に適用可能な Microsoft サービスの特定のセット</span><span class="sxs-lookup"><span data-stu-id="d1bc5-158">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="d1bc5-159">**Microsoft managed controls**: microsoft が実装およびテストした制御</span><span class="sxs-lookup"><span data-stu-id="d1bc5-159">**Microsoft-managed controls**: controls that Microsoft implemented and tested</span></span>
- <span data-ttu-id="d1bc5-160">**顧客管理コントロール**: 管理するコントロール</span><span class="sxs-lookup"><span data-stu-id="d1bc5-160">**Customer-managed controls**: controls that you manage</span></span>
- <span data-ttu-id="d1bc5-161">**評価スコア**: その評価内でアクションを完了して得られたポイントのパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="d1bc5-161">**Assessment score**: the percentage of the points achieved by completing actions within that assessment</span></span>

> [!NOTE]
> <span data-ttu-id="d1bc5-162">コンプライアンススコアには、評価と、全体的なスコアにどのような影響があるかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-162">Compliance Score displays your assessments and how they factor into your overall score.</span></span> <span data-ttu-id="d1bc5-163">ただし、パブリックプレビュー中には、評価を管理するためにコンプライアンスマネージャーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-163">However, during public preview you will be directed to Compliance Manager to manage your assessments.</span></span>

<span data-ttu-id="d1bc5-164">[コンプライアンスマネージャーで評価を処理](working-with-compliance-manager.md#assessments)するための詳細な手順を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-164">View detailed instructions for [working with assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

### <a name="templates"></a><span data-ttu-id="d1bc5-165">テンプレート</span><span class="sxs-lookup"><span data-stu-id="d1bc5-165">Templates</span></span>

<span data-ttu-id="d1bc5-166">コンプライアンススコア評価用に事前に構成されたテンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-166">Compliance Score provides pre-configured templates for assessments.</span></span> <span data-ttu-id="d1bc5-167">コンプライアンススコアを使用すると、自分のニーズに合わせて独自の評価用にテンプレートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-167">Compliance Score also allows you to create templates for your own assessments to suit your needs.</span></span> <span data-ttu-id="d1bc5-168">たとえば、事前に構成されたテンプレートの1つでは網羅されていない地域データ保護またはコンプライアンス標準のテンプレートとして、ビジネスプロセスコントロール用のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-168">For example, you can create a template for your business process control, or a template for a regional data protection or compliance standard that isn’t covered by one of the pre-configured templates.</span></span>  <span data-ttu-id="d1bc5-169">独自のテンプレートを作成することにより、カスタム評価を作成して、コンプライアンススコアが Microsoft クラウド評価だけでなく、組織のスコープ内の他のリスク評価も追跡できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-169">By creating your own templates, you can create custom assessments to ensure that Compliance Score tracks not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

<span data-ttu-id="d1bc5-170">新しいテンプレートを作成するには、既存のテンプレートをコピーするか、Excel ファイルからコントロールの情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-170">You can create new templates by copying an existing template, or by importing controls information from an Excel file.</span></span> <span data-ttu-id="d1bc5-171">[コンプライアンスマネージャーでテンプレートを作成](working-with-compliance-manager.md#templates)するための詳細な手順を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-171">View detailed instructions for [creating templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

<span data-ttu-id="d1bc5-172">コンプライアンススコア用に事前に構成されたテンプレートは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-172">The pre-configured templates for Compliance Score are:</span></span>

1. [<span data-ttu-id="d1bc5-173">ISO 27001: 2013</span><span class="sxs-lookup"><span data-stu-id="d1bc5-173">ISO 27001: 2013</span></span>](https://go.microsoft.com/fwlink/?linkid=2109073)
2. [<span data-ttu-id="d1bc5-174">ISO 27018: 2014</span><span class="sxs-lookup"><span data-stu-id="d1bc5-174">ISO 27018: 2014</span></span>](https://go.microsoft.com/fwlink/?linkid=2109074)
3. [<span data-ttu-id="d1bc5-175">NIST 800-53 リビジョン4</span><span class="sxs-lookup"><span data-stu-id="d1bc5-175">NIST 800-53 Rev. 4</span></span>](https://go.microsoft.com/fwlink/?linkid=2109075)
4. [<span data-ttu-id="d1bc5-176">NIST 800-171</span><span class="sxs-lookup"><span data-stu-id="d1bc5-176">NIST 800-171</span></span>](https://go.microsoft.com/fwlink/?linkid=2108867)
5. [<span data-ttu-id="d1bc5-177">NIST Cybersecurity Framework (CSF)</span><span class="sxs-lookup"><span data-stu-id="d1bc5-177">NIST Cybersecurity Framework (CSF)</span></span>](https://go.microsoft.com/fwlink/?linkid=2108868)
6. [<span data-ttu-id="d1bc5-178">Cloud Security アライアンス (CSA) Cloud Controls Matrix (CCM) 3.0.1</span><span class="sxs-lookup"><span data-stu-id="d1bc5-178">Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1</span></span>](https://go.microsoft.com/fwlink/?linkid=2109076)
8. [<span data-ttu-id="d1bc5-179">連邦金融機関調査協議会 (FFIEC) Information Security ブックレット</span><span class="sxs-lookup"><span data-stu-id="d1bc5-179">Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet</span></span>](https://go.microsoft.com/fwlink/?linkid=2109077) 
8. <span data-ttu-id="d1bc5-180">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / の[ヒット](https://go.microsoft.com/fwlink/?linkid=2109079)</span><span class="sxs-lookup"><span data-stu-id="d1bc5-180">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span></span>
9. [<span data-ttu-id="d1bc5-181">FedRAMP モデレート</span><span class="sxs-lookup"><span data-stu-id="d1bc5-181">FedRAMP Moderate</span></span>](https://go.microsoft.com/fwlink/?linkid=2108869)
10. [<span data-ttu-id="d1bc5-182">欧州連合 GDPR</span><span class="sxs-lookup"><span data-stu-id="d1bc5-182">European Union GDPR</span></span>](https://go.microsoft.com/fwlink/?linkid=2108870)
11. [<span data-ttu-id="d1bc5-183">カリフォルニアコンシューマ Privacy Act (CCPA)-プレビュー</span><span class="sxs-lookup"><span data-stu-id="d1bc5-183">California Consumer Privacy Act (CCPA)- Preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2108871)
12. [<span data-ttu-id="d1bc5-184">Microsoft 365 データ保護のベースライン</span><span class="sxs-lookup"><span data-stu-id="d1bc5-184">Microsoft 365 Data Protection Baseline</span></span>](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)

> [!NOTE]
> <span data-ttu-id="d1bc5-185">パブリックプレビューの間に、[コンプライアンスマネージャー] に移動してテンプレートを作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-185">During public preview, go to Compliance Manager to create and manage your templates.</span></span>

### <a name="groups"></a><span data-ttu-id="d1bc5-186">グループ</span><span class="sxs-lookup"><span data-stu-id="d1bc5-186">Groups</span></span>

<span data-ttu-id="d1bc5-187">グループを使用すると、評価を論理的な方法で整理できます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-187">Groups allow you to organize assessments in a way that is logical to you.</span></span> <span data-ttu-id="d1bc5-188">たとえば、年、コンプライアンス標準、サービス、組織内のチーム、またはその他の方法で評価をグループ化することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-188">For example, you may choose to group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span> 

<span data-ttu-id="d1bc5-189">同じグループで2つの異なる評価を行うと、顧客が管理するアクションが共有されると、1つの評価でのアクションの実装詳細、テスト、状態の完了は、グループ内の他の評価でも同じアクションに自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-189">When two different assessments in the same group share customer-managed actions, the completion of implementation details, testing, and status for the action in one assessment automatically synchronizes to the same action in any other assessment in the group.</span></span> <span data-ttu-id="d1bc5-190">これにより、割り当てられた改善アクションがグループ間で統一され、作業の重複が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-190">This unifies the assigned improvement actions across the group and reduces duplicating work.</span></span>

<span data-ttu-id="d1bc5-191">[コンプライアンスマネージャーでグループを作成](working-with-compliance-manager.md#groups)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-191">Learn how to [create groups in Compliance Manager](working-with-compliance-manager.md#groups).</span></span>

## <a name="next-step"></a><span data-ttu-id="d1bc5-192">次の手順</span><span class="sxs-lookup"><span data-stu-id="d1bc5-192">Next step</span></span>

<span data-ttu-id="d1bc5-193">サインインしてアクセス許可を設定し、[コンプライアンススコアの設定](compliance-score-setup.md)のコンプライアンススコアダッシュボードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1bc5-193">Sign in, set up permissions, and learn about your Compliance Score dashboard in [Compliance Score setup](compliance-score-setup.md).</span></span>
