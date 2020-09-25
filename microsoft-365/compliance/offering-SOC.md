---
title: Service Organization Controls (SOC)
description: Microsoft クラウド サービスは、運用セキュリティについて Service Organization Controls 基準に準拠しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: a648673d06300190695db52d14e85f114bfe0e87
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208149"
---
# <a name="service-organization-controls-soc"></a><span data-ttu-id="2acd2-104">Service Organization Controls (SOC)</span><span class="sxs-lookup"><span data-stu-id="2acd2-104">Service Organization Controls (SOC)</span></span>

## <a name="soc-1-2-and-3-reports-overview"></a><span data-ttu-id="2acd2-105">SOC 1、2、3 報告書の概要</span><span class="sxs-lookup"><span data-stu-id="2acd2-105">SOC 1, 2, and 3 Reports overview</span></span>

<span data-ttu-id="2acd2-106">データ ストレージ、アプリケーションへのアクセスなど、基本的な機能をクラウド サービス プロバイダー (CSP) やその他のサービス組織にアウトソースするビジネスが増えています。</span><span class="sxs-lookup"><span data-stu-id="2acd2-106">Increasingly, businesses outsource basic functions such as data storage and access to applications to cloud service providers (CSPs) and other service organizations.</span></span> <span data-ttu-id="2acd2-107">これを受けて、米国公認会計士協会 (American Institute of Certified Public Accountants: AICPA) は、クラウドで保存および処理される情報の機密性とプライバシーを保護する制御基準である Service Organization Controls (SOC) フレームワークを策定しました。</span><span class="sxs-lookup"><span data-stu-id="2acd2-107">In response, the American Institute of Certified Public Accountants (AICPA) has developed the Service Organization Controls (SOC) framework, a standard for controls that safeguard the confidentiality and privacy of information stored and processed in the cloud.</span></span> <span data-ttu-id="2acd2-108">これは、国際サービス組織の報告書作成基準である 国際保証業務基準 (International Standard on Assurance Engagements: ISAE) に合致するものです。</span><span class="sxs-lookup"><span data-stu-id="2acd2-108">This aligns with the International Standard on Assurance Engagements (ISAE), the reporting standard for international service organizations.</span></span>

<span data-ttu-id="2acd2-109">SOC フレームワークに基づくサービス監査は、SOC 1 と SOC 2 の 2 つに分類され、対象となる Microsoft クラウド サービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-109">Service audits based on the SOC framework fall into two categories — SOC 1 and SOC 2 — that apply to in-scope Microsoft cloud services.</span></span>

<span data-ttu-id="2acd2-110">SOC 1 監査は、財務諸表を監査する公認会計士事務所を対象としており、プロバイダーのクラウド サービスを使用している顧客の財務報告に影響する、CSP の内部コントロールの有効性を評価します。</span><span class="sxs-lookup"><span data-stu-id="2acd2-110">A SOC 1 audit, intended for CPA firms that audit financial statements, evaluates the effectiveness of a CSP's internal controls that affect the financial reports of a customer using the provider's cloud services.</span></span> <span data-ttu-id="2acd2-111">監査は保証業務基準書 (SSAE 18) および国際保証業務基準書第 </span><span class="sxs-lookup"><span data-stu-id="2acd2-111">The Statement on Standards for Attestation Engagements (SSAE 18) and the International Standards for Assurance Engagements No.</span></span> <span data-ttu-id="2acd2-112">3402 号 (ISAE 3402) を基準として実施され、これを基に SOC 1 報告書が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-112">3402 (ISAE 3402) are the standards under which the audit is performed, and is the basis of the SOC 1 report.</span></span>

<span data-ttu-id="2acd2-113">SOC 2 監査では、AICPA Trust Service Principles and Criteria に基づいて CSP のシステムの有効性を評価します。</span><span class="sxs-lookup"><span data-stu-id="2acd2-113">A SOC 2 audit gauges the effectiveness of a CSP's system based on the AICPA Trust Service Principles and Criteria.</span></span> <span data-ttu-id="2acd2-114">Attestation Standards (AT) Section 101 の Attest Engagement を基に SOC 2 および SOC 3 報告書が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-114">An Attest Engagement under Attestation Standards (AT) Section 101 is the basis of SOC 2 and SOC 3 reports.</span></span>

