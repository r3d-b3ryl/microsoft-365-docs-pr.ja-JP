---
title: データ保護影響評価
description: このドキュメントには、データ管理者に対し、DPIA が必要であるかどうかを判断し、必要な場合には DPIA に含める詳細情報を決定する上で役立つ情報が記載されています。
keywords: データ保護影響評価、DPIA、Dynamics 365、Microsoft プロフェッショナル サービス、Microsoft 365、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0a62cf2ef40bbf9da219309cf75eed27ea8739e4
ms.sourcegitcommit: 2498cd4af90c31771167a1be9f8f12a96dc6500f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41916902"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a><span data-ttu-id="58e63-104">GDPR のデータ保護影響評価</span><span class="sxs-lookup"><span data-stu-id="58e63-104">Data Protection Impact Assessment for the GDPR</span></span>

<span data-ttu-id="58e63-105">一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。</span><span class="sxs-lookup"><span data-stu-id="58e63-105">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="58e63-106">詳細については、「[GDPR 概要トピック](gdpr.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e63-106">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span> <span data-ttu-id="58e63-107">このドキュメントでは、Microsoft の製品とサービスを使用する際の GDPR に基づくデータ保護影響評価 (DPIA) に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="58e63-107">This document guides you to information regarding Data Protection Impact Assessments (DPIAs) under the GDPR when using Microsoft products and services.</span></span>

## <a name="terminology"></a><span data-ttu-id="58e63-108">用語</span><span class="sxs-lookup"><span data-stu-id="58e63-108">Terminology</span></span>

<span data-ttu-id="58e63-109">このドキュメントで使用されている GDPR 用語の役に立つ定義:</span><span class="sxs-lookup"><span data-stu-id="58e63-109">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="58e63-110">*データ コントローラー (コントローラー)*: 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="58e63-110">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="58e63-111">*個人データ*と*データ主体*: 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。</span><span class="sxs-lookup"><span data-stu-id="58e63-111">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="58e63-112">*処理者*: コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。</span><span class="sxs-lookup"><span data-stu-id="58e63-112">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="58e63-113">*顧客データ*: ビジネス運営における日々の業務で作成および保存されるデータ。</span><span class="sxs-lookup"><span data-stu-id="58e63-113">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dpia"></a><span data-ttu-id="58e63-114">DPIA とは?</span><span class="sxs-lookup"><span data-stu-id="58e63-114">What is a DPIA?</span></span>

<span data-ttu-id="58e63-115">GDPR では、管理者は、「自然人の権利と自由を危険にさらす可能性が高い」操作に関してデータ保護影響評価 (DPIA) を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e63-115">The GDPR requires controllers to prepare a Data Protection Impact Assessment (DPIA) for operations that are 'likely to result in a high risk to the rights and freedoms of natural persons.'</span></span> <span data-ttu-id="58e63-116">DPIA の作成を必要とする Microsoft の製品とサービスに固有のものはありません。</span><span class="sxs-lookup"><span data-stu-id="58e63-116">There is nothing inherent in Microsoft products and services that need the creation of a DPIA.</span></span> <span data-ttu-id="58e63-117">ただし、Microsoft の製品とサービスは高度なカスタマイズが可能であるため、Microsoft の構成の詳細に応じて DPIA が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="58e63-117">However, because Microsoft products and services are highly customizable, a DPIA may be needed depending on the details of your Microsoft configuration.</span></span> <span data-ttu-id="58e63-118">Microsoft は、このような情報に関して制御することは一切なく、分析情報を得ることもほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="58e63-118">Microsoft has no control over, and little or no insight into such information.</span></span> <span data-ttu-id="58e63-119">お客様はデータ コントローラーとして、データの適切な使用を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e63-119">You, as a data controller must determine appropriate uses of their data.</span></span>

## <a name="dpia-in-action"></a><span data-ttu-id="58e63-120">実行中の DPIA</span><span class="sxs-lookup"><span data-stu-id="58e63-120">DPIA in Action</span></span>

<span data-ttu-id="58e63-121">DPIA ガイダンスは、Office 365、Azure、Dynamics 365、Microsoft サポート/プロフェッショナル サービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="58e63-121">The DPIA guidance applies to Office 365, Azure, Dynamics 365, and Microsoft Support and Professional Services.</span></span> <span data-ttu-id="58e63-122">このガイダンスには、以下の考慮事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58e63-122">That guidance includes consideration of:</span></span>

<span data-ttu-id="58e63-123">**いつ DPIA が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="58e63-123">**When is a DPIA needed?**</span></span>

<span data-ttu-id="58e63-124">DPIA を完了するかどうかを検討する際には、以下にリストするリスク要因に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e63-124">The risk factors listed below should be addressed when considering whether to complete a DPIA.</span></span> <span data-ttu-id="58e63-125">その他の潜在的要因と詳細については、各ガイドラインの第 1 部を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e63-125">Other potential factors and further details are found in Part 1 of each of the guidelines.</span></span>  

- <span data-ttu-id="58e63-126">自動処理に基づく、データの体系的かつ広範囲な評価。</span><span class="sxs-lookup"><span data-stu-id="58e63-126">A systematic and extensive evaluation of data based on automated processing.</span></span>  
- <span data-ttu-id="58e63-127">特殊なカテゴリのデータ (自然人を一意に識別する情報が明らかになるデータ)、または有罪判決や違反に関する個人データを対象とした大規模な処理。</span><span class="sxs-lookup"><span data-stu-id="58e63-127">Processing on a large scale of special categories of data (data revealing information uniquely identifying a natural person), or of personal data relating to criminal convictions and offenses.</span></span>
- <span data-ttu-id="58e63-128">公開アクセス可能な地域での体系的な大規模監視。</span><span class="sxs-lookup"><span data-stu-id="58e63-128">Systematic monitoring of a publicly accessible area on a large scale.</span></span>

<span data-ttu-id="58e63-129">GDPR では次のように説明しています。「個人データの処理は、処理が個々の医師、他の医療専門家、または弁護士の患者または依頼主に関するものである場合、大規模な処理とはみなされない。</span><span class="sxs-lookup"><span data-stu-id="58e63-129">The GDPR clarifies 'The processing of personal data should not be considered to be on a large scale if the processing concerns personal data from patients or clients by an individual physician, other health care professional, or lawyer.</span></span> <span data-ttu-id="58e63-130">その場合、データ保護影響評価は必須ではない」。</span><span class="sxs-lookup"><span data-stu-id="58e63-130">In such cases, a data protection impact assessment should not be mandatory.'</span></span>

<span data-ttu-id="58e63-131">**DPIA の完了には何が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="58e63-131">**What is required to complete a DPIA?**</span></span>

<span data-ttu-id="58e63-132">DPIA では、想定された処理作業に関する具体的な情報を提供する必要があります。これは、このガイダンスの第 2 部で詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="58e63-132">A DPIA should provide specific information about the intended processing, which is detailed in Part 2 of the guidance.</span></span> <span data-ttu-id="58e63-133">この情報には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="58e63-133">That information includes:</span></span>

- <span data-ttu-id="58e63-134">DPIA の目的に関するデータ処理作業の必要性および比例性の評価。</span><span class="sxs-lookup"><span data-stu-id="58e63-134">Assessment of the necessity, and proportionality of data processing in relation to the purpose of the DPIA.</span></span>  
- <span data-ttu-id="58e63-135">自然人の権利および自由に関するリスクの評価。</span><span class="sxs-lookup"><span data-stu-id="58e63-135">Assessment of the risks to the rights and freedoms of natural persons.</span></span>
- <span data-ttu-id="58e63-136">個人データを確実に保護し、GDPR 準拠を実証するためのセーフガード、セキュリティ対策、メカニズムを含む、リスクに対処するための想定された対策。</span><span class="sxs-lookup"><span data-stu-id="58e63-136">Intended measures to address the risks, including safeguards, security measures, and mechanisms to ensure the protection of personal data and demonstrate compliance with the GDPR.</span></span>
- <span data-ttu-id="58e63-137">処理の目的</span><span class="sxs-lookup"><span data-stu-id="58e63-137">Purposes of processing</span></span>  
- <span data-ttu-id="58e63-138">処理される個人データのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="58e63-138">Categories of personal data processed</span></span>  
- <span data-ttu-id="58e63-139">データ保持</span><span class="sxs-lookup"><span data-stu-id="58e63-139">Data retention</span></span>  
- <span data-ttu-id="58e63-140">個人データの保存場所と移転</span><span class="sxs-lookup"><span data-stu-id="58e63-140">Location and transfers of personal data</span></span>  
- <span data-ttu-id="58e63-141">第三者の副処理者とのデータの共有</span><span class="sxs-lookup"><span data-stu-id="58e63-141">Data sharing with third-party subprocessors</span></span>  
- <span data-ttu-id="58e63-142">独立した第三者とのデータの共有</span><span class="sxs-lookup"><span data-stu-id="58e63-142">Data sharing with independent third-parties</span></span>  
- <span data-ttu-id="58e63-143">データ主体の権利</span><span class="sxs-lookup"><span data-stu-id="58e63-143">Data subject rights</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="58e63-144">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="58e63-144">Additional Considerations</span></span>

<span data-ttu-id="58e63-145">Microsoft 実装に関連する可能性がある具体的な詳細情報については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e63-145">Specific details that may be relevant to your Microsoft implementation are below.</span></span>

- <span data-ttu-id="58e63-146">[Office 365](gdpr-dpia-office365.md): このドキュメントは、Exchange Online、SharePoint Online、Yammer、Skype for Business、Power BI などの Office 365 のアプリケーションとサービスに適用されます。ただし、これに限定されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="58e63-146">[Office 365](gdpr-dpia-office365.md): This document applies to Office 365 applications and services, including but not limited to Exchange Online, SharePoint Online, Yammer, Skype for Business, and Power BI.</span></span> <span data-ttu-id="58e63-147">詳細については、表 [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) と [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e63-147">Refer to Tables [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) and [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) for more details.</span></span>  
- <span data-ttu-id="58e63-148">[Azure](gdpr-dpia-azure.md): Microsoft Azure の使用に関しての DPIA の必要性および内容を判断するにあたり、お客様にはプライバシー責任者または弁護士と連携することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58e63-148">[Azure](gdpr-dpia-azure.md): Customers are encouraged to work with their privacy officers and legal counsel to determine the necessity and content of any DPIAs related to their use of Microsoft Azure.</span></span>  
- <span data-ttu-id="58e63-149">[Dynamics 365](gdpr-dpia-dynamics.md): DPIA の内容は、使用している Dynamics 365 ツールによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="58e63-149">[Dynamics 365](gdpr-dpia-dynamics.md): The contents of a DPIA may vary according to which Dynamics 365 tools you are employing.</span></span> <span data-ttu-id="58e63-150">詳細については、「[パート 2 - DPIA の内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e63-150">For specific details refer to [Part 2 Contents of a DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia).</span></span>
- <span data-ttu-id="58e63-151">[Microsoft サポート/プロフェッショナル サービス](gdpr-dpia-prof-services.md): プロフェッショナル サービスでは、特定のルーチンまたは自動データ処理は行われません。また、特別なカテゴリを処理したり、パブリックにアクセス可能なデータの監視を促進または要求するタスクを実行したりすることも想定されていません。</span><span class="sxs-lookup"><span data-stu-id="58e63-151">[Microsoft Support and Professional Services](gdpr-dpia-prof-services.md): Professional Services does not conduct certain routine or automated data processing, nor is it intended to process special categories or perform tasks that facilitate or require monitoring of publicly accessible data.</span></span> <span data-ttu-id="58e63-152">詳細については、「[パート 1 - DPIA が必要であるかどうかの判断](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e63-152">For details see [Part 1 — Determining Whether a DPIA is needed](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed).</span></span> <span data-ttu-id="58e63-153">コントローラーは、コントローラーによる特定の実装およびプロフェッショナル サービスの使用において、上記の DPIA 要素を他のすべての関連要因とともに考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e63-153">Controllers must consider the DPIA elements outlined above, along with any other relevant factors, in the context of the controller’s specific implementations and uses of Professional Services.</span></span> <span data-ttu-id="58e63-154">プロフェッショナル サービス情報については、「[パート 2 - DPIA の内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e63-154">For Professional Services information, see [Part 2 — Contents of a DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia).</span></span>

## <a name="learn-more"></a><span data-ttu-id="58e63-155">詳細情報</span><span class="sxs-lookup"><span data-stu-id="58e63-155">Learn more</span></span>

- [<span data-ttu-id="58e63-156">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="58e63-156">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
