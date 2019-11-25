---
title: Service Organization Controls (SOC)
description: Microsoft クラウド サービスは、運用セキュリティについて Service Organization Controls 基準に準拠しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: c773d2e4f69b415745e0a327e497ce26ed62c223
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "39218676"
---
# <a name="compliance-offering-service-organization-controls-soc"></a><span data-ttu-id="3ebf1-104">コンプライアンス サービス: Service Organization Controls (SOC)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-104">Compliance offering: Service Organization Controls (SOC)</span></span>

## <a name="soc-1-2-and-3-reports-overview"></a><span data-ttu-id="3ebf1-105">SOC 1、2、3 報告書の概要</span><span class="sxs-lookup"><span data-stu-id="3ebf1-105">SOC 1, 2, and 3 Reports overview</span></span>

<span data-ttu-id="3ebf1-106">データ ストレージ、アプリケーションへのアクセスなど、基本的な機能をクラウド サービス プロバイダー (CSP) やその他のサービス組織にアウトソースするビジネスが増えています。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-106">Increasingly, businesses outsource basic functions such as data storage and access to applications to cloud service providers (CSPs) and other service organizations.</span></span> <span data-ttu-id="3ebf1-107">これを受けて、米国公認会計士協会 (American Institute of Certified Public Accountants: AICPA) は、クラウドで保存および処理される情報の機密性とプライバシーを保護する制御基準である Service Organization Controls (SOC) フレームワークを策定しました。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-107">In response, the American Institute of Certified Public Accountants (AICPA) has developed the Service Organization Controls (SOC) framework, a standard for controls that safeguard the confidentiality and privacy of information stored and processed in the cloud.</span></span> <span data-ttu-id="3ebf1-108">これは、国際サービス組織の報告書作成基準である 国際保証業務基準 (International Standard on Assurance Engagements: ISAE) に合致するものです。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-108">This aligns with the International Standard on Assurance Engagements (ISAE), the reporting standard for international service organizations.</span></span>

<span data-ttu-id="3ebf1-109">SOC フレームワークに基づくサービス監査は、SOC 1 と SOC 2 の 2 つに分類され、対象となる Microsoft クラウド サービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-109">Service audits based on the SOC framework fall into two categories — SOC 1 and SOC 2 — that apply to in-scope Microsoft cloud services.</span></span>

<span data-ttu-id="3ebf1-110">SOC 1 監査は、財務諸表を監査する公認会計士事務所を対象としており、プロバイダーのクラウド サービスを使用している顧客の財務報告に影響する、CSP の内部コントロールの有効性を評価します。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-110">A SOC 1 audit, intended for CPA firms that audit financial statements, evaluates the effectiveness of a CSP’s internal controls that affect the financial reports of a customer using the provider’s cloud services.</span></span> <span data-ttu-id="3ebf1-111">監査は保証業務基準書 (SSAE 18) および国際保証業務基準書第 </span><span class="sxs-lookup"><span data-stu-id="3ebf1-111">The Statement on Standards for Attestation Engagements (SSAE 18) and the International Standards for Assurance Engagements No.</span></span> <span data-ttu-id="3ebf1-112">3402 号 (ISAE 3402) を基準として実施され、これを基に SOC 1 報告書が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-112">3402 (ISAE 3402) are the standards under which the audit is performed, and is the basis of the SOC 1 report.</span></span>

<span data-ttu-id="3ebf1-113">SOC 2 監査では、AICPA Trust Service Principles and Criteria に基づいて CSP のシステムの有効性を評価します。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-113">A SOC 2 audit gauges the effectiveness of a CSP’s system based on the AICPA Trust Service Principles and Criteria.</span></span> <span data-ttu-id="3ebf1-114">Attestation Standards (AT) Section 101 の Attest Engagement を基に SOC 2 および SOC 3 報告書が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-114">An Attest Engagement under Attestation Standards (AT) Section 101 is the basis of SOC 2 and SOC 3 reports.</span></span>

<span data-ttu-id="3ebf1-115">SOC 1 または SOC 2 監査の終了時、サービス監査人は SOC 1 Type 2 または SOC 2 Type 2 報告書で意見を述べます。報告書では、CSP のシステムについて説明し、CSP による自身の制御の説明の正当性を評価します。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-115">At the conclusion of a SOC 1 or SOC 2 audit, the service auditor renders an opinion in a SOC 1 Type 2 or SOC 2 Type 2 report, which describes the CSP’s system and assesses the fairness of the CSP’s description of its controls.</span></span> <span data-ttu-id="3ebf1-116">また、CSP の制御が適切に設計されているかどうか、指定した日付に実行されていたか、また、指定した期間に正常に運用されていたかも評価します。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-116">It also evaluates whether the CSP’s controls are designed appropriately, were in operation on a specified date, and were operating effectively over a specified time period.</span></span>

