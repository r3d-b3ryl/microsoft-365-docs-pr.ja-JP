---
title: データプライバシーに関する規制に関する情報保護を、Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: GDPR、Microsoft 365消費者プライバシー法 (CCPA) などのデータプライバシー規制 (Microsoft Teams、SharePoint、電子メールなど) に関する情報保護を構成します。
ms.openlocfilehash: cae3a559c2bce39ecb02afa9be0878ff5e19ba48
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100773"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="0f05e-103">データプライバシーに関する規制に関する情報保護を、Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f05e-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="0f05e-104">組織は、オンプレミスとクラウドの両方を含む、IT インフラストラクチャに保存されている個人情報を保護、管理、および提供する必要がある地域のデータプライバシー規制の対象となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f05e-104">Your organization may be subject to regional data privacy regulations that require you to protect, manage, and provide rights and control over personal information stored in your IT infrastructure, including both on-premises and in the cloud.</span></span> <span data-ttu-id="0f05e-105">データプライバシー規制の最良の例は、欧州連合の一般データ保護規則 (GDPR) です。</span><span class="sxs-lookup"><span data-stu-id="0f05e-105">The best example of a data privacy regulation is the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="0f05e-106">データプライバシー規制に準拠しない場合、多額の罰金が科される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f05e-106">Failure to comply with data privacy regulations can result in substantial fines.</span></span>

<span data-ttu-id="0f05e-107">Microsoft 365 のデータの種類には、Microsoft Teams でのチャット セッション、Exchange のメール、SharePoint と OneDrive のファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="0f05e-107">Examples of the types of data in Microsoft 365 include chat sessions in Microsoft Teams, emails in Exchange, and files in SharePoint and OneDrive.</span></span> <span data-ttu-id="0f05e-108">このソリューションは、リスクを評価し、リスクに関する個人データを保護するための適切なアクションを実行する方法に関するMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="0f05e-108">This solution provides guidance on how to assess risks and take appropriate action to protect personal data in Microsoft 365.</span></span> <span data-ttu-id="0f05e-109">これには、データ プライバシー インシデントを保護、管理、および対応するための個人情報の識別が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f05e-109">This includes identifying  personal information so you can protect, govern, and respond to data privacy incidents.</span></span>

