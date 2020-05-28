---
title: クラウドで個人データを保護するための ISO/IEC 27018 実施基準
description: Microsoft は、クラウド プライバシーに関するこの実施基準を順守した初のクラウド プロバイダーです。
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
ms.openlocfilehash: a5e5879bf176c7be72ead3c80c91934d0a1c5a01
ms.sourcegitcommit: daad5f2f1994a812c2b9c78e7dd148d10c51f61d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "44254416"
---
# <a name="isoiec-27018-code-of-practice-for-protecting-personal-data-in-the-cloud"></a><span data-ttu-id="ae257-104">クラウドで個人データを保護するための ISO/IEC 27018 実施基準</span><span class="sxs-lookup"><span data-stu-id="ae257-104">ISO/IEC 27018 Code of Practice for Protecting Personal Data in the Cloud</span></span>

## <a name="isoiec-27018-overview"></a><span data-ttu-id="ae257-105">ISO/IEC 27018 の概要</span><span class="sxs-lookup"><span data-stu-id="ae257-105">ISO/IEC 27018 overview</span></span>

<span data-ttu-id="ae257-106">国際標準化機構 (ISO) は中立的な非政府組織で、国際基準を自主的に策定する世界最大の組織です。</span><span class="sxs-lookup"><span data-stu-id="ae257-106">The International Organization for Standardization (ISO) is an independent nongovernmental organization and the world's largest developer of voluntary international standards.</span></span> <span data-ttu-id="ae257-107">ISO/IEC 27000 基準ファミリは、すべての形態および規模の組織が情報資産のセキュリティを確保できるよう支援します。</span><span class="sxs-lookup"><span data-stu-id="ae257-107">The ISO/IEC 27000 family of standards helps organizations of every type and size keep information assets secure.</span></span>

<span data-ttu-id="ae257-108">2014 年、ISO は、ISO/IEC 27001 の補遺として、クラウド プライバシーに関する初めての国際実施基準である ISO/IEC 27018:2014 を採用しました。</span><span class="sxs-lookup"><span data-stu-id="ae257-108">In 2014, the ISO adopted ISO/IEC 27018:2014, an addendum to ISO/IEC 27001, the first international code of practice for cloud privacy.</span></span> <span data-ttu-id="ae257-109">EU データ保護法に基づいて、個人を特定できる情報 (PII) の処理者の役割を担うクラウド サービス プロバイダー (CSP) に、PII 保護のためのリスク評価と最新制御の実装に関する特定のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ae257-109">Based on EU data-protection laws, it gives specific guidance to cloud service providers (CSPs) acting as processors of personally identifiable information (PII) on assessing risks and implementing state-of-the-art controls for protecting PII.</span></span>

<span data-ttu-id="ae257-110">Microsoft と ISO/IEC 27018</span><span class="sxs-lookup"><span data-stu-id="ae257-110">Microsoft and ISO/IEC 27018</span></span>

<span data-ttu-id="ae257-111">Microsoft Azure と Azure Germany は、年に 1 回以上、ISO/IEC 27001 および ISO/IEC 27018 への準拠に関して、第三者の公認認定機関の監査を受けています。この機関は、該当するセキュリティ コントロールが導入されていて、効果的に運用されていることを独自に検証します。</span><span class="sxs-lookup"><span data-stu-id="ae257-111">At least once a year, Microsoft Azure and Azure Germany are audited for compliance with ISO/IEC 27001 and ISO/IEC 27018 by an accredited third-party certification body, providing independent validation that applicable security controls are in place and operating effectively.</span></span> <span data-ttu-id="ae257-112">このコンプライアンスの検証プロセスの一環として、監査人は、適用宣言書で、対象となる Microsoft クラウド サービスおよび法人向けテクニカル サポート サービスに、Azure で PII を保護するための ISO/IEC 27018 制御が組み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae257-112">As part of this compliance verification process, the auditors validate in their statement of applicability that Microsoft in-scope cloud services and commercial technical support services have incorporated ISO/IEC 27018 controls for the protection of PII in Azure.</span></span> <span data-ttu-id="ae257-113">コンプライアンスを確保し続けるために、Microsoft クラウド サービスは年 1 回第三者による審査を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae257-113">To remain compliant, Microsoft cloud services must be subject to annual third-party reviews.</span></span>

