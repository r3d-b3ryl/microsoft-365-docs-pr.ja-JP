---
title: コンプライアンスマネージャーを使用して改善アクションを管理する
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: コンプライアンススコアとコンプライアンスマネージャーを使用して、個人データの保護レベルを向上させる方法について説明します。
ms.openlocfilehash: 5b41fa9fc52253d415a22aaa3422a87c4f1bda7c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377101"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="e5336-103">コンプライアンスマネージャーを使用して改善アクションを管理する</span><span class="sxs-lookup"><span data-stu-id="e5336-103">Use Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="e5336-104">Microsoft コンプライアンスマネージャーは、欧州連合の [一般的なデータ保護規則 (GDPR)](../compliance/gdpr.md)、 [カリフォルニアのコンシューマー保護法 ccpa](../compliance/ccpa-faq.md)、HIPAA (米国の医療保険法)、およびブラジルのデータ保護法 (LGPD) など、データのプライバシー規制に関連する改善の管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e5336-104">Microsoft Compliance Manager can help you manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](../compliance/gdpr.md), [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="e5336-105">この記事では、データのプライバシー保護の目的でこのツールを使用するためのガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="e5336-105">This article provides guidance on the use of this tool for data privacy purposes.</span></span>

>[!Note]
><span data-ttu-id="e5336-106">コンプライアンス マネージャーの推奨事項は、コンプライアンスの保証と捉えることはできません。</span><span class="sxs-lookup"><span data-stu-id="e5336-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="e5336-107">お客様は、お客様の規制環境に応じて、カスタマーコントロールの有効性を評価および検証することができます。</span><span class="sxs-lookup"><span data-stu-id="e5336-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="e5336-108">これらのサービスは、 [オンラインサービスの用語](https://go.microsoft.com/fwlink/?linkid=2108910)の条件に従います。</span><span class="sxs-lookup"><span data-stu-id="e5336-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="e5336-109">[セキュリティとコンプライアンスのための Microsoft 365 ライセンスガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)も参照</span><span class="sxs-lookup"><span data-stu-id="e5336-109">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span></span>
>

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="e5336-110">コンプライアンスマネージャーの概要</span><span class="sxs-lookup"><span data-stu-id="e5336-110">Getting started with Compliance Manager</span></span>

#### <a name="what-is-compliance-manager"></a><span data-ttu-id="e5336-111">コンプライアンスマネージャーとは</span><span class="sxs-lookup"><span data-stu-id="e5336-111">What is Compliance Manager</span></span>

<span data-ttu-id="e5336-112">[コンプライアンスマネージャー](../compliance/compliance-manager.md) は、microsoft クラウドサービスに関連する法令遵守アクティビティを管理するために、microsoft 365 コンプライアンスセンターのワークフローベースのリスク評価ツールです。</span><span class="sxs-lookup"><span data-stu-id="e5336-112">[Compliance Manager](../compliance/compliance-manager.md) is a workflow-based risk assessment tool in the Microsoft 365 compliance center for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="e5336-113">Microsoft 365 または Azure Active Directory (Azure AD) サブスクリプションの一部として、コンプライアンスマネージャーは、Microsoft クラウドサービスの共有責任モデル内の法令遵守を管理するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e5336-113">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="e5336-114">**評価の使用準備完了**</span><span class="sxs-lookup"><span data-stu-id="e5336-114">**Ready to use assessments**</span></span>

<span data-ttu-id="e5336-115">コンプライアンスマネージャーは、GDPR や HIPAA/ヒットエコーなど、データプライバシー関連の規制に沿った [評価を作成](../compliance/compliance-manager-assessments.md) するための事前に作成されたテンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5336-115">Compliance Manager provides pre-built templates for [building assessments](../compliance/compliance-manager-assessments.md) that are aligned to data privacy-related regulations, such as GDPR and HIPAA/HITECH.</span></span> <span data-ttu-id="e5336-116">テンプレートには、規制の要件を満たすように改善アクションを実行できるように、組み込みのコントロールマッピングが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e5336-116">The templates have built-in control mapping to help you take improvement actions for meeting the regulation's requirements.</span></span> <span data-ttu-id="e5336-117">各評価では、対象サービスに固有の各規制呼び出しについての情報が提供されます。これは、Microsoft が管理および制御するコントロールによって分解されます。</span><span class="sxs-lookup"><span data-stu-id="e5336-117">Each assessment provides information about the controls each regulation calls for specific to the target service, broken out by controls you manage and controls Microsoft manages.</span></span> 

<span data-ttu-id="e5336-118">事前に作成されたテンプレートを使用すると、リスク評価をすばやく始めることができます。</span><span class="sxs-lookup"><span data-stu-id="e5336-118">Using a pre-built template helps you quickly get started with risk assessments.</span></span> <span data-ttu-id="e5336-119">コンプライアンスマネージャーを使用して熟練した方がきたら、独自のコントロールや改善アクションを追加することによって、作成済みのテンプレートをカスタマイズしたり、組織のニーズに合わせて独自のカスタム評価を作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5336-119">As you become more proficient in using Compliance Manger, you can customize a pre-built template by adding your own controls and improvement actions, or you can create your own custom assessments to suit your organization's needs.</span></span>

<span data-ttu-id="e5336-120">コンプライアンスマネージャーによって提供される [評価テンプレートの完全な一覧](../compliance/compliance-manager-templates-list.md) を表示します。</span><span class="sxs-lookup"><span data-stu-id="e5336-120">View the [full list of assessment templates](../compliance/compliance-manager-templates-list.md) provided by Compliance Manager.</span></span>

<span data-ttu-id="e5336-121">**リアルタイムのコンプライアンススコア**</span><span class="sxs-lookup"><span data-stu-id="e5336-121">**Real-time compliance score**</span></span>

<span data-ttu-id="e5336-122">また、コンプライアンスマネージャーは、コントロール内で推奨される改善アクションを完了するための進捗状況を測定するコンプライアンススコアを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5336-122">Compliance Manager also provides you with a compliance score that measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="e5336-123">このスコアを使用して、進行状況を監視し、リスクを軽減する可能性に基づいてアクションの優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e5336-123">You can use this score to help monitor your progress and prioritize actions based on their potential to reduce risk.</span></span>

#### <a name="use-the-compliance-manager-quickstart-guide"></a><span data-ttu-id="e5336-124">コンプライアンスマネージャーのクイックスタートガイドを使用する</span><span class="sxs-lookup"><span data-stu-id="e5336-124">Use the Compliance Manager quickstart guide</span></span>

<span data-ttu-id="e5336-125">コンプライアンスマネージャーの [クイックスタート](../compliance/compliance-manager-quickstart.md) ガイドには、コンプライアンスマネージャーの操作に役立つ段階的な手順と主要なリソースへのリンクが記載されています。</span><span class="sxs-lookup"><span data-stu-id="e5336-125">The [Compliance Manager quickstart](../compliance/compliance-manager-quickstart.md) guide provides graduated steps and links to key resources to help you work with Compliance Manager:</span></span>

- [<span data-ttu-id="e5336-126">最初の訪問: コンプライアンスマネージャーの理解を深める</span><span class="sxs-lookup"><span data-stu-id="e5336-126">First visit: get familiar with Compliance Manager</span></span>](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - <span data-ttu-id="e5336-127">コンプライアンスマネージャーダッシュボードを使用する</span><span class="sxs-lookup"><span data-stu-id="e5336-127">Working with your Compliance Manager dashboard</span></span>
    - <span data-ttu-id="e5336-128">コンプライアンススコアを理解する</span><span class="sxs-lookup"><span data-stu-id="e5336-128">Understanding your compliance score</span></span>
    - <span data-ttu-id="e5336-129">改善アクションについて学習する</span><span class="sxs-lookup"><span data-stu-id="e5336-129">Learning about improvement actions</span></span>
    - <span data-ttu-id="e5336-130">評価とテンプレートについて</span><span class="sxs-lookup"><span data-stu-id="e5336-130">Understanding assessments and templates</span></span>
- [<span data-ttu-id="e5336-131">ランプアップ: コンプライアンスマネージャーを構成してコンプライアンスアクティビティを管理する</span><span class="sxs-lookup"><span data-stu-id="e5336-131">Ramping up: configure Compliance Manager to manage your compliance activities</span></span>](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - <span data-ttu-id="e5336-132">最初の評価を作成および管理する</span><span class="sxs-lookup"><span data-stu-id="e5336-132">Building and managing your first assessment</span></span>
    - <span data-ttu-id="e5336-133">改善アクションで実装とテストを実行して、評価の制御を完成させる</span><span class="sxs-lookup"><span data-stu-id="e5336-133">Performing implementation and testing work on improvement actions to complete controls in your assessments</span></span>
    - <span data-ttu-id="e5336-134">さまざまなアクションがコンプライアンススコアに与える影響について</span><span class="sxs-lookup"><span data-stu-id="e5336-134">Understanding how different actions impact your compliance score</span></span>
- [<span data-ttu-id="e5336-135">スケールアップ: 高度な機能を使用してカスタムのニーズを満たす</span><span class="sxs-lookup"><span data-stu-id="e5336-135">Scaling up: use advanced functionality to meet your custom needs</span></span>](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - <span data-ttu-id="e5336-136">Microsoft 以外の365製品を追跡するためのカスタム評価を作成する</span><span class="sxs-lookup"><span data-stu-id="e5336-136">Creating your custom assessments to track non-Microsoft 365 products</span></span>
    - <span data-ttu-id="e5336-137">既存のテンプレートを変更してコントロールを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="e5336-137">Modifying existing templates to add or remove controls</span></span>
    - <span data-ttu-id="e5336-138">改善アクションの自動化されたテストの設定</span><span class="sxs-lookup"><span data-stu-id="e5336-138">Setting up automated testing of improvement actions</span></span>

## <a name="how-your-compliance-score-is-calculated"></a><span data-ttu-id="e5336-139">コンプライアンススコアの計算方法</span><span class="sxs-lookup"><span data-stu-id="e5336-139">How your compliance score is calculated</span></span>

<span data-ttu-id="e5336-140">コンプライアンススコアは、Microsoft とお客様が管理する統制の組み合わせに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="e5336-140">Your compliance score is calculated based on a combination of Microsoft and customer-managed control implementations.</span></span> <span data-ttu-id="e5336-141">詳細な説明については、「 [コンプライアンススコアの計算](../compliance/compliance-score-calculation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5336-141">See [compliance score calculation](../compliance/compliance-score-calculation.md) for a detailed explanation.</span></span>

<span data-ttu-id="e5336-142">コントロールには、必須か任意かを基準にしたスコア値、および予防的、検出、または是正のいずれであるかに基づいて、スコア値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e5336-142">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="e5336-143">これらは、他のコントロールに関連して実装されていないリスクをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="e5336-143">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="e5336-144">「コンプライアンススコアの計算」の記事に示されているように、予防的な制御は、検出と修正されたものよりも高いスコアを取得し、固定のコントロールは任意のスコアより高いスコアを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5336-144">As presented in the compliance score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>

<span data-ttu-id="e5336-145">コンプライアンススコア管理 UI では、これらのパラメーターは表示されません。また、これらのパラメーターを使用してフィルター処理することもできません。</span><span class="sxs-lookup"><span data-stu-id="e5336-145">The Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="e5336-146">ただし、関連付けられているテンプレートをコンプライアンスマネージャーからダウンロードした場合、結果として得られるデータセットには、ほとんどの規制に関するこれらのパラメーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5336-146">However, if you download the associated template from  Compliance Manager, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="e5336-147">技術的な統制のため、コンプライアンスマネージャーは、アクションが正常に実装およびテストされた後に、改善アクションのスコアを自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="e5336-147">For technical controls, Compliance Manager automatically updates the improvement action score once the action has been successfully implemented and tested.</span></span> <span data-ttu-id="e5336-148">その他の技術以外の管理操作、 &mdash; またはドキュメントに関連付けられているアクションは、 &mdash; ポイントがスコアになる前に、実装されたとおりに手動で記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5336-148">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually as implemented before points count toward your score.</span></span>

<span data-ttu-id="e5336-149">また、データプライバシー規制へのコンプライアンス以外の理由で保持ラベルを使用するなど、他の目的のために特定の改善アクションを実装することもあります。このような機能は、 &mdash; &mdash; 他の目的で使用されている場合でも、意図的な法令遵守アクションの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="e5336-149">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="e5336-150">コンプライアンススコアは、幅広い規模で改善を追跡するための相対的な指標として考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5336-150">Your compliance score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="e5336-151">完全なスコアを追求する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e5336-151">You should not pursue a perfect score.</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="e5336-152">追加のガイダンス</span><span class="sxs-lookup"><span data-stu-id="e5336-152">Additional guidance</span></span>

<span data-ttu-id="e5336-153">コンプライアンスマネージャーを使用してデータプライバシー規制へのコンプライアンスを実現するための、いくつかの重要なヒントを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e5336-153">Here are a few important tips for using Compliance Manager to help you achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="e5336-154">各データプライバシー規制には、技術統制、ドキュメント仕様、運用、プロセス、およびレポートの要件の組み合わせがあります。</span><span class="sxs-lookup"><span data-stu-id="e5336-154">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="e5336-155">これらのすべてが向上アクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5336-155">All of these show up in the improvement actions.</span></span>

- <span data-ttu-id="e5336-156">改善アクションの表示を関心のある領域に絞り込むには、コンプライアンスマネージャー管理者の [ **ソリューション** ] タブで、アクションの種類によってフィルター処理できます。詳細については [、「コンプライアンスマネージャーダッシュボードビューのフィルター処理](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5336-156">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Manager admin. Learn more about [filtering your Compliance Manager dashboard view](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).</span></span>

- <span data-ttu-id="e5336-157">コンプライアンスマネージャーで特定された改善アクションの相対的な重要性と優先度は、組織が管理する必要があると判断した、より広範なリスクレビューの一環として考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5336-157">The relative importance and priority of improvement actions identified in Compliance Manager should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span>

- <span data-ttu-id="e5336-158">複数の規制要件に対する改善アクションの集約がある場合でも、GDPR、LGPD、CCPA、および HIPAA ヒットの規則の評価テンプレートが選択されている場合は、400向上アクションのほとんどがコンプライアンスマネージャーに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5336-158">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Manager.</span></span> <span data-ttu-id="e5336-159">この長いリストをより適切に処理するには、向上アクションフィルターを使用して、結果セットをより扱いやすいリストに絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="e5336-159">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="e5336-160">[カテゴリ] フィルターは、この総合的なソリューション内の記事を追跡、禁止、保護、保持、および調査する論理グループによって改善アクションをフィルター処理する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5336-160">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span>

- <span data-ttu-id="e5336-161">向上アクションに記載されているコントロールの中には、特定の規制記事に直接関連していると見なされるものがありますが、他のコントロールは規制の精神と多くの場合は、単に推奨されるアクティビティやベストプラクティスに関連している場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5336-161">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and many times are simply recommended activities or best practices.</span></span>