![データプライバシー規制に関する情報保護とは](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

<span data-ttu-id="0f05e-111">また、データプライバシーのニーズに合Microsoft 365 ID、デバイス、および脅威保護制御の使用に関する追加情報も提供されます。</span><span class="sxs-lookup"><span data-stu-id="0f05e-111">Additional information is also provided on the use of Microsoft 365 identity, device, and threat protection controls for your data privacy needs.</span></span> 

<span data-ttu-id="0f05e-112">これらのMicrosoft 365機能は、情報を保護するための条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f05e-112">These Microsoft 365 capabilities and features help you meet the criteria for protecting information.</span></span>

| <span data-ttu-id="0f05e-113">機能</span><span class="sxs-lookup"><span data-stu-id="0f05e-113">Capability or feature</span></span> | <span data-ttu-id="0f05e-114">説明</span><span class="sxs-lookup"><span data-stu-id="0f05e-114">Description</span></span> | <span data-ttu-id="0f05e-115">ライセンス</span><span class="sxs-lookup"><span data-stu-id="0f05e-115">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="0f05e-116">コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="0f05e-116">Compliance Manager</span></span> | <span data-ttu-id="0f05e-117">規制コンプライアンス活動を管理し、現在のコンプライアンス構成の全体的なスコアを取得し、改善のための推奨事項を見つける。</span><span class="sxs-lookup"><span data-stu-id="0f05e-117">Manage regulatory compliance activities, get an overall score of your current compliance configuration, and find recommendations for improvement.</span></span> <span data-ttu-id="0f05e-118">これは、コンプライアンス センターのワークフロー ベースのリスク評価Microsoft 365ツールです。</span><span class="sxs-lookup"><span data-stu-id="0f05e-118">This is a workflow-based risk assessment tool in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="0f05e-119">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="0f05e-119">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0f05e-120">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0f05e-120">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="0f05e-121">メール メッセージ、Office ドキュメント、共同作業のツールなど、Microsoft 365 のアプリやデータを攻撃から保護します。</span><span class="sxs-lookup"><span data-stu-id="0f05e-121">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> | <span data-ttu-id="0f05e-122">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="0f05e-122">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="0f05e-123">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="0f05e-123">Sensitivity labels</span></span> | <span data-ttu-id="0f05e-124">ユーザーの生産性と共同作業能力を妨げることなく、組織のデータを分類して保護します。</span><span class="sxs-lookup"><span data-stu-id="0f05e-124">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate.</span></span> <span data-ttu-id="0f05e-125">メール、ファイル、またはサイトにさまざまなレベルの保護を持つラベルを配置します。</span><span class="sxs-lookup"><span data-stu-id="0f05e-125">Place labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="0f05e-126">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="0f05e-126">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0f05e-127">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="0f05e-127">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="0f05e-128">内部および外部の両方で、個人情報を含むデータのリスク、不注意、または不適切な共有を検出、警告、ブロックします。</span><span class="sxs-lookup"><span data-stu-id="0f05e-128">Detect, warn, and block risky, inadvertent, or inappropriate sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="0f05e-129">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="0f05e-129">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="0f05e-130">データの保持ラベルとポリシー</span><span class="sxs-lookup"><span data-stu-id="0f05e-130">Data retention labels and policies</span></span> | <span data-ttu-id="0f05e-131">情報ガバナンス制御を実装する。</span><span class="sxs-lookup"><span data-stu-id="0f05e-131">Implement information governance controls.</span></span> <span data-ttu-id="0f05e-132">これには、組織のポリシーやデータ規制に準拠するためにデータ (顧客に関連する個人データなど) を保持する期間を決定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f05e-132">These can include determining how long to keep data (such as personal data related to customers) to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="0f05e-133">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="0f05e-133">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0f05e-134">メールの暗号化</span><span class="sxs-lookup"><span data-stu-id="0f05e-134">Email encryption</span></span> | <span data-ttu-id="0f05e-135">組織内外のユーザー間で暗号化された電子メール メッセージを送受信することで、個人データを保護します。</span><span class="sxs-lookup"><span data-stu-id="0f05e-135">Protect personal data by sending and receiving encrypted email messages between people inside and outside your organization.</span></span> | <span data-ttu-id="0f05e-136">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="0f05e-136">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a><span data-ttu-id="0f05e-137">このソリューションのガイダンスの構成</span><span class="sxs-lookup"><span data-stu-id="0f05e-137">Organization of the guidance in this solution</span></span>

<span data-ttu-id="0f05e-138">1 つ以上のプライバシー関連Microsoft 365を満たすのに役立つツールを理解するために、このガイダンスはセクションに整理されています。</span><span class="sxs-lookup"><span data-stu-id="0f05e-138">To help you understand the Microsoft 365 tools available to help you meet one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![データプライバシー規制に関する情報保護を実装する手順](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

<span data-ttu-id="0f05e-140">これらの各セクションは、このソリューションの個別の記事に対応しています。</span><span class="sxs-lookup"><span data-stu-id="0f05e-140">Each of these sections corresponds to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="0f05e-141">データプライバシーの義務について既に理解し、既存のプランに対して実行している場合は、予防、保護、保持、調査のガイダンスに焦点を当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f05e-141">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="0f05e-142">このガイダンスに従って、特に機能のコンテキスト外に必要な手順の数を考慮すると、必ずしもデータプライバシー規制に準拠するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0f05e-142">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="0f05e-143">お客様は、コンプライアンスを確保し、法務およびコンプライアンス チームに相談するか、コンプライアンスに特化した第三者からのガイダンスとアドバイスを求める責任があります。</span><span class="sxs-lookup"><span data-stu-id="0f05e-143">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="0f05e-144">計画: データプライバシーリスクを評価し、機密性の高いアイテムを特定する</span><span class="sxs-lookup"><span data-stu-id="0f05e-144">Plan: Assess data privacy risks and identify sensitive items</span></span>

<span data-ttu-id="0f05e-145">組織が対象となるデータプライバシー規制とリスクを評価する方法は、Microsoft 365 での機能の構成など、改善の実装を開始する前に取る重要な第一歩です。</span><span class="sxs-lookup"><span data-stu-id="0f05e-145">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including configuring capabilities in Microsoft 365.</span></span> <span data-ttu-id="0f05e-146">この作業には、組織が遵守する必要がある規制管理の対象となる特定の機密情報の種類の全体的な準備状況評価または識別が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f05e-146">This work can include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with.</span></span>

<span data-ttu-id="0f05e-147">詳細については、「データプライバシーリスク [を評価し、機密性の高いアイテムを特定する」を参照してください](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="0f05e-147">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a><span data-ttu-id="0f05e-148">追跡: リスク評価を実行し、コンプライアンス スコアを確認する</span><span class="sxs-lookup"><span data-stu-id="0f05e-148">Track: Run risk assessments and check your compliance score</span></span>

<span data-ttu-id="0f05e-149">Microsoft 365 コンプライアンス センターで利用できるコンプライアンス マネージャーは、改善アクション全体と、適用される複数のデータ プライバシー規制に関連するアクションを追跡および管理する組み込みの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f05e-149">Compliance Manager, available in the Microsoft 365 compliance center, provides you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations that apply to you.</span></span>

<span data-ttu-id="0f05e-150">各規制に固有の組み込みの評価テンプレートを使用して、選択した評価テンプレートごとにアクション アイテムを追跡し、特定の規制コントロールを表示し、それらを特定のアクションに関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="0f05e-150">You can use built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="0f05e-151">詳細については、「コンプライアンス マネージャーを [使用して改善アクションを管理する」を参照してください](information-protection-deploy-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="0f05e-151">For more information, see [Use Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-protect-personal-data"></a><span data-ttu-id="0f05e-152">防止: 個人データを保護する</span><span class="sxs-lookup"><span data-stu-id="0f05e-152">Prevent: Protect personal data</span></span>

<span data-ttu-id="0f05e-153">Microsoft 365、ID、デバイス、および脅威保護機能を提供し、データ プライバシーの規制コンプライアンスの遵守に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f05e-153">Microsoft 365 provides identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="0f05e-154">詳細については、「データプライバシー規制に ID、デバイス、および脅威保護を使用 [する」を参照してください](information-protection-deploy-identity-device-threat.md)。</span><span class="sxs-lookup"><span data-stu-id="0f05e-154">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="0f05e-155">この記事では、これらの分野で一般的に必要なデータプライバシー規制について簡単に説明し、実装要件に対処するために役立つ詳細な情報へのリンクを含む、関連する Microsoft 365 ソリューションの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f05e-155">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="0f05e-156">データプライバシー規制の対象となる情報を保護する</span><span class="sxs-lookup"><span data-stu-id="0f05e-156">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="0f05e-157">データプライバシー規制では、GDPR、カリフォルニア州消費者保護法 (CCPA)、HIPAA-HITECH (米国の医療プライバシー法)、およびブラジルデータ保護法 (LGPD) のサンプル セットの 4 つのデータ プライバシー規制に対する 40 以上の制御を含む、環境で使用できる多数の個人情報保護管理が規定されています。</span><span class="sxs-lookup"><span data-stu-id="0f05e-157">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than 40 controls for protecting information across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="0f05e-158">詳細については、「組織内の [データプライバシー規制の対象となる情報を保護する」を参照してください](information-protection-deploy-protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="0f05e-158">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="0f05e-159">この記事では、組織内のデータプライバシーに関する情報保護のニーズに対処するために使用できる主な制御スキームについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0f05e-159">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="0f05e-160">保持: データプライバシー規制の対象となる情報を管理する</span><span class="sxs-lookup"><span data-stu-id="0f05e-160">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="0f05e-161">データ プライバシー規制では、GDPR、CCPA、HIPAA-HITECH、および LGPD のサンプル セットの 4 つのデータ プライバシー規制全体で 24 以上のコントロールを含む、お客様の環境で使用できる個人情報ガバナンス管理が必要です。</span><span class="sxs-lookup"><span data-stu-id="0f05e-161">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than 24 controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="0f05e-162">詳細については、「組織内の [データプライバシー規制の対象となる情報を管理する」を参照してください](information-protection-deploy-govern.md)。</span><span class="sxs-lookup"><span data-stu-id="0f05e-162">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="0f05e-163">この記事では、目的に合った保持、削除、アーカイブなどの情報ガバナンスに関するデータプライバシー規制はあいまいですが、組織のデータプライバシーに関するアドレス情報ガバナンスのニーズを使用できる主な制御スキームが示されています。 &mdash; &mdash;</span><span class="sxs-lookup"><span data-stu-id="0f05e-163">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a><span data-ttu-id="0f05e-164">調査: データ プライバシー インシデントの監視、調査、対応</span><span class="sxs-lookup"><span data-stu-id="0f05e-164">Investigate: Monitor, investigate, and respond to data privacy incidents</span></span>

<span data-ttu-id="0f05e-165">関連する機能Microsoft 365、組織内のデータ プライバシー インシデントの監視、調査、および対応に役立つ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="0f05e-165">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="0f05e-166">これらの機能を使用するプロセス、手順、その他のドキュメントを持つことは、規制機関へのコンプライアンスを実証するために重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f05e-166">Having processes, procedures, and other documentation for using these features can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="0f05e-167">詳細については、「組織内の [データ プライバシー インシデントの](information-protection-deploy-monitor-respond.md)監視と対応」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f05e-167">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
