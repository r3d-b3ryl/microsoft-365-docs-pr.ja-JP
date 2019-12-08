---
title: スペインの Esquema Nacional de Seguridad (ENS) のハイ レベルなセキュリティ対策
description: マイクロソフトはスペインの Esquema Nacional de Seguridad (国家のセキュリティの枠組み) の認定を取得しています。
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
ms.openlocfilehash: 2aa99ca339f6842447fd9e440960bec327c38025
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859927"
---
# <a name="spain-esquema-nacional-de-seguridad-ens-high-level-security-measures"></a><span data-ttu-id="ea91c-104">スペインの Esquema Nacional de Seguridad (ENS) のハイ レベルなセキュリティ対策</span><span class="sxs-lookup"><span data-stu-id="ea91c-104">Spain Esquema Nacional de Seguridad (ENS) High-Level Security Measures</span></span>

## <a name="spain-ens-overview"></a><span data-ttu-id="ea91c-105">ENS (スペイン) の概要</span><span class="sxs-lookup"><span data-stu-id="ea91c-105">Spain ENS overview</span></span>

<span data-ttu-id="ea91c-106">スペイン政府は 2007 年に 11/2007 の法律を制定しました。国民が政府機関の公的なサービスに電子的にアクセスするための法的な枠組みを定めた法律です。</span><span class="sxs-lookup"><span data-stu-id="ea91c-106">In 2007, the Spanish government enacted Law 11/2007, which established a legal framework to give citizens electronic access to government and public services.</span></span> <span data-ttu-id="ea91c-107">この法律は、Esquema Nacional de Seguridad (国家のセキュリティの枠組み) の基盤になっており、その枠組みを規制するのが Royal Decree (王室令) (RD) 3/2010 です。</span><span class="sxs-lookup"><span data-stu-id="ea91c-107">This law is the basis for Esquema Nacional de Seguridad (National Security Framework), which is governed by Royal Decree (RD) 3/2010.</span></span> <span data-ttu-id="ea91c-108">この枠組みの目的は、電子サービスの信頼性を高めることであり、データや情報やサービスのアクセス、整合性、可用性、信頼性、機密性、追跡可能性、保全性を確保することです。</span><span class="sxs-lookup"><span data-stu-id="ea91c-108">The goal of the framework is to build trust in the provision of electronic services, and ensure the access, integrity, availability, authenticity, confidentiality, traceability, and preservation of data, information, and services.</span></span>

<span data-ttu-id="ea91c-109">この枠組みの対象になるのは、クラウド サービスを購入するスペイン国内のすべての公共機関や政府機関と、情報通信技術 (ICT) のプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="ea91c-109">The framework applies to all public organizations and government agencies in Spain that purchase cloud services, as well as to providers of information and communications technologies (ICT).</span></span> <span data-ttu-id="ea91c-110">それらの機関や企業は、セキュリティとプライバシーに関するスペインと EU の基準に準拠しつつ、クラウドやオンプレミスで効果的なセキュリティ対策を実施する際に、その枠組みを守らなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ea91c-110">It guides these agencies and companies in implementing effective controls for security in the cloud and on premises, in compliance with Spanish and EU security and privacy standards.</span></span>

<span data-ttu-id="ea91c-111">この枠組みでは、政府機関とサービス プロバイダーの両方が守らなければならない重要な方針や必須要件を定めています。</span><span class="sxs-lookup"><span data-stu-id="ea91c-111">The framework establishes core policies and mandatory requirements that both government agencies and their service providers must meet.</span></span> <span data-ttu-id="ea91c-112">可用性、信頼性、整合性、機密性、追跡可能性に関する具体的なセキュリティ コントロールを定義しており、その多くは ISO/IEC 27001 に直接かかわっています。</span><span class="sxs-lookup"><span data-stu-id="ea91c-112">It defines a set of specific security controls — (many of which align directly with ISO/IEC 27001) — relating to availability, authenticity, integrity, confidentiality, and traceability.</span></span> <span data-ttu-id="ea91c-113">情報の機密性 (低、中、高) に応じて、情報を保護するために実施しなければならないセキュリティ対策が決まっています。</span><span class="sxs-lookup"><span data-stu-id="ea91c-113">The sensitivity of the information — low, intermediate, or high — determines the security measures that must be applied to protect it.</span></span>