<span data-ttu-id="3ebf1-117">監査人は SOC 3 報告書を作成することもできます。これは、SOC 2 Type 2 監査報告書が簡略化されたもので、CSP の制御についての保証は必要なものの、完全な SOC 2 報告書を必要としないユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-117">Auditors can also create a SOC 3 report — an abbreviated version of the SOC 2 Type 2 audit report — for users who want assurance about the CSP’s controls but don’t need a full SOC 2 report.</span></span> <span data-ttu-id="3ebf1-118">SOC 3 報告書を提供できるのは、CSP が SOC 2 で無限定適正意見を得ている場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-118">A SOC 3 report can be conferred only if the CSP has an unqualified audit opinion for SOC 2.</span></span>

## <a name="microsoft-and-soc-1-2-and-3-reports"></a><span data-ttu-id="3ebf1-119">Microsoft と SOC 1、2、3 報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-119">Microsoft and SOC 1, 2, and 3 Reports</span></span>

<span data-ttu-id="3ebf1-120">Microsoft の対象クラウド サービスは、少なくとも年に 1 回、独立第三者監査機関による監査が SOC 報告フレームワークに照らして実施されています。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-120">Microsoft covered cloud services are audited at least annually against the SOC reporting framework by independent third-party auditors.</span></span> <span data-ttu-id="3ebf1-121">Microsoft クラウド サービスの監査は、サービスごとに適用される信頼の原則に従って、データ セキュリティ、可用性、処理の整合性、および機密性の制御が対象となります。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-121">The audit for Microsoft cloud services covers controls for data security, availability, processing integrity, and confidentiality as applicable to in-scope trust principles for each service.</span></span>

<span data-ttu-id="3ebf1-122">Microsoft では、SOC 1 Type 2、SOC 2 Type 2、および SOC 3 報告書を取得しています。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-122">Microsoft has achieved SOC 1 Type 2, SOC 2 Type 2, and SOC 3 reports.</span></span> <span data-ttu-id="3ebf1-123">原則として、SOC 1 報告書と SOC 2 報告書は、Microsoft と秘密保持契約を結んでいるお客様しか入手できませんが、SOC 3 報告書は公開されています。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-123">In general, the availability of SOC 1 and SOC 2 reports is restricted to customers who have signed nondisclosure agreements with Microsoft; the SOC 3 report is publicly available.</span></span>

