---
title: Microsoft 365 を使用して、データプライバシー規制の情報保護を展開する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 情報を保護し、データのプライバシー規制に準拠するように、セキュリティとサービスインフラストラクチャを構成します。
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695112"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="ffa4e-103">Microsoft 365 を使用して、データプライバシー規制の情報保護を展開する</span><span class="sxs-lookup"><span data-stu-id="ffa4e-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="ffa4e-104">このソリューションでは、Microsoft 365 services に格納されている個人データを計画および保護する方法についてのガイダンスを提供します。また、欧州連合の一般的なデータ保護規則 (GDPR) などのデータプライバシー規制に従う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="ffa4e-105">このソリューションでは、Microsoft の該当する情報保護とコンプライアンスの機能、Microsoft コンプライアンススコア、および評価ツールに焦点を当てて、データをご理解いただくことができます。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="ffa4e-106">データのプライバシー要件やデータインシデント検出および応答ツールに対して Microsoft の id、デバイス、および脅威保護の各制御を使用する場合にも、追加情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="ffa4e-107">このガイダンス資料の構成</span><span class="sxs-lookup"><span data-stu-id="ffa4e-107">Organization of this guidance material</span></span>

<span data-ttu-id="ffa4e-108">1つまたは複数のプライバシー関連の規制の対象となる個人データの識別、管理、制御、監視に使用できる Microsoft 365 ツールの理解を助けるために、このガイダンスはセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![情報保護を展開し、データのプライバシー規制を遵守する](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="ffa4e-110">これらの各セクションは、このソリューションの個別の記事に対応しています。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="ffa4e-111">データプライバシーの義務に精通していて、既存のプランに対して実行されている場合は、禁止、保護、保持、および調査のガイダンスに集中することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="ffa4e-112">このガイダンスに従うことで、特に、機能のコンテキストの範囲外で必要とされる手順の数を考慮して、データプライバシー規制に準拠しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="ffa4e-113">お客様は、コンプライアンスを保証し、法務/コンプライアンスチームを参照したり、コンプライアンスを専門とするサードパーティのガイダンスやアドバイスを求めたりする責任を負います。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="ffa4e-114">計画: データのプライバシーリスクを評価し、機密アイテムを識別する</span><span class="sxs-lookup"><span data-stu-id="ffa4e-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="ffa4e-115">お客様の組織が対象となるデータのプライバシーに関する規制とリスクは、Microsoft 365 構成を通じて実現可能なものを含む、改善の実装を開始する前に行う重要な最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="ffa4e-116">これには、全体的な準備状況の評価、または組織が準拠する必要がある規制統制の対象となる特定の機密情報の種類の確認、および Microsoft 365 環境でのそれらの発生の確認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="ffa4e-117">詳細については、「[データプライバシーのリスクを評価し、機密性の高いアイテムを識別](information-protection-deploy-assess.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="ffa4e-118">追跡: コンプライアンススコアとコンプライアンスマネージャーを使用する</span><span class="sxs-lookup"><span data-stu-id="ffa4e-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="ffa4e-119">コンプライアンススコア/コンプライアンスマネージャー Microsoft 365 コンプライアンス管理センターおよびサービス信頼ポータルで使用可能な一連のツールを統合して提供します。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="ffa4e-120">これらのツールによって、強化された操作全体を追跡して管理することができます。また、対象とする複数のデータプライバシー規制に関連するものも提供します。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="ffa4e-121">また、このツールを使用すると、各規制に固有の組み込みの評価テンプレートを活用することができます。ここでは、選択された各評価テンプレートのアクションアイテムを追跡し、特定の規制統制を表示し、特定のアクションに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="ffa4e-122">詳細については、「[コンプライアンススコアとコンプライアンスマネージャーを使用して改善アクションを管理する](information-protection-deploy-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="ffa4e-123">回避方法: id、デバイス、および脅威保護にデータプライバシー規制を使用します。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="ffa4e-124">Microsoft 365 は、id、デバイス、および脅威の保護に関するさまざまな機能を提供します。これを使用すると、データプライバシーに関する法令遵守に準拠することができます。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="ffa4e-125">詳細については、「[データプライバシー規制の id、デバイス、および脅威保護を使用する](information-protection-deploy-identity-device-threat.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="ffa4e-126">この記事では、一般的にこれらの分野でのデータプライバシー規制について説明し、関連する Microsoft 365 ソリューションの一覧を示します。また、実装要件に対処するための詳細情報へのリンクも掲載しています。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="ffa4e-127">情報をデータプライバシーの規則に従って保護する</span><span class="sxs-lookup"><span data-stu-id="ffa4e-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="ffa4e-128">データプライバシーに関する規制では、GDPR のサンプルセットに含まれる4つのデータプライバシー規制、HIPAA (米国の医療保険法)、HIPAA データ保護法 (LGPD) での4つのデータプライバシー規制に関する情報を保護することができる40、さまざまな個人情報保護の制御があります。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="ffa4e-129">詳細については、「[組織のデータプライバシー規制に関する情報を保護する](information-protection-deploy-protect-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="ffa4e-130">この記事では、組織内のデータプライバシーに関する情報保護のニーズに対処するために使用できる主要な制御スキームについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="ffa4e-131">保持: データプライバシーの規則に従って情報を管理する</span><span class="sxs-lookup"><span data-stu-id="ffa4e-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="ffa4e-132">データプライバシーに関する規制 GDPR のサンプルセットに含まれる4つのデータプライバシー規則 (CCPA、HIPAA、および LGPD) について、24個を超えるコントロールを含む、個人情報ガバナンスの統制についてご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="ffa4e-133">詳細については、「[組織のデータプライバシー規制に関する情報を管理する](information-protection-deploy-govern.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="ffa4e-134">意図的の保存、削除、アーカイブなどの情報ガバナンスに関しては、データプライバシーに関する規制をあいまいにすることができますが、 &mdash; &mdash; この記事では、組織内のデータのプライバシーに関する情報ガバナンスのニーズを解決するために使用できる主要な制御スキームについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="ffa4e-135">調査: データプライバシー規制を監視し、件名に対応する</span><span class="sxs-lookup"><span data-stu-id="ffa4e-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="ffa4e-136">Operationalize 関連の機能を使用して、組織内のデータプライバシーインシデントの監視、調査、および対応に役立てることができる Microsoft 365 の機能があります。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="ffa4e-137">これらのプロセス、手順、およびその他のドキュメントに関するその他のドキュメントは、規制機関に準拠していることを示すために重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="ffa4e-138">詳細については、「[組織内のデータプライバシーインシデントを監視および応答する](information-protection-deploy-monitor-respond.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffa4e-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
