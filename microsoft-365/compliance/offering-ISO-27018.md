---
title: クラウドで個人データを保護するための ISO/IEC 27018 実施基準
description: Microsoft は、クラウド プライバシーに関するこの実施基準を順守した初のクラウド プロバイダーです。
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
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 5f22e7a1dccff1d278ee07adaa56ea7d11de4cd3
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260005"
---
# <a name="isoiec-27018-code-of-practice-for-protecting-personal-data-in-the-cloud"></a><span data-ttu-id="7dd56-104">クラウドで個人データを保護するための ISO/IEC 27018 実施基準</span><span class="sxs-lookup"><span data-stu-id="7dd56-104">ISO/IEC 27018 Code of Practice for Protecting Personal Data in the Cloud</span></span>

## <a name="isoiec-27018-overview"></a><span data-ttu-id="7dd56-105">ISO/IEC 27018 の概要</span><span class="sxs-lookup"><span data-stu-id="7dd56-105">ISO/IEC 27018 overview</span></span>

<span data-ttu-id="7dd56-106">国際標準化機構 (ISO) は中立的な非政府組織で、国際基準を自主的に策定する世界最大の組織です。</span><span class="sxs-lookup"><span data-stu-id="7dd56-106">The International Organization for Standardization (ISO) is an independent nongovernmental organization and the world’s largest developer of voluntary international standards.</span></span> <span data-ttu-id="7dd56-107">ISO/IEC 27000 基準ファミリは、すべての形態および規模の組織が情報資産のセキュリティを確保できるよう支援します。</span><span class="sxs-lookup"><span data-stu-id="7dd56-107">The ISO/IEC 27000 family of standards helps organizations of every type and size keep information assets secure.</span></span>

<span data-ttu-id="7dd56-108">2014 年、ISO は、ISO/IEC 27001 の補遺として、クラウド プライバシーに関する初めての国際実施基準である ISO/IEC 27018:2014 を採用しました。</span><span class="sxs-lookup"><span data-stu-id="7dd56-108">In 2014, the ISO adopted ISO/IEC 27018:2014, an addendum to ISO/IEC 27001, the first international code of practice for cloud privacy.</span></span> <span data-ttu-id="7dd56-109">EU データ保護法に基づいて、個人を特定できる情報 (PII) の処理者の役割を担うクラウド サービス プロバイダー (CSP) に、PII 保護のためのリスク評価と最新制御の実装に関する特定のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7dd56-109">Based on EU data-protection laws, it gives specific guidance to cloud service providers (CSPs) acting as processors of personally identifiable information (PII) on assessing risks and implementing state-of-the-art controls for protecting PII.</span></span>

<span data-ttu-id="7dd56-110">Microsoft と ISO/IEC 27018</span><span class="sxs-lookup"><span data-stu-id="7dd56-110">Microsoft and ISO/IEC 27018</span></span>

<span data-ttu-id="7dd56-111">Microsoft Azure と Azure Germany は、年に 1 回以上、ISO/IEC 27001 および ISO/IEC 27018 への準拠に関して、第三者の公認認定機関の監査を受けています。この機関は、該当するセキュリティ コントロールが導入されていて、効果的に運用されていることを独自に検証します。</span><span class="sxs-lookup"><span data-stu-id="7dd56-111">At least once a year, Microsoft Azure and Azure Germany are audited for compliance with ISO/IEC 27001 and ISO/IEC 27018 by an accredited third-party certification body, providing independent validation that applicable security controls are in place and operating effectively.</span></span> <span data-ttu-id="7dd56-112">このコンプライアンスの検証プロセスの一環として、監査人は、適用宣言書で、対象となる Microsoft クラウド サービスおよび法人向けテクニカル サポート サービスに、Azure で PII を保護するための ISO/IEC 27018 制御が組み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dd56-112">As part of this compliance verification process, the auditors validate in their statement of applicability that Microsoft in-scope cloud services and commercial technical support services have incorporated ISO/IEC 27018 controls for the protection of PII in Azure.</span></span> <span data-ttu-id="7dd56-113">コンプライアンスを確保し続けるために、Microsoft クラウド サービスは年 1 回第三者による審査を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd56-113">To remain compliant, Microsoft cloud services must be subject to annual third-party reviews.</span></span>