<span data-ttu-id="2acd2-115">SOC 1 または SOC 2 監査の終了時、サービス監査人は SOC 1 Type 2 または SOC 2 Type 2 報告書で意見を述べます。報告書では、CSP のシステムについて説明し、CSP による自身の制御の説明の正当性を評価します。</span><span class="sxs-lookup"><span data-stu-id="2acd2-115">At the conclusion of a SOC 1 or SOC 2 audit, the service auditor renders an opinion in a SOC 1 Type 2 or SOC 2 Type 2 report, which describes the CSP's system and assesses the fairness of the CSP's description of its controls.</span></span> <span data-ttu-id="2acd2-116">また、CSP の制御が適切に設計されているかどうか、指定した日付に実行されていたか、また、指定した期間に正常に運用されていたかも評価します。</span><span class="sxs-lookup"><span data-stu-id="2acd2-116">It also evaluates whether the CSP's controls are designed appropriately, were in operation on a specified date, and were operating effectively over a specified time period.</span></span>

<span data-ttu-id="2acd2-117">監査人は SOC 3 報告書 (SOC 2 Type 2 監査報告書が簡略化されたもの) を作成することもできます。これは、CSP の制御についての保証は必要なものの、完全な SOC 2 報告書を必要としないユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="2acd2-117">Auditors can also create a SOC 3 report — an abbreviated version of the SOC 2 Type 2 audit report — for users who want assurance about the CSP's controls but don't need a full SOC 2 report.</span></span> <span data-ttu-id="2acd2-118">SOC 3 報告書を提供できるのは、CSP が SOC 2 で無限定適正意見を得ている場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-118">A SOC 3 report can be conferred only if the CSP has an unqualified audit opinion for SOC 2.</span></span>

## <a name="microsoft-and-soc-1-2-and-3-reports"></a><span data-ttu-id="2acd2-119">Microsoft と SOC 1、2、3 報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-119">Microsoft and SOC 1, 2, and 3 Reports</span></span>

<span data-ttu-id="2acd2-120">Microsoft の対象クラウド サービスは、少なくとも年に 1 回、独立第三者監査機関による監査が SOC 報告フレームワークに照らして実施されています。</span><span class="sxs-lookup"><span data-stu-id="2acd2-120">Microsoft covered cloud services are audited at least annually against the SOC reporting framework by independent third-party auditors.</span></span> <span data-ttu-id="2acd2-121">Microsoft クラウド サービスの監査は、サービスごとに適用される信頼の原則に従って、データ セキュリティ、可用性、処理の整合性、および機密性の制御が対象となります。</span><span class="sxs-lookup"><span data-stu-id="2acd2-121">The audit for Microsoft cloud services covers controls for data security, availability, processing integrity, and confidentiality as applicable to in-scope trust principles for each service.</span></span>

<span data-ttu-id="2acd2-122">Microsoft では、SOC 1 Type 2、SOC 2 Type 2、および SOC 3 報告書を取得しています。</span><span class="sxs-lookup"><span data-stu-id="2acd2-122">Microsoft has achieved SOC 1 Type 2, SOC 2 Type 2, and SOC 3 reports.</span></span> <span data-ttu-id="2acd2-123">原則として、SOC 1 報告書と SOC 2 報告書は、Microsoft と秘密保持契約を結んでいるお客様しか入手できませんが、SOC 3 報告書は公開されています。</span><span class="sxs-lookup"><span data-stu-id="2acd2-123">In general, the availability of SOC 1 and SOC 2 reports is restricted to customers who have signed nondisclosure agreements with Microsoft; the SOC 3 report is publicly available.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="2acd2-124">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="2acd2-124">Microsoft in-scope cloud services</span></span>

### <a name="covered-services-for-soc-1-and-soc-2"></a><span data-ttu-id="2acd2-125">SOC 1 および SOC 2 の対象サービス</span><span class="sxs-lookup"><span data-stu-id="2acd2-125">Covered services for SOC 1 and SOC 2</span></span>

