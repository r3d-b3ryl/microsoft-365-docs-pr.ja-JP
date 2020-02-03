---
title: Service Organization Controls (SOC)
description: Microsoft クラウド サービスは、運用セキュリティについて Service Organization Controls 基準に準拠しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 57d4093712efbee7bcb4f27280b0ba64a50dbe41
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662023"
---
# <a name="service-organization-controls-soc"></a><span data-ttu-id="62a57-104">Service Organization Controls (SOC)</span><span class="sxs-lookup"><span data-stu-id="62a57-104">Service Organization Controls (SOC)</span></span>

## <a name="soc-1-2-and-3-reports-overview"></a><span data-ttu-id="62a57-105">SOC 1、2、3 報告書の概要</span><span class="sxs-lookup"><span data-stu-id="62a57-105">SOC 1, 2, and 3 Reports overview</span></span>

<span data-ttu-id="62a57-106">データ ストレージ、アプリケーションへのアクセスなど、基本的な機能をクラウド サービス プロバイダー (CSP) やその他のサービス組織にアウトソースするビジネスが増えています。</span><span class="sxs-lookup"><span data-stu-id="62a57-106">Increasingly, businesses outsource basic functions such as data storage and access to applications to cloud service providers (CSPs) and other service organizations.</span></span> <span data-ttu-id="62a57-107">これを受けて、米国公認会計士協会 (American Institute of Certified Public Accountants: AICPA) は、クラウドで保存および処理される情報の機密性とプライバシーを保護する制御基準である Service Organization Controls (SOC) フレームワークを策定しました。</span><span class="sxs-lookup"><span data-stu-id="62a57-107">In response, the American Institute of Certified Public Accountants (AICPA) has developed the Service Organization Controls (SOC) framework, a standard for controls that safeguard the confidentiality and privacy of information stored and processed in the cloud.</span></span> <span data-ttu-id="62a57-108">これは、国際サービス組織の報告書作成基準である 国際保証業務基準 (International Standard on Assurance Engagements: ISAE) に合致するものです。</span><span class="sxs-lookup"><span data-stu-id="62a57-108">This aligns with the International Standard on Assurance Engagements (ISAE), the reporting standard for international service organizations.</span></span>

<span data-ttu-id="62a57-109">SOC フレームワークに基づくサービス監査は、SOC 1 と SOC 2 の 2 つに分類され、対象となる Microsoft クラウド サービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="62a57-109">Service audits based on the SOC framework fall into two categories — SOC 1 and SOC 2 — that apply to in-scope Microsoft cloud services.</span></span>

<span data-ttu-id="62a57-110">SOC 1 監査は、財務諸表を監査する公認会計士事務所を対象としており、プロバイダーのクラウド サービスを使用している顧客の財務報告に影響する、CSP の内部コントロールの有効性を評価します。</span><span class="sxs-lookup"><span data-stu-id="62a57-110">A SOC 1 audit, intended for CPA firms that audit financial statements, evaluates the effectiveness of a CSP’s internal controls that affect the financial reports of a customer using the provider’s cloud services.</span></span> <span data-ttu-id="62a57-111">監査は保証業務基準書 (SSAE 18) および国際保証業務基準書第 </span><span class="sxs-lookup"><span data-stu-id="62a57-111">The Statement on Standards for Attestation Engagements (SSAE 18) and the International Standards for Assurance Engagements No.</span></span> <span data-ttu-id="62a57-112">3402 号 (ISAE 3402) を基準として実施され、これを基に SOC 1 報告書が作成されます。</span><span class="sxs-lookup"><span data-stu-id="62a57-112">3402 (ISAE 3402) are the standards under which the audit is performed, and is the basis of the SOC 1 report.</span></span>

<span data-ttu-id="62a57-113">SOC 2 監査では、AICPA Trust Service Principles and Criteria に基づいて CSP のシステムの有効性を評価します。</span><span class="sxs-lookup"><span data-stu-id="62a57-113">A SOC 2 audit gauges the effectiveness of a CSP’s system based on the AICPA Trust Service Principles and Criteria.</span></span> <span data-ttu-id="62a57-114">Attestation Standards (AT) Section 101 の Attest Engagement を基に SOC 2 および SOC 3 報告書が作成されます。</span><span class="sxs-lookup"><span data-stu-id="62a57-114">An Attest Engagement under Attestation Standards (AT) Section 101 is the basis of SOC 2 and SOC 3 reports.</span></span>

