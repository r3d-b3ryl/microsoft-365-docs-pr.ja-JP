---
title: Microsoft 365 を使用して、データプライバシー規制の情報保護を展開する
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
description: 情報を保護し、データのプライバシー規制に準拠するように、セキュリティとサービスインフラストラクチャを構成します。
ms.openlocfilehash: 640ce075515c687c037cb0e4ab3e03e3beda81dc
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522291"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="732c5-103">Microsoft 365 を使用して、データプライバシー規制の情報保護を展開する</span><span class="sxs-lookup"><span data-stu-id="732c5-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="732c5-104">組織は、オンプレミスとクラウドの両方を含む、IT インフラストラクチャに格納されている個人情報に関する権限と制御を保護、管理、提供する必要がある地域データのプライバシー規制の対象となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="732c5-104">Your organization may be subject to regional data privacy regulations that require you to protect, manage, and provide rights and control over personal information stored in your IT infrastructure, including both on-premises and in the cloud.</span></span> <span data-ttu-id="732c5-105">データプライバシー規制の最も良い例は、欧州連合の一般的なデータ保護規則 (GDPR) です。</span><span class="sxs-lookup"><span data-stu-id="732c5-105">The best example of a data privacy regulation is the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="732c5-106">データプライバシー規制への準拠に失敗すると、膨大な罰金を得られることがあります。</span><span class="sxs-lookup"><span data-stu-id="732c5-106">Failure to comply with data privacy regulations can result in substantial fines.</span></span>

<span data-ttu-id="732c5-107">Microsoft 365 のデータの種類の例には、Microsoft Teams のチャットセッション、Exchange の電子メール、および SharePoint および OneDrive のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="732c5-107">Examples of the types of data in Microsoft 365 include chat sessions in Microsoft Teams, emails in Exchange, and files in SharePoint and OneDrive.</span></span> <span data-ttu-id="732c5-108">このソリューションでは、データプライバシーの規制の対象となる Microsoft 365 services に格納されている個人データについて、データのプライバシーインシデントを特定、特定、保護、制御、および対応する方法についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="732c5-108">This solution provides guidance on how to identify, locate, protect, govern, and respond to data privacy incidents for personal data stored in Microsoft 365 services that is subject to data privacy regulations.</span></span>

![データプライバシー規制のための情報の展開保護](../media/information-protection-deploy/information-protection-deploy-big-picture.png)

<span data-ttu-id="732c5-110">また、データのプライバシーのニーズに合わせて Microsoft 365 の id、デバイス、および脅威保護の制御を使用する場合にも、追加情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="732c5-110">Additional information is also provided on the use of Microsoft 365 identity, device, and threat protection controls for your data privacy needs.</span></span> 