<span data-ttu-id="ea91c-114">どの政府機関も、セキュリティに関してリスク管理の手法を採用することが義務付けられています。つまり、リスクを洗い出し、分析したうえで、それぞれのリスクに適したセキュリティ コントロールを実施する、ということです。</span><span class="sxs-lookup"><span data-stu-id="ea91c-114">Each government agency is required to adopt a risk-management approach to security, whereby they identify and assess risks, and then apply security controls appropriate to those risks.</span></span> <span data-ttu-id="ea91c-115">サービス プロバイダーも、さまざまな手順や機能や操作の安全性を確保し、各種の機関が法令に準拠できるようにするために、非常に厳格な枠組みの要件を守らなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ea91c-115">Service providers, too, must comply with the stringent framework requirements to help ensure that their procedures, technical capacities, and operations are secure and enable agencies to comply with the regulations.</span></span>

<span data-ttu-id="ea91c-116">この枠組みでは、認定制度を定めています。この認定は、機密性の低い情報を取り扱うシステムでは任意ですが、中レベルから高レベルの機密情報を取り扱うシステムでは必須になっています。</span><span class="sxs-lookup"><span data-stu-id="ea91c-116">The framework prescribes an accreditation process that is voluntary for systems handling information of low sensitivity, but mandatory for systems handling information at an intermediate or high level of sensitivity.</span></span> <span data-ttu-id="ea91c-117">監査は、認定された独立監査人によって実施されます。</span><span class="sxs-lookup"><span data-stu-id="ea91c-117">An audit is performed by an accredited independent auditor.</span></span> <span data-ttu-id="ea91c-118">監査レポートの精査という段階を経てはじめて、リスク管理の対策が認定プロセスの最終段階で承認される運びになります。</span><span class="sxs-lookup"><span data-stu-id="ea91c-118">The report is then reviewed in a process of certification before risk-management controls are accepted in the final step of accreditation.</span></span>

## <a name="microsoft-and-spain-ens-high-level-security-measures"></a><span data-ttu-id="ea91c-119">マイクロソフトと ENS (スペイン) のハイ レベルなセキュリティ対策</span><span class="sxs-lookup"><span data-stu-id="ea91c-119">Microsoft and Spain ENS high-level security measures</span></span>

<span data-ttu-id="ea91c-120">Microsoft Azure と Microsoft Office 365 は、独立監査人である BDO の厳しい審査を経て、正式な認定証を取得しました。</span><span class="sxs-lookup"><span data-stu-id="ea91c-120">Microsoft Azure and Microsoft Office 365 have gone through a rigorous assessment by BDO, an independent auditor, which issued an official statement of their compliance.</span></span> <span data-ttu-id="ea91c-121">BDO は、両方のサービスにおけるセキュリティ対策、情報システムとデータ処理に関する機能が RD 3/2010 に高水準に準拠しており、是正措置が不要であると報告しています。</span><span class="sxs-lookup"><span data-stu-id="ea91c-121">BDO reports that the security measures in both services, and their information systems and data processing facilities, comply at the high level with RD 3/2010 without requiring any corrective measures.</span></span> <span data-ttu-id="ea91c-122">マイクロソフトは、この認定をスペインで取得した最初の超大規模クラウド サービス プロバイダーになりました。</span><span class="sxs-lookup"><span data-stu-id="ea91c-122">Microsoft was the first hyperscale cloud service provider to receive this certification in Spain.</span></span>