<span data-ttu-id="62a57-115">SOC 1 または SOC 2 監査の終了時、サービス監査人は SOC 1 Type 2 または SOC 2 Type 2 報告書で意見を述べます。報告書では、CSP のシステムについて説明し、CSP による自身の制御の説明の正当性を評価します。</span><span class="sxs-lookup"><span data-stu-id="62a57-115">At the conclusion of a SOC 1 or SOC 2 audit, the service auditor renders an opinion in a SOC 1 Type 2 or SOC 2 Type 2 report, which describes the CSP’s system and assesses the fairness of the CSP’s description of its controls.</span></span> <span data-ttu-id="62a57-116">また、CSP の制御が適切に設計されているかどうか、指定した日付に実行されていたか、また、指定した期間に正常に運用されていたかも評価します。</span><span class="sxs-lookup"><span data-stu-id="62a57-116">It also evaluates whether the CSP’s controls are designed appropriately, were in operation on a specified date, and were operating effectively over a specified time period.</span></span>

<span data-ttu-id="62a57-117">監査人は SOC 3 報告書を作成することもできます。これは、SOC 2 Type 2 監査報告書が簡略化されたもので、CSP の制御についての保証は必要なものの、完全な SOC 2 報告書を必要としないユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="62a57-117">Auditors can also create a SOC 3 report — an abbreviated version of the SOC 2 Type 2 audit report — for users who want assurance about the CSP’s controls but don’t need a full SOC 2 report.</span></span> <span data-ttu-id="62a57-118">SOC 3 報告書を提供できるのは、CSP が SOC 2 で無限定適正意見を得ている場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="62a57-118">A SOC 3 report can be conferred only if the CSP has an unqualified audit opinion for SOC 2.</span></span>

## <a name="microsoft-and-soc-1-2-and-3-reports"></a><span data-ttu-id="62a57-119">Microsoft と SOC 1、2、3 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-119">Microsoft and SOC 1, 2, and 3 Reports</span></span>

<span data-ttu-id="62a57-120">Microsoft の対象クラウド サービスは、少なくとも年に 1 回、独立第三者監査機関による監査が SOC 報告フレームワークに照らして実施されています。</span><span class="sxs-lookup"><span data-stu-id="62a57-120">Microsoft covered cloud services are audited at least annually against the SOC reporting framework by independent third-party auditors.</span></span> <span data-ttu-id="62a57-121">Microsoft クラウド サービスの監査は、サービスごとに適用される信頼の原則に従って、データ セキュリティ、可用性、処理の整合性、および機密性の制御が対象となります。</span><span class="sxs-lookup"><span data-stu-id="62a57-121">The audit for Microsoft cloud services covers controls for data security, availability, processing integrity, and confidentiality as applicable to in-scope trust principles for each service.</span></span>

<span data-ttu-id="62a57-122">Microsoft では、SOC 1 Type 2、SOC 2 Type 2、および SOC 3 報告書を取得しています。</span><span class="sxs-lookup"><span data-stu-id="62a57-122">Microsoft has achieved SOC 1 Type 2, SOC 2 Type 2, and SOC 3 reports.</span></span> <span data-ttu-id="62a57-123">原則として、SOC 1 報告書と SOC 2 報告書は、Microsoft と秘密保持契約を結んでいるお客様しか入手できませんが、SOC 3 報告書は公開されています。</span><span class="sxs-lookup"><span data-stu-id="62a57-123">In general, the availability of SOC 1 and SOC 2 reports is restricted to customers who have signed nondisclosure agreements with Microsoft; the SOC 3 report is publicly available.</span></span>