<span data-ttu-id="3ebf1-124">Microsoft クラウドにおける SOC 1、2、3 の利点の詳細: [SOC 1 および SOC 2 Type 2 の背景解説のダウンロード](https://aka.ms/soc_backgrounder)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-124">Learn about the benefits of SOC 1, 2, 3 on the Microsoft Cloud: [Download the SOC 1 and SOC 2 type 2 reports backgrounder](https://aka.ms/soc_backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="3ebf1-125">対象 Microsoft クラウド サービス</span><span class="sxs-lookup"><span data-stu-id="3ebf1-125">Microsoft in-scope cloud services</span></span>

### <a name="covered-services-for-soc-1-and-soc-2"></a><span data-ttu-id="3ebf1-126">SOC 1 および SOC 2 の対象サービス</span><span class="sxs-lookup"><span data-stu-id="3ebf1-126">Covered services for SOC 1 and SOC 2</span></span>

- <span data-ttu-id="3ebf1-127">Azure、Azure Government、および Azure Germany [詳細リスト](https://aka.ms/AzureCompliance)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-127">Azure, Azure Government, and Azure Germany [detailed list](https://aka.ms/AzureCompliance)</span></span>
- <span data-ttu-id="3ebf1-128">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3ebf1-128">Cloud App Security</span></span>
- <span data-ttu-id="3ebf1-129">Dynamics 365 および Dynamics 365 U.S. Government [詳細リスト](https://aka.ms/d365-compliance-list)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-129">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="3ebf1-130">Graph</span><span class="sxs-lookup"><span data-stu-id="3ebf1-130">Graph</span></span>
- <span data-ttu-id="3ebf1-131">Intune</span><span class="sxs-lookup"><span data-stu-id="3ebf1-131">Intune</span></span>
- <span data-ttu-id="3ebf1-132">Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-132">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="3ebf1-133">Office 365、Office 365 U.S. Government、および Office 365 U.S. Government Defense [詳細リスト](https://go.microsoft.com/fwlink/p/?LinkID=2077751)。Yammer は SOC 1 Type 1 報告書を取得しています。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-133">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense [detailed list](https://go.microsoft.com/fwlink/p/?LinkID=2077751); Yammer has achieved a SOC 1 Type 1 report</span></span>
- <span data-ttu-id="3ebf1-134">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="3ebf1-134">Office 365 Germany</span></span>
- <span data-ttu-id="3ebf1-135">PowerApps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-135">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="3ebf1-136">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-136">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="3ebf1-137">Stream</span><span class="sxs-lookup"><span data-stu-id="3ebf1-137">Stream</span></span>
- <span data-ttu-id="3ebf1-138">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="3ebf1-138">Azure DevOps Services</span></span>

### <a name="covered-services-for-soc-3"></a><span data-ttu-id="3ebf1-139">SOC 3 の対象サービス</span><span class="sxs-lookup"><span data-stu-id="3ebf1-139">Covered services for SOC 3</span></span>

- <span data-ttu-id="3ebf1-140">Azure、Azure Government、および Azure Germany [詳細リスト](https://aka.ms/AzureCompliance)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-140">Azure, Azure Government, and Azure Germany [detailed list](https://aka.ms/AzureCompliance)</span></span>
- <span data-ttu-id="3ebf1-141">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3ebf1-141">Cloud App Security</span></span>
- <span data-ttu-id="3ebf1-142">Graph</span><span class="sxs-lookup"><span data-stu-id="3ebf1-142">Graph</span></span>
- <span data-ttu-id="3ebf1-143">Intune</span><span class="sxs-lookup"><span data-stu-id="3ebf1-143">Intune</span></span>
- <span data-ttu-id="3ebf1-144">Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-144">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="3ebf1-145">PowerApps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="3ebf1-145">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="3ebf1-146">Power BI</span><span class="sxs-lookup"><span data-stu-id="3ebf1-146">Power BI</span></span>
- <span data-ttu-id="3ebf1-147">Stream</span><span class="sxs-lookup"><span data-stu-id="3ebf1-147">Stream</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="3ebf1-148">監査、報告書、証明書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-148">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="3ebf1-149">監査サイクル</span><span class="sxs-lookup"><span data-stu-id="3ebf1-149">Audit cycle</span></span>

<span data-ttu-id="3ebf1-150">Microsoft クラウド サービスでは、少なくとも年に 1 回、SOC 1 (SSAE18、ISAE 3402) および SOC 2 (AT Section 101) 基準に照らした監査が実施されます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-150">Microsoft cloud services are audited at least annually against SOC 1 (SSAE18, ISAE 3402) and SOC 2 (AT Section 101) standards.</span></span>

#### <a name="azure-cloud-app-security-flow-graph-intune-power-bi-powerapps-stream-and-microsoft-datacenters"></a><span data-ttu-id="3ebf1-151">Azure、Cloud App Security、Flow、Graph、Intune、Power BI、Power Apps、Stream、Microsoft データセンター</span><span class="sxs-lookup"><span data-stu-id="3ebf1-151">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters</span></span>

- [<span data-ttu-id="3ebf1-152">Azure および Azure Government の SOC 1 Type 2 報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-152">Azure and Azure Government SOC 1 Type 2 Report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2099601)
- [<span data-ttu-id="3ebf1-153">Azure および Azure Government の SOC 2 Type 2 報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-153">Azure and Azure Government SOC 2 Type 2 Report</span></span>](https://aka.ms/azuresoc2auditreport)
- [<span data-ttu-id="3ebf1-154">Azure および Azure Government の SOC 3 報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-154">Azure and Azure Government SOC 3 Report</span></span>](https://aka.ms/azuresoc3auditreport)

#### <a name="dynamics-365"></a><span data-ttu-id="3ebf1-155">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3ebf1-155">Dynamics 365</span></span>

- [<span data-ttu-id="3ebf1-156">Dynamics 365 SOC 1 Type 2 報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-156">Dynamics 365 SOC 2 Type 2 Report & Bridge Letter</span></span>](https://aka.ms/Dynamics365SOC1AuditReport)
- [<span data-ttu-id="3ebf1-157">Dynamics 365 SOC 2 AT 101 Type II 監査報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-157">Dynamics 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Dynamics365SOC2AuditReport)
- [<span data-ttu-id="3ebf1-158">ブリッジ レターおよびその他の監査報告書を参照する</span><span class="sxs-lookup"><span data-stu-id="3ebf1-158">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

#### <a name="office-365"></a><span data-ttu-id="3ebf1-159">Office 365</span><span class="sxs-lookup"><span data-stu-id="3ebf1-159">Office 365</span></span>

- [<span data-ttu-id="3ebf1-160">Office 365 SOC 1 SSAE 16 Type II 監査報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-160">Office 365 SOC 1 SSAE 16 Type II Audit Report</span></span>](https://aka.ms/office365soc1auditreport)
- [<span data-ttu-id="3ebf1-161">Office 365 SOC 2 AT 101 Type II 監査報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-161">Office 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Office365SOC2AuditReport)
- [<span data-ttu-id="3ebf1-162">Office 365 Customer Lockbox SOC 1 SSAE 16 監査報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-162">Office 365 Customer Lockbox SOC 1 SSAE 16 Audit Report</span></span>](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [<span data-ttu-id="3ebf1-163">Yammer SOC 2 AT 101 Type II 監査報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-163">Yammer SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/YammerSOC2AuditReport)
- [<span data-ttu-id="3ebf1-164">Yammer SOC 2 AT 101 Type I 監査報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-164">Yammer SOC 2 AT 101 Type I Audit Report</span></span>](https://aka.ms/YammerSOC2Type1AuditReport)
- [<span data-ttu-id="3ebf1-165">ブリッジ レターおよびその他の監査報告書を参照する</span><span class="sxs-lookup"><span data-stu-id="3ebf1-165">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="3ebf1-166">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3ebf1-166">Frequently asked questions</span></span>

<span data-ttu-id="3ebf1-167">**SOC 報告書のコピーはどのようにして入手できますか?**</span><span class="sxs-lookup"><span data-stu-id="3ebf1-167">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="3ebf1-168">監査人は、報告書を使って、Microsoft ビジネス クラウド サービスの結果と顧客の法的規制要件を比較できます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-168">With the reports, your auditors can compare Microsoft business cloud services results with your own legal and regulatory requirements.</span></span>

- <span data-ttu-id="3ebf1-169">[Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx)を使用して、すべての SOC 報告書を閲覧できます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-169">You can see all SOC reports through the [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx).</span></span>
- <span data-ttu-id="3ebf1-170">Azure DevOps のサービスをご利用のお客様で、[Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) にアクセスできないお客様は、お客様の SOC 1 および SOC 2 報告書については [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) にメールでご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-170">Azure DevOps Service customers that can’t access [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) can email [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) for its SOC 1 and SOC 2 reports.</span></span> <span data-ttu-id="3ebf1-171">このメールは、Azure DevOps SOC 報告書の要求のみにご使用ください。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-171">This email is to request Azure DevOps SOC reports only.</span></span>

<span data-ttu-id="3ebf1-172">**Azure SOC 報告書が発行される頻度はどれくらいですか?**</span><span class="sxs-lookup"><span data-stu-id="3ebf1-172">**How often are Azure SOC reports issued?**</span></span>

<span data-ttu-id="3ebf1-173">Azure、Cloud App Security、Flow、Graph、Intune、Power BI、PowerApps、Stream、Microsoft データセンターの SOC 報告書は、12 か月連続の実行期間 (監査期間) に基づいており、四半期ごとに新たな報告書が発行されます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-173">SOC reports for Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters are based on a rolling 12-month run window (audit period) with new reports issued quarterly.</span></span> <span data-ttu-id="3ebf1-174">SOC 報告書を通じて監査の頻度が増加することにより、監査期間の対象範囲がさらに時宜を得たものとなり、ブリッジ レターと比較して、より確実な保証が外部監査役により提供されます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-174">The increased audit frequency provides a more timely audit period coverage through a SOC report, which provides greater assurance by an external auditor when compared to a bridge letter.</span></span> <span data-ttu-id="3ebf1-175">最新の報告書は Service Trust Portal から[ダウンロード](https://aka.ms/stp)できます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-175">Customers can [download](https://aka.ms/stp) the latest reports from the Service Trust Portal.</span></span>

<span data-ttu-id="3ebf1-176">**Microsoft データセンターの監査は、自分自身で実施する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="3ebf1-176">**Do I need to conduct my own audit of Microsoft datacenters?**</span></span>

<span data-ttu-id="3ebf1-177">いいえ。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-177">No.</span></span> <span data-ttu-id="3ebf1-178">Microsoft では、Microsoft のセキュリティ コミットメントに Microsoft が準拠していることを確認していただけるように、第三者監査報告書と認定をお客様にも公開しています。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-178">Microsoft shares the independent audit reports and certifications with customers so that they can verify Microsoft compliance with its security commitments.</span></span>

<span data-ttu-id="3ebf1-179">**Microsoft のコンプライアンスを自分の組織の認定プロセスに利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="3ebf1-179">**Can I use Microsoft’s compliance in my organization’s certification process?**</span></span>

<span data-ttu-id="3ebf1-180">はい。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-180">Yes.</span></span> <span data-ttu-id="3ebf1-181">対象となる Microsoft クラウド サービスにアプリケーションやデータを移行する場合、Microsoft が保持する監査と認定を利用できます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-181">When you migrate your applications and data to covered Microsoft cloud services, you can build on the audits and certifications that Microsoft holds.</span></span> <span data-ttu-id="3ebf1-182">お客様のデータのセキュリティとプライバシーを維持するために Microsoft が実装してきた制御の有効性が第三者報告書により証明されます。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-182">The independent reports attest to the effectiveness of controls that Microsoft has implemented to help maintain the security and privacy of your data.</span></span>

<span data-ttu-id="3ebf1-183">**組織でのコンプライアンス活動は、何から始めればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="3ebf1-183">**Where do I start with my organization’s own compliance effort?**</span></span>

<span data-ttu-id="3ebf1-184">[SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) は、SOC 報告書のプロセスを理解し、組織で報告書の利用を促進する上で役立つリソースです。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-184">The [SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) is a helpful resource for understanding SOC reporting processes and promoting your organization’s use of them.</span></span>

## <a name="resources"></a><span data-ttu-id="3ebf1-185">リソース</span><span class="sxs-lookup"><span data-stu-id="3ebf1-185">Resources</span></span>

 - [<span data-ttu-id="3ebf1-186">Microsoft クラウド サービスによるデータの保護の強化</span><span class="sxs-lookup"><span data-stu-id="3ebf1-186">Better protect your data by using Microsoft cloud services</span></span>](https://www.microsoft.com/trustcenter/guidance/protect-data)
 - [<span data-ttu-id="3ebf1-187">Service Organization Control (SOC) 報告書</span><span class="sxs-lookup"><span data-stu-id="3ebf1-187">Service Organization Control (SOC) Reports</span></span>](https://aka.ms/mssocreports)
 - [<span data-ttu-id="3ebf1-188">SSAE 16 監査基準</span><span class="sxs-lookup"><span data-stu-id="3ebf1-188">SSAE 16 Auditing Standard</span></span>](https://www.ssae-16.com/)
 - [<span data-ttu-id="3ebf1-189">ISAE 3402 基準</span><span class="sxs-lookup"><span data-stu-id="3ebf1-189">ISAE 3402 Standard</span></span>](https://isae3402.com/)
 - [<span data-ttu-id="3ebf1-190">Microsoft Common Controls Hub コンプライアンス フレームワーク</span><span class="sxs-lookup"><span data-stu-id="3ebf1-190">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
 - [<span data-ttu-id="3ebf1-191">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="3ebf1-191">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
 - [<span data-ttu-id="3ebf1-192">Microsoft Government クラウド</span><span class="sxs-lookup"><span data-stu-id="3ebf1-192">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
 - [<span data-ttu-id="3ebf1-193">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="3ebf1-193">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="3ebf1-194">サービスの背景資料をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="3ebf1-194">Download the offering backgrounder</span></span>

<span data-ttu-id="3ebf1-195">このサービスに関する背景資料が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="3ebf1-195">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="3ebf1-196">[PDF](https://download.microsoft.com/download/F/E/1/FE10DD69-B5A9-4DA7-A86A-1F565D2B6472/SOC_backgrounder-2018.pdf) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3ebf1-196">Download the [PDF](https://download.microsoft.com/download/F/E/1/FE10DD69-B5A9-4DA7-A86A-1F565D2B6472/SOC_backgrounder-2018.pdf).</span></span>