<span data-ttu-id="ea91c-123">Microsoft Cloud における ENS (スペイン) のハイ レベルなセキュリティ対策についてのメリットを確認してください。[スペインの ENS バックグラウンダーをダウンロードする](https://aka.ms/spainens-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="ea91c-123">Learn about the benefits of Spain ENS High-Level Security Measures on the Microsoft Cloud: [Download the Spain ENS backgrounder](https://aka.ms/spainens-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="ea91c-124">対象となるマイクロソフトのクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="ea91c-124">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="ea91c-125">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="ea91c-125">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="ea91c-126">Office 365</span><span class="sxs-lookup"><span data-stu-id="ea91c-126">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="ea91c-127">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="ea91c-127">Audits, reports, and certificates</span></span>

<span data-ttu-id="ea91c-128">認定の有効期間は 2 年です。また、1 年ごとのサーベイランス監査が必要です。</span><span class="sxs-lookup"><span data-stu-id="ea91c-128">The certification is valid for two years, with an annual surveillance audit.</span></span>

### <a name="azure"></a><span data-ttu-id="ea91c-129">Azure</span><span class="sxs-lookup"><span data-stu-id="ea91c-129">Azure</span></span>

- [<span data-ttu-id="ea91c-130">Azure National Security Framework ENS 認定証</span><span class="sxs-lookup"><span data-stu-id="ea91c-130">Azure National Security Framework ENS certificate</span></span>](https://aka.ms/AzureNationalSecurityFrameworkENSCertificate)
- [<span data-ttu-id="ea91c-131">Azure Spanish National Security Framework (ENS) 監査レポート</span><span class="sxs-lookup"><span data-stu-id="ea91c-131">Azure Spanish National Security Framework (ENS) Audit Report</span></span>](https://aka.ms/AzureNationalSecurityFrameworkAuditReport)
- [<span data-ttu-id="ea91c-132">Azure Informe Auditoria ENS</span><span class="sxs-lookup"><span data-stu-id="ea91c-132">Azure Informe Auditoria ENS (Spanish)</span></span>](https://aka.ms/AzureInformeAuditoriaENS)
- [<span data-ttu-id="ea91c-133">Azure National Security Framework certificado ENS</span><span class="sxs-lookup"><span data-stu-id="ea91c-133">Azure National Security Framework Certificado ENS (Spanish)</span></span>](https://aka.ms/AzureNationalSecurityFrameworkCertificadoENS)

### <a name="office-365"></a><span data-ttu-id="ea91c-134">Office 365</span><span class="sxs-lookup"><span data-stu-id="ea91c-134">Office 365</span></span>

- [<span data-ttu-id="ea91c-135">Office 365 National Security Framework ENS 認定証</span><span class="sxs-lookup"><span data-stu-id="ea91c-135">Office 365 National Security Framework ENS Certificate</span></span>](https://aka.ms/Office365NationalSecurityFrameworkENSCertificate)
- [<span data-ttu-id="ea91c-136">Office 365 Spanish National Security Framework (ENS) 監査レポート</span><span class="sxs-lookup"><span data-stu-id="ea91c-136">Office 365 Spanish National Security Framework (ENS) Audit Report</span></span>](https://aka.ms/Office365NationalSecurityFrameworkAuditReport)
- [<span data-ttu-id="ea91c-137">Office 365 Informe Auditoria ENS (スペイン語)</span><span class="sxs-lookup"><span data-stu-id="ea91c-137">Office 365 Informe Auditoria ENS (Spanish)</span></span>](https://aka.ms/Office365InformeAuditoriaENS)
- [<span data-ttu-id="ea91c-138">Office 365 National Security Framework certificado ENS (スペイン語)</span><span class="sxs-lookup"><span data-stu-id="ea91c-138">Office 365 National Security Framework Certificado ENS (Spanish)</span></span>](https://aka.ms/Office365NationalSecurityFrameworkCertificadoENS)

## <a name="frequently-asked-questions"></a><span data-ttu-id="ea91c-139">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ea91c-139">Frequently asked questions</span></span>

<span data-ttu-id="ea91c-140">**監査レポートと認定証のコピーはどのようにして入手できますか?**</span><span class="sxs-lookup"><span data-stu-id="ea91c-140">**How can I get copies of the audit reports and certifications?**</span></span>

<span data-ttu-id="ea91c-141">[Service Trust Portal](https://aka.ms/stphelp) には、スペイン語と英語の両方の監査レポートと認定証が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea91c-141">The [Service Trust Portal](https://aka.ms/stphelp) provides the audit reports and certifications in both Spanish and English.</span></span> <span data-ttu-id="ea91c-142">お客様の監査人は、そのレポートに基づいて、マイクロソフト クラウド サービスの監査結果とお客様の法的規制要件を比較できます。</span><span class="sxs-lookup"><span data-stu-id="ea91c-142">Your auditors can use them to compare Microsoft cloud services results with your own legal and regulatory requirements.</span></span>

<span data-ttu-id="ea91c-143">**私の組織のコンプライアンス順守は何から始めればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ea91c-143">**Where do I start with my organization’s own compliance effort?**</span></span>

<span data-ttu-id="ea91c-144">お客様の組織が Azure または Office 365 を使用している場合は、お客様独自の認定プロセスの一環として、ENS マイクロソフト監査レポートと認定証をご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="ea91c-144">If your organization is using Azure or Office 365, you can use ENS Microsoft audit reports and accreditation as part of your own accreditation process.</span></span> <span data-ttu-id="ea91c-145">ただしその場合も、お客様の責任で、コンプライアンスの実施状況や組織内の対策やプロセスがその枠組みに沿っているかどうかを監査人が評価するよう手配する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea91c-145">However, you are responsible for engaging an auditor to evaluate your implementation for compliance, and for ensuring that the controls and processes within your own organization align with the framework.</span></span>

## <a name="resources"></a><span data-ttu-id="ea91c-146">リソース</span><span class="sxs-lookup"><span data-stu-id="ea91c-146">Resources</span></span>

- <span data-ttu-id="ea91c-147">スペインの Esquema Nacional de Seguridad ([スペイン語](https://administracionelectronica.gob.es/pae_Home/pae_Estrategias/pae_Seguridad_Inicio/pae_Esquema_Nacional_de_Seguridad.html?idioma=sp#.Vwxp82mcGM8)と[英語](https://administracionelectronica.gob.es/pae_Home/pae_Estrategias/pae_Seguridad_Inicio/pae_Esquema_Nacional_de_Seguridad.html?idioma=en#.VwvcgmmcGM9))</span><span class="sxs-lookup"><span data-stu-id="ea91c-147">Esquema Nacional de Seguridad of Spain ([Spanish](https://administracionelectronica.gob.es/pae_Home/pae_Estrategias/pae_Seguridad_Inicio/pae_Esquema_Nacional_de_Seguridad.html?idioma=sp#.Vwxp82mcGM8) and [English](https://administracionelectronica.gob.es/pae_Home/pae_Estrategias/pae_Seguridad_Inicio/pae_Esquema_Nacional_de_Seguridad.html?idioma=en#.VwvcgmmcGM9))</span></span>
- [<span data-ttu-id="ea91c-148">マイクロソフト オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="ea91c-148">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="ea91c-149">Microsoft セキュリティ センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ea91c-149">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="ea91c-150">サービスの背景資料をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ea91c-150">Download the offering backgrounder</span></span>

<span data-ttu-id="ea91c-151">このサービスに関する背景資料が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="ea91c-151">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="ea91c-152">[PDF](https://download.microsoft.com/download/2/3/2/23208181-BA86-4011-8B4A-3CA7E8E383A1/ENS-Spain-Compliance.pdf) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ea91c-152">Download the [PDF](https://download.microsoft.com/download/2/3/2/23208181-BA86-4011-8B4A-3CA7E8E383A1/ENS-Spain-Compliance.pdf).</span></span>