<span data-ttu-id="ae257-114">ISO/IEC 27001 基準と ISO/IEC 27018 の実施基準への準拠が、(この実施基準を採用した初めての主要クラウド プロバイダーである) Microsoft のプライバシー ポリシーと手順が堅牢で、高い水準が維持されていることを証明しています。</span><span class="sxs-lookup"><span data-stu-id="ae257-114">By following the standards of ISO/IEC 27001 and the code of practice embodied in ISO/IEC 27018, Microsoft (the first major cloud provider to incorporate this code of practice) demonstrates that its privacy policies and procedures are robust and in line with its high standards.</span></span>

- <span data-ttu-id="ae257-115">**Microsoft クラウド サービスの顧客がデータの保存場所を把握している。**</span><span class="sxs-lookup"><span data-stu-id="ae257-115">**Customers of Microsoft cloud services know where their data is stored.**</span></span> <span data-ttu-id="ae257-116">ISO/IEC 27018 では、認定 CSP が、データの保存先の国を顧客に知らせる必要があります。したがって、Microsoft クラウド サービスの顧客には、適用される情報セキュリティ ルールに従うために必要な可視性が提供されています。</span><span class="sxs-lookup"><span data-stu-id="ae257-116">Because ISO/IEC 27018 requires certified CSPs to inform customers of the countries in which their data may be stored, Microsoft cloud service customers have the visibility they need to comply with any applicable information security rules.</span></span>
- <span data-ttu-id="ae257-117">**お客様のデータは、明確な同意がない限りマーケティングや広告に使用されない。**</span><span class="sxs-lookup"><span data-stu-id="ae257-117">**Customer data won't be used for marketing or advertising without explicit consent.**</span></span> <span data-ttu-id="ae257-118">CSP によっては、顧客データを自身の商業目的でターゲットを絞った広告などに使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="ae257-118">Some CSPs use customer data for their own commercial ends, including for targeted advertising.</span></span> <span data-ttu-id="ae257-119">Microsoft では対象となるエンタープライズ クラウド サービスに ISO/IEC 27018 を採用しているため、明確な同意がない限り、お客様のデータがこのような目的で使用されることありません。その点に関しては、お客様は安心して利用できます。また、このような同意が、クラウド サービスの使用条件になることもありません。</span><span class="sxs-lookup"><span data-stu-id="ae257-119">Because Microsoft has adopted ISO/IEC 27018 for its in-scope enterprise cloud services, customers can rest assured that their data will never be used for such purposes without explicit consent, and that consent cannot be a condition for use of the cloud service.</span></span>
- <span data-ttu-id="ae257-120">**Microsoft の顧客は PII の状況を把握できる。**</span><span class="sxs-lookup"><span data-stu-id="ae257-120">**Microsoft customers know what's happening with their PII.**</span></span> <span data-ttu-id="ae257-121">ISO/IEC 27018 には、適正な期間内に個人情報の返却、移行、および安全な破棄を可能にするポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="ae257-121">ISO/IEC 27018 requires a policy that allows for the return, transfer, and secure disposal of personal information within a reasonable period of time.</span></span> <span data-ttu-id="ae257-122">顧客データにアクセスする必要がある他の企業と連携する場合、Microsoft ではこうした二次処理者の身元を積極的に開示します。</span><span class="sxs-lookup"><span data-stu-id="ae257-122">If Microsoft works with other companies that need access to your customer data, Microsoft proactively discloses the identities of those sub-processors.</span></span>
- <span data-ttu-id="ae257-123">**顧客データの開示に対する要求には法的拘束力がある場合にのみ応じる。**</span><span class="sxs-lookup"><span data-stu-id="ae257-123">**Microsoft complies only with legally binding requests for disclosure of customer data.**</span></span> <span data-ttu-id="ae257-124">Microsoft がこうした要求に応じる必要がある場合 (犯罪捜査の場合など)、法律で禁止されていない限り、必ずお客様に通知します。</span><span class="sxs-lookup"><span data-stu-id="ae257-124">If Microsoft must comply with such a request (as in the case of a criminal investigation), it will always notify the customer unless it is prohibited by law from doing so.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="ae257-125">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="ae257-125">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="ae257-126">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="ae257-126">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="ae257-127">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="ae257-127">Azure DevOps Services</span></span>
- <span data-ttu-id="ae257-128">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ae257-128">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="ae257-129">Dynamics 365、Dynamics 365、Dynamics 365 ドイツ</span><span class="sxs-lookup"><span data-stu-id="ae257-129">Dynamics 365, Dynamics 365, and Dynamics 365 Germany</span></span>
- <span data-ttu-id="ae257-130">Microsoft Professional Services: Azure、Dynamics 365、Intune と、Microsoft 365 for business の Medium Business および Enterprise のお客様への Premier およびオンプレミス サポート</span><span class="sxs-lookup"><span data-stu-id="ae257-130">Microsoft Professional Services: Premier and On Premises for Azure, Dynamics 365, Intune, and for medium business and enterprise customers of Microsoft 365 for business</span></span>
- <span data-ttu-id="ae257-131">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ae257-131">Microsoft Graph</span></span>
- <span data-ttu-id="ae257-132">Microsoft Healthcare Bot</span><span class="sxs-lookup"><span data-stu-id="ae257-132">Microsoft Healthcare Bot</span></span>
- <span data-ttu-id="ae257-133">Intune</span><span class="sxs-lookup"><span data-stu-id="ae257-133">Intune</span></span>
- <span data-ttu-id="ae257-134">Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="ae257-134">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="ae257-135">Power Automate (旧称 Microsoft Flow): スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービスとしてのクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="ae257-135">Power Automate (formerly Microsoft Flow): cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="ae257-136">Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="ae257-136">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- <span data-ttu-id="ae257-137">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ae257-137">Office 365 Germany</span></span>
- <span data-ttu-id="ae257-138">OMS Service Map</span><span class="sxs-lookup"><span data-stu-id="ae257-138">OMS Service Map</span></span>
- <span data-ttu-id="ae257-139">PowerApps クラウド サービス: スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス</span><span class="sxs-lookup"><span data-stu-id="ae257-139">PowerApps cloud service: either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="ae257-140">Power BI クラウド サービス: スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス</span><span class="sxs-lookup"><span data-stu-id="ae257-140">Power BI cloud service: either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="ae257-141">Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="ae257-141">Power BI Embedded</span></span>
- <span data-ttu-id="ae257-142">Power Virtual Agents</span><span class="sxs-lookup"><span data-stu-id="ae257-142">Power Virtual Agents</span></span>
- <span data-ttu-id="ae257-143">Microsoft 脅威エキスパート</span><span class="sxs-lookup"><span data-stu-id="ae257-143">Microsoft Threat Experts</span></span>
- <span data-ttu-id="ae257-144">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="ae257-144">Microsoft Stream</span></span>
- <span data-ttu-id="ae257-145">Windows Defender ATP - エンドポイントでの検出と対応、自動の調査と修復、セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="ae257-145">Windows Defender ATP — Endpoint Detection & Response, Automatic Investigation & Remediation, Secure Score</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="ae257-146">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="ae257-146">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="ae257-147">監査サイクル</span><span class="sxs-lookup"><span data-stu-id="ae257-147">Audit cycle</span></span>

