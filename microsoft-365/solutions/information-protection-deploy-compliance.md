---
title: コンプライアンス マネージャーを使用して改善アクションを管理する
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
description: コンプライアンス スコアとコンプライアンス マネージャーを使用して、個人データの保護レベルを向上させる方法について学習します。
ms.openlocfilehash: 87131ea65661e8285fd7c3b36a87c79b618348d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918572"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="35ee0-103">コンプライアンス マネージャーを使用して改善アクションを管理する</span><span class="sxs-lookup"><span data-stu-id="35ee0-103">Use Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="35ee0-104">Microsoft コンプライアンス マネージャーは、EU 一般データ保護規則 [(GDPR)](/compliance/regulatory/gdpr)、カリフォルニア州消費者保護法 CCPA、HIPAA-HITECH (米国の医療プライバシー法)、ブラジルデータ保護法 [(LGPD)](/compliance/regulatory/ccpa-faq)などのデータプライバシー規制に関連する改善を管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-104">Microsoft Compliance Manager can help you manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](/compliance/regulatory/gdpr), [California Consumer Protection Act CCPA)](/compliance/regulatory/ccpa-faq), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="35ee0-105">この記事では、データのプライバシーを目的としてこのツールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-105">This article provides guidance on the use of this tool for data privacy purposes.</span></span>