<span data-ttu-id="732c5-111">データのプライバシー規制に準拠するために情報を保護するための基準を満たすには、次の Microsoft 365 の機能と機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="732c5-111">To meet the criteria for protecting information for compliance with data privacy regulations, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="732c5-112">機能</span><span class="sxs-lookup"><span data-stu-id="732c5-112">Capability or feature</span></span> | <span data-ttu-id="732c5-113">説明</span><span class="sxs-lookup"><span data-stu-id="732c5-113">Description</span></span> | <span data-ttu-id="732c5-114">ライセンス</span><span class="sxs-lookup"><span data-stu-id="732c5-114">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="732c5-115">コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="732c5-115">Compliance Manager</span></span> | <span data-ttu-id="732c5-116">Microsoft Service Trust Portal のワークフローベースのリスク評価ツールを使用して、Microsoft のクラウド サービスに関連する組織の規制準拠の取り組みを管理します。</span><span class="sxs-lookup"><span data-stu-id="732c5-116">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="732c5-117">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="732c5-117">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="732c5-118">コンプライアンス スコア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="732c5-118">Compliance Score (preview)</span></span> | <span data-ttu-id="732c5-119">Microsoft 365 コンプライアンス センターで、現在のコンプライアンス構成の全体のスコアと改善のための推奨事項を確認しましょう。</span><span class="sxs-lookup"><span data-stu-id="732c5-119">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 Compliance Center.</span></span> | <span data-ttu-id="732c5-120">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="732c5-120">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="732c5-121">Office Advanced Threat Protection (ATP)</span><span class="sxs-lookup"><span data-stu-id="732c5-121">Office Advanced Threat Protection (ATP)</span></span> | <span data-ttu-id="732c5-122">メール メッセージ、Office ドキュメント、共同作業のツールなど、Microsoft 365 のアプリやデータを攻撃から保護します。</span><span class="sxs-lookup"><span data-stu-id="732c5-122">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> | <span data-ttu-id="732c5-123">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="732c5-123">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="732c5-124">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="732c5-124">Sensitivity labels</span></span> | <span data-ttu-id="732c5-125">メール、ファイル、サイトに様々な保護レベルを持ったラベルを適用することで、ユーザーの生産性や共同作業機能を妨げることなく、組織のデータを分類して保護します。</span><span class="sxs-lookup"><span data-stu-id="732c5-125">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="732c5-126">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="732c5-126">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="732c5-127">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="732c5-127">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="732c5-128">内部や外部での個人情報を含むデータの共有などの危険な共有、偶発的な共有、不適切な共有を検出し、警告し、ブロックします。</span><span class="sxs-lookup"><span data-stu-id="732c5-128">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="732c5-129">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="732c5-129">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="732c5-130">データの保持ラベルとポリシー</span><span class="sxs-lookup"><span data-stu-id="732c5-130">Data retention labels and policies</span></span> | <span data-ttu-id="732c5-131">データの保持期間や、顧客の個人データの保管についての要件などの情報ガバナンスの制御を展開し、組織のポリシーやデータ規制に準拠します。</span><span class="sxs-lookup"><span data-stu-id="732c5-131">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="732c5-132">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="732c5-132">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="732c5-133">メールの暗号化</span><span class="sxs-lookup"><span data-stu-id="732c5-133">Email encryption</span></span> | <span data-ttu-id="732c5-134">組織内外のユーザーとの間で、顧客の個人情報などの規制されたデータを含む暗号化されたメール メッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="732c5-134">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="732c5-135">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="732c5-135">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a><span data-ttu-id="732c5-136">このソリューションのガイダンスの編成</span><span class="sxs-lookup"><span data-stu-id="732c5-136">Organization of the guidance in this solution</span></span>

