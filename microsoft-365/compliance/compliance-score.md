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
ms.openlocfilehash: 27720412ee8d2b03869b96a1ff9fce68b2fe6eb4
ms.sourcegitcommit: 5fc0f2cd1f2596fd10299333c826c501936dcd98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2020
ms.locfileid: "41261861"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="182e1-103">Microsoft コンプライアンススコア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="182e1-103">Microsoft Compliance Score (Preview)</span></span>

<span data-ttu-id="182e1-104">Microsoft コンプライアンススコアは、コンプライアンスの管理方法を簡素化し、ユーザーフレンドリな環境でコンプライアンスリスクを軽減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="182e1-104">Microsoft Compliance Score helps to simplify the way you manage compliance and reduce compliance risks through a user-friendly experience.</span></span> <span data-ttu-id="182e1-105">コンプライアンススコアは、 [Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)のパブリックプレビューで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="182e1-105">Compliance Score is now available for public preview in the  [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>

<span data-ttu-id="182e1-106">**この記事の内容**この記事を読むと、コンプライアンススコアの概要と、組織に合わせて設定する方法を理解できます。</span><span class="sxs-lookup"><span data-stu-id="182e1-106">**In this article:** Read this article to understand what Compliance Score is and how to set it up for your organization.</span></span>

<span data-ttu-id="182e1-107">**更新プログラムについて説明します。** コンプライアンススコアの[リリースノート](compliance-score-release-notes.md)に移動して、コンプライアンススコアのプレビューバージョンに関する最新情報および既知の問題を確認してください。</span><span class="sxs-lookup"><span data-stu-id="182e1-107">**Learn about updates:** Go to the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new and known issues with the preview version of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="182e1-108">コンプライアンススコアとは</span><span class="sxs-lookup"><span data-stu-id="182e1-108">What is Compliance Score</span></span>

<span data-ttu-id="182e1-109">Microsoft コンプライアンススコアは、Microsoft 365 コンプライアンスセンターのプレビュー機能で、組織の法令遵守状況を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="182e1-109">Microsoft Compliance Score is a preview feature in the Microsoft 365 compliance center to help you understand your organization’s compliance posture.</span></span> <span data-ttu-id="182e1-110">データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。</span><span class="sxs-lookup"><span data-stu-id="182e1-110">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="182e1-111">コンプライアンススコアをツールとして使用して、すべてのリスク評価を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="182e1-111">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="182e1-112">これにより、一般的なツールを使用してリスク評価を効率的に完了できるようにするためのワークフロー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="182e1-112">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="182e1-113">現在[コンプライアンスマネージャー](compliance-manager-overview.md)を使用している場合は、コンプライアンスをより簡単に管理できるようにするための、よりシンプルでわかりやすい設計のスタンドアロンの機能としてコンプライアンススコアが表示されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="182e1-113">If you currently use [Compliance Manager](compliance-manager-overview.md), you’ll notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help you manage compliance more easily.</span></span> 

<span data-ttu-id="182e1-114">メインのコンプライアンススコアページはカスタムダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="182e1-114">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="182e1-115">現在のスコアが表示され、注意が必要な点を確認したり、スコアを向上させるためのアクションを案内したりできます。</span><span class="sxs-lookup"><span data-stu-id="182e1-115">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="182e1-116">コンプライアンススコアのダッシュボードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="182e1-116">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="182e1-117">![コンプライアンススコア-ダッシュボード](media/compliance-score-dashboard.png "コンプライアンススコアダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="182e1-117">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="182e1-118">容易なコンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="182e1-118">Simplified compliance management</span></span>

<span data-ttu-id="182e1-119">コンプライアンススコアは、以下を提供することによりコンプライアンス管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="182e1-119">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="182e1-120">**継続的な評価**: Microsoft 365 環境を自動的にスキャンして、システム内のデータ保護コントロールの有効性を検出および監視します。</span><span class="sxs-lookup"><span data-stu-id="182e1-120">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="182e1-121">**推奨されるアクション**: コントロールを実装してスコアを最大化する方法について、推奨事項と詳しいガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="182e1-121">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="182e1-122">**組み込みのコントロールマッピング**: 組み込みのコモンコントロールフレームワークを提供することにより、進化し続けるコンプライアンスの状況を最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="182e1-122">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="182e1-123">コンプライアンススコアは、特定の標準または規制に対する組織のコンプライアンスの絶対的な測定基準を表しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="182e1-123">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="182e1-124">このことは、個人データや個人のプライバシーに対するリスクを軽減するために、制御を採用した範囲を表しています。</span><span class="sxs-lookup"><span data-stu-id="182e1-124">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="182e1-125">コンプライアンススコアとコンプライアンスマネージャーからの推奨事項は、コンプライアンスの保証として解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="182e1-125">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="182e1-126">このサービスは現在プレビュー段階であり、[オンラインサービス](https://go.microsoft.com/fwlink/?linkid=2108910)の使用条件の条件に従います。</span><span class="sxs-lookup"><span data-stu-id="182e1-126">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="182e1-127">コンプライアンスマネージャーとの関係</span><span class="sxs-lookup"><span data-stu-id="182e1-127">Relationship to Compliance Manager</span></span>

<span data-ttu-id="182e1-128">コンプライアンスマネージャーの簡易版として、コンプライアンススコアと考えてください。</span><span class="sxs-lookup"><span data-stu-id="182e1-128">Think of Compliance Score as a simplified version of Compliance Manager.</span></span> <span data-ttu-id="182e1-129">2つの機能は、個別の統合されたツールとして存在しますが、コンプライアンススコアを使用すると、全体的なコンプライアンスの状況を簡単に監視し、改善するための手順を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="182e1-129">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="182e1-130">コンプライアンススコアは、コンプライアンスマネージャーと同じバックエンドを共有するので、コンプライアンスマネージャーに既に所有しているデータがコンプライアンススコアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="182e1-130">Compliance Score shares the same backend with Compliance Manager, so any data you may already have in Compliance Manager will show in Compliance Score.</span></span>

<span data-ttu-id="182e1-131">パブリックプレビュー中には、評価の管理やテンプレートの作成など、コンプライアンスマネージャーだけで一部の機能が維持されます。</span><span class="sxs-lookup"><span data-stu-id="182e1-131">During public preview, some functionality remains solely in Compliance Manager, such as managing assessments and creating templates.</span></span> <span data-ttu-id="182e1-132">コンプライアンススコアでコンプライアンス管理アクティビティをすべて開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="182e1-132">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="182e1-133">コンプライアンスマネージャーによって処理された機能に到着すると、そのツールにガイドされます。</span><span class="sxs-lookup"><span data-stu-id="182e1-133">When you come to functions handled by Compliance Manager, you will be guided to that tool.</span></span> <span data-ttu-id="182e1-134">そのため、このドキュメントの一部では、コンプライアンスマネージャーのトピックについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="182e1-134">For that reason, some of this documentation directs you to Compliance Manager topics.</span></span>

<span data-ttu-id="182e1-135">コンプライアンススコアとコンプライアンスマネージャーの関係の詳細については、「[コンプライアンススコアのリリースノート](compliance-score-release-notes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="182e1-135">Learn more about the relationship between Compliance Score and Compliance Manager in the [Compliance Score release notes](compliance-score-release-notes.md).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="182e1-136">スコアを理解する</span><span class="sxs-lookup"><span data-stu-id="182e1-136">Understanding your score</span></span>

<span data-ttu-id="182e1-137">コンプライアンススコアには、Microsoft 365 データ保護基準に基づく初期スコアが与えられます。</span><span class="sxs-lookup"><span data-stu-id="182e1-137">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="182e1-138">このベースラインは、一般的な業界の規制と標準を含む一連のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="182e1-138">This baseline is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="182e1-139">このスコアは、コンプライアンスの状況を評価するための開始点として最適ですが、組織にとってより関連性の高い評価を追加すると、コンプライアンススコアがより強力になります。</span><span class="sxs-lookup"><span data-stu-id="182e1-139">While this score is a good starting point for assessing your compliance posture, Compliance Score becomes more powerful once you add assessments that are more relevant to your organization.</span></span>

<span data-ttu-id="182e1-140">たとえば、組織が金融サービス業界に属している場合は、FFIEC 評価を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="182e1-140">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="182e1-141">組織が医療機関に属している場合は、HIPAA/ヒット査定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="182e1-141">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span> <span data-ttu-id="182e1-142">[コンプライアンスマネージャーで評価を追加](working-with-compliance-manager.md#assessments)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="182e1-142">Learn how to [add assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

<span data-ttu-id="182e1-143">[コンプライアンススコアが計算され継続的に監視される方法](compliance-score-methodology.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="182e1-143">Learn more about [how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>


## <a name="key-components-controls-assessments-templates-groups"></a><span data-ttu-id="182e1-144">主要なコンポーネント: コントロール、評価、テンプレート、グループ</span><span class="sxs-lookup"><span data-stu-id="182e1-144">Key components: controls, assessments, templates, groups</span></span>

<span data-ttu-id="182e1-145">コンプライアンススコアは、コンプライアンスアクティビティの管理に役立ついくつかのコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="182e1-145">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="182e1-146">コンプライアンススコアを使用してコンプライアンスアクティビティの割り当て、テスト、および監視を行うときは、これらの主要なコンポーネントについて基本的な理解を得ておくと役立ちます。</span><span class="sxs-lookup"><span data-stu-id="182e1-146">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of these key components.</span></span> <span data-ttu-id="182e1-147">この図は、それらの間の関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="182e1-147">This diagram shows the relationships among them:</span></span>

<span data-ttu-id="182e1-148">![コンプライアンスマネージャーバージョン3のリレーションシップ](media/compliance-manager-relationships.png "コンプライアンススコアコンポーネント")</span><span class="sxs-lookup"><span data-stu-id="182e1-148">![Relationships in Compliance Manager Version 3](media/compliance-manager-relationships.png "Compliance Score components")</span></span>

### <a name="controls"></a><span data-ttu-id="182e1-149">Controls</span><span class="sxs-lookup"><span data-stu-id="182e1-149">Controls</span></span>

<span data-ttu-id="182e1-150">コントロールは、規制、標準、または内部ポリシーの特定の要件を満たすために、システム構成、組織プロセス、および人のアカウンタビリティを評価および管理する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="182e1-150">A control defines how you assess and manage system configuration, organizational process, and people accountability to meet a specific requirement of a regulation, standard, or internal policy.</span></span>

<span data-ttu-id="182e1-151">コンプライアンススコアは、次の2種類のコントロールを追跡します。</span><span class="sxs-lookup"><span data-stu-id="182e1-151">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="182e1-152">**Microsoft managed controls**: microsoft クラウドサービスのコントロール (microsoft が実装する責任者)</span><span class="sxs-lookup"><span data-stu-id="182e1-152">**Microsoft-managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="182e1-153">**顧客管理コントロール**: 組織で管理されているコントロール。</span><span class="sxs-lookup"><span data-stu-id="182e1-153">**Customer-managed controls**: controls managed by your organization, which you are responsible for implementing</span></span>
 
### <a name="assessments"></a><span data-ttu-id="182e1-154">講習</span><span class="sxs-lookup"><span data-stu-id="182e1-154">Assessments</span></span>

<span data-ttu-id="182e1-155">評価は、組織のスコアリングプロセスを開始するテンプレートの評価です。</span><span class="sxs-lookup"><span data-stu-id="182e1-155">An assessment is an evaluation of a template that initiates the scoring process for your organization.</span></span> <span data-ttu-id="182e1-156">評価標準、規制、または法律の要件を満たすために必要な処置をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="182e1-156">Assessments group the actions necessary to meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="182e1-157">たとえば、すべてのアクションを完了したときに、ISO 27001 要件に合わせて Office 365 の設定をオンラインにするという評価がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="182e1-157">For example, you may have an assessment that, when you complete all actions within it, brings your Office 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="182e1-158">既定では、コンプライアンススコアは、Microsoft 365 データ保護基準に基づいた評価を組織に提供します。これには、データ保護とコンプライアンスのリスクを軽減するための推奨事項があります (詳細については、こちらを[参照](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)してください)。</span><span class="sxs-lookup"><span data-stu-id="182e1-158">By default, Compliance Score provides your organization with an assessment based on the Microsoft 365 data protection baseline, a recommendation for reducing your data protection and compliance risks ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

<span data-ttu-id="182e1-159">評価には、いくつかのコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="182e1-159">Assessments include several components:</span></span>

- <span data-ttu-id="182e1-160">**スコープ内サービス**: 評価に適用可能な Microsoft サービスの特定のセット</span><span class="sxs-lookup"><span data-stu-id="182e1-160">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="182e1-161">**Microsoft managed controls**: microsoft が実装およびテストした制御</span><span class="sxs-lookup"><span data-stu-id="182e1-161">**Microsoft-managed controls**: controls that Microsoft implemented and tested</span></span>
- <span data-ttu-id="182e1-162">**顧客管理コントロール**: 管理するコントロール</span><span class="sxs-lookup"><span data-stu-id="182e1-162">**Customer-managed controls**: controls that you manage</span></span>
- <span data-ttu-id="182e1-163">**評価スコア**: その評価内でアクションを完了して得られたポイントのパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="182e1-163">**Assessment score**: the percentage of the points achieved by completing actions within that assessment</span></span>

> [!NOTE]
> <span data-ttu-id="182e1-164">コンプライアンススコアには、評価と、全体的なスコアにどのような影響があるかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="182e1-164">Compliance Score displays your assessments and how they factor into your overall score.</span></span> <span data-ttu-id="182e1-165">ただし、パブリックプレビュー中には、評価を管理するためにコンプライアンスマネージャーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="182e1-165">However, during public preview you will be directed to Compliance Manager to manage your assessments.</span></span>

<span data-ttu-id="182e1-166">[コンプライアンスマネージャーで評価を処理](working-with-compliance-manager.md#assessments)するための詳細な手順を表示します。</span><span class="sxs-lookup"><span data-stu-id="182e1-166">View detailed instructions for [working with assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

### <a name="templates"></a><span data-ttu-id="182e1-167">テンプレート</span><span class="sxs-lookup"><span data-stu-id="182e1-167">Templates</span></span>

<span data-ttu-id="182e1-168">コンプライアンススコア評価用に事前に構成されたテンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="182e1-168">Compliance Score provides pre-configured templates for assessments.</span></span> <span data-ttu-id="182e1-169">コンプライアンススコアを使用すると、自分のニーズに合わせて独自の評価用にテンプレートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="182e1-169">Compliance Score also allows you to create templates for your own assessments to suit your needs.</span></span> <span data-ttu-id="182e1-170">たとえば、事前に構成されたテンプレートの1つでは網羅されていない地域データ保護またはコンプライアンス標準のテンプレートとして、ビジネスプロセスコントロール用のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="182e1-170">For example, you can create a template for your business process control, or a template for a regional data protection or compliance standard that isn’t covered by one of the pre-configured templates.</span></span>  <span data-ttu-id="182e1-171">独自のテンプレートを作成することにより、カスタム評価を作成して、コンプライアンススコアが Microsoft クラウド評価だけでなく、組織のスコープ内の他のリスク評価も追跡できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="182e1-171">By creating your own templates, you can create custom assessments to ensure that Compliance Score tracks not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

<span data-ttu-id="182e1-172">新しいテンプレートを作成するには、既存のテンプレートをコピーするか、Excel ファイルからコントロールの情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="182e1-172">You can create new templates by copying an existing template, or by importing controls information from an Excel file.</span></span> <span data-ttu-id="182e1-173">[コンプライアンスマネージャーでテンプレートを作成](working-with-compliance-manager.md#templates)するための詳細な手順を表示します。</span><span class="sxs-lookup"><span data-stu-id="182e1-173">View detailed instructions for [creating templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

<span data-ttu-id="182e1-174">コンプライアンススコア用に事前に構成されたテンプレートは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="182e1-174">The pre-configured templates for Compliance Score are:</span></span>

1. [<span data-ttu-id="182e1-175">ブラジルの一般データ保護法 (LGPD)</span><span class="sxs-lookup"><span data-stu-id="182e1-175">Brazil General Data Protection Law (LGPD)</span></span>](https://go.microsoft.com/fwlink/?linkid=2115387)
2. <span data-ttu-id="182e1-176">[カリフォルニアコンシューマ Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="182e1-176">[California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (Preview)</span></span>
3. [<span data-ttu-id="182e1-177">Cloud Security アライアンス (CSA) Cloud Controls Matrix (CCM) 3.0.1</span><span class="sxs-lookup"><span data-stu-id="182e1-177">Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1</span></span>](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [<span data-ttu-id="182e1-178">欧州連合 GDPR</span><span class="sxs-lookup"><span data-stu-id="182e1-178">European Union GDPR</span></span>](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [<span data-ttu-id="182e1-179">連邦金融機関調査協議会 (FFIEC) Information Security ブックレット</span><span class="sxs-lookup"><span data-stu-id="182e1-179">Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet</span></span>](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [<span data-ttu-id="182e1-180">FedRAMP モデレート</span><span class="sxs-lookup"><span data-stu-id="182e1-180">FedRAMP Moderate</span></span>](https://go.microsoft.com/fwlink/?linkid=2108869)
7. <span data-ttu-id="182e1-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / の[ヒット](https://go.microsoft.com/fwlink/?linkid=2109079)</span><span class="sxs-lookup"><span data-stu-id="182e1-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span></span>
8. <span data-ttu-id="182e1-182">[Irap](https://go.microsoft.com/fwlink/?linkid=2113709) / [オーストラリア自治体 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="182e1-182">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [Australian Government ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (Preview)</span></span>
9. [<span data-ttu-id="182e1-183">ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="182e1-183">ISO 27001:2013</span></span>](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [<span data-ttu-id="182e1-184">ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="182e1-184">ISO 27018:2014</span></span>](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [<span data-ttu-id="182e1-185">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="182e1-185">ISO 27701:2019</span></span>](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [<span data-ttu-id="182e1-186">Microsoft 365 データ保護のベースライン</span><span class="sxs-lookup"><span data-stu-id="182e1-186">Microsoft 365 Data Protection Baseline</span></span>](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [<span data-ttu-id="182e1-187">NIST 800-53 リビジョン4</span><span class="sxs-lookup"><span data-stu-id="182e1-187">NIST 800-53 Rev. 4</span></span>](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [<span data-ttu-id="182e1-188">NIST 800-171</span><span class="sxs-lookup"><span data-stu-id="182e1-188">NIST 800-171</span></span>](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [<span data-ttu-id="182e1-189">NIST Cybersecurity Framework (CSF)</span><span class="sxs-lookup"><span data-stu-id="182e1-189">NIST Cybersecurity Framework (CSF)</span></span>](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [<span data-ttu-id="182e1-190">SOC 1</span><span class="sxs-lookup"><span data-stu-id="182e1-190">SOC 1</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [<span data-ttu-id="182e1-191">SOC 2</span><span class="sxs-lookup"><span data-stu-id="182e1-191">SOC 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)

> [!NOTE]
> <span data-ttu-id="182e1-192">パブリックプレビューの間に、[コンプライアンスマネージャー] に移動してテンプレートを作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="182e1-192">During public preview, go to Compliance Manager to create and manage your templates.</span></span>

### <a name="groups"></a><span data-ttu-id="182e1-193">グループ</span><span class="sxs-lookup"><span data-stu-id="182e1-193">Groups</span></span>

<span data-ttu-id="182e1-194">グループを使用すると、評価を論理的な方法で整理できます。</span><span class="sxs-lookup"><span data-stu-id="182e1-194">Groups allow you to organize assessments in a way that is logical to you.</span></span> <span data-ttu-id="182e1-195">たとえば、年、コンプライアンス標準、サービス、組織内のチーム、またはその他の方法で評価をグループ化することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="182e1-195">For example, you may choose to group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span>

<span data-ttu-id="182e1-196">同じグループで2つの異なる評価を行うと、顧客が管理するアクションが共有されると、1つの評価でのアクションの実装詳細、テスト、状態の完了は、グループ内の他の評価でも同じアクションに自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="182e1-196">When two different assessments in the same group share customer-managed actions, the completion of implementation details, testing, and status for the action in one assessment automatically synchronizes to the same action in any other assessment in the group.</span></span> <span data-ttu-id="182e1-197">これにより、割り当てられた改善アクションがグループ間で統一され、作業の重複が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="182e1-197">This unifies the assigned improvement actions across the group and reduces duplicating work.</span></span>

<span data-ttu-id="182e1-198">[コンプライアンスマネージャーでグループを作成](working-with-compliance-manager.md#groups)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="182e1-198">Learn how to [create groups in Compliance Manager](working-with-compliance-manager.md#groups).</span></span> <span data-ttu-id="182e1-199">グループを作成すると、[コンプライアンススコアダッシュボードをフィルター処理](compliance-score-setup.md#filtering-your-dashboard-view)して、1つ以上のグループでスコアを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="182e1-199">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

## <a name="next-step-begin-setup"></a><span data-ttu-id="182e1-200">次の手順: セットアップを開始する</span><span class="sxs-lookup"><span data-stu-id="182e1-200">Next step: begin setup</span></span>

<span data-ttu-id="182e1-201">サインイン、アクセス許可の設定、[コンプライアンススコアの設定](compliance-score-setup.md)でのコンプライアンススコアダッシュボードの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="182e1-201">Sign in, set up permissions, and learn about your Compliance Score dashboard at [Compliance Score setup](compliance-score-setup.md).</span></span>
