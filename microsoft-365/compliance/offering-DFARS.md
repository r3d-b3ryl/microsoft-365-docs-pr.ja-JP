---
title: 連邦政府機関買収規制補足 (DFARS dfars)
description: Microsoft Azure Government は、連邦取得の防御法 (DFARS dfars) の要件をサポートしています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 267a506881e8eecdf2ded50e9858054c022dfae1
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859977"
---
# <a name="defense-federal-acquisition-regulation-supplement-dfars"></a><span data-ttu-id="f245d-104">連邦政府機関買収規制補足 (DFARS dfars)</span><span class="sxs-lookup"><span data-stu-id="f245d-104">Defense Federal Acquisition Regulation Supplement (DFARS)</span></span>

## <a name="dfars-overview"></a><span data-ttu-id="f245d-105">DFARS 概要</span><span class="sxs-lookup"><span data-stu-id="f245d-105">DFARS overview</span></span>

<span data-ttu-id="f245d-106">2016年10月21日には、米国国防総省 (DoD) によって最終的なルールが発行され、防衛業者に対して修正を適用し、保護されたインシデントとサイバーインシデントの報告に関する義務を課すことがあります。システムは、カバーされた防衛情報 (CDI) を処理、保存、または送信します。</span><span class="sxs-lookup"><span data-stu-id="f245d-106">On October 21, 2016, the Department of Defense (DoD) issued its Final Rule amending the Defense Federal Acquisition Regulation Supplement (DFARS) and imposing safeguarding and cyber incident reporting obligations on defense contractors whose information systems process, store, or transmit covered defense information (CDI).</span></span>  
  
<span data-ttu-id="f245d-107">最後の DFARS – 7012 (カバーされた防衛情報およびサイバーインシデントレポートを保護する) は、サイバーインシデントレポートの要件と、クラウドサービスプロバイダーの追加の考慮事項を含めるための保護を指定します。</span><span class="sxs-lookup"><span data-stu-id="f245d-107">The final DFARS clause 252.204–7012 (Safeguarding Covered Defense Information and Cyber Incident Reporting) specifies safeguards to include cyber incident reporting requirements and additional considerations for cloud service providers.</span></span> <span data-ttu-id="f245d-108">DFARS 252.204 –7012では、すべての DoD 請負業者および国防工業基盤において、適切なセキュリティのための DFARS 要件に準拠する必要があります。ただし、2017年12月31日より後ではありません。</span><span class="sxs-lookup"><span data-stu-id="f245d-108">Per DFARS 252.204–7012, all DoD contractors and the defense industrial base are required to comply with DFARS requirements for adequate security “as soon as practical, but not later than December 31, 2017.”</span></span>

## <a name="microsoft-and-dfars"></a><span data-ttu-id="f245d-109">Microsoft および DFARS お持ち</span><span class="sxs-lookup"><span data-stu-id="f245d-109">Microsoft and DFARS</span></span>

<span data-ttu-id="f245d-110">Microsoft Government Cloud services では、米国国防総省の基本および防衛請負業者のお客様が、252.204-7012 の DFARS に列挙されている、クラウドサービスプロバイダーに適用される DFARS 要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="f245d-110">Microsoft Government Cloud services help the United States defense industrial base and defense contractor customers meet the DFARS requirements as enumerated in the DFARS clauses of 252.204-7012 that apply to cloud service providers.</span></span> <span data-ttu-id="f245d-111">契約請負業者が、7012の DFARS –に準拠する必要がある場合、Microsoft は、Azure Government および Office 365 米国政府機関向けの米国政府防衛サービスのためのクラウドサービスプロバイダーに適用される要件をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="f245d-111">When defense contractors are required to comply with DFARS clause 252.204–7012 in contracts, Microsoft can support the requirements applicable to cloud service providers for Azure Government and Office 365 U.S. Government Defense services.</span></span> <span data-ttu-id="f245d-112">両方のサービスは、お客様が、「国防総省のセキュリティ要件ガイド」に対する L5 認定によって DFARS 7012 の条項に準拠するために必要な機能のサポートを示しています。</span><span class="sxs-lookup"><span data-stu-id="f245d-112">Both services demonstrate support for the capabilities necessary for customers to comply with the DFARS 7012 clauses through their L5 accreditation to the Department of Defense Security Requirements Guide.</span></span>  
  
<span data-ttu-id="f245d-113">Azure セキュリティおよびコンプライアンスブループリントを使用して、DFARS 迅速に展開する方法について説明します。「 [azure をダウンロードする」: 「青写真のお客様の責任マトリックス](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=7ed1b47c-b180-4323-9aec-21712d54b167&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_DoD_Blueprint)</span><span class="sxs-lookup"><span data-stu-id="f245d-113">Learn how to accelerate your DFARS deployment with our Azure Security and Compliance Blueprint: [Download the Azure — Blueprint DFARS Customer Responsibilities Matrix](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=7ed1b47c-b180-4323-9aec-21712d54b167&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_DoD_Blueprint)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="f245d-114">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="f245d-114">Microsoft in-scope cloud services</span></span>