>[!Note]
><span data-ttu-id="35ee0-106">コンプライアンス マネージャーの推奨事項は、コンプライアンスの保証と捉えることはできません。</span><span class="sxs-lookup"><span data-stu-id="35ee0-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="35ee0-107">規制環境ごとの顧客管理の有効性を評価および検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35ee0-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="35ee0-108">これらのサービスは、Online Services 利用規約の条件 [に従います](https://go.microsoft.com/fwlink/?linkid=2108910)。</span><span class="sxs-lookup"><span data-stu-id="35ee0-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="35ee0-109">セキュリティと [コンプライアンスについては、「Microsoft 365 ライセンス ガイダンス」も参照してください。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span><span class="sxs-lookup"><span data-stu-id="35ee0-109">See also [Microsoft 365 licensing guidance for security and compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span></span>
>

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="35ee0-110">コンプライアンス マネージャーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="35ee0-110">Getting started with Compliance Manager</span></span>

#### <a name="what-is-compliance-manager"></a><span data-ttu-id="35ee0-111">コンプライアンス マネージャーとは</span><span class="sxs-lookup"><span data-stu-id="35ee0-111">What is Compliance Manager</span></span>

<span data-ttu-id="35ee0-112">[コンプライアンス マネージャー](../compliance/compliance-manager.md) は、Microsoft クラウド サービスに関連する規制コンプライアンス 活動を管理するための、Microsoft 365 コンプライアンス センターのワークフロー ベースのリスク評価ツールです。</span><span class="sxs-lookup"><span data-stu-id="35ee0-112">[Compliance Manager](../compliance/compliance-manager.md) is a workflow-based risk assessment tool in the Microsoft 365 compliance center for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="35ee0-113">コンプライアンス マネージャーは、Microsoft 365 または Azure Active Directory (Azure AD) サブスクリプションの一部として、Microsoft クラウド サービスの共有責任モデル内の規制コンプライアンスを管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-113">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="35ee0-114">**評価を使用する準備ができました**</span><span class="sxs-lookup"><span data-stu-id="35ee0-114">**Ready to use assessments**</span></span>

<span data-ttu-id="35ee0-115">コンプライアンス マネージャーは、GDPR や[](../compliance/compliance-manager-assessments.md)HIPAA/HITECH などのデータ プライバシー関連の規制に沿った評価を構築するために事前に構築されたテンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-115">Compliance Manager provides pre-built templates for [building assessments](../compliance/compliance-manager-assessments.md) that are aligned to data privacy-related regulations, such as GDPR and HIPAA/HITECH.</span></span> <span data-ttu-id="35ee0-116">テンプレートには、規制の要件を満たす改善アクションを実行するのに役立つコントロール マッピングが組み込みされています。</span><span class="sxs-lookup"><span data-stu-id="35ee0-116">The templates have built-in control mapping to help you take improvement actions for meeting the regulation's requirements.</span></span> <span data-ttu-id="35ee0-117">各評価では、対象サービスに固有の各規制が呼び出すコントロールに関する情報を提供します。Microsoft が管理および制御するコントロールによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="35ee0-117">Each assessment provides information about the controls each regulation calls for specific to the target service, broken out by controls you manage and controls Microsoft manages.</span></span> 

<span data-ttu-id="35ee0-118">事前構築されたテンプレートを使用すると、リスク評価をすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-118">Using a pre-built template helps you quickly get started with risk assessments.</span></span> <span data-ttu-id="35ee0-119">コンプライアンス マネージャーの使用に詳しくなると、独自のコントロールと改善アクションを追加して、事前に構築されたテンプレートをカスタマイズしたり、組織のニーズに合わせて独自のカスタム評価を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-119">As you become more proficient in using Compliance Manager, you can customize a pre-built template by adding your own controls and improvement actions, or you can create your own custom assessments to suit your organization's needs.</span></span>

<span data-ttu-id="35ee0-120">コンプライアンス マネージャー [によって提供される評価テンプレートの完全](../compliance/compliance-manager-templates-list.md) な一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-120">View the [full list of assessment templates](../compliance/compliance-manager-templates-list.md) provided by Compliance Manager.</span></span>

<span data-ttu-id="35ee0-121">**リアルタイムのコンプライアンス スコア**</span><span class="sxs-lookup"><span data-stu-id="35ee0-121">**Real-time compliance score**</span></span>

<span data-ttu-id="35ee0-122">コンプライアンス マネージャーは、コントロール内で推奨される改善アクションを完了する進捗状況を測定するコンプライアンス スコアも提供します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-122">Compliance Manager also provides you with a compliance score that measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="35ee0-123">このスコアを使用すると、進捗状況を監視し、リスクを軽減する可能性に基づいてアクションの優先順位を設定できます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-123">You can use this score to help monitor your progress and prioritize actions based on their potential to reduce risk.</span></span>

#### <a name="use-the-compliance-manager-quickstart-guide"></a><span data-ttu-id="35ee0-124">コンプライアンス マネージャーのクイック スタート ガイドを使用する</span><span class="sxs-lookup"><span data-stu-id="35ee0-124">Use the Compliance Manager quickstart guide</span></span>

<span data-ttu-id="35ee0-125">コンプライアンス [マネージャーのクイック スタート ガイド](../compliance/compliance-manager-quickstart.md) には、コンプライアンス マネージャーの作業に役立つ主要なリソースへの手順とリンクが示されています。</span><span class="sxs-lookup"><span data-stu-id="35ee0-125">The [Compliance Manager quickstart](../compliance/compliance-manager-quickstart.md) guide provides graduated steps and links to key resources to help you work with Compliance Manager:</span></span>

- [<span data-ttu-id="35ee0-126">最初の訪問: コンプライアンス マネージャーについて理解する</span><span class="sxs-lookup"><span data-stu-id="35ee0-126">First visit: get familiar with Compliance Manager</span></span>](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - <span data-ttu-id="35ee0-127">コンプライアンス マネージャー ダッシュボードの操作</span><span class="sxs-lookup"><span data-stu-id="35ee0-127">Working with your Compliance Manager dashboard</span></span>
    - <span data-ttu-id="35ee0-128">コンプライアンス スコアについて</span><span class="sxs-lookup"><span data-stu-id="35ee0-128">Understanding your compliance score</span></span>
    - <span data-ttu-id="35ee0-129">改善アクションについて学習する</span><span class="sxs-lookup"><span data-stu-id="35ee0-129">Learning about improvement actions</span></span>
    - <span data-ttu-id="35ee0-130">評価とテンプレートについて</span><span class="sxs-lookup"><span data-stu-id="35ee0-130">Understanding assessments and templates</span></span>
- [<span data-ttu-id="35ee0-131">ランプアップ: コンプライアンス アクティビティを管理するコンプライアンス マネージャーを構成する</span><span class="sxs-lookup"><span data-stu-id="35ee0-131">Ramping up: configure Compliance Manager to manage your compliance activities</span></span>](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - <span data-ttu-id="35ee0-132">最初の評価の作成と管理</span><span class="sxs-lookup"><span data-stu-id="35ee0-132">Building and managing your first assessment</span></span>
    - <span data-ttu-id="35ee0-133">改善アクションの実装とテスト作業を実行して、評価のコントロールを完了する</span><span class="sxs-lookup"><span data-stu-id="35ee0-133">Performing implementation and testing work on improvement actions to complete controls in your assessments</span></span>
    - <span data-ttu-id="35ee0-134">さまざまなアクションがコンプライアンス スコアに与える影響を理解する</span><span class="sxs-lookup"><span data-stu-id="35ee0-134">Understanding how different actions impact your compliance score</span></span>
- [<span data-ttu-id="35ee0-135">スケール アップ: 高度な機能を使用してカスタム ニーズを満たす</span><span class="sxs-lookup"><span data-stu-id="35ee0-135">Scaling up: use advanced functionality to meet your custom needs</span></span>](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - <span data-ttu-id="35ee0-136">Microsoft 365 以外の製品を追跡するためのカスタム評価の作成</span><span class="sxs-lookup"><span data-stu-id="35ee0-136">Creating your custom assessments to track non-Microsoft 365 products</span></span>
    - <span data-ttu-id="35ee0-137">既存のテンプレートを変更してコントロールを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="35ee0-137">Modifying existing templates to add or remove controls</span></span>
    - <span data-ttu-id="35ee0-138">改善アクションの自動テストのセットアップ</span><span class="sxs-lookup"><span data-stu-id="35ee0-138">Setting up automated testing of improvement actions</span></span>

## <a name="how-your-compliance-score-is-calculated"></a><span data-ttu-id="35ee0-139">コンプライアンススコアの計算方法</span><span class="sxs-lookup"><span data-stu-id="35ee0-139">How your compliance score is calculated</span></span>

<span data-ttu-id="35ee0-140">コンプライアンス スコアは、Microsoft と顧客が管理するコントロールの実装の組み合わせに基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-140">Your compliance score is calculated based on a combination of Microsoft and customer-managed control implementations.</span></span> <span data-ttu-id="35ee0-141">詳細 [については、「コンプライアンス スコアの](../compliance/compliance-score-calculation.md) 計算」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35ee0-141">See [compliance score calculation](../compliance/compliance-score-calculation.md) for a detailed explanation.</span></span>

<span data-ttu-id="35ee0-142">コントロールには、必須か任意か、予防的か探偵か修正かに基づいてスコア値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-142">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="35ee0-143">これらはまとめて、他のコントロールに対して実装しないリスクを表します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-143">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="35ee0-144">コンプライアンス スコアの計算に関する記事で説明されている通り、予防コントロールは探偵や修正コントロールよりも高いスコアを取得し、必須のコントロールは任意のコントロールよりも高いスコアを取得します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-144">As presented in the compliance score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>

<span data-ttu-id="35ee0-145">コンプライアンス スコア管理 UI では、これらのパラメーターは一覧表示されません。また、これらのパラメーターによってフィルター処理を行う機能も提供しません。</span><span class="sxs-lookup"><span data-stu-id="35ee0-145">The Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="35ee0-146">ただし、コンプライアンス マネージャーから関連付けられたテンプレートをダウンロードした場合、結果のデータ セットには、ほとんどの規制に対してこれらのパラメーターが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-146">However, if you download the associated template from  Compliance Manager, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="35ee0-147">技術コントロールの場合、コンプライアンス マネージャーは、アクションが正常に実装およびテストされると、改善アクション スコアを自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-147">For technical controls, Compliance Manager automatically updates the improvement action score once the action has been successfully implemented and tested.</span></span> <span data-ttu-id="35ee0-148">その他、操作上の操作やドキュメントに関連する操作などの技術的でない制御アクションは、ポイントがスコアにカウントされる前に手動で記録する &mdash; &mdash; 必要があります。</span><span class="sxs-lookup"><span data-stu-id="35ee0-148">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually as implemented before points count toward your score.</span></span>

<span data-ttu-id="35ee0-149">また、データ プライバシー規制のコンプライアンス以外の理由で保持ラベルを使用するなどの目的で、他の目的で特定の改善アクションを実装している場合も多く、意図的なコンプライアンスアクションの一部ではなく、他の目的で使用されている場合でも、そのような機能を使用する際の信用を得る可能性があります。 &mdash; &mdash;</span><span class="sxs-lookup"><span data-stu-id="35ee0-149">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="35ee0-150">コンプライアンス スコアは、広範な規模で改善を追跡する相対的な手段と見なされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35ee0-150">Your compliance score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="35ee0-151">完璧なスコアを追求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35ee0-151">You should not pursue a perfect score.</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="35ee0-152">追加のガイダンス</span><span class="sxs-lookup"><span data-stu-id="35ee0-152">Additional guidance</span></span>

<span data-ttu-id="35ee0-153">コンプライアンス マネージャーを使用してデータプライバシー規制のコンプライアンスを達成するための重要なヒントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-153">Here are a few important tips for using Compliance Manager to help you achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="35ee0-154">各データプライバシー規制には、技術的な制御、ドキュメント仕様、運用、プロセス、およびレポートの要件が組み合わせて含まれています。</span><span class="sxs-lookup"><span data-stu-id="35ee0-154">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="35ee0-155">これらのすべてが改善アクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-155">All of these show up in the improvement actions.</span></span>

- <span data-ttu-id="35ee0-156">改善アクションのビューを関心のある領域に絞り込むには、コンプライアンス マネージャー管理者の[ソリューション] タブでアクションの種類別にフィルター処理できます。コンプライアンス マネージャー ダッシュボード[ビューのフィルター処理について詳しくは、次のページをご覧ください](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)。</span><span class="sxs-lookup"><span data-stu-id="35ee0-156">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Manager admin. Learn more about [filtering your Compliance Manager dashboard view](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).</span></span>

- <span data-ttu-id="35ee0-157">コンプライアンス マネージャーで特定された改善アクションの相対的な重要性と優先度は、組織が管理する必要があるデータ プライバシー リスクと共に、より広範なリスク レビューの一環として考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35ee0-157">The relative importance and priority of improvement actions identified in Compliance Manager should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span>

- <span data-ttu-id="35ee0-158">複数の規制要件で改善アクションが集約されている場合でも、GDPR、LGPD、CCPA、HIPAA-HITECH の規制評価テンプレートが選択されている場合は、コンプライアンス マネージャーに約 400 件の改善アクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35ee0-158">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Manager.</span></span> <span data-ttu-id="35ee0-159">この長いリストに対処するには、改善アクション フィルターを使用して、結果セットをより管理可能なリストに減らします。</span><span class="sxs-lookup"><span data-stu-id="35ee0-159">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="35ee0-160">カテゴリ フィルターは、このソリューション全体の記事を追跡、防止、保護、保持、および調査する論理グループ化によって改善アクションをフィルター処理する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="35ee0-160">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span>

- <span data-ttu-id="35ee0-161">改善アクションに記載されている一部のコントロールは、特定の規制記事に直接関連付けられていると見なされる場合があります。他のコントロールは、規制の精神に間接的に関連付けられる可能性があります。多くの場合は、単に推奨されるアクティビティまたはベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="35ee0-161">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and many times are simply recommended activities or best practices.</span></span>