<span data-ttu-id="62a57-124">Microsoft クラウドにおける SOC 1、2、3 の利点の詳細: [SOC 1 および SOC 2 Type 2 の背景解説のダウンロード](https://aka.ms/soc_backgrounder)</span><span class="sxs-lookup"><span data-stu-id="62a57-124">Learn about the benefits of SOC 1, 2, 3 on the Microsoft Cloud: [Download the SOC 1 and SOC 2 type 2 reports backgrounder](https://aka.ms/soc_backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="62a57-125">対象 Microsoft クラウド サービス</span><span class="sxs-lookup"><span data-stu-id="62a57-125">Microsoft in-scope cloud services</span></span>

### <a name="covered-services-for-soc-1-and-soc-2"></a><span data-ttu-id="62a57-126">SOC 1 および SOC 2 の対象サービス</span><span class="sxs-lookup"><span data-stu-id="62a57-126">Covered services for SOC 1 and SOC 2</span></span>

- [<span data-ttu-id="62a57-127">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="62a57-127">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="62a57-128">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="62a57-128">Cloud App Security</span></span>
- [<span data-ttu-id="62a57-129">Dynamics 365、Dynamics 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="62a57-129">Dynamics 365 and Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="62a57-130">Graph</span><span class="sxs-lookup"><span data-stu-id="62a57-130">Graph</span></span>
- <span data-ttu-id="62a57-131">Intune</span><span class="sxs-lookup"><span data-stu-id="62a57-131">Intune</span></span>
- <span data-ttu-id="62a57-132">Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="62a57-132">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="62a57-133">Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランまたはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="62a57-133">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="62a57-134">Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="62a57-134">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="62a57-135">Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="62a57-135">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="62a57-136">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="62a57-136">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="62a57-137">Stream</span><span class="sxs-lookup"><span data-stu-id="62a57-137">Stream</span></span>
- <span data-ttu-id="62a57-138">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="62a57-138">Azure DevOps Services</span></span>

### <a name="covered-services-for-soc-3"></a><span data-ttu-id="62a57-139">SOC 3 の対象サービス</span><span class="sxs-lookup"><span data-stu-id="62a57-139">Covered services for SOC 3</span></span>

- [<span data-ttu-id="62a57-140">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="62a57-140">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="62a57-141">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="62a57-141">Cloud App Security</span></span>
- <span data-ttu-id="62a57-142">Graph</span><span class="sxs-lookup"><span data-stu-id="62a57-142">Graph</span></span>
- <span data-ttu-id="62a57-143">Intune</span><span class="sxs-lookup"><span data-stu-id="62a57-143">Intune</span></span>
- <span data-ttu-id="62a57-144">Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="62a57-144">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="62a57-145">Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランまたはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="62a57-145">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="62a57-146">Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="62a57-146">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="62a57-147">Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="62a57-147">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="62a57-148">Power BI</span><span class="sxs-lookup"><span data-stu-id="62a57-148">Power BI</span></span>
- <span data-ttu-id="62a57-149">Stream</span><span class="sxs-lookup"><span data-stu-id="62a57-149">Stream</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="62a57-150">監査、報告書、証明書</span><span class="sxs-lookup"><span data-stu-id="62a57-150">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="62a57-151">監査サイクル</span><span class="sxs-lookup"><span data-stu-id="62a57-151">Audit cycle</span></span>

<span data-ttu-id="62a57-152">Microsoft クラウド サービスでは、少なくとも年に 1 回、SOC 1 (SSAE18、ISAE 3402) および SOC 2 (AT Section 101) 基準に照らした監査が実施されます。</span><span class="sxs-lookup"><span data-stu-id="62a57-152">Microsoft cloud services are audited at least annually against SOC 1 (SSAE18, ISAE 3402) and SOC 2 (AT Section 101) standards.</span></span>

#### <a name="azure-cloud-app-security-flow-graph-intune-power-bi-powerapps-stream-and-microsoft-datacenters"></a><span data-ttu-id="62a57-153">Azure、Cloud App Security、Flow、Graph、Intune、Power BI、Power Apps、Stream、Microsoft データセンター</span><span class="sxs-lookup"><span data-stu-id="62a57-153">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters</span></span>

- [<span data-ttu-id="62a57-154">Azure および Azure Government の SOC 1 Type 2 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-154">Azure and Azure Government SOC 1 Type 2 Report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2099601)
- [<span data-ttu-id="62a57-155">Azure および Azure Government の SOC 2 Type 2 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-155">Azure and Azure Government SOC 2 Type 2 Report</span></span>](https://aka.ms/azuresoc2auditreport)
- [<span data-ttu-id="62a57-156">Azure および Azure Government の SOC 3 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-156">Azure and Azure Government SOC 3 Report</span></span>](https://aka.ms/azuresoc3auditreport)

#### <a name="dynamics-365"></a><span data-ttu-id="62a57-157">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="62a57-157">Dynamics 365</span></span>

- [<span data-ttu-id="62a57-158">Dynamics 365 SOC 1 Type 2 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-158">Dynamics 365 SOC 1 Type 2 Report</span></span>](https://aka.ms/Dynamics365SOC1AuditReport)
- [<span data-ttu-id="62a57-159">Dynamics 365 SOC 2 AT 101 Type II 監査報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-159">Dynamics 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Dynamics365SOC2AuditReport)
- [<span data-ttu-id="62a57-160">ブリッジ レターおよびその他の監査報告書を参照する</span><span class="sxs-lookup"><span data-stu-id="62a57-160">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

#### <a name="office-365"></a><span data-ttu-id="62a57-161">Office 365</span><span class="sxs-lookup"><span data-stu-id="62a57-161">Office 365</span></span>

- [<span data-ttu-id="62a57-162">Office 365 Core - SSAE 18 SOC 1 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-162">Office 365 Core - SSAE 18 SOC 1 Report</span></span>](https://aka.ms/o365SOC-1)
- [<span data-ttu-id="62a57-163">Office 365 Core - SSAE 18 SOC 2 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-163">Office 365 Core - SSAE 18 SOC 2 Report</span></span>](https://aka.ms/o365SOC-2)
- [<span data-ttu-id="62a57-164">Office 365 Core - SSAE 18 SOC 3 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-164">Office 365 Core - SSAE 18 SOC 3 Report</span></span>](https://aka.ms/o365SOC-3)
- [<span data-ttu-id="62a57-165">Office 365 Microservices T1 – SSAE 18 SOC2 Type I 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-165">Office 365 Microservices T1 – SSAE 18 SOC2 Type I Report</span></span>](https://aka.ms/o365-MS-SOC-2-type1)
- [<span data-ttu-id="62a57-166">Office 365 Customer Lockbox SOC 1 SSAE 16 監査報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-166">Office 365 Customer Lockbox SOC 1 SSAE 16 Audit Report</span></span>](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [<span data-ttu-id="62a57-167">Yammer SOC 2 AT 101 Type I 監査報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-167">Yammer SOC 2 AT 101 Type I Audit Report</span></span>](https://aka.ms/YammerSOC2Type1AuditReport)
- [<span data-ttu-id="62a57-168">Yammer SOC 2 Type II 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-168">Yammer SOC 2 Type II Report</span></span>](https://aka.ms/yammerSOC-2)
- [<span data-ttu-id="62a57-169">ブリッジ レターおよびその他の監査報告書を参照する</span><span class="sxs-lookup"><span data-stu-id="62a57-169">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="62a57-170">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="62a57-170">Frequently asked questions</span></span>

<span data-ttu-id="62a57-171">**SOC 報告書のコピーはどのようにして入手できますか?**</span><span class="sxs-lookup"><span data-stu-id="62a57-171">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="62a57-172">監査人は、報告書を使って、Microsoft ビジネス クラウド サービスの結果と顧客の法的規制要件を比較できます。</span><span class="sxs-lookup"><span data-stu-id="62a57-172">With the reports, your auditors can compare Microsoft business cloud services results with your own legal and regulatory requirements.</span></span>

- <span data-ttu-id="62a57-173">[Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx)を使用して、すべての SOC 報告書を閲覧できます。</span><span class="sxs-lookup"><span data-stu-id="62a57-173">You can see all SOC reports through the [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx).</span></span>
- <span data-ttu-id="62a57-174">Azure DevOps のサービスをご利用のお客様で、[Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) にアクセスできないお客様は、お客様の SOC 1 および SOC 2 報告書については [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) にメールでご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="62a57-174">Azure DevOps Service customers that can’t access [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) can email [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) for its SOC 1 and SOC 2 reports.</span></span> <span data-ttu-id="62a57-175">このメールは、Azure DevOps SOC 報告書の要求のみにご使用ください。</span><span class="sxs-lookup"><span data-stu-id="62a57-175">This email is to request Azure DevOps SOC reports only.</span></span>

<span data-ttu-id="62a57-176">**Azure SOC 報告書が発行される頻度はどれくらいですか?**</span><span class="sxs-lookup"><span data-stu-id="62a57-176">**How often are Azure SOC reports issued?**</span></span>

<span data-ttu-id="62a57-177">Azure、Cloud App Security、Flow、Graph、Intune、Power BI、PowerApps、Stream、Microsoft データセンターの SOC 報告書は、12 か月連続の実行期間 (監査期間) に基づいており、半年ごとに新たな報告書が発行されます (期間は 3 月 31 日と 9 月 30 日に終了)。</span><span class="sxs-lookup"><span data-stu-id="62a57-177">SOC reports for Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters are based on a rolling 12-month run window (audit period) with new reports issued semi-annually (period ends are March 31 and September 30).</span></span> <span data-ttu-id="62a57-178">ブリッジ レターは、1 月に発行されて 10/1- 12/31 の期間をカバーし、7 月に発行されて 4/1 - 6/30の期間をカバーします。</span><span class="sxs-lookup"><span data-stu-id="62a57-178">Bridge letters are issued in January to cover the period of 10/1 – 12/31 and July to cover the period of 4/1 – 6/30.</span></span> <span data-ttu-id="62a57-179">最新の報告書は Service Trust Portal から[ダウンロード](https://aka.ms/stp)できます。</span><span class="sxs-lookup"><span data-stu-id="62a57-179">Customers can [download](https://aka.ms/stp) the latest reports from the Service Trust Portal.</span></span>

<span data-ttu-id="62a57-180">**Microsoft データセンターの監査は、自分自身で実施する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="62a57-180">**Do I need to conduct my own audit of Microsoft datacenters?**</span></span>

<span data-ttu-id="62a57-181">いいえ。</span><span class="sxs-lookup"><span data-stu-id="62a57-181">No.</span></span> <span data-ttu-id="62a57-182">Microsoft では、Microsoft のセキュリティ コミットメントに Microsoft が準拠していることを確認していただけるように、第三者監査報告書と認定をお客様にも公開しています。</span><span class="sxs-lookup"><span data-stu-id="62a57-182">Microsoft shares the independent audit reports and certifications with customers so that they can verify Microsoft compliance with its security commitments.</span></span>

<span data-ttu-id="62a57-183">**Microsoft のコンプライアンスを自分の組織の認定プロセスに利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="62a57-183">**Can I use Microsoft’s compliance in my organization’s certification process?**</span></span>

<span data-ttu-id="62a57-184">はい。</span><span class="sxs-lookup"><span data-stu-id="62a57-184">Yes.</span></span> <span data-ttu-id="62a57-185">対象となる Microsoft クラウド サービスにアプリケーションやデータを移行する場合、Microsoft が保持する監査と認定を利用できます。</span><span class="sxs-lookup"><span data-stu-id="62a57-185">When you migrate your applications and data to covered Microsoft cloud services, you can build on the audits and certifications that Microsoft holds.</span></span> <span data-ttu-id="62a57-186">お客様のデータのセキュリティとプライバシーを維持するために Microsoft が実装してきた制御の有効性が第三者報告書により証明されます。</span><span class="sxs-lookup"><span data-stu-id="62a57-186">The independent reports attest to the effectiveness of controls that Microsoft has implemented to help maintain the security and privacy of your data.</span></span>

<span data-ttu-id="62a57-187">**組織でのコンプライアンス活動は、何から始めればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="62a57-187">**Where do I start with my organization’s own compliance effort?**</span></span>

<span data-ttu-id="62a57-188">[SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) は、SOC 報告書のプロセスを理解し、組織で報告書の利用を促進する上で役立つリソースです。</span><span class="sxs-lookup"><span data-stu-id="62a57-188">The [SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) is a helpful resource for understanding SOC reporting processes and promoting your organization’s use of them.</span></span>

## <a name="resources"></a><span data-ttu-id="62a57-189">リソース</span><span class="sxs-lookup"><span data-stu-id="62a57-189">Resources</span></span>

- [<span data-ttu-id="62a57-190">Microsoft クラウド サービスによるデータの保護の強化</span><span class="sxs-lookup"><span data-stu-id="62a57-190">Better protect your data by using Microsoft cloud services</span></span>](https://www.microsoft.com/trustcenter/guidance/protect-data)
- [<span data-ttu-id="62a57-191">Service Organization Control (SOC) 報告書</span><span class="sxs-lookup"><span data-stu-id="62a57-191">Service Organization Control (SOC) Reports</span></span>](https://aka.ms/mssocreports)
- [<span data-ttu-id="62a57-192">SSAE 16 の概要</span><span class="sxs-lookup"><span data-stu-id="62a57-192">SSAE 16 Overview</span></span>](http://ssae16.com/SSAE16_overview.html)
- [<span data-ttu-id="62a57-193">ISAE 3402 の概要</span><span class="sxs-lookup"><span data-stu-id="62a57-193">ISAE 3402 Overview</span></span>](http://isae3402.com/ISAE3402_overview.html)
- [<span data-ttu-id="62a57-194">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="62a57-194">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="62a57-195">Microsoft Government クラウド</span><span class="sxs-lookup"><span data-stu-id="62a57-195">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="62a57-196">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="62a57-196">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