- [<span data-ttu-id="2acd2-126">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="2acd2-126">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="2acd2-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2acd2-127">Microsoft Cloud App Security</span></span>
- [<span data-ttu-id="2acd2-128">Dynamics 365、Dynamics 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="2acd2-128">Dynamics 365 and Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="2acd2-129">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="2acd2-129">Microsoft Graph</span></span>
- <span data-ttu-id="2acd2-130">Intune</span><span class="sxs-lookup"><span data-stu-id="2acd2-130">Intune</span></span>
- <span data-ttu-id="2acd2-131">Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="2acd2-131">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="2acd2-132">Power Automate (旧称 Microsoft Flow) スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービスとしてのクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="2acd2-132">Power Automate (formerly Microsoft Flow) cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="2acd2-133">Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="2acd2-133">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="2acd2-134">Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="2acd2-134">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="2acd2-135">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに組み込まれているサービス)</span><span class="sxs-lookup"><span data-stu-id="2acd2-135">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="2acd2-136">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="2acd2-136">Microsoft Stream</span></span>
- <span data-ttu-id="2acd2-137">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="2acd2-137">Azure DevOps Services</span></span>

### <a name="covered-services-for-soc-3"></a><span data-ttu-id="2acd2-138">SOC 3 の対象サービス</span><span class="sxs-lookup"><span data-stu-id="2acd2-138">Covered services for SOC 3</span></span>

- [<span data-ttu-id="2acd2-139">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="2acd2-139">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="2acd2-140">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2acd2-140">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2acd2-141">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="2acd2-141">Microsoft Graph</span></span>
- <span data-ttu-id="2acd2-142">Intune</span><span class="sxs-lookup"><span data-stu-id="2acd2-142">Intune</span></span>
- <span data-ttu-id="2acd2-143">Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="2acd2-143">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="2acd2-144">Power Automate (旧称 Microsoft Flow) スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービスとしてのクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="2acd2-144">Power Automate (formerly Microsoft Flow) cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="2acd2-145">Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="2acd2-145">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="2acd2-146">Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="2acd2-146">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="2acd2-147">Power BI</span><span class="sxs-lookup"><span data-stu-id="2acd2-147">Power BI</span></span>
- <span data-ttu-id="2acd2-148">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="2acd2-148">Microsoft Stream</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="2acd2-149">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="2acd2-149">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="2acd2-150">監査サイクル</span><span class="sxs-lookup"><span data-stu-id="2acd2-150">Audit cycle</span></span>

<span data-ttu-id="2acd2-151">Microsoft クラウド サービスでは、少なくとも年に 1 回、SOC 1 (SSAE18、ISAE 3402)、SOC 2 (AT Section 101)、SOC 3 基準に照らした監査が実施されます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-151">Microsoft cloud services are audited at least annually against SOC 1 (SSAE18, ISAE 3402), SOC 2 (AT Section 101), and SOC 3 standards.</span></span>

#### <a name="azure-dynamics-365-microsoft-cloud-app-security-flow-microsoft-graph-intune-power-bi-powerapps-microsoft-stream-and-microsoft-datacenters"></a><span data-ttu-id="2acd2-152">Azure、Dynamics 365、Microsoft Cloud App Security、Flow、Microsoft Graph、Intune、Power BI、Power Apps、Microsoft Stream、Microsoft データセンター</span><span class="sxs-lookup"><span data-stu-id="2acd2-152">Azure, Dynamics 365, Microsoft Cloud App Security, Flow, Microsoft Graph, Intune, Power BI, PowerApps, Microsoft Stream, and Microsoft Datacenters</span></span>

- [<span data-ttu-id="2acd2-153">Azure + Dynamics 365 と Azure + Dynamics 365 Government SOC 1 タイプ 2 レポート</span><span class="sxs-lookup"><span data-stu-id="2acd2-153">Azure + Dynamics 365 and Azure + Dynamics 365 Government SOC 1 Type 2 Report</span></span>](https://aka.ms/azuresoc1auditreport)
- [<span data-ttu-id="2acd2-154">Azure + Dynamics 365 と Azure + Dynamics 365 Government SOC 2 タイプ 2 レポート</span><span class="sxs-lookup"><span data-stu-id="2acd2-154">Azure + Dynamics 365 and Azure + Dynamics 365 Government SOC 2 Type 2 Report</span></span>](https://aka.ms/azuresoc2auditreport)
- [<span data-ttu-id="2acd2-155">Azure + Dynamics 365 と Azure + Dynamics 365 Government SOC 3 レポート</span><span class="sxs-lookup"><span data-stu-id="2acd2-155">Azure + Dynamics 365 and Azure + Dynamics 365 Government SOC 3 Report</span></span>](https://aka.ms/azuresoc3auditreport)

#### <a name="office-365"></a><span data-ttu-id="2acd2-156">Office 365</span><span class="sxs-lookup"><span data-stu-id="2acd2-156">Office 365</span></span>

- [<span data-ttu-id="2acd2-157">Office 365 Core - SSAE 18 SOC 1 報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-157">Office 365 Core - SSAE 18 SOC 1 Report</span></span>](https://aka.ms/o365SOC-1)
- [<span data-ttu-id="2acd2-158">Office 365 Core - SSAE 18 SOC 2 報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-158">Office 365 Core - SSAE 18 SOC 2 Report</span></span>](https://aka.ms/o365SOC-2)
- [<span data-ttu-id="2acd2-159">Office 365 Core - SSAE 18 SOC 3 報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-159">Office 365 Core - SSAE 18 SOC 3 Report</span></span>](https://aka.ms/o365SOC-3)
- [<span data-ttu-id="2acd2-160">Office 365 Microservices T1 – SSAE 18 SOC2 Type I 報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-160">Office 365 Microservices T1-SSAE 18 SOC2 Type I Report</span></span>](https://aka.ms/o365-MS-SOC-2-type1)
- [<span data-ttu-id="2acd2-161">顧客ロックボックス SOC 1 SSAE 16 監査報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-161">Customer Lockbox SOC 1 SSAE 16 Audit Report</span></span>](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [<span data-ttu-id="2acd2-162">Yammer SOC 2 AT 101 Type I 監査報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-162">Yammer SOC 2 AT 101 Type I Audit Report</span></span>](https://aka.ms/YammerSOC2Type1AuditReport)
- [<span data-ttu-id="2acd2-163">Yammer SOC 2 Type II 報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-163">Yammer SOC 2 Type II Report</span></span>](https://aka.ms/yammerSOC-2)
- [<span data-ttu-id="2acd2-164">ブリッジ レターおよびその他の監査報告書を参照する</span><span class="sxs-lookup"><span data-stu-id="2acd2-164">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="2acd2-165">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="2acd2-165">Frequently asked questions</span></span>

<span data-ttu-id="2acd2-166">**SOC 報告書のコピーはどのようにして入手できますか?**</span><span class="sxs-lookup"><span data-stu-id="2acd2-166">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="2acd2-167">監査人は、報告書を使って、Microsoft ビジネス クラウド サービスの結果と顧客の法的規制要件を比較できます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-167">With the reports, your auditors can compare Microsoft business cloud services results with your own legal and regulatory requirements.</span></span>

- <span data-ttu-id="2acd2-168">[Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx)を使用して、すべての SOC 報告書を閲覧できます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-168">You can see all SOC reports through the [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx).</span></span>
- <span data-ttu-id="2acd2-169">Azure DevOps のサービスをご利用のお客様で、[Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) にアクセスできないお客様は、お客様の SOC 1 および SOC 2 報告書については [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) にメールでご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="2acd2-169">Azure DevOps Service customers that can't access [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) can email [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) for its SOC 1 and SOC 2 reports.</span></span> <span data-ttu-id="2acd2-170">このメールは、Azure DevOps SOC 報告書の要求のみにご使用ください。</span><span class="sxs-lookup"><span data-stu-id="2acd2-170">This email is to request Azure DevOps SOC reports only.</span></span>

<span data-ttu-id="2acd2-171">**Azure SOC 報告書が発行される頻度はどれくらいですか?**</span><span class="sxs-lookup"><span data-stu-id="2acd2-171">**How often are Azure SOC reports issued?**</span></span>

<span data-ttu-id="2acd2-172">Azure、Microsoft Cloud App Security、Flow、Microsoft Graph、Intune、Power BI、PowerApps、Microsoft Stream、Microsoft データセンターの SOC 報告書は、12 か月連続の実行期間 (監査期間) に基づいており、半年ごとに新たな報告書が発行されます (期間は 3 月 31 日と 9 月 30 日に終了)。</span><span class="sxs-lookup"><span data-stu-id="2acd2-172">SOC reports for Azure, Microsoft Cloud App Security, Flow, Microsoft Graph, Intune, Power BI, PowerApps, Microsoft Stream, and Microsoft Datacenters are based on a rolling 12-month run window (audit period) with new reports issued semi-annually (period ends are March 31 and September 30).</span></span> <span data-ttu-id="2acd2-173">ブリッジ レターは四半期ごとに発行され、過去 3 か月間をカバーします。</span><span class="sxs-lookup"><span data-stu-id="2acd2-173">Bridge letters are issued each quarter to cover the prior three month period.</span></span> <span data-ttu-id="2acd2-174">たとえば、1 月のレターは 10 月 1 日から 12 月 31 日を、4 月のレターは 1 月 1 日から 3 月 31 日を、7 月のレターは 4 月 1 日から 6 月 30 日を、10 月のレターは 7 月 1 日から 9 月 30 日をカバーします。</span><span class="sxs-lookup"><span data-stu-id="2acd2-174">For example, the January letter covers 10/1-12/31, the April letter covers 1/1-3/31, the July letter covers 4/1-6/30, and the October letter covers 7/1-9/30.</span></span> <span data-ttu-id="2acd2-175">最新の報告書は Service Trust Portal から[ダウンロード](https://aka.ms/stp)できます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-175">Customers can [download](https://aka.ms/stp) the latest reports from the Service Trust Portal.</span></span>

<span data-ttu-id="2acd2-176">**Microsoft データセンターの監査は、自分自身で実施する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="2acd2-176">**Do I need to conduct my own audit of Microsoft datacenters?**</span></span>

<span data-ttu-id="2acd2-177">いいえ。</span><span class="sxs-lookup"><span data-stu-id="2acd2-177">No.</span></span> <span data-ttu-id="2acd2-178">Microsoft では、Microsoft のセキュリティ コミットメントに Microsoft が準拠していることを確認していただけるように、第三者監査報告書と認定をお客様にも公開しています。</span><span class="sxs-lookup"><span data-stu-id="2acd2-178">Microsoft shares the independent audit reports and certifications with customers so that they can verify Microsoft compliance with its security commitments.</span></span>

<span data-ttu-id="2acd2-179">**Microsoft のコンプライアンスを自分の組織の認定プロセスに利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="2acd2-179">**Can I use Microsoft's compliance in my organization's certification process?**</span></span>

<span data-ttu-id="2acd2-180">はい、できます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-180">Yes.</span></span> <span data-ttu-id="2acd2-181">対象となる Microsoft クラウド サービスにアプリケーションやデータを移行する場合、Microsoft が保持する監査と認定を利用できます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-181">When you migrate your applications and data to covered Microsoft cloud services, you can build on the audits and certifications that Microsoft holds.</span></span> <span data-ttu-id="2acd2-182">お客様のデータのセキュリティとプライバシーを維持するために Microsoft が実装してきた制御の有効性が第三者報告書により証明されます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-182">The independent reports attest to the effectiveness of controls that Microsoft has implemented to help maintain the security and privacy of your data.</span></span>

<span data-ttu-id="2acd2-183">**組織でのコンプライアンス活動は、何から始めればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="2acd2-183">**Where do I start with my organization's own compliance effort?**</span></span>

<span data-ttu-id="2acd2-184">[SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) は、SOC 報告書のプロセスを理解し、組織で報告書の利用を促進する上で役立つリソースです。</span><span class="sxs-lookup"><span data-stu-id="2acd2-184">The [SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) is a helpful resource for understanding SOC reporting processes and promoting your organization's use of them.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="2acd2-185">Microsoft コンプライアンス マネージャーを使用してリスクを評価する</span><span class="sxs-lookup"><span data-stu-id="2acd2-185">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="2acd2-186">[Microsoft コンプライアンス マネージャー](compliance-manager.md)は、[ Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)の機能で、組織のコンプライアンスに対する姿勢を把握し、リスクを軽減するための処置を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2acd2-186">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="2acd2-187">コンプライアンスマネージャーには、この規制の評価を構築するためのプレミアム テンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2acd2-187">Compliance Manager offers a premium template for building an assessment for this regulation.</span></span> <span data-ttu-id="2acd2-188">コンプライアンスマネージャーの**評価テンプレート** ページでテンプレートを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2acd2-188">Find the template in the **assessment templates** page in Compliance Manager.</span></span> <span data-ttu-id="2acd2-189">[コンプライアンスマネージャーで評価をする方法](compliance-manager-assessments.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="2acd2-189">Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="2acd2-190">リソース</span><span class="sxs-lookup"><span data-stu-id="2acd2-190">Resources</span></span>

- [<span data-ttu-id="2acd2-191">Microsoft クラウド サービスによるデータの保護の強化</span><span class="sxs-lookup"><span data-stu-id="2acd2-191">Better protect your data by using Microsoft cloud services</span></span>](https://www.microsoft.com/trustcenter/guidance/protect-data)
- [<span data-ttu-id="2acd2-192">Service Organization Control (SOC) 報告書</span><span class="sxs-lookup"><span data-stu-id="2acd2-192">Service Organization Control (SOC) Reports</span></span>](https://aka.ms/mssocreports)
- [<span data-ttu-id="2acd2-193">SSAE 16 の概要</span><span class="sxs-lookup"><span data-stu-id="2acd2-193">SSAE 16 Overview</span></span>](http://ssae16.com/SSAE16_overview.html)
- [<span data-ttu-id="2acd2-194">ISAE 3402 の概要</span><span class="sxs-lookup"><span data-stu-id="2acd2-194">ISAE 3402 Overview</span></span>](http://isae3402.com/ISAE3402_overview.html)
- [<span data-ttu-id="2acd2-195">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="2acd2-195">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="2acd2-196">Microsoft Government クラウド</span><span class="sxs-lookup"><span data-stu-id="2acd2-196">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="2acd2-197">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="2acd2-197">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