<span data-ttu-id="f245d-115">DoD 影響レベル5の対象となるサービス</span><span class="sxs-lookup"><span data-stu-id="f245d-115">Covered services for DoD Impact Level 5</span></span>

- [<span data-ttu-id="f245d-116">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="f245d-116">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="f245d-117">Office 365 米国政府機関および Office 365 米国政府機関の防御</span><span class="sxs-lookup"><span data-stu-id="f245d-117">Office 365 U.S. Government and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="f245d-118">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="f245d-118">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="f245d-119">Microsoft クラウドサービスの承認</span><span class="sxs-lookup"><span data-stu-id="f245d-119">Microsoft Cloud Services Authorizations</span></span>](https://marketplace.fedramp.gov/index.html#/products?status=Compliant&sort=productName)
- [<span data-ttu-id="f245d-120">Azure P-ATO レター (2017 年3月3日)</span><span class="sxs-lookup"><span data-stu-id="f245d-120">Azure P-ATO Letter Signed March 3, 2017</span></span>](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=94ff5b42-4077-4612-8cf7-3194ded323dc&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)
- [<span data-ttu-id="f245d-121">その他の監査レポートを見る</span><span class="sxs-lookup"><span data-stu-id="f245d-121">See additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="f245d-122">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="f245d-122">Frequently asked questions</span></span>

<span data-ttu-id="f245d-123">**Microsoft Azure Government および Office 365 の米国政府機関によってサポートされている DFARS 要件は何ですか。**</span><span class="sxs-lookup"><span data-stu-id="f245d-123">**Which DFARS requirements are supported by Microsoft Azure Government and Office 365 U.S. Government Defense?**</span></span>

<span data-ttu-id="f245d-124">Azure 自治体および Office 365 の米国政府による防衛を利用することにより、技術部門の 252.204-7012 の DFARS 列挙された、クラウドサービスプロバイダーに適用されるの dfars 要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="f245d-124">Azure Government and Office 365 U.S. Government Defense allow our defense industrial base and defense contractor customers to meet the DFARS requirements as enumerated in the DFARS clauses of 252.204-7012 that apply to cloud service providers.</span></span>

<span data-ttu-id="f245d-125">**独立した査定官があります。これは、Azure 自治体および Office 365 の米国政府機関が DFARS 要件をサポートしているかどうかを検証しました**</span><span class="sxs-lookup"><span data-stu-id="f245d-125">**Has an independent assessor validated that Azure Government and Office 365 U.S. Government Defense supports DFARS requirements?**</span></span>

<span data-ttu-id="f245d-126">はい。サードパーティの評価組織には、Azure 自治体および Office 365 の米国政府防衛機関のクラウドサービスサービスが DFARS –7012の該当する要件を満たしていることが attested されています (未分類の統制された技術の保護情報)。</span><span class="sxs-lookup"><span data-stu-id="f245d-126">Yes, a third-party assessment organization has attested that the Azure Government and Office 365 U.S. Government Defense cloud service offering meets the applicable requirements of DFARS Clause 252.204–7012 (Safeguarding Unclassified Controlled Technical Information).</span></span>

<span data-ttu-id="f245d-127">**統制されていない未分類情報 (CUI) と対象となる防衛情報 (CDI) の関係は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="f245d-127">**What is the relationship between Controlled Unclassified Information (CUI) and covered defense information (CDI)?**</span></span>

<span data-ttu-id="f245d-128">CUI は、法律、規制、または政府全体のポリシーに従って、保護または disseminating の制御を必要とする情報です。</span><span class="sxs-lookup"><span data-stu-id="f245d-128">CUI is information that requires safeguarding or disseminating controls according to law, regulation, or government-wide policy.</span></span> <span data-ttu-id="f245d-129">[Cui レジストリ](https://www.archives.gov/cui/registry/category-list.html)は、承認された cui カテゴリとサブカテゴリを識別します。</span><span class="sxs-lookup"><span data-stu-id="f245d-129">The [CUI Registry](https://www.archives.gov/cui/registry/category-list.html) identifies approved CUI categories and subcategories.</span></span>

<span data-ttu-id="f245d-130">CDI は、制御された技術情報またはその他の情報 (CUI レジストリで説明) で、コントロールの保護または伝達を必要とするものであり、次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="f245d-130">CDI is controlled technical information or other information (as described in the CUI Registry) that requires safeguarding or dissemination controls and is either:</span></span>

- <span data-ttu-id="f245d-131">契約または契約の業績に関連して、契約書、タスクオーダー、または納入注文でマークされているか、または DoD の代理として提供されています。</span><span class="sxs-lookup"><span data-stu-id="f245d-131">Marked or otherwise identified in the contract, task order, or delivery order, and provided to the contractor by or on behalf of DoD in connection with the performance of the contract or</span></span>
- <span data-ttu-id="f245d-132">契約書のパフォーマンスをサポートするために、請負業者による収集、開発、受信、送信、使用、または契約者の代理としての保存</span><span class="sxs-lookup"><span data-stu-id="f245d-132">Collected, developed, received, transmitted, used, or stored by or on behalf of the contractor in support of the performance of the contract</span></span>

<span data-ttu-id="f245d-133">**すべての Microsoft サービスが、DFARS 規制下の「対象となる防衛情報」に該当する「適切なセキュリティ」要件を満たしているか。**</span><span class="sxs-lookup"><span data-stu-id="f245d-133">**Do all Microsoft services meet the “adequate security” requirements applicable to “covered defense information” under the DFARS regulation?**</span></span>

<span data-ttu-id="f245d-134">2016年10月に、国防総省 (DoD) は、「対象となる防衛情報」を通じて処理、保存、または送信するすべての DoD 請負業者に適用される、連邦防御法補足 (DFARS) 句を実装する最終規則を規定しています。情報システム。</span><span class="sxs-lookup"><span data-stu-id="f245d-134">In October 2016, the Department of Defense (DoD) promulgated a final rule implementing Defense Federal Acquisition Regulation Supplement (DFARS) clauses that apply to all DoD contractors who process, store, or transmit “covered defense information” through their information systems.</span></span> <span data-ttu-id="f245d-135">このようなシステムは、NIST SP 800 –171で規定されているセキュリティ要件を満たしている必要があります。[連邦情報システムや組織内の規制](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-171.pdf)されていない未分類情報を保護すること、または DoD 契約責任者によって承認された「代替、同等の効果的なセキュリティ対策」。</span><span class="sxs-lookup"><span data-stu-id="f245d-135">The rule states that such systems must meet the security requirements set forth in NIST SP 800–171, [Protecting Controlled Unclassified Information in nonfederal information systems and organizations](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-171.pdf), or an “alternative, but equally effective, security measure” that is approved by the DoD contracting officer.</span></span> <span data-ttu-id="f245d-136">また、DoD 請負業者は、対象となる防御情報を処理、保存、または送信するために外部クラウドサービスプロバイダーを使用する必要があります。このプロバイダーは、FedRAMP の適度なベースラインと同等のセキュリティ要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f245d-136">And where a DoD contractor uses an external cloud service provider to process, store, or transmit covered defense information, such provider must meet security requirements that are equivalent to the FedRAMP Moderate baseline.</span></span>

<span data-ttu-id="f245d-137">次の Microsoft クラウドサービスは、FedRAMP の中程度の承認を受け取り、DFARS 場合は、Azure Government、Dynamics 365 米国政府、Office 365 米国政府機関、および Office 365 米国政府機関との間で十分です。</span><span class="sxs-lookup"><span data-stu-id="f245d-137">The following Microsoft cloud services have received a FedRAMP moderate authorization and are adequate for DFARS: Azure Government, Dynamics 365 U.S. Government, Office 365 U.S. Government, and Office 365 U.S. Government Defense.</span></span>

<span data-ttu-id="f245d-138">また、「対象の防衛情報」を処理、保存、または送信するために DoD 請負業者によって使用される可能性がある、FedRAMP 認証された境界外の Microsoft 製品については、2017年12月31日のコンプライアンスの期限に達したことをレビューしています。</span><span class="sxs-lookup"><span data-stu-id="f245d-138">Also, Microsoft offerings outside the FedRAMP-certified boundary that could potentially be used by DoD contractors to process, store, or transmit “covered defense information” are undergoing a review to meet a December 31, 2017, compliance deadline.</span></span> <span data-ttu-id="f245d-139">Microsoft は、このような内部サービスおよび顧客向けサービスが、DFARS 800 –171または適切なセキュリティ同等のものに準拠しているかどうかを文書化して、dfars 関連する句を満たすようにしています。</span><span class="sxs-lookup"><span data-stu-id="f245d-139">Microsoft is working to document how these internal and customer-facing services comply with NIST SP 800–171 or an acceptable security equivalent, to meet the DFARS relevant clauses.</span></span>

## <a name="resources"></a><span data-ttu-id="f245d-140">リソース</span><span class="sxs-lookup"><span data-stu-id="f245d-140">Resources</span></span>

- [<span data-ttu-id="f245d-141">連邦政府機関買収規制補足 (DFARS dfars)</span><span class="sxs-lookup"><span data-stu-id="f245d-141">Defense Federal Acquisition Regulation Supplement (DFARS)</span></span>](https://www.acq.osd.mil/dpap/dars/dfarspgi/current/index.html)
- [<span data-ttu-id="f245d-142">Microsoft Cloud for Government</span><span class="sxs-lookup"><span data-stu-id="f245d-142">Microsoft Cloud for Government</span></span>](https://enterprise.microsoft.com/industries/government/start-your-microsoft-cloud-for-government-trial-today)
- [<span data-ttu-id="f245d-143">オンライン サービスの使用条件</span><span class="sxs-lookup"><span data-stu-id="f245d-143">Online Services Terms</span></span>](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [<span data-ttu-id="f245d-144">制御されていない未分類の情報 (CUI)</span><span class="sxs-lookup"><span data-stu-id="f245d-144">Controlled Unclassified Information (CUI)</span></span>](https://www.archives.gov/cui/registry/category-list)
- [<span data-ttu-id="f245d-145">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="f245d-145">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
