---
title: データ損失防止の計画
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: データ損失防止の計画プロセスの概要
ms.openlocfilehash: 84f1dc0426ba88f934c1d67d71f75364adeb4340
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583354"
---
# <a name="plan-for-data-loss-prevention-dlp"></a><span data-ttu-id="088df-103">データ損失防止 (DLP) の計画</span><span class="sxs-lookup"><span data-stu-id="088df-103">Plan for data loss prevention (DLP)</span></span>

<span data-ttu-id="088df-104">すべての組織がデータ損失防止 (DLP) の計画と実装を異なる方法で行うのは、すべての組織のビジネス ニーズ、目標、リソース、および状況が固有のためです。</span><span class="sxs-lookup"><span data-stu-id="088df-104">Every organization will plan for and implement data loss prevention (DLP) differently, because every organization's business needs, goals, resources, and situation are unique to them.</span></span> <span data-ttu-id="088df-105">ただし、すべての成功した DLP 実装に共通する要素があります。</span><span class="sxs-lookup"><span data-stu-id="088df-105">However, there are elements that are common to all successful DLP implementations.</span></span> <span data-ttu-id="088df-106">この記事では、DLP 計画で組織が使用するベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="088df-106">This article presents the best practices that are used by organizations in their DLP planning.</span></span>

## <a name="multiple-starting-points"></a><span data-ttu-id="088df-107">複数の開始点</span><span class="sxs-lookup"><span data-stu-id="088df-107">Multiple starting points</span></span>

<span data-ttu-id="088df-108">多くの組織は、さまざまな政府または業界の規制に準拠するために DLP を実装する選択をしています。</span><span class="sxs-lookup"><span data-stu-id="088df-108">Many organizations choose to implement DLP to comply with various governmental or industry regulations.</span></span> <span data-ttu-id="088df-109">たとえば、欧州連合の一般データ保護規則 (GDPR)、健康保険の移植性と説明責任法 (HIPAA)、またはカリフォルニア州消費者プライバシー法 (CCPA) などです。</span><span class="sxs-lookup"><span data-stu-id="088df-109">For example, the European Union's General Data Protection Regulation (GDPR), or the Health Insurance Portability and Accountability Act (HIPAA), or the California Consumer Privacy Act (CCPA).</span></span> <span data-ttu-id="088df-110">また、データ損失防止を実装して知的財産を保護します。</span><span class="sxs-lookup"><span data-stu-id="088df-110">They also implement data loss prevention to protect their intellectual property.</span></span> <span data-ttu-id="088df-111">ただし、DLP ジャーニーの開始場所と最終的な宛先は異なります。</span><span class="sxs-lookup"><span data-stu-id="088df-111">But the starting place and ultimate destination in the DLP journey vary.</span></span> 

<span data-ttu-id="088df-112">組織は DLP ジャーニーを開始できます。</span><span class="sxs-lookup"><span data-stu-id="088df-112">Organizations can start their DLP journey:</span></span>

- <span data-ttu-id="088df-113">チャットメッセージやチャネル メッセージ、またはデバイス上の情報Teams保護する場合など、プラットフォームWindows 10。</span><span class="sxs-lookup"><span data-stu-id="088df-113">from a platform focus, like wanting to protect information in Teams Chat and Channel messages or on Windows 10 devices</span></span>
- <span data-ttu-id="088df-114">医療記録などの保護に優先順位を付ける機密情報を知り、それを保護するためのポリシーの定義に直行する</span><span class="sxs-lookup"><span data-stu-id="088df-114">knowing what sensitive information they want to prioritize protecting, like health care records, and going straight to defining policies to protect it</span></span>
- <span data-ttu-id="088df-115">機密情報が何か、どこにいて、誰が何をしているのかを知らずに、発見と分類から始め、より方法的なアプローチを取る</span><span class="sxs-lookup"><span data-stu-id="088df-115">without knowing what their sensitive information is, where it is, and who is doing what with it so they start with discovery and categorization and take a more methodical approach</span></span>
- <span data-ttu-id="088df-116">機密情報が何か、どこにいるのか、誰が何をしているのかを知らずに、ポリシーの定義に直接移行し、その結果を開始場所として使用し、そこからポリシーを絞り込む</span><span class="sxs-lookup"><span data-stu-id="088df-116">without knowing what their sensitive information is, or where it is, or who is doing what with it, but they will move straight to defining policies and use those outcomes as a starting place and then refine their policies from there</span></span>
- <span data-ttu-id="088df-117">情報保護スタック全体を実装する必要Microsoft 365、より長期的で方法的なアプローチを取るつもり</span><span class="sxs-lookup"><span data-stu-id="088df-117">knowing that they need to implement the full Microsoft 365 Information Protection stack and so intend to take a longer term, methodical approach</span></span>

<span data-ttu-id="088df-118">これらは、お客様が DLP にアプローチする方法のほんの一部の例であり、どこから始めても問題ありません。Microsoft 365 DLP は、さまざまな種類の情報保護の手順を最初から完全に実現されたデータ損失防止戦略に対応するのに十分な柔軟性を備えています。</span><span class="sxs-lookup"><span data-stu-id="088df-118">These are just some examples of how customers can approach DLP and it doesn't matter where you start from, Microsoft 365 DLP is flexible enough to accommodate various types of information protection journeys from start to a fully realized data loss prevention strategy.</span></span> 