<span data-ttu-id="732c5-137">1つまたは複数のプライバシー関連の規制の対象となる個人データの識別、管理、制御、監視に使用できる Microsoft 365 ツールの理解を助けるために、このガイダンスはセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="732c5-137">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![データプライバシー規制のための情報の展開保護](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="732c5-139">これらの各セクションは、このソリューションの個別の記事に対応しています。</span><span class="sxs-lookup"><span data-stu-id="732c5-139">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="732c5-140">データプライバシーの義務に精通していて、既存のプランに対して実行されている場合は、禁止、保護、保持、および調査のガイダンスに集中することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="732c5-140">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="732c5-141">このガイダンスに従うことで、特に、機能のコンテキストの範囲外で必要とされる手順の数を考慮して、データプライバシー規制に準拠しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="732c5-141">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="732c5-142">お客様は、コンプライアンスを保証し、法務/コンプライアンスチームを参照したり、コンプライアンスを専門とするサードパーティのガイダンスやアドバイスを求めたりする責任を負います。</span><span class="sxs-lookup"><span data-stu-id="732c5-142">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="732c5-143">計画: データのプライバシーリスクを評価し、機密アイテムを識別する</span><span class="sxs-lookup"><span data-stu-id="732c5-143">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="732c5-144">お客様の組織が対象となるデータのプライバシーに関する規制とリスクは、Microsoft 365 構成を通じて実現可能なものを含む、改善の実装を開始する前に行う重要な最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="732c5-144">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="732c5-145">これには、全体的な準備状況の評価、または組織が準拠する必要がある規制統制の対象となる特定の機密情報の種類の確認、および Microsoft 365 環境でのそれらの発生の確認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="732c5-145">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="732c5-146">詳細については、「[データプライバシーのリスクを評価し、機密性の高いアイテムを識別](information-protection-deploy-assess.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="732c5-146">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="732c5-147">追跡: コンプライアンススコアとコンプライアンスマネージャーを使用する</span><span class="sxs-lookup"><span data-stu-id="732c5-147">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="732c5-148">コンプライアンススコア/コンプライアンスマネージャー Microsoft 365 コンプライアンス管理センターおよびサービス信頼ポータルで使用可能な一連のツールを統合して提供します。</span><span class="sxs-lookup"><span data-stu-id="732c5-148">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="732c5-149">これらのツールによって、強化された操作全体を追跡して管理することができます。また、対象とする複数のデータプライバシー規制に関連するものも提供します。</span><span class="sxs-lookup"><span data-stu-id="732c5-149">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="732c5-150">また、このツールを使用すると、各規制に固有の組み込みの評価テンプレートを活用することができます。ここでは、選択された各評価テンプレートのアクションアイテムを追跡し、特定の規制統制を表示し、特定のアクションに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="732c5-150">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="732c5-151">詳細については、「[コンプライアンススコアとコンプライアンスマネージャーを使用して改善アクションを管理する](information-protection-deploy-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="732c5-151">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="732c5-152">回避方法: id、デバイス、および脅威保護にデータプライバシー規制を使用します。</span><span class="sxs-lookup"><span data-stu-id="732c5-152">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="732c5-153">Microsoft 365 は、id、デバイス、および脅威の保護に関するさまざまな機能を提供します。これを使用すると、データプライバシーに関する法令遵守に準拠することができます。</span><span class="sxs-lookup"><span data-stu-id="732c5-153">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="732c5-154">詳細については、「[データプライバシー規制の id、デバイス、および脅威保護を使用する](information-protection-deploy-identity-device-threat.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="732c5-154">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="732c5-155">この記事では、一般的にこれらの分野でのデータプライバシー規制について説明し、関連する Microsoft 365 ソリューションの一覧を示します。また、実装要件に対処するための詳細情報へのリンクも掲載しています。</span><span class="sxs-lookup"><span data-stu-id="732c5-155">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="732c5-156">情報をデータプライバシーの規則に従って保護する</span><span class="sxs-lookup"><span data-stu-id="732c5-156">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="732c5-157">データプライバシーに関する規制では、GDPR のサンプルセットに含まれる4つのデータプライバシー規制、HIPAA (米国の医療保険法)、HIPAA データ保護法 (LGPD) での4つのデータプライバシー規制に関する情報を保護することができる40、さまざまな個人情報保護の制御があります。</span><span class="sxs-lookup"><span data-stu-id="732c5-157">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="732c5-158">詳細については、「[組織のデータプライバシー規制に関する情報を保護する](information-protection-deploy-protect-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="732c5-158">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="732c5-159">この記事では、組織内のデータプライバシーに関する情報保護のニーズに対処するために使用できる主要な制御スキームについて説明します。</span><span class="sxs-lookup"><span data-stu-id="732c5-159">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="732c5-160">保持: データプライバシーの規則に従って情報を管理する</span><span class="sxs-lookup"><span data-stu-id="732c5-160">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="732c5-161">データプライバシーに関する規制 GDPR のサンプルセットに含まれる4つのデータプライバシー規則 (CCPA、HIPAA、および LGPD) について、24個を超えるコントロールを含む、個人情報ガバナンスの統制についてご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="732c5-161">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="732c5-162">詳細については、「[組織のデータプライバシー規制に関する情報を管理する](information-protection-deploy-govern.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="732c5-162">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="732c5-163">意図的の保存、削除、アーカイブなどの情報ガバナンスに関しては、データプライバシーに関する規制をあいまいにすることができますが、 &mdash; &mdash; この記事では、組織内のデータのプライバシーに関する情報ガバナンスのニーズを解決するために使用できる主要な制御スキームについて説明します。</span><span class="sxs-lookup"><span data-stu-id="732c5-163">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="732c5-164">調査: データプライバシー規制を監視し、件名に対応する</span><span class="sxs-lookup"><span data-stu-id="732c5-164">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="732c5-165">Operationalize 関連の機能を使用して、組織内のデータプライバシーインシデントの監視、調査、および対応に役立てることができる Microsoft 365 の機能があります。</span><span class="sxs-lookup"><span data-stu-id="732c5-165">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="732c5-166">これらのプロセス、手順、およびその他のドキュメントに関するその他のドキュメントは、規制機関に準拠していることを示すために重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="732c5-166">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="732c5-167">詳細については、「[組織内のデータプライバシーインシデントを監視および応答する](information-protection-deploy-monitor-respond.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="732c5-167">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