<span data-ttu-id="ae257-148">Microsoft クラウド サービスおよび法人向けテクニカル サポート サービスは、年 1 回、ISO/IEC 27001 の認定プロセスの一環として、ISO/IEC 27018 実施基準に関する監査を受けています。</span><span class="sxs-lookup"><span data-stu-id="ae257-148">Microsoft cloud and commercial technical support services are audited once a year for the ISO/IEC 27018 code of practice as part of the certification process for ISO/IEC 27001.</span></span>

### <a name="audits-and-reports"></a><span data-ttu-id="ae257-149">監査とレポート</span><span class="sxs-lookup"><span data-stu-id="ae257-149">Audits and reports</span></span>

- [<span data-ttu-id="ae257-150">Azure、Dynamics 365、および Online Services: ISO27018 の証明書</span><span class="sxs-lookup"><span data-stu-id="ae257-150">Azure, Dynamics 365, and Online Services: ISO27018 Certificate</span></span>](https://aka.ms/azureiso27018cert)
- [<span data-ttu-id="ae257-151">Azure、Dynamics 365、Online Services: ISO27018 の評価レポート</span><span class="sxs-lookup"><span data-stu-id="ae257-151">AAzure, Dynamics 365, and Online Services: ISO27018 Assessment Report</span></span>](https://aka.ms/azureiso27001report)
- [<span data-ttu-id="ae257-152">Azure Germany: ISO27018 クラウドで個人データを保護するための実施基準証明書</span><span class="sxs-lookup"><span data-stu-id="ae257-152">Azure Germany: ISO27018 Code of Practice for Protecting Personal Data in the Cloud Certificate</span></span>](https://servicetrust.microsoft.com/Documents/ComplianceReports?downloadDocument=1&documentId=6a0dab80-8382-4af6-980c-ed2ed9a341c6)

### <a name="office-365"></a><span data-ttu-id="ae257-153">Office 365</span><span class="sxs-lookup"><span data-stu-id="ae257-153">Office 365</span></span>

- [<span data-ttu-id="ae257-154">Office 365: ISO 27001、27018、27017 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="ae257-154">Office 365: ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)
- [<span data-ttu-id="ae257-155">Yammer ISO 27018 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="ae257-155">Yammer ISO 27018 Audit Assessment Report</span></span>](https://aka.ms/YammerISO27018Auditreport)

### <a name="azure-devops-services"></a><span data-ttu-id="ae257-156">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="ae257-156">Azure DevOps Services</span></span>

- [<span data-ttu-id="ae257-157">Azure DevOps Services: ISO27018 証明書 PII 665918</span><span class="sxs-lookup"><span data-stu-id="ae257-157">Azure DevOps Services: ISO27018 Certificate PII 665918</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2062252)

## <a name="frequently-asked-questions"></a><span data-ttu-id="ae257-158">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ae257-158">Frequently asked questions</span></span>

<span data-ttu-id="ae257-159">**ISO/IEC 27018 はだれに適用されますか?**</span><span class="sxs-lookup"><span data-stu-id="ae257-159">**To whom does ISO/IEC 27018 apply?**</span></span>

<span data-ttu-id="ae257-160">この実施基準は、他の組織のために PII 処理契約を結んでいる CSP に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ae257-160">This code of practice applies to CSPs that process PII under contract for other organizations.</span></span> <span data-ttu-id="ae257-161">また、Microsoft では、これは CSP のサポートにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="ae257-161">At Microsoft, it also applies to the support of those CSPs.</span></span>

<span data-ttu-id="ae257-162">**「個人情報管理者」と「個人情報処理者」はどう違うのですか?**</span><span class="sxs-lookup"><span data-stu-id="ae257-162">**What is the difference between 'personal information controllers' and 'personal information processors'?**</span></span>

<span data-ttu-id="ae257-163">ISO/IEC 27018 のコンテキストでは、次のような違いがあります。</span><span class="sxs-lookup"><span data-stu-id="ae257-163">In the context of ISO/IEC 27018:</span></span>

- <span data-ttu-id="ae257-164">「管理者」は、個人情報の収集、保持、処理、または使用を管理します。他の企業に代わって個人情報を管理する管理担当者も含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae257-164">'Controllers' control the collection, holding, processing, or use of personal information; they include those who control it on another company's behalf.</span></span>
- <span data-ttu-id="ae257-165">「処理者」は、管理者に代わって情報を処理します。情報の使用方法または処理の目的に関する決定を下すことはありません。</span><span class="sxs-lookup"><span data-stu-id="ae257-165">'Processors' process information on behalf of controllers; they do not make decisions as to how to use the information or the purposes of the processing.</span></span> <span data-ttu-id="ae257-166">(ユーザーのベンダーである) Microsoft は、エンタープライズ クラウド サービスを提供する際に、情報処理者の役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="ae257-166">In providing its enterprise cloud services, Microsoft (as a vendor to you) is an information processor.</span></span>

<span data-ttu-id="ae257-167">**Microsoft の ISO/IEC 27018 コンプライアンス情報はどこで確認できますか?**</span><span class="sxs-lookup"><span data-stu-id="ae257-167">**Where can I view Microsoft compliance information for ISO/IEC 27018?**</span></span>

- <span data-ttu-id="ae257-168">[Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016)、[Microsoft Professional Services](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270)、[Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016)の BSI から ISO/IEC 27018 証明書を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ae257-168">You can review the ISO/IEC 27018 certificates from BSI for [Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016), [Microsoft Professional Services](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270), and [Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016).</span></span>
- <span data-ttu-id="ae257-169">また、ISO/IEC 27018 証明書が [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert)、[Office 365](https://aka.ms/Office365-Cert)、[Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159) に基づいている BSI の ISO/IEC 27001 を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae257-169">You can also review ISO/IEC 27001 certificates from BSI upon which ISO/IEC 27018 certification is based for [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert), [Office 365](https://aka.ms/Office365-Cert), and [Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159).</span></span>
- <span data-ttu-id="ae257-170">Microsoft が ISO/IEC 27018 に準拠していることを検証した独立した監査人である BSI のレポートを確認するには、[Service Trust Portal](https://aka.ms/stphelp) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="ae257-170">To review the BSI reports, the independent auditor that validated Microsoft compliance with ISO/IEC 27018, visit the [Service Trust Portal](https://aka.ms/stphelp).</span></span>

<span data-ttu-id="ae257-171">**Microsoft のコンプライアンスを自分の組織の認定プロセスに利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="ae257-171">**Can I use Microsoft's compliance in my organization's certification process?**</span></span>

<span data-ttu-id="ae257-172">はい。</span><span class="sxs-lookup"><span data-stu-id="ae257-172">Yes.</span></span> <span data-ttu-id="ae257-173">ISO/IEC 27018 への準拠が、お客様のビジネスおよび Microsoft の対象企業向けクラウド サービスへの展開において重要である場合、Microsoft の ISO/IEC 27018 への準拠証明書と Microsoft の ISO/IEC 27001 への準拠認証をコンプライアンス評価に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae257-173">If compliance with ISO/IEC 27018 is important for your business and implementations deployed on any of Microsoft in-scope enterprise cloud services, you can use Microsoft's attestation of compliance with ISO/IEC 27018 with Microsoft's certification for ISO/IEC 27001 in your compliance assessment.</span></span>

<span data-ttu-id="ae257-174">ただし、コンプライアンスや、組織内の統制およびプロセスに関して、実装を評価する査定人の手配の責任は、審査を受ける組織が負うものとします。</span><span class="sxs-lookup"><span data-stu-id="ae257-174">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="ae257-175">Microsoft コンプライアンス スコアを使用してリスクを評価する</span><span class="sxs-lookup"><span data-stu-id="ae257-175">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="ae257-176">[Microsoft コンプライアンス スコア](compliance-score.md)は、[Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)のプレビュー機能で、組織のコンプライアンスの状況を把握し、リスクを軽減するための処置を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae257-176">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="ae257-177">[コンプライアンス スコアの設定](compliance-score-setup.md)後、[**テンプレート**] ドロップダウン メニューから事前に構成された [ISO 27018 テンプレート](https://go.microsoft.com/fwlink/?linkid=2117523)を選択してこの規制の要件を満たすようにします。</span><span class="sxs-lookup"><span data-stu-id="ae257-177">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [ISO 27018 template](https://go.microsoft.com/fwlink/?linkid=2117523) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="ae257-178">リソース</span><span class="sxs-lookup"><span data-stu-id="ae257-178">Resources</span></span>

- [<span data-ttu-id="ae257-179">ISO/IEC 27018:2014 実施基準</span><span class="sxs-lookup"><span data-stu-id="ae257-179">ISO/IEC 27018:2014 code of practice</span></span>](https://aka.ms/ISO.IEC_27018.2014)
- [<span data-ttu-id="ae257-180">Microsoft Common Controls Hub コンプライアンス フレームワーク</span><span class="sxs-lookup"><span data-stu-id="ae257-180">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="ae257-181">Microsoft エンタープライズ クラウドおよびテクニカル サービスのデータ アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ae257-181">Data access policies for Microsoft enterprise cloud and technical services</span></span>](https://www.microsoft.com/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms)
- [<span data-ttu-id="ae257-182">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="ae257-182">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="ae257-183">Microsoft Government クラウド</span><span class="sxs-lookup"><span data-stu-id="ae257-183">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="ae257-184">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ae257-184">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