## <a name="overview-of-planning-process"></a><span data-ttu-id="088df-119">計画プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="088df-119">Overview of planning process</span></span>

<span data-ttu-id="088df-120">「 [データ損失防止について」では、DLP](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) 計画プロセスの 3 つの異なる側面 [について説明します](dlp-learn-about-dlp.md#plan-for-dlp)。</span><span class="sxs-lookup"><span data-stu-id="088df-120">The [Learn about data loss prevention](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) introduces the three different aspects of the [DLP planning process](dlp-learn-about-dlp.md#plan-for-dlp).</span></span> <span data-ttu-id="088df-121">ここでは、すべての DLP プランに共通する要素について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="088df-121">We'll go into more detail here on the elements that are common to all DLP plans.</span></span>

### <a name="identify-stakeholders"></a><span data-ttu-id="088df-122">関係者の特定</span><span class="sxs-lookup"><span data-stu-id="088df-122">Identify stakeholders</span></span>

<span data-ttu-id="088df-123">実装すると、組織の大部分で DLP ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="088df-123">When implemented, DLP policies can be applied across large portions of your organization.</span></span> <span data-ttu-id="088df-124">IT では、否定的な結果が生じることなく、広範囲にわたる計画を独自に開発できない。</span><span class="sxs-lookup"><span data-stu-id="088df-124">IT can't develop a broad ranging plan on their own without negative consequences.</span></span> <span data-ttu-id="088df-125">以下を実行できる関係者を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-125">You need to identify the stakeholders who can:</span></span>

- <span data-ttu-id="088df-126">組織が対象となる規制、法律、および業界標準について説明する</span><span class="sxs-lookup"><span data-stu-id="088df-126">describe the regulations, laws, and industry standards your organization is subject to</span></span>
- <span data-ttu-id="088df-127">保護する機密アイテムのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="088df-127">the categories of sensitive items to be protected</span></span>
- <span data-ttu-id="088df-128">で使用されるビジネス プロセス</span><span class="sxs-lookup"><span data-stu-id="088df-128">the business processes they are used in</span></span>
- <span data-ttu-id="088df-129">制限する必要があるリスクの高い動作</span><span class="sxs-lookup"><span data-stu-id="088df-129">the risky behavior that should be limited</span></span>
- <span data-ttu-id="088df-130">アイテムの感度と関連するリスクに基づいて、最初に保護するデータに優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="088df-130">prioritize which data should be protected first based on the sensitivity of the items and risk involved</span></span>
- <span data-ttu-id="088df-131">DLP ポリシー一致イベントのレビューと修復プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="088df-131">outline the DLP policy match event review and remediation process</span></span> 
 
<span data-ttu-id="088df-132">一般に、これらのニーズは 85% の規制とコンプライアンス保護、および 15% の知的財産保護である傾向があります。</span><span class="sxs-lookup"><span data-stu-id="088df-132">In general these needs tend to be 85% regulatory and compliance protection, and 15% intellectual property protection.</span></span> <span data-ttu-id="088df-133">計画プロセスに含める役割に関する提案を次に示します。</span><span class="sxs-lookup"><span data-stu-id="088df-133">Here are some suggestions on roles to include in your planning process:</span></span>

- <span data-ttu-id="088df-134">規制およびコンプライアンス担当者</span><span class="sxs-lookup"><span data-stu-id="088df-134">Regulatory and compliance officers</span></span>
- <span data-ttu-id="088df-135">最高リスク責任者</span><span class="sxs-lookup"><span data-stu-id="088df-135">Chief risk officer</span></span>
- <span data-ttu-id="088df-136">法務担当者</span><span class="sxs-lookup"><span data-stu-id="088df-136">Legal officers</span></span>
- <span data-ttu-id="088df-137">セキュリティおよびコンプライアンス担当者</span><span class="sxs-lookup"><span data-stu-id="088df-137">Security and compliance officers</span></span>
- <span data-ttu-id="088df-138">データ アイテムのビジネス所有者</span><span class="sxs-lookup"><span data-stu-id="088df-138">Business owners for the data items</span></span>
- <span data-ttu-id="088df-139">ビジネス ユーザー</span><span class="sxs-lookup"><span data-stu-id="088df-139">Business users</span></span>
- <span data-ttu-id="088df-140">IT</span><span class="sxs-lookup"><span data-stu-id="088df-140">IT</span></span>

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a><span data-ttu-id="088df-141">保護する機密情報のカテゴリを説明する</span><span class="sxs-lookup"><span data-stu-id="088df-141">Describe the categories of sensitive information to protect</span></span>

<span data-ttu-id="088df-142">その後、関係者は、保護する機密情報のカテゴリと、その中で使用されるビジネス プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="088df-142">The stakeholders then describe the categories of sensitive information to be protected and the business process that they're used in.</span></span> <span data-ttu-id="088df-143">たとえば、次のMicrosoft 365 DLP によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="088df-143">For example, Microsoft 365 DLP defines these categories:</span></span>

- <span data-ttu-id="088df-144">財務</span><span class="sxs-lookup"><span data-stu-id="088df-144">Financial</span></span> 
- <span data-ttu-id="088df-145">医療と健康に関する情報</span><span class="sxs-lookup"><span data-stu-id="088df-145">Medical and health information</span></span>
- <span data-ttu-id="088df-146">プライバシー</span><span class="sxs-lookup"><span data-stu-id="088df-146">Privacy</span></span>
- <span data-ttu-id="088df-147">Custom</span><span class="sxs-lookup"><span data-stu-id="088df-147">Custom</span></span>

<span data-ttu-id="088df-148">関係者は機密情報を「データ 処理者なので、データ主体情報と財務情報に対するプライバシー保護を実装する必要がある」と識別する場合があります。</span><span class="sxs-lookup"><span data-stu-id="088df-148">The stakeholders might identify the sensitive information as "We are a data processor, so we have to implement privacy protections on data subject information and financial information".</span></span>

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a><span data-ttu-id="088df-149">目標と戦略を設定する</span><span class="sxs-lookup"><span data-stu-id="088df-149">Set goals and strategy</span></span>

<span data-ttu-id="088df-150">利害関係者を特定し、保護が必要な機密情報とその使用場所を知った後、関係者は保護目標を設定し、IT は実装計画を策定できます。</span><span class="sxs-lookup"><span data-stu-id="088df-150">Once you have identified your stakeholders and you know which sensitive information needs protection and where it's used, the stakeholders can set their protection goals and IT can develop an implementation plan.</span></span> 


 <!--
### Discovery
 for the locations (DLP workloads) of these types of items.  (mapping DLP locations and data at rest, data in transit, data in use)

### IT can start coding test policies
start small and always in test mode. Note that DLP policies can feed into insider risk.

### Business process owners help with tuning
 false positive/false negative results and fitting DLP into their business processes.

-->

### <a name="set-implementation-plan"></a><span data-ttu-id="088df-151">実装計画の設定</span><span class="sxs-lookup"><span data-stu-id="088df-151">Set implementation plan</span></span>

<span data-ttu-id="088df-152">実装計画には、次のものが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-152">Your implementation plan should include:</span></span>

- <span data-ttu-id="088df-153">開始状態と目的の終了状態、および 1 から別の状態に取得する手順をマッピングする</span><span class="sxs-lookup"><span data-stu-id="088df-153">Mapping out your starting state and desired end state and the steps to get from one to the other</span></span>
- <span data-ttu-id="088df-154">機密性の高いアイテムの検出に対処する方法</span><span class="sxs-lookup"><span data-stu-id="088df-154">how you will address discovery of sensitive items</span></span>
- <span data-ttu-id="088df-155">ポリシーの計画と、ポリシーが実装される順序</span><span class="sxs-lookup"><span data-stu-id="088df-155">policy planning and the order that they will be implemented</span></span>
- <span data-ttu-id="088df-156">前提条件に対処する方法</span><span class="sxs-lookup"><span data-stu-id="088df-156">how you will address any prerequisites</span></span>
- <span data-ttu-id="088df-157">適用に移行する前にポリシーを最初にテストする方法を計画する</span><span class="sxs-lookup"><span data-stu-id="088df-157">planning on how policies will first be tested before moving to enforcement</span></span>
- <span data-ttu-id="088df-158">エンド ユーザーのトレーニング方法</span><span class="sxs-lookup"><span data-stu-id="088df-158">how you will train your end users</span></span>
- <span data-ttu-id="088df-159">ポリシーのテストと調整方法</span><span class="sxs-lookup"><span data-stu-id="088df-159">how you will test and tune your policies</span></span>
- <span data-ttu-id="088df-160">変化する規制、法律、業界標準、または知的財産保護およびビジネス ニーズに基づいて、データ損失防止戦略を確認および更新する方法</span><span class="sxs-lookup"><span data-stu-id="088df-160">how you will review and update your data loss prevention strategy based on changing regulatory, legal, industry standard or intellectual property protection and business needs</span></span>

#### <a name="map-out-path-from-start-to-desired-end-state"></a><span data-ttu-id="088df-161">開始から目的の終了状態へのパスをマップする</span><span class="sxs-lookup"><span data-stu-id="088df-161">Map out path from start to desired end state</span></span>

<span data-ttu-id="088df-162">組織の開始状態から目的の終了状態への取得方法を文書化することが、関係者とのコミュニケーションとプロジェクトスコープの設定に不可欠です。</span><span class="sxs-lookup"><span data-stu-id="088df-162">Documenting how your organization is going to get from its starting state to the desired end state is essential to communicating with your stakeholders and setting the project scope.</span></span> <span data-ttu-id="088df-163">DLP の展開に一般的に使用される一連の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="088df-163">Here is a set of steps that are commonly used to deploy DLP.</span></span> <span data-ttu-id="088df-164">これよりも詳細な情報が必要になりますが、これを使用して DLP 導入パスをフレーム化できます。</span><span class="sxs-lookup"><span data-stu-id="088df-164">You'll want more detail than this, but you can use this to frame your DLP adoption path.</span></span>

![DLP を展開する一般的な順序を示す図](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a><span data-ttu-id="088df-166">機密性の高いアイテムの検出</span><span class="sxs-lookup"><span data-stu-id="088df-166">Sensitive item discovery</span></span>

<span data-ttu-id="088df-167">個々の機密性の高いアイテムの場所と場所を検出するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="088df-167">There are multiple ways to discover what individual sensitive items are and where they are located.</span></span> <span data-ttu-id="088df-168">感度ラベルが既に展開されている場合や、アイテムのみを検出して監査する場所に広範な DLP ポリシーを展開することを決定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="088df-168">You may have sensitivity labels already deployed or you may have decided to deploy a broad DLP policy to all locations that only discovers and audits items.</span></span> <span data-ttu-id="088df-169">詳細については、「データを知 [る」を参照してください](information-protection.md#know-your-data)。</span><span class="sxs-lookup"><span data-stu-id="088df-169">To learn more, see [Know your data](information-protection.md#know-your-data).</span></span>

#### <a name="policy-planning"></a><span data-ttu-id="088df-170">ポリシー計画</span><span class="sxs-lookup"><span data-stu-id="088df-170">Policy planning</span></span>

<span data-ttu-id="088df-171">DLP の導入を開始すると、これらの質問を使用して、ポリシーの設計と実装の取り組みを集中できます。</span><span class="sxs-lookup"><span data-stu-id="088df-171">As you begin your DLP adoption, you can use these questions to focus your policy design and implementation efforts.</span></span>

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a><span data-ttu-id="088df-172">組織が遵守する必要がある法律、規制、業界標準は何ですか?</span><span class="sxs-lookup"><span data-stu-id="088df-172">What laws, regulations and industry standards must your organization comply with?</span></span>

<span data-ttu-id="088df-173">多くの組織が規制コンプライアンスを目標に DLP に参加しています。この質問に答えるのは、DLP の実装を計画する際の自然な開始点です。</span><span class="sxs-lookup"><span data-stu-id="088df-173">Because many organizations come to DLP with the goal of regulatory compliance, answering this question is a natural starting place for planning your DLP implementation.</span></span> <span data-ttu-id="088df-174">ただし、IT 実装者として、回答する立場にはない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="088df-174">But, as the IT implementer, you're probably not positioned to answer it.</span></span> <span data-ttu-id="088df-175">法務チームとビジネスエグゼクティブが回答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-175">It needs to be answered by your legal team and business executives.</span></span> 
 
<span data-ttu-id="088df-176">**例** 組織は英国の対象です。</span><span class="sxs-lookup"><span data-stu-id="088df-176">**Example** Your organization is subject to U.K.</span></span> <span data-ttu-id="088df-177">金融規制。</span><span class="sxs-lookup"><span data-stu-id="088df-177">financial regulations.</span></span>


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a><span data-ttu-id="088df-178">漏えいから保護する必要がある機密性の高いアイテムは何ですか?</span><span class="sxs-lookup"><span data-stu-id="088df-178">What sensitive items does your organization have that must be protected from leakage?</span></span>

<span data-ttu-id="088df-179">規制コンプライアンスニーズの観点から組織がどこに立つかが分かったら、機密アイテムを漏洩から保護する必要があるもの、およびそれらを保護するためにポリシーの実装を優先順位付けする方法について、いくつかのアイデアを得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-179">Once your organization knows where it stands in terms of regulatory compliance needs, you'll have some idea of what sensitive items need to be protected from leakage and how you want to prioritize policy implementation to protect them.</span></span> <span data-ttu-id="088df-180">これにより、最も適切な DLP ポリシー テンプレートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="088df-180">This will help you choose the most appropriate DLP policy templates.</span></span> <span data-ttu-id="088df-181">Microsoft 365、財務、医療、健康、プライバシー用に事前に構成された DLP テンプレートが付属し、カスタム テンプレートを使用して独自のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="088df-181">Microsoft 365 comes with pre-configured DLP templates for Financial, Medical and health, Privacy, and you can build your own using the Custom template.</span></span> <span data-ttu-id="088df-182">実際の DLP ポリシーを設計して作成する場合、この質問に対する答えを知ることにより、適切な機密情報の種類を選 [ぶのにも役立ちます](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)。</span><span class="sxs-lookup"><span data-stu-id="088df-182">As you design and create your actual DLP policies, knowing the answer to this question will also help you choose the right [sensitive information type](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types).</span></span>

<span data-ttu-id="088df-183">**例** すぐに始めるには、ポリシー テンプレート (、機密情報の種類を含む `U.K. Financial Data` `Credit Card Number` ) `EU Debit Card Number` `SWIFT Code` を選択します。</span><span class="sxs-lookup"><span data-stu-id="088df-183">**Example** To get started quickly, you pick the `U.K. Financial Data` policy template, which includes the `Credit Card Number`, `EU Debit Card Number`, and `SWIFT Code` sensitive information types.</span></span> 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a><span data-ttu-id="088df-184">機密性の高いアイテムと、どのビジネス プロセスに関わっているか。</span><span class="sxs-lookup"><span data-stu-id="088df-184">Where are the sensitive items and what business processes are they involved in?</span></span>

<span data-ttu-id="088df-185">組織の機密情報を含むアイテムは、ビジネスの過程で毎日使用されます。</span><span class="sxs-lookup"><span data-stu-id="088df-185">The items that contain your organizations sensitive information are used every day in the course of doing business.</span></span> <span data-ttu-id="088df-186">その機密情報のインスタンスがどこで発生する可能性があるのか、どのビジネス プロセスで使用されるのかを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-186">You need to know where instances of that sensitive information may occur and what business processes they are used in.</span></span> <span data-ttu-id="088df-187">これにより、DLP ポリシーを適用する適切な場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="088df-187">This will help you choose the right locations to apply your DLP policies to.</span></span> <span data-ttu-id="088df-188">Microsoft 365DLP ポリシーは場所に適用されます。</span><span class="sxs-lookup"><span data-stu-id="088df-188">Microsoft 365 DLP policies are applied to locations:</span></span>

- <span data-ttu-id="088df-189">Exchange メール</span><span class="sxs-lookup"><span data-stu-id="088df-189">Exchange email</span></span>
- <span data-ttu-id="088df-190">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="088df-190">SharePoint sites</span></span>
- <span data-ttu-id="088df-191">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="088df-191">OneDrive accounts</span></span>
- <span data-ttu-id="088df-192">Teams チャットおよびチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="088df-192">Teams chat and channel messages</span></span>
- <span data-ttu-id="088df-193">Windows 10デバイス</span><span class="sxs-lookup"><span data-stu-id="088df-193">Windows 10 Devices</span></span>
- <span data-ttu-id="088df-194">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="088df-194">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="088df-195">オンプレミス リポジトリ</span><span class="sxs-lookup"><span data-stu-id="088df-195">On-premises repositories</span></span>

<span data-ttu-id="088df-196">**例** 組織の内部監査人は、一連のクレジット カード番号を追跡しています。</span><span class="sxs-lookup"><span data-stu-id="088df-196">**Example** Your organizations' internal auditors are tracking a set of credit card numbers.</span></span> <span data-ttu-id="088df-197">これらのスプレッドシートは、セキュリティで保護されたサイトSharePointします。</span><span class="sxs-lookup"><span data-stu-id="088df-197">They keep a spreadsheet of them in a secure SharePoint site.</span></span> <span data-ttu-id="088df-198">従業員の中には、コピーを作成し、自分のサイトOneDrive for Businessに保存します。これは、ユーザーのデバイスWindows 10されます。</span><span class="sxs-lookup"><span data-stu-id="088df-198">Several of the employees make copies and save them to their work OneDrive for Business site, which is synced to their Windows 10 device.</span></span> <span data-ttu-id="088df-199">そのうちの 1 つは、そのうち 14 件のリストをメールに貼り付け、外部監査人に送信してレビューを行います。</span><span class="sxs-lookup"><span data-stu-id="088df-199">One of them pastes a list of 14 of them in an email and tries to send it to the outside auditors for review.</span></span> <span data-ttu-id="088df-200">セキュリティで保護された SharePoint サイト、すべての内部監査人 OneDrive for Business アカウント、Windows 10 デバイス、および電子メールExchangeします。</span><span class="sxs-lookup"><span data-stu-id="088df-200">You'd want to apply the policy to the secure SharePoint site, all the internal auditors OneDrive for Business accounts, their Windows 10 devices, and Exchange email.</span></span>

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a><span data-ttu-id="088df-201">漏えいに対する組織の許容度は何ですか?</span><span class="sxs-lookup"><span data-stu-id="088df-201">What is your organizations tolerance for leakage?</span></span>

<span data-ttu-id="088df-202">組織内の異なるグループは、機密性の高いアイテム漏洩の許容レベルとそうではないものについて異なる見解を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="088df-202">Different groups in your organization may have different views on what's an acceptable level of sensitive item leakage and what's not.</span></span> <span data-ttu-id="088df-203">漏えいゼロの完成度を達成すると、ビジネスに大きなコストがかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="088df-203">Achieving the perfection of zero leakage may come at too high a cost to the business.</span></span>

<span data-ttu-id="088df-204">**例** 組織のセキュリティ グループは、法務チームと共に、組織外のユーザーとクレジット カード番号を共有し、漏洩ゼロを主張する必要はないと感じます。</span><span class="sxs-lookup"><span data-stu-id="088df-204">**Example** Your organizations' security group, along with the legal team both feel that there should be no sharing of credit card numbers with anyone outside the org and insist on zero leakage.</span></span> <span data-ttu-id="088df-205">ただし、クレジット カード番号アクティビティの定期的なレビューの一環として、内部監査人は、いくつかのクレジット カード番号をサードパーティの監査人と共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-205">But, as part of regular review of credit card number activity, the internal auditors must share some credit card numbers with third-party auditors.</span></span> <span data-ttu-id="088df-206">DLP ポリシーで組織外でのクレジット カード番号の共有が禁止されている場合は、社内監査人が追跡を完了するために、業務プロセスが大幅に中断され、中断を軽減するためのコストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="088df-206">If your DLP policy prohibits all sharing of credit card numbers outside the org, there will be a significant business process disruption and added cost to mitigate the disruption in order for the internal auditors to complete their tracking.</span></span> <span data-ttu-id="088df-207">この余分なコストは、エグゼクティブ リーダーシップには受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="088df-207">This extra cost is unacceptable to the executive leadership.</span></span> <span data-ttu-id="088df-208">これを解決するには、許容可能なレベルの漏洩を決定するための内部会話が必要です。</span><span class="sxs-lookup"><span data-stu-id="088df-208">To resolve this, there needs to be an internal conversation to decide an acceptable level of leakage.</span></span> <span data-ttu-id="088df-209">ポリシーが決定されると、特定の個人が情報を共有する例外を提供するか、監査のみモードで適用できます。</span><span class="sxs-lookup"><span data-stu-id="088df-209">Once that is decided the policy can provide exceptions for certain individuals to share the information or it can be applied in audit only mode.</span></span>

#### <a name="planning-for-prerequisites"></a><span data-ttu-id="088df-210">前提条件の計画</span><span class="sxs-lookup"><span data-stu-id="088df-210">Planning for prerequisites</span></span>

<span data-ttu-id="088df-211">DLP の場所を監視する前に、満たす必要がある前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="088df-211">Before you can monitor some DLP locations, there are prerequisites that must be met.</span></span> <span data-ttu-id="088df-212">「開始 **する前に」のセクション** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="088df-212">See the **Before you begin** sections of:</span></span>

- [<span data-ttu-id="088df-213">データ損失防止のオンプレミス スキャナー (プレビュー) を開始する</span><span class="sxs-lookup"><span data-stu-id="088df-213">Get started with the data loss prevention on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [<span data-ttu-id="088df-214">エンドポイント データ損失防止の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="088df-214">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md#before-you-begin)
- [<span data-ttu-id="088df-215">Microsoft コンプライアンス拡張機能の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="088df-215">Get started with the Microsoft compliance extension (preview)</span></span>](dlp-chrome-get-started.md#before-you-begin)
- [<span data-ttu-id="088df-216">Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="088df-216">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a><span data-ttu-id="088df-217">ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="088df-217">Policy deployment</span></span>

<span data-ttu-id="088df-218">DLP ポリシーを作成するときは、完全に適用する前に、影響を評価し、有効性をテストしながら、段階的に展開することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-218">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="088df-219">たとえば、新しい DLP ポリシーが何千ものドキュメントへのアクセスを意図せずにブロックしたり、既存のビジネス プロセスを壊したりしたくないとします。</span><span class="sxs-lookup"><span data-stu-id="088df-219">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents or to break an existing business process.</span></span>
  
<span data-ttu-id="088df-220">大きな影響を与える可能性が高い DLP ポリシーを作成している場合は、次の順序に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="088df-220">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="088df-221">**ポリシー ヒントなしのテスト モードで開始** し、DLP レポートとインシデント レポートを使用して、影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="088df-221">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="088df-222">DLP レポートを使用すると、ポリシー一致の回数、場所、種類、および重要度を把握できます。</span><span class="sxs-lookup"><span data-stu-id="088df-222">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="088df-223">結果に基づいて、必要に応じてポリシーを微調整できます。</span><span class="sxs-lookup"><span data-stu-id="088df-223">Based on the results, you can fine-tune the policies as needed.</span></span> <span data-ttu-id="088df-224">テスト モードでは、DLP ポリシーは組織で業務に取り組んでいるユーザーの生産性に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="088df-224">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> <span data-ttu-id="088df-225">また、このステージを使用して、DLP イベントのレビューと問題の修復のためのワークフローをテストします。</span><span class="sxs-lookup"><span data-stu-id="088df-225">Also, use this stage to test out your workflow for DLP event review and issue remediation.</span></span>
    
2. <span data-ttu-id="088df-226">**通知とポリシー ヒント** を使用してテスト モードに移行し、コンプライアンス ポリシーについてユーザーに教え始め、適用するポリシーの準備を開始できます。</span><span class="sxs-lookup"><span data-stu-id="088df-226">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the policies that are going to be applied.</span></span> <span data-ttu-id="088df-227">ポリシー ヒントでポリシーの詳細を示す組織のポリシー ページへのリンクを作成すると便利です。</span><span class="sxs-lookup"><span data-stu-id="088df-227">It's useful to have a link to an organization policy page that provides more details about the policy in the policy tip.</span></span> <span data-ttu-id="088df-228">この段階では、ユーザーに誤検知の報告を求め、ポリシーをさらに絞り込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-228">At this stage, you can also ask users to report false positives so that you can further refine the policies.</span></span> <span data-ttu-id="088df-229">ポリシー アプリケーションの結果が、関係者が念頭に置いた結果と一致する自信が得られたら、この段階に進む。</span><span class="sxs-lookup"><span data-stu-id="088df-229">Move to this stage once you have confidence that the results of policy application match what they stakeholders had in mind.</span></span> 
    
3. <span data-ttu-id="088df-230">**ポリシーの完全な適用を開始** し、ルールのアクションが適用され、コンテンツが保護されるようにします。</span><span class="sxs-lookup"><span data-stu-id="088df-230">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="088df-231">DLP レポートやインシデント レポート、通知を引き続き監視して、結果が計画どおりであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="088df-231">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 

    ![テスト モードを使用しポリシーで有効化するオプション](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    <span data-ttu-id="088df-233">いつでも DLP ポリシーを無効にできます。ポリシーのすべてのルールに反映されます。</span><span class="sxs-lookup"><span data-stu-id="088df-233">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="088df-234">ただし、ルール エディターで状態を切り替えることで、各ルールを個別に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="088df-234">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>

    ![ポリシー内のルールを無効にするオプション](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    <span data-ttu-id="088df-236">ポリシー内の複数のルールの優先順位を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="088df-236">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="088df-237">変更するには、編集のためのポリシーを開きます。</span><span class="sxs-lookup"><span data-stu-id="088df-237">To do that, open a policy for editing.</span></span> <span data-ttu-id="088df-238">ルールの行では、省略記号 (**...**) を選択し、[**下へ移動**] または [**最後へ移動**] などのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="088df-238">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

    ![ルールの優先順位を設定する](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a><span data-ttu-id="088df-240">エンド ユーザー トレーニング</span><span class="sxs-lookup"><span data-stu-id="088df-240">End-user training</span></span>

<span data-ttu-id="088df-241">DLP ポリシーがトリガーされると、ポリシーを構成して、電子メール通知を送信し [、DLP](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) ポリシーのポリシー ヒントを管理者およびエンド ユーザーに表示できます。</span><span class="sxs-lookup"><span data-stu-id="088df-241">When a DLP policy is triggered, you can configure your policies to [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) to admins and end users.</span></span> <span data-ttu-id="088df-242">ポリシーがまだテスト モードであり、ブロックアクションを適用する前にポリシーヒントを使用すると、機密性の高いアイテムに対するリスクの高い動作に対する認識を高め、ユーザーが将来これらの動作を回避するためのトレーニングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="088df-242">While your policies are still in test mode and before they are set to enforce a blocking action, policy tips are useful ways to raise awareness of risky behaviors on sensitive items and train users to avoid those behaviors in the future.</span></span>  

#### <a name="review-dlp-requirements-and-update-strategy"></a><span data-ttu-id="088df-243">DLP 要件と更新戦略を確認する</span><span class="sxs-lookup"><span data-stu-id="088df-243">Review DLP requirements and update strategy</span></span>

<span data-ttu-id="088df-244">組織が適用される規制、法律、業界標準は、時間の間に変化し、DLP のビジネス目標も変わります。</span><span class="sxs-lookup"><span data-stu-id="088df-244">The regulations, laws, and industry standards that your organization is subject to will change over time and your business goals for DLP will too.</span></span> <span data-ttu-id="088df-245">組織がコンプライアンスを遵守し、DLP の実装が引き続きビジネス ニーズを満たし続けるので、これらすべての分野の定期的なレビューを必ず含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-245">Be sure to include regular reviews of all these areas so that your organization stays in compliance and your DLP implementation continues to meet your business needs.</span></span>

## <a name="approaches-to-deployment"></a><span data-ttu-id="088df-246">展開へのアプローチ</span><span class="sxs-lookup"><span data-stu-id="088df-246">Approaches to deployment</span></span>

|<span data-ttu-id="088df-247">顧客のビジネス ニーズの説明</span><span class="sxs-lookup"><span data-stu-id="088df-247">Customer business needs description</span></span>  | <span data-ttu-id="088df-248">アプローチ</span><span class="sxs-lookup"><span data-stu-id="088df-248">approach</span></span>  |
|---------|---------|
|<span data-ttu-id="088df-249">**Contoso Bank** は規制の厳しい業界にいて、さまざまな場所にさまざまな種類の機密性の高いアイテムがあります。</span><span class="sxs-lookup"><span data-stu-id="088df-249">**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations.</span></span> </br> <span data-ttu-id="088df-250">- どの種類の機密情報が最優先事項かを知っています。</span><span class="sxs-lookup"><span data-stu-id="088df-250">- knows which types of sensitive information are top priority.</span></span> </br> <span data-ttu-id="088df-251">- ポリシーが展開される場合、ビジネスの中断を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-251">- must minimize business disruption as policies are rolled out.</span></span> </br> <span data-ttu-id="088df-252">- IT リソースを持ち、専門家を雇って計画、設計の展開を支援できます</span><span class="sxs-lookup"><span data-stu-id="088df-252">-  has IT resources and can hire experts to help plan, design deploy</span></span> </br> <span data-ttu-id="088df-253">- Microsoft とプレミア サポート契約を結んだ</span><span class="sxs-lookup"><span data-stu-id="088df-253">- has a premier support contract with Microsoft</span></span>| <span data-ttu-id="088df-254">- 時間を取って、遵守する必要がある規制と準拠する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="088df-254">- Take the time to understand what regulations they must comply with and how they are going to comply.</span></span> </br> <span data-ttu-id="088df-255">-時間を取って、情報保護スタックのMicrosoft 365理解する</span><span class="sxs-lookup"><span data-stu-id="088df-255">-Take the time to understand the better together value of the Microsoft 365 Information Protection stack</span></span> </br> <span data-ttu-id="088df-256">- 優先順位付けされたアイテムの感度ラベル付けスキームを開発し、適用する</span><span class="sxs-lookup"><span data-stu-id="088df-256">- Develop sensitivity labeling scheme for prioritized items and apply</span></span> </br> <span data-ttu-id="088df-257">- ビジネス プロセスの所有者を巻き込む</span><span class="sxs-lookup"><span data-stu-id="088df-257">- Involve business process owners</span></span> </br><span data-ttu-id="088df-258">- デザイン/コード ポリシー、テスト モードでの展開、ユーザーのトレーニング</span><span class="sxs-lookup"><span data-stu-id="088df-258">- Design/code policies, deploy in test mode, train users</span></span> </br><span data-ttu-id="088df-259">- 繰り返し</span><span class="sxs-lookup"><span data-stu-id="088df-259">- repeat</span></span>|
|<span data-ttu-id="088df-260">**TailSpin Toys** は、自分の持っているものや場所を知らないので、リソースの深さはほとんどない。</span><span class="sxs-lookup"><span data-stu-id="088df-260">**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth.</span></span> <span data-ttu-id="088df-261">これらのユーザーは、Teams、OneDrive for Business、Exchangeを使用します。</span><span class="sxs-lookup"><span data-stu-id="088df-261">They use Teams, OneDrive for Business and Exchange extensively.</span></span>     |<span data-ttu-id="088df-262">- 優先順位付けされた場所の簡単なポリシーから開始します。</span><span class="sxs-lookup"><span data-stu-id="088df-262">- Start with simple policies on the prioritized locations.</span></span> </br><span data-ttu-id="088df-263">- 識別される情報を監視する</span><span class="sxs-lookup"><span data-stu-id="088df-263">- Monitor what gets identified</span></span> </br><span data-ttu-id="088df-264">- 必要に応じて感度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="088df-264">- Apply sensitivity labels accordingly</span></span> </br><span data-ttu-id="088df-265">- ポリシーの絞り込み、ユーザーのトレーニング</span><span class="sxs-lookup"><span data-stu-id="088df-265">- Refine policies, train users</span></span>       |
|<span data-ttu-id="088df-266">**Fabrikam は** 小規模なスタートアップであり、知的財産を保護したいと考え、迅速に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="088df-266">**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly.</span></span> <span data-ttu-id="088df-267">彼らは一部のリソースを提供する気があるが、外部の専門家を雇う余裕はない。</span><span class="sxs-lookup"><span data-stu-id="088df-267">They are willing to dedicate some resources, but can't afford to hire outside experts.</span></span> </br><span data-ttu-id="088df-268">- 機密性の高いアイテムはすべてMicrosoft 365 OneDrive for Business/SharePoint</span><span class="sxs-lookup"><span data-stu-id="088df-268">- Sensitive items are all in Microsoft 365 OneDrive for Business/SharePoint</span></span> </br><span data-ttu-id="088df-269">- アイテムのOneDrive for BusinessとSharePoint採用が遅い、従業員/シャドウ IT は DropBox と Google ドライブを使用してアイテムを共有/保存する</span><span class="sxs-lookup"><span data-stu-id="088df-269">- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items</span></span> </br><span data-ttu-id="088df-270">- 従業員は、データ保護の規律に対する作業の速度を高くする</span><span class="sxs-lookup"><span data-stu-id="088df-270">- Employees value speed of work over data protection discipline</span></span> </br><span data-ttu-id="088df-271">- 顧客は、新しいデバイスで 18 人の従業員全員をWindows 10しました</span><span class="sxs-lookup"><span data-stu-id="088df-271">- Customer splurged and bought all 18 employees new Windows 10 devices</span></span>     |<span data-ttu-id="088df-272">- 既定の DLP ポリシーを使用して、Teams</span><span class="sxs-lookup"><span data-stu-id="088df-272">- Take advantage of the default DLP policy in Teams</span></span> </br><span data-ttu-id="088df-273">- アイテムの既定の設定で制限SharePointする</span><span class="sxs-lookup"><span data-stu-id="088df-273">- Use restricted by default setting for SharePoint items</span></span> </br><span data-ttu-id="088df-274">- 外部共有を防止するポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="088df-274">- Deploy policies that prevent external sharing</span></span> </br><span data-ttu-id="088df-275">- 優先度の高い場所にポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="088df-275">- Deploy policies to prioritized locations</span></span> </br><span data-ttu-id="088df-276">- ポリシーをデバイスにWindows 10する</span><span class="sxs-lookup"><span data-stu-id="088df-276">- Deploy policies to Windows 10 devices</span></span> </br><span data-ttu-id="088df-277">- 非クラウド ストレージへのアップロードOneDrive for Businessブロックする</span><span class="sxs-lookup"><span data-stu-id="088df-277">- Block uploads to non-OneDrive for Business cloud storage</span></span>      |

<!--

## Planning for workloads

### Exchange

### SharePoint

### OneDrive for Business

### Teams

### Windows 10 Devices

### Microsoft Cloud App Security (MCAS)

### On-premises Scanner
-->

## <a name="see-also"></a><span data-ttu-id="088df-278">関連項目</span><span class="sxs-lookup"><span data-stu-id="088df-278">See also</span></span>
- [<span data-ttu-id="088df-279">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="088df-279">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