<span data-ttu-id="7dd56-114">ISO/IEC 27001 基準と ISO/IEC 27018 の実施基準への準拠が、この実施基準を採用した初めての主要クラウド プロバイダーである、Microsoft のプライバシー ポリシーと手順が堅牢で、高い水準が維持されていることの証明になります。</span><span class="sxs-lookup"><span data-stu-id="7dd56-114">By following the standards of ISO/IEC 27001 and the code of practice embodied in ISO/IEC 27018, Microsoft — the first major cloud provider to incorporate this code of practice — demonstrates that its privacy policies and procedures are robust and in line with its high standards.</span></span>

- <span data-ttu-id="7dd56-115">**Microsoft クラウド サービスの顧客がデータの保存場所を把握している。**</span><span class="sxs-lookup"><span data-stu-id="7dd56-115">**Customers of Microsoft cloud services know where their data is stored.**</span></span> <span data-ttu-id="7dd56-116">ISO/IEC 27018 では、認定 CSP が、データの保存先の国を顧客に知らせる必要があります。したがって、Microsoft クラウド サービスの顧客には、適用される情報セキュリティ ルールに従うために必要な可視性が提供されています。</span><span class="sxs-lookup"><span data-stu-id="7dd56-116">Because ISO/IEC 27018 requires certified CSPs to inform customers of the countries in which their data may be stored, Microsoft cloud service customers have the visibility they need to comply with any applicable information security rules.</span></span>
- <span data-ttu-id="7dd56-117">**お客様のデータは、明確な同意がない限りマーケティングや広告に使用されない。**</span><span class="sxs-lookup"><span data-stu-id="7dd56-117">**Customer data won’t be used for marketing or advertising without explicit consent.**</span></span> <span data-ttu-id="7dd56-118">CSP によっては、顧客データを自身の商業目的でターゲットを絞った広告などに使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="7dd56-118">Some CSPs use customer data for their own commercial ends, including for targeted advertising.</span></span> <span data-ttu-id="7dd56-119">Microsoft では対象となるエンタープライズ クラウド サービスに ISO/IEC 27018 を採用しているため、明確な同意がない限り、お客様のデータがこのような目的で使用されることありません。その点に関しては、お客様は安心して利用できます。また、このような同意が、クラウド サービスの使用条件になることもありません。</span><span class="sxs-lookup"><span data-stu-id="7dd56-119">Because Microsoft has adopted ISO/IEC 27018 for its in-scope enterprise cloud services, customers can rest assured that their data will never be used for such purposes without explicit consent, and that consent cannot be a condition for use of the cloud service.</span></span>
- <span data-ttu-id="7dd56-120">**Microsoft の顧客は PII の状況を把握できる。**</span><span class="sxs-lookup"><span data-stu-id="7dd56-120">**Microsoft customers know what’s happening with their PII.**</span></span> <span data-ttu-id="7dd56-121">ISO/IEC 27018 には、適正な期間内に個人情報の返却、移行、および安全な破棄を可能にするポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="7dd56-121">ISO/IEC 27018 requires a policy that allows for the return, transfer, and secure disposal of personal information within a reasonable period of time.</span></span> <span data-ttu-id="7dd56-122">顧客データにアクセスする必要がある他の企業と連携する場合、Microsoft ではこうした二次処理者の身元を積極的に開示します。</span><span class="sxs-lookup"><span data-stu-id="7dd56-122">If Microsoft works with other companies that need access to your customer data, Microsoft proactively discloses the identities of those sub-processors.</span></span>
- <span data-ttu-id="7dd56-123">**顧客データの開示に対する要求には法的拘束力がある場合にのみ応じる。**</span><span class="sxs-lookup"><span data-stu-id="7dd56-123">**Microsoft complies only with legally binding requests for disclosure of customer data.**</span></span> <span data-ttu-id="7dd56-124">犯罪捜査の場合のように、Microsoft がこうした要求に応じる必要がある場合は、法律で禁止されていない限り必ずお客様に通知します。</span><span class="sxs-lookup"><span data-stu-id="7dd56-124">If Microsoft must comply with such a request — as in the case of a criminal investigation — it will always notify the customer unless it is prohibited by law from doing so.</span></span>

<span data-ttu-id="7dd56-125">Microsoft Cloud における ISO-Iec-27018 のメリットを確認してください: [ISO/IEC 27017 背景解説をダウンロードする](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="7dd56-125">Learn about the benefits of ISO-Iec-27018 on the Microsoft Cloud: [Download the ISO/IEC 27017 backgrounder](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="7dd56-126">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="7dd56-126">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="7dd56-127">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="7dd56-127">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="7dd56-128">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7dd56-128">Cloud App Security</span></span>
- <span data-ttu-id="7dd56-129">Microsoft プロフェッショナル サービス: Azure、Dynamics 365、Intune と、Office 365 の Medium Business および Enterprise のお客様への Premier およびオンプレミス サポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-129">Microsoft Professional Services: Premier and On Premises for Azure, Dynamics 365, Intune, and for medium business and enterprise customers of Office 365</span></span>
- [<span data-ttu-id="7dd56-130">Dynamics 365、Dynamics 365 U.S. Government</span><span class="sxs-lookup"><span data-stu-id="7dd56-130">Dynamics 365 and Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="7dd56-131">Genomics</span><span class="sxs-lookup"><span data-stu-id="7dd56-131">Genomics</span></span>
- <span data-ttu-id="7dd56-132">Graph</span><span class="sxs-lookup"><span data-stu-id="7dd56-132">Graph</span></span>
- <span data-ttu-id="7dd56-133">Health Bot</span><span class="sxs-lookup"><span data-stu-id="7dd56-133">Health Bot</span></span>
- <span data-ttu-id="7dd56-134">Intune</span><span class="sxs-lookup"><span data-stu-id="7dd56-134">Intune</span></span>
- <span data-ttu-id="7dd56-135">Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="7dd56-135">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="7dd56-136">Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランまたはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="7dd56-136">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="7dd56-137">Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="7dd56-137">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- <span data-ttu-id="7dd56-138">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="7dd56-138">Office 365 Germany</span></span>
- <span data-ttu-id="7dd56-139">OMS Service Map</span><span class="sxs-lookup"><span data-stu-id="7dd56-139">OMS Service Map</span></span>
- <span data-ttu-id="7dd56-140">Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="7dd56-140">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="7dd56-141">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="7dd56-141">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="7dd56-142">Stream</span><span class="sxs-lookup"><span data-stu-id="7dd56-142">Stream</span></span>
- <span data-ttu-id="7dd56-143">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="7dd56-143">Azure DevOps Services</span></span>
- <span data-ttu-id="7dd56-144">Windows Defender ATP - エンドポイントでの検出と対応、自動の調査と修復、セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="7dd56-144">Windows Defender ATP — Endpoint Detection & Response, Automatic Investigation & Remediation, Secure Score</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="7dd56-145">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="7dd56-145">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="7dd56-146">監査サイクル</span><span class="sxs-lookup"><span data-stu-id="7dd56-146">Audit cycle</span></span>

<span data-ttu-id="7dd56-147">Microsoft クラウド サービスおよび法人向けテクニカル サポート サービスは、年 1 回、ISO/IEC 27001 の認定プロセスの一環として、ISO/IEC 27018 実施基準に関する監査を受けています。</span><span class="sxs-lookup"><span data-stu-id="7dd56-147">Microsoft cloud and commercial technical support services are audited once a year for the ISO/IEC 27018 code of practice as part of the certification process for ISO/IEC 27001.</span></span>

### <a name="audits-and-reports"></a><span data-ttu-id="7dd56-148">監査とレポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-148">Audits and reports</span></span>

- [<span data-ttu-id="7dd56-149">Azure、Intune、Microsoft マネージド デスクトップ、Power BI、Cloud App Security、Microsoft PowerApps、Microsoft Flow、Microsoft Graph、Microsoft Genomics、Microsoft Datacenters - ISO 27001 および 27018 証明書</span><span class="sxs-lookup"><span data-stu-id="7dd56-149">Azure, Intune, Power BI, Cloud App Security, Microsoft PowerApps, Microsoft Flow, Microsoft Graph, Microsoft Genomics, and Microsoft Datacenter — ISO 27001 and 27018 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078016)
- [<span data-ttu-id="7dd56-150">Azure、Intune、Microsoft マネージド デスクトップ、Power BI、Cloud App Security、Microsoft PowerApps、Microsoft Flow、Microsoft Graph、Microsoft Genomics、Microsoft Datacenters - ISO 27001 および 27018 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-150">Azure, Intune, Power BI, Cloud App Security, Microsoft PowerApps, Microsoft Flow, Microsoft Graph, Microsoft Genomics, and Microsoft Datacenter — ISO 27001 and 27018 Audit Assessment Report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078020)
- [<span data-ttu-id="7dd56-151">Azure、Intune、Microsoft マネージド デスクトップ、Power BI、Cloud App Security、Microsoft PowerApps、Microsoft Flow、Microsoft Graph、Microsoft Genomics、Microsoft Datacenters - ISO 27001 および 27018 の適用宣言書 (SOA) 2017</span><span class="sxs-lookup"><span data-stu-id="7dd56-151">Azure, Intune, Power BI, Cloud App Security, Microsoft PowerApps, Microsoft Flow, Microsoft Graph, Microsoft Genomics, and Microsoft Datacenter — ISO 27001 and 27018 Statement of Applicability (SOA) 2017</span></span>](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=47d89200-b24b-491d-b657-7c523ddfb6f9&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports)
- [<span data-ttu-id="7dd56-152">Azure - Germany ISO 27018 - クラウドで個人データを保護するための実施基準 - 証明書</span><span class="sxs-lookup"><span data-stu-id="7dd56-152">Azure — Germany ISO 27018 — Code of Practice for Protecting Personal Data in the Cloud — Certificate</span></span>](https://servicetrust.microsoft.com/Documents/ComplianceReports?downloadDocument=1&documentId=6a0dab80-8382-4af6-980c-ed2ed9a341c6)

### <a name="office-365"></a><span data-ttu-id="7dd56-153">Office 365</span><span class="sxs-lookup"><span data-stu-id="7dd56-153">Office 365</span></span>

- [<span data-ttu-id="7dd56-154">Office 365 - ISO 27001、ISO 27018、ISO 27017 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-154">Office 365 — ISO 27001, ISO 27018, and ISO 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)
- [<span data-ttu-id="7dd56-155">Yammer ISO 27018 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-155">Yammer ISO 27018 Audit Assessment Report</span></span>](https://aka.ms/YammerISO27018Auditreport)

### <a name="dynamics-365"></a><span data-ttu-id="7dd56-156">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7dd56-156">Dynamics 365</span></span>

- [<span data-ttu-id="7dd56-157">Dynamics 365 の ISO 27018 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-157">Dynamics 365 ISO 27018 Audit Assessment Report</span></span>](https://aka.ms/dynamics365iso27018auditreport)
- [<span data-ttu-id="7dd56-158">Dynamics 365 for Marketing の ISO 27018 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-158">Dynamics 365 for Marketing ISO 27018 Audit Assessment Report</span></span>](https://aka.ms/dynamics365Marketingiso27018auditreport)
- [<span data-ttu-id="7dd56-159">Dynamics 365 Parature の ISO 27018 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-159">Dynamics 365 Parature ISO 27018 Audit Assessment Report</span></span>](https://aka.ms/dynamics365Paratureiso27018auditreport)

### <a name="azure-devops-services"></a><span data-ttu-id="7dd56-160">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="7dd56-160">Azure DevOps Services</span></span>

- [<span data-ttu-id="7dd56-161">Azure DevOps Services ISO 27018 証明書 PII 665918</span><span class="sxs-lookup"><span data-stu-id="7dd56-161">Azure DevOps Services ISO 27018 Certificate PII 665918</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2062252)

### <a name="windows-defender-atp"></a><span data-ttu-id="7dd56-162">Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="7dd56-162">Windows Defender ATP</span></span>

- [<span data-ttu-id="7dd56-163">Windows Defender ATP - エンドポイントでの検出と対応、自動の調査と修復、セキュリティ スコア - ISO 27018 証明書</span><span class="sxs-lookup"><span data-stu-id="7dd56-163">Windows Defender ATP — Endpoint Detection & Response, Automatic Investigation & Remediation, Secure Score — ISO 27018 certificate</span></span>](https://aka.ms/windowsdefenderatpiso27018certificate)
- [<span data-ttu-id="7dd56-164">Windows Defender ATP - エンドポイントでの検出と対応、自動の調査と修復、セキュリティ スコア - ISO 27001 および 27018 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="7dd56-164">Windows Defender ATP — Endpoint Detection & Response, Automatic Investigation & Remediation, Secure Score — ISO 27001 and 27018 Audit Assessment Report</span></span>](https://aka.ms/WindowsDefenderATPISO27001AuditReport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="7dd56-165">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7dd56-165">Frequently asked questions</span></span>

<span data-ttu-id="7dd56-166">**ISO/IEC 27018 はだれに適用されますか?**</span><span class="sxs-lookup"><span data-stu-id="7dd56-166">**To whom does ISO/IEC 27018 apply?**</span></span>

<span data-ttu-id="7dd56-167">この実施基準は、他の組織のために PII 処理契約を結んでいる CSP に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7dd56-167">This code of practice applies to CSPs that process PII under contract for other organizations.</span></span> <span data-ttu-id="7dd56-168">また、Microsoft では、これは CSP のサポートにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="7dd56-168">At Microsoft, it also applies to the support of those CSPs.</span></span>

<span data-ttu-id="7dd56-169">**"個人情報管理者" と "個人情報処理者" はどう違うのですか?**</span><span class="sxs-lookup"><span data-stu-id="7dd56-169">**What is the difference between “personal information controllers” and “personal information processors”?**</span></span>

<span data-ttu-id="7dd56-170">ISO/IEC 27018 のコンテキストでは、次のような違いがあります。</span><span class="sxs-lookup"><span data-stu-id="7dd56-170">In the context of ISO/IEC 27018:</span></span>

- <span data-ttu-id="7dd56-171">"管理者" は、個人情報の収集、保持、処理、または使用を管理します。他の企業に代わって個人情報を管理する管理担当者も含まれます。</span><span class="sxs-lookup"><span data-stu-id="7dd56-171">“Controllers” control the collection, holding, processing, or use of personal information; they include those who control it on another company’s behalf.</span></span>
- <span data-ttu-id="7dd56-172">"処理者" は、管理者に代わって情報を処理します。情報の使用方法または処理の目的に関する決定を下すことはありません。</span><span class="sxs-lookup"><span data-stu-id="7dd56-172">“Processors” process information on behalf of controllers; they do not make decisions as to how to use the information or the purposes of the processing.</span></span> <span data-ttu-id="7dd56-173">ユーザーのベンダーである Microsoft は、エンタープライズ クラウド サービスを提供する際に、情報処理者の役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="7dd56-173">In providing its enterprise cloud services, Microsoft — as a vendor to you — is an information processor.</span></span>

<span data-ttu-id="7dd56-174">**Microsoft の ISO/IEC 27018 コンプライアンス情報はどこで確認できますか?**</span><span class="sxs-lookup"><span data-stu-id="7dd56-174">**Where can I view Microsoft compliance information for ISO/IEC 27018?**</span></span>

- <span data-ttu-id="7dd56-175">[Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016)、[Microsoft Professional Services](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270)、[Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016)の BSI から ISO/IEC 27018 証明書を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7dd56-175">You can review the ISO/IEC 27018 certificates from BSI for [Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016), [Microsoft Professional Services](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270), and [Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016).</span></span>
- <span data-ttu-id="7dd56-176">また、ISO/IEC 27018 証明書が [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert)、[Office 365](https://aka.ms/Office365-Cert)、[Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159) に基づいている BSI の ISO/IEC 27001 を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="7dd56-176">You can also review ISO/IEC 27001 certificates from BSI upon which ISO/IEC 27018 certification is based for [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert), [Office 365](https://aka.ms/Office365-Cert), and [Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159).</span></span>
- <span data-ttu-id="7dd56-177">Microsoft が ISO/IEC 27018 に準拠していることを検証した独立した監査人である BSI のレポートを確認するには、[Service Trust Portal](https://aka.ms/stphelp) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="7dd56-177">To review the BSI reports, the independent auditor that validated Microsoft compliance with ISO/IEC 27018, visit the [Service Trust Portal](https://aka.ms/stphelp).</span></span>

<span data-ttu-id="7dd56-178">**Microsoft のコンプライアンスを自分の組織の認定プロセスに利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="7dd56-178">**Can I use Microsoft’s compliance in my organization’s certification process?**</span></span>

<span data-ttu-id="7dd56-179">はい。</span><span class="sxs-lookup"><span data-stu-id="7dd56-179">Yes.</span></span> <span data-ttu-id="7dd56-180">Microsoft の適用エンタープライズ クラウド サービスのいずれかにデプロイされている実装と、ビジネスで ISO/IEC 27018 に準拠していることが重要である場合、Microsoft の ISO/IEC 27001 認定と Microsoft の ISO/IEC 27018 コンプライアンス証明をコンプライアンス評価で利用できます。</span><span class="sxs-lookup"><span data-stu-id="7dd56-180">If compliance with ISO/IEC 27018 is important for your business and implementations deployed on any of Microsoft in-scope enterprise cloud services, you can use Microsoft’s attestation of compliance with ISO/IEC 27018 with Microsoft’s certification for ISO/IEC 27001 in your compliance assessment.</span></span>

<span data-ttu-id="7dd56-181">ただし、コンプライアンスや、組織内の統制およびプロセスに関して、実装を評価する査定人の手配の責任は、審査を受ける組織が負うものとします。</span><span class="sxs-lookup"><span data-stu-id="7dd56-181">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

## <a name="resources"></a><span data-ttu-id="7dd56-182">リソース</span><span class="sxs-lookup"><span data-stu-id="7dd56-182">Resources</span></span>

- [<span data-ttu-id="7dd56-183">ISO/IEC 27018:2014 実施基準</span><span class="sxs-lookup"><span data-stu-id="7dd56-183">ISO/IEC 27018:2014 code of practice</span></span>](https://aka.ms/ISO.IEC_27018.2014)
- [<span data-ttu-id="7dd56-184">Microsoft Common Controls Hub コンプライアンス フレームワーク</span><span class="sxs-lookup"><span data-stu-id="7dd56-184">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="7dd56-185">Microsoft エンタープライズ クラウドおよびテクニカル サービスのデータ アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="7dd56-185">Data access policies for Microsoft enterprise cloud and technical services</span></span>](https://www.microsoft.com/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms)
- [<span data-ttu-id="7dd56-186">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="7dd56-186">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="7dd56-187">Microsoft Government クラウド</span><span class="sxs-lookup"><span data-stu-id="7dd56-187">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="7dd56-188">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7dd56-188">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="7dd56-189">サービスの背景解説をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="7dd56-189">Download the offering backgrounder</span></span>

<span data-ttu-id="7dd56-190">このサービスに関する背景解説をご覧になりたい場合は、</span><span class="sxs-lookup"><span data-stu-id="7dd56-190">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="7dd56-191">[PDF](https://download.microsoft.com/download/F/D/A/FDA4697E-D72D-4513-8626-A5F294DC7A0F/ISOIEC_27018_Compliance_Backgrounder.pdf) ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7dd56-191">Download the [PDF](https://download.microsoft.com/download/F/D/A/FDA4697E-D72D-4513-8626-A5F294DC7A0F/ISOIEC_27018_Compliance_Backgrounder.pdf).</span></span>
